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
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 93ec5bd6984dd1a8f970834070fd77873078b3b0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237131"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="1090e-103">Termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="1090e-103">Schedule a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1090e-104">Ez az eljárás bemutatja, hogyan lehet termelési rendelést ütemezni.</span><span class="sxs-lookup"><span data-stu-id="1090e-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="1090e-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="1090e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1090e-106">Ez a harmadik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.</span><span class="sxs-lookup"><span data-stu-id="1090e-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="1090e-107">Termelési rendelés ütemezése</span><span class="sxs-lookup"><span data-stu-id="1090e-107">Schedule a production order</span></span>
1. <span data-ttu-id="1090e-108">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="1090e-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="1090e-109">Válasszon ki egy Becsült állapotú termelési rendelést.</span><span class="sxs-lookup"><span data-stu-id="1090e-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="1090e-110">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="1090e-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="1090e-111">Kattintson a Feladatok ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1090e-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="1090e-112">Az ütemezéshez beállított paramétereket ezen az oldalon állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="1090e-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="1090e-113">Beállíthatja a paramétereket adott felhasználók, vagy az összes felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="1090e-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="1090e-114">Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól előrefelé” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1090e-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="1090e-115">Adjon meg egy dátumot az Ütemezési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="1090e-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="1090e-116">Jelölje be a Véges kapacitás jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="1090e-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="1090e-117">Jelölje be a Véges anyag jelölőnégyzetet, vagy törölje belőle a jelet.</span><span class="sxs-lookup"><span data-stu-id="1090e-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="1090e-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1090e-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="1090e-119">Ütemezési eredmények megtekintése</span><span class="sxs-lookup"><span data-stu-id="1090e-119">View the scheduling results</span></span>
1. <span data-ttu-id="1090e-120">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="1090e-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="1090e-121">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="1090e-121">Click All jobs.</span></span>
    * <span data-ttu-id="1090e-122">Ezen a lapon láthatók a nemrég létrehozott ütemezett feladatokat.</span><span class="sxs-lookup"><span data-stu-id="1090e-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="1090e-123">Bontsa ki vagy csukja össze az Ütemezés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="1090e-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="1090e-124">Az Ütemezés gyorslapon megtekintheti az ütemezett dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="1090e-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="1090e-125">Kattintson a Lekérdezések elemre.</span><span class="sxs-lookup"><span data-stu-id="1090e-125">Click Inquiries.</span></span>
5. <span data-ttu-id="1090e-126">Kattintson a Kapacitásterhelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1090e-126">Click Capacity load.</span></span>
    * <span data-ttu-id="1090e-127">A Terhelési kapacitás lap megjeleníti, hogy milyen kapacitást foglalt le a feladat ütemezésén keresztül, az erőforráson jelenleg lefoglalt órák összes számát, illetve a fennmaradó az erőforrás a feladat ütemezéséhez még rendelkezésre álló óráinak a számát.</span><span class="sxs-lookup"><span data-stu-id="1090e-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="1090e-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1090e-128">Close the page.</span></span>
7. <span data-ttu-id="1090e-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1090e-129">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]