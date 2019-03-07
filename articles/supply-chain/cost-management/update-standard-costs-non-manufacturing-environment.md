---
title: Elszámoló árak frissítése nem-termelő jellegű környezetben
description: Ez a cikk az elszámoló-árak nem-gyártási környezetben történő frissítésének útmutatását tartalmazza.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4fa545aa6903bd6f789dda20ab5755ffe9a12b88
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "323019"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a><span data-ttu-id="12b22-103">Elszámoló árak frissítése nem-termelő jellegű környezetben</span><span class="sxs-lookup"><span data-stu-id="12b22-103">Update standard costs in a non-manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12b22-104">Ez a cikk az elszámoló-árak nem-gyártási környezetben történő frissítésének útmutatását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="12b22-104">This article provides guidance for updating standard costs in a non-manufacturing environment.</span></span>

<span data-ttu-id="12b22-105">Az alábbi irányelvek feltételezik, hogy a kétverziós megközelítés segítségével frissíti az elszámoló árat.</span><span class="sxs-lookup"><span data-stu-id="12b22-105">The following guidelines assume that you use a two-version approach to update standard cost.</span></span> <span data-ttu-id="12b22-106">Ebben a megközelítésben az egyik költségszámítási verzió az eredetileg a befagyasztott időszakra meghatározott elszámolási árakat tartalmazza, míg a másik költségszámítási verzió a járulékos frissítéseket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="12b22-106">In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates.</span></span> <span data-ttu-id="12b22-107">Minden módosítás a második költségverzióban rögzített költségrekordként kerül bevitelre, végül pedig engedélyezésre.</span><span class="sxs-lookup"><span data-stu-id="12b22-107">Each update is entered as a cost record that is enclosed in the second costing version, and eventually it's enabled.</span></span> <span data-ttu-id="12b22-108">Alternatív megoldás a kezdetben meghatározott elszámolási árakat használó egyverziós megközelítés alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="12b22-108">An alternative, one-version approach uses the set of standard costs that was originally defined.</span></span> <span data-ttu-id="12b22-109">A kétverziós megközelítés egy második költségszámítási verzió meghatározását igényli.</span><span class="sxs-lookup"><span data-stu-id="12b22-109">The two-version approach requires that you define a second costing version.</span></span> <span data-ttu-id="12b22-110">Az ennek a költségszámítási verziónak a meghatározására vonatkozó irányelvek a következők:</span><span class="sxs-lookup"><span data-stu-id="12b22-110">Here are the guidelines for defining this costing version:</span></span>

-   <span data-ttu-id="12b22-111">Rendeljen hozzá egy **Elszámoló árat** a költségszámítási típushoz.</span><span class="sxs-lookup"><span data-stu-id="12b22-111">Assign a costing type of **Standard costs**.</span></span>
-   <span data-ttu-id="12b22-112">Rendeljen hozzá egy egyértelmű azonosítót a költségverzióhoz, amely utal a költségverzió tartalmára. Például: **2016-FRISSÍTÉSEK**.</span><span class="sxs-lookup"><span data-stu-id="12b22-112">Assign a meaningful identifier that indicates the contents of the costing version, such as **2016-UPDATES**.</span></span>
-   <span data-ttu-id="12b22-113">Győződjön meg róla, hogy a tartalomban szerepelnek költségrekordok.</span><span class="sxs-lookup"><span data-stu-id="12b22-113">Make sure that the content includes cost records.</span></span>
-   <span data-ttu-id="12b22-114">Engedélyezze a költségrekordok bevitelét minden webhely esetében.</span><span class="sxs-lookup"><span data-stu-id="12b22-114">Allow cost records to be entered for all sites.</span></span> <span data-ttu-id="12b22-115">Ha megad egy webhelyet, akkor a költségrekordok csak arra a webhelyre rögzíthetők.</span><span class="sxs-lookup"><span data-stu-id="12b22-115">If you specify a site, cost records can be entered only for that site.</span></span>
-   <span data-ttu-id="12b22-116">Tartalékelvként adja meg a **Nincs** beállítást.</span><span class="sxs-lookup"><span data-stu-id="12b22-116">Indicate a fallback principle of **None**.</span></span> <span data-ttu-id="12b22-117">A tartalékelv csak a legyártott cikkek költségkalkulációira vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="12b22-117">The fallback principle applies only to cost calculations for manufactured items.</span></span>

<span data-ttu-id="12b22-118">Az új cikkekre vonatkozó elszámoló árak javításához, korrekciójához vagy frissítéséhez kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="12b22-118">To correct, adjust, or update standard costs for new items, follow these steps.</span></span>

1.  <span data-ttu-id="12b22-119">Használja a **Költségszámítási verzió** **beállítás** lapját a költségadatok második költségszámítási verziójába történő beírásának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="12b22-119">Use the **Costing version** **setup** page to enable cost data to be entered into the second costing version.</span></span> <span data-ttu-id="12b22-120">Lehetőség szerint, akadályozza meg a függő költségek aktiválását, hogy az aktiválás a függő költségek teljes körű és pontos meghatározása után történjen csak meg.</span><span class="sxs-lookup"><span data-stu-id="12b22-120">Optionally, prevent the activation of pending costs, so that activation will be allowed after pending costs have been completely and accurately defined.</span></span> <span data-ttu-id="12b22-121">Szintén igény szerint adhat meg dátumot a **Dátumtól** mezőben.</span><span class="sxs-lookup"><span data-stu-id="12b22-121">You can also optionally enter a date in the **From date** field.</span></span> <span data-ttu-id="12b22-122">Általánosan az az alapelv, hogy a járulékos frissítések tervezett aktiválási időpontjának dátumát kell megadni.</span><span class="sxs-lookup"><span data-stu-id="12b22-122">As a general guideline, use the date when you intend to enable the incremental updates.</span></span> <span data-ttu-id="12b22-123">Másik lehetőségként a költségszámítási verzió **Dátumtól** mezőjét üresen lehet hagyni és elég az egyes költségrekordok esetében kitölteni a **Dátumtól** mezőt.</span><span class="sxs-lookup"><span data-stu-id="12b22-123">Alternatively, leave the **From date** field blank for the costing version, and then enter a date in the **From date** field for each cost record.</span></span>
2.  <span data-ttu-id="12b22-124">Használja a **Cikkár** lapot a frissítések második költségszámítási verzióba foglalt cikk-költségrekordként történő beviteléhez.</span><span class="sxs-lookup"><span data-stu-id="12b22-124">Use the **Item price** page to enter updates as item cost records that are enclosed in the second costing version.</span></span>
3.  <span data-ttu-id="12b22-125">Használja a **Cikk árak** jelentést a második költségszámítási verzióba foglalt cikk-költségrekordok teljességének és pontosságának a megerősítéséhez.</span><span class="sxs-lookup"><span data-stu-id="12b22-125">Use the **Item prices** report to verify the completeness and accuracy of the item cost records that are enclosed in the second costing version.</span></span>
4.  <span data-ttu-id="12b22-126">Használja a **Költségszámítási verzió fenntartása** lapot, hogy módosítsa a zárolás jelzőt, ezzel lehetővé téve a második költségszámítási verzióba foglalt függőben lévő költségrekordok aktiválását.</span><span class="sxs-lookup"><span data-stu-id="12b22-126">Use the **Costing version maintenance** page to change the blocking flag to allow activation of the pending cost records that are enclosed in the second costing version.</span></span>
5.  <span data-ttu-id="12b22-127">Használja a **Költségszámítási verzió fenntartása** lapról megnyitható **Árak aktiválása** oldalt, hogy aktiválja az összes a második költségszámítási verzióba foglalt függőben lévő költségrekordot.</span><span class="sxs-lookup"><span data-stu-id="12b22-127">Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to activate all pending item cost records that are enclosed in the second costing version.</span></span> <span data-ttu-id="12b22-128">Az egyes cikkekhez tartozó függőköltség-rekordokat is aktiválhatja a **Cikk ár** oldalon szereplő **Függő-ár aktiválása** gombbal .</span><span class="sxs-lookup"><span data-stu-id="12b22-128">You can also activate the pending cost records for individual items by clicking the **Activate pending price** button on the **Item price** page.</span></span>
6.  <span data-ttu-id="12b22-129">A további adat-fenntartás megelőzése érdekében, használja a **Költségszámítási verzió beállítása** lapot, hogy módosítsa a második költségszámítási verzióba foglalt zárolás jelzőket.</span><span class="sxs-lookup"><span data-stu-id="12b22-129">To prevent additional data maintenance, use the **Costing version setup** page to change the blocking flags that are enclosed in the second costing version.</span></span> <span data-ttu-id="12b22-130">Az irányelvek zárolása megakadályozza az új függő költségek bevitelét és a függő költségek aktiválását.</span><span class="sxs-lookup"><span data-stu-id="12b22-130">The blocking policies will prevent the entry of new pending costs and the activation of pending costs.</span></span>




