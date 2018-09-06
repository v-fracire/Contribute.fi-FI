---
title: Docs Authoring Pack VS Codelle
description: Tässä artikkelissa kerrotaan VS Code -laajennuspaketista, joka helpottaa docs.microsoft.com -sisällön luomista Markdown-syntaksilla.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.openlocfilehash: b9fedce0a73c5c4212ffd0893c745fab56677c8c
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308912"
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs Authoring Pack VS Codelle

Docs Authoring Pack on kokoelma VS Code -laajennuksia, jotka helpottavat docs.microsoft.com -sisällön luomista Markdown-syntaksilla. Paketti on [saatavilla VS Code Marketplacesta](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack), ja se sisältää seuraavat laajennukset:

- [markdownlint:](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) David Ansonin suunnittelema suosittu Markdown-lintteri varmistaa, että Markdown-syntaksi noudattaa parhaita käytäntöjä.
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): täysin offline-tilassa käytettävä oikeinkirjoituksen tarkistus Street Side Softwarelta.
- [Docs Preview](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): käyttää docs.microsoft.comin CSS-tyylisivuja entistä tarkemman Markdown-esikatselun tuottamiseksi mukautetut Markdownit mukaan lukien.
- [Docs Markdown:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) Avustaa docs.microsoft.com-sisällön luomisessa Markdown-syntaksilla OPS-järjestelmässä. Sisältää perustason Markdown-tuen ja mukautetun Markdown-syntaksin tuen OPS:ssä. Aiheen loppuosa kuvailee Docs Markdown -laajennusta.
- [Docs Article Templates](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): Antaa käyttäjille mahdollisuuden käyttää Markdown-runkoista sisältöä uusissa tiedostoissa.

## <a name="prerequisites-and-assumptions"></a>Edellytykset ja oletukset

Jotta voit lisätä suhteellisia linkkejä, kuvia ja muuta upotettua sisältöä Docs Markdown -laajennuksella, VS Code -työtila on synkronoitava kloonatun OPS (Open Publishing System) -pääsäilön kanssa.

Osa laajennuksen tukemasta syntaksista, kuten ilmoitukset ja koodikatkelmat, ovat OPS:lle mukautettua Markdown-syntaksia, jota ei näytetä oikein, ellei sitä julkaista OPS:n kautta.

## <a name="how-to-use-the-docs-markdown-extension"></a>Docs Markdown -laajennuksen käyttö

Voit avata Docs Markdown -valikon kirjoittamalla `ALT+M`. Voit valita haluamasi funktion napsauttamalla tai ylä-/alanuolinäppäimillä tai aloittaa suodatuksen kirjoittamalla. Paina `ENTER`, haluamasi funktio näkyy valikossa korostettuna. Voit käyttää seuraavia funktioita:

|Funktio     |Kuvaus           |
|-------------|----------------------|
|Esikatsele      |Esikatsele aktiivista aihetta rinnakkaisessa ikkunassa Docs Preview -laajennuksen avulla. Tämä vaihtoehto käytettävissä vain, jos Docs Preview on asennettu.|
|Lihavointi         |Lisää tekstiin **lihavointi**-muotoilun.|
|Kursivoitu       |Lisää tekstiin *kursivointi*-muotoilun.|
|Koodi         |Jos valittuna on yksi rivi tai vähemmän, tekstiin lisätään seuraava muotoilu: `inline code`.<br><br>Jos valittuna on useita rivejä, niihin lisätään aidatun koodilohkon muotoilu. Lisäksi voit halutessasi valita OPS:n tukeman ohjelmointikielen.|
|Ilmoitus        |Lisää Huomautus-, Tärkeää-, Varoitus- tai Vihje-sisällön.<br><br>Valitse valikosta Ilmoitus ja valitse sitten ilmoituksen tyyppi. Jos olet aiemmin valinnut tekstiä, sen ympärille lisätään valitun ilmoituksen syntaksi. Jos tekstiä ei ole valittu, uusi, paikkamerkillä varustettu ilmoitus lisätään.|
|Numeroitu luettelo|Lisää uuden numeroidun luettelon.<br><br> Jos useita rivejä on valittuna, jokaisesta tulee luettelokohde. Huomaa, että Markdownissa numeroitujen luettelojen järjestyslukuina näkyy aina 1, mutta docs.microsoft.comissa ne näkyvät peräkkäisinä järjestyslukuina tai, sisäkkäisten luettelojen tapauksessa, kirjaimina. Jos haluat luoda sisäkkäisen numeroidun luettelon, paina sarkainta pääluettelossa.|
|Luettelomerkeillä varustettu luettelo|Lisää uuden luettelomerkeillä varustetun luettelon.|
|Taulukko        |Lisää Markdown-taulukkorakenteen.<br><br>Kun valitset taulukko-komennon, määritä sarakkeiden ja rivien määrä (sarakkeet:rivit), esim. 3:4. Huomaa, että tämän laajennuksen avulla voit määrittää enintään viisi saraketta, mikä on luettavuuden kannalta korkein suositeltu määrä.|
|Linkki tiedostoon säilössä|Lisää suhteellisen linkin nykyisessä säilössä olevaan toiseen tiedostoon. Kun olet valinnut tämän vaihtoehdon, suodata tiedostoja nimen perusteella kirjoittamalla komentoikkunaan ja valitse sitten haluamasi tiedosto. Jos olit aiemmin valinnut tekstiä, siitä tulee linkin teksti. Muussa tapauksessa kohdetiedoston H1:tä käytetään linkin tekstinä.|
|Linkki verkkosivuun    |Lisää linkin verkkosivuun. Kun olet valinnut tämän vaihtoehdon, liitä tai kirjoita URI komentoikkunaan. `https://` on pakollinen. Jos olit aiemmin valinnut tekstiä, siitä tulee linkin teksti. Muussa tapauksessa URIa käytetään linkin tekstinä.|
|Linkki otsikkoon     |Lisää linkin kirjanmerkkiin nykyisessä tiedostossa tai säilössä olevassa toisessa tiedostossa.<br>`Bookmark in this file`: Valitse nykyisen tiedoston otsikoiden luettelosta, jos haluat lisätä oikein muotoillun kirjanmerkin.<br>`Bookmark in another file`: Suodata ensin tiedostonimen perusteella ja valitse tiedosto, johon haluat linkittää, ja valitse haluamasi otsikko valitusta tiedostosta.|
|Kuva        |Kirjoita vaihtoehtoinen teksti (pakollinen helppokäyttötoimintoja varten) ja valitse se, suodata säilössä olevat tuetut kuvatiedostot tällä komennolla ja valitse haluamasi tiedosto. Jos et ole valinnut vaihtoehtoista tekstiä komentoa käyttäessäsi, sinua pyydetään kirjoittamaan vaihtoehtoinen teksti ennen kuin voit valita kuvatiedoston.|
|Sisällytä      |Etsi tiedosto, jonka haluat upottaa nykyiseen tiedostoon.|
|Koodikatkelma      |Etsi säilöstä koodikatkelma, jonka haluat upottaa nykyiseen tiedostoon.|
|Video        |Lisää upotettu video.|
|Malli     |Luo uusi tiedosto ja käytä Markdown-mallia. Lisätietoja on [Mallit](#how-to-use-docs-templates)-osiossa alla.|

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

## <a name="how-to-show-the-legacy-toolbar"></a>Vanhan työkalurivin näyttäminen

Laajennuksen esijulkaisuversion käyttäjät huomaavat, että sisällönluonnin työkalurivi ei enää näy VS Code -ikkunan alaosassa, kun Docs Markdown -laajennus on asennettu. Työkalurivi vei runsaasti tilaa VS Code -tilarivillä eikä se noudattanut käyttäjäkokemusten parhaita käytäntöjä, joten sitä ei käytetä laajennuksen uudessa versiossa. Voit kuitenkin halutessasi näyttää työkalurivin päivittämällä VS Coden settings.json-tiedoston seuraavasti:

1. Valitse VS Codessa Tiedosto -> Asetukset -> Asetukset (`CTRL+Comma`).
1. Jos valitset Käyttäjäasetukset, voit muuttaa kaikkien VS Code -työtilojen asetuksia. Jos valitset Työtilan asetukset, voit muuttaa ainoastaan senhetkisen työtilan asetuksia.
1. Etsi Oletusasetukset-ruudusta Docs Authoring -laajennuksen asetukset ja valitse kynäkuvake haluamiesi asetusten vierestä. Sinua pyydetään seuraavaksi valitsemaan joko `true` tai `false`. Kun olet tehnyt valintasi, VS Code lisää arvon automaattisesti settings.json-tiedostoon ja sinua pyydetään lataamaan ikkuna uudelleen, jotta muutokset tulevat voimaan.

## <a name="how-to-use-docs-templates"></a>Docs-mallien käyttäminen

Docs Article Templates -laajennuksella VS Codea käyttävät kirjoittajat voivat noutaa Markdown-mallin keskitetystä säilöstä ja käyttää sitä tiedostoon. Mallit auttavat esimerkiksi varmistamaan, että artikkeleihin lisätään tarvittavat metatiedot ja että sisällön standardeja on noudatettu. Malleja hallitaan Markdown-tiedostoina julkisessa GitHub-säilössä.

### <a name="to-apply-a-template-in-vs-code"></a>Mallin käyttäminen VS Codessa

1. Jos Docs Markdown -laajennusta ei ole asennettu, avaa komentoikkuna F1-näppäimellä ja kirjoita suodattimeen ”template”. Valitse sitten `Docs: Template`. Jos Docs Markdown on asennettu, voit avata Docs Markdownin pikavalintavalikon joko komentoikkunalla tai valitsemalla `Alt+M`. Valitse sitten luettelosta `Template`.
1. Valitse haluamasi malli avautuvasta luettelosta.

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>GitHub-tunnuksen ja/tai Microsoft-aliaksen lisääminen VS Code -asetuksiin

Templates-laajennus tukee kolmea dynaamista metatietokenttää: author, ms.author ja ms.date. Jos mallin luoja käyttää näitä kenttiä Markdown-mallin metatieto-otsikkona, ne täytetään automaattisesti tiedostoosi, kun otat mallin käyttöön:

|Metatieto  |Arvo|
|----------|---------------|
|author    |Oma GitHub-tunnuksesi, jos se on määritetty VS Code -asetustiedostossasi.|
|ms.author |Oma Microsoft-aliaksesi, jos se on määritetty VS Code -asetustiedostossasi. Jos et ole  Microsoftin työntekijä, jätä tämä määrittämättä.|
|ms.date   |Nykyinen päivämäärä Docs-tuetussa muodossa: KK/PP/VVVV. Huomaa, että päivämäärää ei päivitetä automaattisesti, jos päivität tiedoston myöhemmin. Se on päivitettävä manuaalisesti kuvastamaan artikkelin päivitysaikaa.|

### <a name="to-set-author-github-id-andor-msauthor-microsoft-alias"></a>author-arvon (GitHub-tunnus) ja/tai ms.author-arvon (Microsoft-alias) asettaminen

1. Valitse VS Codessa Tiedosto -> Asetukset -> Asetukset (`CTRL+Comma`).
1. Jos valitset Käyttäjäasetukset, voit muuttaa kaikkien VS Code -työtilojen asetuksia. Jos valitset Työtilan asetukset, voit muuttaa ainoastaan senhetkisen työtilan asetuksia.
1. Etsi vasemmalla olevasta Oletusasetukset-ruudusta Docs Article Templates -laajennuksen määritykset. Napsauta haluamasi asetuksen vieressä olevaa kynäkuvaketta ja valitse Korvaa asetuksissa.
1. Rinnalle avautuu Käyttäjäasetukset-ruutu, jonka alaosassa näet uuden merkinnän.
1. Lisää GitHub-tunnus tai Microsoft-sähköpostialias ja tallenna tiedosto.
1. Joudut ehkä käynnistämään VS Coden uudelleen, jotta muutokset tulevat voimaan.
1. Kun nyt käytät mallia, jossa käytetään dynaamisia kenttiä, oma GitHub-tunnuksesi ja/tai Microsoft-aliaksesi täytetään automaattisesti metatieto-otsikkoon.
