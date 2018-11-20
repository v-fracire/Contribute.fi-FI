---
title: Kieleen ja sävyyn liittyvät ohjeet .NET-ohjeiden kehittämiseen osallistujille
description: Opettele kieleen ja sävyyn liittyvät ohjeemme vertailemalla ohjeiden mukaisia ja niiden vastaisia esimerkkejä.
ms.date: 11/07/2018
ms.openlocfilehash: cf78bb5d476d35b9b168b619e90e8f372103cb93
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609689"
---
# <a name="voice-and-tone-guidelines"></a>Kielen ja sävyn ohjeet

Erilaiset ihmiset, mukaan lukien IT-ammattilaiset ja kehittäjät, lukevat kirjoittamiasi ohjeistuksia niin .NETin oppimiseen kuin sen käyttämiseen tavallisessa työssään. Sinun tehtäväsi on luoda toimivat ohjeet, jotka auttavat lukijaa työssään. Ohjeemme auttavat sinua siinä. Tyylioppaassamme annetaan seuraavat suositukset:

Jokaisesta kohdasta annetaan esimerkkejä sitä mukaa, kun luet tyyliopasta. Ohjeissa annetaan esimerkkejä, joita voit hyödyntää, kun luot .NET-ohjeistuksia. Annamme myös vastakohtaisia esimerkkejä siitä, miltä artikkelit näyttävät, kun ohjeita ei noudateta.

## <a name="use-a-conversational-tone"></a>Käytä keskustelevaa sävyä

### <a name="appropriate-style"></a>Ohjeiden mukainen esimerkki

Haluamme, että ohjeistuksen sävy on keskusteleva. Opetusohjelmien ja selitysten lukijalle pitäisi tulla sellainen olo, että hän keskustelee suoraan kirjoittajan kanssa. Hänelle tulisi jäädä tekstistä epämuodollinen, keskusteleva ja ja informatiivinen vaikutelma. Tekstin tulisi kuulostaa siltä, kuin lukija kuuntelisi kirjoittajan selitystä eri aiheista.

### <a name="inappropriate-style"></a>Ohjeiden vastainen esimerkki

Keskustelutyylin sekä esimerkiksi teknisiä aiheita käsittelevissä akateemisissa teksteissä tavattavan tyylin välillä havaitaan suuri kontrasti. Viimeksi mainitun kaltaiset resurssit ovat hyödyllisiä, mutta niissä käytettävä tyyli poikkeaa merkittävästi ohjeistuksessamme preferoidusta tyylistä. Lukiessaan akateemista julkaisua lukija kohtaa hyvin erilaisen sävyn ja kirjoittamistyylin. Syntyy vaikutelma ikävystyttävästä aiheesta, joka on vielä esitetty ikävystyttävällä tavalla.  

Yllä olevista kappaleista ensimmäisessä noudatetaan suositustamme keskustelevasta tyylistä. Toinen kappale on kirjoitettu akateemisempaan sävyyn. Eron huomaa heti. 

## <a name="write-in-second-person"></a>Kirjoita toisessa persoonassa

### <a name="appropriate-style"></a>Ohjeiden mukainen esimerkki

Sinun kannattaa kirjoittaa artikkelisi ikään kuin puhuisit suoraan lukijalle. Käytä toista persoonaa (kuten minä olen käyttänyt näissä kahdessa virkkeessä). Et välttämättä tarvitse toisen persoonan käyttöön sinä-pronominia. Pyri kirjoittamaan suoraan lukijalle. Voit kirjoittaa virkkeet käskymuodossa. Kerro lukijalle, mitä haluat tämän oppivan.

### <a name="inappropriate-style"></a>Ohjeiden vastainen esimerkki

Kirjoittaja voi päättää kirjoittaa tekstinsä myös kolmannessa persoonassa. Tässä mallissa kirjoittajan täytyy käyttää pronominia tai substantiivia viitatessaan lukijaan. Lukijan mielestä kolmannen persoonan käyttö voi tehdä tekstistä vähemmän kiinnostavan ja vähemmän miellyttävän lukea.

Ensimmäisessä kappaleessa käytetään suositeltua tyyliä. Toinen kappale on kirjoitettu kolmannessa persoonassa. Käytä toista persoonaa. Sitä oli todennäköisesti sinunkin mielestäsi helpompi lukea.

## <a name="use-active-voice"></a>Kirjoita aktiivimuodossa

Kirjoita artikkelit aktiivimuodossa. Aktiivimuoto tarkoittaa sitä, että virkkeen subjekti suorittaa virkkeen kuvaaman toiminnan (verbin). Aktiivimuodon vastakohta on passiivimuoto, jossa lauseen rakenne on sellainen, että virkkeen subjekti onkin toiminnan kohde. Vertaile näitä kahta esimerkkiä:

>Kääntäjä muunsi lähdekoodin suoritettavaksi tiedostoksi.

>Lähdekoodi muunnettiin suoritettavaksi tiedostoksi kääntäjän toimesta.

Ensimmäinen virke on aktiivimuotoinen. Toinen virke kirjoitettiin passiivimuodossa. (Myös edellä olevat lauseet toimivat esimerkkeinä kummastakin tyylistä).

Suosittelemme käyttämään aktiivimuotoa, koska sitä on helpompi lukea. Passiivimuoto voi tehdä tekstistä vaikealukuisen.

## <a name="target-a-fifth-grade-reading-level"></a>Kirjoita englanninkieliset artikkelit niin, että lukija ymmärtää ne kouluenglannilla.

Tämä viimeinen suositus on annettu siksi, että kaikki lukijat eivät osaa englantia yhtä hyvin. Kirjoitat artikkeleita kansainväliselle yleisölle. Huomioi siis kirjoittaessasi, että kaikilla lukijoilla ei välttämättä ole yhtä laajaa englannin sanavarastoa kuin sinulla.

Toisaalta kirjoitat kuitenkin teknisten alojen ammattilaisille. Voit olettaa lukijoiden tietävän laajasti ohjelmoinnista ja tuntevan ohjelmointitermit myös englanniksi. Object Oriented Programming, Class sekä Object, Function ja Method ovat heille tuttuja termejä. Kaikilla artikkelin lukijoilla ei kuitenkaan ole varsinaista tietotekniikan tutkintoa. Idempotent (idempotenssi) on esimerkki termistä, joka kannattaa määritellä, jos käytät sitä:

>The `Close()` method is idempotent, meaning that you can call it multiple times and the effect is the same as if you called it once. (Metodi on idempotentti, eli vaikutus on sama riippumatta siitä, montako kertaa toiminto suoritetaan.)

## <a name="avoid-future-tense"></a>Vältä futuurin käyttöä

Futuuria eli tulevaa aikamuotoa ei kaikissa kielissä ymmärretä samalla tavalla. Futuurin käyttö voikin tehdä ohjeistuksesta vaikealukuisen. Futuurin käyttö herättää lisäksi lukijassa usein kysymyksen siitä, milloin kuvailtu asia tapahtuu. Jos siis kirjoitat ”PowerShellin oppimisesta tulee olemaan sinulle hyötyä”, lukijalle herää heti kysymys siitä, milloin siitä on hyötyä. Käytä mieluummin ilmaisua ”PowerShellin oppiminen on hyödyllistä.”

## <a name="what-is-it---so-what"></a>Mitä tarkoitat ja mitä siitä?

Kun esittelet lukijalle uuden asian, määrittele se ensin ja kerro vasta sitten, miksi siitä on hyötyä. Lukijalle on tärkeää ymmärtää ensin, mistä on kysymys. Vasta sen jälkeen hän voi ymmärtää asian hyödyt (tai haitat).
