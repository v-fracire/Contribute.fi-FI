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
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a><span data-ttu-id="3d9d5-103">Pikaopas: Salaisen koodin asettaminen ja noutaminen Azure Key Vaultista</span><span class="sxs-lookup"><span data-stu-id="3d9d5-103">Quickstart: Set and retrieve a secret from Azure Key Vault</span></span>

<span data-ttu-id="3d9d5-104">Tämän pikaoppaan avulla opit tallentamaan salaisen koodin Key Vaultiin ja noutamaan sen verkkosovellusta käyttämällä.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-104">This quickstart shows you how to store a secret in Key Vault and how to retrieve it using a Web app.</span></span> <span data-ttu-id="3d9d5-105">Jotta voit nähdä salaisen koodin arvon, tämä on suoritettava Azuressa.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-105">To see the secret value you would have to run this on Azure.</span></span> <span data-ttu-id="3d9d5-106">Pikaoppaassa käytetään Node.js:ää ja hallitun palvelun käyttäjätietoja (MSI).</span><span class="sxs-lookup"><span data-stu-id="3d9d5-106">The quickstart uses Node.js and Managed service identities (MSIs)</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="3d9d5-107">Key Vaultin luominen.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-107">Create a Key Vault.</span></span>
> * <span data-ttu-id="3d9d5-108">Salaisen koodin tallentaminen Key Vaultiin.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-108">Store a secret in Key Vault.</span></span>
> * <span data-ttu-id="3d9d5-109">Salaisen koodin noutaminen Key Vaultista.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-109">Retrieve a secret from Key Vault.</span></span>
> * <span data-ttu-id="3d9d5-110">Azure-verkkosovelluksen luominen.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-110">Create an Azure Web Application.</span></span>
> * <span data-ttu-id="3d9d5-111">[Hallitun palvelun käyttäjätietojen käyttöönotto](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span><span class="sxs-lookup"><span data-stu-id="3d9d5-111">[Enable managed service identities](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span></span>
> * <span data-ttu-id="3d9d5-112">Anna verkkosovellukselle tarvittavat oikeudet tietojen lukemiseen Key Vaultista.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-112">Grant the required permissions for the web application to read data from Key vault.</span></span>

<span data-ttu-id="3d9d5-113">Varmista ennen jatkamista, että tunnet [peruskäsitteet](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span><span class="sxs-lookup"><span data-stu-id="3d9d5-113">Before you proceed make sure that you are familiar with the [basic concepts](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span></span>

>[!NOTE]
<span data-ttu-id="3d9d5-114">Alla oleva opetusohjelma edustaa parasta käytäntöä. Syy siihen selviää tutustumalla tiettyihin käsitteisiin.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-114">To understand why the below tutorial is the best practice we need to understand a few concepts.</span></span> <span data-ttu-id="3d9d5-115">Key Vault on keskussäilö salaisten koodien ohjelmalliseen tallentamiseen.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-115">Key Vault is a central repository to store secrets programmatically.</span></span> <span data-ttu-id="3d9d5-116">Jotta niin voi tehdä, sovellusten tai käyttäjien on ensin suoritettava Key Vaultin todentaminen eli esitettävä salainen koodi.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-116">But to do so applications / users need to first authenticate to Key Vault i.e. present a secret.</span></span> <span data-ttu-id="3d9d5-117">Lisäksi tietoturvan parhaat käytännöt edellyttävät, että tätä ensimmäistä salaista koodia kierrätetään jaksoittain.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-117">To follow security best practices this first secret needs to be rotated periodically as well.</span></span> <span data-ttu-id="3d9d5-118">Azuressa toimiville [hallitun palvelun käyttäjätietosovelluksille](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) annetaan kuitenkin käyttäjätiedot, joita Azure hallitsee automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-118">But with [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) applications that run in Azure are given an identity which is automatically managed by Azure.</span></span> <span data-ttu-id="3d9d5-119">Tämä auttaa ratkaisemaan **salaisen koodin esittelyongelman**, jossa käyttäjät tai sovellukset voivat noudattaa parhaita käytäntöjä huolehtimatta ensimmäisen salaisen koodin kierrättämisestä.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-119">This helps solve the **Secret Introduction Problem** where users / applications can follow best practices and not have to worry about rotating the first secret</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d9d5-120">Edellytykset</span><span class="sxs-lookup"><span data-stu-id="3d9d5-120">Prerequisites</span></span>

<span data-ttu-id="3d9d5-121">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-121">::: zone pivot="nodejs"</span></span>
* <span data-ttu-id="3d9d5-122">[Node JS](https://nodejs.org/en/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-122">[Node JS](https://nodejs.org/en/) ::: zone-end</span></span>

<span data-ttu-id="3d9d5-123">::: zone pivot="dotnet, windows"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-123">::: zone pivot="dotnet, windows"</span></span>
* <span data-ttu-id="3d9d5-124">[Visual Studio 2017 -versio 15.7.3 tai uudempi](https://www.microsoft.com/net/download/windows) seuraavilla kuormituksilla:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-124">[Visual Studio 2017 version 15.7.3 or later](https://www.microsoft.com/net/download/windows) with the following workloads:</span></span>
  * <span data-ttu-id="3d9d5-125">ASP.NET ja verkkokehitys</span><span class="sxs-lookup"><span data-stu-id="3d9d5-125">ASP.NET and web development</span></span>
  * <span data-ttu-id="3d9d5-126">Käyttöympäristöjen välinen .NET Core -kehitys</span><span class="sxs-lookup"><span data-stu-id="3d9d5-126">.NET Core cross-platform development</span></span>
* <span data-ttu-id="3d9d5-127">[.NET Core 2.1 SDK tai uudempi](https://www.microsoft.com/net/download/windows) :::zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-127">[.NET Core 2.1 SDK or later](https://www.microsoft.com/net/download/windows) :::zone-end</span></span>

<span data-ttu-id="3d9d5-128">::: zone pivot="dotnet, mac"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-128">::: zone pivot="dotnet, mac"</span></span>
* <span data-ttu-id="3d9d5-129">Lisätietoja: [Visual Studio for Macin uudet ominaisuudet](https://visualstudio.microsoft.com/vs/mac/).</span><span class="sxs-lookup"><span data-stu-id="3d9d5-129">See [What’s New in Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/).</span></span>
<span data-ttu-id="3d9d5-130">:::zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-130">:::zone-end</span></span>

* <span data-ttu-id="3d9d5-131">Git ([lataa](https://git-scm.com/downloads)).</span><span class="sxs-lookup"><span data-stu-id="3d9d5-131">Git ([download](https://git-scm.com/downloads)).</span></span>
* <span data-ttu-id="3d9d5-132">Azure-tilaus.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-132">An Azure subscription.</span></span> <span data-ttu-id="3d9d5-133">Jos sinulla ei ole Azure-tilausta, luo [maksuton tili](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) ennen aloittamista.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-133">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>
* <span data-ttu-id="3d9d5-134">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) -versio 2.0.4 tai uudempi.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-134">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 or later.</span></span> <span data-ttu-id="3d9d5-135">Tämä on saatavilla Windowsille, Macille ja Linuxille.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-135">This is available for Windows, Mac, and Linux.</span></span>

## <a name="login-to-azure"></a><span data-ttu-id="3d9d5-136">Kirjaudu sisään Azureen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-136">Login to Azure</span></span>

<span data-ttu-id="3d9d5-137">Jos haluat kirjautua sisään Azureen komentorivikäyttöliittymää käyttämällä, voit kirjoittaa:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-137">To log in to Azure using the CLI, you can type:</span></span>

```azurecli
az login
```

## <a name="create-resource-group"></a><span data-ttu-id="3d9d5-138">Resurssiryhmän luominen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-138">Create resource group</span></span>

<span data-ttu-id="3d9d5-139">Luo resurssiryhmä [az group create](/cli/azure/group#az-group-create) -komennolla.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-139">Create a resource group with the [az group create](/cli/azure/group#az-group-create) command.</span></span> <span data-ttu-id="3d9d5-140">Azure-resurssiryhmä on looginen säilö, jossa Azure-resursseja otetaan käyttöön ja hallitaan.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-140">An Azure resource group is a logical container into which Azure resources are deployed and managed.</span></span>

<span data-ttu-id="3d9d5-141">Valitse resurssiryhmä ja täytä paikkamerkki.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-141">Please select a Resource Group name and fill in the placeholder.</span></span>
<span data-ttu-id="3d9d5-142">Seuraava esimerkki luo resurssiryhmän nimeltä *<YourResourceGroupName>* sijaintiin *eastus*.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-142">The following example creates a resource group named *<YourResourceGroupName>* in the *eastus* location.</span></span>

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="3d9d5-143">Juuri luomaasi resurssiryhmää käytetään läpi tämän opetusohjelman.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-143">The resource group you just created is used throughout this tutorial.</span></span>

## <a name="create-an-azure-key-vault"></a><span data-ttu-id="3d9d5-144">Azure Key Vaultin luominen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-144">Create an Azure Key Vault</span></span>

<span data-ttu-id="3d9d5-145">Seuraavaksi luot Key Vaultin käyttämällä edellisessä vaiheessa luotua resurssiryhmää.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-145">Next you create a Key Vault using the resource group created in the previous step.</span></span> <span data-ttu-id="3d9d5-146">Tässä artikkelissa Key Vaultin nimenä käytetään ContosoKeyVaultia, mutta sinun on käytettävä yksilöllistä nimeä.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-146">Although “ContosoKeyVault” is used as the name for the Key Vault throughout this article, you have to use a unique name.</span></span> <span data-ttu-id="3d9d5-147">Anna seuraavat tiedot:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-147">Provide the following information:</span></span>

* <span data-ttu-id="3d9d5-148">Vaultin nimi – **valitse Key Vaultin nimi tähän**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-148">Vault name - **Select a Key Vault Name here**.</span></span>
* <span data-ttu-id="3d9d5-149">Resurssiryhmän nimi – **valitse resurssiryhmän nimi tähän**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-149">Resource group name - **Select a Resource Group Name here**.</span></span>
* <span data-ttu-id="3d9d5-150">Sijainti – **Itä-Yhdysvallat**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-150">The location - **East US**.</span></span>

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="3d9d5-151">Tässä vaiheessa oma Azure-tilisi on ainoa, jolla on valtuudet suorittaa toimia tässä uudessa Vaultissa.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-151">At this point, your Azure account is the only one authorized to perform any operations on this new vault.</span></span>

## <a name="add-a-secret-to-key-vault"></a><span data-ttu-id="3d9d5-152">Salaisen koodin lisääminen Key Vaultiin</span><span class="sxs-lookup"><span data-stu-id="3d9d5-152">Add a secret to key vault</span></span>

<span data-ttu-id="3d9d5-153">Lisäämme nyt salaisen koodin toimintaperiaatteen havainnollistamiseksi.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-153">We're adding a secret to help illustrate how this works.</span></span> <span data-ttu-id="3d9d5-154">Sinulla voi olla tallessa SQL-yhteysmerkkijono tai jokin muu tieto, joka on pidettävä suojattuna mutta tarjottava sovelluksesi käyttöön.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-154">You could be storing a SQL connection string or any other information that you need to keep securely but make available to your application.</span></span> <span data-ttu-id="3d9d5-155">Tässä opetusohjelmassa salasana on nimeltään **AppSecret** ja siihen tallennetaan arvo **MySecret**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-155">In this tutorial, the password will be called **AppSecret** and will store the value of **MySecret** in it.</span></span>

<span data-ttu-id="3d9d5-156">Luo Key Vaultiin salainen koodi nimeltä **AppSecret**, johon tallennetaan arvo **MySecret**. Se tapahtuu kirjoittamalla alla olevat komennot:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-156">Type the commands below to create a secret in Key Vault called **AppSecret** that will store the value **MySecret**:</span></span>

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

<span data-ttu-id="3d9d5-157">Voit nähdä salaisen koodin sisältämän arvon vain teksti -muodossa seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-157">To view the value contained in the secret as plain text:</span></span>

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

<span data-ttu-id="3d9d5-158">Tämä komento näyttää salaisen koodin tiedot URI mukaan lukien.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-158">This command shows the secret information including the URI.</span></span> <span data-ttu-id="3d9d5-159">Näiden vaiheiden jälkeen sinulla pitäisi olla Azure Key Vaultissa salaisen koodin URI.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-159">After completing these steps, you should have a URI to a secret in an Azure Key Vault.</span></span> <span data-ttu-id="3d9d5-160">Kirjoita nämä tiedot muistiin,</span><span class="sxs-lookup"><span data-stu-id="3d9d5-160">Write this information down.</span></span> <span data-ttu-id="3d9d5-161">sillä tarvitset niitä myöhemmin.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-161">You need it in a later step.</span></span>

## <a name="clone-the-repo"></a><span data-ttu-id="3d9d5-162">Säilön kloonaaminen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-162">Clone the Repo</span></span>

<span data-ttu-id="3d9d5-163">Kloonaa säilö, jotta saat itsellesi paikallisen kopion. Siten voit muokata lähdettä suorittamalla seuraavan komennon:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-163">Clone the repo in order to make a local copy for you to edit the source by running the following command:</span></span>

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

<span data-ttu-id="3d9d5-164">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-164">::: zone pivot="nodejs"</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="3d9d5-165">Riippuvuuksien asentaminen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-165">Install dependencies</span></span>

<span data-ttu-id="3d9d5-166">Tässä osiossa asennetaan riippuvuudet.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-166">Here we install the dependencies.</span></span> <span data-ttu-id="3d9d5-167">Suorita tämä komento: cd key-vault-node-quickstart npm install</span><span class="sxs-lookup"><span data-stu-id="3d9d5-167">Run the following commands cd key-vault-node-quickstart npm install</span></span>

<span data-ttu-id="3d9d5-168">Tässä projektissa käytettiin kahta solmumoduulia:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-168">This project used 2 node modules:</span></span>

* [<span data-ttu-id="3d9d5-169">ms-rest-azure</span><span class="sxs-lookup"><span data-stu-id="3d9d5-169">ms-rest-azure</span></span>](https://www.npmjs.com/package/ms-rest-azure) 
* [<span data-ttu-id="3d9d5-170">azure-keyvault</span><span class="sxs-lookup"><span data-stu-id="3d9d5-170">azure-keyvault</span></span>](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="3d9d5-171">Verkkosovelluksen julkaiseminen Azureen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-171">Publish the web application to Azure</span></span>

<span data-ttu-id="3d9d5-172">Alla on muutamia suoritettavia vaiheita.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-172">Below are the few steps we need to do</span></span>

* <span data-ttu-id="3d9d5-173">Ensimmäinen vaihe on luoda [Azure-sovelluspalvelun](https://azure.microsoft.com/services/app-service/) sopimus.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-173">The 1st step is to create a [Azure App Service](https://azure.microsoft.com/services/app-service/) Plan.</span></span> <span data-ttu-id="3d9d5-174">Sopimukseen voi tallentaa useita verkkosovelluksia.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-174">You can store multiple web apps in this plan.</span></span>

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* <span data-ttu-id="3d9d5-175">Seuraavaksi luodaan verkkosovellus.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-175">Next we create a web app.</span></span> <span data-ttu-id="3d9d5-176">Korvaa seuraavassa esimerkissä <app_name> globaalisti yksilöllisellä sovellusnimellä (kelvollisia merkkejä ovat a–z, 0–9 ja -).</span><span class="sxs-lookup"><span data-stu-id="3d9d5-176">In the following example, replace <app_name> with a globally unique app name (valid characters are a-z, 0-9, and -).</span></span> <span data-ttu-id="3d9d5-177">Suorituspalvelun arvoksi on asetettu NODE|6.9.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-177">The runtime is set to NODE|6.9.</span></span> <span data-ttu-id="3d9d5-178">Näet kaikki tuetut suorituspalvelut komennolla az webapp list-runtimes</span><span class="sxs-lookup"><span data-stu-id="3d9d5-178">To see all supported runtimes, run az webapp list-runtimes</span></span>

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    <span data-ttu-id="3d9d5-179">Kun verkkosovellus on luotu Azure CLI näyttää seuraavaa esimerkkiä vastaavan tuloksen:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-179">When the web app has been created, the Azure CLI shows output similar to the following example:</span></span>

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
    <span data-ttu-id="3d9d5-180">Selaa juuri luotuun verkkosovellukseesi, niin sinun tulisi nähdä täysin toimiva verkkosovellus.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-180">Browse to your newly created web app and you should see a functioning web app.</span></span> <span data-ttu-id="3d9d5-181">Korvaa <app_name> yksilöllisellä sovellusnimellä.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-181">Replace <app_name> with a unique app name.</span></span>

    ```text
    http://<app name>.azurewebsites.net
    ```
    <span data-ttu-id="3d9d5-182">Yllä oleva komento luo myös Gitiä käyttävän sovelluksen, jolla voit suorittaa käyttöönoton Azureen paikallisesta Gitistä käsin.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-182">The above command also creates a Git-enabled app which allows you to deploy to azure from your local git.</span></span> 
    <span data-ttu-id="3d9d5-183">Paikallisen Gitin määrittämiseen on käytetty URL-osoitetta https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git</span><span class="sxs-lookup"><span data-stu-id="3d9d5-183">Local git is configured with url of 'https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git'</span></span>

* <span data-ttu-id="3d9d5-184">Käyttöönottokäyttäjän luominen Edellisen komennon valmistuttua voit lisätä Azure-etäkohteen paikalliseen Git-säilöösi.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-184">Create a deployment user After the previous command is completed you can add add an Azure remote to your local Git repository.</span></span> <span data-ttu-id="3d9d5-185">Korvaa <url> Git-etäkohteen URL-osoitteella, jonka sait sovelluksesi Git-käyttöönotosta.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-185">Replace <url> with the URL of the Git remote that you got from Enable Git for your app.</span></span>

    ```bash
    git remote add azure <url>
    ```
<span data-ttu-id="3d9d5-186">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-186">::: zone-end</span></span>

<span data-ttu-id="3d9d5-187">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-187">::: zone pivot="dotnet"</span></span>

## <a name="open-and-edit-the-solution"></a><span data-ttu-id="3d9d5-188">Ratkaisun avaaminen ja muokkaaminen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-188">Open and edit the solution</span></span>

<span data-ttu-id="3d9d5-189">Muokkaa Program.cs-tiedostoa siten, että se voi suorittaa mallin erityisellä Key Vault -nimelläsi:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-189">Edit the program.cs file to run the sample with your specific key vault name:</span></span>

1. <span data-ttu-id="3d9d5-190">Selaa kansioon key-vault-dotnet-core-quickstart.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-190">Browse to the folder key-vault-dotnet-core-quickstart.</span></span>
2. <span data-ttu-id="3d9d5-191">Avaa key-vault-dotnet-core-quickstart.sln-tiedosto Visual Studio 2017:ssä.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-191">Open the key-vault-dotnet-core-quickstart.sln file in Visual Studio 2017.</span></span>
3. <span data-ttu-id="3d9d5-192">Avaa Program.cs-tiedosto ja korvaa *YourKeyVaultName*-paikkamerkki aiemmin luomasi Key Vaultin nimellä.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-192">Open the Program.cs file and update the placeholder *YourKeyVaultName* with the name of your key vault that you created earlier.</span></span>

<span data-ttu-id="3d9d5-193">Tämä ratkaisu käyttää [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication)- ja [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet -kirjastoja.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-193">This solution uses [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) and [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet libraries.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="3d9d5-194">Suorita sovellus</span><span class="sxs-lookup"><span data-stu-id="3d9d5-194">Run the app</span></span>

<span data-ttu-id="3d9d5-195">Valitse Visual Studio 2017:n päävalikosta **Virheenkorjaus** > **Aloita** ilman virheenkorjausta.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-195">From the main menu of Visual Studio 2017, select **Debug** > **Start** without debugging.</span></span> <span data-ttu-id="3d9d5-196">Kun selain avautuu, siirry **Tietoja**-sivulle.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-196">When the browser appears, go to the **About** page.</span></span> <span data-ttu-id="3d9d5-197">Näet **AppSecret**-arvon.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-197">The value for **AppSecret** is displayed.</span></span>

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="3d9d5-198">Verkkosovelluksen julkaiseminen Azureen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-198">Publish the web application to Azure</span></span>

<span data-ttu-id="3d9d5-199">Kun julkaiset tämän sovelluksen Azureen, näet sen toiminnassa verkkosovelluksena. Voit myös noutaa salaisen koodin arvon:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-199">Publish this app to Azure to see it live as a web app, and to see that you can fetch the secret value:</span></span>

1. <span data-ttu-id="3d9d5-200">Valitse Visual Studiossa projekti **key-vault-dotnet-core-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-200">In Visual Studio, select the **key-vault-dotnet-core-quickstart** project.</span></span>
2. <span data-ttu-id="3d9d5-201">Valitse **Julkaise** > **Aloita**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-201">Select **Publish** > **Start**.</span></span>
3. <span data-ttu-id="3d9d5-202">Luo uusi **sovelluspalvelu** ja valitse **Julkaise**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-202">Create a new **App Service**, and then select **Publish**.</span></span>
4. <span data-ttu-id="3d9d5-203">Vaihda sovelluksen nimeksi **keyvaultdotnetcorequickstart**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-203">Change the app name to **keyvaultdotnetcorequickstart**.</span></span>
5. <span data-ttu-id="3d9d5-204">Valitse **Luo**.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-204">Select **Create**.</span></span>

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]

<span data-ttu-id="3d9d5-205">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-205">::: zone-end</span></span>

## <a name="enable-managed-service-identities"></a><span data-ttu-id="3d9d5-206">Hallitun palvelun käyttäjätietojen käyttöönotto</span><span class="sxs-lookup"><span data-stu-id="3d9d5-206">Enable managed service identities</span></span>

<span data-ttu-id="3d9d5-207">Azure Key Vault on tapa tallentaa tunnistetietoja, muita avaimia ja salaisia koodeja suojatusti. Koodisi on kuitenkin todennettava Azure Key Vaultiin niiden noutamiseksi.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-207">Azure Key Vault provides a way to securely store credentials and other keys and secrets, but your code needs to authenticate to Azure Key Vault to retrieve them.</span></span> <span data-ttu-id="3d9d5-208">Hallitun palvelun käyttäjätiedot tekevät tästä helpompaa antamalla Azure-palveluille automaattisesti hallitut käyttäjätiedot Azure Active Directoryssa (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3d9d5-208">Managed Service Identity makes this easier by giving Azure services an automatically managed identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3d9d5-209">Voit käyttää näitä käyttäjätietoja todentamisessa mihin tahansa palveluun, joka tukee Azure AD -todentamista – Key Vault mukaan lukien. Tällöin koodin ei tarvitse sisältää tunnistetietoja.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-209">You can use this identity to authenticate to any service that supports Azure AD authentication, including Key Vault, without having any credentials in your code.</span></span>

1. <span data-ttu-id="3d9d5-210">Palaa Azure CLI:hin.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-210">Return to the Azure CLI.</span></span>
2. <span data-ttu-id="3d9d5-211">Luo käyttäjätiedot tälle sovellukselle komennolla assign-identity:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-211">Run the assign-identity command to create the identity for this application:</span></span>

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
><span data-ttu-id="3d9d5-212">Tässä toimintosarjassa komento vastaa siirtymistä portaaliin ja **Hallitun palvelun käyttäjätiedot** -asetuksen ottamista **käyttöön** verkkosovelluksen ominaisuuksissa.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-212">The command in this procedure is the equivalent of going to the portal and switching **Managed service identity** to **On** in the web application properties.</span></span>

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a><span data-ttu-id="3d9d5-213">Oikeuksien määrittäminen sovellukselle salaisten koodien lukemiseksi Key Vaultista</span><span class="sxs-lookup"><span data-stu-id="3d9d5-213">Assign permissions to your application to read secrets from Key Vault</span></span>

<span data-ttu-id="3d9d5-214">Kun julkaiset sovelluksen Azureen, kirjaa tulos muistiin.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-214">Make a note of the output when you publish the application to Azure.</span></span> <span data-ttu-id="3d9d5-215">Se tulisi olla tällaisessa muodossa:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-215">It should be of the format:</span></span>

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

<span data-ttu-id="3d9d5-216">Suorita sen jälkeen tämä komento käyttämällä Key Vaultisi nimeä ja **PrincipalId**-arvoa:</span><span class="sxs-lookup"><span data-stu-id="3d9d5-216">Then, run this command by using the name of your key vault and the value of **PrincipalId**:</span></span>

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

<span data-ttu-id="3d9d5-217">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-217">::: zone pivot="nodejs"</span></span>
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a><span data-ttu-id="3d9d5-218">Solmusovelluksen käyttöönotto Azuressa ja salaisen koodin arvon noutaminen</span><span class="sxs-lookup"><span data-stu-id="3d9d5-218">Deploy the Node App to Azure and retrieve the secret value</span></span>

<span data-ttu-id="3d9d5-219">Nyt kun kaikki on valmiina,</span><span class="sxs-lookup"><span data-stu-id="3d9d5-219">Now that everything is set.</span></span> <span data-ttu-id="3d9d5-220">suorita seuraava komento sovelluksen käyttöönottamiseksi Azuressa.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-220">Run the following command to deploy the app to Azure</span></span>

```bash
git push azure master
```

<span data-ttu-id="3d9d5-221">Kun tämän jälkeen siirryt osoitteeseen https://<app_name>.azurewebsites.net, näet näet salaisen koodin arvon.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-221">After this when you browse https://<app_name>.azurewebsites.net you can see the secret value.</span></span>
<span data-ttu-id="3d9d5-222">Varmista, että korvasit nimen <YourKeyVaultName> oman Vaultisi nimellä ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-222">Make sure that you replaced the name <YourKeyVaultName> with your vault name ::: zone-end</span></span>

<span data-ttu-id="3d9d5-223">::: zone pivot="dotnet" Kun nyt suoritat sovelluksen, sinun tulisi nähdä noudettu salaisen koodin arvo.</span><span class="sxs-lookup"><span data-stu-id="3d9d5-223">::: zone pivot="dotnet" Now when you run the application, you should see your secret value retrieved.</span></span>
<span data-ttu-id="3d9d5-224">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-224">::: zone-end</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d9d5-225">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="3d9d5-225">Next steps</span></span>

<span data-ttu-id="3d9d5-226">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-226">::: zone pivot="nodejs"</span></span>
* [<span data-ttu-id="3d9d5-227">Azure Key Vaultin aloitussivu</span><span class="sxs-lookup"><span data-stu-id="3d9d5-227">Azure Key Vault Home Page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="3d9d5-228">Azure Key Vaultin dokumentaatio</span><span class="sxs-lookup"><span data-stu-id="3d9d5-228">Azure Key Vault Documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="3d9d5-229">Azure SDK For Node</span><span class="sxs-lookup"><span data-stu-id="3d9d5-229">Azure SDK For Node</span></span>](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* <span data-ttu-id="3d9d5-230">[Azuren REST-ohjelmointirajapinnan viittaus](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-230">[Azure REST API Reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>

<span data-ttu-id="3d9d5-231">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="3d9d5-231">::: zone pivot="dotnet"</span></span>
* [<span data-ttu-id="3d9d5-232">Azure Key Vaultin aloitussivu</span><span class="sxs-lookup"><span data-stu-id="3d9d5-232">Azure Key Vault home page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="3d9d5-233">Azure Key Vaultin dokumentaatio</span><span class="sxs-lookup"><span data-stu-id="3d9d5-233">Azure Key Vault documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="3d9d5-234">Azure SDK For .NET</span><span class="sxs-lookup"><span data-stu-id="3d9d5-234">Azure SDK For .NET</span></span>](https://github.com/Azure/azure-sdk-for-net)
* <span data-ttu-id="3d9d5-235">[Azuren REST-ohjelmointirajapinnan viittaus](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="3d9d5-235">[Azure REST API reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>