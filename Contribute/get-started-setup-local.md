---
title: Git-säilön paikallinen määritys
description: Tässä artikkelissa on ohjeet paikallisen Git-säilön luomiseen ja osallistumiseen dokumentaatioon, mukaan lukien haarautumis- ja kloonausprosessit.
author: jasonwhowell
ms.author: jasonh
ms.date: 01/18/2018
ms.openlocfilehash: 5373bf34399105c15caabe0abdc1ea0692c46a4a
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609495"
---
# <a name="set-up-git-repository-locally-for-documentation"></a>Git-säilön paikallinen määritys dokumentaatiota varten

Tässä artikkelissa kuvataan vaiheet Git-säilön määrittämiseksi paikallisessa koneessa Microsoft-dokumentaatioon osallistumiseksi. Osallistujat voivat paikallisesti kloonatun säilön avulla lisätä uusia artikkeleja, tehdä merkittäviä muokkauksia aiemmin luotuihin artikkeleihin tai muuttaa kuvitusta.

Voit aloittaa osallistumisen seuraavien kertaalleen suoritettavien määritystoimien avulla:
> [!div class="checklist"]
> * Määritä asianmukainen säilö
> * Haaroita säilö omalle GitHub-tilillesi
> * Valitse paikallinen kansio kloonatuille tiedostoille
> * Kloonaa säilö paikalliseen koneeseen
> * Konfiguroi yläpuolisen säilön etäarvo

> [!IMPORTANT]
> Jos teet artikkeliin vain pieniä muutoksia, tässä artikkelissa olevia vaiheita *ei* tarvitse suorittaa. Voit jatkaa suoraan [nopeiden muutosten työnkulkuun](index.md#quick-edits-to-existing-documents).
>

## <a name="overview"></a>Yleiskatsaus

Microsoftin dokumentaatiosivustolle osallistumiseksi voit luoda ja muokata Markdown-tiedostoja paikallisesti kloonaamalla vastaavan dokumentaatiosäilön. Microsoft edellyttää, että haaroitat asianmukaisen säilön omalle GitHub-tilillesi siten, että sinulla on siihen luku- ja kirjoitusoikeudet ehdotettujen muutostesi tallentamiseksi. Voit sitten pull-pyyntöjen avulla sulauttaa muutokset keskitettyyn jaettuun säilöön, johon on vain luku -oikeudet.

![GitHub-kolmio](./media/git-and-github-initial-setup.png)

Jos et ole aiemmin käyttänyt GitHubia, katso seuraava video, jossa on haarautumis- ja kloonausprosessien konseptuaalinen yleiskatsaus:

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a>Säilön määrittäminen

[docs.microsoft.comin](https://docs.microsoft.com) isännöimä dokumentaatio on useissa eri säilöissä [github.comissa](https://www.github.com).

1. Jos et ole varma käytettävästä säilöstä, lue [docs.microsoft.comin](https://docs.microsoft.com) artikkeli verkkoselaimen avulla. Valitse **Muokkaa**-linkki (kynäkuvake) artikkelin oikeasta yläkulmasta.

   ![Määritä säilö ja tiedoston sijainti napsauttamalla Muokkaa.](media/index/edit-article.png)

2. Linkki vie sinut vastaavan Markdown-tiedoston sijaintiin asianmukaisessa säilössä. Huomaa URL-osoite säilön nimen tarkastelemiseksi.

   ![Huomaa URL-osoite säilön sijainnin määrittämiseksi.](media/public-repo.png)

   Julkisen osallistumisen piiriin kuuluvat muun muassa seuraavat suositut säilöt:
   - Azure-dokumentaatio [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)
   - SQL Server -dokumentaatio [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)
   - Visual Studio -dokumentaatio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)
   - .NET-dokumentaatio [https://github.com/dotnet/docs](https://github.com/dotnet/docs)
   - Azure .Net SDK -dokumentaatio [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)

## <a name="fork-the-repository"></a>Haaroita säilö
Voit asianmukaisen säilön avulla luoda säilön haarauman omalle GitHub-tilillesi GitHub-verkkosivuston avulla.

Henkilökohtaista haaraumaa edellytetään, koska kaikki pääasialliset dokumentaatiosäilöt tarjoavat vain luku -käyttöoikeuden. Jos haluat tehdä muutoksia, sinun on lähetettävä [pull-pyyntö](git-github-fundamentals.md#pull-requests) haaraumasta pääasialliseen säilöön. Tämän prosessin helpottamiseksi tarvitset ensin säilön oman kopion, johon sinulla on kirjoitusoikeus. GitHub-*haarauma* on tätä tarkoitusta varten.

1. Siirry pääasiallisen säilön GitHub-sivulle ja napsauta **Haarauma**-painiketta yläoikealla.

   ![Esimerkki GitHub-profiilista](./media/contribute-get-started-setup-local/fork.png)

2. Jos sinua kehotetaan tekemään niin, valitse GitHub-tilin ruutu haarauman luomisen kohdesijainniksi. Tämä kehote luo omalle GitHub-tilillesi säilön kopion, jota nimitetään haaraumaksi.

## <a name="choose-a-local-folder"></a>Valitse paikallinen kansio
Säilytä säilön paikallinen kopio luomalla paikallinen kansio. Jotkin säilöistä voivat olla suuria: esimerkiksi Azure-asiakirjojen koko voi olla jopa 5 Gt. Valitse sijainti, jossa on riittävästi levytilaa.

1. Valitse kansion nimi, joka on helppo muistaa ja kirjoittaa. Voit valita esimerkiksi juurikansion `C:\docs\` tai luoda kansion käyttäjäprofiilin hakemistoon `~/Documents/docs/`.

   > [!IMPORTANT]
   > Vältä valitsemasta paikallisen kansion polkua, joka on upotettu toisen Git-säilön kansion sijaintiin. Vaikka Git-kloonattuja kansioita voidaankin tallentaa vierekkäin, Git-kansioiden upottaminen sisäkkäin voi aiheuttaa virheitä tiedoston seurannassa.

2. Käynnistä Git Bash

   ![Käynnistä Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   Oletussijainti, jossa Git Bash alkaa, on yleensä aloitushakemisto (~) tai `/c/users/<Windows-user-account>/` Windows-käyttöjärjestelmässä.

   Voit määrittää nykyisen hakemiston kirjoittamalla `pwd` $-komentoriville. 

3. Vaihda hakemisto (cd) kansioon, jonka loit säilön paikallista isännöintiä varten. Huomaa, että Git Bash käyttää kansiopoluissa vinoviivojen Linux-konventiota kenoviivojen sijasta.

   Esimerkiksi `cd /c/docs/ ` tai `cd ~/Documents/docs/`.

## <a name="create-a-local-clone"></a>Luo paikallinen klooni

Valmistele **Kloonaa**-komennon suorittaminen Git Bashin avulla viemällä säilön kopio (haarautuma) alaspäin laitteeseen nykyisessä hakemistossa. 

### <a name="authenticate-by-using-git-credential-manager"></a>Todenna Git-tunnistetietojenhallinnan avulla
Jos olet asentanut Git for Windowsin uusimman version ja hyväksynyt oletusasennuksen, Git-tunnistetietojenhallinta on oletusarvoisesti käytössä. Git-tunnistetietojen hallinta helpottaa selvästi todennusta, koska sinun ei tarvitse peruuttaa henkilökohtaista käyttöoikeustietuettasi, kun muodostat uudelleen todennettuja yhteyksiä ja etäyhteyksiä GitHubin kanssa.

1. Suorita **Kloonaa**-komento antamalla säilön nimi. Kloonaa lataukset (Kloonaa) haaroitettuun säilöön paikallisessa tietokoneessa. 

    > [!Tip]
    > Saat haarauman GitHub URL-osoitteen Kloonaa-komennolle painamalla **Kloonaa tai lataa** -painiketta GitHubin käyttöliittymässä:
    >
    > ![Kloonaa tai lataa](./media/contribute-get-started-setup-local/clone-or-download.png)

    Muista määrittää polku *haaraumallesi* kloonausprosessin aikana, ei pääsäilöä, josta haarauma luotiin. Muuten et voi osallistua muutoksiin. Haaraumaan viitataan henkilökohtaisella GitHub-käyttäjätililläsi, kuten `github.com/<github-username>/<repo>`.

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    Kloonaa-komennon pitäisi näyttää tämän esimerkin kaltaiselta:

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. Kun näyttöön tulee kehote, anna GitHub-tunnistetietosi.

    ![GitHub-sisäänkirjautuminen](./media/contribute-get-started-setup-local/github-login.png)

3. Kun näyttöön tulee kehote, anna kaksivaiheinen todennuskoodisi.

    ![GitHubin kaksivaiheinen todennus](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > Tunnistetiedot tallennetaan ja niitä käytetään tulevien GitHub-pyyntöjen todentamiseen. Tämä todennus on suoritettava vain kertaalleen tietokonetta kohti. 

4. Kloonaa-komento suorittaa ja lataa säilön tiedostojen kopion uuden kansion haaraumaan paikallisella levyllä. Uusi kansio luodaan nykyiseen kansioon. Se voi kestää muutaman minuutin säilön koon mukaan. Voit tarkastella kansion rakennetta luomisen jälkeen.

## <a name="configure-remote-upstream"></a>Konfiguroi etäyhteys
Voit säilön kloonaamisen jälkeen määrittää vain luku -etäyhteyden pääsäilöön eli **yläpuoliseen säilöön**. Voit yläpuolisen säilön URL-osoitteen avulla synkronoida paikalliseen säilöön muiden tekemät muutokset. Konfigurointiarvo määritetään **Git-etäyhteys**-komennon avulla. Voit **Nouda**-komennon avulla päivittää haarautumistiedot yläpuolisesta säilöstä.

1. Jos käytät **Git-tunnistetietojenhallintaa**, käytä seuraavia komentoja. Korvaa \<säilö\>- ja \<organisaatio\>-paikkamerkit.
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. Tarkastele konfiguroituja arvoja ja varmista, että URL-osoitteet ovat oikein. Varmista, että **alkuperäiset** URL-osoitteet osoittavat henkilökohtaiseen haaraumaasi. Varmista, että **yläpuoliset** URL-osoitteet osoittavat pääsäilöön, kuten MicrosoftDocsiin tai Azureen. 
   ```bash
   git remote -v 
   ```

   Näkyviin tulee etäyhteyden esimerkki. Konfiguroituna on kuvitteellinen Git-tili nimeltä MyGitAccount ja henkilökohtainen käyttäjätunnuksesi säilön Azure-asiakirjoihin:
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. Jos teit virheen, voit poistaa etäarvon. Voit poistaa yläpuolisen säilön arvon suorittamalla komennon `git remote remove upstream`.

## <a name="next-steps"></a>Seuraavat vaiheet
- Saat lisätietoja sisällön lisäämisestä ja päivittämisestä jatkamalla [GitHub-osallistumisen työnkulkuun](how-to-write-workflows-major.md).
