---
title: Termelési rendelés ütemezése
description: Ez az eljárás bemutatja, hogyan lehet termelési rendelést ütemezni.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b3fe8f6890c7d8ac8835503091642faa773f7f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429478"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="f6a29-103">Termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="f6a29-103">Schedule a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f6a29-104">Ez az eljárás bemutatja, hogyan lehet termelési rendelést ütemezni.</span><span class="sxs-lookup"><span data-stu-id="f6a29-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="f6a29-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="f6a29-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f6a29-106">Ez a harmadik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="f6a29-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="f6a29-107">Termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="f6a29-107">Schedule a production order</span></span>
1. <span data-ttu-id="f6a29-108">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="f6a29-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="f6a29-109">Válasszon ki egy Becsült állapotú termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="f6a29-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="f6a29-110">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="f6a29-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="f6a29-111">Kattintson a Feladatok ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f6a29-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="f6a29-112">Az ütemezéshez beállított paramétereket ezen az oldalon állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="f6a29-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="f6a29-113">Beállíthatja a paramétereket adott felhasználók, vagy az összes felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="f6a29-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="f6a29-114">Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól előrefelé” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6a29-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="f6a29-115">Adjon meg egy dátumot az Ütemezési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="f6a29-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="f6a29-116">Jelölje be a Véges kapacitás jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="f6a29-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="f6a29-117">Jelölje be a Véges anyag jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="f6a29-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="f6a29-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f6a29-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="f6a29-119">Ütemezési eredmények megtekintése</span><span class="sxs-lookup"><span data-stu-id="f6a29-119">View the scheduling results</span></span>
1. <span data-ttu-id="f6a29-120">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="f6a29-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="f6a29-121">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="f6a29-121">Click All jobs.</span></span>
    * <span data-ttu-id="f6a29-122">Ezen a lapon láthatók a nemrég létrehozott ütemezett feladatokat.</span><span class="sxs-lookup"><span data-stu-id="f6a29-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="f6a29-123">Bontsa ki vagy csukja össze az Ütemezés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f6a29-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="f6a29-124">Az Ütemezés gyorslapon megtekintheti az ütemezett dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="f6a29-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="f6a29-125">Kattintson a Lekérdezések elemre.</span><span class="sxs-lookup"><span data-stu-id="f6a29-125">Click Inquiries.</span></span>
5. <span data-ttu-id="f6a29-126">Kattintson a Kapacitásterhelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f6a29-126">Click Capacity load.</span></span>
    * <span data-ttu-id="f6a29-127">A Terhelési kapacitás lap megjeleníti, hogy milyen kapacitást foglalt le a feladat ütemezésén keresztül, az erőforráson jelenleg lefoglalt órák összes számát, illetve a fennmaradó az erőforrás a feladat ütemezéséhez még rendelkezésre álló óráinak a számát.</span><span class="sxs-lookup"><span data-stu-id="f6a29-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="f6a29-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6a29-128">Close the page.</span></span>
7. <span data-ttu-id="f6a29-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6a29-129">Close the page.</span></span>

