---
title: Linkkien käyttäminen ohjeissa
description: Tämä artikkeli opastaa linkkien luomiseen osoitteessa docs.microsoft.com olevaan sisältöön.
ms.date: 06/29/2017
ms.openlocfilehash: dad0460cfb36594c17cef1b079c5fc14191f56f7
ms.sourcegitcommit: 886ca76086a302d1d6124967df12a5bcfe4fd4b5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2018
ms.locfileid: "40251483"
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="16694-103">Linkkien käyttäminen ohjeissa</span><span class="sxs-lookup"><span data-stu-id="16694-103">Using links in documentation</span></span>
<span data-ttu-id="16694-104">Tässä artikkelissa kuvataan hyperlinkkien luominen osoitteessa docs.microsoft.com isännöidyistä sivuista.</span><span class="sxs-lookup"><span data-stu-id="16694-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com.</span></span> <span data-ttu-id="16694-105">Linkit on helppo lisätä merkintöihin erilaisilla keinoilla.</span><span class="sxs-lookup"><span data-stu-id="16694-105">Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="16694-106">Linkeillä käyttäjä voidaan ohjata samalla sivulla olevaan sisältöön, viereisiin sivuihin tai ulkoisiin sivustoihin ja URL-osoitteisiin.</span><span class="sxs-lookup"><span data-stu-id="16694-106">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="16694-107">Docs.microsoft.com-sivuston taustajärjestelmän käyttää Open Publishing Services (OPS) -palvelua, jossa hyödynnetään DocFX Flavored Markdown (DFM) -ominaisuutta.</span><span class="sxs-lookup"><span data-stu-id="16694-107">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="16694-108">DFM on hyvin yhteensopiva GitHub Flavored Markdownin (GFM) kanssa, ja DFM lisää toimintoja Markdown-laajennusten kautta.</span><span class="sxs-lookup"><span data-stu-id="16694-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16694-109">Kaikkien linkkien on oltava suojattuja (`https` vs `http`) aina, kun kohde tukee sitä (useimmissa tapauksissa).</span><span class="sxs-lookup"><span data-stu-id="16694-109">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="16694-110">Linkin teksti</span><span class="sxs-lookup"><span data-stu-id="16694-110">Link text</span></span>

<span data-ttu-id="16694-111">Linkin tekstin tulee olla sävyltään ystävällinen.</span><span class="sxs-lookup"><span data-stu-id="16694-111">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="16694-112">Sen on siis koostuttava normaaleista suomenkielistä sanoista tai linkitettävän sivun otsikosta.</span><span class="sxs-lookup"><span data-stu-id="16694-112">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16694-113">Älä käytä ilmaisua ”napsauta tästä”.</span><span class="sxs-lookup"><span data-stu-id="16694-113">Do not use "click here."</span></span> <span data-ttu-id="16694-114">Se heikentää hakukoneiden tuloksia ja kuvailee sisältöä huonosti.</span><span class="sxs-lookup"><span data-stu-id="16694-114">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="16694-115">**Oikein:**</span><span class="sxs-lookup"><span data-stu-id="16694-115">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="16694-116">**Väärin:**</span><span class="sxs-lookup"><span data-stu-id="16694-116">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="16694-117">Artikkelien väliset linkit</span><span class="sxs-lookup"><span data-stu-id="16694-117">Links from one article to another</span></span>

<span data-ttu-id="16694-118">Käytä seuraavaa syntaksia, kun haluat luoda linkin teknisestä Docs-artikkelista toiseen, samaan ohjesarjaan kuuluvaan artikkeliin:</span><span class="sxs-lookup"><span data-stu-id="16694-118">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="16694-119">Hakemistossa oleva artikkeli sisältää linkin samassa hakemistossa olevaan toiseen artikkeliin:</span><span class="sxs-lookup"><span data-stu-id="16694-119">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="16694-120">Artikkeli sisältää linkin alahakemistosta päähakemistossa olevaan toiseen artikkeliin:</span><span class="sxs-lookup"><span data-stu-id="16694-120">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="16694-121">Päähakemistossa oleva artikkeli sisältää linkin alahakemistossa olevaan toiseen artikkeliin:</span><span class="sxs-lookup"><span data-stu-id="16694-121">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="16694-122">Alahakemistossa oleva artikkeli sisältää linkin toisessa alahakemistossa olevaan artikkeliin:</span><span class="sxs-lookup"><span data-stu-id="16694-122">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="16694-123">Artikkeli, joka sisältää samaan (samassa säilössä tai muualla sijaitsevaan) ohjesarjaan viittaavia linkkejä: `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="16694-123">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16694-124">Missään edellisistä esimerkeistä ei ole käytetty merkkejä `~/` osana linkkiä.</span><span class="sxs-lookup"><span data-stu-id="16694-124">None of the above examples use the `~/` as part of the link.</span></span> <span data-ttu-id="16694-125">Jos linkität säilön juuressa olevaan polkuun, aloita merkillä `/`.</span><span class="sxs-lookup"><span data-stu-id="16694-125">If you are linking to a path at the root of the repository, start with the `/`.</span></span> <span data-ttu-id="16694-126">Merkkien `~/` sisällyttäminen saa aikaan virheellisiä linkkejä siirryttäessä lähdesäilöjen välillä GitHubissa.</span><span class="sxs-lookup"><span data-stu-id="16694-126">Including the `~/` produces invalid links when navigating the source repositories on GitHub.</span></span> <span data-ttu-id="16694-127">Kun polku aloitetaan merkillä `/`, se määrittyy oikein.</span><span class="sxs-lookup"><span data-stu-id="16694-127">Starting the path with `/` resolves correctly.</span></span>

## <a name="links-to-anchors"></a><span data-ttu-id="16694-128">Ankkureihin viittaavat linkit</span><span class="sxs-lookup"><span data-stu-id="16694-128">Links to anchors</span></span>

<span data-ttu-id="16694-129">Sinun ei tarvitse luoda ankkureita.</span><span class="sxs-lookup"><span data-stu-id="16694-129">You do not have to create anchors.</span></span> <span data-ttu-id="16694-130">Ne luodaan automaattisesti H2-alaotsikoista julkaisun yhteydessä.</span><span class="sxs-lookup"><span data-stu-id="16694-130">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="16694-131">Sinun on ainoastaan luotava linkit H2-osioihin.</span><span class="sxs-lookup"><span data-stu-id="16694-131">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="16694-132">Linkittäminen artikkelin sisäiseen otsikkoon:</span><span class="sxs-lookup"><span data-stu-id="16694-132">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="16694-133">Linkittäminen samassa alikansiossa sijaitsevan artikkelin ankkuriin:</span><span class="sxs-lookup"><span data-stu-id="16694-133">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="16694-134">Linkittäminen samassa alikansiossa sijaitsevan palvelun alahakemiston ankkuriin:</span><span class="sxs-lookup"><span data-stu-id="16694-134">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="16694-135">Linkit sisällytetyistä tiedostoista</span><span class="sxs-lookup"><span data-stu-id="16694-135">Links from includes</span></span>

<span data-ttu-id="16694-136">Koska sisällytetyt tiedostot sijaitsevat toisessa hakemistossa, sinun on käytettävä pidempiä suhteellisia polkuja.</span><span class="sxs-lookup"><span data-stu-id="16694-136">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="16694-137">Käytä seuraavaa muotoa, kun haluat linkittää sisällytetystä tiedostosta:</span><span class="sxs-lookup"><span data-stu-id="16694-137">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="16694-138">Linkit valitsimissa</span><span class="sxs-lookup"><span data-stu-id="16694-138">Links in selectors</span></span>

<span data-ttu-id="16694-139">Jos sinulla on valitsimia, jotka on upotettu sisällytettyyn tiedostoon (joita mm. Azuren ohjetiimi käyttää) käytä seuraavaa linkkirakennetta:</span><span class="sxs-lookup"><span data-stu-id="16694-139">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="16694-140">[AZURE.SELECTOR-LIST (Avattava valikko1 | Avattava valikko2 )]</span><span class="sxs-lookup"><span data-stu-id="16694-140">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="16694-141">(Teksti1 | Esimerkki1)</span><span class="sxs-lookup"><span data-stu-id="16694-141">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="16694-142">(Teksti1 | Esimerkki2)</span><span class="sxs-lookup"><span data-stu-id="16694-142">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="16694-143">(Teksti2 | Esimerkki3)</span><span class="sxs-lookup"><span data-stu-id="16694-143">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="16694-144">[(Teksti2 | Esimerkki4)](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="16694-144">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="16694-145">Viitetyyliset linkit</span><span class="sxs-lookup"><span data-stu-id="16694-145">Reference-style links</span></span>

<span data-ttu-id="16694-146">Viitetyylisten linkkien avulla voit helpottaa lähdesisällön luettavuutta.</span><span class="sxs-lookup"><span data-stu-id="16694-146">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="16694-147">Viitetyyliset linkit korvaavat sidottujen linkkien syntaksin yksinkertaistetulla syntaksilla, jonka avulla pitkät URL-osoitteet voidaan siirtää artikkelin loppuun.</span><span class="sxs-lookup"><span data-stu-id="16694-147">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="16694-148">Tässä on esimerkki, jonka [Daring Fireball](https://daringfireball.net/projects/markdown/) loi:</span><span class="sxs-lookup"><span data-stu-id="16694-148">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="16694-149">Sidottu teksti:</span><span class="sxs-lookup"><span data-stu-id="16694-149">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="16694-150">Viitelinkit artikkelin lopussa:</span><span class="sxs-lookup"><span data-stu-id="16694-150">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="16694-151">Muista sisällyttää kaksoispisteen jälkeen tuleva, linkkiä edeltävä välilyönti.</span><span class="sxs-lookup"><span data-stu-id="16694-151">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="16694-152">Jos unohdat välilyönnin linkittäessäsi muihin teknisiin artikkeleihin, julkaistun artikkelin linkki ei toimi.</span><span class="sxs-lookup"><span data-stu-id="16694-152">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="16694-153">Linkit sivuille, jotka eivät kuulu teknisten ohjeiden sarjaan</span><span class="sxs-lookup"><span data-stu-id="16694-153">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="16694-154">Jos haluat linkittää toiselle Microsoftin omistamalle sivulle (esim. hinnastosivu, palvelutasosopimuksen sivu tai muu sivu, joka ei sisällä ohjeartikkelia), käytä absoluuttista URL-osoitetta, mutta poista aluetunnus.</span><span class="sxs-lookup"><span data-stu-id="16694-154">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="16694-155">Tässä tavoitteena on, että linkit toimivat GitHubissa ja hahmonnetulla sivustolla:</span><span class="sxs-lookup"><span data-stu-id="16694-155">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="16694-156">Linkit kolmansien osapuolten sivustoille</span><span class="sxs-lookup"><span data-stu-id="16694-156">Links to third-party sites</span></span>

<span data-ttu-id="16694-157">Paras käyttäjäkokemus on sellainen, jossa vältetään ohjaamasta käyttäjä toiselle sivustolle.</span><span class="sxs-lookup"><span data-stu-id="16694-157">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="16694-158">Kolmansien osapuolen sivustoille linkittämistä ei voi aina välttää, joten perusta tällaisille sivustoille johtavat linkit seuraaviin tietoihin:</span><span class="sxs-lookup"><span data-stu-id="16694-158">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="16694-159">**Vastuullisuus**: Linkitä kolmannen osapuolen sisältöön, kun kyseisen tiedon jakaminen on kolmannen osapuolen vastuulla.</span><span class="sxs-lookup"><span data-stu-id="16694-159">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="16694-160">Esimerkiksi Android-kehittäjätyökalujen käytön kuvailu on Googlen tehtävä, ei Microsoftin.</span><span class="sxs-lookup"><span data-stu-id="16694-160">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="16694-161">Voimme tarvittaessa kertoa, miten Android-kehittäjätyökaluja käytetään Azuren *kanssa*, mutta Googlen on annettava ohjeet omien työkalujensa käyttöön.</span><span class="sxs-lookup"><span data-stu-id="16694-161">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="16694-162">**Projektipäällikön hyväksyntä**: Pyydä Microsoftia hyväksymään kolmannen osapuolen sisältö.</span><span class="sxs-lookup"><span data-stu-id="16694-162">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="16694-163">Sisältöön linkittäminen ilmaisee luottamuksemme ja vastuumme ihmisten noudattaessa annettuja ohjeita.</span><span class="sxs-lookup"><span data-stu-id="16694-163">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="16694-164">**Tuoreuden arviointi**: Varmista, että kolmannen osapuolen antamat tiedot ovat ajantasaiset, paikkaansa pitävät ja asianmukaiset ja että linkki ole muuttunut.</span><span class="sxs-lookup"><span data-stu-id="16694-164">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="16694-165">**Sivustolta poistuminen**: Varmista, että käyttäjä tietää siirtyvänsä toiselle sivustolle.</span><span class="sxs-lookup"><span data-stu-id="16694-165">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="16694-166">Jos tämä ei ilmene asiayhteydestä, lisää selventävä lause.</span><span class="sxs-lookup"><span data-stu-id="16694-166">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="16694-167">Esimerkki: ”Toimet edellyttävät Android-kehittäjätyökaluja, jotka voit ladata Android Studio -sivustolta.”</span><span class="sxs-lookup"><span data-stu-id="16694-167">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="16694-168">**Seuraavat vaiheet**: Voit lisätä linkin esimerkiksi MVP-blogiin ”Seuraavat vaiheet” -osiossa.</span><span class="sxs-lookup"><span data-stu-id="16694-168">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="16694-169">Varmista jälleen, että käyttäjät ymmärtävät poistuvansa sivustolta.</span><span class="sxs-lookup"><span data-stu-id="16694-169">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="16694-170">**Oikeudelliset asiat**: Jokaisen ms.com-sivun alaviitteessä olevien **Käyttöehtojen** **Linkit kolmansien osapuolten sivustoille** -osio kuvailee oikeudelliset ehdot.</span><span class="sxs-lookup"><span data-stu-id="16694-170">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="16694-171">MSDN- ja TechNet-linkit</span><span class="sxs-lookup"><span data-stu-id="16694-171">Links to MSDN or TechNet</span></span>

<span data-ttu-id="16694-172">Kun haluat linkittää MSDN- tai TechNet-sivustolle, käytä aiheen täydellistä linkkiä ja poista linkistä maakohtainen ”en-us” -asetus.</span><span class="sxs-lookup"><span data-stu-id="16694-172">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="16694-173">Linkit Azure PowerShell -viittaussisältöön</span><span class="sxs-lookup"><span data-stu-id="16694-173">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="16694-174">Azure PowerShell -viittaussisältöön on tehty useita muutoksia marraskuun 2016 jälkeen.</span><span class="sxs-lookup"><span data-stu-id="16694-174">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="16694-175">Noudata seuraavia ohjeita, kun linkität tähän sisältöön muista docs.microsoft.com -sivuston artikkeleita.</span><span class="sxs-lookup"><span data-stu-id="16694-175">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="16694-176">URL-osoitteen rakenne:</span><span class="sxs-lookup"><span data-stu-id="16694-176">Structure of the URL:</span></span>

* <span data-ttu-id="16694-177">Cmdlet-komennot:</span><span class="sxs-lookup"><span data-stu-id="16694-177">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="16694-178">Käsitteelliset aiheet:</span><span class="sxs-lookup"><span data-stu-id="16694-178">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="16694-179">&lt;Moniker-name&gt; -osa on valinnainen.</span><span class="sxs-lookup"><span data-stu-id="16694-179">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="16694-180">Jos se jätetään pois, sinut ohjataan sisällön uusimpaan versioon.</span><span class="sxs-lookup"><span data-stu-id="16694-180">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="16694-181">&lt;Service-name&gt; -osa on yksi seuraavissa perus-URL:issä näytetyistä esimerkeistä:</span><span class="sxs-lookup"><span data-stu-id="16694-181">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="16694-182">Azure PowerShell (AzureRM) -sisältö: [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="16694-182">Azure PowerShell (AzureRM) content: [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span></span>
- <span data-ttu-id="16694-183">Azure PowerShell (ASM) -sisältö: [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span><span class="sxs-lookup"><span data-stu-id="16694-183">Azure PowerShell (ASM) content: [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span></span>
- <span data-ttu-id="16694-184">Azure Active Directory (AzureAD) PowerShell -sisältö: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span><span class="sxs-lookup"><span data-stu-id="16694-184">Azure Active Directory (AzureAD) PowerShell content: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span></span>
- <span data-ttu-id="16694-185">Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)</span><span class="sxs-lookup"><span data-stu-id="16694-185">Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)</span></span>
- <span data-ttu-id="16694-186">Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span><span class="sxs-lookup"><span data-stu-id="16694-186">Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span></span>
- <span data-ttu-id="16694-187">Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span><span class="sxs-lookup"><span data-stu-id="16694-187">Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span></span>

<span data-ttu-id="16694-188">Kun käytät näitä URL-osoitteita, sinut ohjataan sisällön uusimpaan versioon.</span><span class="sxs-lookup"><span data-stu-id="16694-188">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="16694-189">Näin sinun ei tarvitse määrittää monikerin versiota.</span><span class="sxs-lookup"><span data-stu-id="16694-189">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="16694-190">Asiasisältöön viittaavia linkkejä ei tarvitse päivittää, kun sen versio muuttuu.</span><span class="sxs-lookup"><span data-stu-id="16694-190">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="16694-191">Jotta luomasi linkki on oikein, hae linkitettävä sivu selaimella ja kopioi sen URL-osoite.</span><span class="sxs-lookup"><span data-stu-id="16694-191">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="16694-192">Poista sitten ”https://docs.microsoft.com” ja viittaus kielialueeseen.</span><span class="sxs-lookup"><span data-stu-id="16694-192">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="16694-193">Kun linkität sisällysluettelosta, käytä täydellistä URL-osoitetta ilman viittausta kielialueeseen.</span><span class="sxs-lookup"><span data-stu-id="16694-193">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="16694-194">Esimerkkimerkintä:</span><span class="sxs-lookup"><span data-stu-id="16694-194">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
