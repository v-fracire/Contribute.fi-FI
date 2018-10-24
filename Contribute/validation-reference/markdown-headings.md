---
title: Markdown-otsikot
description: Tässä artikkelissa kuvataan Markdown-otsikoita koskevat vaatimukset.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 05/03/2017
ms.openlocfilehash: 18beb815fdf7caad3e8e675e8d79853d8a5688f2
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084487"
---
# <a name="markdown-headings"></a>Markdown-otsikot

Seuraavat tarkistusvaatimukset koskevat OPS Markdown -tiedostojen otsikoita.

## <a name="h1"></a>H1

`H1` tarkoittaa Markdown-tiedoston ensimmäistä otsikkoa. Docs.microsoft.comiin julkaisemisen jälkeen H1 näkyy sivun yläreunassa suurella fontilla.

H1 luodaan aloittamalla viiva, jossa on yksi hajautusarvo (`#`), sitten välilyönti ja sitten otsikkoteksti. Esimerkiksi tämän artikkelin H1 on:

```md
# Markdown headings
```

H1-otsikoihin sovelletaan seuraavia sääntöjä:

- Tiedostossa on oltava H1.
- Siinä voi olla vain yksi H1.
- H1:ssä pitää olla sisältöä.

  ```markdown
  # 
  This is not allowed.
  ```
- `#`-hajautusarvon ja H1-sisällön välillä pitää olla välilyönti. H1 ilman välilyöntiä ei hahmonnu otsikkona julkaistulla sivulla.

  ```markdown
  #This looks bad on the site.
  ```
- H1:n on oltava tiedoston ensimmäinen sisältö YML-metatietojen otsikon jälkeen. Sisältöä, kuten tekstiä tai kuvia, ei tarvitse olla YML-otsikon lopun ja H1:n välillä.

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- HTML-elementtiä ensimmäisen tason otsikoille `<h1>` ei pidä käyttää. Käytä Markdown-syntaksia (`# `).
- H1:n pituus saa olla enintään 100 merkkiä. Tämä on tyylin ohje.

## <a name="h2---h6"></a>H2–H6

H2 (`## `) – H6 (`###### `) ovat sallittuja OPS:ssä. Käytä Markdown-otsikoita, älä HTML:ää (`<h2>` - `<h6>`) otsikoiden luomiseen.
