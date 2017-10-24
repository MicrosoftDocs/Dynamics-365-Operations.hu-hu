--- 
title: "Egy helyhez tartozó ütemezés létrehozása"
description: "Ez az eljárás bemutatja az egy helyhez tartozó, még el nem indított termelési rendelések ütemezését."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 775428bf84a752c03c492e764fa9ed576ab64fb8
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="937d5-103">Egy helyhez tartozó ütemezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="937d5-103">Create a schedule for a site</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="937d5-104">Ez az eljárás bemutatja az egy helyhez tartozó, még el nem indított termelési rendelések ütemezését.</span><span class="sxs-lookup"><span data-stu-id="937d5-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="937d5-105">Az USMF bemutatócég segítségével végzik el ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="937d5-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="937d5-106">Határozza meg az el nem indított termelési rendeléseket</span><span class="sxs-lookup"><span data-stu-id="937d5-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="937d5-107">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="937d5-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="937d5-108">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="937d5-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="937d5-109">Például végezzen szűrést az „1”-es értékkel ellátott Hely mezőben.</span><span class="sxs-lookup"><span data-stu-id="937d5-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="937d5-110">Az 1 egy helyet jelöl az USMF-ben.</span><span class="sxs-lookup"><span data-stu-id="937d5-110">1 represents a site in USMF.</span></span> <span data-ttu-id="937d5-111">Ha nem használ USMF-et, válasszon ki egy helyet a saját vállalatai közül.</span><span class="sxs-lookup"><span data-stu-id="937d5-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="937d5-112">Nyissa meg az Állapot oszlopszűrőt.</span><span class="sxs-lookup"><span data-stu-id="937d5-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="937d5-113">Alkalmazzon szűrőt a „Állapot mezőben” az „Ütemezett értékkel” a „pontosan” szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="937d5-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="937d5-114">Hozzon létre egy ütemezést</span><span class="sxs-lookup"><span data-stu-id="937d5-114">Create a schedule</span></span>
1. <span data-ttu-id="937d5-115">A listában jelölje meg az összes sort, vagy törölje a jelölésüket.</span><span class="sxs-lookup"><span data-stu-id="937d5-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="937d5-116">A Művelet panelen kattintson az Ütemezés elemre.</span><span class="sxs-lookup"><span data-stu-id="937d5-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="937d5-117">Kattintson a Feladatok ütemezése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="937d5-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="937d5-118">Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól visszafelé” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="937d5-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="937d5-119">Válassza a Nem lehetőséget a Véges kapacitás mezőben.</span><span class="sxs-lookup"><span data-stu-id="937d5-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="937d5-120">Válassza a Nem lehetőséget a Véges anyag mezőben.</span><span class="sxs-lookup"><span data-stu-id="937d5-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="937d5-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="937d5-121">Click OK.</span></span>
    * <span data-ttu-id="937d5-122">Ez eltarthat egy ideig.</span><span class="sxs-lookup"><span data-stu-id="937d5-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="937d5-123">Az ütemezett termelési rendelés eredményének megtekintése.</span><span class="sxs-lookup"><span data-stu-id="937d5-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="937d5-124">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="937d5-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="937d5-125">Bármelyik sort megjelölheti.</span><span class="sxs-lookup"><span data-stu-id="937d5-125">You can mark any row.</span></span>  
2. <span data-ttu-id="937d5-126">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="937d5-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="937d5-127">Kattintson a Minden feladat elemre.</span><span class="sxs-lookup"><span data-stu-id="937d5-127">Click All jobs.</span></span>
    * <span data-ttu-id="937d5-128">Ezen a lapon megtekintheti a feladatok listáját.</span><span class="sxs-lookup"><span data-stu-id="937d5-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="937d5-129">Az ütemezés lapon megtekintheti a feladat kezdő és záró dátumát.</span><span class="sxs-lookup"><span data-stu-id="937d5-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="937d5-130">Kattintson az Anyagok elemre.</span><span class="sxs-lookup"><span data-stu-id="937d5-130">Click Materials.</span></span>
    * <span data-ttu-id="937d5-131">Ezen a lapon megtekintheti a becsült anyagfelhasználást a termelési rendelésben és az aktuális rendelkezésre álló készletben szereplő műveletekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="937d5-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  

