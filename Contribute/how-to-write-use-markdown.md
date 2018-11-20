---
title: Miten käyttää Markdownina Docsien kirjoittamiseen
description: Tässä artikkelissa on perustiedot ja viiteohjeet docs.microsoft.com -artikkelien kirjoittamiseen käytettävään Markdown-kieleen.
ms.date: 07/13/2017
ms.openlocfilehash: 21194c4bd6020d847b526a4d9544c826aa199e2a
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609518"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="066d0-103">Miten käyttää Markdownia Docsien kirjoittamiseen</span><span class="sxs-lookup"><span data-stu-id="066d0-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="066d0-104">[Docs.microsoft.com](http://docs.microsoft.com)-artikkelit kirjoitetaan kevyellä [Markdown](https://daringfireball.net/projects/markdown/)-nimisellä merkintäkielellä, joka on sekä helppolukuinen että helppo oppia.</span><span class="sxs-lookup"><span data-stu-id="066d0-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="066d0-105">Tämän vuoksi siitä on nopeasti tullut alan standardi.</span><span class="sxs-lookup"><span data-stu-id="066d0-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="066d0-106">Koska Docs-sisältö säilytetään GitHubissa, se voi käyttää [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) -nimistä Markdownin yläjoukkoa, joka sisältää lisätoimintoja yleisiä muotoilutarpeita varten.</span><span class="sxs-lookup"><span data-stu-id="066d0-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="066d0-107">Lisäksi Open Publishing Services (OPS) käyttää Markdig Markdown Parseria.</span><span class="sxs-lookup"><span data-stu-id="066d0-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="066d0-108">Markdig on laajasti yhteensopiva GFM:n kanssa, ja se lisää Docsiin liittyvää toiminnallisuutta.</span><span class="sxs-lookup"><span data-stu-id="066d0-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="066d0-109">Markdig on nopea, tehokas, CommonMark-yhteensopiva, laajennettava Markdown-suoritin .NETiä varten.</span><span class="sxs-lookup"><span data-stu-id="066d0-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="066d0-110">Entistä parempi yhteisön tuki</span><span class="sxs-lookup"><span data-stu-id="066d0-110">Better community support</span></span>
* <span data-ttu-id="066d0-111">Entistä parempi standardien tuki</span><span class="sxs-lookup"><span data-stu-id="066d0-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="066d0-112">Markdownin perusteet</span><span class="sxs-lookup"><span data-stu-id="066d0-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="066d0-113">Otsikot</span><span class="sxs-lookup"><span data-stu-id="066d0-113">Headings</span></span>

<span data-ttu-id="066d0-114">Voit luoda otsikon käyttämällä #-merkkiä seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

<span data-ttu-id="066d0-115">Otsikoiden luonnissa tulee käyttää atx-tyyliä, eli otsikko tulee merkitä rivin alussa olevilla 1–6 ristikkomerkillä, jotka vastaavat HTML-otsikkotasoja H1–H6.</span><span class="sxs-lookup"><span data-stu-id="066d0-115">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="066d0-116">Yllä näet esimerkit tasojen 1–4 otsikoista.</span><span class="sxs-lookup"><span data-stu-id="066d0-116">Examples of first- through fourth-level headers are used above.</span></span>

<span data-ttu-id="066d0-117">Aiheessa saa olla **vain yksi** ensimmäisen tason otsikko (H1). Se näytetään sivun otsikkona.</span><span class="sxs-lookup"><span data-stu-id="066d0-117">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="066d0-118">Jos otsikko päättyy `#`-merkkiin, otsikon oikea hahmontaminen edellyttää ylimääräisen `#`-merkin lisäämistä otsikon loppuun.</span><span class="sxs-lookup"><span data-stu-id="066d0-118">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="066d0-119">Esimerkki: `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="066d0-119">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="066d0-120">Toisen tason otsikoista luodaan sivulle sisällysluettelo, joka näytetään sivun otsikon alla olevassa Artikkelin sisältö -kohdassa.</span><span class="sxs-lookup"><span data-stu-id="066d0-120">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="bold-and-italic-text"></a><span data-ttu-id="066d0-121">Tekstin lihavointi ja kursivointi</span><span class="sxs-lookup"><span data-stu-id="066d0-121">Bold and italic text</span></span>

<span data-ttu-id="066d0-122">Voit **lihavoida** tekstiä ympäröimällä sen kahdella tähtimerkillä:</span><span class="sxs-lookup"><span data-stu-id="066d0-122">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="066d0-123">Voit *kursivoida* tekstiä ympäröimällä sen yhdellä tähtimerkillä:</span><span class="sxs-lookup"><span data-stu-id="066d0-123">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="066d0-124">Voit ***lihavoida ja kursivoida***  tekstiä ympäröimällä sen kolmella tähtimerkillä:</span><span class="sxs-lookup"><span data-stu-id="066d0-124">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a><span data-ttu-id="066d0-125">Pitkät lainaukset</span><span class="sxs-lookup"><span data-stu-id="066d0-125">Blockquotes</span></span>

<span data-ttu-id="066d0-126">Pitkät lainaukset luodaan `>`-merkin avulla:</span><span class="sxs-lookup"><span data-stu-id="066d0-126">Blockquotes are created using the `>` character:</span></span>

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

<span data-ttu-id="066d0-127">Yllä oleva esimerkki hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-127">The preceding example renders as follows:</span></span>

> <span data-ttu-id="066d0-128">Kuivuutta oli nyt kestänyt kymmenen miljoonaa vuotta, ja hirmuliskojen valtakausi oli aikoja sitten päättynyt.</span><span class="sxs-lookup"><span data-stu-id="066d0-128">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="066d0-129">Täällä päiväntasaajalla, mantereella, joka jonain päivänä tunnettaisiin Afrikkana, oli olemassaolon taistelu saavuttanut uuden raivokkaan huipun.</span><span class="sxs-lookup"><span data-stu-id="066d0-129">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="066d0-130">Tässä hedelmättömässä, kuivassa maassa voivat vain pienet, nopeat tai raivoisat menestyä tai edes toivoa säilyvänsä.</span><span class="sxs-lookup"><span data-stu-id="066d0-130">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

### <a name="lists"></a><span data-ttu-id="066d0-131">Luettelot</span><span class="sxs-lookup"><span data-stu-id="066d0-131">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="066d0-132">Järjestämätön luettelo</span><span class="sxs-lookup"><span data-stu-id="066d0-132">Unordered list</span></span>

<span data-ttu-id="066d0-133">Voit muotoilla järjestämättömän / luettelomerkein varustetun luettelon käyttämällä joko tähtimerkkejä tai ajatusviivoja.</span><span class="sxs-lookup"><span data-stu-id="066d0-133">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="066d0-134">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="066d0-134">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="066d0-135">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-135">will be rendered as:</span></span>

- <span data-ttu-id="066d0-136">Luettelokohde 1</span><span class="sxs-lookup"><span data-stu-id="066d0-136">List item 1</span></span>
- <span data-ttu-id="066d0-137">Luettelokohde 2</span><span class="sxs-lookup"><span data-stu-id="066d0-137">List item 2</span></span>
- <span data-ttu-id="066d0-138">Luettelokohde 3</span><span class="sxs-lookup"><span data-stu-id="066d0-138">List item 3</span></span>

<span data-ttu-id="066d0-139">Voit luoda luettelon toisen luettelon sisälle sisentämällä aliluettelon kohteet.</span><span class="sxs-lookup"><span data-stu-id="066d0-139">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="066d0-140">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="066d0-140">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="066d0-141">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-141">will be rendered as:</span></span>

- <span data-ttu-id="066d0-142">Luettelokohde 1</span><span class="sxs-lookup"><span data-stu-id="066d0-142">List item 1</span></span>
  - <span data-ttu-id="066d0-143">Luettelokohde A</span><span class="sxs-lookup"><span data-stu-id="066d0-143">List item A</span></span>
  - <span data-ttu-id="066d0-144">Luettelokohde B</span><span class="sxs-lookup"><span data-stu-id="066d0-144">List item B</span></span>
- <span data-ttu-id="066d0-145">Luettelokohde 2</span><span class="sxs-lookup"><span data-stu-id="066d0-145">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="066d0-146">Järjestetty luettelo</span><span class="sxs-lookup"><span data-stu-id="066d0-146">Ordered list</span></span>

<span data-ttu-id="066d0-147">Voit muotoilla järjestetyn/asteittaisen luettelon käyttämällä vastaavia numeroita.</span><span class="sxs-lookup"><span data-stu-id="066d0-147">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="066d0-148">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="066d0-148">For example, the following Markdown:</span></span>

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

<span data-ttu-id="066d0-149">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-149">will be rendered as:</span></span>

1. <span data-ttu-id="066d0-150">Ensimmäinen ohje</span><span class="sxs-lookup"><span data-stu-id="066d0-150">First instruction</span></span>
2. <span data-ttu-id="066d0-151">Toinen ohje</span><span class="sxs-lookup"><span data-stu-id="066d0-151">Second instruction</span></span>
3. <span data-ttu-id="066d0-152">Kolmas ohje</span><span class="sxs-lookup"><span data-stu-id="066d0-152">Third instruction</span></span>

<span data-ttu-id="066d0-153">Voit luoda luettelon toisen luettelon sisälle sisentämällä aliluettelon kohteet.</span><span class="sxs-lookup"><span data-stu-id="066d0-153">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="066d0-154">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="066d0-154">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

<span data-ttu-id="066d0-155">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-155">will be rendered as:</span></span>

1. <span data-ttu-id="066d0-156">Ensimmäinen ohje</span><span class="sxs-lookup"><span data-stu-id="066d0-156">First instruction</span></span>
   1. <span data-ttu-id="066d0-157">Alaohje</span><span class="sxs-lookup"><span data-stu-id="066d0-157">Sub-instruction</span></span>
   2. <span data-ttu-id="066d0-158">Alaohje</span><span class="sxs-lookup"><span data-stu-id="066d0-158">Sub-instruction</span></span>
2. <span data-ttu-id="066d0-159">Toinen ohje</span><span class="sxs-lookup"><span data-stu-id="066d0-159">Second instruction</span></span>

<span data-ttu-id="066d0-160">Huomaa, että lukua 1</span><span class="sxs-lookup"><span data-stu-id="066d0-160">Note that we use '1.'</span></span> <span data-ttu-id="066d0-161">käytetään jokaisessa kohdassa.</span><span class="sxs-lookup"><span data-stu-id="066d0-161">for all entries.</span></span> <span data-ttu-id="066d0-162">Se tekee muutosten tarkistamisesta helpompaa, kun myöhemmissä päivityksessä lisätään tai poistetaan vaiheita.</span><span class="sxs-lookup"><span data-stu-id="066d0-162">It makes diffs easier to review when later updates include new steps or remove existing steps.</span></span>

### <a name="tables"></a><span data-ttu-id="066d0-163">taulukoilla</span><span class="sxs-lookup"><span data-stu-id="066d0-163">Tables</span></span>

<span data-ttu-id="066d0-164">Taulukot eivät kuulu Markdownin ydinkokonaisuuteen, mutta GFM tukee niitä.</span><span class="sxs-lookup"><span data-stu-id="066d0-164">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="066d0-165">Voit luoda taulukoita käyttämällä pystyviivaa (|) ja tavuviivaa (-).</span><span class="sxs-lookup"><span data-stu-id="066d0-165">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="066d0-166">Tavuviivat luovat sarakkeen otsikon ja pystyviivat erottavat sarakkeet toisistaan.</span><span class="sxs-lookup"><span data-stu-id="066d0-166">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="066d0-167">Lisää tyhjä rivi taulukon eteen, niin se hahmonnetaan oikein.</span><span class="sxs-lookup"><span data-stu-id="066d0-167">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="066d0-168">Esimerkiksi seuraava Markdown:</span><span class="sxs-lookup"><span data-stu-id="066d0-168">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="066d0-169">hahmonnetaan seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-169">will be rendered as:</span></span>

| <span data-ttu-id="066d0-170">Pidä</span><span class="sxs-lookup"><span data-stu-id="066d0-170">Fun</span></span>                  | <span data-ttu-id="066d0-171">hauskaa</span><span class="sxs-lookup"><span data-stu-id="066d0-171">With</span></span>                 | <span data-ttu-id="066d0-172">taulukoilla</span><span class="sxs-lookup"><span data-stu-id="066d0-172">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="066d0-173">vasemmalle tasattu sarake</span><span class="sxs-lookup"><span data-stu-id="066d0-173">left-aligned column</span></span>  | <span data-ttu-id="066d0-174">oikealle tasattu sarake</span><span class="sxs-lookup"><span data-stu-id="066d0-174">right-aligned column</span></span> | <span data-ttu-id="066d0-175">keskitetty sarake</span><span class="sxs-lookup"><span data-stu-id="066d0-175">centered column</span></span> |
| <span data-ttu-id="066d0-176">100 €</span><span class="sxs-lookup"><span data-stu-id="066d0-176">$100</span></span>                 | <span data-ttu-id="066d0-177">100 €</span><span class="sxs-lookup"><span data-stu-id="066d0-177">$100</span></span>                 | <span data-ttu-id="066d0-178">100 €</span><span class="sxs-lookup"><span data-stu-id="066d0-178">$100</span></span>            |
| <span data-ttu-id="066d0-179">10 €</span><span class="sxs-lookup"><span data-stu-id="066d0-179">$10</span></span>                  | <span data-ttu-id="066d0-180">10 €</span><span class="sxs-lookup"><span data-stu-id="066d0-180">$10</span></span>                  | <span data-ttu-id="066d0-181">10 €</span><span class="sxs-lookup"><span data-stu-id="066d0-181">$10</span></span>             |
| <span data-ttu-id="066d0-182">1 €</span><span class="sxs-lookup"><span data-stu-id="066d0-182">$1</span></span>                   | <span data-ttu-id="066d0-183">1 €</span><span class="sxs-lookup"><span data-stu-id="066d0-183">$1</span></span>                   | <span data-ttu-id="066d0-184">1 €</span><span class="sxs-lookup"><span data-stu-id="066d0-184">$1</span></span>              |

<span data-ttu-id="066d0-185">Jos haluat lisätietoja taulukoiden luomisesta, katso:</span><span class="sxs-lookup"><span data-stu-id="066d0-185">For more information on creating tables, see:</span></span>

- <span data-ttu-id="066d0-186">Markdigin [taulukon rivitysominaisuus](#table-wrapping), joka voi auttaa leveiden taulukoiden muotoilussa.</span><span class="sxs-lookup"><span data-stu-id="066d0-186">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="066d0-187">GitHubin [tietojen järjestäminen taulukoiden avulla](https://help.github.com/articles/organizing-information-with-tables/).</span><span class="sxs-lookup"><span data-stu-id="066d0-187">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="066d0-188">[Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) -verkkosovellus.</span><span class="sxs-lookup"><span data-stu-id="066d0-188">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="066d0-189">[Adam Pritchardin Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span><span class="sxs-lookup"><span data-stu-id="066d0-189">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="066d0-190">[Michel Fortinin Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="066d0-190">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="066d0-191">[HTML-taulukoiden muuntaminen Markdowniksi](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="066d0-191">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="066d0-192">Linkit</span><span class="sxs-lookup"><span data-stu-id="066d0-192">Links</span></span>

<span data-ttu-id="066d0-193">Tekstin sisäisen linkin Markdown-syntaksi koostuu `[link text]`-osasta, joka on hyperlinkitettävä teksti, ja `(file-name.md)`-osasta, joka on linkitettävän URL-osoitteen tai tiedoston nimi:</span><span class="sxs-lookup"><span data-stu-id="066d0-193">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="066d0-194">Jos haluat lisätietoja linkittämisestä, katso:</span><span class="sxs-lookup"><span data-stu-id="066d0-194">For more information on linking, see:</span></span>

- <span data-ttu-id="066d0-195">[Markdown- syntaksioppaasta](https://daringfireball.net/projects/markdown/syntax#link) tietoja Markdownin peruslinkitystuesta.</span><span class="sxs-lookup"><span data-stu-id="066d0-195">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="066d0-196">Tämän oppaan [Linkit](how-to-write-links.md)-osasta tietoja Markdigin sisältämästä lisäsyntaksista linkittämistä varten.</span><span class="sxs-lookup"><span data-stu-id="066d0-196">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="066d0-197">Koodikatkelmat</span><span class="sxs-lookup"><span data-stu-id="066d0-197">Code snippets</span></span>

<span data-ttu-id="066d0-198">Markdown tukee koodikatkelmien sijoittamista lauseiden sisään sekä lauseiden väliin erillisinä aidattuina lohkoina.</span><span class="sxs-lookup"><span data-stu-id="066d0-198">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="066d0-199">Lisätietoja:</span><span class="sxs-lookup"><span data-stu-id="066d0-199">For details, see:</span></span>

- [<span data-ttu-id="066d0-200">Markdownin oma koodilohkojen tuki</span><span class="sxs-lookup"><span data-stu-id="066d0-200">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="066d0-201">GFM:n tuki koodin aitaamiselle ja syntaksin korostukselle</span><span class="sxs-lookup"><span data-stu-id="066d0-201">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="066d0-202">Aidatut koodilohkot ovat helppo tapa mahdollistaa syntaksin korostus koodikatkelmissa.</span><span class="sxs-lookup"><span data-stu-id="066d0-202">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="066d0-203">Aidattujen koodilohkojen yleinen muotoilu on:</span><span class="sxs-lookup"><span data-stu-id="066d0-203">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="066d0-204">Ensimmäisten kolmen gravis-merkin (\`) jälkeen tuleva alias määrittää käytettävän syntaksin korostuksen.</span><span class="sxs-lookup"><span data-stu-id="066d0-204">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="066d0-205">Seuraavassa on luettelo Docs-sisällössä yleisesti käytetyistä ohjelmointikielistä ja vastaavasta selitteestä:</span><span class="sxs-lookup"><span data-stu-id="066d0-205">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="066d0-206">Näille kielille on kutsumanimituki, ja useimmille on käytössä kielen korostus.</span><span class="sxs-lookup"><span data-stu-id="066d0-206">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="066d0-207">Nimi</span><span class="sxs-lookup"><span data-stu-id="066d0-207">Name</span></span>|<span data-ttu-id="066d0-208">Markdown-selite</span><span class="sxs-lookup"><span data-stu-id="066d0-208">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="066d0-209">.NET Console</span><span class="sxs-lookup"><span data-stu-id="066d0-209">.NET Console</span></span>|<span data-ttu-id="066d0-210">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="066d0-210">dotnetcli</span></span>|
|<span data-ttu-id="066d0-211">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="066d0-211">ASP.NET (C#)</span></span>|<span data-ttu-id="066d0-212">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="066d0-212">aspx-csharp</span></span>|
|<span data-ttu-id="066d0-213">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="066d0-213">ASP.NET (VB)</span></span>|<span data-ttu-id="066d0-214">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="066d0-214">aspx-vb</span></span>|
|<span data-ttu-id="066d0-215">AzCopy</span><span class="sxs-lookup"><span data-stu-id="066d0-215">AzCopy</span></span>|<span data-ttu-id="066d0-216">AzCopy</span><span class="sxs-lookup"><span data-stu-id="066d0-216">azcopy</span></span>|
|<span data-ttu-id="066d0-217">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="066d0-217">Azure CLI</span></span>|<span data-ttu-id="066d0-218">azurecli</span><span class="sxs-lookup"><span data-stu-id="066d0-218">azurecli</span></span>|
|<span data-ttu-id="066d0-219">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="066d0-219">Azure PowerShell</span></span>|<span data-ttu-id="066d0-220">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="066d0-220">azurepowershell</span></span>|
|<span data-ttu-id="066d0-221">C++</span><span class="sxs-lookup"><span data-stu-id="066d0-221">C++</span></span>|<span data-ttu-id="066d0-222">cpp</span><span class="sxs-lookup"><span data-stu-id="066d0-222">cpp</span></span>|
|<span data-ttu-id="066d0-223">C++/CX</span><span class="sxs-lookup"><span data-stu-id="066d0-223">C++/CX</span></span>|<span data-ttu-id="066d0-224">cppcx</span><span class="sxs-lookup"><span data-stu-id="066d0-224">cppcx</span></span>|
|<span data-ttu-id="066d0-225">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="066d0-225">C++/WinRT</span></span>|<span data-ttu-id="066d0-226">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="066d0-226">cppwinrt</span></span>|
|<span data-ttu-id="066d0-227">C#</span><span class="sxs-lookup"><span data-stu-id="066d0-227">C#</span></span>|<span data-ttu-id="066d0-228">csharp</span><span class="sxs-lookup"><span data-stu-id="066d0-228">csharp</span></span>|
|<span data-ttu-id="066d0-229">C# selaimessa</span><span class="sxs-lookup"><span data-stu-id="066d0-229">C# in browser</span></span>|<span data-ttu-id="066d0-230">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="066d0-230">csharp-interactive</span></span>|
|<span data-ttu-id="066d0-231">Console</span><span class="sxs-lookup"><span data-stu-id="066d0-231">Console</span></span>|<span data-ttu-id="066d0-232">console</span><span class="sxs-lookup"><span data-stu-id="066d0-232">console</span></span>|
|<span data-ttu-id="066d0-233">CSHTML</span><span class="sxs-lookup"><span data-stu-id="066d0-233">CSHTML</span></span>|<span data-ttu-id="066d0-234">cshtml</span><span class="sxs-lookup"><span data-stu-id="066d0-234">cshtml</span></span>|
|<span data-ttu-id="066d0-235">DAX</span><span class="sxs-lookup"><span data-stu-id="066d0-235">DAX</span></span>|<span data-ttu-id="066d0-236">dax</span><span class="sxs-lookup"><span data-stu-id="066d0-236">dax</span></span>|
|<span data-ttu-id="066d0-237">F#</span><span class="sxs-lookup"><span data-stu-id="066d0-237">F#</span></span>|<span data-ttu-id="066d0-238">fsharp</span><span class="sxs-lookup"><span data-stu-id="066d0-238">fsharp</span></span>|
|<span data-ttu-id="066d0-239">Go</span><span class="sxs-lookup"><span data-stu-id="066d0-239">Go</span></span>|<span data-ttu-id="066d0-240">go</span><span class="sxs-lookup"><span data-stu-id="066d0-240">go</span></span>|
|<span data-ttu-id="066d0-241">HTML</span><span class="sxs-lookup"><span data-stu-id="066d0-241">HTML</span></span>|<span data-ttu-id="066d0-242">html</span><span class="sxs-lookup"><span data-stu-id="066d0-242">html</span></span>|
|<span data-ttu-id="066d0-243">HTTP</span><span class="sxs-lookup"><span data-stu-id="066d0-243">HTTP</span></span>|<span data-ttu-id="066d0-244">http</span><span class="sxs-lookup"><span data-stu-id="066d0-244">http</span></span>|
|<span data-ttu-id="066d0-245">Java</span><span class="sxs-lookup"><span data-stu-id="066d0-245">Java</span></span>|<span data-ttu-id="066d0-246">java</span><span class="sxs-lookup"><span data-stu-id="066d0-246">java</span></span>|
|<span data-ttu-id="066d0-247">JavaScript</span><span class="sxs-lookup"><span data-stu-id="066d0-247">JavaScript</span></span>|<span data-ttu-id="066d0-248">javascript</span><span class="sxs-lookup"><span data-stu-id="066d0-248">javascript</span></span>|
|<span data-ttu-id="066d0-249">JSON</span><span class="sxs-lookup"><span data-stu-id="066d0-249">JSON</span></span>|<span data-ttu-id="066d0-250">json</span><span class="sxs-lookup"><span data-stu-id="066d0-250">json</span></span>|
|<span data-ttu-id="066d0-251">Markdown</span><span class="sxs-lookup"><span data-stu-id="066d0-251">Markdown</span></span>|<span data-ttu-id="066d0-252">md</span><span class="sxs-lookup"><span data-stu-id="066d0-252">md</span></span>|
|<span data-ttu-id="066d0-253">NodeJS</span><span class="sxs-lookup"><span data-stu-id="066d0-253">NodeJS</span></span>|<span data-ttu-id="066d0-254">nodejs</span><span class="sxs-lookup"><span data-stu-id="066d0-254">nodejs</span></span>|
|<span data-ttu-id="066d0-255">Objective-C</span><span class="sxs-lookup"><span data-stu-id="066d0-255">Objective-C</span></span>|<span data-ttu-id="066d0-256">objc</span><span class="sxs-lookup"><span data-stu-id="066d0-256">objc</span></span>|
|<span data-ttu-id="066d0-257">OData</span><span class="sxs-lookup"><span data-stu-id="066d0-257">OData</span></span>|<span data-ttu-id="066d0-258">odata</span><span class="sxs-lookup"><span data-stu-id="066d0-258">odata</span></span>|
|<span data-ttu-id="066d0-259">PHP</span><span class="sxs-lookup"><span data-stu-id="066d0-259">PHP</span></span>|<span data-ttu-id="066d0-260">php</span><span class="sxs-lookup"><span data-stu-id="066d0-260">php</span></span>|
|<span data-ttu-id="066d0-261">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="066d0-261">Power Apps Formula</span></span>|<span data-ttu-id="066d0-262">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="066d0-262">powerappsfl</span></span>|
|<span data-ttu-id="066d0-263">PowerShell</span><span class="sxs-lookup"><span data-stu-id="066d0-263">PowerShell</span></span>|<span data-ttu-id="066d0-264">powershell</span><span class="sxs-lookup"><span data-stu-id="066d0-264">powershell</span></span>|
|<span data-ttu-id="066d0-265">Python</span><span class="sxs-lookup"><span data-stu-id="066d0-265">Python</span></span>|<span data-ttu-id="066d0-266">python</span><span class="sxs-lookup"><span data-stu-id="066d0-266">python</span></span>|
|<span data-ttu-id="066d0-267">Q#</span><span class="sxs-lookup"><span data-stu-id="066d0-267">Q#</span></span>|<span data-ttu-id="066d0-268">qsharp</span><span class="sxs-lookup"><span data-stu-id="066d0-268">qsharp</span></span>|
|<span data-ttu-id="066d0-269">R</span><span class="sxs-lookup"><span data-stu-id="066d0-269">R</span></span>|<span data-ttu-id="066d0-270">r</span><span class="sxs-lookup"><span data-stu-id="066d0-270">r</span></span>|
|<span data-ttu-id="066d0-271">Ruby</span><span class="sxs-lookup"><span data-stu-id="066d0-271">Ruby</span></span>|<span data-ttu-id="066d0-272">ruby</span><span class="sxs-lookup"><span data-stu-id="066d0-272">ruby</span></span>|
|<span data-ttu-id="066d0-273">SQL</span><span class="sxs-lookup"><span data-stu-id="066d0-273">SQL</span></span>|<span data-ttu-id="066d0-274">sql</span><span class="sxs-lookup"><span data-stu-id="066d0-274">sql</span></span>|
|<span data-ttu-id="066d0-275">Swift</span><span class="sxs-lookup"><span data-stu-id="066d0-275">Swift</span></span>|<span data-ttu-id="066d0-276">swift</span><span class="sxs-lookup"><span data-stu-id="066d0-276">swift</span></span>|
|<span data-ttu-id="066d0-277">TypeScript</span><span class="sxs-lookup"><span data-stu-id="066d0-277">TypeScript</span></span>|<span data-ttu-id="066d0-278">typescript</span><span class="sxs-lookup"><span data-stu-id="066d0-278">typescript</span></span>|
|<span data-ttu-id="066d0-279">VB</span><span class="sxs-lookup"><span data-stu-id="066d0-279">VB</span></span>|<span data-ttu-id="066d0-280">vb</span><span class="sxs-lookup"><span data-stu-id="066d0-280">vb</span></span>|
|<span data-ttu-id="066d0-281">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="066d0-281">VSTS CLI</span></span>|<span data-ttu-id="066d0-282">vstscli</span><span class="sxs-lookup"><span data-stu-id="066d0-282">vstscli</span></span>|
|<span data-ttu-id="066d0-283">XAML</span><span class="sxs-lookup"><span data-stu-id="066d0-283">XAML</span></span>|<span data-ttu-id="066d0-284">xaml</span><span class="sxs-lookup"><span data-stu-id="066d0-284">xaml</span></span>|
|<span data-ttu-id="066d0-285">XML</span><span class="sxs-lookup"><span data-stu-id="066d0-285">XML</span></span>|<span data-ttu-id="066d0-286">xml</span><span class="sxs-lookup"><span data-stu-id="066d0-286">xml</span></span>|

<span data-ttu-id="066d0-287">Nimi `csharp-interactive` määrittää C#-kielen sekä mahdollisuuden suorittaa esimerkit selaimesta.</span><span class="sxs-lookup"><span data-stu-id="066d0-287">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="066d0-288">Nämä katkelmat on käännetty ja suoritettu Docker-säilössä, ja ohjelman suorituksen tulokset näkyvät käyttäjän selainikkunassa.</span><span class="sxs-lookup"><span data-stu-id="066d0-288">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

#### <a name="example-c"></a><span data-ttu-id="066d0-289">Esimerkki: C\#</span><span class="sxs-lookup"><span data-stu-id="066d0-289">Example: C\#</span></span>

<span data-ttu-id="066d0-290">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="066d0-290">__Markdown__</span></span>

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

<span data-ttu-id="066d0-291">__Hahmonnus__</span><span class="sxs-lookup"><span data-stu-id="066d0-291">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="066d0-292">Esimerkki: SQL</span><span class="sxs-lookup"><span data-stu-id="066d0-292">Example: SQL</span></span>

<span data-ttu-id="066d0-293">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="066d0-293">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="066d0-294">__Hahmonnus__</span><span class="sxs-lookup"><span data-stu-id="066d0-294">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="066d0-295">OPS:n mukautetut Markdown-laajennukset</span><span class="sxs-lookup"><span data-stu-id="066d0-295">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="066d0-296">Open Publishing Services (OPS) käyttää Markdig Parser for Markdownia, joka on laajasti yhteensopiva GitHub Flavored Markdownin (GFM) kanssa.</span><span class="sxs-lookup"><span data-stu-id="066d0-296">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="066d0-297">Markdig lisää joitakin toimintoja Markdown-laajennusten kautta.</span><span class="sxs-lookup"><span data-stu-id="066d0-297">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="066d0-298">Tähän oppaaseen onkin sisällytetty valittuja artikkeleita OPS-oppaasta.</span><span class="sxs-lookup"><span data-stu-id="066d0-298">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="066d0-299">(Katso sisällysluettelosta esimerkiksi kohdat Markdig ja Markdown-laajennukset ja Koodikatkelmat.)</span><span class="sxs-lookup"><span data-stu-id="066d0-299">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="066d0-300">Docs.artikkelit käyttävät GFM:ää suurimpaan osaan artikkeleiden muotoilusta, esimerkiksi kappaleiden, luettelojen ja otsikkojen muotoiluun.</span><span class="sxs-lookup"><span data-stu-id="066d0-300">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="066d0-301">Monipuolisempaa muotoilua artikkeleihin saadaan käyttämällä Markdig-ominaisuuksia, kuten:</span><span class="sxs-lookup"><span data-stu-id="066d0-301">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="066d0-302">Huomautuslohkot</span><span class="sxs-lookup"><span data-stu-id="066d0-302">Note blocks</span></span>
- <span data-ttu-id="066d0-303">Sisällytykset</span><span class="sxs-lookup"><span data-stu-id="066d0-303">Includes</span></span>
- <span data-ttu-id="066d0-304">Valitsimet</span><span class="sxs-lookup"><span data-stu-id="066d0-304">Selectors</span></span>
- <span data-ttu-id="066d0-305">Upotetut videot</span><span class="sxs-lookup"><span data-stu-id="066d0-305">Embedded videos</span></span>
- <span data-ttu-id="066d0-306">Koodikatkelmat/-näytteet</span><span class="sxs-lookup"><span data-stu-id="066d0-306">Code snippets/samples</span></span>

<span data-ttu-id="066d0-307">Täydellisen luettelon näet sisällysluettelon kohdista Markdig ja Markdown-laajennukset ja Koodikatkelmat.</span><span class="sxs-lookup"><span data-stu-id="066d0-307">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="066d0-308">Huomautuslohkot</span><span class="sxs-lookup"><span data-stu-id="066d0-308">Note blocks</span></span>

<span data-ttu-id="066d0-309">Voit kiinnittää käyttäjän huomion tiettyyn sisältöön valitsemalla neljästä huomautuslohkotyypistä:</span><span class="sxs-lookup"><span data-stu-id="066d0-309">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="066d0-310">HUOMAUTUS</span><span class="sxs-lookup"><span data-stu-id="066d0-310">NOTE</span></span>
- <span data-ttu-id="066d0-311">VAROITUS</span><span class="sxs-lookup"><span data-stu-id="066d0-311">WARNING</span></span>
- <span data-ttu-id="066d0-312">VIHJE</span><span class="sxs-lookup"><span data-stu-id="066d0-312">TIP</span></span>
- <span data-ttu-id="066d0-313">TÄRKEÄ</span><span class="sxs-lookup"><span data-stu-id="066d0-313">IMPORTANT</span></span>

<span data-ttu-id="066d0-314">Huomautuslohkoja tulisi käyttää säästeliäästi, koska ne voivat olla häiritsevä.</span><span class="sxs-lookup"><span data-stu-id="066d0-314">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="066d0-315">Vaikka huomautuslohkot tukevat koodilohkoja, kuvia, luetteloja ja linkkejä, pyri pitämään ne yksinkertaisina ja selkeinä.</span><span class="sxs-lookup"><span data-stu-id="066d0-315">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

<span data-ttu-id="066d0-316">Esimerkkejä:</span><span class="sxs-lookup"><span data-stu-id="066d0-316">Examples:</span></span>

```markdown
> [!NOTE]
> This is a NOTE

> [!WARNING]
> This is a WARNING

> [!TIP]
> This is a TIP

> [!IMPORTANT]
> This is IMPORTANT
```

<span data-ttu-id="066d0-317">Nämä hahmontuvat seuraavasti:</span><span class="sxs-lookup"><span data-stu-id="066d0-317">These render as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="066d0-318">Tämä on HUOMAUTUS</span><span class="sxs-lookup"><span data-stu-id="066d0-318">This is a NOTE</span></span>

> [!WARNING]
> <span data-ttu-id="066d0-319">Tämä on VAROITUS</span><span class="sxs-lookup"><span data-stu-id="066d0-319">This is a WARNING</span></span>

> [!TIP]
> <span data-ttu-id="066d0-320">Tämä on VINKKI</span><span class="sxs-lookup"><span data-stu-id="066d0-320">This is a TIP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="066d0-321">Tämä on TÄRKEÄÄ</span><span class="sxs-lookup"><span data-stu-id="066d0-321">This is IMPORTANT</span></span>

### <a name="includes"></a><span data-ttu-id="066d0-322">Sisällytykset</span><span class="sxs-lookup"><span data-stu-id="066d0-322">Includes</span></span>

<span data-ttu-id="066d0-323">Kun haluat lisätä artikkelitiedostoihin uudelleenkäytettävää tekstiä tai kuvatiedostoja, voit sisällyttää tiedoston käyttämällä viittausta Markdigin tiedostojen sisällytysominaisuuden avulla.</span><span class="sxs-lookup"><span data-stu-id="066d0-323">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="066d0-324">Tämä ominaisuus ohjaa OPS:n sisällyttämään tiedoston artikkelitiedostoon artikkelin muodostamisen aikana, jolloin siitä tulee julkaistun artikkelin osa.</span><span class="sxs-lookup"><span data-stu-id="066d0-324">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="066d0-325">Sisällön uudelleenkäyttämisen avuksi on kolme erityyppistä sisällytystä:</span><span class="sxs-lookup"><span data-stu-id="066d0-325">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="066d0-326">Tekstin sisäinen: Käytä yleinen tekstikatkelma uudelleen toisen lauseen sisällä.</span><span class="sxs-lookup"><span data-stu-id="066d0-326">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="066d0-327">Lohko: Käytä kokonainen Markdown-tiedosto lohkona artikkelin osassa.</span><span class="sxs-lookup"><span data-stu-id="066d0-327">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="066d0-328">Kuva: Kuvat sisällytetään Docsissa tavallisesti näin.</span><span class="sxs-lookup"><span data-stu-id="066d0-328">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="066d0-329">Tekstin sisäinen tai lohkosisällytys on vain yksinkertainen Markdown-tiedosto (.md).</span><span class="sxs-lookup"><span data-stu-id="066d0-329">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="066d0-330">Se voi sisältää minkä tahansa kelvollisen Markdownin.</span><span class="sxs-lookup"><span data-stu-id="066d0-330">It can contain any valid Markdown.</span></span> <span data-ttu-id="066d0-331">Kaikki sisällytettävät Markdown-tiedostot tulisi sijoittaa [yhteiseen `/includes`-alihakemistoon](git-github-fundamentals.md#includes-subdirectory), säilön pääkansioon.</span><span class="sxs-lookup"><span data-stu-id="066d0-331">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="066d0-332">Kun artikkeli julkaistaan, sisällytetty tiedosto lisätään siihen saumattomasti.</span><span class="sxs-lookup"><span data-stu-id="066d0-332">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="066d0-333">Tässä on sisällytyksien vaatimukset ja huomioitavat seikat:</span><span class="sxs-lookup"><span data-stu-id="066d0-333">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="066d0-334">Käytä sisällytyksiä, kun haluat käyttää samaa tekstiä useassa artikkelissa.</span><span class="sxs-lookup"><span data-stu-id="066d0-334">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="066d0-335">Käytä lohkosisällytyksiä, kun sisältöä on merkittävä määrä – yksi tai kaksi kappaletta, yhteinen toimenpide tai yhteinen osa.</span><span class="sxs-lookup"><span data-stu-id="066d0-335">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="066d0-336">Älä käytä niitä mihinkään virkettä lyhyempään.</span><span class="sxs-lookup"><span data-stu-id="066d0-336">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="066d0-337">Sisällytyksiä ei hahmonneta GitHubissa artikkelin hahmonnusnäkymässä, koska ne käyttävät Markdig-laajennuksia.</span><span class="sxs-lookup"><span data-stu-id="066d0-337">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="066d0-338">Ne hahmonnetaan vasta julkaisemisen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="066d0-338">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="066d0-339">Varmista, että kaikki sisällytyksessä oleva teksti on kirjoitettu käyttäen kokonaisia virkkeitä ja ettei sen ymmärrettävyys perustu sellaiseen alkuperäisessä artikkelissa olevaan tekstiin, joka on lainattavan kohdan edellä tai jälkeen.</span><span class="sxs-lookup"><span data-stu-id="066d0-339">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="066d0-340">Jos tätä ohjetta ei noudateta, artikkeliin syntyy käännöskelvoton merkkijono, joka pilaa lokalisoidun käyttökokemuksen.</span><span class="sxs-lookup"><span data-stu-id="066d0-340">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="066d0-341">Älä upota sisällytyksiä toisiin sisällytyksiin.</span><span class="sxs-lookup"><span data-stu-id="066d0-341">Don't embed includes within other includes.</span></span> <span data-ttu-id="066d0-342">Niitä ei tueta.</span><span class="sxs-lookup"><span data-stu-id="066d0-342">They are not supported.</span></span>
- <span data-ttu-id="066d0-343">Sijoita mediatiedostot sisällytyksen alihakemistoon erityisesti liittyvään mediakansioon, esimerkiksi `<repo>`/sisällytykset/media-kansioon.</span><span class="sxs-lookup"><span data-stu-id="066d0-343">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="066d0-344">Mediakansion pääkansio ei saa sisältää kuvia.</span><span class="sxs-lookup"><span data-stu-id="066d0-344">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="066d0-345">Jos sisällytyksessä ei ole kuvia, vastaavaa mediahakemistoa ei tarvita.</span><span class="sxs-lookup"><span data-stu-id="066d0-345">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="066d0-346">Samoin kuin tavallisten artikkelien tapauksessa, älä jaa mediaa sisällytyskansioiden välillä.</span><span class="sxs-lookup"><span data-stu-id="066d0-346">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="066d0-347">Käytä jokaiseen sisällytykseen ja artikkeliin erillistä tiedostoa, jolla on yksilöllinen nimi.</span><span class="sxs-lookup"><span data-stu-id="066d0-347">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="066d0-348">Tallenna mediatiedosto siihen mediakansioon, joka liittyy sisällytykseen.</span><span class="sxs-lookup"><span data-stu-id="066d0-348">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="066d0-349">Älä käytä sisällytystä artikkelin ainoana sisältönä.</span><span class="sxs-lookup"><span data-stu-id="066d0-349">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="066d0-350">Sisällytysten on tarkoitus lisätä sisältöä varsinaiseen artikkeliin.</span><span class="sxs-lookup"><span data-stu-id="066d0-350">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

<span data-ttu-id="066d0-351">Esimerkki:</span><span class="sxs-lookup"><span data-stu-id="066d0-351">Example:</span></span>

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a><span data-ttu-id="066d0-352">Valitsimet</span><span class="sxs-lookup"><span data-stu-id="066d0-352">Selectors</span></span>

<span data-ttu-id="066d0-353">Käytä valitsimia teknisissä artikkeleissa, kun kirjoitat samasta artikkelista useampaa versiota. Valitsimien avulla voit ottaa huomioon eri teknologioista ja käyttöympäristöistä johtuvat erot.</span><span class="sxs-lookup"><span data-stu-id="066d0-353">Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="066d0-354">Tämä koskee useimmiten kehittäjille suunnattua mobiilikäyttöympäristöä käsittelevää sisältöä.</span><span class="sxs-lookup"><span data-stu-id="066d0-354">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="066d0-355">Markdigissä on tällä hetkellä kaksi erityyppistä valitsinta: yksittäinen valitsin ja monivalitsin.</span><span class="sxs-lookup"><span data-stu-id="066d0-355">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="066d0-356">Koska sama valitsin-Markdown sijoitetaan kaikkiin valittuihin artikkeleihin, artikkelin valitsin on suositeltavaa sijoittaa sisällytykseen.</span><span class="sxs-lookup"><span data-stu-id="066d0-356">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="066d0-357">Tällöin voit viitata sisällytykseen kaikissa niissä artikkeleissa, jotka käyttävät samaa valitsinta.</span><span class="sxs-lookup"><span data-stu-id="066d0-357">Then you can reference that include in all your articles that use the same selector.</span></span>

<span data-ttu-id="066d0-358">Seuraavassa on esimerkki valitsimesta:</span><span class="sxs-lookup"><span data-stu-id="066d0-358">The following shows an example selector:</span></span>

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

<span data-ttu-id="066d0-359">Näet aidon esimerkin valitsimista [Azure-ohjeissa](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="066d0-359">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="code-includes"></a><span data-ttu-id="066d0-360">Koodin sisällytys</span><span class="sxs-lookup"><span data-stu-id="066d0-360">Code includes</span></span>

<span data-ttu-id="066d0-361">Markdig tukee koodin edistynyttä sisällytystä artikkeleihin koodikatkelmalaajennuksen avulla.</span><span class="sxs-lookup"><span data-stu-id="066d0-361">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="066d0-362">Se käyttää edistynyttä hahmonnusta, joka perustuu erilaisiin GFM-ominaisuuksiin, kuten ohjelmointikielen valintaan ja syntaksin väritykseen, sekä ominaisuuksiin, kuten:</span><span class="sxs-lookup"><span data-stu-id="066d0-362">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="066d0-363">Keskitettyjen koodinäytteiden/-katkelmien sisällyttäminen ulkoisesta säilöstä.</span><span class="sxs-lookup"><span data-stu-id="066d0-363">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="066d0-364">Välilehtiin jaettu käyttöliittymä, jolloin voidaan näyttää koodinäytteiden useita versioita eri kielillä.</span><span class="sxs-lookup"><span data-stu-id="066d0-364">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="066d0-365">Gotchat ja vianmääritys</span><span class="sxs-lookup"><span data-stu-id="066d0-365">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="066d0-366">Alt-teksti</span><span class="sxs-lookup"><span data-stu-id="066d0-366">Alt text</span></span>

<span data-ttu-id="066d0-367">Alaviivoja sisältävää Alt-tekstiä ei hahmonneta oikein.</span><span class="sxs-lookup"><span data-stu-id="066d0-367">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="066d0-368">Esimerkiksi tämän käyttämisen sijaan:</span><span class="sxs-lookup"><span data-stu-id="066d0-368">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="066d0-369">Muotoile alaviivat näin:</span><span class="sxs-lookup"><span data-stu-id="066d0-369">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="066d0-370">Heittomerkit ja lainausmerkit</span><span class="sxs-lookup"><span data-stu-id="066d0-370">Apostrophes and quotation marks</span></span>

<span data-ttu-id="066d0-371">Jos kopioit tekstiä Wordista Markdown-editoriin, teksti saattaa sisältää ns. älykkäitä (kaarevia) heittomerkkejä tai lainausmerkkejä.</span><span class="sxs-lookup"><span data-stu-id="066d0-371">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="066d0-372">Nämä täytyy koodata tai muuttaa tavallisiksi heittomerkeiksi tai lainausmerkeiksi.</span><span class="sxs-lookup"><span data-stu-id="066d0-372">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="066d0-373">Muuten tekstiin päätyy julkaisuvaiheessa virheellisiä merkkejä, esim. Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="066d0-373">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="066d0-374">Seuraavassa on näiden välimerkkien älykkäiden versioiden koodaukset:</span><span class="sxs-lookup"><span data-stu-id="066d0-374">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="066d0-375">Vasen (avaava) lainausmerkki: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="066d0-375">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="066d0-376">Oikea (sulkeva) lainausmerkki: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="066d0-376">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="066d0-377">Oikea (sulkeva) puolilainausmerkki tai heittomerkki: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="066d0-377">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="066d0-378">Vasen (avaava) puolilainausmerkki (käytetään harvoin): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="066d0-378">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="066d0-379">Kulmasulkeet</span><span class="sxs-lookup"><span data-stu-id="066d0-379">Angle brackets</span></span>

<span data-ttu-id="066d0-380">Kulmasulkeita käytetään tavallisesti osoittamaan paikkamerkkiä.</span><span class="sxs-lookup"><span data-stu-id="066d0-380">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="066d0-381">Kun teet näin tekstin sisällä (ei koodissa), kulmasulkeet on koodattava.</span><span class="sxs-lookup"><span data-stu-id="066d0-381">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="066d0-382">Muuten Markdown tulkitsee ne HTML-tunnisteiksi.</span><span class="sxs-lookup"><span data-stu-id="066d0-382">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="066d0-383">Koodaa `<script name>` esimerkiksi näin: `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="066d0-383">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="066d0-384">Katso myös:</span><span class="sxs-lookup"><span data-stu-id="066d0-384">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="066d0-385">Markdown-resursseja</span><span class="sxs-lookup"><span data-stu-id="066d0-385">Markdown resources</span></span>

- [<span data-ttu-id="066d0-386">Johdatus Markdowniin</span><span class="sxs-lookup"><span data-stu-id="066d0-386">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="066d0-387">Docs Markdown -pikaopas</span><span class="sxs-lookup"><span data-stu-id="066d0-387">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="066d0-388">GitHubin Markdown-perusteet</span><span class="sxs-lookup"><span data-stu-id="066d0-388">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
- [<span data-ttu-id="066d0-389">Markdown-opas</span><span class="sxs-lookup"><span data-stu-id="066d0-389">The Markdown Guide</span></span>](https://www.markdownguide.org/)
