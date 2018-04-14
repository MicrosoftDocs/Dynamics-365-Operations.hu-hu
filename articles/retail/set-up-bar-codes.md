---
title: "Vonalkódk beállítása"
description: "Ez a cikk a vonalkódok Microsoft Dynamics 365 for Retail rendszerben történő használatát írja le."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 099779707cb2b9b821085563b155976cd6ff8777
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-bar-codes"></a><span data-ttu-id="cdfe9-103">Vonalkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="cdfe9-103">Set up bar codes</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="cdfe9-104">Ez a cikk a vonalkódok Microsoft Dynamics 365 for Retail rendszerben történő használatát írja le.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-104">This article describes how to use bar codes in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="cdfe9-105">A vonalkódok segítségével beszerzéseket és értékesítéseket is kezelhet, termékváltozatokat követhet nyomon, és vevőket és alkalmazottakat állíthat be.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-105">You can use bar codes to purchase and sell products, track product variants, and set up customers and employees.</span></span> <span data-ttu-id="cdfe9-106">A vonalkódokkal emellett utalványokat, ajándékutalványokat és jóváírásokat adhat ki és hitelesíthet.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-106">You can also use bar codes to issue and endorse coupons, gift cards, and credit memos.</span></span> <span data-ttu-id="cdfe9-107">A kereskedelmi termékekhez szabványos vonalkódok, és egyéni, saját kódolású alkalmazott vonalkódok is beállíthatók.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-107">You can set up retail products so that they have standard bar codes or custom, in-house bar codes.</span></span> <span data-ttu-id="cdfe9-108">Egy termékhez egynél több vonalkód is tartozhat.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-108">Products can have more than one bar code.</span></span> <span data-ttu-id="cdfe9-109">Például egy termék több vonalkóddal rendelkezhet, ha különböző gyártóktól származik, vagy ha méret, stílus és szín tekintetében különböző variánsai vannak.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-109">For example, a product might have multiple bar codes if it comes from various manufacturers, or if it has variants that are based on size, style, or color.</span></span> <span data-ttu-id="cdfe9-110">A vonalkódok a termék súlyát és árát is magukban foglalhatják.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-110">Bar codes can include the weight or price of the product.</span></span> <span data-ttu-id="cdfe9-111">A vonalkódmaszkok a vonalkódok létrehozásához használt sablonok.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-111">Bar code masks are templates that are used to create bar codes.</span></span> <span data-ttu-id="cdfe9-112">**Megjegyzés:** Ha az egyes változatokhoz egyedi vonalkódot rendel, akkor a termék vonalkódjának pénztárgépnél történő leolvasásával lehetővé válik, hogy a program megtalálja az éppen értékesített változatot.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-112">**Note:** If you assign a unique bar code to each variant combination, you can scan the bar code at the register and let the program determine which variant of the product is being sold.</span></span> <span data-ttu-id="cdfe9-113">Emellett ez lehetővé teszi, hogy változatok szerinti értékesítési statisztikát készítsen és jelenítsen meg.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-113">You can also collect and view statistics about sales by variant.</span></span> <span data-ttu-id="cdfe9-114">Minden egyes méret-, szín- és stíluscsoporthoz egy egyedi szám társítható, amely egy vonalkódba csoportosul.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-114">Each size, color, and style group can be assigned a unique number that identifies that group in the bar code.</span></span> <span data-ttu-id="cdfe9-115">A Dynamics 365 for Retail a vonalkódmaszk segítségével automatikusan előállítja minden egyes változat-kombináció vonalkódját.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-115">Dynamics 365 for Retail uses the bar code mask to automatically generate bar codes for each variant combination.</span></span> <span data-ttu-id="cdfe9-116">Ez a funkció hasznos lehet, ha sok méret, szín vagy stílus fordul elő, mivel a kombinációk száma az egyes változatkódok hozzáadásával jelentősen nő.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-116">This functionality can be useful if there are many sizes, colors, and styles, because the number of combinations increases significantly as each variant code is added.</span></span> <span data-ttu-id="cdfe9-117">Ha nem használják ezt a funkciót, akkor a vonalkódokat kézzel kell hozzárendelni a termékváltozatot képviselő minden egyes kombinációhoz.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-117">If this functionality isn't used, bar codes must be manually assigned to each combination that represents a product variant.</span></span> <span data-ttu-id="cdfe9-118">A vonalkódokat manuálisan és automatikusan is létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-118">You can create bar codes manually or automatically.</span></span> <span data-ttu-id="cdfe9-119">A vonalkódok létrehozásához kövesse az alábbi feladatokat a megadott sorrendben.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-119">To create bar codes, complete the following tasks in the order in which they are listed.</span></span>

1.  <span data-ttu-id="cdfe9-120">[Vonalkódmaszk-karakterek beállítása](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="cdfe9-120">[Set up bar code mask characters](set-up-bar-code-masks.md).</span></span>
2.  <span data-ttu-id="cdfe9-121">[Vonalkódmaszkok beállítása](set-up-bar-code-masks.md).</span><span class="sxs-lookup"><span data-stu-id="cdfe9-121">[Set up bar code masks](set-up-bar-code-masks.md).</span></span>
3.  <span data-ttu-id="cdfe9-122">Vonalkód-beállítások konfigurálása.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-122">Configure bar code setups.</span></span>
4.  <span data-ttu-id="cdfe9-123">Termékek vonalkódjainak létrehozása.</span><span class="sxs-lookup"><span data-stu-id="cdfe9-123">Create bar codes for products.</span></span>


<a name="see-also"></a><span data-ttu-id="cdfe9-124">Lásd még</span><span class="sxs-lookup"><span data-stu-id="cdfe9-124">See also</span></span>
--------

[<span data-ttu-id="cdfe9-125">Vonalkódmaszkok beállítása</span><span class="sxs-lookup"><span data-stu-id="cdfe9-125">Set up bar code masks</span></span>](set-up-bar-code-masks.md)




