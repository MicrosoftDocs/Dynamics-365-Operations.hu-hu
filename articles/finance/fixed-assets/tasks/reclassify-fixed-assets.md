---
title: Tárgyi eszközök átsorolása
description: A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fbfb754459fad1f3b1509f4f9c65c20e0385b013
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944712"
---
# <a name="reclassify-fixed-assets"></a><span data-ttu-id="f16e4-103">Tárgyi eszközök átsorolása</span><span class="sxs-lookup"><span data-stu-id="f16e4-103">Reclassify fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f16e4-104">A tárgyi eszközök átsorolása előtt át kell vinni az eszközöket egy új tárgyieszköz-csoportba, vagy ugyanazon a csoporton belül új tárgyieszközszámot kell társítani a tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="f16e4-104">To reclassify a fixed asset, you must transfer it to a new fixed asset group or assign a new fixed asset number to it in the same group.</span></span> 

<span data-ttu-id="f16e4-105">Ha egy tárgyi eszközt átsorolnak:</span><span class="sxs-lookup"><span data-stu-id="f16e4-105">When a fixed asset is reclassified:</span></span>

- <span data-ttu-id="f16e4-106">A létező tárgyi eszköz valamennyi könyve létrejön az új tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="f16e4-106">All books for the existing fixed asset are created for the new fixed asset.</span></span> <span data-ttu-id="f16e4-107">Az eredeti tárgyi eszköznél beállított valamennyi adat az új tárgyi eszköz adataként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="f16e4-107">Any information that was set up for the original fixed asset is copied to the new fixed asset.</span></span> <span data-ttu-id="f16e4-108">Az eredeti tárgyi eszköz könyveinek állapota Lezárt lesz.</span><span class="sxs-lookup"><span data-stu-id="f16e4-108">The status of the books for the original fixed asset is Closed.</span></span> 

- <span data-ttu-id="f16e4-109">Az új tárgyi eszköz könyvénél az átsorolás dátuma fog szerepelni a **Beszerzési dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f16e4-109">The new books for the new fixed asset contain the date of the reclassification in the **Acquisition date** field.</span></span> <span data-ttu-id="f16e4-110">Az **Értékcsökkenés** futtatásának dátuma mezőben szereplő dátum az eredeti eszközadatokból lesz átmásolva.</span><span class="sxs-lookup"><span data-stu-id="f16e4-110">The date in the **Depreciation run date** field is copied from the original asset information.</span></span> <span data-ttu-id="f16e4-111">Ha már elkezdődött az értékcsökkenés, akkor az **Utolsó értékcsökkenés futtatásának** dátuma mezőben az átsorolás dátuma jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="f16e4-111">If the depreciation has already started, the **Date when depreciation was last run** field displays the date of the reclassification.</span></span> 

- <span data-ttu-id="f16e4-112">Az eredeti tárgyi eszköz tárgyieszköz-tranzakciói törlődnek, és ismét létrejönnek az új tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="f16e4-112">The existing fixed asset transactions for the original fixed asset are canceled and regenerated for the new fixed asset.</span></span>

- <span data-ttu-id="f16e4-113">Ha egy átsorolási tranzakcióval rendelkező eszközt átsorolnak akkor a rendszer egy üzenetet jelenít meg a **Műveletközpontban**, amely azt jelzi, hogy az átsorolási folyamat során nem fejeződött be az átviteli tranzakció.</span><span class="sxs-lookup"><span data-stu-id="f16e4-113">When an asset that has a transfer transaction has been reclassified, the system will display a message in the **Action center** to indicate that a transfer transaction wasn't completed during the reclassification process.</span></span> <span data-ttu-id="f16e4-114">Ahhoz, hogy a meglévő átsorolási tranzakciókat a megfelelő pénzügyi dimenziókba át lehessen helyezni végre kell hajtani egy átátviteli tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="f16e4-114">It's necessary to complete a transfer transaction to move the existing reclassification transactions to the appropriate financial dimensions.</span></span> 

   <span data-ttu-id="f16e4-115">Az átsorolási folyamat során a rendszer a következő műveleteket futtatja az eszközegyenleg átsorolásához az eredeti eszközről az új eszközre.</span><span class="sxs-lookup"><span data-stu-id="f16e4-115">During the reclassification process, the system runs the following actions to reclassify the asset balance from the original asset to the new asset.</span></span> 
   
   - <span data-ttu-id="f16e4-116">Az átsorolási folyamat az eredeti tárgyieszköz-könyv adatait az új tárgyieszköz-könyvbe másolja.</span><span class="sxs-lookup"><span data-stu-id="f16e4-116">The reclassification process copies the data from the original fixed asset book to the new fixed asset book.</span></span>

   - <span data-ttu-id="f16e4-117">Az átsorolási tranzakció az eredeti feladott beszerzés adatait használja fel, és tartalmazza a beszerzési tranzakcióban szereplő pénzügyi dimenzióadatokat.</span><span class="sxs-lookup"><span data-stu-id="f16e4-117">The reclassification transaction uses information from the original posted acquisition that includes financial dimension information that is included in the acquisition transaction.</span></span>  
   
   - <span data-ttu-id="f16e4-118">Ugyanakkor az átsorolási folyamat sztornírozza az eredeti eszközbeszerzési és eszközátadási tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="f16e4-118">At the same time, the reclassification process reverses the original asset acquisition and asset transfer transaction.</span></span> 

<span data-ttu-id="f16e4-119">Az alábbi ábra és eljárás az átsorolási folyamatra mutat be egy példát.</span><span class="sxs-lookup"><span data-stu-id="f16e4-119">The following diagram and procedure provide an example of the reclassification process.</span></span> 

<span data-ttu-id="f16e4-120">[![Az átsorolási folyamatot megjelenítő diagram](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span><span class="sxs-lookup"><span data-stu-id="f16e4-120">[![Diagram showing the reclassicification process](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)</span></span>

<span data-ttu-id="f16e4-121">A tárgyi eszköz átsorolásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="f16e4-121">Follow these steps to reclassify a fixed asset:</span></span>

1. <span data-ttu-id="f16e4-122">Ugorjon a **Tárgyi eszközök > Időszakos feladatok > Újbóli osztályozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="f16e4-122">Go to **Fixed assets > Periodic tasks > Reclassification.**</span></span>
2. <span data-ttu-id="f16e4-123">A **Tárgyieszköz-csoport** mezőben válassza ki az újraosztályozandó csoport.</span><span class="sxs-lookup"><span data-stu-id="f16e4-123">In the **Fixed asset group** field, select the group to reclassify.</span></span>
3. <span data-ttu-id="f16e4-124">A **Tárgyi eszköz száma** mezőben válassza ki a tárgyi eszközt az újraosztályozáshoz.</span><span class="sxs-lookup"><span data-stu-id="f16e4-124">In the **Fixed asset number** field, select the fixed asset to reclassify.</span></span>
4. <span data-ttu-id="f16e4-125">Az **Új tárgyieszköz-csoport** mezőjében válassza ki a csoportot, amelybe át szeretné vinni a tárgyi eszközt.</span><span class="sxs-lookup"><span data-stu-id="f16e4-125">In the **New fixed asset group** field, select a group to transfer the fixed asset to.</span></span>
    * <span data-ttu-id="f16e4-126">Ha az új tárgyieszköz-csoport hozzá van csatolva egy specifikus számsorozathoz, az **Új tárgyieszköz-szám** mező frissítése az új tárgyieszköz-csoport számsorozatából származó számmal történik.</span><span class="sxs-lookup"><span data-stu-id="f16e4-126">If the new fixed asset group is attached to a number sequence, the **New fixed asset number** field is updated with the number from the new fixed asset group number sequence.</span></span> <span data-ttu-id="f16e4-127">Ellenkező esetben az **Új tárgyieszköz-szám** mező frissítése azzal a számmal történik, amelyik a **Tárgyi eszköz paraméterei** oldalon beállított számsorozatból származik.</span><span class="sxs-lookup"><span data-stu-id="f16e4-127">Otherwise, the **New fixed asset number** field is updated with the number from the number sequence that is set up on the **Fixed asset parameters** page.</span></span> <span data-ttu-id="f16e4-128">Ha a **Tárgyi eszköz paraméterei** oldalon nincs beállítva számsorozat, írjon be egy számot az **Új tárgyieszköz-szám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f16e4-128">If a number sequence is not set up on the **Fixed asset parameters** page, enter a number in the **New fixed asset number** field.</span></span>  
5. <span data-ttu-id="f16e4-129">Adjon meg egy dátumot az **Átsorolás dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f16e4-129">In the **Reclassification date** field, enter a date.</span></span>
6. <span data-ttu-id="f16e4-130">A **Bizonylatsorozat** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f16e4-130">In the **Voucher series** field, enter or select a value.</span></span>
7. <span data-ttu-id="f16e4-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f16e4-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
