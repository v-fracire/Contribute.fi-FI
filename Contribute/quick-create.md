---
title: 'Pikaopas: Salaisen koodin asettaminen ja noutaminen Azure Key Vaultista | Microsoft Docs'
description: 'Pikaopas: Salaisen koodin asettaminen ja noutaminen Azure Key Vaultista'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages, keyvault-platforms
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8b758274203748bb6e04c03dec5de38fb77947b4
ms.sourcegitcommit: b0105f322f91bb4dbde47f6da35b3c12271d5b03
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/29/2018
ms.locfileid: "43239565"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a>Pikaopas: Salaisen koodin asettaminen ja noutaminen Azure Key Vaultista

Tämän pikaoppaan avulla opit tallentamaan salaisen koodin Key Vaultiin ja noutamaan sen verkkosovellusta käyttämällä. Jotta voit nähdä salaisen koodin arvon, tämä on suoritettava Azuressa. Pikaoppaassa käytetään Node.js:ää ja hallitun palvelun käyttäjätietoja (MSI).

> [!div class="checklist"]
> * Key Vaultin luominen.
> * Salaisen koodin tallentaminen Key Vaultiin.
> * Salaisen koodin noutaminen Key Vaultista.
> * Azure-verkkosovelluksen luominen.
> * [Hallitun palvelun käyttäjätietojen käyttöönotto](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).
> * Anna verkkosovellukselle tarvittavat oikeudet tietojen lukemiseen Key Vaultista.

Varmista ennen jatkamista, että tunnet [peruskäsitteet](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).

>[!NOTE]
Alla oleva opetusohjelma edustaa parasta käytäntöä. Syy siihen selviää tutustumalla tiettyihin käsitteisiin. Key Vault on keskussäilö salaisten koodien ohjelmalliseen tallentamiseen. Jotta niin voi tehdä, sovellusten tai käyttäjien on ensin suoritettava Key Vaultin todentaminen eli esitettävä salainen koodi. Lisäksi tietoturvan parhaat käytännöt edellyttävät, että tätä ensimmäistä salaista koodia kierrätetään jaksoittain. Azuressa toimiville [hallitun palvelun käyttäjätietosovelluksille](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) annetaan kuitenkin käyttäjätiedot, joita Azure hallitsee automaattisesti. Tämä auttaa ratkaisemaan **salaisen koodin esittelyongelman**, jossa käyttäjät tai sovellukset voivat noudattaa parhaita käytäntöjä huolehtimatta ensimmäisen salaisen koodin kierrättämisestä.

## <a name="prerequisites"></a>Edellytykset

::: zone pivot="nodejs"
* [Node JS](https://nodejs.org/en/) ::: zone-end

::: zone pivot="dotnet, windows"
* [Visual Studio 2017 -versio 15.7.3 tai uudempi](https://www.microsoft.com/net/download/windows) seuraavilla kuormituksilla:
  * ASP.NET ja verkkokehitys
  * Käyttöympäristöjen välinen .NET Core -kehitys
* [.NET Core 2.1 SDK tai uudempi](https://www.microsoft.com/net/download/windows) :::zone-end

::: zone pivot="dotnet, mac"
* Lisätietoja: [Visual Studio for Macin uudet ominaisuudet](https://visualstudio.microsoft.com/vs/mac/).
:::zone-end

* Git ([lataa](https://git-scm.com/downloads)).
* Azure-tilaus. Jos sinulla ei ole Azure-tilausta, luo [maksuton tili](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) ennen aloittamista.
* [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) -versio 2.0.4 tai uudempi. Tämä on saatavilla Windowsille, Macille ja Linuxille.

## <a name="login-to-azure"></a>Kirjaudu sisään Azureen

Jos haluat kirjautua sisään Azureen komentorivikäyttöliittymää käyttämällä, voit kirjoittaa:

```azurecli
az login
```

## <a name="create-resource-group"></a>Resurssiryhmän luominen

Luo resurssiryhmä [az group create](/cli/azure/group#az-group-create) -komennolla. Azure-resurssiryhmä on looginen säilö, jossa Azure-resursseja otetaan käyttöön ja hallitaan.

Valitse resurssiryhmä ja täytä paikkamerkki.
Seuraava esimerkki luo resurssiryhmän nimeltä *<YourResourceGroupName>* sijaintiin *eastus*.

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

Juuri luomaasi resurssiryhmää käytetään läpi tämän opetusohjelman.

## <a name="create-an-azure-key-vault"></a>Azure Key Vaultin luominen

Seuraavaksi luot Key Vaultin käyttämällä edellisessä vaiheessa luotua resurssiryhmää. Tässä artikkelissa Key Vaultin nimenä käytetään ContosoKeyVaultia, mutta sinun on käytettävä yksilöllistä nimeä. Anna seuraavat tiedot:

* Vaultin nimi – **valitse Key Vaultin nimi tähän**.
* Resurssiryhmän nimi – **valitse resurssiryhmän nimi tähän**.
* Sijainti – **Itä-Yhdysvallat**.

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

Tässä vaiheessa oma Azure-tilisi on ainoa, jolla on valtuudet suorittaa toimia tässä uudessa Vaultissa.

## <a name="add-a-secret-to-key-vault"></a>Salaisen koodin lisääminen Key Vaultiin

Lisäämme nyt salaisen koodin toimintaperiaatteen havainnollistamiseksi. Sinulla voi olla tallessa SQL-yhteysmerkkijono tai jokin muu tieto, joka on pidettävä suojattuna mutta tarjottava sovelluksesi käyttöön. Tässä opetusohjelmassa salasana on nimeltään **AppSecret** ja siihen tallennetaan arvo **MySecret**.

Luo Key Vaultiin salainen koodi nimeltä **AppSecret**, johon tallennetaan arvo **MySecret**. Se tapahtuu kirjoittamalla alla olevat komennot:

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

Voit nähdä salaisen koodin sisältämän arvon vain teksti -muodossa seuraavasti:

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

Tämä komento näyttää salaisen koodin tiedot URI mukaan lukien. Näiden vaiheiden jälkeen sinulla pitäisi olla Azure Key Vaultissa salaisen koodin URI. Kirjoita nämä tiedot muistiin, sillä tarvitset niitä myöhemmin.

## <a name="clone-the-repo"></a>Säilön kloonaaminen

Kloonaa säilö, jotta saat itsellesi paikallisen kopion. Siten voit muokata lähdettä suorittamalla seuraavan komennon:

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a>Riippuvuuksien asentaminen

Tässä osiossa asennetaan riippuvuudet. Suorita tämä komento: cd key-vault-node-quickstart npm install

Tässä projektissa käytettiin kahta solmumoduulia:

* [ms-rest-azure](https://www.npmjs.com/package/ms-rest-azure) 
* [azure-keyvault](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a>Verkkosovelluksen julkaiseminen Azureen

Alla on muutamia suoritettavia vaiheita.

* Ensimmäinen vaihe on luoda [Azure-sovelluspalvelun](https://azure.microsoft.com/services/app-service/) sopimus. Sopimukseen voi tallentaa useita verkkosovelluksia.

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* Seuraavaksi luodaan verkkosovellus. Korvaa seuraavassa esimerkissä <app_name> globaalisti yksilöllisellä sovellusnimellä (kelvollisia merkkejä ovat a–z, 0–9 ja -). Suorituspalvelun arvoksi on asetettu NODE|6.9. Näet kaikki tuetut suorituspalvelut komennolla az webapp list-runtimes

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    Kun verkkosovellus on luotu Azure CLI näyttää seuraavaa esimerkkiä vastaavan tuloksen:

    ```json
    {
      "availabilityState": "Normal",
      "clientAffinityEnabled": true,
      "clientCertEnabled": false,
      "cloningInfo": null,
      "containerSize": 0,
      "dailyMemoryTimeQuota": 0,
      "defaultHostName": "<app_name>.azurewebsites.net",
      "enabled": true,
      "deploymentLocalGitUrl": "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git"
      < JSON data removed for brevity. >
    }
    ```
    Selaa juuri luotuun verkkosovellukseesi, niin sinun tulisi nähdä täysin toimiva verkkosovellus. Korvaa <app_name> yksilöllisellä sovellusnimellä.

    ```text
    http://<app name>.azurewebsites.net
    ```
    Yllä oleva komento luo myös Gitiä käyttävän sovelluksen, jolla voit suorittaa käyttöönoton Azureen paikallisesta Gitistä käsin. 
    Paikallisen Gitin määrittämiseen on käytetty URL-osoitetta https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git

* Käyttöönottokäyttäjän luominen Edellisen komennon valmistuttua voit lisätä Azure-etäkohteen paikalliseen Git-säilöösi. Korvaa <url> Git-etäkohteen URL-osoitteella, jonka sait sovelluksesi Git-käyttöönotosta.

    ```bash
    git remote add azure <url>
    ```
::: zone-end

::: zone pivot="dotnet"

## <a name="open-and-edit-the-solution"></a>Ratkaisun avaaminen ja muokkaaminen

Muokkaa Program.cs-tiedostoa siten, että se voi suorittaa mallin erityisellä Key Vault -nimelläsi:

1. Selaa kansioon key-vault-dotnet-core-quickstart.
2. Avaa key-vault-dotnet-core-quickstart.sln-tiedosto Visual Studio 2017:ssä.
3. Avaa Program.cs-tiedosto ja korvaa *YourKeyVaultName*-paikkamerkki aiemmin luomasi Key Vaultin nimellä.

Tämä ratkaisu käyttää [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication)- ja [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet -kirjastoja.

## <a name="run-the-app"></a>Suorita sovellus

Valitse Visual Studio 2017:n päävalikosta **Virheenkorjaus** > **Aloita** ilman virheenkorjausta. Kun selain avautuu, siirry **Tietoja**-sivulle. Näet **AppSecret**-arvon.

## <a name="publish-the-web-application-to-azure"></a>Verkkosovelluksen julkaiseminen Azureen

Kun julkaiset tämän sovelluksen Azureen, näet sen toiminnassa verkkosovelluksena. Voit myös noutaa salaisen koodin arvon:

1. Valitse Visual Studiossa projekti **key-vault-dotnet-core-quickstart**.
2. Valitse **Julkaise** > **Aloita**.
3. Luo uusi **sovelluspalvelu** ja valitse **Julkaise**.
4. Vaihda sovelluksen nimeksi **keyvaultdotnetcorequickstart**.
5. Valitse **Luo**.

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]

::: zone-end

## <a name="enable-managed-service-identities"></a>Hallitun palvelun käyttäjätietojen käyttöönotto

Azure Key Vault on tapa tallentaa tunnistetietoja, muita avaimia ja salaisia koodeja suojatusti. Koodisi on kuitenkin todennettava Azure Key Vaultiin niiden noutamiseksi. Hallitun palvelun käyttäjätiedot tekevät tästä helpompaa antamalla Azure-palveluille automaattisesti hallitut käyttäjätiedot Azure Active Directoryssa (Azure AD). Voit käyttää näitä käyttäjätietoja todentamisessa mihin tahansa palveluun, joka tukee Azure AD -todentamista – Key Vault mukaan lukien. Tällöin koodin ei tarvitse sisältää tunnistetietoja.

1. Palaa Azure CLI:hin.
2. Luo käyttäjätiedot tälle sovellukselle komennolla assign-identity:

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
>Tässä toimintosarjassa komento vastaa siirtymistä portaaliin ja **Hallitun palvelun käyttäjätiedot** -asetuksen ottamista **käyttöön** verkkosovelluksen ominaisuuksissa.

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a>Oikeuksien määrittäminen sovellukselle salaisten koodien lukemiseksi Key Vaultista

Kun julkaiset sovelluksen Azureen, kirjaa tulos muistiin. Se tulisi olla tällaisessa muodossa:

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

Suorita sen jälkeen tämä komento käyttämällä Key Vaultisi nimeä ja **PrincipalId**-arvoa:

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a>Solmusovelluksen käyttöönotto Azuressa ja salaisen koodin arvon noutaminen

Nyt kun kaikki on valmiina, suorita seuraava komento sovelluksen käyttöönottamiseksi Azuressa.

```bash
git push azure master
```

Kun tämän jälkeen siirryt osoitteeseen https://<app_name>.azurewebsites.net, näet näet salaisen koodin arvon.
Varmista, että korvasit nimen <YourKeyVaultName> oman Vaultisi nimellä ::: zone-end

::: zone pivot="dotnet" Kun nyt suoritat sovelluksen, sinun tulisi nähdä noudettu salaisen koodin arvo.
::: zone-end

## <a name="next-steps"></a>Seuraavat vaiheet

::: zone pivot="nodejs"
* [Azure Key Vaultin aloitussivu](https://azure.microsoft.com/services/key-vault/)
* [Azure Key Vaultin dokumentaatio](https://docs.microsoft.com/azure/key-vault/)
* [Azure SDK For Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* [Azuren REST-ohjelmointirajapinnan viittaus](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end

::: zone pivot="dotnet"
* [Azure Key Vaultin aloitussivu](https://azure.microsoft.com/services/key-vault/)
* [Azure Key Vaultin dokumentaatio](https://docs.microsoft.com/azure/key-vault/)
* [Azure SDK For .NET](https://github.com/Azure/azure-sdk-for-net)
* [Azuren REST-ohjelmointirajapinnan viittaus](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end