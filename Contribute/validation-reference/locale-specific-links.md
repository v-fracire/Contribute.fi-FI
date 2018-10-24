# <a name="locale-specific-links"></a>Kieliasetuskohtaiset linkit

Kieliasetuskoodeja,kuten `en-us`, ei pitäisi sisällyttää tiettyihin Microsoft-sivustoihin johtaviin linkkeihin. Jos sisällytät kieliasetuskoodin linkkiin englanninkielisessä sisällössä, se sisällytetään myös lokalisoituihin linkkeihin, mikä johtaa huonoon lokalisointikokemukseen. Jos esimerkiksi linkki saksaksi lokalisoituun sisältöön sisältää koodin `en-us`, saksankieliset asiakkaat seuraavat linkkiä englanninkieliseen artikkeliin, vaikka saksankielinenkin versio olisi saatavana.

Poista kieliasetuskoodit Microsoft-sivustoihin johtavista linkeistä. Seuraavassa on esimerkki.

Ennen:

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

Jälkeen:

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

Seuraavat sivustot sisältyvät tämän tarkistuksen alueeseen:

- azure.microsoft.com
- docs.microsoft.com
- msdn.microsoft.com
- technet.microsoft.com