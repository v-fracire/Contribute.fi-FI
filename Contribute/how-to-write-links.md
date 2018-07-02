---
title: Linkkien käyttäminen ohjeissa
description: Tämä artikkeli opastaa linkkien luomiseen osoitteessa docs.microsoft.com olevaan sisältöön.
ms.date: 06/29/2017
ms.openlocfilehash: a66e2fb4febf1947afe01919b96b1c10873cf57d
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2018
ms.locfileid: "36239722"
---
# <a name="using-links-in-documentation"></a>Linkkien käyttäminen ohjeissa
Tässä artikkelissa kuvataan hyperlinkkien luominen osoitteessa docs.microsoft.com isännöidyistä sivuista. Linkit on helppo lisätä merkintöihin erilaisilla keinoilla. Linkeillä käyttäjä voidaan ohjata samalla sivulla olevaan sisältöön, viereisiin sivuihin tai ulkoisiin sivustoihin ja URL-osoitteisiin.

Docs.microsoft.com-sivuston taustajärjestelmän käyttää Open Publishing Services (OPS) -palvelua, jossa hyödynnetään DocFX Flavored Markdown (DFM) -ominaisuutta. DFM on hyvin yhteensopiva GitHub Flavored Markdownin (GFM) kanssa, ja DFM lisää toimintoja Markdown-laajennusten kautta.

> [!IMPORTANT]
> Kaikkien linkkien on oltava suojattuja (`https` vs `http`) aina, kun kohde tukee sitä (useimmissa tapauksissa).

## <a name="link-text"></a>Linkin teksti

Linkin tekstin tulee olla sävyltään ystävällinen. Sen on siis koostuttava normaaleista suomenkielistä sanoista tai linkitettävän sivun otsikosta.

> [!IMPORTANT]
> Älä käytä ilmaisua ”napsauta tästä”. Se heikentää hakukoneiden tuloksia ja kuvailee sisältöä huonosti.

**Oikein:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Väärin:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>Artikkelien väliset linkit

Käytä seuraavaa syntaksia, kun haluat luoda linkin teknisestä Docs-artikkelista toiseen, samaan ohjesarjaan kuuluvaan artikkeliin:

- Hakemistossa oleva artikkeli sisältää linkin samassa hakemistossa olevaan toiseen artikkeliin:

  `[link text](article-name.md)`

- Artikkeli sisältää linkin alahakemistosta päähakemistossa olevaan toiseen artikkeliin:

  `[link text](../article-name.md)`

- Päähakemistossa oleva artikkeli sisältää linkin alahakemistossa olevaan toiseen artikkeliin:

  `[link text](./directory/article-name.md)`

- Alahakemistossa oleva artikkeli sisältää linkin toisessa alahakemistossa olevaan artikkeliin:

  `[link text](../directory/article-name.md)`

- Artikkeli, joka sisältää samaan (samassa säilössä tai muualla sijaitsevaan) ohjesarjaan viittaavia linkkejä: `[link text](./directory/article-name)`

> [!IMPORTANT]
> Missään edellisistä esimerkeistä ei ole käytetty merkkejä `~/` osana linkkiä. Jos linkität säilön juuressa olevaan polkuun, aloita merkillä `/`. Merkkien `~/` sisällyttäminen saa aikaan virheellisiä linkkejä siirryttäessä lähdesäilöjen välillä GitHubissa. Kun polku aloitetaan merkillä `/`, se määrittyy oikein.

## <a name="links-to-anchors"></a>Ankkureihin viittaavat linkit

Sinun ei tarvitse luoda ankkureita. Ne luodaan automaattisesti H2-alaotsikoista julkaisun yhteydessä. Sinun on ainoastaan luotava linkit H2-osioihin.

- Linkittäminen artikkelin sisäiseen otsikkoon:

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- Linkittäminen samassa alikansiossa sijaitsevan artikkelin ankkuriin:

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- Linkittäminen samassa alikansiossa sijaitsevan palvelun alahakemiston ankkuriin:

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a>Linkit sisällytetyistä tiedostoista

Koska sisällytetyt tiedostot sijaitsevat toisessa hakemistossa, sinun on käytettävä pidempiä suhteellisia polkuja. Käytä seuraavaa muotoa, kun haluat linkittää sisällytetystä tiedostosta:

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a>Linkit valitsimissa

Jos sinulla on valitsimia, jotka on upotettu sisällytettyyn tiedostoon (joita mm. Azuren ohjetiimi käyttää) käytä seuraavaa linkkirakennetta:

    > [AZURE.SELECTOR-LIST (Avattava valikko1 | Avattava valikko2 )]
    - [(Teksti1 | Esimerkki1)](../articles/folder/article-name1.md)
    - [(Teksti1 | Esimerkki2)](../articles/folder/article-name2.md)
    - [(Teksti2 | Esimerkki3)](../articles/folder/article-name3.md)
    - [(Teksti2 | Esimerkki4)](../articles/folder/article-name4.md) -->

## <a name="reference-style-links"></a>Viitetyyliset linkit

Viitetyylisten linkkien avulla voit helpottaa lähdesisällön luettavuutta. Viitetyyliset linkit korvaavat sidottujen linkkien syntaksin yksinkertaistetulla syntaksilla, jonka avulla pitkät URL-osoitteet voidaan siirtää artikkelin loppuun. Tässä on esimerkki, jonka [Daring Fireball](https://daringfireball.net/projects/markdown/) loi:

Sidottu teksti:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Viitelinkit artikkelin lopussa:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

Muista sisällyttää kaksoispisteen jälkeen tuleva, linkkiä edeltävä välilyönti. Jos unohdat välilyönnin linkittäessäsi muihin teknisiin artikkeleihin, julkaistun artikkelin linkki ei toimi.

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a>Linkit sivuille, jotka eivät kuulu teknisten ohjeiden sarjaan

Jos haluat linkittää toiselle Microsoftin omistamalle sivulle (esim. hinnastosivu, palvelutasosopimuksen sivu tai muu sivu, joka ei sisällä ohjeartikkelia), käytä absoluuttista URL-osoitetta, mutta poista aluetunnus. Tässä tavoitteena on, että linkit toimivat GitHubissa ja hahmonnetulla sivustolla:

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a>Linkit kolmansien osapuolten sivustoille

Paras käyttäjäkokemus on sellainen, jossa vältetään ohjaamasta käyttäjä toiselle sivustolle. Kolmansien osapuolen sivustoille linkittämistä ei voi aina välttää, joten perusta tällaisille sivustoille johtavat linkit seuraaviin tietoihin:

- **Vastuullisuus**: Linkitä kolmannen osapuolen sisältöön, kun kyseisen tiedon jakaminen on kolmannen osapuolen vastuulla. Esimerkiksi Android-kehittäjätyökalujen käytön kuvailu on Googlen tehtävä, ei Microsoftin. Voimme tarvittaessa kertoa, miten Android-kehittäjätyökaluja käytetään Azuren *kanssa*, mutta Googlen on annettava ohjeet omien työkalujensa käyttöön.
- **Projektipäällikön hyväksyntä**: Pyydä Microsoftia hyväksymään kolmannen osapuolen sisältö. Sisältöön linkittäminen ilmaisee luottamuksemme ja vastuumme ihmisten noudattaessa annettuja ohjeita.
- **Tuoreuden arviointi**: Varmista, että kolmannen osapuolen antamat tiedot ovat ajantasaiset, paikkaansa pitävät ja asianmukaiset ja että linkki ole muuttunut.
- **Sivustolta poistuminen**: Varmista, että käyttäjä tietää siirtyvänsä toiselle sivustolle. Jos tämä ei ilmene asiayhteydestä, lisää selventävä lause. Esimerkki: ”Toimet edellyttävät Android-kehittäjätyökaluja, jotka voit ladata Android Studio -sivustolta.”
- **Seuraavat vaiheet**: Voit lisätä linkin esimerkiksi MVP-blogiin ”Seuraavat vaiheet” -osiossa. Varmista jälleen, että käyttäjät ymmärtävät poistuvansa sivustolta.
- **Oikeudelliset asiat**: Jokaisen ms.com-sivun alaviitteessä olevien **Käyttöehtojen** **Linkit kolmansien osapuolten sivustoille** -osio kuvailee oikeudelliset ehdot.

## <a name="links-to-msdn-or-technet"></a>MSDN- ja TechNet-linkit

Kun haluat linkittää MSDN- tai TechNet-sivustolle, käytä aiheen täydellistä linkkiä ja poista linkistä maakohtainen ”en-us” -asetus.

## <a name="links-to-azure-powershell-reference-content"></a>Linkit Azure PowerShell -viittaussisältöön

Azure PowerShell -viittaussisältöön on tehty useita muutoksia marraskuun 2016 jälkeen. Noudata seuraavia ohjeita, kun linkität tähän sisältöön muista docs.microsoft.com -sivuston artikkeleita.

URL-osoitteen rakenne:

* Cmdlet-komennot:
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* Käsitteelliset aiheet:
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

&lt;Moniker-name&gt; -osa on valinnainen. Jos se jätetään pois, sinut ohjataan sisällön uusimpaan versioon. &lt;Service-name&gt; -osa on yksi seuraavissa perus-URL:issä näytetyistä esimerkeistä:

- Azure PowerShell (AzureRM) -sisältö: https://docs.microsoft.com/powershell/azure/
- Azure PowerShell (ASM) -sisältö: https://docs.microsoft.com/powershell/azure/_servicemanagement_
- Azure Active Directory (AzureAD) PowerShell -sisältö: https://docs.microsoft.com/powershell/azure/_active-directory_
- Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_
- Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_
- Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_

Kun käytät näitä URL-osoitteita, sinut ohjataan sisällön uusimpaan versioon. Näin sinun ei tarvitse määrittää monikerin versiota. Asiasisältöön viittaavia linkkejä ei tarvitse päivittää, kun sen versio muuttuu.

Jotta luomasi linkki on oikein, hae linkitettävä sivu selaimella ja kopioi sen URL-osoite.
Poista sitten ”https://docs.microsoft.com” ja viittaus kielialueeseen.

Kun linkität sisällysluettelosta, käytä täydellistä URL-osoitetta ilman viittausta kielialueeseen.

Esimerkkimerkintä:

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
