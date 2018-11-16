---
title: Microsoft Docs -sisällöntuottajan oppaan yleiskatsaus
description: Oppaassa kerrotaan, miten voit tuottaa sisältöä Microsoftin dokumentaatiosivustoon docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 04/17/2018
ms.openlocfilehash: dab2de80654fb55382b2ca7c9f78df36df9971dc
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609357"
---
# <a name="microsoft-docs-contributor-guide-overview"></a>Microsoft Docs -sisällöntuottajan oppaan yleiskatsaus

Tervetuloa [docs.microsoft.com](https://docs.microsoft.com) (Docs) -sisällöntuottajan oppaaseen!

Suurin osa tuottamastamme sisällöstä on avointa ja saatavilla GitHub-palvelussa. Yhä useammat Microsoft-tiimit ottavat tämän mallin käyttöön. Pull-pyyntöjä voi tehdä myös artikkeleissa, jotka eivät ole täysin avoimen lähdekoodin periaatteen mukaisia. Tämä tehostaa ja parantaa tuotesuunnittelijoiden, sisältötyöryhmien ja asiakkaiden välistä viestintää. Avoin työskentely tuo monia hyötyjä:

- Avoimet säilöt suunnittelevat avoimesti ja saavat paremmin palautetta tarvittavista asiakirjoista.
- Avoimet säilöt tarkistavat avoimesti ja voivat julkaista tärkeimmän ohjesisällön heti ensimmäisestä versiosta.
- Avoimet säilöt päivittävät avoimesti ja voivat jatkuvasti parantaa sisältöä.

Sivuston [docs.microsoft.com](https://docs.microsoft.com) käyttöliittymä on integroitu suoraan [GitHub](https://github.com)-työkulkuihin, mikä helpottaa työskentelyä entisestään. Aloita [muokkaamalla tarkasteltavaa asiakirjaa](#quick-edits-to-existing-documents). Tai auta [tarkistamalla uusia aiheita](#review-open-prs) tai [ilmoita laatuongelmista](#create-quality-issues).

> [!IMPORTANT]
> Kaikki docs.microsoft.comiin julkaisevat säilöt noudattavat joko [Microsoft Open Source -toimintasääntöjä](https://opensource.microsoft.com/codeofconduct/) tai [.NET Foundation -toimintasääntöjä](https://dotnetfoundation.org/code-of-conduct). Lisätietoja on ohjeaiheessa [Toimintasääntöjen usein kysytyt kysymykset](https://opensource.microsoft.com/codeofconduct/faq/). Tai ota yhteyttä [ opencode@microsoft.com ](mailto:opencode@microsoft.com) tai [ conduct@dotnetfoundation.org ](mailto:conduct@dotnetfoundation.org) kaikkien kysymysten tai kommenttien osalta.<br>
>
> Pienet korjaukset ja selvennykset dokumentaatioon ja julkisten säilöjen koodiesimerkit ovat [docs.microsoft.comin käyttöehtojen](https://docs.microsoft.com/legal/termsofuse) alaisia. Uudet tai merkittävät muutokset luovat kommentin pull-pyyntöön, joka pyytää sinua lähettämään osallistujien lisenssisopimuksen (CLA) verkossa, mikäli et ole Microsoftin työntekijä. Verkkolomake on täytettävä ennen kuin pull-pyyntö voidaan tarkastaa ja hyväksyä.

## <a name="quick-edits-to-existing-documents"></a>Nopeat muutokset olemassa oleviin asiakirjoihin

Nopeat muutokset tehostavat ja nopeuttavat raportointiprosessia ja pienten korjausten tekemistä asiakirjoissa. Kirjoittajat ovat vain ihmisiä, joten julkaistut asiakirjat voivat sisältää pieniä kielioppi- tai oikeinkirjoitusvirheitä. Voit raportoida virheistä ilmoittamalla ongelmasta, mutta nopeampi tapa on luoda pull-pyyntö (PR) ongelman korjaamiseksi. Lähes jokaisessa artikkelissa on alla olevan kuvan mukainen muokkauspainike. Napsauttamalla **Muokkaa**-painiketta (tai vastaavaa lokalisoitua painiketta) siirryt lähdetiedostoon GitHubissa.

![Muokkaa-linkin sijainti](./media/index/edit-article.png)

Muokkaa artikkelia napsauttamalla alla olevan kuvan mukaista kynäkuvaketta.

![Kynäkuvakkeen sijainti](./media/index/editicon.png)

> [!NOTE]
> Jos kynäkuvake näkyy harmaana, sinun on kirjauduttava GitHub-tiliisi tai luotava uusi tili.

Tee muutokset suoraan verkkoeditorissa. Voit tarkistaa muotoilun **Esikatsele muutoksia** -välilehdellä.

Kun olet tehnyt tarvittavat muutokset, siirry sivun loppuun. Anna pull-pyynnölle otsikko ja kuvaus ja valitse sitten **Ehdota tiedoston muutosta** kuten kuvassa alla:

![muutoksen ehdottaminen](./media/index/submit-pull-request.png)

Kun olet nyt ehdottanut muutosta, sinun on pyydettävä säilön omistajia noutamaan muutoksesi omaan säilöönsä. Tämä tapahtuu käyttämällä niin sanottua pull-pyyntöä. Kun valitsit **Ehdota tiedoston muutosta** yllä olevassa kuvassa, siirryit uudelle sivulle, joka näyttää seuraavalta kuvalta:

![luo pull-pyyntö](media/index/create-pull-request.png)

Valitse **Luo pull-pyyntö**, anna pull-pyynnölle nimi ja halutessasi kuvaus ja valitse **Luo pull-pyyntö** uudelleen.

Se oli siinä! Sisällön työryhmä tarkastaa ja yhdistää pull-pyyntösi. Jos olet tehnyt isompia muutoksia tekstiin, voit saada niistä palautetta.

GitHubin editointikäyttöliittymä vastaa käyttäjän säilön oikeuksia. Kuvat yllä ovat esimerkkejä osallistujien näkymästä, joilla ei ole kohdesäilön kirjoitusoikeuksia. GitHub luo automaattisesti haarauman kohdesäilöstä tiliisi. Jos sinulla on kohdesäilön kirjoitusoikeudet, GitHub luo siihen automaattisesti uuden haaran. Haaran nimi on muodossa **\<GitHubId\>-patch-n**, jossa on GitHub-tunnisteesi sekä haaran numeerinen tunnus.

Pull-pyyntöjä käytetään kaikissa muutoksissa riippumatta siitä, onko osallistujalla kirjoitusoikeuksia. Haara `master` on suojattu useimmissa säilöissä, jolloin päivitykset on lähetettävä pull-pyynnön muodossa.

Suoraan selaimessa kannattaa tehdä ainoastaan pienempiä muutoksia. Jos teet suuria lisäyksiä tai käytät edistyneitä Git-ominaisuuksia (kuten haaranhallintaa tai edistynyttä ristiriitojen ratkaisumenetelmää), sinun on [suoritettava fork-toiminto säilössä ja työskenneltävä paikallisesti](how-to-write-workflows-major.md).

> [!NOTE]
> Jos ominaisuus on käytössä, voit muokata artikkelia **millä tahansa kielellä**. Muokkauksesta riippuen tapahtuu seuraavaa:
> 1. jokainen hyväksytty lingvistinen muutos auttaa myös parantamaan konekäännösohjelmaamme
> 2. mikä tahansa artikkelin sisältöä merkittävästi muuttava muokkaus käsitellään sisäisesti, jotta muutos voidaan lisätä myös samaan englanninkieliseen artikkeliin. Näin se hyväksytyksi tullessaan lokalisoidaan kaikille kielille.
> Ehdottamasi parannukset eivät siis vaikuta positiivisesti artikkeleihin vain omalla kielelläsi vaan myös kaikilla tuetuilla kielillä.

## <a name="review-open-prs"></a>Avointen pull-pyyntöjen tarkastaminen

Voit tarkastella uusia aiheita ennen niiden julkaisua hakemalla avoimia pull-pyyntöjä. Tarkastukset noudattavat [GitHub-työnkulun](https://guides.github.com/introduction/flow/) prosessia. Julkisissa säilöissä voit tarkastella ehdotettuja päivityksiä ja uusia artikkeleita. Tarkasta ja jätä tarvittaessa kommentteja. Tarkastele mitä tahansa asiakirjasäilöämme ja tutustu sinua kiinnostaviin avoimiin pull-pyyntöihin. Yhteisön palaute ehdotetuista päivityksistä auttaa koko yhteisöä.

## <a name="create-quality-issues"></a>Laatuongelmista ilmoittaminen

Työstämme jatkuvasti asiakirjojamme. Ongelmista ilmoittaminen auttaa meitä keskittymään yhteisön kannalta tärkeimpiin ongelmiin. Mitä enemmän tietoja voit antaa, sitä helpommin voimme korjata ongelman. Kerro mitä tietoja hait. Kerro meille tarkat hakuehdot. Jos et pääse alkuun, kerro meille miten haluaisit aloittaa vieraaseen tekniikkaan tutustumisen.

Ongelmista ilmoittaminen synnyttää keskustelua tarvittavista toimista. Sisällön työryhmä voi vastata ongelmiin ideoilla lisäyksistä ja kysyä yhteisön mielipiteitä. Luodessamme luonnosta voimme pyytää sinua [tarkastamaan Pull-pyynnön](#review-open-prs).

## <a name="get-more-involved"></a>Yhteisön osallistaminen

Muut aiheet auttavat Microsoft Docs -sisällön tuottamiseen osallistuvia. Niissä käydään läpi GitHub-säilöissä työskentely, Markdown-työkalut ja Microsoft Docs -ympäristössä käytetyt laajennukset.
