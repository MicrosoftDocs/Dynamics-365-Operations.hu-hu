---
title: Kanbanszabály létrehozása kanbansoresemény használatával
description: Ez az eljárás kanbanszabályt hoz létre a kanban soresemény beállítás segítségével a folyamattevékenységből történő lekérés aktiválásához.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe2fa817229af541baa61406487bd60b20ddc8b7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838679"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a><span data-ttu-id="8fa7e-103">Kanbanszabály létrehozása kanbansoresemény használatával</span><span class="sxs-lookup"><span data-stu-id="8fa7e-103">Create a kanban rule using a kanban line event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8fa7e-104">Ez az eljárás kanbanszabályt hoz létre a kanban soresemény beállítás segítségével a folyamattevékenységből történő lekérés aktiválásához.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-104">This procedure creates a kanban rule by using the kanban line event setting to trigger pull from a process activity.</span></span> <span data-ttu-id="8fa7e-105">A kanban folyamattevékenység által elindított kanbanszabály, amely mennyisége egyenként egyenlő vagy nagyobb mint 25.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-105">The kanban rule is triggered by a kanban process activity, with a quantity equal to or greater than 25 each.</span></span> <span data-ttu-id="8fa7e-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="8fa7e-107">Ez a feladat a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mivel ők készítik elő az új vagy módosított termékek termelését a lean környezetben.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-107">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-kanban-rule"></a><span data-ttu-id="8fa7e-108">Kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="8fa7e-108">Create a kanban rule</span></span>
1. <span data-ttu-id="8fa7e-109">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-109">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="8fa7e-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-110">Click New.</span></span>
3. <span data-ttu-id="8fa7e-111">A Feltöltési stratégia mezőben válassza az „Esemény” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="8fa7e-112">A rendszer kanbanokat hoz létre közvetlenül az igények alapján.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-112">This generates kanbans directly from demand.</span></span> <span data-ttu-id="8fa7e-113">Ez a rendelésre készített esetet meghatározó szabályok beállítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-113">It is used to set up rules that define a make-to-order scenario.</span></span>  
4. <span data-ttu-id="8fa7e-114">Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="8fa7e-115">Adja meg vagy válassza ki a SpeakerAssemblyAndPolish lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-115">Enter or select SpeakerAssemblyAndPolish.</span></span> <span data-ttu-id="8fa7e-116">A gyártási kanban szabály első tevékenysége a termelési folyamatban megjelenő folyamattevékenység.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-116">The first activity of a manufacturing kanban rule is a process activity in the production flow.</span></span> <span data-ttu-id="8fa7e-117">A tevékenység kiválasztásakor a rendszer a tevékenység érvényességi dátumát a kanbanszabály érvényességi dátumára másolja.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-117">When you select the activity, the validity dates of the activity are copied to the validity dates of the kanban rule.</span></span>  
5. <span data-ttu-id="8fa7e-118">A Részletek szakasz kibontása.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-118">Expand the Details section.</span></span>
6. <span data-ttu-id="8fa7e-119">Írja be a „L0001” szöveget a Termék mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-119">In the Product field, type 'L0001'.</span></span>
7. <span data-ttu-id="8fa7e-120">Bontsa ki a Események szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-120">Expand the Events section.</span></span>
8. <span data-ttu-id="8fa7e-121">Válassza ki az „Automatikus” lehetőséget a Kanbansoresemény mezőben.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-121">In the Kanban line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="8fa7e-122">Igény szerint eseménykanbanokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-122">This generates event kanbans on demand.</span></span>  <span data-ttu-id="8fa7e-123">Ez a mező szolgál azon kanbanszabályok konfigurálására, amelyek lefelé irányuló folyamattevékenységhez szükséges anyagokat töltenek fel.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-123">The field is used to configure kanban rules that replenish material that is required for a downstream process activity.</span></span> <span data-ttu-id="8fa7e-124">Az automatikus lehetőség kiválasztásakor az eseménykanbanokat igény szerint hozzák létre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-124">When you select Automatic, the event kanbans are created with the demand.</span></span> <span data-ttu-id="8fa7e-125">Ez a beállítás akkor ajánlott, ha ugyanazon a napon szeretné végrehajtani a gyártást.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-125">This setting is recommended if you expect to execute production on the same day.</span></span>  
9. <span data-ttu-id="8fa7e-126">A minimális eseménymennyiséget állítsa „25” értékre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-126">Set Minimum event quantity to '25'.</span></span>
    * <span data-ttu-id="8fa7e-127">A eseménykanbanok akkor jönnek létre, ha az igény mennyisége egyenlő vagy nagyobb, mint az ebben a mezőben található érték.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-127">Event kanbans are generated when the demand quantity is equal to or more than this field.</span></span> <span data-ttu-id="8fa7e-128">Ez akkor hasznos, ha kisebb rendelési mennyiséget szeretne előállítani, mint egy gépen található mezőben és nagyobb rendelési mennyiséget, mint egy másik gépen található mezőben.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-128">This is useful if you want to produce an order quantity less than this field on one machine and more than this field on another machine.</span></span>  
10. <span data-ttu-id="8fa7e-129">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-129">Click Save.</span></span>

## <a name="create-sales-order-and-trigger-kanban-chain"></a><span data-ttu-id="8fa7e-130">Értékesítési rendelés létrehozása és kanban lánc aktiválása</span><span class="sxs-lookup"><span data-stu-id="8fa7e-130">Create sales order and trigger kanban chain</span></span>
1. <span data-ttu-id="8fa7e-131">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="8fa7e-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-132">Click New.</span></span>
3. <span data-ttu-id="8fa7e-133">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-133">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="8fa7e-134">Válassza ki az US-003, Forest Wholesales Vevői számlát.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-134">Select Customer account US-003, Forest Wholesales.</span></span>  
4. <span data-ttu-id="8fa7e-135">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-135">Click OK.</span></span>
5. <span data-ttu-id="8fa7e-136">A Cikkszám mezőbe írja be az „L0001” értéket.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-136">In the Item number field, type 'L0001'.</span></span>
    * <span data-ttu-id="8fa7e-137">Az L0001 elem az a cikk, amelyhez létrehozta a kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-137">L0001 is the item for which you created the kanban rule.</span></span>  
6. <span data-ttu-id="8fa7e-138">Állítsa a mennyiséget 27 értékre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-138">Set Quantity to '27'.</span></span>
    * <span data-ttu-id="8fa7e-139">Mivel 27 nagyobb, mint 25, a kanbanszabályban található minimális mennyiség, így egy eseménykanbant indít el.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-139">Because 27 is higher than the minimum quantity of 25 on the kanban rule, this will trigger an event kanban.</span></span>  
7. <span data-ttu-id="8fa7e-140">A Hely mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-140">In the Site field, type '1'.</span></span>
8. <span data-ttu-id="8fa7e-141">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-141">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="8fa7e-142">Válasszak ki a 13. raktárt.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-142">Select warehouse 13.</span></span>  
9. <span data-ttu-id="8fa7e-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-143">Click Save.</span></span>

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a><span data-ttu-id="8fa7e-144">A kanbanszabály által létrehozott kanban megtekintése</span><span class="sxs-lookup"><span data-stu-id="8fa7e-144">View the kanban generated by the kanban rule</span></span>
1. <span data-ttu-id="8fa7e-145">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-145">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="8fa7e-146">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-146">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8fa7e-147">Bontsa ki a Kanbanok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-147">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="8fa7e-148">Jegyezze meg, hogy a rendszer a 27-es kanbant a létrehozott kanbanszabályon alapuló tevékenység feldolgozására hozta létre.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-148">Notice that a kanban for 27 was created to process the  activity based on the created kanban rule.</span></span>  
    * <span data-ttu-id="8fa7e-149">Ez az utolsó lépés.</span><span class="sxs-lookup"><span data-stu-id="8fa7e-149">This is the last step.</span></span>  

