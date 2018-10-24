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
# <a name="markdown-headings"></a><span data-ttu-id="d8612-103">Markdown-otsikot</span><span class="sxs-lookup"><span data-stu-id="d8612-103">Markdown headings</span></span>

<span data-ttu-id="d8612-104">Seuraavat tarkistusvaatimukset koskevat OPS Markdown -tiedostojen otsikoita.</span><span class="sxs-lookup"><span data-stu-id="d8612-104">The following validation requirements apply to headings in OPS Markdown files.</span></span>

## <a name="h1"></a><span data-ttu-id="d8612-105">H1</span><span class="sxs-lookup"><span data-stu-id="d8612-105">H1</span></span>

<span data-ttu-id="d8612-106">`H1` tarkoittaa Markdown-tiedoston ensimmäistä otsikkoa.</span><span class="sxs-lookup"><span data-stu-id="d8612-106">`H1` refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="d8612-107">Docs.microsoft.comiin julkaisemisen jälkeen H1 näkyy sivun yläreunassa suurella fontilla.</span><span class="sxs-lookup"><span data-stu-id="d8612-107">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span>

<span data-ttu-id="d8612-108">H1 luodaan aloittamalla viiva, jossa on yksi hajautusarvo (`#`), sitten välilyönti ja sitten otsikkoteksti.</span><span class="sxs-lookup"><span data-stu-id="d8612-108">An H1 is created by beginning a line with a single hash (`#`) followed by a space, then the heading text.</span></span> <span data-ttu-id="d8612-109">Esimerkiksi tämän artikkelin H1 on:</span><span class="sxs-lookup"><span data-stu-id="d8612-109">For example, the H1 of this article is:</span></span>

```md
# Markdown headings
```

<span data-ttu-id="d8612-110">H1-otsikoihin sovelletaan seuraavia sääntöjä:</span><span class="sxs-lookup"><span data-stu-id="d8612-110">The following rules apply to H1 headings:</span></span>

- <span data-ttu-id="d8612-111">Tiedostossa on oltava H1.</span><span class="sxs-lookup"><span data-stu-id="d8612-111">An H1 must be present in the file.</span></span>
- <span data-ttu-id="d8612-112">Siinä voi olla vain yksi H1.</span><span class="sxs-lookup"><span data-stu-id="d8612-112">There can only be one H1.</span></span>
- <span data-ttu-id="d8612-113">H1:ssä pitää olla sisältöä.</span><span class="sxs-lookup"><span data-stu-id="d8612-113">The H1 must have content.</span></span>

  ```markdown
  # 
  This is not allowed.
  ```
- <span data-ttu-id="d8612-114">`#`-hajautusarvon ja H1-sisällön välillä pitää olla välilyönti.</span><span class="sxs-lookup"><span data-stu-id="d8612-114">There must be a space between the `#` and the H1 content.</span></span> <span data-ttu-id="d8612-115">H1 ilman välilyöntiä ei hahmonnu otsikkona julkaistulla sivulla.</span><span class="sxs-lookup"><span data-stu-id="d8612-115">An H1 with no space doesn't render as a heading on the published page.</span></span>

  ```markdown
  #This looks bad on the site.
  ```
- <span data-ttu-id="d8612-116">H1:n on oltava tiedoston ensimmäinen sisältö YML-metatietojen otsikon jälkeen.</span><span class="sxs-lookup"><span data-stu-id="d8612-116">The H1 must be the first content in the file after the YML metadata header.</span></span> <span data-ttu-id="d8612-117">Sisältöä, kuten tekstiä tai kuvia, ei tarvitse olla YML-otsikon lopun ja H1:n välillä.</span><span class="sxs-lookup"><span data-stu-id="d8612-117">No content, such as text or images, is allowed between the end of the YML header and the H1.</span></span>

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- <span data-ttu-id="d8612-118">HTML-elementtiä ensimmäisen tason otsikoille `<h1>` ei pidä käyttää.</span><span class="sxs-lookup"><span data-stu-id="d8612-118">The HTML element for first-level headings, `<h1>`, should not be used.</span></span> <span data-ttu-id="d8612-119">Käytä Markdown-syntaksia (`# `).</span><span class="sxs-lookup"><span data-stu-id="d8612-119">Use the Markdown syntax (`# `).</span></span>
- <span data-ttu-id="d8612-120">H1:n pituus saa olla enintään 100 merkkiä.</span><span class="sxs-lookup"><span data-stu-id="d8612-120">The H1 should be no more than 100 characters long.</span></span> <span data-ttu-id="d8612-121">Tämä on tyylin ohje.</span><span class="sxs-lookup"><span data-stu-id="d8612-121">This is a style guideline.</span></span>

## <a name="h2---h6"></a><span data-ttu-id="d8612-122">H2–H6</span><span class="sxs-lookup"><span data-stu-id="d8612-122">H2 - H6</span></span>

<span data-ttu-id="d8612-123">H2 (`## `) – H6 (`###### `) ovat sallittuja OPS:ssä.</span><span class="sxs-lookup"><span data-stu-id="d8612-123">H2 (`## `) through H6 (`###### `) are allowed in OPS.</span></span> <span data-ttu-id="d8612-124">Käytä Markdown-otsikoita, älä HTML:ää (`<h2>` - `<h6>`) otsikoiden luomiseen.</span><span class="sxs-lookup"><span data-stu-id="d8612-124">Use the Markdown headers, not the HTML (`<h2>` - `<h6>`), to create headings.</span></span>
