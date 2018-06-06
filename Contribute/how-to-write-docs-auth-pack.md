---
title: Docs Authoring Pack VS Codelle
description: Tässä artikkelissa kerrotaan VS Code -laajennuspaketista, joka helpottaa docs.microsoft.com -sisällön luomista Markdown-syntaksilla.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: d0d61db2faf88598ecd2c800fb5fbe8df8ec44f5
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469574"
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs Authoring Pack VS Codelle

Docs Authoring Pack on kokoelma VS Code -laajennuksia, jotka helpottavat docs.microsoft.com -sisällön luomista Markdown-syntaksilla. Paketti on [saatavilla VS Code Marketplacesta](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack), ja se sisältää seuraavat laajennukset:

- **DocFx:** Sisältää docs.microsoft.comille suunnitellun Markdown-esikatselun. Katso lisätiedot [DocFx](https://marketplace.visualstudio.com/items?itemName=ms-docfx.DocFX)-ohjeista.
- **markdownlint:** David Ansonin suunnittelema suosittu Markdown-lintteri varmistaa, että Markdown-syntaksi noudattaa parhaita käytäntöjä. Katso lisätiedot [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)-ohjeista.
- **Docs Markdown:** Avustaa docs.microsoft.com-sisällön luomisessa Markdown-syntaksilla OPS-järjestelmässä. Sisältää perustason Markdown-tuen ja mukautetun Markdown-syntaksin tuen OPS:ssä. Aiheen loppuosa kuvailee Docs Markdown -laajennusta.

## <a name="prerequisites-and-assumptions"></a>Edellytykset ja oletukset

Jotta voit lisätä suhteellisia linkkejä, kuvia ja muuta upotettua sisältöä Docs Markdown -laajennuksella, VS Code -työtila on synkronoitava kloonatun OPS-pääsäilön kanssa.

Osa laajennuksen tukemasta syntaksista, kuten ilmoitukset ja koodikatkelmat, ovat OPS:lle mukautettua Markdown-syntaksia, jota ei näytetä oikein, ellei sitä julkaista OPS:n kautta.

## <a name="how-to-use-the-docs-markdown-extension"></a>Docs Markdown -laajennuksen käyttö

Voit avata Docs Markdown -valikon kirjoittamalla `ALT+M`. Voit valita haluamasi funktion napsauttamalla tai ylä-/alanuolinäppäimillä tai aloittaa suodatuksen kirjoittamalla. Paina `ENTER`, haluamasi funktio näkyy valikossa korostettuna. Voit käyttää seuraavia funktioita:

|Funktio     |Komento             |Kuvaus           |
|-------------|--------------------|----------------------|
|Lihavointi         |`formatBold`        |Lisää tekstiin **lihavointi**-muotoilun.|
|Kursivoitu       |`formatItalic`      |Lisää tekstiin *kursivointi*-muotoilun.|
|Koodi         |`formatCode`        |Jos valittuna on yksi rivi tai vähemmän, tekstiin lisätään seuraava muotoilu: `inline code`.<br><br>Jos valittuna on useita rivejä, niihin lisätään aidatun koodilohkon muotoilu. Lisäksi voit halutessasi valita OPS:n tukeman ohjelmointikielen.|
|Ilmoitus        |`insertAlert`       |Lisää Huomautus-, Tärkeää-, Varoitus- tai Vihje-sisällön.<br><br>Valitse valikosta Ilmoitus ja valitse sitten ilmoituksen tyyppi. Jos olet aiemmin valinnut tekstiä, sen ympärille lisätään valitun ilmoituksen syntaksi. Jos tekstiä ei ole valittu, uusi, paikkamerkillä varustettu ilmoitus lisätään.|
|Numeroitu luettelo|`insertNumberedList` |Lisää uuden numeroidun luettelon.<br><br> Jos useita rivejä on valittuna, jokaisesta tulee luettelokohde. Huomaa, että Markdownissa numeroitujen luettelojen järjestyslukuina näkyy aina 1, mutta docs.microsoft.comissa ne näkyvät peräkkäisinä järjestyslukuina tai, sisäkkäisten luettelojen tapauksessa, kirjaimina. Jos haluat luoda sisäkkäisen numeroidun luettelon, paina sarkainta pääluettelossa.|
|Luettelomerkeillä varustettu luettelo|`insertBulletedList` |Lisää uuden luettelomerkeillä varustetun luettelon.|
|Taulukko        |`insertTable`        |Lisää Markdown-taulukkorakenteen.<br><br>Kun valitset taulukko-komennon, määritä sarakkeiden ja rivien määrä (sarakkeet:rivit), esim. 3:4. Huomaa, että tämän laajennuksen avulla voit määrittää enintään viisi saraketta, mikä on luettavuuden kannalta korkein suositeltu määrä.|
|Linkitä         |`selectLinkType`      |Lisää linkin. Kun valitset tämän komennon, näyttöön tulee seuraava alavalikko.<br><br>`External`: Linkitä verkkosivustolle URI:n avulla. Tämän on sisällettävä ”http” tai ”https”.<br>`Internal`: Lisää suhteellinen linkki samassa säilössä olevaan toiseen tiedostoon. Kun olet valinnut tämän vaihtoehdon, suodata tiedostoja nimen perusteella kirjoittamalla komentoikkunaan ja valitse sitten haluamasi tiedosto. <br>`Bookmark in this file`: Valitse nykyisen tiedoston otsikoiden luettelosta, jos haluat lisätä oikein muotoillun kirjanmerkin.<br>`Bookmark in another file`: Suodata ensin tiedostonimen perusteella ja valitse tiedosto, johon haluat linkittää, ja valitse haluamasi otsikko valitusta tiedostosta.|
|Kuva        |`insertImage`     |Kirjoita vaihtoehtoinen teksti (pakollinen helppokäyttötoimintoja varten) ja valitse se, suodata säilössä olevat tuetut kuvatiedostot tällä komennolla ja valitse haluamasi tiedosto. Jos et ole valinnut vaihtoehtoista tekstiä komentoa käyttäessäsi, sinua pyydetään kirjoittamaan vaihtoehtoinen teksti ennen kuin voit valita kuvatiedoston.|
|Sisällytä      |`insertInclude`   |Etsi tiedosto, jonka haluat upottaa nykyiseen tiedostoon.|
|Koodikatkelma      |`insertSnippet`   |Etsi säilöstä koodikatkelma, jonka haluat upottaa nykyiseen tiedostoon.|
|Video        |`insertVideo`     |Lisää upotettu video.|
|Esikatsele      |`previewTopic`    |Esikatsele aktiivista aihetta rinnakkaisessa ikkunassa DocFX-laajennuksen avulla.  Jos DocFX-laajennusta ei ole asennettu tai jos asennettu laajennus on poistettu käytöstä, aihetta ei näytetä.


## <a name="how-to-assign-keyboard-shortcuts"></a>Pikanäppäinten määrittäminen

1. Avaa pikanäppäinluettelo kirjoittamalla `CTRL+K` ja sitten `CTRL+S`.
1. Hae komento, esim. `formatBold`, jolle haluat luoda mukautetun pikanäppäimen.
1. Vie hiiren osoitin rivin ylle ja napsauta esiin tulevaa plusmerkkiä.
1. Kun uusi tekstiruutu on näkyvissä, kirjoita pikanäppäin, jonka haluat sitoa kyseiseen komentoon. Jos haluat esimerkiksi käyttää lihavoinnin yleistä pikanäppäintä, kirjoita `ctrl+b`.
1. `when`-lauseke on hyvä lisätä pikanäppäimeen, jotta pikanäppäin toimii ainoastaan Markdown-tiedostoissa. Voit tehdä tämän avaamalla *keybindings.json*-tiedoston ja lisäämällä seuraavan rivin komennon nimen alapuolelle (muista lisätä rivien väliin pilkku):
   
    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    Valmis mukautettu pikanäppäin näyttää keybindings.json-tiedostossa seuraavalta:

    ```json
    // Place your key bindings in this file to overwrite the defaults
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

1. Tallenna keybindings.json.

Katso lisätiedot VS Code -ohjeiden [Pikanäppäimet](https://code.visualstudio.com/docs/getstarted/keybindings)-kohdasta.

## <a name="how-to-show-the-legacy-gauntlet-toolbar"></a>Vanhan ”Gauntlet”-työkalurivin näyttäminen

Jos olet ”Gauntlet”-koodinimellä tunnetun, laajennuksen vanhan version käyttäjä, sisällönluonnin työkalurivi ei enää näy VS Code -ikkunan alaosassa Docs Markdown -laajennuksen ollessa asennettu. Työkalurivi vei runsaasti tilaa VS Code -tilarivillä eikä se noudattanut käyttäjäkokemusten parhaita käytäntöjä, joten sitä ei käytetä laajennuksen uudessa versiossa. Voit kuitenkin halutessasi näyttää työkalurivin päivittämällä VS Coden settings.json-tiedoston seuraavasti:

1. Valitse VS Codessa Tiedosto -> Asetukset -> Asetukset (`CTRL+Comma`).
1. Jos valitset Käyttäjäasetukset, voit muuttaa kaikkien VS Code -työtilojen asetuksia. Jos valitset Työtilan asetukset, voit muuttaa ainoastaan senhetkisen työtilan asetuksia.
1. Etsi Oletusasetukset-ruudusta Docs Authoring -laajennuksen asetukset ja valitse kynäkuvake haluamiesi asetusten vierestä. Sinua pyydetään seuraavaksi valitsemaan joko `true` tai `false`. Kun olet tehnyt valintasi, VS Code lisää arvon automaattisesti settings.json-tiedostoon ja sinua pyydetään lataamaan ikkuna uudelleen, jotta muutokset tulevat voimaan.

## <a name="known-issues"></a>Tunnetut ongelmat

- DocFX-esikatselu: MacOS- ja Linux-järjestelmissä DocFX-esikatselu ei avaa esikatselua oikein (esikatselu valitsee oletusarvoisesti VS Code Markdown -esikatselun näissä ympäristöissä).
- DocFx-esikatselu: Kaikissa ympäristöissä jotkut syntaksit, kuten xref-viittaukset (ristiviittaukset) ohjelmointirajapintoihin, eivät näy esikatselussa oikein. Joissain tapauksissa sisältö voi olla puutteellista.
- Ulkoiset kirjanmerkit: Linux-järjestelmissä tiedostoluettelo näkyy ilman valittavia otsikoita.
- Sisällyttäminen: Linux-järjestelmissä tiedostoluettelo näkyy, mutta linkkiä ei lisätä valinnan jälkeen.
