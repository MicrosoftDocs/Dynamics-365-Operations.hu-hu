---
title: Visszavonási kanbanszabály létrehozása
description: Ez az eljárás bemutatja a visszavonási kanbanszabály létrehozásához szükséges beállítást az anyagok átvitelére vonatkozóan a lean környezetben.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1e1fc6dff80457cecdcd1659ffa42fd6c9c4447
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263994"
---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="a7474-103">Visszavonási kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7474-103">Create a withdrawal kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7474-104">Ez az eljárás bemutatja a visszavonási kanbanszabály létrehozásához szükséges beállítást az anyagok átvitelére vonatkozóan a lean környezetben.</span><span class="sxs-lookup"><span data-stu-id="a7474-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="a7474-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a7474-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a7474-106">Ez az eljárás a Folyamatmérnök vagy az Érték-előállítási vezető munkáját segíti, mivel előkészítik az új vagy a módosított anyagok feltöltését.</span><span class="sxs-lookup"><span data-stu-id="a7474-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="a7474-107">Új kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7474-107">Create new kanban rule</span></span>
1. <span data-ttu-id="a7474-108">Ugorjon a Kanbanszabályokhoz.</span><span class="sxs-lookup"><span data-stu-id="a7474-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="a7474-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7474-109">Click New.</span></span>
3. <span data-ttu-id="a7474-110">A Típus mezőben válassza ki a „Terhelések” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7474-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="a7474-111">A Levonás típusa az anyagok és áruk átvitelére szolgál a kanbanszabályokra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="a7474-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="a7474-112">Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a7474-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="a7474-113">Válassza ki a ReplenishSpeakerComponents lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7474-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="a7474-114">Ezt a tevékenységet az összetevők 11-es raktárból, 11-es helyről 12-es raktárba, 12 helyre történő áthelyezéséhez állították be.</span><span class="sxs-lookup"><span data-stu-id="a7474-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="a7474-115">A Termék mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a7474-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="a7474-116">Válassza az M0007 lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7474-116">Select M0007.</span></span>  
6. <span data-ttu-id="a7474-117">Adjon meg egy számot az Átfutási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7474-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="a7474-118">Például, 60 elem.</span><span class="sxs-lookup"><span data-stu-id="a7474-118">For example, 60.</span></span>  
7. <span data-ttu-id="a7474-119">A Mértékegység mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a7474-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="a7474-120">Páldául, Perc.</span><span class="sxs-lookup"><span data-stu-id="a7474-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="a7474-121">Állítsa be a mennyiséget a kanbanra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="a7474-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="a7474-122">Állítsa az Alapértelmezett mennyiséget a „5” értékre.</span><span class="sxs-lookup"><span data-stu-id="a7474-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="a7474-123">Ez a mennyiség átkerül az összes kanbanba.</span><span class="sxs-lookup"><span data-stu-id="a7474-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="a7474-124">A Fix kanbanmennyiség mezőben adja meg a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="a7474-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="a7474-125">Ez az aktív kanbanok mennyisége.</span><span class="sxs-lookup"><span data-stu-id="a7474-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="a7474-126">Ebben az esetben a 2 kanban egyenként 5-elemet visz át.</span><span class="sxs-lookup"><span data-stu-id="a7474-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="a7474-127">A Minimális figyelmeztetési határ mezőben adja meg a „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="a7474-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="a7474-128">Ennek segítségével nyomon követik azon teljes kanbanok minimum mennyiségét, amelyeknek a célhelyen kellene lenni.</span><span class="sxs-lookup"><span data-stu-id="a7474-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="a7474-129">Például ezt használják a kanbanmennyiség ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="a7474-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="a7474-130">A Maximális figyelmeztetési határ mezőben adja meg a „2” értéket.</span><span class="sxs-lookup"><span data-stu-id="a7474-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="a7474-131">Ennek segítségével nyomon követik azon teljes kanbanok maximum mennyiségét, amelyeknek a célhelyen kellene lenni.</span><span class="sxs-lookup"><span data-stu-id="a7474-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="a7474-132">Például ezt használják a kanbanmennyiség ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="a7474-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="a7474-133">Kanbanok létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7474-133">Create kanbans</span></span>
1. <span data-ttu-id="a7474-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7474-134">Click Save.</span></span>
    * <span data-ttu-id="a7474-135">A kanbanszabályt a kanbanok létrehozása előtt el kell menteni.</span><span class="sxs-lookup"><span data-stu-id="a7474-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="a7474-136">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a7474-136">Click Add.</span></span>
    * <span data-ttu-id="a7474-137">Vegye figyelembe, hogy nincsenek aktív kanbanok, mert 2 a javasolt „Kanbanok száma”, amely megegyezik a „Rögzített kanbanmennyiség” lehetőséggel.</span><span class="sxs-lookup"><span data-stu-id="a7474-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="a7474-138">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7474-138">Click Create.</span></span>
    * <span data-ttu-id="a7474-139">Ez 2 kanbant hoz létre.</span><span class="sxs-lookup"><span data-stu-id="a7474-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="a7474-140">Vegye figyelembe, hogy a rendszer a visszavonási kanbanszabályokra vonatkozóan 2 kanbant hozott létre, egyenként 5-öt.</span><span class="sxs-lookup"><span data-stu-id="a7474-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="a7474-141">Ez az eljárás utolsó lépése.</span><span class="sxs-lookup"><span data-stu-id="a7474-141">This is the last step in this procedure.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]