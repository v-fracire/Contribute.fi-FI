---
title: OPS-ympäristön ja docs.microsoft.com-sivuston Markdown-viiteopas
description: OPS-ympäristön opas Markdownin ja DocFX Flavored Markdown (DFM) -laajennusten käyttöön.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
audience: internal,external
ms.openlocfilehash: 64921bacf48e638221048db4b24e1a941f1d2777
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609541"
---
# <a name="markdown-reference-for-ops"></a><span data-ttu-id="86f17-103">OPS-ympäristön Markdown-viiteopas</span><span class="sxs-lookup"><span data-stu-id="86f17-103">Markdown Reference for OPS</span></span>

<span data-ttu-id="86f17-104">Markdown on kevyt merkintäkieli, jonka syntaksi on tekstipohjainen.</span><span class="sxs-lookup"><span data-stu-id="86f17-104">Markdown is a lightweight markup language with plain text formatting syntax.</span></span> <span data-ttu-id="86f17-105">Open Publishing Services (OPS) tukee Markdownille luotua CommonMark-standardia sekä joitakin mukautettuja Markdown-laajennuksia, jotka mahdollistavat docs.microsoft.com-sivuston sisältöjen monipuolisemmat muotoilut.</span><span class="sxs-lookup"><span data-stu-id="86f17-105">Open Publishing Services (OPS) supports the CommonMark standard for Markdown, plus some custom Markdown extensions designed to provide richer content on docs.microsoft.com.</span></span> <span data-ttu-id="86f17-106">Tämä artikkeli sisältää aakkostetun viiteoppaan docs.microsoft.com-sivustolla julkaistavan sisällön luomiseen Markdownilla OPS-ympäristössä.</span><span class="sxs-lookup"><span data-stu-id="86f17-106">This article provides an alphabetical reference for using Markdown in OPS for docs.microsoft.com.</span></span>

<span data-ttu-id="86f17-107">Voit kirjoittaa Markdown-syntaksia millä tahansa tekstieditorilla.</span><span class="sxs-lookup"><span data-stu-id="86f17-107">You can use any text editor to author Markdown.</span></span> <span data-ttu-id="86f17-108">Jos käytät sekä tavallista Markdown-syntaksia että mukautettuja OPS-laajennuksia, sinun kannattaa käyttää [VS Code](https://code.visualstudio.com/) -editoria, johon on asennettu [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack).</span><span class="sxs-lookup"><span data-stu-id="86f17-108">For an editor that facilitates inserting both standard Markdown syntax and custom OPS extensions, we recommend [VS Code](https://code.visualstudio.com/) with the [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) installed.</span></span>

<span data-ttu-id="86f17-109">OPS käyttää Markdigia standardinaan kaikissa uusissa säilöissä, ja Markdig otetaan käyttöön myös vanhemmissa säilöissä.</span><span class="sxs-lookup"><span data-stu-id="86f17-109">OPS has standardized on Markdig for all new repos, and older repos are migrating to Markdig.</span></span> <span data-ttu-id="86f17-110">Voit testata Markdownin hahmontamista Markdigissa verrattuna muihin vaihtoehtoihin osoitteessa [https://babelmark.github.io/](https://babelmark.github.io/).</span><span class="sxs-lookup"><span data-stu-id="86f17-110">You can test the rendering of Markdown in Markdig vs. other engines at [https://babelmark.github.io/](https://babelmark.github.io/).</span></span>

## <a name="alerts-note-tip-important-caution-warning"></a><span data-ttu-id="86f17-111">Ilmoitukset (huomautus, vinkki, tärkeää, huomio ja varoitus)</span><span class="sxs-lookup"><span data-stu-id="86f17-111">Alerts (Note, Tip, Important, Caution, Warning)</span></span>

<span data-ttu-id="86f17-112">OPS:lle suunnitellussa Markdown-laajennuksessa ilmoituksilla luodaan tekstilohkoja, jotka hahmonnetaan docs.microsoft.com-sivustolle käyttämällä sisällön tärkeyttä korostavia värejä ja kuvakkeita.</span><span class="sxs-lookup"><span data-stu-id="86f17-112">Alerts is an OPS-specific Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="86f17-113">Seuraavia ilmoitustyyppejä tuetaan:</span><span class="sxs-lookup"><span data-stu-id="86f17-113">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="86f17-114">Ilmoitukset näyttävät seuraavanlaisilta docs.microsoft.com-sivustolla:</span><span class="sxs-lookup"><span data-stu-id="86f17-114">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="86f17-115">Tietoja, jotka käyttäjän on huomattava tekstiä silmäillessään.</span><span class="sxs-lookup"><span data-stu-id="86f17-115">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="86f17-116">Valinnaista tietoa, joka auttaa käyttäjää suoriutumaan entistä paremmin.</span><span class="sxs-lookup"><span data-stu-id="86f17-116">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86f17-117">Oleellista tietoa, jota käyttäjä tarvitsee onnistuakseen.</span><span class="sxs-lookup"><span data-stu-id="86f17-117">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="86f17-118">Toimenpiteen mahdolliset kielteiset seuraukset.</span><span class="sxs-lookup"><span data-stu-id="86f17-118">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="86f17-119">Toimenpiteen varmat vaaralliset seuraukset.</span><span class="sxs-lookup"><span data-stu-id="86f17-119">Dangerous certain consequences of an action.</span></span>

## <a name="code-snippets"></a><span data-ttu-id="86f17-120">Koodikatkelmat</span><span class="sxs-lookup"><span data-stu-id="86f17-120">Code snippets</span></span>

<span data-ttu-id="86f17-121">Voit upottaa koodikatkelmia Markdown-tiedostoihin:</span><span class="sxs-lookup"><span data-stu-id="86f17-121">You can embed code snippets in your Markdown files:</span></span>

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a><span data-ttu-id="86f17-122">Otsikot</span><span class="sxs-lookup"><span data-stu-id="86f17-122">Headings</span></span>

<span data-ttu-id="86f17-123">OPS tukee kuuden tason Markdown-otsikoita:</span><span class="sxs-lookup"><span data-stu-id="86f17-123">OPS supports six levels of Markdown headings:</span></span>

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- <span data-ttu-id="86f17-124">Viimeisen `#`-merkin ja otsikon välissä on oltava välilyönti.</span><span class="sxs-lookup"><span data-stu-id="86f17-124">There must be a space between the last `#` and heading text.</span></span>
- <span data-ttu-id="86f17-125">Kussakin Markdown-tiedostossa on oltava täsmälleen yksi ylimmän tason otsikko (H1).</span><span class="sxs-lookup"><span data-stu-id="86f17-125">Each Markdown file must have one and only one H1.</span></span>
- <span data-ttu-id="86f17-126">H1-otsikon on oltava tiedoston ensimmäinen sisältö YML-metatietoalueen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="86f17-126">The H1 must be the first content in the file after the YML metadata block.</span></span>
- <span data-ttu-id="86f17-127">H2-tason otsikot näkyvät automaattisesti julkaistun tiedoston oikeassa reunassa olevassa siirtymävalikossa.</span><span class="sxs-lookup"><span data-stu-id="86f17-127">H2s automatically appear in the right-hand navigating menu of the published file.</span></span> <span data-ttu-id="86f17-128">Alempien tasojen otsikot eivät näy siirtymävalikossa. H2-otsikoita kannattaakin käyttää siten, että lukijoiden on helppoa liikkua sisällössä.</span><span class="sxs-lookup"><span data-stu-id="86f17-128">Lower-level headings do not, so use H2s strategically to help readers navigate your content.</span></span>
- <span data-ttu-id="86f17-129">HTML-otsikoita, kuten `<h1>`, ei suositella, ja joissakin tapauksissa ne aiheuttavat koontiversiovaroituksia.</span><span class="sxs-lookup"><span data-stu-id="86f17-129">HMTL headings, such as `<h1>`, are not recommended and in some cases will cause build warnings.</span></span>
- <span data-ttu-id="86f17-130">Tiedoston yksittäisiin otsikoihin voi lisätä linkkejä [kirjanmerkkien](#bookmark-links) avulla.</span><span class="sxs-lookup"><span data-stu-id="86f17-130">You can link to individual headings in a file via [bookmarks](#bookmark-links).</span></span>

## <a name="html"></a><span data-ttu-id="86f17-131">HTML</span><span class="sxs-lookup"><span data-stu-id="86f17-131">HTML</span></span>

<span data-ttu-id="86f17-132">Vaikka Markdown tukee rivin sisäistä HTML:ää, HTML:ää ei suositella julkaistaessa sisältöä OPS:n kautta. Muut kuin tietyt määrätyt arvot aiheuttavat koontiversiovirheitä tai -varoituksia.</span><span class="sxs-lookup"><span data-stu-id="86f17-132">Although Markdown supports inline HTML, HTML is not recommended for publishing via OPS, and except for a limited list of values will cause build errors or warnings.</span></span> <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a><span data-ttu-id="86f17-133">Kuvat</span><span class="sxs-lookup"><span data-stu-id="86f17-133">Images</span></span>

<span data-ttu-id="86f17-134">Kuvan liittämisen syntaksi on seuraava:</span><span class="sxs-lookup"><span data-stu-id="86f17-134">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

<span data-ttu-id="86f17-135">`alt text` on kuvan lyhyt kuvaus, ja `<folder path>` on kuvan suhteellinen polku.</span><span class="sxs-lookup"><span data-stu-id="86f17-135">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="86f17-136">Vaihtoehtoista tekstiä tarvitaan heikkonäköisten käyttämiä näytönlukuohjelmia varten.</span><span class="sxs-lookup"><span data-stu-id="86f17-136">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="86f17-137">Siitä on hyötyä myös, jos sivustolla on virhe, joka estää kuvan hahmontamisen.</span><span class="sxs-lookup"><span data-stu-id="86f17-137">It is also useful if there is a site bug where the image cannot render.</span></span>

<span data-ttu-id="86f17-138">Kuvat on tallennettava asiakirjajoukon `/media`-kansioon.</span><span class="sxs-lookup"><span data-stu-id="86f17-138">Images should be stored in a `/media` folder within your doc set.</span></span> <span data-ttu-id="86f17-139">Seuraavia kuvatiedostotyyppejä tuetaan oletusarvoisesti:</span><span class="sxs-lookup"><span data-stu-id="86f17-139">The following file types are supported by default for images:</span></span>

- <span data-ttu-id="86f17-140">.jpg</span><span class="sxs-lookup"><span data-stu-id="86f17-140">.jpg</span></span>
- <span data-ttu-id="86f17-141">.png</span><span class="sxs-lookup"><span data-stu-id="86f17-141">.png</span></span>

<span data-ttu-id="86f17-142">Muiden kuvatyyppien tuen voi lisätä lisäämällä ne resursseina asiakirjajoukon docfx.json-tiedostoon<!--add link to reference when available-->.</span><span class="sxs-lookup"><span data-stu-id="86f17-142">You can add support for other image types by adding them as resources to the docfx.json file<!--add link to reference when available--> for your doc set.</span></span>

## <a name="links"></a><span data-ttu-id="86f17-143">Linkit</span><span class="sxs-lookup"><span data-stu-id="86f17-143">Links</span></span>

<span data-ttu-id="86f17-144">Useimmissa tapauksissa OPS käyttää tavallisia Markdown-linkkejä viittaamaan muihin tiedostoihin ja muille sivuille.</span><span class="sxs-lookup"><span data-stu-id="86f17-144">In most cases, OPS uses standard Markdown links to other files and pages.</span></span> <span data-ttu-id="86f17-145">Linkkien tyypit on kuvattu alla olevissa alakohdissa.</span><span class="sxs-lookup"><span data-stu-id="86f17-145">The types of links are described in subsections below.</span></span>

> [!TIP]
> <span data-ttu-id="86f17-146">Docs Authoring Pack VS Codelle voi auttaa lisäämään suhteelliset linkit ja kirjanmerkit oikein ilman polkujen selvittämisen vaivaa!</span><span class="sxs-lookup"><span data-stu-id="86f17-146">The Docs Authoring Pack for VS Code can help insert relative links and bookmarks correctly without the tedium of figuring out the paths!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86f17-147">Älä lisää kieliasetuskoodeja (esimerkiksi en-us) Microsoft-sivustoille viittaaviin linkkeihin.</span><span class="sxs-lookup"><span data-stu-id="86f17-147">Do not include locale codes, such as en-us, in your links to Microsoft sites.</span></span> <span data-ttu-id="86f17-148">Pysyväiskoodatut kieliasetuskoodit estävät lokalisoidun sisällön hahmontamisen, mikä on ikävää muunkielisille käyttäjille ja aiheuttaa merkittäviä lokalisointikustannuksia.</span><span class="sxs-lookup"><span data-stu-id="86f17-148">Hard-coded locale codes prevent localized content from rendering, which is a bad customer experience for users in other locales and incurs significant localization costs.</span></span> <span data-ttu-id="86f17-149">Kieliasetuskoodi sisältyy oletusarvoisesti selaimesta kopioituun URL-osoitteeseen, joten sinun on poistettava se manuaalisesti luodessasi linkin.</span><span class="sxs-lookup"><span data-stu-id="86f17-149">When you copy a URL from a browser, the locale code is included by default, so you need to manually delete it when you create your link.</span></span> <span data-ttu-id="86f17-150">Esimerkki oikeasta muodosta:</span><span class="sxs-lookup"><span data-stu-id="86f17-150">For example, use:</span></span>
>
> `[Microsoft](https://www.microsoft.com)`
>
> <span data-ttu-id="86f17-151">Virheellinen muoto:</span><span class="sxs-lookup"><span data-stu-id="86f17-151">Not:</span></span>
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a><span data-ttu-id="86f17-152">Saman asiakirjajoukon tiedostoihin viittaavat suhteelliset linkit</span><span class="sxs-lookup"><span data-stu-id="86f17-152">Relative links to files in the same doc set</span></span>

<span data-ttu-id="86f17-153">Suhteellinen polku on kohdetiedostoon johtava polku, joka on määritetty suhteessa nykyiseen tiedostoon.</span><span class="sxs-lookup"><span data-stu-id="86f17-153">A relative path is the path to the target file relative to the current file.</span></span> <span data-ttu-id="86f17-154">OPS-ympäristössä suhteellisen polun avulla voi muodostaa linkin samassa asiakirjajoukossa sijaitsevaan toiseen tiedostoon.</span><span class="sxs-lookup"><span data-stu-id="86f17-154">In OPS, you can use a relative path to link to another file within the same doc set.</span></span> <span data-ttu-id="86f17-155">Suhteellisen polun syntaksi on seuraava:</span><span class="sxs-lookup"><span data-stu-id="86f17-155">The syntax for a relative path is as follows:</span></span>

```markdown
[link text](../../folder/filename.md)
```

<span data-ttu-id="86f17-156">`../` tarkoittaa hierarkiassa yhtä ylempänä olevaa tasoa.</span><span class="sxs-lookup"><span data-stu-id="86f17-156">Where `../` indicates one level above in the hierarchy.</span></span>

- <span data-ttu-id="86f17-157">Suhteellinen polku selvitetään ja .md-tunniste poistetaan koonnin aikana.</span><span class="sxs-lookup"><span data-stu-id="86f17-157">The relative path will be resolved during the build, including removal of the .md extension.</span></span>
- <span data-ttu-id="86f17-158">Voit muodostaa linkin pääkansiossa olevaan tiedostoon "../"-rakenteen avulla, kunhan kyseinen tiedosto kuuluu samaan asiakirjajoukkoon.</span><span class="sxs-lookup"><span data-stu-id="86f17-158">You can use "../" to link to a file in the parent folder, but that file has to be in the same doc set.</span></span> <span data-ttu-id="86f17-159">"../"-rakenteella ei voi muodostaa linkkiä jonkin toisen asiakirjajoukon kansiossa sijaitsevaan tiedostoon.</span><span class="sxs-lookup"><span data-stu-id="86f17-159">You cannot use "../" to link to a file in another doc set folder.</span></span>
- <span data-ttu-id="86f17-160">OPS tukee myös suhteellisen polun erityismuotoa, joka alkaa merkillä ~ (esimerkiksi ~/foo/bar.md).</span><span class="sxs-lookup"><span data-stu-id="86f17-160">OPS also supports a special form of relative path that starts with "~" (for example, ~/foo/bar.md).</span></span> <span data-ttu-id="86f17-161">Tämä syntaksi ilmaisee tiedoston suhteen asiakirjajoukon pääkansioon.</span><span class="sxs-lookup"><span data-stu-id="86f17-161">This syntax indicates a file relative to the root folder of a doc set.</span></span> <span data-ttu-id="86f17-162">Myös tämäntyyppinen polku vahvistetaan ja selvitetään koonnin aikana.</span><span class="sxs-lookup"><span data-stu-id="86f17-162">This kind of path is also validated and resolved during the build.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86f17-163">Lisää suhteelliseen polkuun tiedostotunniste.</span><span class="sxs-lookup"><span data-stu-id="86f17-163">Include the file extension in the relative path.</span></span> <span data-ttu-id="86f17-164">Koonnin aikana kyseisen suhteellisen polun kohdetiedoston olemassaolo vahvistetaan.</span><span class="sxs-lookup"><span data-stu-id="86f17-164">Build validates the existence of the target file of that relative path.</span></span> <span data-ttu-id="86f17-165">Jos suhteellinen polku ei sisällä tiedostotunnistetta, on todennäköistä, että koontiversio antaa varoituksen katkenneesta hyperlinkistä.</span><span class="sxs-lookup"><span data-stu-id="86f17-165">If relative path does not include file extension, it is likely build will report a warning of broken link.</span></span> <span data-ttu-id="86f17-166">Esimerkki oikeasta muodosta:</span><span class="sxs-lookup"><span data-stu-id="86f17-166">For example, use:</span></span>
>
> `[link text](../../folder/filename.md)`
>
> <span data-ttu-id="86f17-167">Virheellinen muoto:</span><span class="sxs-lookup"><span data-stu-id="86f17-167">Not:</span></span>
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a><span data-ttu-id="86f17-168">Muihin OPS:ssä sijaitseviin tiedostoihin viittaavat absoluuttiset linkit</span><span class="sxs-lookup"><span data-stu-id="86f17-168">Absolute links to other files in OPS</span></span>

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

<span data-ttu-id="86f17-169">Älä käytä tiedostotunnistetta (.md).</span><span class="sxs-lookup"><span data-stu-id="86f17-169">Do not include the file extension (.md).</span></span> <span data-ttu-id="86f17-170">Tämä muodostaa linkin Linuxin Overview-tiedostoon Azuren Articles-asiakirjajoukon ulkopuolelta.</span><span class="sxs-lookup"><span data-stu-id="86f17-170">This links to the Linux overview file from outside the Azure "articles" doc set.</span></span>

### <a name="links-to-external-sites"></a><span data-ttu-id="86f17-171">Ulkoisiin sivustoihin viittaavat linkit</span><span class="sxs-lookup"><span data-stu-id="86f17-171">Links to external sites</span></span>

```markdown
[Microsoft](https://www.microsoft.com)
```

<span data-ttu-id="86f17-172">URL-pohjainen linkki toiselle verkkosivulle (alun on oltava https://).</span><span class="sxs-lookup"><span data-stu-id="86f17-172">URL-based link to another web page (must include https://).</span></span>

### <a name="bookmark-links"></a><span data-ttu-id="86f17-173">Kirjanmerkkilinkit</span><span class="sxs-lookup"><span data-stu-id="86f17-173">Bookmark links</span></span>

<span data-ttu-id="86f17-174">Kirjanmerkkilinkki samassa säilössä sijaitsevan toisen tiedoston otsikkoon:</span><span class="sxs-lookup"><span data-stu-id="86f17-174">Bookmark link to a heading in another file in the same repo:</span></span>

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<span data-ttu-id="86f17-175">Kirjanmerkkilinkki nykyisen tiedoston otsikkoon:</span><span class="sxs-lookup"><span data-stu-id="86f17-175">Bookmark link to a heading in the current file:</span></span>

```markdown
[Managed Disks](#managed-disks)
```

<span data-ttu-id="86f17-176">Kirjoita ristikkomerkin perään otsikon sanat siten, että poistat välimerkit ja korvaat välilyönnit viivalla.</span><span class="sxs-lookup"><span data-stu-id="86f17-176">Use a hash tag followed by the words of the heading with punctuation removed and spaces replaced with dashes.</span></span>

### <a name="explicit-anchor-links"></a><span data-ttu-id="86f17-177">Eksplisiittiset ankkurilinkit</span><span class="sxs-lookup"><span data-stu-id="86f17-177">Explicit anchor links</span></span>

<span data-ttu-id="86f17-178">Eksplisiittisiä ankkurilinkkejä, joissa käytetään HTML-tunnistetta `<a>` **ei edellytetä eikä suositella** käytettäväksi muuten kuin keskuksessa ja saapumissivuilla.</span><span class="sxs-lookup"><span data-stu-id="86f17-178">Explicit anchor links using the `<a>` HTML tag are **not required or recommended** except in hub and landing pages.</span></span> <span data-ttu-id="86f17-179">Käytä yleisissä Markdown-tiedostoissa kirjanmerkkejä yllä kuvatulla tavalla.</span><span class="sxs-lookup"><span data-stu-id="86f17-179">Use bookmarks as described above in general Markdown files.</span></span> <span data-ttu-id="86f17-180">Käytä keskuksissa ja saapumissivuilla ankkureita seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-180">For hub and landing pages, use anchors as follows:</span></span>

<span data-ttu-id="86f17-181">`## <a id="AnchorText"> </a>Header text` tai `## <a name="AnchorText"> </a>Header text`</span><span class="sxs-lookup"><span data-stu-id="86f17-181">`## <a id="AnchorText"> </a>Header text` or `## <a name="AnchorText"> </a>Header text`</span></span>

<span data-ttu-id="86f17-182">Voit muodostaa eksplisiittisiin ankkureihin viittaavia linkkejä seuraavalla syntaksilla:</span><span class="sxs-lookup"><span data-stu-id="86f17-182">To link to explicit anchors, use the following syntax:</span></span>

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a><span data-ttu-id="86f17-183">XREF-linkit (ristiviittaus)</span><span class="sxs-lookup"><span data-stu-id="86f17-183">XREF (cross reference) links</span></span>

<span data-ttu-id="86f17-184">Voit muodostaa linkkejä automaattisesti muodostettuihin ohjelmointirajapintaviitesivuihin nykyisessä asiakirjajoukossa tai muissa asiakirjajoukoissa käyttämällä XREF-linkkejä, joilla on yksilöivä tunnus (UID).</span><span class="sxs-lookup"><span data-stu-id="86f17-184">To link to auto-generated API references pages in the current doc set or other doc sets, use XREF links with the unique ID (UID).</span></span>

> [!NOTE]
> <span data-ttu-id="86f17-185">Voidaksesi viitata muiden asiakirjajoukkojen ohjelmointirajapintaviitesivuihin sinun on lisättävä määritys `xrefService` tiedostoon `docfx.json`.</span><span class="sxs-lookup"><span data-stu-id="86f17-185">To reference API reference pages in other doc sets, you need to add `xrefService` configuration in `docfx.json` file.</span></span>
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

<span data-ttu-id="86f17-186">UID-tunnus vastaa täydellistä luokan ja jäsenen nimeä.</span><span class="sxs-lookup"><span data-stu-id="86f17-186">The UID equates to the fully qualified class and member name.</span></span> <span data-ttu-id="86f17-187">Jos lisäät \*-merkin UID:n perään, linkki edustaa kuormitussivua tietyn ohjelmointirajapinnan sijaan.</span><span class="sxs-lookup"><span data-stu-id="86f17-187">If you add a \* after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="86f17-188">Esimerkiksi käyttämällä rakennetta `List<T>.BinarySearch*` voit muodostaa linkin BinarySearch-metodisivuun sen sijaan, että linkki viittaisi tiettyyn kuormitukseen, kuten rakenteessa `List<T>.BinarySearch(T, IComparer<T>)`.</span><span class="sxs-lookup"><span data-stu-id="86f17-188">For example, use `List<T>.BinarySearch*` to link to the BinarySearch Method page instead of linking to a specific overload such as `List<T>.BinarySearch(T, IComparer<T>)`.</span></span>

<span data-ttu-id="86f17-189">Voit käyttää jotakin seuraavista syntakseista:</span><span class="sxs-lookup"><span data-stu-id="86f17-189">You can use one of the following syntaxes:</span></span>

- <span data-ttu-id="86f17-190">Automaattinen linkki: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="86f17-190">Auto-link: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span></span>

  <span data-ttu-id="86f17-191">Valinnainen kyselyparametri `displayProperty` tuottaa täydellisen linkkitekstin.</span><span class="sxs-lookup"><span data-stu-id="86f17-191">The optional `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="86f17-192">Oletusarvoisesti linkkitekstissä näkyy vain jäsenen tai tyypin nimi.</span><span class="sxs-lookup"><span data-stu-id="86f17-192">By default, link text shows only the member or type name.</span></span>

- <span data-ttu-id="86f17-193">Markdown-linkki: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="86f17-193">Markdown link: `[link text](xref:UID)`</span></span>
  
  <span data-ttu-id="86f17-194">Käytä tätä vaihtoehtoa, kun haluat mukauttaa näkyviin tulevaa linkkitekstiä.</span><span class="sxs-lookup"><span data-stu-id="86f17-194">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="86f17-195">Esimerkkejä:</span><span class="sxs-lookup"><span data-stu-id="86f17-195">Examples:</span></span>

- <span data-ttu-id="86f17-196">`<xref:System.String>` hahmontuu muotoon "String".</span><span class="sxs-lookup"><span data-stu-id="86f17-196">`<xref:System.String>` renders as "String".</span></span>
- <span data-ttu-id="86f17-197">`<xref:System.String?displayProperty=nameWithType>` hahmontuu muotoon "System.String".</span><span class="sxs-lookup"><span data-stu-id="86f17-197">`<xref:System.String?displayProperty=nameWithType>` renders as "System.String".</span></span>
- <span data-ttu-id="86f17-198">`[String class](xref:System.String)` hahmontuu muotoon "String class".</span><span class="sxs-lookup"><span data-stu-id="86f17-198">`[String class](xref:System.String)` renders as "String class".</span></span>

<span data-ttu-id="86f17-199">Tällä hetkellä ei ole olemassa helppoa tapaa löytää UID-tunnuksia.</span><span class="sxs-lookup"><span data-stu-id="86f17-199">Right now, there is no easy way to find the UIDs.</span></span> <span data-ttu-id="86f17-200"><!-- ? -->Paras tapa löytää ohjelmointirajapinnan UID-tunnus on tutkia linkitettävän ohjelmointirajapintasivun lähdettä ja etsiä sieltä ms.assetid-arvo.</span><span class="sxs-lookup"><span data-stu-id="86f17-200"><!-- ? -->The best way to find the UID for an API is to view the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="86f17-201">Yksittäisiä kuormitusarvoja ei näytetä lähteessä.</span><span class="sxs-lookup"><span data-stu-id="86f17-201">Individual overload values are not shown in the source.</span></span> <span data-ttu-id="86f17-202">Pyrimme luomaan paremman järjestelmän tulevaisuudessa.</span><span class="sxs-lookup"><span data-stu-id="86f17-202">We're working on having a better system in the future.</span></span>

<span data-ttu-id="86f17-203">Kun UID-tunnus sisältää erikoismerkkejä \`, \# tai \*, UID-arvo on HTML-koodattava vastaavasti seuraavasti: `%60`, `%23` tai `%2A`.</span><span class="sxs-lookup"><span data-stu-id="86f17-203">When the UID contains the special characters \`, \#, or \*, the UID value needs to be HTML encoded as `%60`, `%23`, and `%2A`, respectively.</span></span> <span data-ttu-id="86f17-204">Joskus myös sulkeet koodataan, mutta tämä ei ole välttämätöntä.</span><span class="sxs-lookup"><span data-stu-id="86f17-204">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="86f17-205">Esimerkkejä:</span><span class="sxs-lookup"><span data-stu-id="86f17-205">Examples:</span></span>

- <span data-ttu-id="86f17-206">System.Threading.Tasks.Task\`1 muuttuu muotoon `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="86f17-206">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="86f17-207">System.Exception.\#ctor muuttuu muotoon `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="86f17-207">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="86f17-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) muuttuu muotoon `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="86f17-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a><span data-ttu-id="86f17-209">Luettelot (numeroidut luettelot, luettelomerkeillä varustetut luettelot ja tarkistusluettelot)</span><span class="sxs-lookup"><span data-stu-id="86f17-209">Lists (Numbered, Bulleted, Checklist)</span></span>

### <a name="numbered-list"></a><span data-ttu-id="86f17-210">Numeroitu luettelo</span><span class="sxs-lookup"><span data-stu-id="86f17-210">Numbered list</span></span>

<span data-ttu-id="86f17-211">Voit luoda numeroidun luettelon käyttämällä aina numeroa 1. Numerot hahmonnetaan järjestyslukuluetteloksi julkaisuvaiheessa.</span><span class="sxs-lookup"><span data-stu-id="86f17-211">To create a numbered list, you can use all 1s, which are rendered as a sequential list when published.</span></span> <span data-ttu-id="86f17-212">Voit parantaa lähteen luettavuutta käyttämällä luetteloissa kasvavia järjestyslukuja.</span><span class="sxs-lookup"><span data-stu-id="86f17-212">For increased source readability, you can increment your lists.</span></span>

<span data-ttu-id="86f17-213">Älä käytä luetteloissa kirjaimia. Tämä pätee myös sisäkkäisiin luetteloihin.</span><span class="sxs-lookup"><span data-stu-id="86f17-213">Do not use letters in lists, including nested lists.</span></span> <span data-ttu-id="86f17-214">Ne eivät hahmonnu oikein, kun ne julkaistaan OPS:n kautta.</span><span class="sxs-lookup"><span data-stu-id="86f17-214">They do not render correctly when published via OPS.</span></span> <span data-ttu-id="86f17-215">Sisäkkäisten luetteloiden numerointi hahmontuu julkaistaessa pieniksi kirjaimiksi.</span><span class="sxs-lookup"><span data-stu-id="86f17-215">Nested lists using numbers will render as lowercase letters when published.</span></span> <span data-ttu-id="86f17-216">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="86f17-216">For example:</span></span>

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

<span data-ttu-id="86f17-217">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-217">This renders as follows:</span></span>

1. <span data-ttu-id="86f17-218">Tämä on</span><span class="sxs-lookup"><span data-stu-id="86f17-218">This is</span></span>
1. <span data-ttu-id="86f17-219">numeroitu pääluettelo</span><span class="sxs-lookup"><span data-stu-id="86f17-219">a parent numbered list</span></span>
   1. <span data-ttu-id="86f17-220">ja tämä on</span><span class="sxs-lookup"><span data-stu-id="86f17-220">and this is</span></span>
   1. <span data-ttu-id="86f17-221">numeroitu sisäkkäinen luettelo</span><span class="sxs-lookup"><span data-stu-id="86f17-221">a nested numbered list</span></span>
1. <span data-ttu-id="86f17-222">(loppu)</span><span class="sxs-lookup"><span data-stu-id="86f17-222">(fin)</span></span>

### <a name="bulleted-list"></a><span data-ttu-id="86f17-223">Luettelomerkeillä varustettu luettelo</span><span class="sxs-lookup"><span data-stu-id="86f17-223">Bulleted list</span></span>

<span data-ttu-id="86f17-224">Voit luoda luettelomerkeillä varustetun luettelon lisäämällä kunkin rivin alkuun symbolin `-` ja sen perään välilyönnin:</span><span class="sxs-lookup"><span data-stu-id="86f17-224">To create a bulleted list, use `-` followed by a space at the beginning of each line:</span></span>

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

<span data-ttu-id="86f17-225">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-225">This renders as follows:</span></span>

- <span data-ttu-id="86f17-226">Tämä on</span><span class="sxs-lookup"><span data-stu-id="86f17-226">This is</span></span>
- <span data-ttu-id="86f17-227">luettelomerkeillä varustettu pääluettelo</span><span class="sxs-lookup"><span data-stu-id="86f17-227">a parent bulleted list</span></span>
  - <span data-ttu-id="86f17-228">ja tämä on</span><span class="sxs-lookup"><span data-stu-id="86f17-228">and this is</span></span>
  - <span data-ttu-id="86f17-229">luettelomerkeillä varustettu sisäkkäinen luettelo</span><span class="sxs-lookup"><span data-stu-id="86f17-229">a nested bulleted list</span></span>
- <span data-ttu-id="86f17-230">Valmista!</span><span class="sxs-lookup"><span data-stu-id="86f17-230">All done!</span></span>

### <a name="checklist"></a><span data-ttu-id="86f17-231">Tarkistusluettelo</span><span class="sxs-lookup"><span data-stu-id="86f17-231">Checklist</span></span>

<span data-ttu-id="86f17-232">Tarkistusluetteloita voi laatia mukautetun Markdown-laajennuksen avulla (vain) docs.microsoft.com-sivustolle:</span><span class="sxs-lookup"><span data-stu-id="86f17-232">Checklists are available for use on docs.microsoft.com (only) via a custom Markdown extension:</span></span>

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

<span data-ttu-id="86f17-233">Tämä esimerkki hahmontuu docs.microsoft.com-sivustolla seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-233">This example renders on docs.microsoft.com like this:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="86f17-234">Luettelokohde 1</span><span class="sxs-lookup"><span data-stu-id="86f17-234">List item 1</span></span>
> * <span data-ttu-id="86f17-235">Luettelokohde 2</span><span class="sxs-lookup"><span data-stu-id="86f17-235">List item 2</span></span>
> * <span data-ttu-id="86f17-236">Luettelokohde 3</span><span class="sxs-lookup"><span data-stu-id="86f17-236">List item 3</span></span>

<span data-ttu-id="86f17-237">Voit käyttää tarkistusluetteloita artikkelin alussa tai lopussa kuvaamaan artikkelin sisältämää opittavaa sisältöä.</span><span class="sxs-lookup"><span data-stu-id="86f17-237">Use checklists at the beginning or end of an article to summarize "What will you learn" or "What have you learned" content.</span></span> <span data-ttu-id="86f17-238">Älä lisää tarkistusluetteloja satunnaisesti eri puolille artikkelia.</span><span class="sxs-lookup"><span data-stu-id="86f17-238">Do not add random checklists throughout your articles.</span></span>
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a><span data-ttu-id="86f17-239">Siirtyminen seuraavaan vaiheeseen</span><span class="sxs-lookup"><span data-stu-id="86f17-239">Next step action</span></span>

<span data-ttu-id="86f17-240">Mukautetun laajennuksen avulla voit lisätä seuraavaan vaiheeseen siirtymisen painikkeen (vain) docs.microsoft.com-sivustolle.</span><span class="sxs-lookup"><span data-stu-id="86f17-240">You can use a custom extension to add a next step action button to pages on docs.microsoft.com (only).</span></span>

<span data-ttu-id="86f17-241">Syntaksi on seuraava:</span><span class="sxs-lookup"><span data-stu-id="86f17-241">The syntax is as follows:</span></span>

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

<span data-ttu-id="86f17-242">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="86f17-242">For example:</span></span>

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

<span data-ttu-id="86f17-243">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-243">This renders as follows:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="86f17-244">Tietoja perustyylistä</span><span class="sxs-lookup"><span data-stu-id="86f17-244">Learn about basic style</span></span>](style-quick-start.md)

<span data-ttu-id="86f17-245">Seuraavaan vaiheeseen siirtymisessä voi käyttää mitä tahansa tuettua linkkiä, mukaan lukien toiselle verkkosivulle viittaavaa Markdown-linkkiä.</span><span class="sxs-lookup"><span data-stu-id="86f17-245">You can use any supported link in a next step action, including a Markdown link to another web page.</span></span> <span data-ttu-id="86f17-246">Useimmissa tapauksissa seuraavaan vaiheeseen siirtymisen linkki on toiseen samassa asiakirjajoukossa olevaan tiedostoon viittaava suhteellinen linkki.</span><span class="sxs-lookup"><span data-stu-id="86f17-246">In most cases, the next action link will be a relative link to another file in the same doc set.</span></span>

## <a name="section-definition"></a><span data-ttu-id="86f17-247">Osion määrittely</span><span class="sxs-lookup"><span data-stu-id="86f17-247">Section definition</span></span>

<span data-ttu-id="86f17-248"><!-- more info about this would be helpful! --> Joskus osion määrittely on tarpeen.</span><span class="sxs-lookup"><span data-stu-id="86f17-248"><!-- more info about this would be helpful! --> You might need to define a section.</span></span> <span data-ttu-id="86f17-249">Tätä syntaksia käytetään eniten kooditaulukoissa.</span><span class="sxs-lookup"><span data-stu-id="86f17-249">This syntax is mostly used for code tables.</span></span>
<span data-ttu-id="86f17-250">Seuraavassa on esimerkki.</span><span class="sxs-lookup"><span data-stu-id="86f17-250">See the following example:</span></span>

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

<span data-ttu-id="86f17-251">Edellä oleva Markdown-tekstikatkelma hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-251">The preceding blockquote Markdown text will be rendered as:</span></span>
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a><span data-ttu-id="86f17-252">Valitsimet</span><span class="sxs-lookup"><span data-stu-id="86f17-252">Selectors</span></span>

<span data-ttu-id="86f17-253"><!-- could be more clear! --> Valitsimen avulla voit yhdistää saman artikkelin eri sivuja.</span><span class="sxs-lookup"><span data-stu-id="86f17-253"><!-- could be more clear! --> You can use a selector when you want to connect different pages for the same article.</span></span> <span data-ttu-id="86f17-254">Näin lukijat voivat siirtyä sivulta toiselle.</span><span class="sxs-lookup"><span data-stu-id="86f17-254">Readers can then switch between those pages.</span></span>

> [!NOTE]
> <span data-ttu-id="86f17-255">Tämä laajennus toimii eri tavoin docs.microsoft.com-sivustossa ja MSDN:ssä.</span><span class="sxs-lookup"><span data-stu-id="86f17-255">This extension works differently between docs.microsoft.com and MSDN.</span></span> <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a><span data-ttu-id="86f17-256">Yksittäinen valitsin</span><span class="sxs-lookup"><span data-stu-id="86f17-256">Single selector</span></span>

```
> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)
```

<span data-ttu-id="86f17-257">... hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-257">... will be rendered like this:</span></span>

> [!div class="op_single_selector"]
> - [Universaali Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a><span data-ttu-id="86f17-266">Monivalitsin</span><span class="sxs-lookup"><span data-stu-id="86f17-266">Multi-selector</span></span>

```
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)
```

<span data-ttu-id="86f17-267">... hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-267">... will be rendered like this:</span></span>

> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | JavaScript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | JavaScript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | JavaScript)](how-to-write-workflows-major.md)

<!-- uncomment and link when Cory's topic is live
## Tabbed content

Tabs are a Markdown extension for docs.microsoft.com that allow us to present different versions of content, such as procedural steps to accomplish the same task on different platforms, in a tabbed format.

Because the syntax and requirements for tabbed content are fairly complex, they are documented separately in Tabbed Content.
-->

## <a name="tables"></a><span data-ttu-id="86f17-278">taulukoilla</span><span class="sxs-lookup"><span data-stu-id="86f17-278">Tables</span></span>

<span data-ttu-id="86f17-279">Yksinkertaisin tapa luoda taulukko Markdownilla on käyttää pystyviivoja ja yhdysmerkkejä.</span><span class="sxs-lookup"><span data-stu-id="86f17-279">The simplest way to create a table in Markdown is to use pipes and lines.</span></span> <span data-ttu-id="86f17-280">Voit luoda vakiomallisen taulukon otsikoineen lisäämällä ensimmäisen rivin jälkeen katkoviivan:</span><span class="sxs-lookup"><span data-stu-id="86f17-280">To create a standard table with a header, follow the first line with dashed line:</span></span>

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

<span data-ttu-id="86f17-281">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-281">This renders as follows:</span></span>

|<span data-ttu-id="86f17-282">Tämä on</span><span class="sxs-lookup"><span data-stu-id="86f17-282">This is</span></span>   |<span data-ttu-id="86f17-283">yksinkertainen</span><span class="sxs-lookup"><span data-stu-id="86f17-283">a simple</span></span>   |<span data-ttu-id="86f17-284">taulukon otsikko</span><span class="sxs-lookup"><span data-stu-id="86f17-284">table header</span></span>|
|----------|-----------|------------|
|<span data-ttu-id="86f17-285">taulukon</span><span class="sxs-lookup"><span data-stu-id="86f17-285">table</span></span>     |<span data-ttu-id="86f17-286">tiedot</span><span class="sxs-lookup"><span data-stu-id="86f17-286">data</span></span>       |<span data-ttu-id="86f17-287">tänne</span><span class="sxs-lookup"><span data-stu-id="86f17-287">here</span></span>        |
|<span data-ttu-id="86f17-288">niiden ei</span><span class="sxs-lookup"><span data-stu-id="86f17-288">it doesn't</span></span>|<span data-ttu-id="86f17-289">oikeastaan</span><span class="sxs-lookup"><span data-stu-id="86f17-289">actually</span></span>   |<span data-ttu-id="86f17-290">tarvitse asettua kauniisti!</span><span class="sxs-lookup"><span data-stu-id="86f17-290">have to line up nicely!</span></span>||

<span data-ttu-id="86f17-291">Voit myös luoda taulukon ilman otsikkoa.</span><span class="sxs-lookup"><span data-stu-id="86f17-291">You can also create a table without a header.</span></span> <span data-ttu-id="86f17-292">Esimerkiksi monisarakkeisen luettelon voi luoda seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-292">For example, to create a multiple-column list:</span></span>

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

<span data-ttu-id="86f17-293">Tämä hahmontuu seuraavalla tavalla:</span><span class="sxs-lookup"><span data-stu-id="86f17-293">This renders like this:</span></span>

|   |   |
| - | - |
| <span data-ttu-id="86f17-294">Tässä</span><span class="sxs-lookup"><span data-stu-id="86f17-294">This</span></span> | <span data-ttu-id="86f17-295">taulukossa</span><span class="sxs-lookup"><span data-stu-id="86f17-295">table</span></span> |
| <span data-ttu-id="86f17-296">ei ole</span><span class="sxs-lookup"><span data-stu-id="86f17-296">has no</span></span> | <span data-ttu-id="86f17-297">otsikkoa</span><span class="sxs-lookup"><span data-stu-id="86f17-297">header</span></span> |

<span data-ttu-id="86f17-298">Voit tasata sarakkeet käyttämällä kaksoispisteitä:</span><span class="sxs-lookup"><span data-stu-id="86f17-298">You can align the columns by using colons:</span></span>

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

<span data-ttu-id="86f17-299">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-299">Renders as follows:</span></span>

|                  |
|------------------|
|    <span data-ttu-id="86f17-300">tasattu oikealle:</span><span class="sxs-lookup"><span data-stu-id="86f17-300">right aligned:</span></span>|
|<span data-ttu-id="86f17-301">:tasattu vasemmalle</span><span class="sxs-lookup"><span data-stu-id="86f17-301">:left aligned</span></span>     |
|<span data-ttu-id="86f17-302">:keskitetty        :</span><span class="sxs-lookup"><span data-stu-id="86f17-302">:centered        :</span></span>|

> [!TIP]
> VS Coden Docs Authoring -laajennuksen avulla perustyyppisten Markdown-taulukoiden lisääminen sujuu helposti.
>
> Vaihtoehtoisesti voit käyttää [verkossa olevaa taulukkogeneraattoria](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a><span data-ttu-id="86f17-305">mx-tdBreakAll</span><span class="sxs-lookup"><span data-stu-id="86f17-305">mx-tdBreakAll</span></span>

> [!IMPORTANT]
> Tämä toimii vain docs.microsoft.com-sivustossa.

<span data-ttu-id="86f17-307">Markdownilla luotu taulukko saattaa laajentua oikealle ja muuttua lukukelvottomaksi.</span><span class="sxs-lookup"><span data-stu-id="86f17-307">If you create a table in Markdown, the table might expand to the right navigation and become unreadable.</span></span> <span data-ttu-id="86f17-308">Ongelman voi ratkaista sallimalla Docs-hahmonnuksen katkaista taulukko tarvittaessa.</span><span class="sxs-lookup"><span data-stu-id="86f17-308">You can solve that by allowing Docs rendering to break the table when needed.</span></span> <span data-ttu-id="86f17-309">Rivitä taulukko käyttämällä mukautettua luokkaa `[!div class="mx-tdBreakAll"]`.</span><span class="sxs-lookup"><span data-stu-id="86f17-309">Just wrap up the table with the custom class `[!div class="mx-tdBreakAll"]`.</span></span>

<span data-ttu-id="86f17-310">Ohessa on Markdown-malli kolmirivisestä taulukosta, joka rivitetään syntaksilla `div` ja luokan nimellä `mx-tdBreakAll`.</span><span class="sxs-lookup"><span data-stu-id="86f17-310">Here is a Markdown sample of a table with three rows that will be wrapped by a `div` with the class name `mx-tdBreakAll`.</span></span>

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

<span data-ttu-id="86f17-311">Se hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-311">It will be rendered like this:</span></span>

> [!div class="mx-tdBreakAll"]
> |<span data-ttu-id="86f17-312">Nimi</span><span class="sxs-lookup"><span data-stu-id="86f17-312">Name</span></span>|<span data-ttu-id="86f17-313">Syntaksi</span><span class="sxs-lookup"><span data-stu-id="86f17-313">Syntax</span></span>|<span data-ttu-id="86f17-314">Pakollinen hiljaisessa asennuksessa?</span><span class="sxs-lookup"><span data-stu-id="86f17-314">Mandatory for silent installation?</span></span>|<span data-ttu-id="86f17-315">Kuvaus</span><span class="sxs-lookup"><span data-stu-id="86f17-315">Description</span></span>|
> |-------------|----------|---------|---------|
> |<span data-ttu-id="86f17-316">Quiet</span><span class="sxs-lookup"><span data-stu-id="86f17-316">Quiet</span></span>|<span data-ttu-id="86f17-317">/quiet</span><span class="sxs-lookup"><span data-stu-id="86f17-317">/quiet</span></span>|<span data-ttu-id="86f17-318">Kyllä</span><span class="sxs-lookup"><span data-stu-id="86f17-318">Yes</span></span>|<span data-ttu-id="86f17-319">Suorittaa asennusohjelman näyttämättä käyttöliittymää tai kehotteita.</span><span class="sxs-lookup"><span data-stu-id="86f17-319">Runs the installer, displaying no UI and no prompts.</span></span>|
> |<span data-ttu-id="86f17-320">NoRestart</span><span class="sxs-lookup"><span data-stu-id="86f17-320">NoRestart</span></span>|<span data-ttu-id="86f17-321">/norestart</span><span class="sxs-lookup"><span data-stu-id="86f17-321">/norestart</span></span>|<span data-ttu-id="86f17-322">Ei</span><span class="sxs-lookup"><span data-stu-id="86f17-322">No</span></span>|<span data-ttu-id="86f17-323">Estää uudelleenkäynnistysyritykset.</span><span class="sxs-lookup"><span data-stu-id="86f17-323">Suppresses any attempts to restart.</span></span> <span data-ttu-id="86f17-324">Oletusarvoisesti käyttöliittymä näyttää kehotteen ennen uudelleenkäynnistystä.</span><span class="sxs-lookup"><span data-stu-id="86f17-324">By default, the UI will prompt before restart.</span></span>|
> |<span data-ttu-id="86f17-325">Help</span><span class="sxs-lookup"><span data-stu-id="86f17-325">Help</span></span>|<span data-ttu-id="86f17-326">/help</span><span class="sxs-lookup"><span data-stu-id="86f17-326">/help</span></span>|<span data-ttu-id="86f17-327">Ei</span><span class="sxs-lookup"><span data-stu-id="86f17-327">No</span></span>|<span data-ttu-id="86f17-328">Tarjoaa ohjeita ja pikaoppaita.</span><span class="sxs-lookup"><span data-stu-id="86f17-328">Provides help and quick reference.</span></span> <span data-ttu-id="86f17-329">Näyttää oikean tavan käyttää asennuskomentoa sekä luettelon kaikista asetuksista ja toiminnoista.</span><span class="sxs-lookup"><span data-stu-id="86f17-329">Displays the correct use of the setup command, including a list of all options and behaviors.</span></span>|

### <a name="mx-tdcol2breakall"></a><span data-ttu-id="86f17-330">mx-tdCol2BreakAll</span><span class="sxs-lookup"><span data-stu-id="86f17-330">mx-tdCol2BreakAll</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86f17-331">Tämä toimii vain docs.microsoft.com-sivustossa.</span><span class="sxs-lookup"><span data-stu-id="86f17-331">This only works on the docs.microsoft.com site.</span></span>

<span data-ttu-id="86f17-332">Toisinaan taulukon toisessa sarakkeessa saattaa olla hyvin pitkiä sanoja.</span><span class="sxs-lookup"><span data-stu-id="86f17-332">From time to time, you might have very long words in the second column of a table.</span></span> <span data-ttu-id="86f17-333">Saat ne katkeamaan kauniisti, kun käytät rivityssyntaksia `div` edellä kuvatulla tavalla mutta määrität luokaksi `mx-tdCol2BreakAll`.</span><span class="sxs-lookup"><span data-stu-id="86f17-333">To ensure they are broken apart nicely, you can apply the class `mx-tdCol2BreakAll` by using the `div` wrapper syntax as shown earlier.</span></span>

### <a name="html-tables"></a><span data-ttu-id="86f17-334">HTML-taulukot</span><span class="sxs-lookup"><span data-stu-id="86f17-334">HTML Tables</span></span>

<span data-ttu-id="86f17-335">HTML-taulukoita ei suositella käytettäväksi docs.microsoft.com-sivustolla.</span><span class="sxs-lookup"><span data-stu-id="86f17-335">HTML tables are not recommended for docs.microsoft.com.</span></span> <span data-ttu-id="86f17-336">Ne eivät ole helposti luettavassa muodossa lähteessä, mikä on Markdownin pääperiaate.</span><span class="sxs-lookup"><span data-stu-id="86f17-336">They are not human readable in the source - which is a key principle of Markdown.</span></span>

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a><span data-ttu-id="86f17-337">Videot</span><span class="sxs-lookup"><span data-stu-id="86f17-337">Videos</span></span>

### <a name="embedding-videos-into-a-markdown-page"></a><span data-ttu-id="86f17-338">Videoiden upottaminen Markdown-sivuun</span><span class="sxs-lookup"><span data-stu-id="86f17-338">Embedding videos into a Markdown page</span></span>

<span data-ttu-id="86f17-339">Tällä hetkellä OPS voi tukea videoita, jotka on julkaistu jossakin seuraavista kolmesta sijainnista:</span><span class="sxs-lookup"><span data-stu-id="86f17-339">Currently, OPS can support videos published to one of three locations:</span></span>

- <span data-ttu-id="86f17-340">YouTube</span><span class="sxs-lookup"><span data-stu-id="86f17-340">YouTube</span></span>
- <span data-ttu-id="86f17-341">Channel 9</span><span class="sxs-lookup"><span data-stu-id="86f17-341">Channel 9</span></span>
- <span data-ttu-id="86f17-342">Microsoftin oma One Player -järjestelmä</span><span class="sxs-lookup"><span data-stu-id="86f17-342">Microsoft's own 'One Player' system</span></span>

<span data-ttu-id="86f17-343">Voit upottaa videon seuraavan syntaksin avulla, ja OPS hahmontaa sen.</span><span class="sxs-lookup"><span data-stu-id="86f17-343">You can embed a video with the following syntax, and OPS will render it.</span></span>

```markdown
> [!VIDEO <embedded_video_link>]
```

<span data-ttu-id="86f17-344">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="86f17-344">Example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

<span data-ttu-id="86f17-345">... hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="86f17-345">... will be rendered as:</span></span>

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

<span data-ttu-id="86f17-346">Julkaistuilla sivuilla tulos näyttää tältä:</span><span class="sxs-lookup"><span data-stu-id="86f17-346">And it will be displayed like this on published pages:</span></span>

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> <span data-ttu-id="86f17-347">CH9-videon URL-osoitteen alun on oltava `https` ja lopun `/player`.</span><span class="sxs-lookup"><span data-stu-id="86f17-347">The CH9 video URL should start with `https` and end with `/player`.</span></span> <span data-ttu-id="86f17-348">Muuten upotetuksi tulee koko sivu pelkän videon sijasta.</span><span class="sxs-lookup"><span data-stu-id="86f17-348">Otherwise, it will embed the whole page instead of the video only.</span></span>

### <a name="uploading-new-videos"></a><span data-ttu-id="86f17-349">Uusien videoiden lataaminen</span><span class="sxs-lookup"><span data-stu-id="86f17-349">Uploading new videos</span></span>

<span data-ttu-id="86f17-350">Uudet videot on ladattava seuraavalla tavalla:</span><span class="sxs-lookup"><span data-stu-id="86f17-350">Any new videos should be uploaded using the following process:</span></span>

1. <span data-ttu-id="86f17-351">Liity IDWEB:n **docs_video_users**-ryhmään.</span><span class="sxs-lookup"><span data-stu-id="86f17-351">Join the **docs_video_users** group on IDWEB.</span></span>
1. <span data-ttu-id="86f17-352">Siirry osoitteeseen https://aka.ms/VideoUploadRequest ja anna videon tiedot.</span><span class="sxs-lookup"><span data-stu-id="86f17-352">Go to https://aka.ms/VideoUploadRequest and fill in the details for your video.</span></span> <span data-ttu-id="86f17-353">Tarvitset seuraavat tiedot (huomaa, että nämä tiedot eivät näy julkisesti):</span><span class="sxs-lookup"><span data-stu-id="86f17-353">You will need (note that none of these items will be visible to the public):</span></span>
    1. <span data-ttu-id="86f17-354">Videon nimi.</span><span class="sxs-lookup"><span data-stu-id="86f17-354">A title for your video.</span></span>
    1. <span data-ttu-id="86f17-355">Luettelo tuotteista tai palveluista, joihin video liittyy.</span><span class="sxs-lookup"><span data-stu-id="86f17-355">A list of products/services that your video is related to.</span></span>
    1. <span data-ttu-id="86f17-356">Kohdesivu tai (jos sivua ei vielä ole) asiakirjajoukko, jossa videota isännöidään.</span><span class="sxs-lookup"><span data-stu-id="86f17-356">The target page or (if you don’t have the page yet) doc set that your video will be hosted on.</span></span>
    1. <span data-ttu-id="86f17-357">Linkki videon MP4-tiedostoon (jos sinulla ei ole paikkaa, johon voisit tallentaa tiedoston, voit tallentaa sen tilapäisesti tänne:   `\\scratch2\scratch\apex`).</span><span class="sxs-lookup"><span data-stu-id="86f17-357">A link to the MP4 file for your video (if you don’t have a location to put the file, you can put it here temporarily:   `\\scratch2\scratch\apex`).</span></span> <span data-ttu-id="86f17-358">MP4-tiedostojen tarkkuuden on oltava vähintään 720p.</span><span class="sxs-lookup"><span data-stu-id="86f17-358">MP4 files should be 720p or higher.</span></span>
    1. <span data-ttu-id="86f17-359">Videon kuvaus.</span><span class="sxs-lookup"><span data-stu-id="86f17-359">A description of the video.</span></span>
1. <span data-ttu-id="86f17-360">Lähetä (tallenna) kohde.</span><span class="sxs-lookup"><span data-stu-id="86f17-360">Submit (save) that item.</span></span>
1. <span data-ttu-id="86f17-361">Video ladataan kahden arkipäivän kuluessa.</span><span class="sxs-lookup"><span data-stu-id="86f17-361">Within two business days, the video will get uploaded.</span></span> <span data-ttu-id="86f17-362">Upotuksessa tarvittava linkki lisätään työkohteeseen, ja kohde ratkaistaan lähettämällä se *takaisin sinulle*.</span><span class="sxs-lookup"><span data-stu-id="86f17-362">The link you need for embedding will be placed into the work item, and it will be resolved *back to you*.</span></span>
1. <span data-ttu-id="86f17-363">Kun olet hakenut videolinkin, sulje työkohde.</span><span class="sxs-lookup"><span data-stu-id="86f17-363">Once you have grabbed the video link, close the work item.</span></span>
1. <span data-ttu-id="86f17-364">Tämän jälkeen voit lisätä videolinkin julkaisuun seuraavalla syntaksilla:</span><span class="sxs-lookup"><span data-stu-id="86f17-364">The video link can then be added to your post, using this syntax:</span></span>

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
