---
title: Kanbanszabály létrehozása minimális készletesemény használatával
description: Ez az eljárás az olyan beállításokra irányul, amelyek a minimális készletesemény segítségével történő kanbanszabály létrehozásához szükségesek, annak érdekében, hogy az adott termékek mindig elérhetőek legyenek az adott helyeken.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 297ee73daf10dffd027dadec11725ae6f0408d4c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255157"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a><span data-ttu-id="66de2-103">Kanbanszabály létrehozása minimális készletesemény használatával</span><span class="sxs-lookup"><span data-stu-id="66de2-103">Create a kanban rule using a minimum stock event</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="66de2-104">Ez az eljárás az olyan beállításokra irányul, amelyek a minimális készletesemény segítségével történő kanbanszabály létrehozásához szükségesek, annak érdekében, hogy az adott termékek mindig elérhetőek legyenek az adott helyeken.</span><span class="sxs-lookup"><span data-stu-id="66de2-104">This procedure focuses on the setup needed to create a kanban rule using a minimum stock event to ensure that a specific product is always available at a specific location.</span></span> <span data-ttu-id="66de2-105">A kanbanszabály az anyagok a helyre történő átvitelének lebonyolítására szolgál, ha a készletszint 200 darab alá csökken.</span><span class="sxs-lookup"><span data-stu-id="66de2-105">A kanban rule is created to transfer material to the location when the inventory level drops below 200 pieces.</span></span> <span data-ttu-id="66de2-106">Az igényjelző esemény feldolgozásának futtatása során jönnek létre a szükséges kanbanok.</span><span class="sxs-lookup"><span data-stu-id="66de2-106">By running the Pegging event processing, the needed kanbans are created.</span></span> <span data-ttu-id="66de2-107">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="66de2-107">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="66de2-108">Ez a feladat a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mivel ők készítik elő az új vagy módosított termékek termelését a lean környezetben.</span><span class="sxs-lookup"><span data-stu-id="66de2-108">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="66de2-109">Új kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="66de2-109">Create a new kanban rule</span></span>
1. <span data-ttu-id="66de2-110">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="66de2-110">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="66de2-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="66de2-111">Click New.</span></span>
3. <span data-ttu-id="66de2-112">A Típus mezőben válassza ki a „Terhelések” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66de2-112">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="66de2-113">Ez a típus az átviteli kanbanok létrehozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="66de2-113">This type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="66de2-114">A Feltöltési stratégia mezőben válassza az „Esemény” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66de2-114">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="66de2-115">Az Esemény stratégia az eseményen alapuló átvitel kanbanok létrehozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="66de2-115">The Event strategy is used to create the transfer kanbans based on an event.</span></span> <span data-ttu-id="66de2-116">A rendszer később fogja aktiválni az átvitel kanbanokat a készletfeltöltés segítségével az eljárás során.</span><span class="sxs-lookup"><span data-stu-id="66de2-116">Later in the procedure, you will trigger transfer kanbans by using stock replenishment.</span></span>  
5. <span data-ttu-id="66de2-117">Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="66de2-117">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="66de2-118">Adja meg vagy válassza ki a ReplenishSpeakerComponents lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66de2-118">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="66de2-119">Ez az átmozgatási tevékenység érkeztetési (kimenő) raktárral és 12-es hellyel rendelkezik, ami azt jelenti, hogy az anyagokat a 12-es raktárba, a 12-es helyre helyezik át.</span><span class="sxs-lookup"><span data-stu-id="66de2-119">This transfer activity has receipt (output) warehouse and location 12, which means that materials will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="66de2-120">A Részletek szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="66de2-120">Expand the Details section.</span></span>
7. <span data-ttu-id="66de2-121">A Termék mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="66de2-121">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="66de2-122">Válassza az M0007 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66de2-122">Select M0007.</span></span>  
8. <span data-ttu-id="66de2-123">Bontsa ki a Események szakaszt.</span><span class="sxs-lookup"><span data-stu-id="66de2-123">Expand the Events section.</span></span>
9. <span data-ttu-id="66de2-124">Válassza ki a „Köteg” lehetőséget a Készletfeltöltési esemény mezőben.</span><span class="sxs-lookup"><span data-stu-id="66de2-124">In the Stock replenishment event field, select 'Batch'.</span></span>
    * <span data-ttu-id="66de2-125">Kanbanokat hoz létre a kapcsolódó helyen az anyagi szükségletek kielégítésére az Igényjelző esemény feldolgozása során.</span><span class="sxs-lookup"><span data-stu-id="66de2-125">This creates kanbans to fulfill material needs at the related location during Pegging event processing.</span></span>  

## <a name="set-the-minimum-quantity-for-the-item"></a><span data-ttu-id="66de2-126">Állítsa be a minimális mennyiséget a cikkhez</span><span class="sxs-lookup"><span data-stu-id="66de2-126">Set the minimum quantity for the item</span></span>
1. <span data-ttu-id="66de2-127">Kattintson a Termék mezőben található hivatkozás követésére.</span><span class="sxs-lookup"><span data-stu-id="66de2-127">Click to follow the link in the Product field.</span></span>
2. <span data-ttu-id="66de2-128">Kattintson a Cikkszám mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="66de2-128">Click to follow the link in the Item number field.</span></span>
3. <span data-ttu-id="66de2-129">Bontsa ki a Termék kép Adatterület lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66de2-129">Expand the Product image FactBox.</span></span>
4. <span data-ttu-id="66de2-130">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="66de2-130">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="66de2-131">Kattintson a cikkfedezet elemre.</span><span class="sxs-lookup"><span data-stu-id="66de2-131">Click Item coverage.</span></span>
6. <span data-ttu-id="66de2-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="66de2-132">Click New.</span></span>
7. <span data-ttu-id="66de2-133">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="66de2-133">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="66de2-134">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="66de2-134">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="66de2-135">Állítsa be a 12-as raktárat.</span><span class="sxs-lookup"><span data-stu-id="66de2-135">Set Warehouse to 12.</span></span>  
9. <span data-ttu-id="66de2-136">Állítsa át a minimális értéket „200” értékre.</span><span class="sxs-lookup"><span data-stu-id="66de2-136">Set Minimum to '200'.</span></span>

## <a name="run-the-batch-event-creation-job"></a><span data-ttu-id="66de2-137">A kötegelt esemény létrehozási feladat futtatása</span><span class="sxs-lookup"><span data-stu-id="66de2-137">Run the batch event creation job</span></span>
1. <span data-ttu-id="66de2-138">Ugorjon a Gyártásvezérlés > Időszakos feladatok > Kanban feladat kötegelt feldolgozása > Igényjelző esemény feldolgozása pontra.</span><span class="sxs-lookup"><span data-stu-id="66de2-138">Go to Production control > Periodic tasks > Kanban job batch processing > Pegging event processing.</span></span>
2. <span data-ttu-id="66de2-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="66de2-139">Click OK.</span></span>
3. <span data-ttu-id="66de2-140">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="66de2-140">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
4. <span data-ttu-id="66de2-141">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="66de2-141">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="66de2-142">Válassza ki a korábban létrehozott kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="66de2-142">Select the kanban rule that you created earlier.</span></span>  
5. <span data-ttu-id="66de2-143">Bontsa ki a Kanbanok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="66de2-143">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="66de2-144">Jegyezze meg, hogy a rendszer a kanbant a szükséges anyagok 12-es raktárba történő átvitel lebonyolítására hozta létre.</span><span class="sxs-lookup"><span data-stu-id="66de2-144">Notice that a kanban was created to transfer the needed material to warehouse 12.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]