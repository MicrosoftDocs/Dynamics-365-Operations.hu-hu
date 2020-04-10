---
title: Tárgyi eszközök átsorolása
description: A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cdcb9c337440b8fa9de2bdeb78d3b2d118e91ca
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138277"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="93b01-103">Tárgyi eszközök átsorolása</span><span class="sxs-lookup"><span data-stu-id="93b01-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="93b01-104">A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="93b01-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="93b01-105">Ha egy tárgyi eszközt átsorolnak:</span><span class="sxs-lookup"><span data-stu-id="93b01-105">When a fixed asset is reclassified:</span></span>

* <span data-ttu-id="93b01-106">A létező tárgyi eszköz valamennyi könyve létrejön az új tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="93b01-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="93b01-107">Az eredeti tárgyi eszköznél beállított valamennyi adat az új tárgyi eszköz adataként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="93b01-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="93b01-108">Az eredeti tárgyi eszköz könyveinek állapota Lezárt lesz.</span><span class="sxs-lookup"><span data-stu-id="93b01-108">The status of the books for the original fixed asset is Closed.</span></span> 

* <span data-ttu-id="93b01-109">Az új tárgyi eszköz könyvénél az átsorolás dátuma fog szerepelni a **Beszerzési dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="93b01-109">The new books of the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="93b01-110">Az **Értékcsökkenés** futtatásának dátuma mezőben szereplő dátum az eredeti eszközadatokból lesz átmásolva.</span><span class="sxs-lookup"><span data-stu-id="93b01-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="93b01-111">Ha már elkezdődött az értékcsökkenés, akkor az **Utolsó értékcsökkenés futtatásának** dátuma mezőben az átsorolás dátuma jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="93b01-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

* <span data-ttu-id="93b01-112">Az eredeti tárgyi eszköz tárgyieszköz-tranzakciói törlődnek, és ismét létrejönnek az új tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="93b01-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

<span data-ttu-id="93b01-113">A tárgyi eszköz átsorolásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="93b01-113">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="93b01-114">Ugorjon a **Tárgyi eszközök > Időszakos feladatok > Újbóli osztályozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="93b01-114">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="93b01-115">A **Tárgyieszköz-csoport** mezőben válassza ki az újraosztályozandó csoport.</span><span class="sxs-lookup"><span data-stu-id="93b01-115">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="93b01-116">A **Tárgyi eszköz száma** mezőben válassza ki a tárgyi eszközt az újraosztályozáshoz.</span><span class="sxs-lookup"><span data-stu-id="93b01-116">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="93b01-117">Az **Új tárgyieszköz-csoport** mezőjében válassza ki a csoportot, amelybe át szeretné vinni a tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="93b01-117">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="93b01-118">Ha az új tárgyieszköz-csoport hozzá van csatolva egy specifikus számsorozathoz, az **Új tárgyieszköz-szám** mező frissítése az új tárgyieszköz-csoport számsorozatából származó számmal történik.</span><span class="sxs-lookup"><span data-stu-id="93b01-118">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="93b01-119">Ellenkező esetben az **Új tárgyieszköz-szám** mező frissítése azzal a számmal történik, amelyik a **Tárgyi eszköz paraméterei** oldalon beállított számsorozatból származik.</span><span class="sxs-lookup"><span data-stu-id="93b01-119">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="93b01-120">Ha a **Tárgyi eszköz paraméterei** oldalon nincs beállítva számsorozat, írjon be egy számot az **Új tárgyieszköz-szám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="93b01-120">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="93b01-121">Adjon meg egy dátumot az **Átsorolás dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="93b01-121">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="93b01-122">A **Bizonylatsorozat** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="93b01-122">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="93b01-123">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="93b01-123">Click **OK**.</span></span>
