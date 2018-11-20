---
title: .NET-artikkeleiden malli ja pikaohje
description: Tässä artikkelissa tarjotaan kätevä malli, jonka avulla voit luoda uusia artikkeleita .NET-ohjesäilöihin
ms.date: 11/07/2018
ms.openlocfilehash: 8980f5e39213d8f2edd1d29e66d900f2c3d04bbc
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609735"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a><span data-ttu-id="dadcf-103">Metatieto- ja Markdown-malli .NET-ohjeita varten</span><span class="sxs-lookup"><span data-stu-id="dadcf-103">Metadata and Markdown template for .NET docs</span></span>

<span data-ttu-id="dadcf-104">Tämä dotnet/docs-malli sisältää esimerkkejä Markdown-syntaksista sekä ohjeita metatietojen määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="dadcf-104">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span>

<span data-ttu-id="dadcf-105">Kun luot Markdown-tiedostoa, kopioi liitteenä oleva malli uuteen tiedostoon, täytä metatiedot alla olevien ohjeiden mukaan ja määritä artikkelin otsikolle yllä oleva H1-otsikko.</span><span class="sxs-lookup"><span data-stu-id="dadcf-105">When creating a Markdown file, you should copy the included template to a new file, fill out the metadata as specified below, and set the H1 heading above to the title of the article.</span></span>

## <a name="metadata"></a><span data-ttu-id="dadcf-106">Metatieto</span><span class="sxs-lookup"><span data-stu-id="dadcf-106">Metadata</span></span>

<span data-ttu-id="dadcf-107">Pakolliset metatiedot on annettu alla olevassa metatietolohkon esimerkissä:</span><span class="sxs-lookup"><span data-stu-id="dadcf-107">The required metadata block is in the following sample metadata block:</span></span>

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- <span data-ttu-id="dadcf-108">Kaksoispisteen (:) ja metatietoelementin välissä **täytyy** olla välilyönti.</span><span class="sxs-lookup"><span data-stu-id="dadcf-108">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="dadcf-109">Arvon (esimerkiksi otsikon) sisäiset kaksoispisteet rikkovat metatietojen jäsennyksen.</span><span class="sxs-lookup"><span data-stu-id="dadcf-109">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="dadcf-110">Jos haluat käyttää kaksoispistettä otsikossa, käytä otsikon ympärillä kaksoispisteitä (esimerkiksi `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="dadcf-110">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="dadcf-111">**title**: Näkyy hakukoneiden tuloksissa.</span><span class="sxs-lookup"><span data-stu-id="dadcf-111">**title**: Appears in search engine results.</span></span> <span data-ttu-id="dadcf-112">Tässä oleva otsikko ei saa olla täsmälleen sama kuin H1-otsikko, ja siinä voi olla korkeintaan 60 merkkiä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-112">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="dadcf-113">**description**: Yhteenveto artikkelin sisällöstä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-113">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="dadcf-114">Se näkyy yleensä haun tulossivulla, mutta se ei vaikuta hakutulosten keskinäiseen järjestykseen.</span><span class="sxs-lookup"><span data-stu-id="dadcf-114">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="dadcf-115">Kuvauksen pituus voi olla 115–145 merkkiä välilyönnit mukaan lukien.</span><span class="sxs-lookup"><span data-stu-id="dadcf-115">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="dadcf-116">**author**: Author-kentässä tulee olla artikkelin kirjoittajan **GitHub-käyttäjänimi**.</span><span class="sxs-lookup"><span data-stu-id="dadcf-116">**author**: The author field should contain the **GitHub username** of the author.</span></span>
- <span data-ttu-id="dadcf-117">**ms.date**: Viimeisimmän merkittävän päivityksen päivämäärä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-117">**ms.date**: The date of the last significant update.</span></span> <span data-ttu-id="dadcf-118">Päivitä tämä vanhoihin artikkeleihin, jos olet tarkistanut ja päivittänyt koko artikkelin.</span><span class="sxs-lookup"><span data-stu-id="dadcf-118">Update this on existing articles if you reviewed and updated the entire article.</span></span> <span data-ttu-id="dadcf-119">Pieniä muutoksia, kuten kirjoitusvirheiden korjauksia, ei lasketa merkittäviksi päivityksiksi.</span><span class="sxs-lookup"><span data-stu-id="dadcf-119">Small fixes, such as typos or similar do not warrant an update.</span></span>

<span data-ttu-id="dadcf-120">Jokaiseen artikkeliin kuuluu muutakin metatietoa, mutta suurin osa metatietoarvoista lisätään kansiotasolla määrittämällä ne **docfx.json**-tiedostossa.</span><span class="sxs-lookup"><span data-stu-id="dadcf-120">Other metadata is attached to each article, but we typically apply most metadata values at the folder level, specified in **docfx.json**.</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="dadcf-121">Markdownin perusteet, GFM ja erikoismerkit</span><span class="sxs-lookup"><span data-stu-id="dadcf-121">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="dadcf-122">Voit opetella Markdownin, GFM:n (GitHub Flavored Markdown) ja OPS-kohtaisten laajennusten perustiedot yleisistä [Markdown](how-to-write-use-markdown.md)- ja [Markdownin viitetiedot](markdown-reference.md) -aiheisista artikkeleista.</span><span class="sxs-lookup"><span data-stu-id="dadcf-122">You can learn the basics of Markdown, GitHub Flavored Markdown (GFM), and OPS specific extensions in the general articles on [Markdown](how-to-write-use-markdown.md) and [Markdown reference](markdown-reference.md).</span></span>

<span data-ttu-id="dadcf-123">Markdownissa käytetään muotoilussa erikoismerkkejä, kuten \*, \` ja \#.</span><span class="sxs-lookup"><span data-stu-id="dadcf-123">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="dadcf-124">Jos haluat käyttää jotakin näistä merkeistä sisällössäsi, sinun on tehtävä jompi kumpi seuraavista:</span><span class="sxs-lookup"><span data-stu-id="dadcf-124">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="dadcf-125">Lisätä kenoviiva erikoismerkin eteen (esimerkiksi `\*`, jos haluat merkin \*)</span><span class="sxs-lookup"><span data-stu-id="dadcf-125">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="dadcf-126">Käyttää merkin [HTML-merkkikoodia](http://www.ascii.cl/htmlcodes.htm) (esimerkiksi `&#42;`, jos haluat merkin &#42;).</span><span class="sxs-lookup"><span data-stu-id="dadcf-126">Use the [HTML entity code](http://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-names"></a><span data-ttu-id="dadcf-127">Tiedostonimet</span><span class="sxs-lookup"><span data-stu-id="dadcf-127">File names</span></span>

<span data-ttu-id="dadcf-128">Tiedostonimissä noudatetaan seuraavia sääntöjä:</span><span class="sxs-lookup"><span data-stu-id="dadcf-128">File names use the following rules:</span></span>

* <span data-ttu-id="dadcf-129">Nimessä saa olla ainoastaan pieniä kirjaimia, numeroita ja tavuviivoja.</span><span class="sxs-lookup"><span data-stu-id="dadcf-129">Contain only lowercase letters, numbers, and hyphens.</span></span>
* <span data-ttu-id="dadcf-130">Ei välilyöntejä tai välimerkkejä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-130">No spaces or punctuation characters.</span></span> <span data-ttu-id="dadcf-131">Erota tiedostonimessä esiintyvät sanat ja numerot toisistaan tavuviivoilla.</span><span class="sxs-lookup"><span data-stu-id="dadcf-131">Use the hyphens to separate words and numbers in the file name.</span></span>
* <span data-ttu-id="dadcf-132">Käytä selkeitä toiminnallisia verbejä, kuten develop (kehitä), buy (osta), build (luo), troubleshoot (vianmääritys).</span><span class="sxs-lookup"><span data-stu-id="dadcf-132">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="dadcf-133">Ei -ing-sanoja.</span><span class="sxs-lookup"><span data-stu-id="dadcf-133">No -ing words.</span></span>
* <span data-ttu-id="dadcf-134">Ei pieniä sanoja, kuten ja, tai sekä englannin artikkelit.</span><span class="sxs-lookup"><span data-stu-id="dadcf-134">No small words - don't include a, and, the, in, or, etc.</span></span>
* <span data-ttu-id="dadcf-135">Nimissä on käytettävä Markdown-merkintätapaa ja .md-tiedostotunnistetta.</span><span class="sxs-lookup"><span data-stu-id="dadcf-135">Must be in Markdown and use the .md file extension.</span></span>
* <span data-ttu-id="dadcf-136">Pidä tiedostonimet suhteellisen lyhyinä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-136">Keep file names reasonably short.</span></span> <span data-ttu-id="dadcf-137">Ne ovat osa artikkeleidesi URL-osoitteita.</span><span class="sxs-lookup"><span data-stu-id="dadcf-137">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="dadcf-138">Otsikot</span><span class="sxs-lookup"><span data-stu-id="dadcf-138">Headings</span></span>

<span data-ttu-id="dadcf-139">Kirjoita isolla alkukirjaimella vain otsikon ensimmäinen sana ja erisnimet.</span><span class="sxs-lookup"><span data-stu-id="dadcf-139">Use sentence-style capitalization.</span></span> <span data-ttu-id="dadcf-140">Otsikon ensimmäinen sana kirjoitetaan aina isolla alkukirjaimella.</span><span class="sxs-lookup"><span data-stu-id="dadcf-140">Always capitalize the first word of a heading.</span></span>

## <a name="text-styling"></a><span data-ttu-id="dadcf-141">Tekstin muotoilu</span><span class="sxs-lookup"><span data-stu-id="dadcf-141">Text styling</span></span>

<span data-ttu-id="dadcf-142">*Kursivointi* Käytä tiedostojen, kansioiden, polkujen (erota pitkät kohteet omalle rivilleen) ja uusien termien kohdalla.</span><span class="sxs-lookup"><span data-stu-id="dadcf-142">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="dadcf-143">**Lihavointi** Käytä viitatessa käyttöliittymäelementteihin.</span><span class="sxs-lookup"><span data-stu-id="dadcf-143">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="dadcf-144">`Code` Käytä tekstin sisäiseen koodiin, kielen avainsanoihin, NuGet-pakettien nimiin, komentorivin komentoihin, tietokantataulukoihin ja sarakkeiden nimiin sekä URL-osoitteisiin, jos haluat, ettei niitä voi napsauttaa.</span><span class="sxs-lookup"><span data-stu-id="dadcf-144">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="dadcf-145">Linkit</span><span class="sxs-lookup"><span data-stu-id="dadcf-145">Links</span></span>

<span data-ttu-id="dadcf-146">[Linkit](how-to-write-links.md)-yleisartikkelista saat lisätietoja ankkureista, sisäisistä linkeistä, muihin asiakirjoihin osoittavista linkeistä, koodisisällöistä ja ulkoisista linkeistä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-146">See the general article on [Links](how-to-write-links.md) for information about anchors, internal links, links to other documents, code includes, and external links.</span></span>

<span data-ttu-id="dadcf-147">.NET-ohjetiimi noudattaa seuraavia tapoja:</span><span class="sxs-lookup"><span data-stu-id="dadcf-147">The .NET docs team uses the following conventions:</span></span>

- <span data-ttu-id="dadcf-148">Käytämme yleensä suhteellisia linkkejä ja kehotamme välttämään `~/`:n käyttöä linkeissä, koska suhteelliset linkit selvitetään GitHubissa lähteessä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-148">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="dadcf-149">`~/`-merkkiä käytetään kuitenkin polun ilmaisemiseen linkitettäessä riippuvaisessa säilössä olevaan tiedostoon.</span><span class="sxs-lookup"><span data-stu-id="dadcf-149">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="dadcf-150">Riippuvaisen säilön tiedostot ovat GitHubissa eri sijainnissa, ja siksi suhteellisia linkkejä ei kirjoitustavasta riippumatta voida selvittää oikein.</span><span class="sxs-lookup"><span data-stu-id="dadcf-150">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>
- <span data-ttu-id="dadcf-151">C#-kielimääritys ja Visual Basic -kielimääritys sisällytetään .NET-ohjeistuksiin lisäämällä lähde kielisäilöistä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-151">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="dadcf-152">Markdown-lähteitä hallinnoidaan [csharplang](https://github.com/dotnet/csharplang)- ja [vblang](https://github.com/dotnet/vblang)-säilöissä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-152">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [vblang](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="dadcf-153">Määrityksen linkkien on osoitettava niihin lähdehakemistoihin, joihin kyseiset määritykset kuuluvat.</span><span class="sxs-lookup"><span data-stu-id="dadcf-153">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="dadcf-154">C#:n osalta kyseessä on **~/_csharplang/spec** ja VB:n **~/_vblang/spec**.</span><span class="sxs-lookup"><span data-stu-id="dadcf-154">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="dadcf-155">Esimerkki: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)`</span><span class="sxs-lookup"><span data-stu-id="dadcf-155">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)`</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="dadcf-156">Ohjelmointirajapintoihin viittaavat linkit</span><span class="sxs-lookup"><span data-stu-id="dadcf-156">Links to APIs</span></span>

<span data-ttu-id="dadcf-157">Osa koontijärjestelmän laajennuksista mahdollistaa linkittämisen .NET-ohjelmointirajapintoihin ilman ulkoisia linkkejä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-157">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span> <span data-ttu-id="dadcf-158">Voit käyttää jompaa kumpaa seuraavista syntakseista:</span><span class="sxs-lookup"><span data-stu-id="dadcf-158">You use one of the following syntax:</span></span>

1. <span data-ttu-id="dadcf-159">Automaattinen linkki: `<xref:UID>` tai `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="dadcf-159">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="dadcf-160">Kyselyparametri `displayProperty` tuottaa täysin toimivan linkkitekstin.</span><span class="sxs-lookup"><span data-stu-id="dadcf-160">The `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="dadcf-161">Oletusarvoisesti linkkitekstissä näkyy vain jäsenen tai tyypin nimi.</span><span class="sxs-lookup"><span data-stu-id="dadcf-161">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="dadcf-162">Markdown-linkki: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="dadcf-162">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="dadcf-163">Käytä tätä vaihtoehtoa, kun haluat mukauttaa näkyviin tulevaa linkkitekstiä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-163">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="dadcf-164">Esimerkkejä:</span><span class="sxs-lookup"><span data-stu-id="dadcf-164">Examples:</span></span>

- <span data-ttu-id="dadcf-165">`<xref:System.String>` hahmontuu muotoon [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="dadcf-165">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="dadcf-166">`<xref:System.String?displayProperty=nameWithType>` hahmontuu muotoon [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="dadcf-166">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="dadcf-167">`[String class](xref:System.String)` hahmontuu muotoon [String class](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="dadcf-167">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="dadcf-168">Lisätietoja tämän merkintätavan käytöstä on artikkelissa [Ristiviitteiden käyttö](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="dadcf-168">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="dadcf-169">Jos UID sisältää erikoismerkkejä \`, \# tai \*, UID-arvo on HTML-koodattava vastaavasti seuraavasti: `%60`, `%23` tai `%2A`.</span><span class="sxs-lookup"><span data-stu-id="dadcf-169">Some UIDs contain the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="dadcf-170">Joskus myös sulkeet koodataan, mutta tämä ei ole välttämätöntä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-170">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="dadcf-171">Esimerkkejä:</span><span class="sxs-lookup"><span data-stu-id="dadcf-171">Examples:</span></span>

- <span data-ttu-id="dadcf-172">System.Threading.Tasks.Task\`1 muuttuu muotoon `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="dadcf-172">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="dadcf-173">System.Exception.\#ctor muuttuu muotoon `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="dadcf-173">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="dadcf-174">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) muuttuu muotoon `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="dadcf-174">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<span data-ttu-id="dadcf-175">Voit hakea tyyppien, jäsenen ylikuormitusluettelon tai tietyn ylikuormitetun jäsenen UID:t osoitteesta `https://xref.docs.microsoft.com/autocomplete`.</span><span class="sxs-lookup"><span data-stu-id="dadcf-175">You can find the UIDs of types, a member overload list, or a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="dadcf-176">Kyselymerkkijono "?text=*\<tyypin-tai-jäsenen-nimi>*" määrittää tyypin tai jäsenen, jonka UID:t haluat hakea.</span><span class="sxs-lookup"><span data-stu-id="dadcf-176">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="dadcf-177">Esimerkiksi `https://xref.docs.microsoft.com/autocomplete?text=string.format` hakee [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format)-ylikuormitukset.</span><span class="sxs-lookup"><span data-stu-id="dadcf-177">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span> <span data-ttu-id="dadcf-178">Työkalu hakee annettua `text`-kyselyparametria mistä tahansa UID:n osasta.</span><span class="sxs-lookup"><span data-stu-id="dadcf-178">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="dadcf-179">Voit esimerkiksi hakea jäsenen nimellä (ToString), puutteellisella jäsenen nimellä (ToStri), tyypin ja jäsenen nimellä (Double.ToString) jne.</span><span class="sxs-lookup"><span data-stu-id="dadcf-179">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="dadcf-180">Jos lisäät \*-merkin (tai %2A) UID:n perään, linkki edustaa ylikuormitussivua tietyn ohjelmointirajapinnan sijaan.</span><span class="sxs-lookup"><span data-stu-id="dadcf-180">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="dadcf-181">Voit käyttää merkkiä esimerkiksi silloin, jos haluat linkittää [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch)-sivulle yleisellä tasolla tietyn ylikuormituksen (esim. [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_)) sijasta.</span><span class="sxs-lookup"><span data-stu-id="dadcf-181">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="dadcf-182">Voit käyttää \*-merkkiä myös linkittäessäsi jäsenen sivulle silloin, kun jäsentä ei ole ylikuormitettu. Tällöin sinun ei tarvitse lisätä parametriluetteloa UID:hen.</span><span class="sxs-lookup"><span data-stu-id="dadcf-182">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="dadcf-183">Jos haluat linkittää tietyn menetelmän ylikuormitukseen, sinun on annettava menetelmän jokaisen parametrin kelvollinen tyypin nimi.</span><span class="sxs-lookup"><span data-stu-id="dadcf-183">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="dadcf-184">Esimerkiksi \<xref:System.DateTime.ToString> linkittyy menetelmään [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString), jolla ei ole parametrejä, kun taas \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> linkittyy [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_)-menetelmään.</span><span class="sxs-lookup"><span data-stu-id="dadcf-184">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span>

<span data-ttu-id="dadcf-185">Jos haluat linkittää yleiseen tyyppiin, kuten [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), käytä \`-merkkiä (%60) ja kirjoita sen perään yleisen tyypin parametrien lukumäärä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-185">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="dadcf-186">Esimerkiksi \<xref:System.Nullable%601> linkittää tyyppiin [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), kun taas \<xref:System.Func%602> linkittää valtuutettuun viittaukseen [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="dadcf-186">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

## <a name="code"></a><span data-ttu-id="dadcf-187">Koodi</span><span class="sxs-lookup"><span data-stu-id="dadcf-187">Code</span></span>

<span data-ttu-id="dadcf-188">Koodia on suositeltavaa lisätä toimivasta esimerkkisovelluksesta poimittuina koodikatkelmina.</span><span class="sxs-lookup"><span data-stu-id="dadcf-188">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="dadcf-189">Voit luoda esimerkkisovelluksen [.NETin kehittämiseen osallistumista](dotnet-contribute-process.md#contributing-to-samples) koskevan artikkelin ohjeiden mukaan.</span><span class="sxs-lookup"><span data-stu-id="dadcf-189">Create your sample following the instructions in the [contributing to .NET](dotnet-contribute-process.md#contributing-to-samples) article.</span></span> <span data-ttu-id="dadcf-190">Koodin lisäämisen perussäännöt on kerrottu [koodia](how-to-write-use-markdown.md#code-includes) käsittelevissä yleisohjeissa.</span><span class="sxs-lookup"><span data-stu-id="dadcf-190">The basic rules for including code are located in the general guidance on [code](how-to-write-use-markdown.md#code-includes).</span></span>

<span data-ttu-id="dadcf-191">Käytä koodin lisäämiseen seuraavaa syntaksia:</span><span class="sxs-lookup"><span data-stu-id="dadcf-191">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* <span data-ttu-id="dadcf-192">`-<language>` (*valinnainen* mutta *suositeltava*)</span><span class="sxs-lookup"><span data-stu-id="dadcf-192">`-<language>` (*optional* but *recommended*)</span></span>
  * <span data-ttu-id="dadcf-193">Viitattavan koodikatkelman ohjelmointikieli.</span><span class="sxs-lookup"><span data-stu-id="dadcf-193">Language of the code snippet being referenced.</span></span> <span data-ttu-id="dadcf-194">Tuettujen arvojen luettelo on kohdassa [Tuetut kielet](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="dadcf-194">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

* <span data-ttu-id="dadcf-195">`<name>` (*valinnainen*)</span><span class="sxs-lookup"><span data-stu-id="dadcf-195">`<name>` (*optional*)</span></span>
  * <span data-ttu-id="dadcf-196">Koodikatkelman nimi.</span><span class="sxs-lookup"><span data-stu-id="dadcf-196">Name for the code snippet.</span></span> <span data-ttu-id="dadcf-197">Tällä ei ole vaikutusta lopulliseen HTML-tulokseen, mutta voit käyttää tätä parantaaksesi Markdown-lähteesi luettavuutta.</span><span class="sxs-lookup"><span data-stu-id="dadcf-197">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

* <span data-ttu-id="dadcf-198">`<pathToFile>` (*pakollinen*)</span><span class="sxs-lookup"><span data-stu-id="dadcf-198">`<pathToFile>` (*mandatory*)</span></span>
  * <span data-ttu-id="dadcf-199">Tiedostojärjestelmässä oleva suhteellinen polku, joka osoittaa koodikatkelmatiedoston, johon viitataan.</span><span class="sxs-lookup"><span data-stu-id="dadcf-199">Relative path in the file system that indicates the code snippet file to reference.</span></span> <span data-ttu-id="dadcf-200">Eri säilöt, joista .NET-ohjejoukko koostuu, voivat mutkistaa tätä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-200">This can be complicated by the different repos that make up the .NET doc set.</span></span> <span data-ttu-id="dadcf-201">.NET-esimerkkisovellukset sijaitsevat dotnet/samples-säilössä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-201">The .NET samples are in the dotnet/samples repo.</span></span> <span data-ttu-id="dadcf-202">Kaikki katkelmapolut alkavat samalla tavalla: `~/samples`. Polun loppuosa on lähteeseen viittaava polku kyseisen säilön juuresta.</span><span class="sxs-lookup"><span data-stu-id="dadcf-202">All snippet paths would start with `~/samples`, the rest of the path being the path to the source from the root of that repo.</span></span>

* <span data-ttu-id="dadcf-203">`<queryoption>` (*valinnainen*)</span><span class="sxs-lookup"><span data-stu-id="dadcf-203">`<queryoption>` (*optional*)</span></span>
  * <span data-ttu-id="dadcf-204">Käytetään määrittämään, miten koodi noudetaan tiedostosta:</span><span class="sxs-lookup"><span data-stu-id="dadcf-204">Used to specify how the code should be retrieved from the file:</span></span>
    * <span data-ttu-id="dadcf-205">`#`:  `#{tagname}` (tunnisteen nimi) *tai* `#L{startlinenumber}-L{endlinenumber}` (rivit).</span><span class="sxs-lookup"><span data-stu-id="dadcf-205">`#`:  `#{tagname}` (tag name) *or* `#L{startlinenumber}-L{endlinenumber}` (line range).</span></span>
    <span data-ttu-id="dadcf-206">Rivinumeroiden käyttöä ei suositella, koska ne voivat herkästi muuttua.</span><span class="sxs-lookup"><span data-stu-id="dadcf-206">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="dadcf-207">On suositeltavaa viitata koodikatkelmiin tunnisteiden nimillä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-207">Tag name is the preferred way of referencing code snippets.</span></span> <span data-ttu-id="dadcf-208">Anna tunnisteille merkitykselliset nimet.</span><span class="sxs-lookup"><span data-stu-id="dadcf-208">Use meaningful tag names.</span></span> <span data-ttu-id="dadcf-209">(Aiemmasta alustasta siirrettiin paljon koodikatkelmia, joiden tunnisteet olivat `Snippet1`, `Snippet2` jne. Tätä käytäntöä on paljon haastavampaa ylläpitää.)</span><span class="sxs-lookup"><span data-stu-id="dadcf-209">(Many snippets were migrated from a previous platform and the tags have names such as `Snippet1`, `Snippet2` etc. That practice is much harder to maintain.)</span></span>
    * <span data-ttu-id="dadcf-210">`range`: `?range=1,3-5` Rivialue.</span><span class="sxs-lookup"><span data-stu-id="dadcf-210">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="dadcf-211">Tämä esimerkki sisältää rivit 1, 3, 4 ja 5.</span><span class="sxs-lookup"><span data-stu-id="dadcf-211">This example includes lines 1, 3, 4, and 5.</span></span>

<span data-ttu-id="dadcf-212">Suosittelemme tunnisteen nimen käyttöä aina kun mahdollista.</span><span class="sxs-lookup"><span data-stu-id="dadcf-212">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="dadcf-213">Tunnisteen nimi on lähdekoodista löytyvä alueen tai koodin kommentin nimi muodossa `Snippettagname`.</span><span class="sxs-lookup"><span data-stu-id="dadcf-213">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="dadcf-214">Seuraavassa esimerkissä näytetään tunnisteen nimeen `BasicThrow` viittaaminen:</span><span class="sxs-lookup"><span data-stu-id="dadcf-214">The following example shows how to refer to the tag name `BasicThrow`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

<span data-ttu-id="dadcf-215">Säilössä **dotnet/samples** olevan lähteen suhteellinen polku seuraa `~/samples`-polkua.</span><span class="sxs-lookup"><span data-stu-id="dadcf-215">The relative path to the source in the **dotnet/samples** repo follows the `~/samples` path.</span></span>

<span data-ttu-id="dadcf-216">[Tästä lähdetiedostosta](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) näet koodikatkelman tunnisteiden rakenteen.</span><span class="sxs-lookup"><span data-stu-id="dadcf-216">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs).</span></span> <span data-ttu-id="dadcf-217">Lisätietoja tunnisteen nimen esittämisestä koodikatkelmien lähdetiedostoissa kielen mukaan on artikkelissa [DocFX-ohjeet](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="dadcf-217">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="dadcf-218">Seuraavassa esimerkissä koodia on lisätty kaikilla kolmella .NET-kielellä:</span><span class="sxs-lookup"><span data-stu-id="dadcf-218">The following example shows code included in all three .NET languages:</span></span>

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

<span data-ttu-id="dadcf-219">Kun koodikatkelmia lisätään kokonaisista ohjelmista, varmistetaan samalla, että kaikki koodi suoritetaan CI-järjestelmämme (Continuous Integration) läpi.</span><span class="sxs-lookup"><span data-stu-id="dadcf-219">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="dadcf-220">Jos kuitenkin haluat näyttää lukijalle jotakin, josta aiheutuu käännösaika- tai suorituspalveluvirheitä, voit käyttää tekstiin sidottuja koodilohkoja.</span><span class="sxs-lookup"><span data-stu-id="dadcf-220">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

## <a name="images"></a><span data-ttu-id="dadcf-221">Kuvat</span><span class="sxs-lookup"><span data-stu-id="dadcf-221">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="dadcf-222">Staattinen kuva tai animoitu GIF</span><span class="sxs-lookup"><span data-stu-id="dadcf-222">Static image or animated GIF</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a><span data-ttu-id="dadcf-223">Linkitetty kuva</span><span class="sxs-lookup"><span data-stu-id="dadcf-223">Linked image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a><span data-ttu-id="dadcf-224">Videot</span><span class="sxs-lookup"><span data-stu-id="dadcf-224">Videos</span></span>

<span data-ttu-id="dadcf-225">Voit tällä hetkellä upottaa sekä Channel 9- että YouTube-videoita seuraavalla syntaksilla:</span><span class="sxs-lookup"><span data-stu-id="dadcf-225">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="dadcf-226">Channel 9</span><span class="sxs-lookup"><span data-stu-id="dadcf-226">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="dadcf-227">Voit hakea videon oikean URL-osoitteen valitsemalla videon alta **Embed**-välilehden ja kopioimalla URL-osoitteen `<iframe>`-elementistä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-227">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="dadcf-228">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="dadcf-228">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="dadcf-229">YouTube</span><span class="sxs-lookup"><span data-stu-id="dadcf-229">YouTube</span></span>

<span data-ttu-id="dadcf-230">Voit hakea videon oikean URL-osoitteen napsauttamalla videota hiiren kakkospainikkeella, valitsemalla **Kopioi upotuskoodi** ja kopioimalla sitten URL-osoitteen `<iframe>`-elementistä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-230">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="dadcf-231">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="dadcf-231">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="dadcf-232">docs.microsoft-laajennukset</span><span class="sxs-lookup"><span data-stu-id="dadcf-232">docs.microsoft extensions</span></span>

<span data-ttu-id="dadcf-233">docs.microsoft tarjoaa muutamia lisälaajennuksia GitHub Flavored Markdowniin.</span><span class="sxs-lookup"><span data-stu-id="dadcf-233">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="checked-lists"></a><span data-ttu-id="dadcf-234">Tarkistusmerkeillä merkityt luettelot</span><span class="sxs-lookup"><span data-stu-id="dadcf-234">Checked lists</span></span>

<span data-ttu-id="dadcf-235">Luetteloille on käytettävissä mukautettu tyyli.</span><span class="sxs-lookup"><span data-stu-id="dadcf-235">A custom style is available for lists.</span></span> <span data-ttu-id="dadcf-236">Voit hahmontaa luettelot vihreillä tarkistusmerkeillä.</span><span class="sxs-lookup"><span data-stu-id="dadcf-236">You can render lists with green check marks.</span></span>

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

<span data-ttu-id="dadcf-237">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="dadcf-237">This renders as:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="dadcf-238">How to create a .NET Core app</span><span class="sxs-lookup"><span data-stu-id="dadcf-238">How to create a .NET Core app</span></span>
> * <span data-ttu-id="dadcf-239">How to add a reference to the Microsoft.XmlSerializer.Generator package</span><span class="sxs-lookup"><span data-stu-id="dadcf-239">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="dadcf-240">How to edit your MyApp.csproj to add dependencies</span><span class="sxs-lookup"><span data-stu-id="dadcf-240">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="dadcf-241">How to add a class and an XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="dadcf-241">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="dadcf-242">How to build and run the application</span><span class="sxs-lookup"><span data-stu-id="dadcf-242">How to build and run the application</span></span>

<span data-ttu-id="dadcf-243">Aidon esimerkin tarkistusmerkeillä merkityistä luetteloista saat [.NET Core -ohjeista](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="dadcf-243">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="dadcf-244">Painikkeet</span><span class="sxs-lookup"><span data-stu-id="dadcf-244">Buttons</span></span>

<span data-ttu-id="dadcf-245">Painikelinkit:</span><span class="sxs-lookup"><span data-stu-id="dadcf-245">Button links:</span></span>

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

<span data-ttu-id="dadcf-246">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="dadcf-246">This renders as:</span></span>

> [!div class="button"]
[<span data-ttu-id="dadcf-247">button links</span><span class="sxs-lookup"><span data-stu-id="dadcf-247">button links</span></span>](dotnet-contribute.md)

<span data-ttu-id="dadcf-248">Aidon esimerkin painikkeista saat [Visual Studio -ohjeista](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="dadcf-248">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="dadcf-249">Vaiheittaiset ohjeet</span><span class="sxs-lookup"><span data-stu-id="dadcf-249">Step-by-steps</span></span>

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

<span data-ttu-id="dadcf-250">Aidon esimerkin vaiheittaisista ohjeista näet [C#-ohjeista](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="dadcf-250">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
