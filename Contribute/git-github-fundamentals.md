---
title: Git- ja GitHub-perusteet asiakirjojen käsittelyä varten
description: Tässä artikkelissa esitellään yleisluontoisesti Git, GitHub-säilö, sen sisällön järjestämistapa ja docs.microsoft.com-sivustossa käytetyt nimeämiskäytännöt.
ms.date: 06/30/2017
ms.openlocfilehash: 8a116067fdd7d031c560abfb7055236e0bfb1a3d
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2018
ms.locfileid: "36239798"
---
# <a name="git-and-github-essentials-for-docs"></a>Git- ja GitHub-perusteet asiakirjoja varten

## <a name="overview"></a>Yleiskatsaus

Osallistuessasi asiakirjasisällön käsittelyyn joudut tekemisiin useiden eri työkalujen ja prosessien kanssa. Työskentelet muiden osallistujien kanssa rinnakkain samassa projektissa, mahdollisesti täsmälleen saman sisällön parissa ja ehkä jopa samanaikaisesti. Tämä kaikki on mahdollista Git- ja GitHub-ohjelmiston kautta.

Git on avoimen lähdekoodin versiontarkistusjärjestelmä. Se helpottaa tällaista projektiyhteistyötä mahdollistamalla *jaetun versionhallinnan* tiedostoissa, joita säilytetään reaaliaikaisen käytön aikana *säilöissä*. Lyhyesti sanottuna Git mahdollistaa useiden eri osallistujien ajan mittaan tekemän työn työvirtojen integroinnin tietyssä säilössä.

GitHub on Git-säilöjen, kuten [docs.microsoft.com](https://docs.microsoft.com)-sisällön säilytykseen tarkoitettujen säilöjen, verkkopohjainen isännöintipalvelu. Missä tahansa projektissa GitHub isännöi pääsäilöä, josta osallistujat voivat tehdä kopioita omaa työskentelyään varten.

## <a name="git"></a>Git

Jos keskitetyt versiontarkistusjärjestelmät (kuten Team Foundation Server, SharePoint ja Visual SourceSafe) ovat sinulle tuttuja, huomaat, että Gitin jaetun mallin tukena käytetään ainutlaatuista osallistumistyönkulkua ja -terminologiaa. Esimerkiksi tiedoston lukitsemista, joka tavallisesti liittyy sisään- ja uloskuittaustoimintoihin, ei käytetä. Git itse asiassa käsittelee muutoksia vieläkin hienommalla tasolla vertaamalla tiedostoja tavu kerrallaan.

Git käyttää myös kerrostettua rakennetta projektin sisällön tallennukseen ja hallintaan:

- *Säilö*: tämä on korkeimman tason tallennusyksikkö *.* Säilö sisältää yhden tai useamman haaran.
- *Haara*: tallennusyksikkö, joka sisältää tiedostot ja kansiot, jotka muodostavat projektin sisältöjoukon. Haarat erottavat toisistaan työvirrat (joita yleensä kutsutaan versioiksi). Eri osallistujien työpanokset tallentuvat ja rajoittuvat aina tiettyyn haaraan. Kaikki säilöt sisältävät oletushaaran (jota tavallisesti kutsutaan päähaaraksi) ja yhden tai useampia haaroja, jotka on tarkoitus yhdistää takaisin päähaaraan. Päähaara toimii nykyisenä versiona ja projektin yksittäisenä todellisena tietolähteenä. Kaikki muut säilön haarat luodaan päähaarasta.

Osallistujat päivittävät ja käsittelevät säilöjä vuorovaikutuksessa Git-palvelun kanssa sekä paikallisella tasolla että GitHub-tasolla seuraavilla tavoilla:

- Paikallisesti hyödyntämällä erilaisia työkaluja, kuten Git Bash -konsolia, joka tukee Git-komentoja paikallisten säilöjen hallinnassa ja kommunikoinnissa GitHub-säilöjen kanssa
- Käyttämällä [www.github.com](https://www.github.com)-sivustoa, johon on integroitu Git-palvelu pääsäilöön takaisin virtaavien työpanosten yhteensovitusta varten

## <a name="github"></a>GitHub

> [!NOTE]
> Vaikka asiakirjojen ohjaus perustuu GitHubin käyttöön, jotkin työryhmät käyttävät Visual Studio Team Servicesiä Git-säilöjen isännöintiin. Visual Studio Team Explorer -asiakasohjelmassa on graafinen käyttöliittymä Team Services -säilöjen hallintaan vaihtoehtona komentorivin Git-komentojen käytölle.
> </br>
> Myös monet seuraavista ohjeista on kehitetty parhaina käytäntöinä Azure-palvelusisällön isännöinnistä GitHubissa vuosien varrella saadun kokemuksen pohjalta. Ne voivat olla tarpeen joidenkin asiakirjasäilöjen tapauksessa.

Kaikki työnkulut alkavat ja päättyvät GitHubin tasolla, jolla sijaitsee kaikkien asiakirjaprojektien ensisijainen säilö. Kopiot, jotka osallistujat luovat omiin tarpeisiinsa, jaetaan useisiin tietokoneisiin. Nämä kopiot yhdistetään lopulta takaisin projektin GitHub-pääsäilöön.

### <a name="directory-organization"></a>Hakemiston järjestely

Kuten edellä mainittiin, projektin oletus- eli päähaara toimii projektin sisällön nykyisenä versiona. Päähaaran – ja siitä luotujen haarojen – sisältö on löyhästi suhteessa artikkelien järjestelyyn vastaavilla asiakirjojen sivuilla. Alihakemistoja käytetään samankaltaisen sisällön (kuten palvelujen), mediasisällön (kuten kuvatiedostojen) ja ns. sisällytettyjen tiedostojen (jotka mahdollistavat sisällön uudelleenkäytön) erotteluun.

Löydät `articles`-päähakemiston tavallisesti säilön juuresta. Artikkelihakemisto sisältää joukon alihakemistoja. Alihakemistojen artikkelit on muotoiltu Markdown-tiedostoiksi, joilla on tiedostonimen *.md*-tunniste. Jotkin useita palveluja tukevat säilöt käyttävät yleistä `/articles`-alihakemistoa. Esimerkiksi [ https://github.com/microsoft/Azure-Docs](https://github.com/microsoft/Azure-Docs)-säilö on tällainen. Muut säilöt saattavat käyttää palvelukohtaista nimeä. Tällainen on esimerkiksi [ https://github.com/microsoft/IntuneDocs ](https://github.com/microsoft/IntuneDocs)-säilö, joka käyttää `/IntuneDocs`-nimeä.

Tämän hakemiston juuresta löydät yleisiä artikkeleita, jotka liittyvät koko palveluun tai tuotteeseen. Löydät tavallisesti myös toisen alihakemistojen sarjan, joka vastaa toimintoja ja palveluja tai yleisiä skenaarioita. Esimerkiksi Azuren näennäiskoneen artikkelit ovat `/virtual-machines`-alihakemistossa ja Intunen ”ymmärtämisen ja tutkimisen” artikkelit ovat `/understand-explore`-alihakemistossa.

### <a name="media-subdirectory"></a>Media-alihakemisto

Jokainen artikkelihakemisto sisältää `/media`-alihakemiston vastaavia mediatiedostoja varten. Mediatiedostot sisältävät kuvia, joita käyttävät artikkelit, joissa on kuvaviitteitä.

### <a name="includes-subdirectory"></a>Sisältää alihakemiston

Mahdollinen kahden tai useamman artikkelin välillä jaettu uudelleenkäytettävä sisältö sijoitetaan `/includes`-alihakemistoon `articles`-päähakemistossa. Jos Markdown-tiedostossa käytetään sisällytettyä tiedostoa, vastaava sisällytyksen Markdown-tunniste sijoitetaan paikkaan, johon sisällytetyn tiedoston täytyy viitata.

Saat lisäohjeita artikkelista [Markdownin käyttäminen: sisällytykset](how-to-write-use-markdown.md#includes).

### <a name="markdown-file-template"></a>Markdown-tiedostomalli

Kunkin säilön juurihakemistossa on yleensä käytännöllisyyden vuoksi Markdown-mallitiedosto, jonka nimi on `template.md`. Voit käyttää tätä mallitiedostoa lähtökohtana, jos haluat luoda uuden artikkelin säilöön lähetettäväksi. Tiedostossa on seuraava sisältö:

- Tiedoston yläosassa sijaitseva **metatieto-otsikko**, joka on hahmoteltu kahdelle kolmen yhdysmerkin viivalle. Se sisältää erinäisiä tunnisteita, joita käytetään artikkeliin liittyvien tietojen seurantaan. Artikkelin metatiedot mahdollistavat tietyt toiminnot, kuten tekijän attribuution, osallistujan attribuution, navigointipolut ja artikkelin kuvaukset. Se sisältää myös SEO-optimointeja ja raportointiprosesseja, joita Microsoft käyttää sisällön suorituskyvyn arviointiin. Metatiedot ovat siis tärkeitä!
- **Metatieto-osio**, joka kuvaa eri metatietotunnisteet ja -arvot. Jos et ole varma metatieto-osiossa käytettävistä arvoista, voit jättää ne tyhjiksi tai kommentoida niitä lisäämällä niiden eteen ristikkomerkin (#), jolloin säilön pull-pyyntöjen tarkistaja tarkistaa/täydentää ne.
- **Esimerkkejä Markdownin käytöstä** artikkelin osien muotoilussa.
- Yleisiä **ohjeita eri ilmoitustyyppien yhteydessä käytettävien Markdown-laajennusten käytöstä**.
- Esimerkkejä **videon upottamisesta** iframe-kehyksen avulla.
- Yleiset **erityisissä ohjausobjekteissa, kuten painikkeissa ja valitsimissa, käytettävien docs.microsoft.com-laajennusten käyttöohjeet**.

## <a name="pull-requests"></a>Pull-pyynnöt

*Pull-pyyntö* on käytännöllinen menetelmä, jonka avulla osallistuja voi ehdottaa oletushaaraan tehtäviä muutoksia. Muutokset (joita kutsutaan myös *vahvistuksiksi*) tallennetaan osallistujan haaraan, jotta GitHub voi ensin mallintaa vaikutuksen, joka niiden *yhdistämisellä* oletushaaraan on. Pull-pyyntö toimii myös mekanismina, jonka avulla osallistuja saa palautetta koonti- ja vahvistusprosessista ja pull-pyynnön tarkistaja voi ratkaista mahdolliset ongelmat tai vastata mahdollisiin kysymyksiin ennen muutosten yhdistämistä oletushaaraan.

Pull-pyynnön avulla osallistumiseen on kaksi eri tapaa ehdotettavien muutosten koon mukaan. Tätä aihetta käsitellään yksityiskohtaisesti jäljempänä tämän oppaan [GitHub-työnkulku](how-to-write-workflows-major.md)-osiossa.

<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
<!---- NOTE: these links are saved for future use in another/new article; no longer used above in this article --->
[Visual-Studio-Page]:(https://docs.microsoft.com/en-us/visualstudio/index)
[Visual-Studio-Repo-Internal]:(https://github.com/Microsoft/vsdocs)
[Visual-Studio-Repo-External]:(https://github.com/Microsoft/visualstudio-docs)
[Visual-Studio-SO]: (https://stackoverflow.com/search?q=Visual+Studio+2017)
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp
[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: https://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: https://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: https://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: https://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: https://stackoverflow.com/tags
[Forum-SO-Intune]: https://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: https://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: https://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: https://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/
