---
title: Helyettesítési kanbanszabály létrehozása
description: Ez az eljárás egy meglévő kanbanszabály egy új kanbanszabállyal történő lecserélésére irányul az adott dátumon.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5aebd88dee9621d2c85af3a4fb5bf76ae8e6b80
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828946"
---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="ffc3e-103">Helyettesítési kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="ffc3e-103">Create a replacement kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ffc3e-104">Ez az eljárás egy meglévő kanbanszabály egy új kanbanszabállyal történő lecserélésére irányul az adott dátumon.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="ffc3e-105">Ez akkor hasznos, amikor koordinálni és ütemezni kell a gyártási folyamatban vagy a feltöltési szabályokban történt módosításokat.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="ffc3e-106">Az USMF bemutatócéget segítségével jött létre az eljárás.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="ffc3e-107">Ez az eljárás a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, amikor előkészítik a termelést a módosított termelési folyamathoz vagy az új feltöltési szabályhoz.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="ffc3e-108">Ez a feladat a 000022-es kanbanszabályt egy új szabállyal cseréli ki, illetve a maximális mennyiséget 48-ról 100-ra növeli az új szabályra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="ffc3e-109">Válassza ki a lecserélni kívánt kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="ffc3e-110">Ugorjon a Kanbanszabályokhoz.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="ffc3e-111">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ffc3e-112">Válasszon ki a 000022 kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="ffc3e-113">Helyettesítési kanbanszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="ffc3e-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="ffc3e-114">Kattintson a Kanbanszabály lecserélése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="ffc3e-115">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="ffc3e-116">Válassza ki egy jövőbeli dátumot, például egy héttel későbbi dátumot.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="ffc3e-117">Ez az a dátum és időpont, amikor az új kanbanszabály aktívvá válik és helyettesíti a régi kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="ffc3e-118">Ha a kanbanszabály módosítja a termelési folyamat elérési útját, akkor ki lehet választani egy másik tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="ffc3e-119">Ebben az eljárásban ajánlott változatlanul hagyni a tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="ffc3e-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-120">Click OK.</span></span>
    * <span data-ttu-id="ffc3e-121">Figyelje meg, hogy a rendszer már létrehozott egy új kanbanszabályt a 000022 kanbanszabály helyettesítésére.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="ffc3e-122">Az érvényességi dátumot azon kiválasztott dátum szerint állítják be, amikor kicseréli a kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="ffc3e-123">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ffc3e-124">Válassza ki a cserélt 000022 kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="ffc3e-125">Vegye figyelembe, hogy a cserélt kanbanszabály dátuma ugyanaz, mint a Lejárati dátum, mert ez az a dátum, amikor a kanbanszabály lejár.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="ffc3e-126">Jelölje ki az 1. sort a listában.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="ffc3e-127">Válassza ki a lista tetején az új kanbanszabályt.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="ffc3e-128">Ez a legnagyobb kanbanszabály számmal rendelkező kanbanszabály.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="ffc3e-129">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ffc3e-130">Kattintson a kanbanszabály-számra a kanbanszabály megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="ffc3e-131">Módosítsa a maximális mennyiségét a Helyettesítési kanbanszabályra vonatkozóan</span><span class="sxs-lookup"><span data-stu-id="ffc3e-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="ffc3e-132">Állítsa a Maximális mennyiséget „100” értékre.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="ffc3e-133">Bontsa ki a Mennyiségek gyorslapot a Maximális mennyiség mező megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="ffc3e-134">A maximális mennyiség 100-ra történő módosítása legfeljebb 100 kanban feldolgozását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="ffc3e-135">Ez az feladat utolsó lépése.</span><span class="sxs-lookup"><span data-stu-id="ffc3e-135">This is the last step in this task.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]