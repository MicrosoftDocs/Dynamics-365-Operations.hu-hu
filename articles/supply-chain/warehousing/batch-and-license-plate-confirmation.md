---
title: "Köteg és azonosítótábla megerősítése"
description: "Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6454335989fe03a7332b6fb956667850896ffaf4
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="2f880-103">Köteg és azonosítótábla megerősítése</span><span class="sxs-lookup"><span data-stu-id="2f880-103">Batch and license plate confirmation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2f880-104">A kötegelés megerősítésével meggyőződhet arról, hogy a helyes tételt tárolta ki a mobileszközről.</span><span class="sxs-lookup"><span data-stu-id="2f880-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="2f880-105">A csak a fenti tételek kitárolásánál, amennyiben a fentiek kötegelése azt jelzi, hogy a köteg tartománya magasabb, mint a hely a keresési hierarchiában, így ellenőriznie kell, hogy a kitárolt köteg egyezik a munkasoron lévő köteggel.</span><span class="sxs-lookup"><span data-stu-id="2f880-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span> 

<span data-ttu-id="2f880-106">Az azonosítótábla megerősítésével meggyőződhet arról, hogy a helyes azonosítótáblát tárolta ki a mobileszközről.</span><span class="sxs-lookup"><span data-stu-id="2f880-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="2f880-107">Amikor egy betervezett helyről tárol ki munkát, ellenőriznie kell, hogy a kitárolni kívánt azonosítótábla egyezik-e a munkához kapcsolódó azonosítótáblával.</span><span class="sxs-lookup"><span data-stu-id="2f880-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="2f880-108">Ha a munka azonosítótábla leolvasásával kezdődik, akkor ezt a megerősítő lépést átugorja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="2f880-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="2f880-109">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="2f880-109">Where it applies</span></span>
<span data-ttu-id="2f880-110">A visszaigazolás az alábbi esetekben alkalmazandó:</span><span class="sxs-lookup"><span data-stu-id="2f880-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="2f880-111">A kötegelés megerősítése a fenti cikkek munkáinak kezdeti kitárolására vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2f880-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="2f880-112">Az azonosítótábla megerősítése az előkészítési helyeknél lévő kitárolásokra érvényes.</span><span class="sxs-lookup"><span data-stu-id="2f880-112">License plate confirmation applies to picks from stage locations.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="2f880-113">Köteg és azonosítótábla beállításának megerősítése</span><span class="sxs-lookup"><span data-stu-id="2f880-113">Set up batch and license plate confirmation</span></span>
<span data-ttu-id="2f880-114">Ez a témakör a kötegalkalmazás és az azonosítótábla-megerősítés mobileszközről való beállítását és alkalmazását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="2f880-114">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>  
1.  <span data-ttu-id="2f880-115">Lépjen be a munka-visszaigazolás beállításához a mobileszköz menüelemeitől.</span><span class="sxs-lookup"><span data-stu-id="2f880-115">From the mobile device menu items, enter the work confirmation setup.</span></span>  
2.  <span data-ttu-id="2f880-116">Válassza ki, hogy kötegelést vagy azonosítótábla-megerősítést szeretne végezni.</span><span class="sxs-lookup"><span data-stu-id="2f880-116">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="2f880-117">Mindkét lehetőség rendelkezésre áll azoknál a munkatípus-kitárolásoknál, amelyeknél nincs engedélyezve az automatikus visszaigazolás.</span><span class="sxs-lookup"><span data-stu-id="2f880-117">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  
