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
# <a name="docs-pr-validation-service"></a><span data-ttu-id="467cb-101">Docs PR -tarkistuspalvelu</span><span class="sxs-lookup"><span data-stu-id="467cb-101">Docs PR validation service</span></span>

<span data-ttu-id="467cb-102">Docs PR -tarkistuspalvelu on GitHub-sovellus, joka suorittaa tiedostojen kelpoisuussääntöjä PR:ssä.</span><span class="sxs-lookup"><span data-stu-id="467cb-102">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span>

<span data-ttu-id="467cb-103">Kun tarkistuspalvelu otetaan käyttöön säilössä, näet seuraavat toiminnot:</span><span class="sxs-lookup"><span data-stu-id="467cb-103">When the validation service is enabled on a repo, you'll see the following behavior:</span></span>

1. <span data-ttu-id="467cb-104">Lähetät PR:n.</span><span class="sxs-lookup"><span data-stu-id="467cb-104">You submit a PR.</span></span>
1. <span data-ttu-id="467cb-105">GitHubin kommentissa, joka ilmaiseen PR:n tilan, näet säilössä käyttöön otettujen tarkistusten tilan.</span><span class="sxs-lookup"><span data-stu-id="467cb-105">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="467cb-106">Huomaa, että tässä esimerkissä on käytössä kaksi tarkistusta: "Commit Validation" ja "OpenPublishing.Build":</span><span class="sxs-lookup"><span data-stu-id="467cb-106">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![jotkin tarkistukset epäonnistuivat](media/validation-failed.png)

   <span data-ttu-id="467cb-108">Koontiversio voi läpäistä tarkistuksen, vaikka tarkistusten vahvistus epäonnistuu.</span><span class="sxs-lookup"><span data-stu-id="467cb-108">Build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="467cb-109">Lisätietoa on **Tiedot**-kohdassa.</span><span class="sxs-lookup"><span data-stu-id="467cb-109">Click **Details** for more information.</span></span>
1. <span data-ttu-id="467cb-110">Tiedot-sivulla näkyvät kaikki epäonnistuneet kelpoisuustarkistukset ja tiedot ongelmien korjaamisesta:</span><span class="sxs-lookup"><span data-stu-id="467cb-110">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues:</span></span>

   ![tarkistusviesti](media/validation-details.png)

<span data-ttu-id="467cb-112">Artikkelin vasemmalla puolella olevassa sisällysluettelossa on luettelo palvelun tämän hetkisistä tarkistuksista.</span><span class="sxs-lookup"><span data-stu-id="467cb-112">See the left-hand TOC of this article for the list of validations currently in the service.</span></span>