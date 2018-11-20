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
# <a name="set-up-git-repository-locally-for-documentation"></a><span data-ttu-id="5c6c3-103">Git-säilön paikallinen määritys dokumentaatiota varten</span><span class="sxs-lookup"><span data-stu-id="5c6c3-103">Set up Git repository locally for documentation</span></span>

<span data-ttu-id="5c6c3-104">Tässä artikkelissa kuvataan vaiheet Git-säilön määrittämiseksi paikallisessa koneessa Microsoft-dokumentaatioon osallistumiseksi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-104">This article describes the steps to set up a git repository on your local machine, with the intent to contribute to Microsoft documentation.</span></span> <span data-ttu-id="5c6c3-105">Osallistujat voivat paikallisesti kloonatun säilön avulla lisätä uusia artikkeleja, tehdä merkittäviä muokkauksia aiemmin luotuihin artikkeleihin tai muuttaa kuvitusta.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-105">Contributors may use a locally cloned repository to add new articles, do major edits on existing articles, or change artwork.</span></span>

<span data-ttu-id="5c6c3-106">Voit aloittaa osallistumisen seuraavien kertaalleen suoritettavien määritystoimien avulla:</span><span class="sxs-lookup"><span data-stu-id="5c6c3-106">You run these one-time setup activities to get started contributing:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5c6c3-107">Määritä asianmukainen säilö</span><span class="sxs-lookup"><span data-stu-id="5c6c3-107">Determine the appropriate repository</span></span>
> * <span data-ttu-id="5c6c3-108">Haaroita säilö omalle GitHub-tilillesi</span><span class="sxs-lookup"><span data-stu-id="5c6c3-108">Fork the repository to your GitHub account</span></span>
> * <span data-ttu-id="5c6c3-109">Valitse paikallinen kansio kloonatuille tiedostoille</span><span class="sxs-lookup"><span data-stu-id="5c6c3-109">Choose a local folder for the cloned files</span></span>
> * <span data-ttu-id="5c6c3-110">Kloonaa säilö paikalliseen koneeseen</span><span class="sxs-lookup"><span data-stu-id="5c6c3-110">Clone the repository to your local machine</span></span>
> * <span data-ttu-id="5c6c3-111">Konfiguroi yläpuolisen säilön etäarvo</span><span class="sxs-lookup"><span data-stu-id="5c6c3-111">Configure the upstream remote value</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c6c3-112">Jos teet artikkeliin vain pieniä muutoksia, tässä artikkelissa olevia vaiheita *ei* tarvitse suorittaa.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-112">If you're making only minor changes to an article, you *do not* need to complete the steps in this article.</span></span> <span data-ttu-id="5c6c3-113">Voit jatkaa suoraan [nopeiden muutosten työnkulkuun](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="5c6c3-113">You can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>

## <a name="overview"></a><span data-ttu-id="5c6c3-114">Yleiskatsaus</span><span class="sxs-lookup"><span data-stu-id="5c6c3-114">Overview</span></span>

<span data-ttu-id="5c6c3-115">Microsoftin dokumentaatiosivustolle osallistumiseksi voit luoda ja muokata Markdown-tiedostoja paikallisesti kloonaamalla vastaavan dokumentaatiosäilön.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-115">To contribute to Microsoft's documentation site, you can make and edit Markdown files locally by cloning the corresponding documentation repository.</span></span> <span data-ttu-id="5c6c3-116">Microsoft edellyttää, että haaroitat asianmukaisen säilön omalle GitHub-tilillesi siten, että sinulla on siihen luku- ja kirjoitusoikeudet ehdotettujen muutostesi tallentamiseksi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-116">Microsoft requires you to fork the appropriate repository into your own GitHub account so that you have read/write permissions there to store your proposed changes.</span></span> <span data-ttu-id="5c6c3-117">Voit sitten pull-pyyntöjen avulla sulauttaa muutokset keskitettyyn jaettuun säilöön, johon on vain luku -oikeudet.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-117">Then you use pull requests to merge changes into the read-only central shared repository.</span></span>

![GitHub-kolmio](./media/git-and-github-initial-setup.png)

<span data-ttu-id="5c6c3-119">Jos et ole aiemmin käyttänyt GitHubia, katso seuraava video, jossa on haarautumis- ja kloonausprosessien konseptuaalinen yleiskatsaus:</span><span class="sxs-lookup"><span data-stu-id="5c6c3-119">If you're new to GitHub, watch the following video for a conceptual overview of the forking and cloning process:</span></span>

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a><span data-ttu-id="5c6c3-120">Säilön määrittäminen</span><span class="sxs-lookup"><span data-stu-id="5c6c3-120">Determine the repository</span></span>

<span data-ttu-id="5c6c3-121">[docs.microsoft.comin](https://docs.microsoft.com) isännöimä dokumentaatio on useissa eri säilöissä [github.comissa](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="5c6c3-121">Documentation hosted at [docs.microsoft.com](https://docs.microsoft.com) resides in several different repositories at [github.com](https://www.github.com).</span></span>

1. <span data-ttu-id="5c6c3-122">Jos et ole varma käytettävästä säilöstä, lue [docs.microsoft.comin](https://docs.microsoft.com) artikkeli verkkoselaimen avulla.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-122">If you are unsure of which repository to use, then visit the article on [docs.microsoft.com](https://docs.microsoft.com) using your web browser.</span></span> <span data-ttu-id="5c6c3-123">Valitse **Muokkaa**-linkki (kynäkuvake) artikkelin oikeasta yläkulmasta.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-123">Select the **Edit** link (pencil icon) on the upper right of the article.</span></span>

   ![Määritä säilö ja tiedoston sijainti napsauttamalla Muokkaa.](media/index/edit-article.png)

2. <span data-ttu-id="5c6c3-125">Linkki vie sinut vastaavan Markdown-tiedoston sijaintiin asianmukaisessa säilössä.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-125">That link takes you to github.com location for the corresponding Markdown file in the appropriate repository.</span></span> <span data-ttu-id="5c6c3-126">Huomaa URL-osoite säilön nimen tarkastelemiseksi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-126">Note the URL to view the repository name.</span></span>

   ![Huomaa URL-osoite säilön sijainnin määrittämiseksi.](media/public-repo.png)

   <span data-ttu-id="5c6c3-128">Julkisen osallistumisen piiriin kuuluvat muun muassa seuraavat suositut säilöt:</span><span class="sxs-lookup"><span data-stu-id="5c6c3-128">For example, these popular repositories are available for public contributions:</span></span>
   - <span data-ttu-id="5c6c3-129">Azure-dokumentaatio [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span><span class="sxs-lookup"><span data-stu-id="5c6c3-129">Azure documentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span></span>
   - <span data-ttu-id="5c6c3-130">SQL Server -dokumentaatio [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span><span class="sxs-lookup"><span data-stu-id="5c6c3-130">SQL Server documentation [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span></span>
   - <span data-ttu-id="5c6c3-131">Visual Studio -dokumentaatio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span><span class="sxs-lookup"><span data-stu-id="5c6c3-131">Visual Studio documentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span></span>
   - <span data-ttu-id="5c6c3-132">.NET-dokumentaatio [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span><span class="sxs-lookup"><span data-stu-id="5c6c3-132">.NET Documentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span></span>
   - <span data-ttu-id="5c6c3-133">Azure .Net SDK -dokumentaatio [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span><span class="sxs-lookup"><span data-stu-id="5c6c3-133">Azure .Net SDK documentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span></span>

## <a name="fork-the-repository"></a><span data-ttu-id="5c6c3-134">Haaroita säilö</span><span class="sxs-lookup"><span data-stu-id="5c6c3-134">Fork the repository</span></span>
<span data-ttu-id="5c6c3-135">Voit asianmukaisen säilön avulla luoda säilön haarauman omalle GitHub-tilillesi GitHub-verkkosivuston avulla.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-135">Using the appropriate repository, create a fork of the repository into your own GitHub account by using the GitHub website.</span></span>

<span data-ttu-id="5c6c3-136">Henkilökohtaista haaraumaa edellytetään, koska kaikki pääasialliset dokumentaatiosäilöt tarjoavat vain luku -käyttöoikeuden.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-136">A personal fork is required since all main documentation repositories provide read-only access.</span></span> <span data-ttu-id="5c6c3-137">Jos haluat tehdä muutoksia, sinun on lähetettävä [pull-pyyntö](git-github-fundamentals.md#pull-requests) haaraumasta pääasialliseen säilöön.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-137">To make changes, you must submit a [pull request](git-github-fundamentals.md#pull-requests) from your fork into the main repository.</span></span> <span data-ttu-id="5c6c3-138">Tämän prosessin helpottamiseksi tarvitset ensin säilön oman kopion, johon sinulla on kirjoitusoikeus.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-138">To facilitate this process, you first need your own copy of the repository, in which you have write access.</span></span> <span data-ttu-id="5c6c3-139">GitHub-*haarauma* on tätä tarkoitusta varten.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-139">A GitHub *fork* serves that purpose.</span></span>

1. <span data-ttu-id="5c6c3-140">Siirry pääasiallisen säilön GitHub-sivulle ja napsauta **Haarauma**-painiketta yläoikealla.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-140">Go to the main repository's GitHub page and click the **Fork** button on the upper right.</span></span>

   ![Esimerkki GitHub-profiilista](./media/contribute-get-started-setup-local/fork.png)

2. <span data-ttu-id="5c6c3-142">Jos sinua kehotetaan tekemään niin, valitse GitHub-tilin ruutu haarauman luomisen kohdesijainniksi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-142">If you are prompted, select your GitHub account tile as the destination where the fork should be created.</span></span> <span data-ttu-id="5c6c3-143">Tämä kehote luo omalle GitHub-tilillesi säilön kopion, jota nimitetään haaraumaksi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-143">This prompt creates a copy of the repository within your GitHub account, known as a fork.</span></span>

## <a name="choose-a-local-folder"></a><span data-ttu-id="5c6c3-144">Valitse paikallinen kansio</span><span class="sxs-lookup"><span data-stu-id="5c6c3-144">Choose a local folder</span></span>
<span data-ttu-id="5c6c3-145">Säilytä säilön paikallinen kopio luomalla paikallinen kansio.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-145">Make a local folder to hold a copy of the repository locally.</span></span> <span data-ttu-id="5c6c3-146">Jotkin säilöistä voivat olla suuria: esimerkiksi Azure-asiakirjojen koko voi olla jopa 5 Gt.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-146">Some of the repositories can be large; up to 5 GB for azure-docs for example.</span></span> <span data-ttu-id="5c6c3-147">Valitse sijainti, jossa on riittävästi levytilaa.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-147">Choose a location with available disk space.</span></span>

1. <span data-ttu-id="5c6c3-148">Valitse kansion nimi, joka on helppo muistaa ja kirjoittaa.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-148">Choose a folder name should be easy for you to remember and type.</span></span> <span data-ttu-id="5c6c3-149">Voit valita esimerkiksi juurikansion `C:\docs\` tai luoda kansion käyttäjäprofiilin hakemistoon `~/Documents/docs/`.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-149">For example, consider a root folder `C:\docs\` or make a folder in your user profile directory `~/Documents/docs/`</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5c6c3-150">Vältä valitsemasta paikallisen kansion polkua, joka on upotettu toisen Git-säilön kansion sijaintiin.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-150">Avoid choosing a local folder path that is nested inside of another git repository folder location.</span></span> <span data-ttu-id="5c6c3-151">Vaikka Git-kloonattuja kansioita voidaankin tallentaa vierekkäin, Git-kansioiden upottaminen sisäkkäin voi aiheuttaa virheitä tiedoston seurannassa.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-151">While it is acceptable to store the git cloned folders adjacent to each other, nesting git folders inside one another causes errors for the file tracking.</span></span>

2. <span data-ttu-id="5c6c3-152">Käynnistä Git Bash</span><span class="sxs-lookup"><span data-stu-id="5c6c3-152">Launch Git Bash</span></span>

   ![Käynnistä Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   <span data-ttu-id="5c6c3-154">Oletussijainti, jossa Git Bash alkaa, on yleensä aloitushakemisto (~) tai `/c/users/<Windows-user-account>/` Windows-käyttöjärjestelmässä.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-154">The default location that Git Bash starts in is typically the home directory (~) or `/c/users/<Windows-user-account>/` on Windows OS.</span></span>

   <span data-ttu-id="5c6c3-155">Voit määrittää nykyisen hakemiston kirjoittamalla `pwd` $-komentoriville.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-155">To determine the current directory, type `pwd` at the $ prompt.</span></span> 

3. <span data-ttu-id="5c6c3-156">Vaihda hakemisto (cd) kansioon, jonka loit säilön paikallista isännöintiä varten.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-156">Change directory (cd) into the folder that you created for hosting the repository locally.</span></span> <span data-ttu-id="5c6c3-157">Huomaa, että Git Bash käyttää kansiopoluissa vinoviivojen Linux-konventiota kenoviivojen sijasta.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-157">Note that Git Bash uses the Linux convention of forward-slashes instead of back-slashes for folder paths.</span></span>

   <span data-ttu-id="5c6c3-158">Esimerkiksi `cd /c/docs/ ` tai `cd ~/Documents/docs/`.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-158">For example, `cd /c/docs/ ` or `cd ~/Documents/docs/`</span></span>

## <a name="create-a-local-clone"></a><span data-ttu-id="5c6c3-159">Luo paikallinen klooni</span><span class="sxs-lookup"><span data-stu-id="5c6c3-159">Create a local clone</span></span>

<span data-ttu-id="5c6c3-160">Valmistele **Kloonaa**-komennon suorittaminen Git Bashin avulla viemällä säilön kopio (haarautuma) alaspäin laitteeseen nykyisessä hakemistossa.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-160">Using Git Bash, prepare to run the **clone** command to pull a copy of a repository (your fork) down to your device on the current directory.</span></span> 

### <a name="authenticate-by-using-git-credential-manager"></a><span data-ttu-id="5c6c3-161">Todenna Git-tunnistetietojenhallinnan avulla</span><span class="sxs-lookup"><span data-stu-id="5c6c3-161">Authenticate by using Git Credential Manager</span></span>
<span data-ttu-id="5c6c3-162">Jos olet asentanut Git for Windowsin uusimman version ja hyväksynyt oletusasennuksen, Git-tunnistetietojenhallinta on oletusarvoisesti käytössä.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-162">If you installed the latest version of Git for Windows and accepted the default installation, Git Credential Manager is enabled by default.</span></span> <span data-ttu-id="5c6c3-163">Git-tunnistetietojen hallinta helpottaa selvästi todennusta, koska sinun ei tarvitse peruuttaa henkilökohtaista käyttöoikeustietuettasi, kun muodostat uudelleen todennettuja yhteyksiä ja etäyhteyksiä GitHubin kanssa.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-163">Git Credential Manager makes authentication much easier because you don't need to recall your personal access token when re-establishing authenticated connections and remotes with GitHub.</span></span>

1. <span data-ttu-id="5c6c3-164">Suorita **Kloonaa**-komento antamalla säilön nimi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-164">Run the **clone** command, by providing the repository name.</span></span> <span data-ttu-id="5c6c3-165">Kloonaa lataukset (Kloonaa) haaroitettuun säilöön paikallisessa tietokoneessa.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-165">Cloning downloads (clone) the forked repository on your local computer.</span></span> 

    > [!Tip]
    > <span data-ttu-id="5c6c3-166">Saat haarauman GitHub URL-osoitteen Kloonaa-komennolle painamalla **Kloonaa tai lataa** -painiketta GitHubin käyttöliittymässä:</span><span class="sxs-lookup"><span data-stu-id="5c6c3-166">You can get your fork's GitHub URL for the clone command from the **Clone or download** button in the GitHub UI:</span></span>
    >
    > ![Kloonaa tai lataa](./media/contribute-get-started-setup-local/clone-or-download.png)

    <span data-ttu-id="5c6c3-168">Muista määrittää polku *haaraumallesi* kloonausprosessin aikana, ei pääsäilöä, josta haarauma luotiin.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-168">Be sure to specify the path to *your fork* during the cloning process, not the main repository from which you created the fork.</span></span> <span data-ttu-id="5c6c3-169">Muuten et voi osallistua muutoksiin.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-169">Otherwise, you cannot contribute changes.</span></span> <span data-ttu-id="5c6c3-170">Haaraumaan viitataan henkilökohtaisella GitHub-käyttäjätililläsi, kuten `github.com/<github-username>/<repo>`.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-170">Your fork is referenced through your personal GitHub user account, such as `github.com/<github-username>/<repo>`.</span></span>

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    <span data-ttu-id="5c6c3-171">Kloonaa-komennon pitäisi näyttää tämän esimerkin kaltaiselta:</span><span class="sxs-lookup"><span data-stu-id="5c6c3-171">Your clone command should look similar to this example:</span></span>

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. <span data-ttu-id="5c6c3-172">Kun näyttöön tulee kehote, anna GitHub-tunnistetietosi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-172">When you're prompted, enter your GitHub credentials.</span></span>

    ![GitHub-sisäänkirjautuminen](./media/contribute-get-started-setup-local/github-login.png)

3. <span data-ttu-id="5c6c3-174">Kun näyttöön tulee kehote, anna kaksivaiheinen todennuskoodisi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-174">When you're prompted, enter your two-factor authentication code.</span></span>

    ![GitHubin kaksivaiheinen todennus](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > <span data-ttu-id="5c6c3-176">Tunnistetiedot tallennetaan ja niitä käytetään tulevien GitHub-pyyntöjen todentamiseen.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-176">Your credentials will be saved and used to authenticate future GitHub requests.</span></span> <span data-ttu-id="5c6c3-177">Tämä todennus on suoritettava vain kertaalleen tietokonetta kohti.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-177">You only need to do this authentication once per computer.</span></span> 

4. <span data-ttu-id="5c6c3-178">Kloonaa-komento suorittaa ja lataa säilön tiedostojen kopion uuden kansion haaraumaan paikallisella levyllä.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-178">The clone command runs and downloads a copy of the repository files from your fork into a new folder on the local disk.</span></span> <span data-ttu-id="5c6c3-179">Uusi kansio luodaan nykyiseen kansioon.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-179">A new folder is made within the current folder.</span></span> <span data-ttu-id="5c6c3-180">Se voi kestää muutaman minuutin säilön koon mukaan.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-180">It may take a few minutes, depending on the repository size.</span></span> <span data-ttu-id="5c6c3-181">Voit tarkastella kansion rakennetta luomisen jälkeen.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-181">You can explore the folder to see the structure once it is finished.</span></span>

## <a name="configure-remote-upstream"></a><span data-ttu-id="5c6c3-182">Konfiguroi etäyhteys</span><span class="sxs-lookup"><span data-stu-id="5c6c3-182">Configure remote upstream</span></span>
<span data-ttu-id="5c6c3-183">Voit säilön kloonaamisen jälkeen määrittää vain luku -etäyhteyden pääsäilöön eli **yläpuoliseen säilöön**.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-183">After cloning the repository, set up a read-only remote connection to the main repository named **upstream**.</span></span> <span data-ttu-id="5c6c3-184">Voit yläpuolisen säilön URL-osoitteen avulla synkronoida paikalliseen säilöön muiden tekemät muutokset.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-184">You use the upstream URL to keep your local repository in sync with the latest changes made by others.</span></span> <span data-ttu-id="5c6c3-185">Konfigurointiarvo määritetään **Git-etäyhteys**-komennon avulla.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-185">The **git remote** command is used to set the configuration value.</span></span> <span data-ttu-id="5c6c3-186">Voit **Nouda**-komennon avulla päivittää haarautumistiedot yläpuolisesta säilöstä.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-186">You use the **fetch** command to refresh the branch info from the upstream repository.</span></span>

1. <span data-ttu-id="5c6c3-187">Jos käytät **Git-tunnistetietojenhallintaa**, käytä seuraavia komentoja.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-187">If you're using **Git Credential Manager**, use the following commands.</span></span> <span data-ttu-id="5c6c3-188">Korvaa \<säilö\>- ja \<organisaatio\>-paikkamerkit.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-188">Replace the \<repo\> and \<organization\> placeholders.</span></span>
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. <span data-ttu-id="5c6c3-189">Tarkastele konfiguroituja arvoja ja varmista, että URL-osoitteet ovat oikein.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-189">View the configured values and confirm the URLs are correct.</span></span> <span data-ttu-id="5c6c3-190">Varmista, että **alkuperäiset** URL-osoitteet osoittavat henkilökohtaiseen haaraumaasi.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-190">Ensure the **origin** URLs point to your personal fork.</span></span> <span data-ttu-id="5c6c3-191">Varmista, että **yläpuoliset** URL-osoitteet osoittavat pääsäilöön, kuten MicrosoftDocsiin tai Azureen.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-191">Ensure the **upstream** URLs point to the main repository, such as MicrosoftDocs or Azure.</span></span> 
   ```bash
   git remote -v 
   ```

   <span data-ttu-id="5c6c3-192">Näkyviin tulee etäyhteyden esimerkki.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-192">Example remote output is shown.</span></span> <span data-ttu-id="5c6c3-193">Konfiguroituna on kuvitteellinen Git-tili nimeltä MyGitAccount ja henkilökohtainen käyttäjätunnuksesi säilön Azure-asiakirjoihin:</span><span class="sxs-lookup"><span data-stu-id="5c6c3-193">A fictitious git account named MyGitAccount is configured with a personal access token to access the repo azure-docs:</span></span>
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. <span data-ttu-id="5c6c3-194">Jos teit virheen, voit poistaa etäarvon.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-194">If you made a mistake, you can remove the remote value.</span></span> <span data-ttu-id="5c6c3-195">Voit poistaa yläpuolisen säilön arvon suorittamalla komennon `git remote remove upstream`.</span><span class="sxs-lookup"><span data-stu-id="5c6c3-195">To remove the upstream value, run the command `git remote remove upstream`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c6c3-196">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="5c6c3-196">Next steps</span></span>
- <span data-ttu-id="5c6c3-197">Saat lisätietoja sisällön lisäämisestä ja päivittämisestä jatkamalla [GitHub-osallistumisen työnkulkuun](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="5c6c3-197">To learn more about adding and updating content, continue to the [GitHub contribution workflow](how-to-write-workflows-major.md).</span></span>
