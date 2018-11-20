---
title: .NET-asiakirjasäilöihin osallistumisen prosessi
description: Tässä artikkelissa esitellään lyhyesti .NET-asiakirjasäilöihin osallistuminen. Saat tietoa käytetyistä säilöistä, sisällön organisoinnin prosessi sekä koodinäytteiden ja muiden resurssien hallinnan käytännöt.
ms.date: 11/07/2018
ms.openlocfilehash: b83a3080f1abd4df8caaa9d10859760006216e86
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609758"
---
# <a name="process-for-contributing-to-net-docs"></a>.NET-asiakirjoihin osallistumisen prosessi

Arvostamme yhteisön jäsenten osallistumista asiakirjojen tuotantoon. Seuraava luettelo sisältää joitakin sääntöjä, jotka sinun täytyy pitää mielessä julkaistessasi sisältöä .NET-asiakirjoihin:

- **ÄLÄ** yllätä meitä suurilla pull-pyynnöillä. Luo sen sijaan aihe ja aloita keskustelu, niin voimme sopia jatkotoimista ennen kuin käytät asiaan paljon aikaa.
- **NOUDATA** näitä ohjeita ja [sävyä](dotnet-voice-tone.md) koskeviin ohjeisiin.
- **KÄYTÄ** [mallitiedostoa](dotnet-style-guide.md) työsi pohjana.
- **LUO** erillinen haara haaraumaasi ennen artikkelien muokkaamista.
- **NOUDATA** [GitHub-työnkulkua](https://guides.github.com/introduction/flow/).
- **JULKAISE** blogikirjoituksia ja twiittejä (tai mitä tahansa) sisältöjulkaisuistasi säännöllisesti.

Näitä ohjeita noudattamalla voit varmistaa paremman käyttökokemuksen itsellesi ja meille.

## <a name="make-a-contribution-to-net-docs"></a>Julkaise sisältöä .NET-asiakirjoihin

**Vaihe 1:** Ohita tämä vaihe, jos teet vain vähäisiä muutoksia. Jos olet kiinnostunut kirjoittamaan uutta sisältöä tai muokkaamaan sisältöä perusteellisesti, avaa uusi [aihe](https://github.com/dotnet/docs/issues), jossa kuvaat, mitä haluat tehdä.

**Asiakirjakansion** sisältö on järjestetty osioihin, ja ne näkyvät sisällysluettelossa. Määritä, missä kohtaa haluat aiheen näkyvän sisällysluettelossa. Pyydä palautetta ehdotuksestasi.

-tai-

Voit valita olemassa olevista aiheista, joihin otetaan vastaan uutta sisältöä yhteisöltä. [.NET-yhteisön osallistujien projektit](https://github.com/dotnet/docs/projects/35) sisältävät monia aiheita, joihin yhteisön jäsenet voivat osallistua. Voit valita aiheita seuraavilta osa-alueilta kiinnostuksesi ja sitoutumishalukkuutesi mukaan:

- **Ylläpito**. Tähän luokkaan kuuluu melko yksinkertaisia muutoksia, kuten katkenneiden tai virheellisten linkkien korjauksia, puuttuvien koodinäytteiden lisäyksiä tai rajoitettujen sisältöongelmien korjauksia. Joissakin tapauksissa näihin aiheisiin voi liittyä suuri määrä tiedostoja. Tällöin sinun pitää ilmoittaa meille ennen aloittamista, mitä haluat muokata. Lisää aiheeseen kommentti, jossa kerrot, että teet siihen muokkauksia.

- **Sisältöpäivitykset**. Asiakirjojen suuren määrän vuoksi sisältö helposti vanhenee ja vaatii muokkauksia. Lisäksi tiettyjä sisältöjä on eri syistä esiintynyt kaksin- tai jopa kolminkertaisesti. Sisällön päivittämiseen kuuluu sen varmistaminen, että yksittäiset aiheet ovat ajan tasalla, tai sisällön muokkaaminen ominaisuusalueella, jotta sama sisältö ei esiinny kahteen kertaan. Pitää myös varmistaa, että kaikkea yksilöllistä sisältöä säilytetään pienemmässä asiakirjajoukossa.

- **Uuden sisällön luominen**. Jos olet kiinnostunut oman aiheen luomisesta, tässä näet aiheita, joista haluaisimme sisältöä asiakirjoihimme. Ilmoita kuitenkin meille ennen kuin aloitat aiheen käsittelyn. Jos olet kiinnostunut kirjoittamaan muusta kuin täällä mainitusta aiheesta, aloita aihe.

Voit myös tutustua [avoimien aiheiden](https://github.com/dotnet/docs/issues) luetteloon ja osallistua niiden aiheiden käsittelyyn, joista olet kiinnostunut. Merkitsemme yhteisölle avoimet aiheet tunnisteella [saatavilla](https://github.com/dotnet/docs/labels/up-for-grabs). Niihin vaaditaan yleensä vähäinen määrä sisältöä, ja ne sopivat hyvin osallistujan ensimmäisiksi aiheiksi. Kannustamme yhteisömme kokeneita osallistujia katsomaan, onko luettelossa jotain heitä kiinnostavia aiheita. Jos kiinnostava aihe löytyy, lisää kommentti ja kysy siinä, onko aihe avoin.

Kun olet valinnut tehtävän käsiteltäväksi, luo GitHub-tili [aloitusohjeiden](get-started-setup-github.md) mukaisesti ja määritä ympäristösi.

**Vaihe 2:** Tee säilöistä `/dotnet/docs`, `dotnet/samples`, `dotnet/dotnet-api-docs`, `dotnet/roslyn-api-docs` tai `dotnet/ml-api-docs` haarat tarpeen mukaan ja luo haara tekemiäsi muutoksia varten.

Jos teet pieniä muutoksia, katso ohjeet GitHubin käyttämisestä muutosten tekemiseen osallistujaoppaan [etusivulta](index.md#quick-edits-to-existing-documents).

**Vaihe 3:** Tee muutokset tähän uuteen haaraan.

Jos aihe on uusi, voit käyttää tätä [mallitiedostoa](dotnet-style-guide.md) pohjana. Se sisältää kirjoitusohjeita, ja siinä kerrotaan myös kunkin artikkelin vaatimat metatiedot, kuten tekijätiedot.

Siirry kansioon, joka määritettiin artikkelisi sisällysluettelolle vaiheessa 1. Kansio sisältää kyseisen osion kaikkien artikkelien Markdown-tiedostot. Luo tarvittaessa uusi kansio tiedostojasi varten. Osion pääartikkeli on *index.md*. Luo kuville ja muille staattisille resursseille alikansio **media** siihen kansioon, joka sisältää artikkelisi, ellei alikansio ole jo olemassa. Luo **media**-kansioon alikansio, jonka nimi on artikkelin nimen mukainen (paitsi index-tiedostolle). Näytekoodin täytyy olla `dotnet/samples`-säilössä, kuten on kerrottu [näytteitä](#contributing-to-samples) koskevassa osiossa.

Noudata asianmukaista Markdown-syntaksia. Esimerkkejä yleisistä on [mallien ja markdownien pikaoppaassa](dotnet-style-guide.md).

## <a name="example-structure"></a>Esimerkkirakenne

    docs
      /about
      /core
        /porting
          porting-overview.md
          /media
            /porting-overview
                portability_report.png

**Vaihe 4:** Tee haarastasi pull-pyyntö päähaaraan.

> [!IMPORTANT]
> [Automaattisen kommentoinnin](how-to-write-workflows-major.md#review-and-sign-off) toiminnot eivät ole tällä hetkellä käytettävissä .NET-asiakirjasäilöissä. .NET-asiakirjatiimi tarkistaa ja yhdistää pull-pyyntösi.

Kunkin pull-pyynnön tulisi aina koskea vain yhtä ongelmaa. Pull-pyynnöllä voidaan muokata yhtä tai useaa tiedostoa. Jos olet tekemässä useita korjauksia eri tiedostoihin, on suositeltavaa tehdä erilliset pull-pyynnöt. Jos olet luomassa näytteitä ja päivittämässä markdownia, sinun täytyy luoda erillinen pull-pyyntö näytteitä varten.

Jos pull-pyyntösi korjaa olemassa olevan ongelman, lisää avainsana `Fixes #Issue_Number` muutosvahvistusviestiin tai pull-pyynnön kuvaukseen. Tällä tavalla ongelma suljetaan automaattisesti, kun pull-pyyntö yhdistetään. Lisätietoa on artikkelissa [Ongelmien sulkeminen muutosvahvistusviesteillä](https://help.github.com/articles/closing-issues-via-commit-messages/).

.NET-tiimi tarkistaa pull-pyyntösi ja ilmoittaa sinulle, onko muita päivityksiä/muutoksia, jotka on tehtävä, jotta pyyntösi voidaan hyväksyä.

**Vaihe 5:** Tee tarvittavat muutokset tiimin kanssa käymiesi keskustelujen mukaisesti.

Ylläpitäjät yhdistävät pull-pyyntösi päähaaraan, kun on saatu palaute ja muutoksesi on hyväksytty.

Siirrämme muutoksesi push-toiminnolla päähaarasta live-haaraan, jonka jälkeen voit nähdä muutoksesi kohteessa https://docs.microsoft.com/dotnet/. Teemme julkaisut tavallisesti päivittäin arkipäivinä. Ylläpitotoimet voivat viivästyttää julkaisemista muutaman päivän.

## <a name="contributing-to-samples"></a>Osallistuminen näytteiden tuotantoon

[Dotnet/samples](https://github.com/dotnet/samples)-säilö sisältää kaikki näytekoodit, jotka sisältyvät kuhunkin aiheeseen .NET-asiakirjoissa. Eri projektit on järjestetty alikansioihin. Nämä alikansiot on järjestetty samalla tavalla kuin .NET-asiakirjat.

Erittelemme säilössämme olevat koodit seuraavasti:

- Näytteet: lukijat voivat ladata ja suorittaa näytteitä. Kaikkien näytteiden pitäisi olla valmiita sovelluksia tai kirjastoja. Jos näyte muodostaa kirjaston, sen pitää sisältää vähintään yksikkötestit tai sovellus, joka antaa lukijoiden suorittaa koodin. Niissä käytetään usein montaa teknologiaa, ominaisuutta tai työkalupakettia. Kunkin näytteen readme.md-tiedosto viittaa artikkeliin, jotta voit lukea lisää kussakin näytteessä käsitellyistä käsitteistä.
- Katkelmat: edustavat suppeampaa käsitettä tai tehtävää. Ne voidaan kääntää, mutta niitä ei ole tarkoitettu kokonaisiksi sovelluksiksi. Niiden suorittamisen pitäisi onnistua, mutta ne eivät ole tyypillisen skenaarion esimerkkisovelluksia. Niistä pyritään sen sijaan tekemään niin pieniä kuin mahdollista yksittäisen käsitteen tai ominaisuuden esittämiseksi. Niiden pitäisi olla koodinsa laajuudelta enintään yhden näytön kokoisia.

Vie kaikki live-haarojen koodit [dotnet/näytteet](https://github.com/dotnet/samples)-säilöön. Olemme kehittämässä mallia, jossa näytekansion rakenne vastaa asiakirjakansion rakennetta. Noudatamme seuraavia standardeja:

- Ylimmän tason *katkelmien* kansio sisältää katkelmia pienistä, tärkeimmistä näytteistä.
- Ohjelmointirajapinnan viitenäytteet ovat kansiossa, jonka polku on seuraavaa muotoa: *katkelmat/\<kieli>/ohjelmointirajapinta/\<nimitila>/\<ohjelmointirajapinnan nimi>*.
- Muut ylimmän tason kansioiden nimet vastaavat *asiakirjat*-säilön ylimmän tason kansioiden nimiä. Esimerkki: asiakirjat-säilössä on *koneoppiminen/opetusohjelmat*-kansiot, ja koneoppimisen opetusohjelmien näytteet ovat *näytteet/koneoppiminen/opetusohjelmat*-kansiossa.

Lisäksi kaikkien *ydin*- ja *vakio*-kansioissa olevien näytteiden pitäisi kääntyä ja toimia kaikissa .NET Coren tukemissa alustoissa. CI-koontijärjestelmämme tekee tämän pakotetusti. Ylimmän tason *sovelluskehys*-kansio sisältää näytteitä, jotka on käännetty ja vahvistettu vain Windowsille.

Näyteprojektien pitäisi kääntyä ja toimia mahdollisimman laajassa joukossa ympäristöjä, joita näyte tukee. Tämä tarkoittaa käytännössä .NET Core -pohjaisten konsolisovellusten kääntämistä aina kun mahdollista. Tietylle verkko- tai käyttöliittymäsovelluskehykselle tarkoitettujen näytteiden tulee lisätä nämä työkalut tarpeen mukaan. Näitä ovat esimerkiksi verkkosovellukset, mobiilisovellukset tai WPF- tai WinForms-sovellukset.

Tavoitteenamme on kehittää CI-järjestelmä kaikelle koodille. Kun teet päivityksiä näytteisiin, varmista, että kukin päivitys on osa käännettävää projektia. Ihanteellista olisi, jos lisäisit näytteisiin myös oikeellisuustestit.

Kunkin luomasi kokonaisen näytteen tulee sisältää *readme.md*-tiedosto. Tämän tiedoston tulee sisältää lyhyt näytteen kuvaus (yksi tai kaksi kappaletta). *readme.md*-tiedostosi tulee kertoa lukijoille, mitä he oppivat näytteeseen tutustumisesta. *readme.md*-tiedoston tulee sisältää myös linkki [.NET-dokumentaatiosivustolla](https://docs.microsoft.com/dotnet/welcome) olevaan live-asiakirjaan. Jos haluat määrittää, että tietty kyseisessä säilössä oleva tiedosto yhdistetään kyseiseen sivustoon, korvaa säilön polun `/docs` osoitteella `http://docs.microsoft.com/dotnet`.

Aiheesi tulee myös sisältämään linkit siihen näytteeseen. Tee suora linkitys näytteen GitHub-kansioon.

### <a name="writing-a-new-snippet-or-sample"></a>Uuden katkelman tai näytteen kirjoittaminen

1. Näytteesi **on oltava osa käännettävää projektia**. Jos mahdollista, projektien pitäisi olla käännettävissä kaikissa .NET Coren tukemissa ympäristöissä. Poikkeuksia ovat näytteet, jotka esittelevät ympäristökohtaisen ominaisuuden tai ympäristökohtaisen työkalun.

2. Näytteesi tulee yhdenmukaisuuden vuoksi olla [corefx-koodaustyylin](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md) mukainen.

    - Suosimme lisäksi `static`-menetelmiä esiintymämenetelmien sijaan, kun esitellään jotain, joka ei vaadi uuden objektin esiintymän luomista.

3. Näytteesi tulee sisältää **asianmukainen poikkeusten käsittely**. Sen tulee käsitellä kaikki poikkeukset, jotka todennäköisesti ilmenevät näytteen kontekstissa. Esimerkiksi näytteen, joka kutsuu [Console.ReadLine](https://docs.microsoft.com/dotnet/api/system.console.readline)-menetelmää käyttäjän syötteen vastaanottamiseen, tulee käyttää asianmukaista poikkeustenkäsittelyä, kun syötemerkkijono välitetään argumenttina menetelmälle. Samoin jos näytteesi odottaa menetelmäkutsun epäonnistuvan, siitä seuraava poikkeus tulee käsitellä. Käsittele aina menetelmässä ilmenevät menetelmän omat poikkeukset perusluokkapoikkeusten kuten [Exception](https://docs.microsoft.com/dotnet/api/system.exception)- [SystemException](https://docs.microsoft.com/dotnet/api/system.systemexception)-poikkeusten sijaan.

4. Jos näytteesi kääntää erillisen paketin, sinun täytyy sisällyttää siihen CI-koontijärjestelmämme käyttämät suorituspalvelut näytteesi käyttämien suorituspalveluiden lisäksi:
    - `win7-x64`
    - `win8-x64`
    - `win81-x64`
    - `ubuntu.16.04-x64`

Olemme pian tuomassa saataville näiden projektien kääntämiseen tarvittavan CI-järjestelmän.

Näytteen luominen:

1. Julkaise [aihe](https://github.com/dotnet/docs/issues) tai lisää kommentti olemassa olevaan aiheeseen, jota olet muokkaamassa.
2. Kirjoita aihe, jossa kuvaillaan näytteessäsi esitellyt konseptit (esimerkki: `docs/standard/linq/where-clause.md`).
3. Kirjoita näytteesi (esimerkki: `WhereClause-Sample1.cs`).
4. Luo Program.cs, joka sisältää näytteitäsi kutsuvan Main-aloituskohdan. Jos se on jo olemassa, lisää kutsu näytteeseesi:
    ```csharp
    public class Program
    {
        public void Main(string[] args)
        {
            WhereClause1.QuerySyntaxExample();

            // Add the method syntax as an example.
            WhereClause1.MethodSyntaxExample();
        }
    }
    ```
.NET Core -katkelma tai -näyte käännetään .NET Core -komentorivikäyttöliittymässä, joka voidaan asentaa [.NET Core SDK](https://www.microsoft.com/net/download):n kanssa. Käännä ja suorita näytteesi:

1. Mene näytekansioon ja käännä näyte virheiden tarkistamiseksi:

    ```console
    dotnet build
    ```
2. Suorita näytteesi:

    ```console
    dotnet run
    ```

3. Lisää readme.md näytteesi päähakemistoon. 

   Sen tulee sisältää lyhyt koodin kuvaus sekä viite artikkeliin, joka viittaa näytteeseen.

Ellei muuta ole mainittu, kaikki näytteet voidaan kääntää komentorivillä missä tahansa .NET Corea tukevassa ympäristössä. Jotkin näytteet ovat Visual Studiota varten ja vaativat Visual Studio 2017:n tai uudemman. Lisäksi jotkin näytteet esittelevät ympäristökohtaisia ominaisuuksia ja vaativat tietyn ympäristön. Muut näytteet ja katkelmat vaativat .NET Frameworkin ja toimivat Windows-ympäristöissä, ja niitä varten tarvitaan sen Framework-version Developer Packin, jolle näyte tai katkelma tehdään.

## <a name="the-c-interactive-experience"></a>Vuorovaikutteinen C#-käyttö

Kaikissa artikkelin sisältämissä näytteissä lähdekieli ilmaistaan [kielitunnisteella](how-to-write-use-markdown.md#code-snippets).  Lyhyissä C#-koodinäytteissä voidaan käyttää `csharp-interactive`-kielitunnistetta ilmaisemaan C#-näytettä, joka voidaan suorittaa selaimessa. (Tekstiin sidotuissa koodinäytteissä käytetään `csharp-interactive`-tunnistetta. Käytä lähteestä otetuissa katkelmissa `code-csharp-interactive`-tunnistetta.) Nämä koodinäytteet näyttävät koodi-ikkunan ja tietoikkunan artikkelissa. Tietoikkunassa näkyvät vuorovaikutteisen koodin suorittamisen mahdolliset tulokset, kun käyttäjä on suorittanut näytteen.

Vuorovaikutteinen C#-käyttö muuttaa näytteiden käsittelyn tapaa. Vierailijat näkevät tulokset suorittamalla näytteen. Eri tekijöistä voidaan päätellä, pitäisikö näytteen tai sitä vastaavan tekstin sisältää tiedot tuloksista.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Milloin odotetut tulokset kannattaa näyttää suorittamatta näytettä?

- Aloittelijoille tarkoitettujen näytteiden tulee näyttää tulokset, jotta lukijat voivat verrata omien töidensä tuloksiin, sekä odotettu vastaus.
- Näytteissä, joissa tulokset ovat keskeinen osa aihetta, tulee näyttää nämä tulokset. Esimerkiksi muotoiltua tekstiä koskevissa artikkeleissa tulee näyttää tekstin muotoilu ilman, että näytettä tarvitsee suorittaa.
- Kun sekä näyte että odotettu tulos on lyhyt, harkitse tuloksen näyttämistä. Se säästää jonkin verran aikaa.
- Artikkeleissa, joissa kerrotaan, miten nykyinen maa-asetus tai muuttumaton maa-asetus vaikuttaa tulokseen, tulee selittää odotettu tulos. Vuorovaikutteinen REPL (Read Evaluate Print Loop) suoritetaan Linux-pohjaisessa isännässä. Oletusmaa-asetus ja muuttumaton maa-asetus tuottavat eri tulokset eri käyttöjärjestelmissä ja koneissa. Artikkelissa tulee selittää, millaiset tulokset ovat Windows-, Linux- ja Mac-järjestelmissä.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Milloin odotettu tulos kannattaa jättää pois näytteestä?

- Artikkeleissa, joissa näyte luo suuremmat tulokset, tuloksia ei kannata näyttää kommenteissa. Muutoin koodi jää piiloon, kun näyte on suoritettu.
- Tulokset kannattaa jättää pois myös artikkeleissa, joissa näyte esittelee aiheen mutta joissa tulokset eivät ole olennaiset aiheen ymmärtämiseen. Tällainen voi olla esimerkiksi koodi, joka suorittaa LINQ-kyselyn kyselysyntaksin esittämiseksi ja näyttää sitten tuloskokoelman jokaisen kohteen.

> [!NOTE]
> Saatat huomata, että jotkin aiheet eivät tällä hetkellä ole täällä määritettyjen ohjeiden mukaiset. Kehitämme sivustoa jatkuvasti, jotta saamme siitä mahdollisimman yhdenmukaisen. Tutustu [avoimiin aiheisiin](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3A%22%3Abookmark_tabs%3A+Information+Architecture%22), joita tällä hetkellä seuraamme yhdenmukaisuuden parantamiseksi.

## <a name="contributor-license-agreement"></a>Osallistujan käyttöoikeussopimus

Sinun tulee allekirjoittaa [.NET Foundation -osallistujien lisenssisopimus](https://cla.dotnetfoundation.org) ennen pull-pyyntösi yhdistämistä. Tämä vaaditaan kerran .NET Foundation-projekteja varten. Lisätietoja [osallistujien lisenssisopimuksesta](http://en.wikipedia.org/wiki/Contributor_License_Agreement) on Wikipediassa.

Sopimus: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

Sinun ei tarvitse allekirjoittaa sopimusta etukäteen. Voit kloonata, suorittaa fork-toimintoja ja lähettää pull-pyyntösi tavalliseen tapaan. Kun pull-pyyntösi on luotu, CLA-botti luokittelee sen. Jos muutos on pieni (esimerkiksi korjasit kirjoitusvirheen), pull-pyynnölle asetetaan tunniste `cla-not-required`. Muutoin sille asetetaan luokitus `cla-required`. Kun olet allekirjoittanut osallistujan lisenssisopimuksen, nykyinen ja tulevat pull-pyyntösi saavat tunnisteen `cla-signed`.
