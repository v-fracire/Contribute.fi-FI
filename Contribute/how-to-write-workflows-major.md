---
title: GitHub-osallistumistyönkulku merkittäville tai pitkäkestoisille muutoksille
description: Tässä artikkelissa kerrotaan, miten merkittäviä osallistumistyönkulkuja käytetään hyväksi osallistuttaessa docs.microsoft.comin artikkeleiden tekoon.
ms.date: 08/30/2017
ms.openlocfilehash: 31f9421fc5edbc2f65c5ff20a86da08c70211ec7
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2018
ms.locfileid: "36239821"
---
# <a name="github-contribution-workflow-for-major-or-long-running-changes"></a>GitHub-osallistumistyönkulku merkittäville tai pitkäkestoisille muutoksille

> [!IMPORTANT]
> Kaikki säilöt, jotka lähettävät julkaisuja docs.microsoft.comiin, noudattavat joko [Microsoft Open Source -toimintasääntöjä](https://opensource.microsoft.com/codeofconduct/) tai [.NET Foundation -toimintasääntöjä](https://dotnetfoundation.org/code-of-conduct). Lisätietoja on ohjeaiheessa [Toimintasääntöjen usein kysytyt kysymykset](https://opensource.microsoft.com/codeofconduct/faq/). Tai ota yhteyttä [ opencode@microsoft.com ](mailto:opencode@microsoft.com) tai [ conduct@dotnetfoundation.org ](mailto:conduct@dotnetfoundation.org) kaikkien kysymysten tai kommenttien osalta.<br>
>
> Pienet korjaukset ja selvennykset dokumentaatioon ja julkisten säilöjen koodiesimerkit ovat [docs.microsoft.comin käyttöehtojen](https://docs.microsoft.com/legal/termsofuse) alaisia. Uudet tai merkittävät muutokset luovat kommentin Pull-pyyntöön, joka pyytää sinua lähettämään osallistujien lisenssisopimuksen (CLA) verkossa, mikäli et ole Microsoftin työntekijä. Verkkolomake on täytettävä ennen kuin Pull-pyyntö voidaan yhdistää.

## <a name="overview"></a>Yleiskatsaus

Tämä työnkulku sopii osallistujalle, jonka täytyy tehdä merkittävä muutos tai joka osallistuu säännöllisesti säilön käyttöön. Säännöllisillä osallistujilla on tavallisesti jatkuvia (pitkäkestoisia) muutoksia, jotka käyvät läpi useita koontiversio-/validointi-/valmisteluvaiheita tai kestävät useita päiviä ennen Pull-pyynnön hyväksymistä ja yhdistämistä.

Tällaisia osallistumistyöpanoksia ovat esimerkiksi:

[!INCLUDE[contribute-major-changes-change-definition](includes/contribute-how-to-write-workflows-major-change-definition.md)]

### <a name="terminology"></a>Sanasto

Ennen kuin aloitat, käydäänpä ensin läpi muutamia Git- ja GitHub-ehtoja ja -nimityksiä, joita tässä työnkulussa käytetään. Älä murehdi niiden täydellistä ymmärtämistä vielä. Riittää, että tiedostat, että opit niistä lisää kohta, ja että voit palata takaisin tähän osioon, jos jokin määritelmä pitää tarkistaa.

| Nimi | Kuvaus |
|-----------|-------------|
|haarauma|Käytetään tavallisesti substantiivina, kun puhutaan GitHub-pääsäilön kopiosta. Käytännössä haarautuma on vain säilö muiden joukossa. Se on kuitenkin erityinen siinä mielessä, että GitHub ylläpitää yhteyttä takaisin pääsäilöön. Sitä käytetään joskus verbinä, kuten ”Säilöön täytyy ensin tehdä haarauma”.|
|etä/etäsäilö|Nimetty yhteys etäsäilöön, kuten ”alkuperä”- ja ”ylätaso”-etäsäilöön. Git viittaa näihin etäsäilöinä, koska niitä käytetään puhuttaessa säilöstä, joka sijaitsee toisella tietokoneella. Tässä työnkulussa etäsäilö on aina GitHub-säilö.|
|alkuperä|Sen yhteyden nimi, joka kulkee paikallisen säilösi ja sen säilön välillä, josta se on kloonattu. Tässä työnkulussa alkuperä edustaa yhteyttä haaraumaasi. Sitä käytetään toisinaan nimityksenä itse alkuperäsäilölle, kuten ”Muista siirtää muutokset alkuperään”.|
|ylätaso|Samoin kuin alkuperäetäsäilö, ylätaso on toisen säilön nimetty yhteys. Tässä työnkulussa ylätaso edustaa yhteyttä paikallisen säilösi ja sen pääsäilön välillä, josta sinun haaraumasi on luotu. Sitä käytetään toisinaan nimityksenä itse ylätason säilölle, kuten ”Muista ottaa muutokset ylätasolta”.|

## <a name="workflow"></a>Työnkulku

>[!IMPORTANT]
> Jos et ole jo tehnyt niin, sinun on suoritettava vaiheet [Asennus](get-started-setup-github.md)-osassa. Tässä osassa käydään läpi GitHub-tilisi määrittäminen, Git Bashin ja Markdown-editorin asentaminen, haarauman luominen ja paikallisen säilön määrittäminen. Jos et ole perehtynyt Git- ja GitHub-käsitteisiin, kuten säilö tai haara, käy ensin läpi [Gitin ja GitHubin perusteet](git-github-fundamentals.md).

Tässä työnkulussa muutokset kulkevat toistuvana syklinä. Ne lähtevät laitteesi paikallisesta säilöstä ja kulkevat takaisin GitHub-haaraumaasi, GitHub-pääsäilöön, ja sieltä takaisin paikallisesti, kun lisäät muiden osallistujien tekemät muutokset työnkulkuun.

### <a name="use-github-flow"></a>GitHub-työnkulun käyttö

Muistat varmaan [Gitin ja GitHubin perusteista](git-github-fundamentals.md#git) , että Git-säilö sisältää päähaaran sekä muita työn alla olevia haaroja, joita ei vielä ole integroitu pääkohteeseen. Aina, kun lisäät joukon loogisesti toisiinsa liittyviä muutoksia, parhaiden käytäntöjen mukaan on hyvä luoda *toimiva haara*, jonka avulla voit hallita tekemiäsi muutoksia koko työnkulun ajan. Viittaamme siihen tässä ’toimivana haarana’, koska se on työtila, jossa muutoksia voidaan toistaa/tarkentaa, kunnes ne voidaan integroida takaisin päähaaraan.

Eristämällä tiettyyn haaraan liittyvät muutokset voit halita ja lisätä kyseiset muutokset erikseen ja kohdentaa ne tiettyyn julkaisuaikaan julkaisujaksossa. Riippuen siitä, millaista työtä teet, saatat käytännössä päätyä tilanteeseen, jossa säilössäsi on useita toimivia haaroja. On hyvin tavallista työskennellä useiden haarojen parissa samanaikaisesti, joista kukin edustaa eri projektia.

>[!TIP]
>Muutosten tekeminen päähaaraan *ei* ole hyvän käytännön mukaista. Kuvittele, että käytät päähaaraa tiettyjen muutosten käyttöönottoon ajoitetussa ominaisuuden julkaisussa. Saat muutokset valmiiksi ja odotat niiden julkaisemista. Sitten saat sillä välin kiireellisen pyynnön korjata jotain, joten teet muutokset päähaarassa olevaan tiedostoon, ja sitten julkaiset muutoksen. Tässä esimerkissä julkaiset vahingossa sekä korjauksen *että* muutokset, joita olit pitänyt odottamassa julkaistaviksi tiettynä päivänä.

Luodaanpa nyt uusi toimiva haara paikalliseen säilöösi ehdotettujen muutosten tekemiseksi. Jokainen Git-asiakaskone on erilainen, joten katso lisätietoja ohjeista haluamasi asiakaskoneen osalta. Voit nähdä yleiskuvan prosessista GitHub-oppaassa [GitHub-työnkulussa](https://guides.github.com/introduction/flow/).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Seuraavat vaiheet

Se oli siinä! Olet osallistunut työpanoksellasi docs.microsoft.comin sisältöön!

- Saat lisätietoja aiheista, kuten Markdownista ja Markdown-tunnisteiden syntaksista, osasta ”Kirjoittamisen perusteet”.
