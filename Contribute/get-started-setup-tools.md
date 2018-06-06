---
title: Sisällön tuottamisen työkalujen asentaminen
description: Tässä artikkelissa on ohjeet Git-asiakastyökalujen ja Markdown-tiedostojen muokkaukseen tarvittavien työkalujen lataamiseen ja asentamiseen.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1011c3fc829202a3df134ddc80eb05b8959b7bf6
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469367"
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="60f78-103">Sisällön tuottamisen työkalujen asentaminen</span><span class="sxs-lookup"><span data-stu-id="60f78-103">Install content authoring tools</span></span>

<span data-ttu-id="60f78-104">Tässä artikkelissa kuvataan Git-asiakastyökalujen ja Visual Studio Coden asennusvaiheet vuorovaikutteisesti.</span><span class="sxs-lookup"><span data-stu-id="60f78-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="60f78-105">[Git for Windowsin](https://git-scm.com/download/win) asentaminen</span><span class="sxs-lookup"><span data-stu-id="60f78-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="60f78-106">[Visual Studio Coden](https://code.visualstudio.com/) asentaminen</span><span class="sxs-lookup"><span data-stu-id="60f78-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>
> * <span data-ttu-id="60f78-107">[Docs Authoring Packin](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) asentaminen</span><span class="sxs-lookup"><span data-stu-id="60f78-107">Install [Docs Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="60f78-108">Jos teet vain pieniä muutoksia artikkeliin, sinun *ei* tarvitse käydä läpi tämän artikkelin vaiheita vaan voit jatkaa suoraan [nopeiden muutosten työnkulkuun](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="60f78-108">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>
> <span data-ttu-id="60f78-109">Merkittäviä osallistujia kehotetaan käymään läpi nämä vaiheet, joiden avulla voi käyttää [merkittävien/pitkäkestoisten muutosten työnkulkua](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="60f78-109">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](how-to-write-workflows-major.md).</span></span> <span data-ttu-id="60f78-110">Vaikka sinulla olisi kirjoitusoikeudet pääsäilössä, *on suositeltavaa (ja tässä ohjeessa oletetaan), että teet säilöön haarauman ja kloonaat sen*, jotta sinulla on luku- ja kirjoitusoikeudet ehdottamiesi muutosten tallentamiseen haaraumaasi.</span><span class="sxs-lookup"><span data-stu-id="60f78-110">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="60f78-111">Git-asiakastyökalujen asentaminen Windowsiin</span><span class="sxs-lookup"><span data-stu-id="60f78-111">Install Git client tools on Windows</span></span>

 <span data-ttu-id="60f78-112">Asenna uusin versio [Software Freedom Conservancyn Git-asiakastyökaluista](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="60f78-112">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="60f78-113">Asennukseen kuuluu Git-versiontarkistusjärjestelmä ja Git Bash, joka on paikallisen Git-säilön käsittelyyn käytettävä komentorivisovellus.</span><span class="sxs-lookup"><span data-stu-id="60f78-113">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="60f78-114">Jos haluat käyttää graafista käyttöliittymää (GUI) komentorivikäyttöliittymän (CLI) sijaan, katso suosittuja vaihtoehtoja [Software Freedom Conservancyn käytettävissä olevien GUI-asiakkaiden sivulta](https://git-scm.com/downloads/guis), [GitHubin GitHub-työpöydältä](https://desktop.github.com/) tai [Visual Studio Codesta](https://www.visualstudio.com/products/code-vs.aspx).</span><span class="sxs-lookup"><span data-stu-id="60f78-114">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="60f78-115">Noudata valitsemasi asiakkaan asennus- ja määritysohjeita.</span><span class="sxs-lookup"><span data-stu-id="60f78-115">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="60f78-116">Seuraavassa artikkelissa [määrität paikallisen Git-säilön](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="60f78-116">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="60f78-117">Seuraavia muita Git-resursseja on saatavilla: [Git-sanasto](https://help.github.com/articles/github-glossary) | [Git-perusteet](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Git- ja GitHub-opiskelu](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span><span class="sxs-lookup"><span data-stu-id="60f78-117">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="60f78-118">Tietoa Markdown-editoreista</span><span class="sxs-lookup"><span data-stu-id="60f78-118">Understand Markdown editors</span></span>

<span data-ttu-id="60f78-119">Markdown on kevyt merkintäkieli, jota on helppo lukea ja helppo oppia.</span><span class="sxs-lookup"><span data-stu-id="60f78-119">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="60f78-120">Tämän vuoksi siitä on nopeasti tullut alan standardi.</span><span class="sxs-lookup"><span data-stu-id="60f78-120">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="60f78-121">Jos haluat kirjoittaa artikkeleita Markdown-merkintäkielellä, suosittelemme ensin lataamaan ja asentamaan Markdown-editorin.</span><span class="sxs-lookup"><span data-stu-id="60f78-121">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="60f78-122">[Visual Studio Code](https://code.visualstudio.com/) on Microsoftin suosittelema työkalu Markdown-tiedostojen muokkaukseen.</span><span class="sxs-lookup"><span data-stu-id="60f78-122">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="60f78-123">[Atom](https://atom.io) on toinen suosittu työkalu Markdown-tiedostojen muokkaukseen.</span><span class="sxs-lookup"><span data-stu-id="60f78-123">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="60f78-124">Markdown-tiedostojen tunniste on .md.</span><span class="sxs-lookup"><span data-stu-id="60f78-124">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="60f78-125">Lisätietoja Markdownilla kirjoittamisesta, mukaan lukien Markdownin perusteet ja OPS:n mukautettujen Markdown-laajennusten tukemat ominaisuudet, annetaan myöhemmin [Markdownin käyttö](how-to-write-use-markdown.md) -artikkelissa.</span><span class="sxs-lookup"><span data-stu-id="60f78-125">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="60f78-126">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="60f78-126">Visual Studio Code</span></span>

<span data-ttu-id="60f78-127">[Visual Studio Code](https://code.visualstudio.com/) eli VS Code on kevyt editori, joka toimii Windowsissa, Linuxissa ja Macissa.</span><span class="sxs-lookup"><span data-stu-id="60f78-127">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="60f78-128">Se sisältää Git-integroinnin ja laajennusten tuen.</span><span class="sxs-lookup"><span data-stu-id="60f78-128">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="60f78-129">Lataa ja asenna [VS Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="60f78-129">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="60f78-130">VS Coden aloitussivun pitäisi tunnistaa käyttöjärjestelmäsi.</span><span class="sxs-lookup"><span data-stu-id="60f78-130">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="60f78-131">Windows</span><span class="sxs-lookup"><span data-stu-id="60f78-131">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="60f78-132">Mac</span><span class="sxs-lookup"><span data-stu-id="60f78-132">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="60f78-133">Linux</span><span class="sxs-lookup"><span data-stu-id="60f78-133">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="60f78-134">Käynnistä VS Code ja avaa nykyinen kansio suorittamalla komento `code .` komentorivillä tai bash-komentotulkissa.</span><span class="sxs-lookup"><span data-stu-id="60f78-134">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="60f78-135">Jos nykyinen kansio kuuluu paikalliseen Git-säilöön, GitHub-integrointi näkyy Visual Studio Codessa automaattisesti.</span><span class="sxs-lookup"><span data-stu-id="60f78-135">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="docs-authoring-pack"></a><span data-ttu-id="60f78-136">Docs Authoring Pack</span><span class="sxs-lookup"><span data-stu-id="60f78-136">Docs Authoring Pack</span></span>
<span data-ttu-id="60f78-137">Asenna Docs Authoring Pack Visual Studio Codelle.</span><span class="sxs-lookup"><span data-stu-id="60f78-137">Install the Docs Authoring Pack for Visual Studio Code.</span></span> <span data-ttu-id="60f78-138">Tämä laajennus sisältää perusaputoimintoja Markdownin kirjoittamiseen liittyen ja esikatselutoiminnon, jonka avulla käyttäjä voi tarkastaa, miltä Markdown näyttää docs.microsoft.com-sivuston tyylissä.</span><span class="sxs-lookup"><span data-stu-id="60f78-138">This set of extensions includes basic authoring assistance for help when writing Markdown, and a preview feature, so that you can see what the Markdown looks like in the style of the docs.microsoft.com site.</span></span>

   <span data-ttu-id="60f78-139">Siirry tälle [marketplace-sivulle](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) ja valitse **Asenna** tai hae ”`docsmsft.docs-authoring-pack`” VS Code -ikkunan laajennusluettelosta.</span><span class="sxs-lookup"><span data-stu-id="60f78-139">Visit this [marketplace page](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) and select **Install**, or search for `docsmsft.docs-authoring-pack` in your extensions list in the VS Code window.</span></span> 

   <span data-ttu-id="60f78-140">Docs Authoring Pack on käytettävissä VS Codessa näppäinkomennolla Alt+M.</span><span class="sxs-lookup"><span data-stu-id="60f78-140">The Docs Authoring Pack is accessible by pressing Alt+M inside of VS Code.</span></span> <span data-ttu-id="60f78-141">Työkalurivi on oletusarvoisesti piilotettu.</span><span class="sxs-lookup"><span data-stu-id="60f78-141">The toolbar is hidden by default but can be shown.</span></span> <span data-ttu-id="60f78-142">Näytä työkalurivi lisäämällä VS Coden asetuksissa (Control+pilkku) käyttäjäasetuksen `"markdown.showToolbar": true`.</span><span class="sxs-lookup"><span data-stu-id="60f78-142">Edit the VS Code settings (Control+comma) and adding user setting `"markdown.showToolbar": true` to show the toolbar.</span></span>

   <span data-ttu-id="60f78-143">Lisätietoja on sivulla [Docs Authoring Pack](how-to-write-docs-auth-pack.md).</span><span class="sxs-lookup"><span data-stu-id="60f78-143">For more information, see the [Docs Authoring Pack](how-to-write-docs-auth-pack.md) page.</span></span>


## <a name="next-steps"></a><span data-ttu-id="60f78-144">Seuraavat vaiheet</span><span class="sxs-lookup"><span data-stu-id="60f78-144">Next steps</span></span>

<span data-ttu-id="60f78-145">Nyt olet valmis [määrittämään paikallisen Git-säilön](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="60f78-145">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
