--- 
title: "Tárgyi eszközök átsorolása"
description: "A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cafd499e849570cae7b7f58bf2d487a7ac0093e6
ms.openlocfilehash: 6bce294329c7ec6dc436c3d3baf6597e0283c9bd
ms.contentlocale: hu-hu
ms.lasthandoff: 10/30/2017

---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="893f1-103">Tárgyi eszközök átsorolása</span><span class="sxs-lookup"><span data-stu-id="893f1-103">Reclassify fixed assets</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="893f1-104">A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="893f1-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="893f1-105">Ha egy tárgyi eszközt átsorolnak:</span><span class="sxs-lookup"><span data-stu-id="893f1-105">When a fixed asset is reclassified:</span></span>

<span data-ttu-id="893f1-106">• A létező tárgyi eszköz valamennyi értékmodellje létrejön az új tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="893f1-106">• All value models for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="893f1-107">Az eredeti tárgyi eszköznél beállított valamennyi adat az új tárgyi eszköz adataként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="893f1-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="893f1-108">Az eredeti tárgyi eszköz értékmodelljeinek állapota Lezárt lesz.</span><span class="sxs-lookup"><span data-stu-id="893f1-108">The status of the value models for the original fixed asset is Closed.</span></span> 

<span data-ttu-id="893f1-109">• Az új tárgyi eszköz értékmodelljeinél az átsorolás dátuma fog szerepelni a Beszerzési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="893f1-109">• The new value models of the new fixed asset contain the date of the reclassification in the Acquisition date field.</span></span> <span data-ttu-id="893f1-110">Az Értékcsökkenés futtatásának dátuma mezőben szereplő dátum az eredeti eszközadatokból lesz átmásolva.</span><span class="sxs-lookup"><span data-stu-id="893f1-110">The date in the Depreciation run date field is copied from the original asset information.</span></span> <span data-ttu-id="893f1-111">Ha már elkezdődött az értékcsökkenés, akkor az Utolsó értékcsökkenés futtatásának dátuma mezőben az átsorolás dátuma jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="893f1-111">If the depreciation has already started, the Date when depreciation was last run field displays the date of the reclassification.</span></span> 

<span data-ttu-id="893f1-112">• Az eredeti tárgyi eszköz tárgyieszköz-tranzakciói törlődnek, és ismét létrejönnek az új tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="893f1-112">• The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

1. <span data-ttu-id="893f1-113">Ugorjon a Tárgyi eszközök > Időszakos feladatok > Újbóli osztályozás elemre.</span><span class="sxs-lookup"><span data-stu-id="893f1-113">Go to Fixed assets > Periodic tasks > Reclassification.</span></span>
2. <span data-ttu-id="893f1-114">A Tárgyieszköz-csoport mezőben válassza ki az újraosztályozandó csoport.</span><span class="sxs-lookup"><span data-stu-id="893f1-114">In the Fixed asset group field, select the group to reclassify.</span></span>
3. <span data-ttu-id="893f1-115">A Tárgyi eszköz száma mezőben válassza ki a tárgyi eszközt az újraosztályozáshoz.</span><span class="sxs-lookup"><span data-stu-id="893f1-115">In the Fixed asset number field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="893f1-116">Az Új tárgyieszköz-csoport mezőjében válassza ki a csoportot, amelybe át szeretné vinni a tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="893f1-116">In the New fixed asset group field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="893f1-117">Ha az új tárgyieszköz-csoport hozzá van csatolva egy specifikus számsorozathoz, az Új tárgyieszköz-szám mező frissítése az új tárgyieszköz-csoport számsorozatából származó számmal történik.</span><span class="sxs-lookup"><span data-stu-id="893f1-117">If the new fixed asset group is attached to a number sequence, the New fixed asset number field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="893f1-118">Ellenkező esetben az Új tárgyieszköz-szám mező frissítése azzal a számmal történik, amelyik a Tárgyi eszköz paraméterei oldalon beállított számsorozatból származik.</span><span class="sxs-lookup"><span data-stu-id="893f1-118">Otherwise, the New fixed asset number field is updated with the number from the number sequence that is set up in the Fixed asset parameters page.</span></span> <span data-ttu-id="893f1-119">Ha a Tárgyi eszköz paraméterei oldalon nincs beállítva számsorozat, írjon be egy számot az Új tárgyieszköz-szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="893f1-119">If a number sequence is not set up in the Fixed asset parameters page, enter a number in the New fixed asset number field.</span></span>  
5. <span data-ttu-id="893f1-120">Adjon meg egy dátumot az Átsorolás dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="893f1-120">In the Reclassification date field, enter a date.</span></span>
6. <span data-ttu-id="893f1-121">A Bizonylatsorozat mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="893f1-121">In the Voucher series field, enter or select a value.</span></span>
7. <span data-ttu-id="893f1-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="893f1-122">Click OK.</span></span>


