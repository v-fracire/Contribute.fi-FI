---
title: Miten käyttää Markdownina Docsien kirjoittamiseen
description: Tässä artikkelissa on perustiedot ja viiteohjeet docs.microsoft.com -artikkelien kirjoittamiseen käytettävään Markdown-kieleen.
ms.date: 07/13/2017
ms.openlocfilehash: 6bb8a1fa20957512addb07dda0e68abec4b0a83f
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805721"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="4aa68-103">Miten käyttää Markdownia Docsien kirjoittamiseen</span><span class="sxs-lookup"><span data-stu-id="4aa68-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="4aa68-104">[Docs.microsoft.com](http://docs.microsoft.com)-artikkelit kirjoitetaan kevyellä [Markdown](https://daringfireball.net/projects/markdown/)-nimisellä merkintäkielellä, joka on sekä helppolukuinen että helppo oppia.</span><span class="sxs-lookup"><span data-stu-id="4aa68-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="4aa68-105">Tämän vuoksi siitä on nopeasti tullut alan standardi.</span><span class="sxs-lookup"><span data-stu-id="4aa68-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="4aa68-106">Koska Docs-sisältö säilytetään GitHubissa, se voi käyttää [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) -nimistä Markdownin yläjoukkoa, joka sisältää lisätoimintoja yleisiä muotoilutarpeita varten.</span><span class="sxs-lookup"><span data-stu-id="4aa68-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="4aa68-107">Lisäksi Open Publishing Services (OPS) käyttää Markdig Markdown Parseria.</span><span class="sxs-lookup"><span data-stu-id="4aa68-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="4aa68-108">Markdig on laajasti yhteensopiva GFM:n kanssa, ja se lisää Docsiin liittyvää toiminnallisuutta.</span><span class="sxs-lookup"><span data-stu-id="4aa68-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="4aa68-109">Markdig on nopea, tehokas, CommonMark-yhteensopiva, laajennettava Markdown-suoritin .NETiä varten.</span><span class="sxs-lookup"><span data-stu-id="4aa68-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="4aa68-110">Entistä parempi yhteisön tuki</span><span class="sxs-lookup"><span data-stu-id="4aa68-110">Better community support</span></span>
* <span data-ttu-id="4aa68-111">Entistä parempi standardien tuki</span><span class="sxs-lookup"><span data-stu-id="4aa68-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="4aa68-112">Markdownin perusteet</span><span class="sxs-lookup"><span data-stu-id="4aa68-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="4aa68-113">Otsikot</span><span class="sxs-lookup"><span data-stu-id="4aa68-113">Headings</span></span>

<span data-ttu-id="4aa68-114">Voit luoda otsikon käyttämällä #-merkkiä seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="4aa68-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="4aa68-115">Tekstin lihavointi ja kursivointi</span><span class="sxs-lookup"><span data-stu-id="4aa68-115">Bold and italic text</span></span>

<span data-ttu-id="4aa68-116">Voit **lihavoida** tekstiä ympäröimällä sen kahdella tähtimerkillä:</span><span class="sxs-lookup"><span data-stu-id="4aa68-116">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="4aa68-117">Voit *kursivoida* tekstiä ympäröimällä sen yhdellä tähtimerkillä:</span><span class="sxs-lookup"><span data-stu-id="4aa68-117">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="4aa68-118">Voit ***lihavoida ja kursivoida***  tekstiä ympäröimällä sen kolmella tähtimerkillä:</span><span class="sxs-lookup"><span data-stu-id="4aa68-118">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="4aa68-119">Luettelot</span><span class="sxs-lookup"><span data-stu-id="4aa68-119">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="4aa68-120">Järjestämätön luettelo</span><span class="sxs-lookup"><span data-stu-id="4aa68-120">Unordered list</span></span>

<span data-ttu-id="4aa68-121">Voit muotoilla järjestämättömän / luettelomerkein varustetun luettelon käyttämällä joko tähtimerkkejä tai ajatusviivoja.</span><span class="sxs-lookup"><span data-stu-id="4aa68-121">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="4aa68-122">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="4aa68-122">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="4aa68-123">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="4aa68-123">will be rendered as:</span></span>

- <span data-ttu-id="4aa68-124">Luettelokohde 1</span><span class="sxs-lookup"><span data-stu-id="4aa68-124">List item 1</span></span>
- <span data-ttu-id="4aa68-125">Luettelokohde 2</span><span class="sxs-lookup"><span data-stu-id="4aa68-125">List item 2</span></span>
- <span data-ttu-id="4aa68-126">Luettelokohde 3</span><span class="sxs-lookup"><span data-stu-id="4aa68-126">List item 3</span></span>

<span data-ttu-id="4aa68-127">Voit luoda luettelon toisen luettelon sisälle sisentämällä aliluettelon kohteet.</span><span class="sxs-lookup"><span data-stu-id="4aa68-127">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="4aa68-128">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="4aa68-128">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="4aa68-129">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="4aa68-129">will be rendered as:</span></span>

- <span data-ttu-id="4aa68-130">Luettelokohde 1</span><span class="sxs-lookup"><span data-stu-id="4aa68-130">List item 1</span></span>
  - <span data-ttu-id="4aa68-131">Luettelokohde A</span><span class="sxs-lookup"><span data-stu-id="4aa68-131">List item A</span></span>
  - <span data-ttu-id="4aa68-132">Luettelokohde B</span><span class="sxs-lookup"><span data-stu-id="4aa68-132">List item B</span></span>
- <span data-ttu-id="4aa68-133">Luettelokohde 2</span><span class="sxs-lookup"><span data-stu-id="4aa68-133">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="4aa68-134">Järjestetty luettelo</span><span class="sxs-lookup"><span data-stu-id="4aa68-134">Ordered list</span></span>

<span data-ttu-id="4aa68-135">Voit muotoilla järjestetyn/asteittaisen luettelon käyttämällä vastaavia numeroita.</span><span class="sxs-lookup"><span data-stu-id="4aa68-135">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="4aa68-136">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="4aa68-136">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="4aa68-137">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="4aa68-137">will be rendered as:</span></span>

1. <span data-ttu-id="4aa68-138">Ensimmäinen ohje</span><span class="sxs-lookup"><span data-stu-id="4aa68-138">First instruction</span></span>
2. <span data-ttu-id="4aa68-139">Toinen ohje</span><span class="sxs-lookup"><span data-stu-id="4aa68-139">Second instruction</span></span>
3. <span data-ttu-id="4aa68-140">Kolmas ohje</span><span class="sxs-lookup"><span data-stu-id="4aa68-140">Third instruction</span></span>

<span data-ttu-id="4aa68-141">Voit luoda luettelon toisen luettelon sisälle sisentämällä aliluettelon kohteet.</span><span class="sxs-lookup"><span data-stu-id="4aa68-141">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="4aa68-142">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="4aa68-142">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="4aa68-143">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="4aa68-143">will be rendered as:</span></span>

1. <span data-ttu-id="4aa68-144">Ensimmäinen ohje</span><span class="sxs-lookup"><span data-stu-id="4aa68-144">First instruction</span></span>
   1. <span data-ttu-id="4aa68-145">Alaohje</span><span class="sxs-lookup"><span data-stu-id="4aa68-145">Sub-instruction</span></span>
   2. <span data-ttu-id="4aa68-146">Alaohje</span><span class="sxs-lookup"><span data-stu-id="4aa68-146">Sub-instruction</span></span>
2. <span data-ttu-id="4aa68-147">Toinen ohje</span><span class="sxs-lookup"><span data-stu-id="4aa68-147">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="4aa68-148">Taulukot</span><span class="sxs-lookup"><span data-stu-id="4aa68-148">Tables</span></span>

<span data-ttu-id="4aa68-149">Taulukot eivät kuulu Markdownin ydinkokonaisuuteen, mutta GFM tukee niitä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-149">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="4aa68-150">Voit luoda taulukoita käyttämällä pystyviivaa (|) ja tavuviivaa (-).</span><span class="sxs-lookup"><span data-stu-id="4aa68-150">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="4aa68-151">Tavuviivat luovat sarakkeen otsikon ja pystyviivat erottavat sarakkeet toisistaan.</span><span class="sxs-lookup"><span data-stu-id="4aa68-151">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="4aa68-152">Lisää tyhjä rivi taulukon eteen, niin se hahmonnetaan oikein.</span><span class="sxs-lookup"><span data-stu-id="4aa68-152">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="4aa68-153">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="4aa68-153">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="4aa68-154">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="4aa68-154">will be rendered as:</span></span>

| <span data-ttu-id="4aa68-155">Pidä</span><span class="sxs-lookup"><span data-stu-id="4aa68-155">Fun</span></span>                  | <span data-ttu-id="4aa68-156">hauskaa</span><span class="sxs-lookup"><span data-stu-id="4aa68-156">With</span></span>                 | <span data-ttu-id="4aa68-157">taulukoilla</span><span class="sxs-lookup"><span data-stu-id="4aa68-157">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="4aa68-158">vasemmalle tasattu sarake</span><span class="sxs-lookup"><span data-stu-id="4aa68-158">left-aligned column</span></span>  | <span data-ttu-id="4aa68-159">oikealle tasattu sarake</span><span class="sxs-lookup"><span data-stu-id="4aa68-159">right-aligned column</span></span> | <span data-ttu-id="4aa68-160">keskitetty sarake</span><span class="sxs-lookup"><span data-stu-id="4aa68-160">centered column</span></span> |
| <span data-ttu-id="4aa68-161">100 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-161">$100</span></span>                 | <span data-ttu-id="4aa68-162">100 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-162">$100</span></span>                 | <span data-ttu-id="4aa68-163">100 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-163">$100</span></span>            |
| <span data-ttu-id="4aa68-164">10 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-164">$10</span></span>                  | <span data-ttu-id="4aa68-165">10 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-165">$10</span></span>                  | <span data-ttu-id="4aa68-166">10 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-166">$10</span></span>             |
| <span data-ttu-id="4aa68-167">1 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-167">$1</span></span>                   | <span data-ttu-id="4aa68-168">1 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-168">$1</span></span>                   | <span data-ttu-id="4aa68-169">1 €</span><span class="sxs-lookup"><span data-stu-id="4aa68-169">$1</span></span>              |

<span data-ttu-id="4aa68-170">Jos haluat lisätietoja taulukoiden luomisesta, katso:</span><span class="sxs-lookup"><span data-stu-id="4aa68-170">For more information on creating tables, see:</span></span>

- <span data-ttu-id="4aa68-171">Markdigin [taulukon rivitysominaisuus](#table-wrapping), joka voi auttaa leveiden taulukoiden muotoilussa.</span><span class="sxs-lookup"><span data-stu-id="4aa68-171">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="4aa68-172">GitHubin [tietojen järjestäminen taulukoiden avulla](https://help.github.com/articles/organizing-information-with-tables/).</span><span class="sxs-lookup"><span data-stu-id="4aa68-172">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="4aa68-173">[Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) -verkkosovellus.</span><span class="sxs-lookup"><span data-stu-id="4aa68-173">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="4aa68-174">[Adam Pritchardin Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span><span class="sxs-lookup"><span data-stu-id="4aa68-174">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="4aa68-175">[Michel Fortinin Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="4aa68-175">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="4aa68-176">[HTML-taulukoiden muuntaminen Markdowniksi](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="4aa68-176">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="4aa68-177">Linkit</span><span class="sxs-lookup"><span data-stu-id="4aa68-177">Links</span></span>

<span data-ttu-id="4aa68-178">Tekstin sisäisen linkin Markdown-syntaksi koostuu `[link text]`-osasta, joka on hyperlinkitettävä teksti, ja `(file-name.md)`-osasta, joka on linkitettävän URL-osoitteen tai tiedoston nimi:</span><span class="sxs-lookup"><span data-stu-id="4aa68-178">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="4aa68-179">Jos haluat lisätietoja linkittämisestä, katso:</span><span class="sxs-lookup"><span data-stu-id="4aa68-179">For more information on linking, see:</span></span>

- <span data-ttu-id="4aa68-180">[Markdown- syntaksioppaasta](https://daringfireball.net/projects/markdown/syntax#link) tietoja Markdownin peruslinkitystuesta.</span><span class="sxs-lookup"><span data-stu-id="4aa68-180">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="4aa68-181">Tämän oppaan [Linkit](how-to-write-links.md)-osasta tietoja Markdigin sisältämästä lisäsyntaksista linkittämistä varten.</span><span class="sxs-lookup"><span data-stu-id="4aa68-181">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="4aa68-182">Koodikatkelmat</span><span class="sxs-lookup"><span data-stu-id="4aa68-182">Code snippets</span></span>

<span data-ttu-id="4aa68-183">Markdown tukee koodikatkelmien sijoittamista lauseiden sisään sekä lauseiden väliin erillisinä aidattuina lohkoina.</span><span class="sxs-lookup"><span data-stu-id="4aa68-183">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="4aa68-184">Lisätietoja:</span><span class="sxs-lookup"><span data-stu-id="4aa68-184">For details, see:</span></span>

- [<span data-ttu-id="4aa68-185">Markdownin oma koodilohkojen tuki</span><span class="sxs-lookup"><span data-stu-id="4aa68-185">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="4aa68-186">GFM:n tuki koodin aitaamiselle ja syntaksin korostukselle</span><span class="sxs-lookup"><span data-stu-id="4aa68-186">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="4aa68-187">Aidatut koodilohkot ovat helppo tapa mahdollistaa syntaksin korostus koodikatkelmissa.</span><span class="sxs-lookup"><span data-stu-id="4aa68-187">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="4aa68-188">Aidattujen koodilohkojen yleinen muotoilu on:</span><span class="sxs-lookup"><span data-stu-id="4aa68-188">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="4aa68-189">Ensimmäisten kolmen gravis-merkin (\`) jälkeen tuleva alias määrittää käytettävän syntaksin korostuksen.</span><span class="sxs-lookup"><span data-stu-id="4aa68-189">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="4aa68-190">Seuraavassa on luettelo Docs-sisällössä yleisesti käytetyistä ohjelmointikielistä ja vastaavasta selitteestä:</span><span class="sxs-lookup"><span data-stu-id="4aa68-190">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="4aa68-191">Näille kielille on kutsumanimituki, ja useimmille on käytössä kielen korostus.</span><span class="sxs-lookup"><span data-stu-id="4aa68-191">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="4aa68-192">Nimi</span><span class="sxs-lookup"><span data-stu-id="4aa68-192">Name</span></span>|<span data-ttu-id="4aa68-193">Markdown-selite</span><span class="sxs-lookup"><span data-stu-id="4aa68-193">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="4aa68-194">.NET Console</span><span class="sxs-lookup"><span data-stu-id="4aa68-194">.NET Console</span></span>|<span data-ttu-id="4aa68-195">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="4aa68-195">dotnetcli</span></span>|
|<span data-ttu-id="4aa68-196">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="4aa68-196">ASP.NET (C#)</span></span>|<span data-ttu-id="4aa68-197">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="4aa68-197">aspx-csharp</span></span>|
|<span data-ttu-id="4aa68-198">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="4aa68-198">ASP.NET (VB)</span></span>|<span data-ttu-id="4aa68-199">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="4aa68-199">aspx-vb</span></span>|
|<span data-ttu-id="4aa68-200">AzCopy</span><span class="sxs-lookup"><span data-stu-id="4aa68-200">AzCopy</span></span>|<span data-ttu-id="4aa68-201">AzCopy</span><span class="sxs-lookup"><span data-stu-id="4aa68-201">azcopy</span></span>|
|<span data-ttu-id="4aa68-202">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="4aa68-202">Azure CLI</span></span>|<span data-ttu-id="4aa68-203">azurecli</span><span class="sxs-lookup"><span data-stu-id="4aa68-203">azurecli</span></span>|
|<span data-ttu-id="4aa68-204">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="4aa68-204">Azure PowerShell</span></span>|<span data-ttu-id="4aa68-205">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="4aa68-205">azurepowershell</span></span>|
|<span data-ttu-id="4aa68-206">C++</span><span class="sxs-lookup"><span data-stu-id="4aa68-206">C++</span></span>|<span data-ttu-id="4aa68-207">cpp</span><span class="sxs-lookup"><span data-stu-id="4aa68-207">cpp</span></span>|
|<span data-ttu-id="4aa68-208">C++/CX</span><span class="sxs-lookup"><span data-stu-id="4aa68-208">C++/CX</span></span>|<span data-ttu-id="4aa68-209">cppcx</span><span class="sxs-lookup"><span data-stu-id="4aa68-209">cppcx</span></span>|
|<span data-ttu-id="4aa68-210">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="4aa68-210">C++/WinRT</span></span>|<span data-ttu-id="4aa68-211">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="4aa68-211">cppwinrt</span></span>|
|<span data-ttu-id="4aa68-212">C#</span><span class="sxs-lookup"><span data-stu-id="4aa68-212">C#</span></span>|<span data-ttu-id="4aa68-213">csharp</span><span class="sxs-lookup"><span data-stu-id="4aa68-213">csharp</span></span>|
|<span data-ttu-id="4aa68-214">CSHTML</span><span class="sxs-lookup"><span data-stu-id="4aa68-214">CSHTML</span></span>|<span data-ttu-id="4aa68-215">cshtml</span><span class="sxs-lookup"><span data-stu-id="4aa68-215">cshtml</span></span>|
|<span data-ttu-id="4aa68-216">DAX</span><span class="sxs-lookup"><span data-stu-id="4aa68-216">DAX</span></span>|<span data-ttu-id="4aa68-217">dax</span><span class="sxs-lookup"><span data-stu-id="4aa68-217">dax</span></span>|
|<span data-ttu-id="4aa68-218">F#</span><span class="sxs-lookup"><span data-stu-id="4aa68-218">F#</span></span>|<span data-ttu-id="4aa68-219">fsharp</span><span class="sxs-lookup"><span data-stu-id="4aa68-219">fsharp</span></span>|
|<span data-ttu-id="4aa68-220">Go</span><span class="sxs-lookup"><span data-stu-id="4aa68-220">Go</span></span>|<span data-ttu-id="4aa68-221">go</span><span class="sxs-lookup"><span data-stu-id="4aa68-221">go</span></span>|
|<span data-ttu-id="4aa68-222">HTML</span><span class="sxs-lookup"><span data-stu-id="4aa68-222">HTML</span></span>|<span data-ttu-id="4aa68-223">html</span><span class="sxs-lookup"><span data-stu-id="4aa68-223">html</span></span>|
|<span data-ttu-id="4aa68-224">HTTP</span><span class="sxs-lookup"><span data-stu-id="4aa68-224">HTTP</span></span>|<span data-ttu-id="4aa68-225">http</span><span class="sxs-lookup"><span data-stu-id="4aa68-225">http</span></span>|
|<span data-ttu-id="4aa68-226">Java</span><span class="sxs-lookup"><span data-stu-id="4aa68-226">Java</span></span>|<span data-ttu-id="4aa68-227">java</span><span class="sxs-lookup"><span data-stu-id="4aa68-227">java</span></span>|
|<span data-ttu-id="4aa68-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4aa68-228">JavaScript</span></span>|<span data-ttu-id="4aa68-229">javascript</span><span class="sxs-lookup"><span data-stu-id="4aa68-229">javascript</span></span>|
|<span data-ttu-id="4aa68-230">JSON</span><span class="sxs-lookup"><span data-stu-id="4aa68-230">JSON</span></span>|<span data-ttu-id="4aa68-231">json</span><span class="sxs-lookup"><span data-stu-id="4aa68-231">json</span></span>|
|<span data-ttu-id="4aa68-232">Markdown</span><span class="sxs-lookup"><span data-stu-id="4aa68-232">Markdown</span></span>|<span data-ttu-id="4aa68-233">md</span><span class="sxs-lookup"><span data-stu-id="4aa68-233">md</span></span>|
|<span data-ttu-id="4aa68-234">NodeJS</span><span class="sxs-lookup"><span data-stu-id="4aa68-234">NodeJS</span></span>|<span data-ttu-id="4aa68-235">nodejs</span><span class="sxs-lookup"><span data-stu-id="4aa68-235">nodejs</span></span>|
|<span data-ttu-id="4aa68-236">Objective-C</span><span class="sxs-lookup"><span data-stu-id="4aa68-236">Objective-C</span></span>|<span data-ttu-id="4aa68-237">objc</span><span class="sxs-lookup"><span data-stu-id="4aa68-237">objc</span></span>|
|<span data-ttu-id="4aa68-238">OData</span><span class="sxs-lookup"><span data-stu-id="4aa68-238">OData</span></span>|<span data-ttu-id="4aa68-239">odata</span><span class="sxs-lookup"><span data-stu-id="4aa68-239">odata</span></span>|
|<span data-ttu-id="4aa68-240">PHP</span><span class="sxs-lookup"><span data-stu-id="4aa68-240">PHP</span></span>|<span data-ttu-id="4aa68-241">php</span><span class="sxs-lookup"><span data-stu-id="4aa68-241">php</span></span>|
|<span data-ttu-id="4aa68-242">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="4aa68-242">Power Apps Formula</span></span>|<span data-ttu-id="4aa68-243">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="4aa68-243">powerappsfl</span></span>|
|<span data-ttu-id="4aa68-244">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4aa68-244">PowerShell</span></span>|<span data-ttu-id="4aa68-245">powershell</span><span class="sxs-lookup"><span data-stu-id="4aa68-245">powershell</span></span>|
|<span data-ttu-id="4aa68-246">Python</span><span class="sxs-lookup"><span data-stu-id="4aa68-246">Python</span></span>|<span data-ttu-id="4aa68-247">python</span><span class="sxs-lookup"><span data-stu-id="4aa68-247">python</span></span>|
|<span data-ttu-id="4aa68-248">Q#</span><span class="sxs-lookup"><span data-stu-id="4aa68-248">Q#</span></span>|<span data-ttu-id="4aa68-249">qsharp</span><span class="sxs-lookup"><span data-stu-id="4aa68-249">qsharp</span></span>|
|<span data-ttu-id="4aa68-250">R</span><span class="sxs-lookup"><span data-stu-id="4aa68-250">R</span></span>|<span data-ttu-id="4aa68-251">r</span><span class="sxs-lookup"><span data-stu-id="4aa68-251">r</span></span>|
|<span data-ttu-id="4aa68-252">Ruby</span><span class="sxs-lookup"><span data-stu-id="4aa68-252">Ruby</span></span>|<span data-ttu-id="4aa68-253">ruby</span><span class="sxs-lookup"><span data-stu-id="4aa68-253">ruby</span></span>|
|<span data-ttu-id="4aa68-254">SQL</span><span class="sxs-lookup"><span data-stu-id="4aa68-254">SQL</span></span>|<span data-ttu-id="4aa68-255">sql</span><span class="sxs-lookup"><span data-stu-id="4aa68-255">sql</span></span>|
|<span data-ttu-id="4aa68-256">Swift</span><span class="sxs-lookup"><span data-stu-id="4aa68-256">Swift</span></span>|<span data-ttu-id="4aa68-257">swift</span><span class="sxs-lookup"><span data-stu-id="4aa68-257">swift</span></span>|
|<span data-ttu-id="4aa68-258">TypeScript</span><span class="sxs-lookup"><span data-stu-id="4aa68-258">TypeScript</span></span>|<span data-ttu-id="4aa68-259">typescript</span><span class="sxs-lookup"><span data-stu-id="4aa68-259">typescript</span></span>|
|<span data-ttu-id="4aa68-260">VB</span><span class="sxs-lookup"><span data-stu-id="4aa68-260">VB</span></span>|<span data-ttu-id="4aa68-261">vb</span><span class="sxs-lookup"><span data-stu-id="4aa68-261">vb</span></span>|
|<span data-ttu-id="4aa68-262">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="4aa68-262">VSTS CLI</span></span>|<span data-ttu-id="4aa68-263">vstscli</span><span class="sxs-lookup"><span data-stu-id="4aa68-263">vstscli</span></span>|
|<span data-ttu-id="4aa68-264">XAML</span><span class="sxs-lookup"><span data-stu-id="4aa68-264">XAML</span></span>|<span data-ttu-id="4aa68-265">xaml</span><span class="sxs-lookup"><span data-stu-id="4aa68-265">xaml</span></span>|
|<span data-ttu-id="4aa68-266">XML</span><span class="sxs-lookup"><span data-stu-id="4aa68-266">XML</span></span>|<span data-ttu-id="4aa68-267">xml</span><span class="sxs-lookup"><span data-stu-id="4aa68-267">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="4aa68-268">Esimerkki: C\#</span><span class="sxs-lookup"><span data-stu-id="4aa68-268">Example: C\#</span></span>

<span data-ttu-id="4aa68-269">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="4aa68-269">__Markdown__</span></span>

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

<span data-ttu-id="4aa68-270">__Hahmonnus__</span><span class="sxs-lookup"><span data-stu-id="4aa68-270">__Render__</span></span>

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a><span data-ttu-id="4aa68-271">Esimerkki: SQL</span><span class="sxs-lookup"><span data-stu-id="4aa68-271">Example: SQL</span></span>

<span data-ttu-id="4aa68-272">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="4aa68-272">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="4aa68-273">__Hahmonnus__</span><span class="sxs-lookup"><span data-stu-id="4aa68-273">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="4aa68-274">OPS:n mukautetut Markdown-laajennukset</span><span class="sxs-lookup"><span data-stu-id="4aa68-274">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="4aa68-275">Open Publishing Services (OPS) käyttää Markdig Parser for Markdownia, joka on laajasti yhteensopiva GitHub Flavored Markdownin (GFM) kanssa.</span><span class="sxs-lookup"><span data-stu-id="4aa68-275">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="4aa68-276">Markdig lisää joitakin toimintoja Markdown-laajennusten kautta.</span><span class="sxs-lookup"><span data-stu-id="4aa68-276">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="4aa68-277">Tähän oppaaseen onkin sisällytetty valittuja artikkeleita OPS-oppaasta.</span><span class="sxs-lookup"><span data-stu-id="4aa68-277">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="4aa68-278">(Katso sisällysluettelosta esimerkiksi kohdat Markdig ja Markdown-laajennukset ja Koodikatkelmat.)</span><span class="sxs-lookup"><span data-stu-id="4aa68-278">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="4aa68-279">Docs.artikkelit käyttävät GFM:ää suurimpaan osaan artikkeleiden muotoilusta, esimerkiksi kappaleiden, luettelojen ja otsikkojen muotoiluun.</span><span class="sxs-lookup"><span data-stu-id="4aa68-279">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="4aa68-280">Monipuolisempaa muotoilua artikkeleihin saadaan käyttämällä Markdig-ominaisuuksia, kuten:</span><span class="sxs-lookup"><span data-stu-id="4aa68-280">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="4aa68-281">Huomautuslohkot</span><span class="sxs-lookup"><span data-stu-id="4aa68-281">Note blocks</span></span>
- <span data-ttu-id="4aa68-282">Sisällytykset</span><span class="sxs-lookup"><span data-stu-id="4aa68-282">Includes</span></span>
- <span data-ttu-id="4aa68-283">Valitsimet</span><span class="sxs-lookup"><span data-stu-id="4aa68-283">Selectors</span></span>
- <span data-ttu-id="4aa68-284">Upotetut videot</span><span class="sxs-lookup"><span data-stu-id="4aa68-284">Embedded videos</span></span>
- <span data-ttu-id="4aa68-285">Koodikatkelmat/-näytteet</span><span class="sxs-lookup"><span data-stu-id="4aa68-285">Code snippets/samples</span></span>

<span data-ttu-id="4aa68-286">Täydellisen luettelon näet sisällysluettelon kohdista Markdig ja Markdown-laajennukset ja Koodikatkelmat.</span><span class="sxs-lookup"><span data-stu-id="4aa68-286">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="4aa68-287">Huomautuslohkot</span><span class="sxs-lookup"><span data-stu-id="4aa68-287">Note blocks</span></span>

<span data-ttu-id="4aa68-288">Voit kiinnittää käyttäjän huomion tiettyyn sisältöön valitsemalla neljästä huomautuslohkotyypistä:</span><span class="sxs-lookup"><span data-stu-id="4aa68-288">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="4aa68-289">HUOMAUTUS</span><span class="sxs-lookup"><span data-stu-id="4aa68-289">NOTE</span></span>
- <span data-ttu-id="4aa68-290">VAROITUS</span><span class="sxs-lookup"><span data-stu-id="4aa68-290">WARNING</span></span>
- <span data-ttu-id="4aa68-291">VIHJE</span><span class="sxs-lookup"><span data-stu-id="4aa68-291">TIP</span></span>
- <span data-ttu-id="4aa68-292">TÄRKEÄ</span><span class="sxs-lookup"><span data-stu-id="4aa68-292">IMPORTANT</span></span>

<span data-ttu-id="4aa68-293">Huomautuslohkoja tulisi käyttää säästeliäästi, koska ne voivat olla häiritsevä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-293">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="4aa68-294">Vaikka huomautuslohkot tukevat koodilohkoja, kuvia, luetteloja ja linkkejä, pyri pitämään ne yksinkertaisina ja selkeinä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-294">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="4aa68-295">Sisällytykset</span><span class="sxs-lookup"><span data-stu-id="4aa68-295">Includes</span></span>

<span data-ttu-id="4aa68-296">Kun haluat lisätä artikkelitiedostoihin uudelleenkäytettävää tekstiä tai kuvatiedostoja, voit sisällyttää tiedoston käyttämällä viittausta Markdigin tiedostojen sisällytysominaisuuden avulla.</span><span class="sxs-lookup"><span data-stu-id="4aa68-296">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="4aa68-297">Tämä ominaisuus ohjaa OPS:n sisällyttämään tiedoston artikkelitiedostoon artikkelin muodostamisen aikana, jolloin siitä tulee julkaistun artikkelin osa.</span><span class="sxs-lookup"><span data-stu-id="4aa68-297">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="4aa68-298">Sisällön uudelleenkäyttämisen avuksi on kolme erityyppistä sisällytystä:</span><span class="sxs-lookup"><span data-stu-id="4aa68-298">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="4aa68-299">Tekstin sisäinen: Käytä yleinen tekstikatkelma uudelleen toisen lauseen sisällä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-299">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="4aa68-300">Lohko: Käytä kokonainen Markdown-tiedosto lohkona artikkelin osassa.</span><span class="sxs-lookup"><span data-stu-id="4aa68-300">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="4aa68-301">Kuva: Kuvat sisällytetään Docsissa tavallisesti näin.</span><span class="sxs-lookup"><span data-stu-id="4aa68-301">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="4aa68-302">Tekstin sisäinen tai lohkosisällytys on vain yksinkertainen Markdown-tiedosto (.md).</span><span class="sxs-lookup"><span data-stu-id="4aa68-302">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="4aa68-303">Se voi sisältää minkä tahansa kelvollisen Markdownin.</span><span class="sxs-lookup"><span data-stu-id="4aa68-303">It can contain any valid Markdown.</span></span> <span data-ttu-id="4aa68-304">Kaikki sisällytettävät Markdown-tiedostot tulisi sijoittaa [yhteiseen `/includes`-alihakemistoon](git-github-fundamentals.md#includes-subdirectory), säilön pääkansioon.</span><span class="sxs-lookup"><span data-stu-id="4aa68-304">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="4aa68-305">Kun artikkeli julkaistaan, sisällytetty tiedosto lisätään siihen saumattomasti.</span><span class="sxs-lookup"><span data-stu-id="4aa68-305">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="4aa68-306">Tässä on sisällytyksien vaatimukset ja huomioitavat seikat:</span><span class="sxs-lookup"><span data-stu-id="4aa68-306">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="4aa68-307">Käytä sisällytyksiä, kun haluat käyttää samaa tekstiä useassa artikkelissa.</span><span class="sxs-lookup"><span data-stu-id="4aa68-307">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="4aa68-308">Käytä lohkosisällytyksiä, kun sisältöä on merkittävä määrä – yksi tai kaksi kappaletta, yhteinen toimenpide tai yhteinen osa.</span><span class="sxs-lookup"><span data-stu-id="4aa68-308">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="4aa68-309">Älä käytä niitä mihinkään virkettä lyhyempään.</span><span class="sxs-lookup"><span data-stu-id="4aa68-309">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="4aa68-310">Sisällytyksiä ei hahmonneta GitHubissa artikkelin hahmonnusnäkymässä, koska ne käyttävät Markdig-laajennuksia.</span><span class="sxs-lookup"><span data-stu-id="4aa68-310">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="4aa68-311">Ne hahmonnetaan vasta julkaisemisen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="4aa68-311">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="4aa68-312">Varmista, että kaikki sisällytyksessä oleva teksti on kirjoitettu käyttäen kokonaisia virkkeitä ja ettei sen ymmärrettävyys perustu sellaiseen alkuperäisessä artikkelissa olevaan tekstiin, joka on lainattavan kohdan edellä tai jälkeen.</span><span class="sxs-lookup"><span data-stu-id="4aa68-312">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="4aa68-313">Jos tätä ohjetta ei noudateta, artikkeliin syntyy käännöskelvoton merkkijono, joka pilaa lokalisoidun käyttökokemuksen.</span><span class="sxs-lookup"><span data-stu-id="4aa68-313">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="4aa68-314">Älä upota sisällytyksiä toisiin sisällytyksiin.</span><span class="sxs-lookup"><span data-stu-id="4aa68-314">Don't embed includes within other includes.</span></span> <span data-ttu-id="4aa68-315">Niitä ei tueta.</span><span class="sxs-lookup"><span data-stu-id="4aa68-315">They are not supported.</span></span>
- <span data-ttu-id="4aa68-316">Sijoita mediatiedostot sisällytyksen alihakemistoon erityisesti liittyvään mediakansioon, esimerkiksi `<repo>`/sisällytykset/media-kansioon.</span><span class="sxs-lookup"><span data-stu-id="4aa68-316">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="4aa68-317">Mediakansion pääkansio ei saa sisältää kuvia.</span><span class="sxs-lookup"><span data-stu-id="4aa68-317">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="4aa68-318">Jos sisällytyksessä ei ole kuvia, vastaavaa mediahakemistoa ei tarvita.</span><span class="sxs-lookup"><span data-stu-id="4aa68-318">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="4aa68-319">Samoin kuin tavallisten artikkelien tapauksessa, älä jaa mediaa sisällytyskansioiden välillä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-319">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="4aa68-320">Käytä jokaiseen sisällytykseen ja artikkeliin erillistä tiedostoa, jolla on yksilöllinen nimi.</span><span class="sxs-lookup"><span data-stu-id="4aa68-320">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="4aa68-321">Tallenna mediatiedosto siihen mediakansioon, joka liittyy sisällytykseen.</span><span class="sxs-lookup"><span data-stu-id="4aa68-321">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="4aa68-322">Älä käytä sisällytystä artikkelin ainoana sisältönä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-322">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="4aa68-323">Sisällytysten on tarkoitus lisätä sisältöä varsinaiseen artikkeliin.</span><span class="sxs-lookup"><span data-stu-id="4aa68-323">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="4aa68-324">Valitsimet</span><span class="sxs-lookup"><span data-stu-id="4aa68-324">Selectors</span></span>

<span data-ttu-id="4aa68-325">Käytä valitsimia teknisissä artikkeleissa, kun kirjoitat samasta artikkelista useampaa versiota. Valitsimien avulla voit ottaa huomioon eri teknologioista ja käyttöympäristöistä johtuvat erot.</span><span class="sxs-lookup"><span data-stu-id="4aa68-325">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="4aa68-326">Tämä koskee useimmiten kehittäjille suunnattua mobiilikäyttöympäristöä käsittelevää sisältöä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-326">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="4aa68-327">Markdigissä on tällä hetkellä kaksi erityyppistä valitsinta: yksittäinen valitsin ja monivalitsin.</span><span class="sxs-lookup"><span data-stu-id="4aa68-327">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="4aa68-328">Koska sama valitsin-Markdown sijoitetaan kaikkiin valittuihin artikkeleihin, artikkelin valitsin on suositeltavaa sijoittaa sisällytykseen.</span><span class="sxs-lookup"><span data-stu-id="4aa68-328">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="4aa68-329">Tällöin voit viitata sisällytykseen kaikissa niissä artikkeleissa, jotka käyttävät samaa valitsinta.</span><span class="sxs-lookup"><span data-stu-id="4aa68-329">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="4aa68-330">Koodikatkelmat</span><span class="sxs-lookup"><span data-stu-id="4aa68-330">Code snippets</span></span>

<span data-ttu-id="4aa68-331">Markdig tukee koodin edistynyttä sisällytystä artikkeleihin koodikatkelmalaajennuksen avulla.</span><span class="sxs-lookup"><span data-stu-id="4aa68-331">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="4aa68-332">Se käyttää edistynyttä hahmonnusta, joka perustuu erilaisiin GFM-ominaisuuksiin, kuten ohjelmointikielen valintaan ja syntaksin väritykseen, sekä ominaisuuksiin, kuten:</span><span class="sxs-lookup"><span data-stu-id="4aa68-332">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="4aa68-333">Keskitettyjen koodinäytteiden/-katkelmien sisällyttäminen ulkoisesta säilöstä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-333">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="4aa68-334">Välilehtiin jaettu käyttöliittymä, jolloin voidaan näyttää koodinäytteiden useita versioita eri kielillä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-334">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="4aa68-335">Gotchat ja vianmääritys</span><span class="sxs-lookup"><span data-stu-id="4aa68-335">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="4aa68-336">Alt-teksti</span><span class="sxs-lookup"><span data-stu-id="4aa68-336">Alt text</span></span>

<span data-ttu-id="4aa68-337">Alaviivoja sisältävää Alt-tekstiä ei hahmonneta oikein.</span><span class="sxs-lookup"><span data-stu-id="4aa68-337">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="4aa68-338">Esimerkiksi tämän käyttämisen sijaan:</span><span class="sxs-lookup"><span data-stu-id="4aa68-338">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="4aa68-339">Muotoile alaviivat näin:</span><span class="sxs-lookup"><span data-stu-id="4aa68-339">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="4aa68-340">Heittomerkit ja lainausmerkit</span><span class="sxs-lookup"><span data-stu-id="4aa68-340">Apostrophes and quotation marks</span></span>

<span data-ttu-id="4aa68-341">Jos kopioit tekstiä Wordista Markdown-editoriin, teksti saattaa sisältää ns. älykkäitä (kaarevia) heittomerkkejä tai lainausmerkkejä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-341">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="4aa68-342">Nämä täytyy koodata tai muuttaa tavallisiksi heittomerkeiksi tai lainausmerkeiksi.</span><span class="sxs-lookup"><span data-stu-id="4aa68-342">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span>
<span data-ttu-id="4aa68-343">Muuten tekstiin päätyy julkaisuvaiheessa virheellisiä merkkejä, esim. Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="4aa68-343">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="4aa68-344">Seuraavassa on näiden välimerkkien älykkäiden versioiden koodaukset:</span><span class="sxs-lookup"><span data-stu-id="4aa68-344">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="4aa68-345">Vasen (avaava) lainausmerkki: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="4aa68-345">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="4aa68-346">Oikea (sulkeva) lainausmerkki: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="4aa68-346">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="4aa68-347">Oikea (sulkeva) puolilainausmerkki tai heittomerkki: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="4aa68-347">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="4aa68-348">Vasen (avaava) puolilainausmerkki (käytetään harvoin): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="4aa68-348">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="4aa68-349">Kulmasulkeet</span><span class="sxs-lookup"><span data-stu-id="4aa68-349">Angle brackets</span></span>

<span data-ttu-id="4aa68-350">Kulmasulkeita käytetään tavallisesti osoittamaan paikkamerkkiä.</span><span class="sxs-lookup"><span data-stu-id="4aa68-350">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="4aa68-351">Kun teet näin tekstin sisällä (ei koodissa), kulmasulkeet on koodattava.</span><span class="sxs-lookup"><span data-stu-id="4aa68-351">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="4aa68-352">Muuten Markdown tulkitsee ne HTML-tunnisteiksi.</span><span class="sxs-lookup"><span data-stu-id="4aa68-352">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="4aa68-353">Koodaa `<script name>` esimerkiksi näin: `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="4aa68-353">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="4aa68-354">Katso myös:</span><span class="sxs-lookup"><span data-stu-id="4aa68-354">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="4aa68-355">Markdown-resursseja</span><span class="sxs-lookup"><span data-stu-id="4aa68-355">Markdown resources</span></span>

- [<span data-ttu-id="4aa68-356">Johdatus Markdowniin</span><span class="sxs-lookup"><span data-stu-id="4aa68-356">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="4aa68-357">Docs Markdown -pikaopas</span><span class="sxs-lookup"><span data-stu-id="4aa68-357">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="4aa68-358">GitHubin Markdown-perusteet</span><span class="sxs-lookup"><span data-stu-id="4aa68-358">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
- [<span data-ttu-id="4aa68-359">Markdown-opas</span><span class="sxs-lookup"><span data-stu-id="4aa68-359">The Markdown Guide</span></span>](https://www.markdownguide.org/)
