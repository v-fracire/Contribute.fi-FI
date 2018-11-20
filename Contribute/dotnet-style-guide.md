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
# <a name="metadata-and-markdown-template-for-net-docs"></a>Metatieto- ja Markdown-malli .NET-ohjeita varten

Tämä dotnet/docs-malli sisältää esimerkkejä Markdown-syntaksista sekä ohjeita metatietojen määrittämiseen.

Kun luot Markdown-tiedostoa, kopioi liitteenä oleva malli uuteen tiedostoon, täytä metatiedot alla olevien ohjeiden mukaan ja määritä artikkelin otsikolle yllä oleva H1-otsikko.

## <a name="metadata"></a>Metatieto

Pakolliset metatiedot on annettu alla olevassa metatietolohkon esimerkissä:

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- Kaksoispisteen (:) ja metatietoelementin välissä **täytyy** olla välilyönti.
- Arvon (esimerkiksi otsikon) sisäiset kaksoispisteet rikkovat metatietojen jäsennyksen. Jos haluat käyttää kaksoispistettä otsikossa, käytä otsikon ympärillä kaksoispisteitä (esimerkiksi `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: Näkyy hakukoneiden tuloksissa. Tässä oleva otsikko ei saa olla täsmälleen sama kuin H1-otsikko, ja siinä voi olla korkeintaan 60 merkkiä.
- **description**: Yhteenveto artikkelin sisällöstä. Se näkyy yleensä haun tulossivulla, mutta se ei vaikuta hakutulosten keskinäiseen järjestykseen. Kuvauksen pituus voi olla 115–145 merkkiä välilyönnit mukaan lukien.
- **author**: Author-kentässä tulee olla artikkelin kirjoittajan **GitHub-käyttäjänimi**.
- **ms.date**: Viimeisimmän merkittävän päivityksen päivämäärä. Päivitä tämä vanhoihin artikkeleihin, jos olet tarkistanut ja päivittänyt koko artikkelin. Pieniä muutoksia, kuten kirjoitusvirheiden korjauksia, ei lasketa merkittäviksi päivityksiksi.

Jokaiseen artikkeliin kuuluu muutakin metatietoa, mutta suurin osa metatietoarvoista lisätään kansiotasolla määrittämällä ne **docfx.json**-tiedostossa.

## <a name="basic-markdown-gfm-and-special-characters"></a>Markdownin perusteet, GFM ja erikoismerkit

Voit opetella Markdownin, GFM:n (GitHub Flavored Markdown) ja OPS-kohtaisten laajennusten perustiedot yleisistä [Markdown](how-to-write-use-markdown.md)- ja [Markdownin viitetiedot](markdown-reference.md) -aiheisista artikkeleista.

Markdownissa käytetään muotoilussa erikoismerkkejä, kuten \*, \` ja \#. Jos haluat käyttää jotakin näistä merkeistä sisällössäsi, sinun on tehtävä jompi kumpi seuraavista:

- Lisätä kenoviiva erikoismerkin eteen (esimerkiksi `\*`, jos haluat merkin \*)
- Käyttää merkin [HTML-merkkikoodia](http://www.ascii.cl/htmlcodes.htm) (esimerkiksi `&#42;`, jos haluat merkin &#42;).

## <a name="file-names"></a>Tiedostonimet

Tiedostonimissä noudatetaan seuraavia sääntöjä:

* Nimessä saa olla ainoastaan pieniä kirjaimia, numeroita ja tavuviivoja.
* Ei välilyöntejä tai välimerkkejä. Erota tiedostonimessä esiintyvät sanat ja numerot toisistaan tavuviivoilla.
* Käytä selkeitä toiminnallisia verbejä, kuten develop (kehitä), buy (osta), build (luo), troubleshoot (vianmääritys). Ei -ing-sanoja.
* Ei pieniä sanoja, kuten ja, tai sekä englannin artikkelit.
* Nimissä on käytettävä Markdown-merkintätapaa ja .md-tiedostotunnistetta.
* Pidä tiedostonimet suhteellisen lyhyinä. Ne ovat osa artikkeleidesi URL-osoitteita.

## <a name="headings"></a>Otsikot

Kirjoita isolla alkukirjaimella vain otsikon ensimmäinen sana ja erisnimet. Otsikon ensimmäinen sana kirjoitetaan aina isolla alkukirjaimella.

## <a name="text-styling"></a>Tekstin muotoilu

*Kursivointi* Käytä tiedostojen, kansioiden, polkujen (erota pitkät kohteet omalle rivilleen) ja uusien termien kohdalla.

**Lihavointi** Käytä viitatessa käyttöliittymäelementteihin.

`Code` Käytä tekstin sisäiseen koodiin, kielen avainsanoihin, NuGet-pakettien nimiin, komentorivin komentoihin, tietokantataulukoihin ja sarakkeiden nimiin sekä URL-osoitteisiin, jos haluat, ettei niitä voi napsauttaa.

## <a name="links"></a>Linkit

[Linkit](how-to-write-links.md)-yleisartikkelista saat lisätietoja ankkureista, sisäisistä linkeistä, muihin asiakirjoihin osoittavista linkeistä, koodisisällöistä ja ulkoisista linkeistä.

.NET-ohjetiimi noudattaa seuraavia tapoja:

- Käytämme yleensä suhteellisia linkkejä ja kehotamme välttämään `~/`:n käyttöä linkeissä, koska suhteelliset linkit selvitetään GitHubissa lähteessä. `~/`-merkkiä käytetään kuitenkin polun ilmaisemiseen linkitettäessä riippuvaisessa säilössä olevaan tiedostoon. Riippuvaisen säilön tiedostot ovat GitHubissa eri sijainnissa, ja siksi suhteellisia linkkejä ei kirjoitustavasta riippumatta voida selvittää oikein.
- C#-kielimääritys ja Visual Basic -kielimääritys sisällytetään .NET-ohjeistuksiin lisäämällä lähde kielisäilöistä. Markdown-lähteitä hallinnoidaan [csharplang](https://github.com/dotnet/csharplang)- ja [vblang](https://github.com/dotnet/vblang)-säilöissä.

Määrityksen linkkien on osoitettava niihin lähdehakemistoihin, joihin kyseiset määritykset kuuluvat. C#:n osalta kyseessä on **~/_csharplang/spec** ja VB:n **~/_vblang/spec**.

- Esimerkki: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)`

### <a name="links-to-apis"></a>Ohjelmointirajapintoihin viittaavat linkit

Osa koontijärjestelmän laajennuksista mahdollistaa linkittämisen .NET-ohjelmointirajapintoihin ilman ulkoisia linkkejä. Voit käyttää jompaa kumpaa seuraavista syntakseista:

1. Automaattinen linkki: `<xref:UID>` tai `<xref:UID?displayProperty=nameWithType>`

   Kyselyparametri `displayProperty` tuottaa täysin toimivan linkkitekstin. Oletusarvoisesti linkkitekstissä näkyy vain jäsenen tai tyypin nimi.

2. Markdown-linkki: `[link text](xref:UID)`

   Käytä tätä vaihtoehtoa, kun haluat mukauttaa näkyviin tulevaa linkkitekstiä.

Esimerkkejä:

- `<xref:System.String>` hahmontuu muotoon [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` hahmontuu muotoon [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` hahmontuu muotoon [String class](https://docs.microsoft.com/dotnet/api/system.string)

Lisätietoja tämän merkintätavan käytöstä on artikkelissa [Ristiviitteiden käyttö](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).

Jos UID sisältää erikoismerkkejä \`, \# tai \*, UID-arvo on HTML-koodattava vastaavasti seuraavasti: `%60`, `%23` tai `%2A`. Joskus myös sulkeet koodataan, mutta tämä ei ole välttämätöntä.

Esimerkkejä:

- System.Threading.Tasks.Task\`1 muuttuu muotoon `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor muuttuu muotoon `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) muuttuu muotoon `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

Voit hakea tyyppien, jäsenen ylikuormitusluettelon tai tietyn ylikuormitetun jäsenen UID:t osoitteesta `https://xref.docs.microsoft.com/autocomplete`. Kyselymerkkijono "?text=*\<tyypin-tai-jäsenen-nimi>*" määrittää tyypin tai jäsenen, jonka UID:t haluat hakea. Esimerkiksi `https://xref.docs.microsoft.com/autocomplete?text=string.format` hakee [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format)-ylikuormitukset. Työkalu hakee annettua `text`-kyselyparametria mistä tahansa UID:n osasta. Voit esimerkiksi hakea jäsenen nimellä (ToString), puutteellisella jäsenen nimellä (ToStri), tyypin ja jäsenen nimellä (Double.ToString) jne.

Jos lisäät \*-merkin (tai %2A) UID:n perään, linkki edustaa ylikuormitussivua tietyn ohjelmointirajapinnan sijaan. Voit käyttää merkkiä esimerkiksi silloin, jos haluat linkittää [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch)-sivulle yleisellä tasolla tietyn ylikuormituksen (esim. [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_)) sijasta. Voit käyttää \*-merkkiä myös linkittäessäsi jäsenen sivulle silloin, kun jäsentä ei ole ylikuormitettu. Tällöin sinun ei tarvitse lisätä parametriluetteloa UID:hen.

Jos haluat linkittää tietyn menetelmän ylikuormitukseen, sinun on annettava menetelmän jokaisen parametrin kelvollinen tyypin nimi. Esimerkiksi \<xref:System.DateTime.ToString> linkittyy menetelmään [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString), jolla ei ole parametrejä, kun taas \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> linkittyy [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_)-menetelmään.

Jos haluat linkittää yleiseen tyyppiin, kuten [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), käytä \`-merkkiä (%60) ja kirjoita sen perään yleisen tyypin parametrien lukumäärä. Esimerkiksi \<xref:System.Nullable%601> linkittää tyyppiin [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), kun taas \<xref:System.Func%602> linkittää valtuutettuun viittaukseen [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).

## <a name="code"></a>Koodi

Koodia on suositeltavaa lisätä toimivasta esimerkkisovelluksesta poimittuina koodikatkelmina. Voit luoda esimerkkisovelluksen [.NETin kehittämiseen osallistumista](dotnet-contribute-process.md#contributing-to-samples) koskevan artikkelin ohjeiden mukaan. Koodin lisäämisen perussäännöt on kerrottu [koodia](how-to-write-use-markdown.md#code-includes) käsittelevissä yleisohjeissa.

Käytä koodin lisäämiseen seuraavaa syntaksia:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* `-<language>` (*valinnainen* mutta *suositeltava*)
  * Viitattavan koodikatkelman ohjelmointikieli. Tuettujen arvojen luettelo on kohdassa [Tuetut kielet](#supported-languages).

* `<name>` (*valinnainen*)
  * Koodikatkelman nimi. Tällä ei ole vaikutusta lopulliseen HTML-tulokseen, mutta voit käyttää tätä parantaaksesi Markdown-lähteesi luettavuutta.

* `<pathToFile>` (*pakollinen*)
  * Tiedostojärjestelmässä oleva suhteellinen polku, joka osoittaa koodikatkelmatiedoston, johon viitataan. Eri säilöt, joista .NET-ohjejoukko koostuu, voivat mutkistaa tätä. .NET-esimerkkisovellukset sijaitsevat dotnet/samples-säilössä. Kaikki katkelmapolut alkavat samalla tavalla: `~/samples`. Polun loppuosa on lähteeseen viittaava polku kyseisen säilön juuresta.

* `<queryoption>` (*valinnainen*)
  * Käytetään määrittämään, miten koodi noudetaan tiedostosta:
    * `#`:  `#{tagname}` (tunnisteen nimi) *tai* `#L{startlinenumber}-L{endlinenumber}` (rivit).
    Rivinumeroiden käyttöä ei suositella, koska ne voivat herkästi muuttua. On suositeltavaa viitata koodikatkelmiin tunnisteiden nimillä. Anna tunnisteille merkitykselliset nimet. (Aiemmasta alustasta siirrettiin paljon koodikatkelmia, joiden tunnisteet olivat `Snippet1`, `Snippet2` jne. Tätä käytäntöä on paljon haastavampaa ylläpitää.)
    * `range`: `?range=1,3-5` Rivialue. Tämä esimerkki sisältää rivit 1, 3, 4 ja 5.

Suosittelemme tunnisteen nimen käyttöä aina kun mahdollista. Tunnisteen nimi on lähdekoodista löytyvä alueen tai koodin kommentin nimi muodossa `Snippettagname`. Seuraavassa esimerkissä näytetään tunnisteen nimeen `BasicThrow` viittaaminen:

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

Säilössä **dotnet/samples** olevan lähteen suhteellinen polku seuraa `~/samples`-polkua.

[Tästä lähdetiedostosta](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) näet koodikatkelman tunnisteiden rakenteen. Lisätietoja tunnisteen nimen esittämisestä koodikatkelmien lähdetiedostoissa kielen mukaan on artikkelissa [DocFX-ohjeet](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

Seuraavassa esimerkissä koodia on lisätty kaikilla kolmella .NET-kielellä:

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

Kun koodikatkelmia lisätään kokonaisista ohjelmista, varmistetaan samalla, että kaikki koodi suoritetaan CI-järjestelmämme (Continuous Integration) läpi. Jos kuitenkin haluat näyttää lukijalle jotakin, josta aiheutuu käännösaika- tai suorituspalveluvirheitä, voit käyttää tekstiin sidottuja koodilohkoja.

## <a name="images"></a>Kuvat

### <a name="static-image-or-animated-gif"></a>Staattinen kuva tai animoitu GIF

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a>Linkitetty kuva

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a>Videot

Voit tällä hetkellä upottaa sekä Channel 9- että YouTube-videoita seuraavalla syntaksilla:

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

Voit hakea videon oikean URL-osoitteen valitsemalla videon alta **Embed**-välilehden ja kopioimalla URL-osoitteen `<iframe>`-elementistä. Esimerkki:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Voit hakea videon oikean URL-osoitteen napsauttamalla videota hiiren kakkospainikkeella, valitsemalla **Kopioi upotuskoodi** ja kopioimalla sitten URL-osoitteen `<iframe>`-elementistä.

```markdown
> [!VIDEO <youtube_video_link>]
```

Esimerkki:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>docs.microsoft-laajennukset

docs.microsoft tarjoaa muutamia lisälaajennuksia GitHub Flavored Markdowniin.

### <a name="checked-lists"></a>Tarkistusmerkeillä merkityt luettelot

Luetteloille on käytettävissä mukautettu tyyli. Voit hahmontaa luettelot vihreillä tarkistusmerkeillä.

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

Tämä hahmontuu seuraavasti:

> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application

Aidon esimerkin tarkistusmerkeillä merkityistä luetteloista saat [.NET Core -ohjeista](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Painikkeet

Painikelinkit:

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

Tämä hahmontuu seuraavasti:

> [!div class="button"]
[button links](dotnet-contribute.md)

Aidon esimerkin painikkeista saat [Visual Studio -ohjeista](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="step-by-steps"></a>Vaiheittaiset ohjeet

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

Aidon esimerkin vaiheittaisista ohjeista näet [C#-ohjeista](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
