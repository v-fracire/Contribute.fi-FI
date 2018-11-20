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
# <a name="how-to-use-markdown-for-writing-docs"></a>Miten käyttää Markdownia Docsien kirjoittamiseen

[Docs.microsoft.com](http://docs.microsoft.com)-artikkelit kirjoitetaan kevyellä [Markdown](https://daringfireball.net/projects/markdown/)-nimisellä merkintäkielellä, joka on sekä helppolukuinen että helppo oppia. Tämän vuoksi siitä on nopeasti tullut alan standardi.

Koska Docs-sisältö säilytetään GitHubissa, se voi käyttää [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) -nimistä Markdownin yläjoukkoa, joka sisältää lisätoimintoja yleisiä muotoilutarpeita varten. Lisäksi Open Publishing Services (OPS) käyttää Markdig Markdown Parseria. Markdig on laajasti yhteensopiva GFM:n kanssa, ja se lisää Docsiin liittyvää toiminnallisuutta.

* Markdig on nopea, tehokas, CommonMark-yhteensopiva, laajennettava Markdown-suoritin .NETiä varten.
* https://github.com/lunet-io/markdig
* Entistä parempi yhteisön tuki
* Entistä parempi standardien tuki

## <a name="markdown-basics"></a>Markdownin perusteet

### <a name="headings"></a>Otsikot

Voit luoda otsikon käyttämällä #-merkkiä seuraavasti:

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

Otsikoiden luonnissa tulee käyttää atx-tyyliä, eli otsikko tulee merkitä rivin alussa olevilla 1–6 ristikkomerkillä, jotka vastaavat HTML-otsikkotasoja H1–H6. Yllä näet esimerkit tasojen 1–4 otsikoista.

Aiheessa saa olla **vain yksi** ensimmäisen tason otsikko (H1). Se näytetään sivun otsikkona.

Jos otsikko päättyy `#`-merkkiin, otsikon oikea hahmontaminen edellyttää ylimääräisen `#`-merkin lisäämistä otsikon loppuun. Esimerkki: `# Async Programming in F# #`.

Toisen tason otsikoista luodaan sivulle sisällysluettelo, joka näytetään sivun otsikon alla olevassa Artikkelin sisältö -kohdassa.

### <a name="bold-and-italic-text"></a>Tekstin lihavointi ja kursivointi

Voit **lihavoida** tekstiä ympäröimällä sen kahdella tähtimerkillä:

```markdown
This text is **bold**.
```

Voit *kursivoida* tekstiä ympäröimällä sen yhdellä tähtimerkillä:

```markdown
This text is *italic*.
```

Voit ***lihavoida ja kursivoida***  tekstiä ympäröimällä sen kolmella tähtimerkillä:

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a>Pitkät lainaukset

Pitkät lainaukset luodaan `>`-merkin avulla:

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

Yllä oleva esimerkki hahmonnetaan seuraavasti:

> Kuivuutta oli nyt kestänyt kymmenen miljoonaa vuotta, ja hirmuliskojen valtakausi oli aikoja sitten päättynyt. Täällä päiväntasaajalla, mantereella, joka jonain päivänä tunnettaisiin Afrikkana, oli olemassaolon taistelu saavuttanut uuden raivokkaan huipun. Tässä hedelmättömässä, kuivassa maassa voivat vain pienet, nopeat tai raivoisat menestyä tai edes toivoa säilyvänsä.

### <a name="lists"></a>Luettelot

#### <a name="unordered-list"></a>Järjestämätön luettelo

Voit muotoilla järjestämättömän / luettelomerkein varustetun luettelon käyttämällä joko tähtimerkkejä tai ajatusviivoja. Esimerkiksi seuraava Markdown:

```markdown
- List item 1
- List item 2
- List item 3
```

hahmonnetaan seuraavasti:

- Luettelokohde 1
- Luettelokohde 2
- Luettelokohde 3

Voit luoda luettelon toisen luettelon sisälle sisentämällä aliluettelon kohteet. Esimerkiksi seuraava Markdown:

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

hahmonnetaan seuraavasti:

- Luettelokohde 1
  - Luettelokohde A
  - Luettelokohde B
- Luettelokohde 2

#### <a name="ordered-list"></a>Järjestetty luettelo

Voit muotoilla järjestetyn/asteittaisen luettelon käyttämällä vastaavia numeroita. Esimerkiksi seuraava Markdown:

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

hahmonnetaan seuraavasti:

1. Ensimmäinen ohje
2. Toinen ohje
3. Kolmas ohje

Voit luoda luettelon toisen luettelon sisälle sisentämällä aliluettelon kohteet. Esimerkiksi seuraava Markdown:

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

hahmonnetaan seuraavasti:

1. Ensimmäinen ohje
   1. Alaohje
   2. Alaohje
2. Toinen ohje

Huomaa, että lukua 1 käytetään jokaisessa kohdassa. Se tekee muutosten tarkistamisesta helpompaa, kun myöhemmissä päivityksessä lisätään tai poistetaan vaiheita.

### <a name="tables"></a>taulukoilla

Taulukot eivät kuulu Markdownin ydinkokonaisuuteen, mutta GFM tukee niitä. Voit luoda taulukoita käyttämällä pystyviivaa (|) ja tavuviivaa (-). Tavuviivat luovat sarakkeen otsikon ja pystyviivat erottavat sarakkeet toisistaan. Lisää tyhjä rivi taulukon eteen, niin se hahmonnetaan oikein.

Esimerkiksi seuraava Markdown:

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

hahmonnetaan seuraavasti:

| Pidä                  | hauskaa                 | taulukoilla          |
| :------------------- | -------------------: |:---------------:|
| vasemmalle tasattu sarake  | oikealle tasattu sarake | keskitetty sarake |
| 100 €                 | 100 €                 | 100 €            |
| 10 €                  | 10 €                  | 10 €             |
| 1 €                   | 1 €                   | 1 €              |

Jos haluat lisätietoja taulukoiden luomisesta, katso:

- Markdigin [taulukon rivitysominaisuus](#table-wrapping), joka voi auttaa leveiden taulukoiden muotoilussa.
- GitHubin [tietojen järjestäminen taulukoiden avulla](https://help.github.com/articles/organizing-information-with-tables/).
- [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) -verkkosovellus.
- [Adam Pritchardin Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).
- [Michel Fortinin Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).
- [HTML-taulukoiden muuntaminen Markdowniksi](https://jmalarcon.github.io/markdowntables/).

### <a name="links"></a>Linkit

Tekstin sisäisen linkin Markdown-syntaksi koostuu `[link text]`-osasta, joka on hyperlinkitettävä teksti, ja `(file-name.md)`-osasta, joka on linkitettävän URL-osoitteen tai tiedoston nimi:

 `[link text](file-name.md)`

Jos haluat lisätietoja linkittämisestä, katso:

- [Markdown- syntaksioppaasta](https://daringfireball.net/projects/markdown/syntax#link) tietoja Markdownin peruslinkitystuesta.
- Tämän oppaan [Linkit](how-to-write-links.md)-osasta tietoja Markdigin sisältämästä lisäsyntaksista linkittämistä varten.

### <a name="code-snippets"></a>Koodikatkelmat

Markdown tukee koodikatkelmien sijoittamista lauseiden sisään sekä lauseiden väliin erillisinä aidattuina lohkoina. Lisätietoja:

- [Markdownin oma koodilohkojen tuki](https://daringfireball.net/projects/markdown/syntax#precode)
- [GFM:n tuki koodin aitaamiselle ja syntaksin korostukselle](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Aidatut koodilohkot ovat helppo tapa mahdollistaa syntaksin korostus koodikatkelmissa. Aidattujen koodilohkojen yleinen muotoilu on:

    ```alias
    ...
    your code goes in here
    ...
    ```

Ensimmäisten kolmen gravis-merkin (`) jälkeen tuleva alias määrittää käytettävän syntaksin korostuksen. Seuraavassa on luettelo Docs-sisällössä yleisesti käytetyistä ohjelmointikielistä ja vastaavasta selitteestä:

Näille kielille on kutsumanimituki, ja useimmille on käytössä kielen korostus.

|Nimi|Markdown-selite|
|-----|-------|
|.NET Console|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|AzCopy|AzCopy|
|Azure CLI|azurecli|
|Azure PowerShell|azurepowershell|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|C# selaimessa|csharp-interactive|
|Console|console|
|CSHTML|cshtml|
|DAX|dax|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|Power Apps Formula|powerappsfl|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|R|r|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|VSTS CLI|vstscli|
|XAML|xaml|
|XML|xml|

Nimi `csharp-interactive` määrittää C#-kielen sekä mahdollisuuden suorittaa esimerkit selaimesta. Nämä katkelmat on käännetty ja suoritettu Docker-säilössä, ja ohjelman suorituksen tulokset näkyvät käyttäjän selainikkunassa.

#### <a name="example-c"></a>Esimerkki: C\#

__Markdown__

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

__Hahmonnus__

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

#### <a name="example-sql"></a>Esimerkki: SQL

__Markdown__

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

__Hahmonnus__

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a>OPS:n mukautetut Markdown-laajennukset

> [!NOTE]
> Open Publishing Services (OPS) käyttää Markdig Parser for Markdownia, joka on laajasti yhteensopiva GitHub Flavored Markdownin (GFM) kanssa. Markdig lisää joitakin toimintoja Markdown-laajennusten kautta. Tähän oppaaseen onkin sisällytetty valittuja artikkeleita OPS-oppaasta. (Katso sisällysluettelosta esimerkiksi kohdat Markdig ja Markdown-laajennukset ja Koodikatkelmat.)

Docs.artikkelit käyttävät GFM:ää suurimpaan osaan artikkeleiden muotoilusta, esimerkiksi kappaleiden, luettelojen ja otsikkojen muotoiluun. Monipuolisempaa muotoilua artikkeleihin saadaan käyttämällä Markdig-ominaisuuksia, kuten:

- Huomautuslohkot
- Sisällytykset
- Valitsimet
- Upotetut videot
- Koodikatkelmat/-näytteet

Täydellisen luettelon näet sisällysluettelon kohdista Markdig ja Markdown-laajennukset ja Koodikatkelmat.

### <a name="note-blocks"></a>Huomautuslohkot

Voit kiinnittää käyttäjän huomion tiettyyn sisältöön valitsemalla neljästä huomautuslohkotyypistä:

- HUOMAUTUS
- VAROITUS
- VIHJE
- TÄRKEÄ

Huomautuslohkoja tulisi käyttää säästeliäästi, koska ne voivat olla häiritsevä. Vaikka huomautuslohkot tukevat koodilohkoja, kuvia, luetteloja ja linkkejä, pyri pitämään ne yksinkertaisina ja selkeinä.

Esimerkkejä:

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

Nämä hahmontuvat seuraavasti:

> [!NOTE]
> Tämä on HUOMAUTUS

> [!WARNING]
> Tämä on VAROITUS

> [!TIP]
> Tämä on VINKKI

> [!IMPORTANT]
> Tämä on TÄRKEÄÄ

### <a name="includes"></a>Sisällytykset

Kun haluat lisätä artikkelitiedostoihin uudelleenkäytettävää tekstiä tai kuvatiedostoja, voit sisällyttää tiedoston käyttämällä viittausta Markdigin tiedostojen sisällytysominaisuuden avulla. Tämä ominaisuus ohjaa OPS:n sisällyttämään tiedoston artikkelitiedostoon artikkelin muodostamisen aikana, jolloin siitä tulee julkaistun artikkelin osa. Sisällön uudelleenkäyttämisen avuksi on kolme erityyppistä sisällytystä:

- Tekstin sisäinen: Käytä yleinen tekstikatkelma uudelleen toisen lauseen sisällä.
- Lohko: Käytä kokonainen Markdown-tiedosto lohkona artikkelin osassa.
- Kuva: Kuvat sisällytetään Docsissa tavallisesti näin.

Tekstin sisäinen tai lohkosisällytys on vain yksinkertainen Markdown-tiedosto (.md). Se voi sisältää minkä tahansa kelvollisen Markdownin. Kaikki sisällytettävät Markdown-tiedostot tulisi sijoittaa [yhteiseen `/includes`-alihakemistoon](git-github-fundamentals.md#includes-subdirectory), säilön pääkansioon. Kun artikkeli julkaistaan, sisällytetty tiedosto lisätään siihen saumattomasti.

Tässä on sisällytyksien vaatimukset ja huomioitavat seikat:

- Käytä sisällytyksiä, kun haluat käyttää samaa tekstiä useassa artikkelissa.
- Käytä lohkosisällytyksiä, kun sisältöä on merkittävä määrä – yksi tai kaksi kappaletta, yhteinen toimenpide tai yhteinen osa. Älä käytä niitä mihinkään virkettä lyhyempään.
- Sisällytyksiä ei hahmonneta GitHubissa artikkelin hahmonnusnäkymässä, koska ne käyttävät Markdig-laajennuksia. Ne hahmonnetaan vasta julkaisemisen jälkeen.
- Varmista, että kaikki sisällytyksessä oleva teksti on kirjoitettu käyttäen kokonaisia virkkeitä ja ettei sen ymmärrettävyys perustu sellaiseen alkuperäisessä artikkelissa olevaan tekstiin, joka on lainattavan kohdan edellä tai jälkeen. Jos tätä ohjetta ei noudateta, artikkeliin syntyy käännöskelvoton merkkijono, joka pilaa lokalisoidun käyttökokemuksen.
- Älä upota sisällytyksiä toisiin sisällytyksiin. Niitä ei tueta.
- Sijoita mediatiedostot sisällytyksen alihakemistoon erityisesti liittyvään mediakansioon, esimerkiksi `<repo>`/sisällytykset/media-kansioon. Mediakansion pääkansio ei saa sisältää kuvia. Jos sisällytyksessä ei ole kuvia, vastaavaa mediahakemistoa ei tarvita.
- Samoin kuin tavallisten artikkelien tapauksessa, älä jaa mediaa sisällytyskansioiden välillä. Käytä jokaiseen sisällytykseen ja artikkeliin erillistä tiedostoa, jolla on yksilöllinen nimi. Tallenna mediatiedosto siihen mediakansioon, joka liittyy sisällytykseen.
- Älä käytä sisällytystä artikkelin ainoana sisältönä.  Sisällytysten on tarkoitus lisätä sisältöä varsinaiseen artikkeliin.

Esimerkki:

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a>Valitsimet

Käytä valitsimia teknisissä artikkeleissa, kun kirjoitat samasta artikkelista useampaa versiota. Valitsimien avulla voit ottaa huomioon eri teknologioista ja käyttöympäristöistä johtuvat erot. Tämä koskee useimmiten kehittäjille suunnattua mobiilikäyttöympäristöä käsittelevää sisältöä. Markdigissä on tällä hetkellä kaksi erityyppistä valitsinta: yksittäinen valitsin ja monivalitsin.

Koska sama valitsin-Markdown sijoitetaan kaikkiin valittuihin artikkeleihin, artikkelin valitsin on suositeltavaa sijoittaa sisällytykseen. Tällöin voit viitata sisällytykseen kaikissa niissä artikkeleissa, jotka käyttävät samaa valitsinta.

Seuraavassa on esimerkki valitsimesta:

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

Näet aidon esimerkin valitsimista [Azure-ohjeissa](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).

### <a name="code-includes"></a>Koodin sisällytys

Markdig tukee koodin edistynyttä sisällytystä artikkeleihin koodikatkelmalaajennuksen avulla. Se käyttää edistynyttä hahmonnusta, joka perustuu erilaisiin GFM-ominaisuuksiin, kuten ohjelmointikielen valintaan ja syntaksin väritykseen, sekä ominaisuuksiin, kuten:

- Keskitettyjen koodinäytteiden/-katkelmien sisällyttäminen ulkoisesta säilöstä.
- Välilehtiin jaettu käyttöliittymä, jolloin voidaan näyttää koodinäytteiden useita versioita eri kielillä.

## <a name="gotchas-and-troubleshooting"></a>Gotchat ja vianmääritys

### <a name="alt-text"></a>Alt-teksti

Alaviivoja sisältävää Alt-tekstiä ei hahmonneta oikein. Esimerkiksi tämän käyttämisen sijaan:

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Muotoile alaviivat näin:

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Heittomerkit ja lainausmerkit

Jos kopioit tekstiä Wordista Markdown-editoriin, teksti saattaa sisältää ns. älykkäitä (kaarevia) heittomerkkejä tai lainausmerkkejä. Nämä täytyy koodata tai muuttaa tavallisiksi heittomerkeiksi tai lainausmerkeiksi. Muuten tekstiin päätyy julkaisuvaiheessa virheellisiä merkkejä, esim. Itâ€™s

Seuraavassa on näiden välimerkkien älykkäiden versioiden koodaukset:

- Vasen (avaava) lainausmerkki: `&#8220;`
- Oikea (sulkeva) lainausmerkki: `&#8221;`
- Oikea (sulkeva) puolilainausmerkki tai heittomerkki: `&#8217;`
- Vasen (avaava) puolilainausmerkki (käytetään harvoin): `&#8216;`

### <a name="angle-brackets"></a>Kulmasulkeet

Kulmasulkeita käytetään tavallisesti osoittamaan paikkamerkkiä. Kun teet näin tekstin sisällä (ei koodissa), kulmasulkeet on koodattava. Muuten Markdown tulkitsee ne HTML-tunnisteiksi.

Koodaa `<script name>` esimerkiksi näin: `&lt;script name&gt;`

## <a name="see-also"></a>Katso myös:

### <a name="markdown-resources"></a>Markdown-resursseja

- [Johdatus Markdowniin](https://daringfireball.net/projects/markdown/syntax)
- [Docs Markdown -pikaopas](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [GitHubin Markdown-perusteet](https://help.github.com/articles/markdown-basics/)
- [Markdown-opas](https://www.markdownguide.org/)
