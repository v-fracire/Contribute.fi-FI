## <a name="pull-request-processing"></a>Pull-pyynnön käsittely

Edellisessä osiossa opastettiin, miten voit lähettää ehdotettuja muutoksia niputtamalla ne uuteen pull-pyyntöön (PR), joka lisätään kohdesäilön PR-jonoon. Pull-pyyntö käynnistää GitHub-yhteistyömallin kysymällä, haluatko vetää ja yhdistää muutokset työstämästäsi haarasta toiseen haaraan. Useimmissa tapauksissa kyseinen toinen haara on pääsäilön oletus-/päähaara.

### <a name="validation"></a>Vahvistus

Pull-pyynnölle saatetaan suorittaa yksi tai useampi PR-vahvistusprosessi, ennen kuin se voidaan yhdistää kohdehaaraan. Tarkistusprosessit vaihtelevat ehdotettujen muutosten laajuuden ja kohdesäilön sääntöjen mukaan. Pull-pyynnön lähettämisen jälkeen voi tapahtua yksi tai useampi seuraavista:

- **Yhdistettävyys**: Perustason GitHub-yhdistettävyyskoe suoritetaan ensin, jotta voidaan tarkistaa, ovatko käyttämäsi haaran ehdotetut muutokset ristiriidassa kohdehaaran kanssa. Jos pull-pyyntö ilmaisee, että tämä testi epäonnistui, sinun on korjattava yhdistämisristiriidan aiheuttava sisältö, ennen kuin käsittelyä voidaan jatkaa.
- **CLA**: Jos osallistut julkisen säilön sisällöntuottoon etkä ole Microsoftin työntekijä, ehdotettujen muutosten vaikuttavuuden perusteella sinua saatetaan pyytää täyttämään lyhyt osallistumisen käyttöoikeussopimus (Contribution License Agreement, CLA) ensimmäisen kerran, kun lähetät pull-pyynnön kyseiseen säilöön. Pull-pyyntö käsitellään, kun CLA-vaihe on suoritettu.
- **Merkinnät**: Pull-pyyntöihin lisätään automaattisesti merkintä ilmaisemaan pull-pyynnön tila vahvistusprosessissa. Esimerkiksi uudet pull-pyynnöt saatetaan automattisesti merkitä ”do-not-merge”-merkinnällä, joka osoittaa, että pull-pyyntö ei ole vielä ollut vahvistus-, tarkastus- ja hyväksyntävaiheessa.
- **Vahvistus ja koostaminen**: Automaattiset tarkastukset varmistavat, läpäisevätkö muutokset vahvistustestit. Vahvistustestit saattavat palauttaa varoituksia tai virheitä, jotka edellyttävät muutoksia yhteen tai useampaan pull-pyynnön tiedostoon, ennen kuin se voidaan yhdistää. Vahvistustestin tulokset lisätään kommenttina pull-pyyntöön tarkistettavaksi ja ne voidaan lähettää sinulle sähköpostitse.
- **Valmistelu**: Vahvistuksen ja koostamisen jälkeen artikkelisivut, joita tekemäsi muutokset koskevat, lisätään automaattisesti valmisteluympäristöön tarkistettavaksi. Esikatselun URL-osoitteet näkyvät PR-kommentissa.
- **Automaattinen yhdistämisen**: Pull-pyyntö voidaan yhdistää automaattisesti, jos se läpäisee vahvistustestauksen ja tietyt ehdot. Tällaisessa tapauksessa sinun ei tarvitse enää tehdä mitään.

### <a name="review-and-sign-off"></a>Tarkistus ja hyväksyntä

Kun PR-käsittely on valmis, tarkista sen tulokset (PR-kommentit, esikatselun URL-osoitteet jne.) ja määritä, tarvitseeko tiedostoihin tehdä vielä muutoksia ennen kuin hyväksyt niiden yhdistämisen. Jos PR-tarkistaja on tarkistanut pull-pyyntösi, hän voi antaa myös palautetta kommenteilla, jos hän tarvitsee vastauksia kysymyksiin tai ratkaisuja ongelmiin ennen yhdistämistä.

[!INCLUDE[contribute-how-to-pull-requests-apex-automation.md](contribute-how-to-pull-requests-apex-automation.md)]

Kun pull-pyynnössä ei ole ongelmia ja se on hyväksytty, muutokset yhdistetään päähaaraan ja pull-pyyntö suljetaan.

### <a name="publishing"></a>Julkaiseminen

Muista, että PR-tarkistajan on yhdistettävä pull-pyyntö, ennen kuin muutokset voidaan sisällyttää seuraavaan ajoitettuun julkaisuun. Pull-pyynnöt tarkistetaan ja yhdistetään tavallisesti lähetysjärjestyksessä. Jos pull-pyyntö edellyttää yhdistämistä tiettyä julkaisua varten, ole ennalta yhteydessä PR-tarkistajaasi ja varmista yhdessä hänen kanssaan, että yhdistäminen tapahtuu ennen julkaisemista.

Kun panoksesi on hyväksytty ja yhdistetty, se lisätään docs.microsoft.com-julkaisuprosessiin. Julkaisuajat vaihtelevat julkaistavan sisällön kohdesäilöä hallinnoivan tiimin mukaan. Seuraavissa poluissa julkaistut artikkelit otetaan tavallisesti käyttöön noin klo 10:30 ja 15:30 Tyynenmeren aikaa maanantaista perjantaihin:

- https://docs.microsoft.com/azure/
- https://docs.microsoft.com/aspnet/
- https://docs.microsoft.com/dotnet/
- https://docs.microsoft.com/enterprise-mobility-security

Tavallisesti kestää enintään 45 minuuttia, ennen kuin julkaistu artikkeli näkyy verkossa. Kun artikkeli on julkaistu, voit tarkistaa tekemäsi muutokset asianmukaisessa URL-osoitteessa: `https://docs.microsoft.com/<path-to-your-article-without-the-md-extension>`.
