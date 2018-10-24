---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084527"
---
# <a name="docs-pr-validation-service"></a>Docs PR -tarkistuspalvelu

Docs PR -tarkistuspalvelu on GitHub-sovellus, joka suorittaa tiedostojen kelpoisuussääntöjä PR:ssä.

Kun tarkistuspalvelu otetaan käyttöön säilössä, näet seuraavat toiminnot:

1. Lähetät PR:n.
1. GitHubin kommentissa, joka ilmaiseen PR:n tilan, näet säilössä käyttöön otettujen tarkistusten tilan. Huomaa, että tässä esimerkissä on käytössä kaksi tarkistusta: "Commit Validation" ja "OpenPublishing.Build":

   ![jotkin tarkistukset epäonnistuivat](media/validation-failed.png)

   Koontiversio voi läpäistä tarkistuksen, vaikka tarkistusten vahvistus epäonnistuu.

1. Lisätietoa on **Tiedot**-kohdassa.
1. Tiedot-sivulla näkyvät kaikki epäonnistuneet kelpoisuustarkistukset ja tiedot ongelmien korjaamisesta:

   ![tarkistusviesti](media/validation-details.png)

Artikkelin vasemmalla puolella olevassa sisällysluettelossa on luettelo palvelun tämän hetkisistä tarkistuksista.