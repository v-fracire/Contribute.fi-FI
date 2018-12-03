---
title: .NET-artikkeleiden malli ja pikaohje
description: Tässä artikkelissa tarjotaan kätevä malli, jonka avulla voit luoda uusia artikkeleita .NET-ohjesäilöihin
ms.date: 11/07/2018
ms.openlocfilehash: 15f64ec86c475e2da2f6539c8f388d076389c4e0
ms.sourcegitcommit: 68d81b61ffa60aba16acfed023760449e16de91b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/26/2018
ms.locfileid: "52299656"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a><span data-ttu-id="d2793-103">Metatieto- ja Markdown-malli .NET-ohjeita varten</span><span class="sxs-lookup"><span data-stu-id="d2793-103">Metadata and Markdown template for .NET docs</span></span>

<span data-ttu-id="d2793-104">Tämä dotnet/docs-malli sisältää esimerkkejä Markdown-syntaksista sekä ohjeita metatietojen määrittämiseen.</span><span class="sxs-lookup"><span data-stu-id="d2793-104">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span>

<span data-ttu-id="d2793-105">Kun luot Markdown-tiedostoa, kopioi liitteenä oleva malli uuteen tiedostoon, täytä metatiedot alla olevien ohjeiden mukaan ja määritä artikkelin otsikolle yllä oleva H1-otsikko.</span><span class="sxs-lookup"><span data-stu-id="d2793-105">When creating a Markdown file, you should copy the included template to a new file, fill out the metadata as specified below, and set the H1 heading above to the title of the article.</span></span>

## <a name="metadata"></a><span data-ttu-id="d2793-106">Metatieto</span><span class="sxs-lookup"><span data-stu-id="d2793-106">Metadata</span></span>

<span data-ttu-id="d2793-107">Pakolliset metatiedot on annettu alla olevassa metatietolohkon esimerkissä:</span><span class="sxs-lookup"><span data-stu-id="d2793-107">The required metadata block is in the following sample metadata block:</span></span>

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- <span data-ttu-id="d2793-108">Kaksoispisteen (:) ja metatietoelementin välissä **täytyy** olla välilyönti.</span><span class="sxs-lookup"><span data-stu-id="d2793-108">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="d2793-109">Arvon (esimerkiksi otsikon) sisäiset kaksoispisteet rikkovat metatietojen jäsennyksen.</span><span class="sxs-lookup"><span data-stu-id="d2793-109">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="d2793-110">Jos haluat käyttää kaksoispistettä otsikossa, käytä otsikon ympärillä kaksoispisteitä (esimerkiksi `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="d2793-110">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="d2793-111">**title**: Näkyy hakukoneiden tuloksissa.</span><span class="sxs-lookup"><span data-stu-id="d2793-111">**title**: Appears in search engine results.</span></span> <span data-ttu-id="d2793-112">Tässä oleva otsikko ei saa olla täsmälleen sama kuin H1-otsikko, ja siinä voi olla korkeintaan 60 merkkiä.</span><span class="sxs-lookup"><span data-stu-id="d2793-112">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="d2793-113">**description**: Yhteenveto artikkelin sisällöstä.</span><span class="sxs-lookup"><span data-stu-id="d2793-113">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="d2793-114">Se näkyy yleensä haun tulossivulla, mutta se ei vaikuta hakutulosten keskinäiseen järjestykseen.</span><span class="sxs-lookup"><span data-stu-id="d2793-114">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="d2793-115">Kuvauksen pituus voi olla 115–145 merkkiä välilyönnit mukaan lukien.</span><span class="sxs-lookup"><span data-stu-id="d2793-115">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="d2793-116">**author**: Author-kentässä tulee olla artikkelin kirjoittajan **GitHub-käyttäjänimi**.</span><span class="sxs-lookup"><span data-stu-id="d2793-116">**author**: The author field should contain the **GitHub username** of the author.</span></span>
- <span data-ttu-id="d2793-117">**ms.date**: Viimeisimmän merkittävän päivityksen päivämäärä.</span><span class="sxs-lookup"><span data-stu-id="d2793-117">**ms.date**: The date of the last significant update.</span></span> <span data-ttu-id="d2793-118">Päivitä tämä vanhoihin artikkeleihin, jos olet tarkistanut ja päivittänyt koko artikkelin.</span><span class="sxs-lookup"><span data-stu-id="d2793-118">Update this on existing articles if you reviewed and updated the entire article.</span></span> <span data-ttu-id="d2793-119">Pieniä muutoksia, kuten kirjoitusvirheiden korjauksia, ei lasketa merkittäviksi päivityksiksi.</span><span class="sxs-lookup"><span data-stu-id="d2793-119">Small fixes, such as typos or similar do not warrant an update.</span></span>

<span data-ttu-id="d2793-120">Jokaiseen artikkeliin kuuluu muutakin metatietoa, mutta suurin osa metatietoarvoista lisätään kansiotasolla määrittämällä ne **docfx.json**-tiedostossa.</span><span class="sxs-lookup"><span data-stu-id="d2793-120">Other metadata is attached to each article, but we typically apply most metadata values at the folder level, specified in **docfx.json**.</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="d2793-121">Markdownin perusteet, GFM ja erikoismerkit</span><span class="sxs-lookup"><span data-stu-id="d2793-121">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="d2793-122">Voit opetella Markdownin, GFM:n (GitHub Flavored Markdown) ja OPS-kohtaisten laajennusten perustiedot yleisistä [Markdown](how-to-write-use-markdown.md)- ja [Markdownin viitetiedot](markdown-reference.md) -aiheisista artikkeleista.</span><span class="sxs-lookup"><span data-stu-id="d2793-122">You can learn the basics of Markdown, GitHub Flavored Markdown (GFM), and OPS specific extensions in the general articles on [Markdown](how-to-write-use-markdown.md) and [Markdown reference](markdown-reference.md).</span></span>

<span data-ttu-id="d2793-123">Markdownissa käytetään muotoilussa erikoismerkkejä, kuten \*, \` ja \#.</span><span class="sxs-lookup"><span data-stu-id="d2793-123">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="d2793-124">Jos haluat käyttää jotakin näistä merkeistä sisällössäsi, sinun on tehtävä jompi kumpi seuraavista:</span><span class="sxs-lookup"><span data-stu-id="d2793-124">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="d2793-125">Lisätä kenoviiva erikoismerkin eteen (esimerkiksi `\*`, jos haluat merkin \*)</span><span class="sxs-lookup"><span data-stu-id="d2793-125">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="d2793-126">Käyttää merkin [HTML-merkkikoodia](http://www.ascii.cl/htmlcodes.htm) (esimerkiksi `&#42;`, jos haluat merkin &#42;).</span><span class="sxs-lookup"><span data-stu-id="d2793-126">Use the [HTML entity code](http://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-names"></a><span data-ttu-id="d2793-127">Tiedostonimet</span><span class="sxs-lookup"><span data-stu-id="d2793-127">File names</span></span>

<span data-ttu-id="d2793-128">Tiedostonimissä noudatetaan seuraavia sääntöjä:</span><span class="sxs-lookup"><span data-stu-id="d2793-128">File names use the following rules:</span></span>

* <span data-ttu-id="d2793-129">Nimessä saa olla ainoastaan pieniä kirjaimia, numeroita ja tavuviivoja.</span><span class="sxs-lookup"><span data-stu-id="d2793-129">Contain only lowercase letters, numbers, and hyphens.</span></span>
* <span data-ttu-id="d2793-130">Ei välilyöntejä tai välimerkkejä.</span><span class="sxs-lookup"><span data-stu-id="d2793-130">No spaces or punctuation characters.</span></span> <span data-ttu-id="d2793-131">Erota tiedostonimessä esiintyvät sanat ja numerot toisistaan tavuviivoilla.</span><span class="sxs-lookup"><span data-stu-id="d2793-131">Use the hyphens to separate words and numbers in the file name.</span></span>
* <span data-ttu-id="d2793-132">Käytä selkeitä toiminnallisia verbejä, kuten develop (kehitä), buy (osta), build (luo), troubleshoot (vianmääritys).</span><span class="sxs-lookup"><span data-stu-id="d2793-132">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="d2793-133">Ei -ing-sanoja.</span><span class="sxs-lookup"><span data-stu-id="d2793-133">No -ing words.</span></span>
* <span data-ttu-id="d2793-134">Ei pieniä sanoja, kuten ja, tai sekä englannin artikkelit.</span><span class="sxs-lookup"><span data-stu-id="d2793-134">No small words - don't include a, and, the, in, or, etc.</span></span>
* <span data-ttu-id="d2793-135">Nimissä on käytettävä Markdown-merkintätapaa ja .md-tiedostotunnistetta.</span><span class="sxs-lookup"><span data-stu-id="d2793-135">Must be in Markdown and use the .md file extension.</span></span>
* <span data-ttu-id="d2793-136">Pidä tiedostonimet suhteellisen lyhyinä.</span><span class="sxs-lookup"><span data-stu-id="d2793-136">Keep file names reasonably short.</span></span> <span data-ttu-id="d2793-137">Ne ovat osa artikkeleidesi URL-osoitteita.</span><span class="sxs-lookup"><span data-stu-id="d2793-137">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="d2793-138">Otsikot</span><span class="sxs-lookup"><span data-stu-id="d2793-138">Headings</span></span>

<span data-ttu-id="d2793-139">Kirjoita isolla alkukirjaimella vain otsikon ensimmäinen sana ja erisnimet.</span><span class="sxs-lookup"><span data-stu-id="d2793-139">Use sentence-style capitalization.</span></span> <span data-ttu-id="d2793-140">Otsikon ensimmäinen sana kirjoitetaan aina isolla alkukirjaimella.</span><span class="sxs-lookup"><span data-stu-id="d2793-140">Always capitalize the first word of a heading.</span></span>

## <a name="text-styling"></a><span data-ttu-id="d2793-141">Tekstin muotoilu</span><span class="sxs-lookup"><span data-stu-id="d2793-141">Text styling</span></span>

<span data-ttu-id="d2793-142">*Kursivointi* Käytä tiedostojen, kansioiden, polkujen (erota pitkät kohteet omalle rivilleen) ja uusien termien kohdalla.</span><span class="sxs-lookup"><span data-stu-id="d2793-142">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="d2793-143">**Lihavointi** Käytä viitatessa käyttöliittymäelementteihin.</span><span class="sxs-lookup"><span data-stu-id="d2793-143">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="d2793-144">`Code` Käytä tekstin sisäiseen koodiin, kielen avainsanoihin, NuGet-pakettien nimiin, komentorivin komentoihin, tietokantataulukoihin ja sarakkeiden nimiin sekä URL-osoitteisiin, jos haluat, ettei niitä voi napsauttaa.</span><span class="sxs-lookup"><span data-stu-id="d2793-144">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="d2793-145">Linkit</span><span class="sxs-lookup"><span data-stu-id="d2793-145">Links</span></span>

<span data-ttu-id="d2793-146">[Linkit](how-to-write-links.md)-yleisartikkelista saat lisätietoja ankkureista, sisäisistä linkeistä, muihin asiakirjoihin osoittavista linkeistä, koodisisällöistä ja ulkoisista linkeistä.</span><span class="sxs-lookup"><span data-stu-id="d2793-146">See the general article on [Links](how-to-write-links.md) for information about anchors, internal links, links to other documents, code includes, and external links.</span></span>

<span data-ttu-id="d2793-147">.NET-ohjetiimi noudattaa seuraavia tapoja:</span><span class="sxs-lookup"><span data-stu-id="d2793-147">The .NET docs team uses the following conventions:</span></span>

- <span data-ttu-id="d2793-148">Käytämme yleensä suhteellisia linkkejä ja kehotamme välttämään `~/`:n käyttöä linkeissä, koska suhteelliset linkit selvitetään GitHubissa lähteessä.</span><span class="sxs-lookup"><span data-stu-id="d2793-148">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="d2793-149">`~/`-merkkiä käytetään kuitenkin polun ilmaisemiseen linkitettäessä riippuvaisessa säilössä olevaan tiedostoon.</span><span class="sxs-lookup"><span data-stu-id="d2793-149">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="d2793-150">Riippuvaisen säilön tiedostot ovat GitHubissa eri sijainnissa, ja siksi suhteellisia linkkejä ei kirjoitustavasta riippumatta voida selvittää oikein.</span><span class="sxs-lookup"><span data-stu-id="d2793-150">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>
- <span data-ttu-id="d2793-151">C#-kielimääritys ja Visual Basic -kielimääritys sisällytetään .NET-ohjeistuksiin lisäämällä lähde kielisäilöistä.</span><span class="sxs-lookup"><span data-stu-id="d2793-151">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="d2793-152">Markdown-lähteitä hallinnoidaan [csharplang](https://github.com/dotnet/csharplang)- ja [vblang](https://github.com/dotnet/vblang)-säilöissä.</span><span class="sxs-lookup"><span data-stu-id="d2793-152">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [vblang](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="d2793-153">Määrityksen linkkien on osoitettava niihin lähdehakemistoihin, joihin kyseiset määritykset kuuluvat.</span><span class="sxs-lookup"><span data-stu-id="d2793-153">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="d2793-154">C#:n osalta kyseessä on **~/_csharplang/spec** ja VB:n **~/_vblang/spec**, kuten seuraavassa esimerkissä:</span><span class="sxs-lookup"><span data-stu-id="d2793-154">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**, as in the following example:</span></span>

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a><span data-ttu-id="d2793-155">Ohjelmointirajapintoihin viittaavat linkit</span><span class="sxs-lookup"><span data-stu-id="d2793-155">Links to APIs</span></span>

<span data-ttu-id="d2793-156">Osa koontijärjestelmän laajennuksista mahdollistaa linkittämisen .NET-ohjelmointirajapintoihin ilman ulkoisia linkkejä.</span><span class="sxs-lookup"><span data-stu-id="d2793-156">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span> <span data-ttu-id="d2793-157">Voit käyttää jompaa kumpaa seuraavista syntakseista:</span><span class="sxs-lookup"><span data-stu-id="d2793-157">You use one of the following syntax:</span></span>

1. <span data-ttu-id="d2793-158">Automaattinen linkki: `<xref:UID>` tai `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="d2793-158">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="d2793-159">Kyselyparametri `displayProperty` tuottaa täysin toimivan linkkitekstin.</span><span class="sxs-lookup"><span data-stu-id="d2793-159">The `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="d2793-160">Oletusarvoisesti linkkitekstissä näkyy vain jäsenen tai tyypin nimi.</span><span class="sxs-lookup"><span data-stu-id="d2793-160">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="d2793-161">Markdown-linkki: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="d2793-161">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="d2793-162">Käytä tätä vaihtoehtoa, kun haluat mukauttaa näkyviin tulevaa linkkitekstiä.</span><span class="sxs-lookup"><span data-stu-id="d2793-162">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="d2793-163">Esimerkkejä:</span><span class="sxs-lookup"><span data-stu-id="d2793-163">Examples:</span></span>

- <span data-ttu-id="d2793-164">`<xref:System.String>` hahmontuu muotoon [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="d2793-164">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="d2793-165">`<xref:System.String?displayProperty=nameWithType>` hahmontuu muotoon [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="d2793-165">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="d2793-166">`[String class](xref:System.String)` hahmontuu muotoon [String class](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="d2793-166">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="d2793-167">Lisätietoja tämän merkintätavan käytöstä on artikkelissa [Ristiviitteiden käyttö](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span><span class="sxs-lookup"><span data-stu-id="d2793-167">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="d2793-168">Jos UID sisältää erikoismerkkejä \`, \# tai \*, UID-arvo on HTML-koodattava vastaavasti seuraavasti: `%60`, `%23` tai `%2A`.</span><span class="sxs-lookup"><span data-stu-id="d2793-168">Some UIDs contain the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="d2793-169">Joskus myös sulkeet koodataan, mutta tämä ei ole välttämätöntä.</span><span class="sxs-lookup"><span data-stu-id="d2793-169">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="d2793-170">Esimerkkejä:</span><span class="sxs-lookup"><span data-stu-id="d2793-170">Examples:</span></span>

- <span data-ttu-id="d2793-171">System.Threading.Tasks.Task\`1 muuttuu muotoon `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="d2793-171">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="d2793-172">System.Exception.\#ctor muuttuu muotoon `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="d2793-172">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="d2793-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) muuttuu muotoon `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="d2793-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<span data-ttu-id="d2793-174">Voit hakea tyyppien, jäsenen ylikuormitusluettelon tai tietyn ylikuormitetun jäsenen UID:t osoitteesta `https://xref.docs.microsoft.com/autocomplete`.</span><span class="sxs-lookup"><span data-stu-id="d2793-174">You can find the UIDs of types, a member overload list, or a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="d2793-175">Kyselymerkkijono `?text=*\<type-member-name>*` määrittää tyypin tai jäsenen, jonka UID:t haluat hakea.</span><span class="sxs-lookup"><span data-stu-id="d2793-175">The query string `?text=*\<type-member-name>*` identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="d2793-176">Esimerkiksi `https://xref.docs.microsoft.com/autocomplete?text=string.format` hakee [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format)-ylikuormitukset.</span><span class="sxs-lookup"><span data-stu-id="d2793-176">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span> <span data-ttu-id="d2793-177">Työkalu hakee annettua `text`-kyselyparametria mistä tahansa UID:n osasta.</span><span class="sxs-lookup"><span data-stu-id="d2793-177">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="d2793-178">Voit esimerkiksi hakea jäsenen nimellä (ToString), puutteellisella jäsenen nimellä (ToStri), tyypin ja jäsenen nimellä (Double.ToString) jne.</span><span class="sxs-lookup"><span data-stu-id="d2793-178">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="d2793-179">Jos lisäät merkin \* (tai merkin `%2A`) UID:n perään, linkki edustaa ylikuormitussivua tietyn ohjelmointirajapinnan sijaan.</span><span class="sxs-lookup"><span data-stu-id="d2793-179">If you add a \* (or `%2A`) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="d2793-180">Voit käyttää merkkiä esimerkiksi silloin, jos haluat linkittää [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch)-sivulle yleisellä tasolla tietyn ylikuormituksen (esim. [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_)) sijasta.</span><span class="sxs-lookup"><span data-stu-id="d2793-180">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="d2793-181">Voit käyttää \*-merkkiä myös linkittäessäsi jäsenen sivulle silloin, kun jäsentä ei ole ylikuormitettu. Tällöin sinun ei tarvitse lisätä parametriluetteloa UID:hen.</span><span class="sxs-lookup"><span data-stu-id="d2793-181">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="d2793-182">Jos haluat linkittää tietyn menetelmän ylikuormitukseen, sinun on annettava menetelmän jokaisen parametrin kelvollinen tyypin nimi.</span><span class="sxs-lookup"><span data-stu-id="d2793-182">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="d2793-183">Esimerkiksi \<xref:System.DateTime.ToString> linkittyy menetelmään [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString), jolla ei ole parametrejä, kun taas \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> linkittyy [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_)-menetelmään.</span><span class="sxs-lookup"><span data-stu-id="d2793-183">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span>

<span data-ttu-id="d2793-184">Jos haluat linkittää yleiseen tyyppiin, kuten [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), käytä merkkiä \` (`%60`) ja kirjoita sen perään yleisen tyypin parametrien lukumäärä.</span><span class="sxs-lookup"><span data-stu-id="d2793-184">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (`%60`) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="d2793-185">Esimerkiksi `<xref:System.Nullable%601>` linkittää tyyppiin [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), kun taas `<xref:System.Func%602>` linkittää valtuutettuun viittaukseen [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="d2793-185">For example, `<xref:System.Nullable%601>` links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while `<xref:System.Func%602>` links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

## <a name="code"></a><span data-ttu-id="d2793-186">Koodi</span><span class="sxs-lookup"><span data-stu-id="d2793-186">Code</span></span>

<span data-ttu-id="d2793-187">Koodia on suositeltavaa lisätä toimivasta esimerkkisovelluksesta poimittuina koodikatkelmina.</span><span class="sxs-lookup"><span data-stu-id="d2793-187">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="d2793-188">Voit luoda esimerkkisovelluksen [.NETin kehittämiseen osallistumista](dotnet-contribute-process.md#contributing-to-samples) koskevan artikkelin ohjeiden mukaan.</span><span class="sxs-lookup"><span data-stu-id="d2793-188">Create your sample following the instructions in the [contributing to .NET](dotnet-contribute-process.md#contributing-to-samples) article.</span></span> <span data-ttu-id="d2793-189">Koodin lisäämisen perussäännöt on kerrottu [koodia](how-to-write-use-markdown.md#code-includes) käsittelevissä yleisohjeissa.</span><span class="sxs-lookup"><span data-stu-id="d2793-189">The basic rules for including code are located in the general guidance on [code](how-to-write-use-markdown.md#code-includes).</span></span>

<span data-ttu-id="d2793-190">Käytä koodin lisäämiseen seuraavaa syntaksia:</span><span class="sxs-lookup"><span data-stu-id="d2793-190">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* <span data-ttu-id="d2793-191">`-<language>` (*valinnainen* mutta *suositeltava*)</span><span class="sxs-lookup"><span data-stu-id="d2793-191">`-<language>` (*optional* but *recommended*)</span></span>
  * <span data-ttu-id="d2793-192">Viitattavan koodikatkelman ohjelmointikieli.</span><span class="sxs-lookup"><span data-stu-id="d2793-192">Language of the code snippet being referenced.</span></span> <span data-ttu-id="d2793-193">Tuettujen arvojen luettelo on kohdassa [Tuetut kielet](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="d2793-193">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

* <span data-ttu-id="d2793-194">`<name>` (*valinnainen*)</span><span class="sxs-lookup"><span data-stu-id="d2793-194">`<name>` (*optional*)</span></span>
  * <span data-ttu-id="d2793-195">Koodikatkelman nimi.</span><span class="sxs-lookup"><span data-stu-id="d2793-195">Name for the code snippet.</span></span> <span data-ttu-id="d2793-196">Tällä ei ole vaikutusta lopulliseen HTML-tulokseen, mutta voit käyttää tätä parantaaksesi Markdown-lähteesi luettavuutta.</span><span class="sxs-lookup"><span data-stu-id="d2793-196">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

* <span data-ttu-id="d2793-197">`<pathToFile>` (*pakollinen*)</span><span class="sxs-lookup"><span data-stu-id="d2793-197">`<pathToFile>` (*mandatory*)</span></span>
  * <span data-ttu-id="d2793-198">Tiedostojärjestelmässä oleva suhteellinen polku, joka osoittaa koodikatkelmatiedoston, johon viitataan.</span><span class="sxs-lookup"><span data-stu-id="d2793-198">Relative path in the file system that indicates the code snippet file to reference.</span></span> <span data-ttu-id="d2793-199">Eri säilöt, joista .NET-ohjejoukko koostuu, voivat mutkistaa tätä.</span><span class="sxs-lookup"><span data-stu-id="d2793-199">This can be complicated by the different repos that make up the .NET doc set.</span></span> <span data-ttu-id="d2793-200">.NET-esimerkkisovellukset sijaitsevat dotnet/samples-säilössä.</span><span class="sxs-lookup"><span data-stu-id="d2793-200">The .NET samples are in the dotnet/samples repo.</span></span> <span data-ttu-id="d2793-201">Kaikki katkelmapolut alkavat samalla tavalla: `~/samples`. Polun loppuosa on lähteeseen viittaava polku kyseisen säilön juuresta.</span><span class="sxs-lookup"><span data-stu-id="d2793-201">All snippet paths would start with `~/samples`, the rest of the path being the path to the source from the root of that repo.</span></span>

* <span data-ttu-id="d2793-202">`<queryoption>` (*valinnainen*)</span><span class="sxs-lookup"><span data-stu-id="d2793-202">`<queryoption>` (*optional*)</span></span>
  * <span data-ttu-id="d2793-203">Käytetään määrittämään, miten koodi noudetaan tiedostosta:</span><span class="sxs-lookup"><span data-stu-id="d2793-203">Used to specify how the code should be retrieved from the file:</span></span>
    * <span data-ttu-id="d2793-204">`#`:  `#{tagname}` (tunnisteen nimi) *tai* `#L{startlinenumber}-L{endlinenumber}` (rivit).</span><span class="sxs-lookup"><span data-stu-id="d2793-204">`#`:  `#{tagname}` (tag name) *or* `#L{startlinenumber}-L{endlinenumber}` (line range).</span></span>
    <span data-ttu-id="d2793-205">Rivinumeroiden käyttöä ei suositella, koska ne voivat herkästi muuttua.</span><span class="sxs-lookup"><span data-stu-id="d2793-205">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="d2793-206">On suositeltavaa viitata koodikatkelmiin tunnisteiden nimillä.</span><span class="sxs-lookup"><span data-stu-id="d2793-206">Tag name is the preferred way of referencing code snippets.</span></span> <span data-ttu-id="d2793-207">Anna tunnisteille merkitykselliset nimet.</span><span class="sxs-lookup"><span data-stu-id="d2793-207">Use meaningful tag names.</span></span> <span data-ttu-id="d2793-208">(Aiemmasta alustasta siirrettiin paljon koodikatkelmia, joiden tunnisteet olivat `Snippet1`, `Snippet2` jne. Tätä käytäntöä on paljon haastavampaa ylläpitää.)</span><span class="sxs-lookup"><span data-stu-id="d2793-208">(Many snippets were migrated from a previous platform and the tags have names such as `Snippet1`, `Snippet2` etc. That practice is much harder to maintain.)</span></span>
    * <span data-ttu-id="d2793-209">`range`: `?range=1,3-5` Rivialue.</span><span class="sxs-lookup"><span data-stu-id="d2793-209">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="d2793-210">Tämä esimerkki sisältää rivit 1, 3, 4 ja 5.</span><span class="sxs-lookup"><span data-stu-id="d2793-210">This example includes lines 1, 3, 4, and 5.</span></span>

<span data-ttu-id="d2793-211">Suosittelemme tunnisteen nimen käyttöä aina kun mahdollista.</span><span class="sxs-lookup"><span data-stu-id="d2793-211">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="d2793-212">Tunnisteen nimi on lähdekoodista löytyvä alueen tai koodin kommentin nimi muodossa `Snippettagname`.</span><span class="sxs-lookup"><span data-stu-id="d2793-212">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="d2793-213">Seuraavassa esimerkissä näytetään tunnisteen nimeen `BasicThrow` viittaaminen:</span><span class="sxs-lookup"><span data-stu-id="d2793-213">The following example shows how to refer to the tag name `BasicThrow`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

<span data-ttu-id="d2793-214">Säilössä **dotnet/samples** olevan lähteen suhteellinen polku seuraa `~/samples`-polkua.</span><span class="sxs-lookup"><span data-stu-id="d2793-214">The relative path to the source in the **dotnet/samples** repo follows the `~/samples` path.</span></span>

<span data-ttu-id="d2793-215">[Tästä lähdetiedostosta](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) näet koodikatkelman tunnisteiden rakenteen.</span><span class="sxs-lookup"><span data-stu-id="d2793-215">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs).</span></span> <span data-ttu-id="d2793-216">Lisätietoja tunnisteen nimen esittämisestä koodikatkelmien lähdetiedostoissa kielen mukaan on artikkelissa [DocFX-ohjeet](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="d2793-216">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="d2793-217">Seuraavassa esimerkissä koodia on lisätty kaikilla kolmella .NET-kielellä:</span><span class="sxs-lookup"><span data-stu-id="d2793-217">The following example shows code included in all three .NET languages:</span></span>

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

<span data-ttu-id="d2793-218">Kun koodikatkelmia lisätään kokonaisista ohjelmista, varmistetaan samalla, että kaikki koodi suoritetaan CI-järjestelmämme (Continuous Integration) läpi.</span><span class="sxs-lookup"><span data-stu-id="d2793-218">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="d2793-219">Jos kuitenkin haluat näyttää lukijalle jotakin, josta aiheutuu käännösaika- tai suorituspalveluvirheitä, voit käyttää tekstiin sidottuja koodilohkoja.</span><span class="sxs-lookup"><span data-stu-id="d2793-219">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

## <a name="images"></a><span data-ttu-id="d2793-220">Kuvat</span><span class="sxs-lookup"><span data-stu-id="d2793-220">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="d2793-221">Staattinen kuva tai animoitu GIF</span><span class="sxs-lookup"><span data-stu-id="d2793-221">Static image or animated GIF</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a><span data-ttu-id="d2793-222">Linkitetty kuva</span><span class="sxs-lookup"><span data-stu-id="d2793-222">Linked image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a><span data-ttu-id="d2793-223">Videot</span><span class="sxs-lookup"><span data-stu-id="d2793-223">Videos</span></span>

<span data-ttu-id="d2793-224">Voit tällä hetkellä upottaa sekä Channel 9- että YouTube-videoita seuraavalla syntaksilla:</span><span class="sxs-lookup"><span data-stu-id="d2793-224">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="d2793-225">Channel 9</span><span class="sxs-lookup"><span data-stu-id="d2793-225">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="d2793-226">Voit hakea videon oikean URL-osoitteen valitsemalla videon alta **Embed**-välilehden ja kopioimalla URL-osoitteen `<iframe>`-elementistä.</span><span class="sxs-lookup"><span data-stu-id="d2793-226">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="d2793-227">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="d2793-227">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="d2793-228">YouTube</span><span class="sxs-lookup"><span data-stu-id="d2793-228">YouTube</span></span>

<span data-ttu-id="d2793-229">Voit hakea videon oikean URL-osoitteen napsauttamalla videota hiiren kakkospainikkeella, valitsemalla **Kopioi upotuskoodi** ja kopioimalla sitten URL-osoitteen `<iframe>`-elementistä.</span><span class="sxs-lookup"><span data-stu-id="d2793-229">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="d2793-230">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="d2793-230">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="d2793-231">docs.microsoft-laajennukset</span><span class="sxs-lookup"><span data-stu-id="d2793-231">docs.microsoft extensions</span></span>

<span data-ttu-id="d2793-232">docs.microsoft tarjoaa muutamia lisälaajennuksia GitHub Flavored Markdowniin.</span><span class="sxs-lookup"><span data-stu-id="d2793-232">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="checked-lists"></a><span data-ttu-id="d2793-233">Tarkistusmerkeillä merkityt luettelot</span><span class="sxs-lookup"><span data-stu-id="d2793-233">Checked lists</span></span>

<span data-ttu-id="d2793-234">Luetteloille on käytettävissä mukautettu tyyli.</span><span class="sxs-lookup"><span data-stu-id="d2793-234">A custom style is available for lists.</span></span> <span data-ttu-id="d2793-235">Voit hahmontaa luettelot vihreillä tarkistusmerkeillä.</span><span class="sxs-lookup"><span data-stu-id="d2793-235">You can render lists with green check marks.</span></span>

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

<span data-ttu-id="d2793-236">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="d2793-236">This renders as:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="d2793-237">How to create a .NET Core app</span><span class="sxs-lookup"><span data-stu-id="d2793-237">How to create a .NET Core app</span></span>
> * <span data-ttu-id="d2793-238">How to add a reference to the Microsoft.XmlSerializer.Generator package</span><span class="sxs-lookup"><span data-stu-id="d2793-238">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="d2793-239">How to edit your MyApp.csproj to add dependencies</span><span class="sxs-lookup"><span data-stu-id="d2793-239">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="d2793-240">How to add a class and an XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="d2793-240">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="d2793-241">How to build and run the application</span><span class="sxs-lookup"><span data-stu-id="d2793-241">How to build and run the application</span></span>

<span data-ttu-id="d2793-242">Aidon esimerkin tarkistusmerkeillä merkityistä luetteloista saat [.NET Core -ohjeista](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="d2793-242">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="d2793-243">Painikkeet</span><span class="sxs-lookup"><span data-stu-id="d2793-243">Buttons</span></span>

<span data-ttu-id="d2793-244">Painikelinkit:</span><span class="sxs-lookup"><span data-stu-id="d2793-244">Button links:</span></span>

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

<span data-ttu-id="d2793-245">Tämä hahmontuu seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="d2793-245">This renders as:</span></span>

> [!div class="button"]
[<span data-ttu-id="d2793-246">button links</span><span class="sxs-lookup"><span data-stu-id="d2793-246">button links</span></span>](dotnet-contribute.md)

<span data-ttu-id="d2793-247">Aidon esimerkin painikkeista saat [Visual Studio -ohjeista](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d2793-247">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="d2793-248">Vaiheittaiset ohjeet</span><span class="sxs-lookup"><span data-stu-id="d2793-248">Step-by-steps</span></span>

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

<span data-ttu-id="d2793-249">Aidon esimerkin vaiheittaisista ohjeista näet [C#-ohjeista](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="d2793-249">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
