---
title: Kanbanmennyiségi irányelv hozzáadása egy kanbanszabályhoz
description: Ez a folyamat egy kanbanmennyiség-számítási irányelv létrehozására irányul, valamint annak hozzáadásához egy kanbanszabályhoz, amivel optimalizálható a kanban mérete és a mennyisége.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19f563379a10bbe42681a5f61779fb9e72d1f60c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211008"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="3dab4-103">Kanbanmennyiségi irányelv hozzáadása egy kanbanszabályhoz</span><span class="sxs-lookup"><span data-stu-id="3dab4-103">Add a kanban quantity calculation policy to a kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3dab4-104">Ez a folyamat egy kanbanmennyiség-számítási irányelv létrehozására irányul, valamint annak hozzáadásához egy kanbanszabályhoz, amivel optimalizálható a kanban mérete és a mennyisége.</span><span class="sxs-lookup"><span data-stu-id="3dab4-104">This procedure focuses on creating a kanban quantity calculation policy and adding it to a kanban rule to optimize the kanban size and quantities.</span></span> <span data-ttu-id="3dab4-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="3dab4-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3dab4-106">Ez az eljárás az érték-előállítási folyamat vezetője számára készült.</span><span class="sxs-lookup"><span data-stu-id="3dab4-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="3dab4-107">Ez az eljárás a Kanbanmennyiség-javaslatok kiszámítása eljárás létrehozásának előfeltétele.</span><span class="sxs-lookup"><span data-stu-id="3dab4-107">This procedure is a prerequisite for creating the procedure Calculate kanban quantity suggestions.</span></span> 


## <a name="create-a-kanban-quantity-calculation-policy"></a><span data-ttu-id="3dab4-108">Kanbanmennyiség-számítási irányelv létrehozása</span><span class="sxs-lookup"><span data-stu-id="3dab4-108">Create a kanban quantity calculation policy</span></span>
1. <span data-ttu-id="3dab4-109">Ugorjon a Gyártásvezérlés > Időszakos feladatok > Kanbanmennyiség-számítás > Kanbanmennyiség-számítási irányelvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3dab4-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban quantity calculation policies.</span></span>
2. <span data-ttu-id="3dab4-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3dab4-110">Click New.</span></span>
3. <span data-ttu-id="3dab4-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3dab4-111">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3dab4-112">Például, írja be a Speaker2016 szöveget.</span><span class="sxs-lookup"><span data-stu-id="3dab4-112">For example, type Speaker2016.</span></span>  
4. <span data-ttu-id="3dab4-113">Az Alapterv mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3dab4-113">In the Master plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="3dab4-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3dab4-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3dab4-115">Válassza ki a StaticPlan lehetőséget a kereslet kiszámolására.</span><span class="sxs-lookup"><span data-stu-id="3dab4-115">Select StaticPlan to calculate demand.</span></span>  
6. <span data-ttu-id="3dab4-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3dab4-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="3dab4-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3dab4-117">Click Save.</span></span>
8. <span data-ttu-id="3dab4-118">A Minimális kanbanmennyiség mezőben adja meg az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="3dab4-118">In the Minimum kanban quantity field, enter '1'.</span></span>
    * <span data-ttu-id="3dab4-119">Ez a kanbanmennyiség-számításban szerepeltetett további kanbanok száma.</span><span class="sxs-lookup"><span data-stu-id="3dab4-119">This is the additional number of kanbans that is included in the kanban quantity calculation.</span></span>  
9. <span data-ttu-id="3dab4-120">Állítsa a biztonsági tényezőt „1” értékre.</span><span class="sxs-lookup"><span data-stu-id="3dab4-120">Set Safety factor to '1'.</span></span>
    * <span data-ttu-id="3dab4-121">Ez a további biztonsági készletmennyiség kiszámításához használt tényező.</span><span class="sxs-lookup"><span data-stu-id="3dab4-121">This is the factor that is used to calculate additional quantity of safety stock.</span></span>  
10. <span data-ttu-id="3dab4-122">Az Elkövetkező napok száma mezőbe írja be a „30” értéket.</span><span class="sxs-lookup"><span data-stu-id="3dab4-122">In the Days ahead field, enter '30'.</span></span>
    * <span data-ttu-id="3dab4-123">Ez a kanbanmennyiség kiszámítási dátumát megelőző napok száma, amelyek az igényszámítás részét képezik.</span><span class="sxs-lookup"><span data-stu-id="3dab4-123">This is the number of days prior to the kanban quantity calculation date that is included in the demand calculation.</span></span>  
11. <span data-ttu-id="3dab4-124">Az Elmúlt napok száma mezőbe írja be a „30” értéket.</span><span class="sxs-lookup"><span data-stu-id="3dab4-124">In the Days behind field, enter '30'.</span></span>
    * <span data-ttu-id="3dab4-125">Ez a kanbanmennyiség kiszámítási dátumát követő napok száma, amelyek az igényszámítás részét képezik.</span><span class="sxs-lookup"><span data-stu-id="3dab4-125">This is the number of days forward from the kanban quantity calculation date that is included in the demand calculation.</span></span>  <span data-ttu-id="3dab4-126">A számításokhoz használt képletet valódi értékekkel mutatjuk be.</span><span class="sxs-lookup"><span data-stu-id="3dab4-126">The formula used for the calculation is shown with the actual values.</span></span> <span data-ttu-id="3dab4-127">Például, kanbanmennyiség = ((átlagos napi igény x átfutási idő x 2,00) / termékmennyiség anyagkezelési egységenként) + 1</span><span class="sxs-lookup"><span data-stu-id="3dab4-127">For example,  Kanban quantity = ((Average daily demand x lead time x 2.00) / Product quantity per handling unit) + 1</span></span>  
12. <span data-ttu-id="3dab4-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3dab4-128">Close the page.</span></span>

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="3dab4-129">Kanbanmennyiség-számítási irányelv hozzáadása a kanbanszabályhoz</span><span class="sxs-lookup"><span data-stu-id="3dab4-129">Add the kanban quantity calculation policy to a kanban rule</span></span>
1. <span data-ttu-id="3dab4-130">Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3dab4-130">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="3dab4-131">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3dab4-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3dab4-132">Válassza ki a 000020 kanbanszabályt ehhez az eljáráshoz.</span><span class="sxs-lookup"><span data-stu-id="3dab4-132">Select kanban rule 000020 for this procedure.</span></span>  
3. <span data-ttu-id="3dab4-133">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3dab4-133">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3dab4-134">Bontsa ki a Kanbanmennyiség-számítási irányelvek részt.</span><span class="sxs-lookup"><span data-stu-id="3dab4-134">Toggle the expansion of the Kanban quantity calculation policies section.</span></span>
5. <span data-ttu-id="3dab4-135">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="3dab4-135">Click Add.</span></span>
    * <span data-ttu-id="3dab4-136">Vegye fel a kanbanmennyiség előző alfeladatban létrehozott számítási irányelvét.</span><span class="sxs-lookup"><span data-stu-id="3dab4-136">Add the kanban quantity calculation policy that you have just created in the previous sub-task.</span></span>  
6. <span data-ttu-id="3dab4-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="3dab4-137">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="3dab4-138">A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3dab4-138">In the Name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="3dab4-139">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3dab4-139">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3dab4-140">Válassza ki a előző alfeladatban létrehozott Speaker2016 irányelvet.</span><span class="sxs-lookup"><span data-stu-id="3dab4-140">Select the policy Speaker2016 that you have just created in the previous sub-task.</span></span>  

