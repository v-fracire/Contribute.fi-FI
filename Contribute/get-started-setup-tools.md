---
title: Sisällön tuottamisen työkalujen asentaminen
description: Tässä artikkelissa on ohjeet Git-asiakastyökalujen ja Markdown-tiedostojen muokkaukseen tarvittavien työkalujen lataamiseen ja asentamiseen.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.openlocfilehash: 9f22a416810711c076645a9483f022112a3a7642
ms.sourcegitcommit: 886ca76086a302d1d6124967df12a5bcfe4fd4b5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/10/2018
ms.locfileid: "40251419"
---
# <a name="install-content-authoring-tools"></a>Sisällön tuottamisen työkalujen asentaminen

Tässä artikkelissa kuvataan Git-asiakastyökalujen ja Visual Studio Coden asennusvaiheet vuorovaikutteisesti.
> [!div class="checklist"]
> * [Gitin](https://git-scm.com/) asentaminen
> * [Visual Studio Coden](https://code.visualstudio.com/) asentaminen
> * [Docs Authoring Packin](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) asentaminen

>[!IMPORTANT]
> Jos teet vain pieniä muutoksia artikkeliin, sinun *ei* tarvitse käydä läpi tämän artikkelin vaiheita vaan voit jatkaa suoraan [nopeiden muutosten työnkulkuun](index.md#quick-edits-to-existing-documents).
>
> Merkittäviä osallistujia kehotetaan käymään läpi nämä vaiheet, joiden avulla voi käyttää [merkittävien/pitkäkestoisten muutosten työnkulkua](how-to-write-workflows-major.md). Vaikka sinulla olisi kirjoitusoikeudet pääsäilössä, *on suositeltavaa (ja tässä ohjeessa oletetaan), että teet säilöön haarauman ja kloonaat sen*, jotta sinulla on luku- ja kirjoitusoikeudet ehdottamiesi muutosten tallentamiseen haaraumaasi.

## <a name="install-git-client-tools"></a>Git-asiakastyökalujen asentaminen 

 Asenna uusin versio [Software Freedom Conservancyn Git-asiakastyökaluista](https://git-scm.com/download/) alustaasi. 

* [Git for Windows](https://git-scm.com/download/win). Tähän asennukseen kuuluu Git-versiontarkistusjärjestelmä ja Git Bash, joka on paikallisen Git-säilön käsittelyyn käytettävä komentorivisovellus.
* Git for Mac toimitetaan osana Xcode Command Line -työkaluja. Suorita vain `git` komentoriviltä. Sinua kehotetaan asentamaan komentorivityökalut tarvittaessa. Voit myös ladata [Git for Macin](https://git-scm.com/download/mac) Software Freedom Conservancysta.
* [Git for Linux ja Unix](https://git-scm.com/download/linux)

Jos haluat käyttää graafista käyttöliittymää (GUI) komentorivikäyttöliittymän (CLI) sijaan, katso suosittuja vaihtoehtoja [Software Freedom Conservancyn käytettävissä olevien GUI-asiakkaiden sivulta](https://git-scm.com/downloads/guis), [GitHubin GitHub-työpöydältä](https://desktop.github.com/) tai [Visual Studio Codesta](https://www.visualstudio.com/products/code-vs.aspx).

Noudata valitsemasi asiakkaan asennus- ja määritysohjeita.

Seuraavassa artikkelissa [määrität paikallisen Git-säilön](get-started-setup-local.md).

   Seuraavia muita Git-resursseja on saatavilla: [Git-sanasto](https://help.github.com/articles/github-glossary) | [Git-perusteet](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Git- ja GitHub-opiskelu](https://help.github.com/articles/good-resources-for-learning-git-and-github/)

## <a name="understand-markdown-editors"></a>Tietoa Markdown-editoreista

Markdown on kevyt merkintäkieli, jota on helppo lukea ja helppo oppia. Tämän vuoksi siitä on nopeasti tullut alan standardi. Jos haluat kirjoittaa artikkeleita Markdown-merkintäkielellä, suosittelemme ensin lataamaan ja asentamaan Markdown-editorin.  [Visual Studio Code](https://code.visualstudio.com/) on Microsoftin suosittelema työkalu Markdown-tiedostojen muokkaukseen. [Atom](https://atom.io) on toinen suosittu työkalu Markdown-tiedostojen muokkaukseen.

Markdown-tiedostojen tunniste on .md.

Lisätietoja Markdownilla kirjoittamisesta, mukaan lukien Markdownin perusteet ja OPS:n mukautettujen Markdown-laajennusten tukemat ominaisuudet, annetaan myöhemmin [Markdownin käyttö](how-to-write-use-markdown.md) -artikkelissa.

## <a name="visual-studio-code"></a>Visual Studio Code

[Visual Studio Code](https://code.visualstudio.com/) eli VS Code on kevyt editori, joka toimii Windowsissa, Linuxissa ja Macissa. Se sisältää Git-integroinnin ja laajennusten tuen.

Lataa ja asenna [VS Code](https://code.visualstudio.com/). VS Coden aloitussivun pitäisi tunnistaa käyttöjärjestelmäsi.

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> Käynnistä VS Code ja avaa nykyinen kansio suorittamalla komento `code .` komentorivillä tai bash-komentotulkissa. Jos nykyinen kansio kuuluu paikalliseen Git-säilöön, GitHub-integrointi näkyy Visual Studio Codessa automaattisesti.

## <a name="docs-authoring-pack"></a>Docs Authoring Pack
Asenna Docs Authoring Pack Visual Studio Codelle. Tämä laajennus sisältää perusaputoimintoja Markdownin kirjoittamiseen liittyen ja esikatselutoiminnon, jonka avulla käyttäjä voi tarkastaa, miltä Markdown näyttää docs.microsoft.com-sivuston tyylissä.

   Siirry tälle [marketplace-sivulle](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) ja valitse **Asenna** tai hae ”`docsmsft.docs-authoring-pack`” VS Code -ikkunan laajennusluettelosta. 

   Docs Authoring Pack on käytettävissä VS Codessa näppäinkomennolla Alt+M. Työkalurivi on oletusarvoisesti piilotettu. Näytä työkalurivi lisäämällä VS Coden asetuksissa (Control+pilkku) käyttäjäasetuksen `"markdown.showToolbar": true`.

   Lisätietoja on sivulla [Docs Authoring Pack](how-to-write-docs-auth-pack.md).


## <a name="next-steps"></a>Seuraavat vaiheet

Nyt olet valmis [määrittämään paikallisen Git-säilön](get-started-setup-local.md).
