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
# <a name="markdown-reference-for-ops"></a>OPS-ympäristön Markdown-viiteopas

Markdown on kevyt merkintäkieli, jonka syntaksi on tekstipohjainen. Open Publishing Services (OPS) tukee Markdownille luotua CommonMark-standardia sekä joitakin mukautettuja Markdown-laajennuksia, jotka mahdollistavat docs.microsoft.com-sivuston sisältöjen monipuolisemmat muotoilut. Tämä artikkeli sisältää aakkostetun viiteoppaan docs.microsoft.com-sivustolla julkaistavan sisällön luomiseen Markdownilla OPS-ympäristössä.

Voit kirjoittaa Markdown-syntaksia millä tahansa tekstieditorilla. Jos käytät sekä tavallista Markdown-syntaksia että mukautettuja OPS-laajennuksia, sinun kannattaa käyttää [VS Code](https://code.visualstudio.com/) -editoria, johon on asennettu [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack).

OPS käyttää Markdigia standardinaan kaikissa uusissa säilöissä, ja Markdig otetaan käyttöön myös vanhemmissa säilöissä. Voit testata Markdownin hahmontamista Markdigissa verrattuna muihin vaihtoehtoihin osoitteessa [https://babelmark.github.io/](https://babelmark.github.io/).

## <a name="alerts-note-tip-important-caution-warning"></a>Ilmoitukset (huomautus, vinkki, tärkeää, huomio ja varoitus)

OPS:lle suunnitellussa Markdown-laajennuksessa ilmoituksilla luodaan tekstilohkoja, jotka hahmonnetaan docs.microsoft.com-sivustolle käyttämällä sisällön tärkeyttä korostavia värejä ja kuvakkeita. Seuraavia ilmoitustyyppejä tuetaan:

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

Ilmoitukset näyttävät seuraavanlaisilta docs.microsoft.com-sivustolla:

> [!NOTE]
> Tietoja, jotka käyttäjän on huomattava tekstiä silmäillessään.

> [!TIP]
> Valinnaista tietoa, joka auttaa käyttäjää suoriutumaan entistä paremmin.

> [!IMPORTANT]
> Oleellista tietoa, jota käyttäjä tarvitsee onnistuakseen.

> [!CAUTION]
> Toimenpiteen mahdolliset kielteiset seuraukset.

> [!WARNING]
> Toimenpiteen varmat vaaralliset seuraukset.

## <a name="code-snippets"></a>Koodikatkelmat

Voit upottaa koodikatkelmia Markdown-tiedostoihin:

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a>Otsikot

OPS tukee kuuden tason Markdown-otsikoita:

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- Viimeisen `#`-merkin ja otsikon välissä on oltava välilyönti.
- Kussakin Markdown-tiedostossa on oltava täsmälleen yksi ylimmän tason otsikko (H1).
- H1-otsikon on oltava tiedoston ensimmäinen sisältö YML-metatietoalueen jälkeen.
- H2-tason otsikot näkyvät automaattisesti julkaistun tiedoston oikeassa reunassa olevassa siirtymävalikossa. Alempien tasojen otsikot eivät näy siirtymävalikossa. H2-otsikoita kannattaakin käyttää siten, että lukijoiden on helppoa liikkua sisällössä.
- HTML-otsikoita, kuten `<h1>`, ei suositella, ja joissakin tapauksissa ne aiheuttavat koontiversiovaroituksia.
- Tiedoston yksittäisiin otsikoihin voi lisätä linkkejä [kirjanmerkkien](#bookmark-links) avulla.

## <a name="html"></a>HTML

Vaikka Markdown tukee rivin sisäistä HTML:ää, HTML:ää ei suositella julkaistaessa sisältöä OPS:n kautta. Muut kuin tietyt määrätyt arvot aiheuttavat koontiversiovirheitä tai -varoituksia. <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a>Kuvat

Kuvan liittämisen syntaksi on seuraava:

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

`alt text` on kuvan lyhyt kuvaus, ja `<folder path>` on kuvan suhteellinen polku. Vaihtoehtoista tekstiä tarvitaan heikkonäköisten käyttämiä näytönlukuohjelmia varten. Siitä on hyötyä myös, jos sivustolla on virhe, joka estää kuvan hahmontamisen.

Kuvat on tallennettava asiakirjajoukon `/media`-kansioon. Seuraavia kuvatiedostotyyppejä tuetaan oletusarvoisesti:

- .jpg
- .png

Muiden kuvatyyppien tuen voi lisätä lisäämällä ne resursseina asiakirjajoukon docfx.json-tiedostoon<!--add link to reference when available-->.

## <a name="links"></a>Linkit

Useimmissa tapauksissa OPS käyttää tavallisia Markdown-linkkejä viittaamaan muihin tiedostoihin ja muille sivuille. Linkkien tyypit on kuvattu alla olevissa alakohdissa.

> [!TIP]
> Docs Authoring Pack VS Codelle voi auttaa lisäämään suhteelliset linkit ja kirjanmerkit oikein ilman polkujen selvittämisen vaivaa!

> [!IMPORTANT]
> Älä lisää kieliasetuskoodeja (esimerkiksi en-us) Microsoft-sivustoille viittaaviin linkkeihin. Pysyväiskoodatut kieliasetuskoodit estävät lokalisoidun sisällön hahmontamisen, mikä on ikävää muunkielisille käyttäjille ja aiheuttaa merkittäviä lokalisointikustannuksia. Kieliasetuskoodi sisältyy oletusarvoisesti selaimesta kopioituun URL-osoitteeseen, joten sinun on poistettava se manuaalisesti luodessasi linkin. Esimerkki oikeasta muodosta:
>
> `[Microsoft](https://www.microsoft.com)`
>
> Virheellinen muoto:
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a>Saman asiakirjajoukon tiedostoihin viittaavat suhteelliset linkit

Suhteellinen polku on kohdetiedostoon johtava polku, joka on määritetty suhteessa nykyiseen tiedostoon. OPS-ympäristössä suhteellisen polun avulla voi muodostaa linkin samassa asiakirjajoukossa sijaitsevaan toiseen tiedostoon. Suhteellisen polun syntaksi on seuraava:

```markdown
[link text](../../folder/filename.md)
```

`../` tarkoittaa hierarkiassa yhtä ylempänä olevaa tasoa.

- Suhteellinen polku selvitetään ja .md-tunniste poistetaan koonnin aikana.
- Voit muodostaa linkin pääkansiossa olevaan tiedostoon "../"-rakenteen avulla, kunhan kyseinen tiedosto kuuluu samaan asiakirjajoukkoon. "../"-rakenteella ei voi muodostaa linkkiä jonkin toisen asiakirjajoukon kansiossa sijaitsevaan tiedostoon.
- OPS tukee myös suhteellisen polun erityismuotoa, joka alkaa merkillä ~ (esimerkiksi ~/foo/bar.md). Tämä syntaksi ilmaisee tiedoston suhteen asiakirjajoukon pääkansioon. Myös tämäntyyppinen polku vahvistetaan ja selvitetään koonnin aikana.

> [!IMPORTANT]
> Lisää suhteelliseen polkuun tiedostotunniste. Koonnin aikana kyseisen suhteellisen polun kohdetiedoston olemassaolo vahvistetaan. Jos suhteellinen polku ei sisällä tiedostotunnistetta, on todennäköistä, että koontiversio antaa varoituksen katkenneesta hyperlinkistä. Esimerkki oikeasta muodosta:
>
> `[link text](../../folder/filename.md)`
>
> Virheellinen muoto:
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a>Muihin OPS:ssä sijaitseviin tiedostoihin viittaavat absoluuttiset linkit

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

Älä käytä tiedostotunnistetta (.md). Tämä muodostaa linkin Linuxin Overview-tiedostoon Azuren Articles-asiakirjajoukon ulkopuolelta.

### <a name="links-to-external-sites"></a>Ulkoisiin sivustoihin viittaavat linkit

```markdown
[Microsoft](https://www.microsoft.com)
```

URL-pohjainen linkki toiselle verkkosivulle (alun on oltava https://).

### <a name="bookmark-links"></a>Kirjanmerkkilinkit

Kirjanmerkkilinkki samassa säilössä sijaitsevan toisen tiedoston otsikkoon:

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

Kirjanmerkkilinkki nykyisen tiedoston otsikkoon:

```markdown
[Managed Disks](#managed-disks)
```

Kirjoita ristikkomerkin perään otsikon sanat siten, että poistat välimerkit ja korvaat välilyönnit viivalla.

### <a name="explicit-anchor-links"></a>Eksplisiittiset ankkurilinkit

Eksplisiittisiä ankkurilinkkejä, joissa käytetään HTML-tunnistetta `<a>` **ei edellytetä eikä suositella** käytettäväksi muuten kuin keskuksessa ja saapumissivuilla. Käytä yleisissä Markdown-tiedostoissa kirjanmerkkejä yllä kuvatulla tavalla. Käytä keskuksissa ja saapumissivuilla ankkureita seuraavasti:

`## <a id="AnchorText"> </a>Header text` tai `## <a name="AnchorText"> </a>Header text`

Voit muodostaa eksplisiittisiin ankkureihin viittaavia linkkejä seuraavalla syntaksilla:

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a>XREF-linkit (ristiviittaus)

Voit muodostaa linkkejä automaattisesti muodostettuihin ohjelmointirajapintaviitesivuihin nykyisessä asiakirjajoukossa tai muissa asiakirjajoukoissa käyttämällä XREF-linkkejä, joilla on yksilöivä tunnus (UID).

> [!NOTE]
> Voidaksesi viitata muiden asiakirjajoukkojen ohjelmointirajapintaviitesivuihin sinun on lisättävä määritys `xrefService` tiedostoon `docfx.json`.
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

UID-tunnus vastaa täydellistä luokan ja jäsenen nimeä. Jos lisäät *-merkin UID:n perään, linkki edustaa kuormitussivua tietyn ohjelmointirajapinnan sijaan. Esimerkiksi käyttämällä rakennetta `List<T>.BinarySearch*` voit muodostaa linkin BinarySearch-metodisivuun sen sijaan, että linkki viittaisi tiettyyn kuormitukseen, kuten rakenteessa `List<T>.BinarySearch(T, IComparer<T>)`.

Voit käyttää jotakin seuraavista syntakseista:

- Automaattinen linkki: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`

  Valinnainen kyselyparametri `displayProperty` tuottaa täydellisen linkkitekstin. Oletusarvoisesti linkkitekstissä näkyy vain jäsenen tai tyypin nimi.

- Markdown-linkki: `[link text](xref:UID)`
  
  Käytä tätä vaihtoehtoa, kun haluat mukauttaa näkyviin tulevaa linkkitekstiä.

Esimerkkejä:

- `<xref:System.String>` hahmontuu muotoon "String".
- `<xref:System.String?displayProperty=nameWithType>` hahmontuu muotoon "System.String".
- `[String class](xref:System.String)` hahmontuu muotoon "String class".

Tällä hetkellä ei ole olemassa helppoa tapaa löytää UID-tunnuksia. <!-- ? -->Paras tapa löytää ohjelmointirajapinnan UID-tunnus on tutkia linkitettävän ohjelmointirajapintasivun lähdettä ja etsiä sieltä ms.assetid-arvo. Yksittäisiä kuormitusarvoja ei näytetä lähteessä. Pyrimme luomaan paremman järjestelmän tulevaisuudessa.

Kun UID-tunnus sisältää erikoismerkkejä \`, \# tai \*, UID-arvo on HTML-koodattava vastaavasti seuraavasti: `%60`, `%23` tai `%2A`. Joskus myös sulkeet koodataan, mutta tämä ei ole välttämätöntä.

Esimerkkejä:

- System.Threading.Tasks.Task\`1 muuttuu muotoon `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor muuttuu muotoon `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) muuttuu muotoon `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a>Luettelot (numeroidut luettelot, luettelomerkeillä varustetut luettelot ja tarkistusluettelot)

### <a name="numbered-list"></a>Numeroitu luettelo

Voit luoda numeroidun luettelon käyttämällä aina numeroa 1. Numerot hahmonnetaan järjestyslukuluetteloksi julkaisuvaiheessa. Voit parantaa lähteen luettavuutta käyttämällä luetteloissa kasvavia järjestyslukuja.

Älä käytä luetteloissa kirjaimia. Tämä pätee myös sisäkkäisiin luetteloihin. Ne eivät hahmonnu oikein, kun ne julkaistaan OPS:n kautta. Sisäkkäisten luetteloiden numerointi hahmontuu julkaistaessa pieniksi kirjaimiksi. Esimerkki:

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

Tämä hahmontuu seuraavasti:

1. Tämä on
1. numeroitu pääluettelo
   1. ja tämä on
   1. numeroitu sisäkkäinen luettelo
1. (loppu)

### <a name="bulleted-list"></a>Luettelomerkeillä varustettu luettelo

Voit luoda luettelomerkeillä varustetun luettelon lisäämällä kunkin rivin alkuun symbolin `-` ja sen perään välilyönnin:

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

Tämä hahmontuu seuraavasti:

- Tämä on
- luettelomerkeillä varustettu pääluettelo
  - ja tämä on
  - luettelomerkeillä varustettu sisäkkäinen luettelo
- Valmista!

### <a name="checklist"></a>Tarkistusluettelo

Tarkistusluetteloita voi laatia mukautetun Markdown-laajennuksen avulla (vain) docs.microsoft.com-sivustolle:

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

Tämä esimerkki hahmontuu docs.microsoft.com-sivustolla seuraavasti:

> [!div class="checklist"]
> * Luettelokohde 1
> * Luettelokohde 2
> * Luettelokohde 3

Voit käyttää tarkistusluetteloita artikkelin alussa tai lopussa kuvaamaan artikkelin sisältämää opittavaa sisältöä. Älä lisää tarkistusluetteloja satunnaisesti eri puolille artikkelia.
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a>Siirtyminen seuraavaan vaiheeseen

Mukautetun laajennuksen avulla voit lisätä seuraavaan vaiheeseen siirtymisen painikkeen (vain) docs.microsoft.com-sivustolle.

Syntaksi on seuraava:

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

Esimerkki:

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

Tämä hahmontuu seuraavasti:

> [!div class="nextstepaction"]
> [Tietoja perustyylistä](style-quick-start.md)

Seuraavaan vaiheeseen siirtymisessä voi käyttää mitä tahansa tuettua linkkiä, mukaan lukien toiselle verkkosivulle viittaavaa Markdown-linkkiä. Useimmissa tapauksissa seuraavaan vaiheeseen siirtymisen linkki on toiseen samassa asiakirjajoukossa olevaan tiedostoon viittaava suhteellinen linkki.

## <a name="section-definition"></a>Osion määrittely

<!-- more info about this would be helpful! --> Joskus osion määrittely on tarpeen. Tätä syntaksia käytetään eniten kooditaulukoissa.
Seuraavassa on esimerkki.

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

Edellä oleva Markdown-tekstikatkelma hahmontuu seuraavasti:
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a>Valitsimet

<!-- could be more clear! --> Valitsimen avulla voit yhdistää saman artikkelin eri sivuja. Näin lukijat voivat siirtyä sivulta toiselle.

> [!NOTE]
> Tämä laajennus toimii eri tavoin docs.microsoft.com-sivustossa ja MSDN:ssä. <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a>Yksittäinen valitsin

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

... hahmonnetaan seuraavasti:

> [!div class="op_single_selector"]
> - [Universaali Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a>Monivalitsin

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

... hahmonnetaan seuraavasti:

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

## <a name="tables"></a>taulukoilla

Yksinkertaisin tapa luoda taulukko Markdownilla on käyttää pystyviivoja ja yhdysmerkkejä. Voit luoda vakiomallisen taulukon otsikoineen lisäämällä ensimmäisen rivin jälkeen katkoviivan:

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

Tämä hahmontuu seuraavasti:

|Tämä on   |yksinkertainen   |taulukon otsikko|
|----------|-----------|------------|
|taulukon     |tiedot       |tänne        |
|niiden ei|oikeastaan   |tarvitse asettua kauniisti!||

Voit myös luoda taulukon ilman otsikkoa. Esimerkiksi monisarakkeisen luettelon voi luoda seuraavasti:

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

Tämä hahmontuu seuraavalla tavalla:

|   |   |
| - | - |
| Tässä | taulukossa |
| ei ole | otsikkoa |

Voit tasata sarakkeet käyttämällä kaksoispisteitä:

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

Tämä hahmontuu seuraavasti:

|                  |
|------------------|
|    tasattu oikealle:|
|:tasattu vasemmalle     |
|:keskitetty        :|

> [!TIP]
> VS Coden Docs Authoring -laajennuksen avulla perustyyppisten Markdown-taulukoiden lisääminen sujuu helposti.
>
> Vaihtoehtoisesti voit käyttää [verkossa olevaa taulukkogeneraattoria](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a>mx-tdBreakAll

> [!IMPORTANT]
> Tämä toimii vain docs.microsoft.com-sivustossa.

Markdownilla luotu taulukko saattaa laajentua oikealle ja muuttua lukukelvottomaksi. Ongelman voi ratkaista sallimalla Docs-hahmonnuksen katkaista taulukko tarvittaessa. Rivitä taulukko käyttämällä mukautettua luokkaa `[!div class="mx-tdBreakAll"]`.

Ohessa on Markdown-malli kolmirivisestä taulukosta, joka rivitetään syntaksilla `div` ja luokan nimellä `mx-tdBreakAll`.

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

Se hahmonnetaan seuraavasti:

> [!div class="mx-tdBreakAll"]
> |Nimi|Syntaksi|Pakollinen hiljaisessa asennuksessa?|Kuvaus|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Kyllä|Suorittaa asennusohjelman näyttämättä käyttöliittymää tai kehotteita.|
> |NoRestart|/norestart|Ei|Estää uudelleenkäynnistysyritykset. Oletusarvoisesti käyttöliittymä näyttää kehotteen ennen uudelleenkäynnistystä.|
> |Help|/help|Ei|Tarjoaa ohjeita ja pikaoppaita. Näyttää oikean tavan käyttää asennuskomentoa sekä luettelon kaikista asetuksista ja toiminnoista.|

### <a name="mx-tdcol2breakall"></a>mx-tdCol2BreakAll

> [!IMPORTANT]
> Tämä toimii vain docs.microsoft.com-sivustossa.

Toisinaan taulukon toisessa sarakkeessa saattaa olla hyvin pitkiä sanoja. Saat ne katkeamaan kauniisti, kun käytät rivityssyntaksia `div` edellä kuvatulla tavalla mutta määrität luokaksi `mx-tdCol2BreakAll`.

### <a name="html-tables"></a>HTML-taulukot

HTML-taulukoita ei suositella käytettäväksi docs.microsoft.com-sivustolla. Ne eivät ole helposti luettavassa muodossa lähteessä, mikä on Markdownin pääperiaate.

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a>Videot

### <a name="embedding-videos-into-a-markdown-page"></a>Videoiden upottaminen Markdown-sivuun

Tällä hetkellä OPS voi tukea videoita, jotka on julkaistu jossakin seuraavista kolmesta sijainnista:

- YouTube
- Channel 9
- Microsoftin oma One Player -järjestelmä

Voit upottaa videon seuraavan syntaksin avulla, ja OPS hahmontaa sen.

```markdown
> [!VIDEO <embedded_video_link>]
```

Esimerkki:

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

... hahmonnetaan seuraavasti:

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

Julkaistuilla sivuilla tulos näyttää tältä:

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> CH9-videon URL-osoitteen alun on oltava `https` ja lopun `/player`. Muuten upotetuksi tulee koko sivu pelkän videon sijasta.

### <a name="uploading-new-videos"></a>Uusien videoiden lataaminen

Uudet videot on ladattava seuraavalla tavalla:

1. Liity IDWEB:n **docs_video_users**-ryhmään.
1. Siirry osoitteeseen https://aka.ms/VideoUploadRequest ja anna videon tiedot. Tarvitset seuraavat tiedot (huomaa, että nämä tiedot eivät näy julkisesti):
    1. Videon nimi.
    1. Luettelo tuotteista tai palveluista, joihin video liittyy.
    1. Kohdesivu tai (jos sivua ei vielä ole) asiakirjajoukko, jossa videota isännöidään.
    1. Linkki videon MP4-tiedostoon (jos sinulla ei ole paikkaa, johon voisit tallentaa tiedoston, voit tallentaa sen tilapäisesti tänne:   `\\scratch2\scratch\apex`). MP4-tiedostojen tarkkuuden on oltava vähintään 720p.
    1. Videon kuvaus.
1. Lähetä (tallenna) kohde.
1. Video ladataan kahden arkipäivän kuluessa. Upotuksessa tarvittava linkki lisätään työkohteeseen, ja kohde ratkaistaan lähettämällä se *takaisin sinulle*.
1. Kun olet hakenut videolinkin, sulje työkohde.
1. Tämän jälkeen voit lisätä videolinkin julkaisuun seuraavalla syntaksilla:

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
