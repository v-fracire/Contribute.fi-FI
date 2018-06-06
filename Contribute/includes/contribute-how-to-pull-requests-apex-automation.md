Kommenttien automaation avulla luku-tason käyttäjät (käyttäjät, joilla ei ole säilössä kirjoitusoikeuksia) voivat kirjoittaa kirjoitus-käyttöoikeustason toimintoja liittämällä asiamukaisen merkinnän pull-pyyntöön. Jos työstät säilöä, jossa kommenttien automaatio on otettu käyttöön, voit lisätä merkintöjä, muuttaa merkintöjä tai sulkea pull-pyynnön käyttämällä seuraavassa taulukossa lueteltuja aihetunnistekommentteja. Microsoftin työntekijöitä pyydetään sähköpostitse tarkistamaan ja hyväksymään julkisia säilöjä koskevat PR:t aina, kun kirjoittamiisi artikkeleihin ehdotetaan muutoksia.


| Aihetunnistekommentti | Vaikutus | Säilön saatavuus |
| --- | --- | --- |
| #sign-off |Kun artikkelin kirjoittaja kirjoittaa **#sign-off**-kommentin kommenttivirtaan, **ready-to-merge**-merkintä lisätään. Tämän merkinnän avulla säilön tarkistajan tietävät, milloin pull-pyyntö on valmis tarkistettavaksi/yhdistettäväksi. |Julkinen ja yksityinen |
| #sign-off |Jos osallistuja *ei* ole artikkelin tekijä ja yrittää hyväksyä julkisen pull-pyynnön **#sign-off** -kommentilla, pull-pyyntöön kirjoitetaan viesti, joka ilmaisee, että ainoastaan artikkelin tekijä voi lisätä merkinnän. |Julkinen |
| #hold-off |Tekijä voi kirjoittaa **#hold-off** PR-kommentteihin poistaakseen **ready-to-merge**-merkinnän, jos hänen mielensä muuttuu tai jos hän teki virheen. Yksityisessä säilössä tämä lisää **do-not-merge** -merkinnän. |Julkinen ja yksityinen |
| #please-close |Tekijä voi kirjoittaa **#please-close** kommenttivirtaan, jos hän ei halua muutoksia yhdistettävän. |Julkinen |
