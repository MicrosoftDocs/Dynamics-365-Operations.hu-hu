--- 
title: "Jelentés készként egy azonosítótábla-vezérelt helyre "
description: "Ez a Feladat útmutató a készként történő jelentés példáját mutatja be azon a helyen, amely nem azonosítótábla-vezérelt."
author: ChristianRytt
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 34fac03a0ff3d71a2349b66f8f85e4e124dcd708
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="report-as-finished-to-a-plate-controlled-location"></a><span data-ttu-id="7f743-103">Jelentés készként egy azonosítótábla-vezérelt helyre </span><span class="sxs-lookup"><span data-stu-id="7f743-103">Report as finished to a plate-controlled location</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7f743-104">Ez a Feladat útmutató a készként történő jelentés példáját mutatja be azon a helyen, amely nem azonosítótábla-vezérelt.</span><span class="sxs-lookup"><span data-stu-id="7f743-104">This task guide shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="7f743-105">Az alkalmazható munkairányelvek ezen feladat előfeltételei.</span><span class="sxs-lookup"><span data-stu-id="7f743-105">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="7f743-106">A korábbi feladat útmutató a munkairányelvek beállítását mutatta be.</span><span class="sxs-lookup"><span data-stu-id="7f743-106">A previous task guide showed the setup of the work policy.</span></span> <span data-ttu-id="7f743-107">Ez a feladat 7.0.1-es vagy újabb verziós Dynamics AX alkalmazást igényel.</span><span class="sxs-lookup"><span data-stu-id="7f743-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>




## <a name="set-up-an-output-location"></a><span data-ttu-id="7f743-108">A kimeneti helyek beállítása</span><span class="sxs-lookup"><span data-stu-id="7f743-108">Set up an output location</span></span>
1. <span data-ttu-id="7f743-109">Ugrás a Szervezet felügyelete > Erőforrások > Erőforráscsoportok részhez.</span><span class="sxs-lookup"><span data-stu-id="7f743-109">Go to Organization administration > Resources > Resource groups.</span></span>
2. <span data-ttu-id="7f743-110">Válassza ki a listában az „5102” erőforráscsoportot.</span><span class="sxs-lookup"><span data-stu-id="7f743-110">In the list, select resource group '5102'.</span></span>
3. <span data-ttu-id="7f743-111">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f743-111">Click Edit.</span></span>
4. <span data-ttu-id="7f743-112">Adja meg a Kimeneti raktár mezőben az „51” értéket.</span><span class="sxs-lookup"><span data-stu-id="7f743-112">In the Output warehouse field, enter '51'.</span></span>
5. <span data-ttu-id="7f743-113">Adja meg a Kimeneti hely mezőben az „001” értéket.</span><span class="sxs-lookup"><span data-stu-id="7f743-113">In the Output location field, enter '001'.</span></span>
    * <span data-ttu-id="7f743-114">A 001 Hely nem egy azonosítótáblás szabályozású hely.</span><span class="sxs-lookup"><span data-stu-id="7f743-114">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="7f743-115">A nem azonosítótáblás kimeneti helyet csak akkor állíthatja be, ha a megfelelő munkairányelveket létrehozták a helyre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="7f743-115">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span>  

## <a name="create-a-production-order-and-report-it-as-finished"></a><span data-ttu-id="7f743-116">A Termelési jelentés létrehozása és készként történő jelentése.</span><span class="sxs-lookup"><span data-stu-id="7f743-116">Create a production order and report it as finished</span></span>
1. <span data-ttu-id="7f743-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7f743-117">Close the page.</span></span>
2. <span data-ttu-id="7f743-118">Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.</span><span class="sxs-lookup"><span data-stu-id="7f743-118">Go to Production control > Production orders > All production orders.</span></span>
3. <span data-ttu-id="7f743-119">Kattintson az Új termelési rendelés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f743-119">Click New production order.</span></span>
4. <span data-ttu-id="7f743-120">Adja meg a „L0101” értéket a Cikkszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="7f743-120">In the Item number field, enter 'L0101'.</span></span>
5. <span data-ttu-id="7f743-121">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f743-121">Click Create.</span></span>
6. <span data-ttu-id="7f743-122">A Művelet panelen kattintson a Termelési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="7f743-122">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="7f743-123">Kattintson a Becslés elemre.</span><span class="sxs-lookup"><span data-stu-id="7f743-123">Click Estimate.</span></span>
8. <span data-ttu-id="7f743-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7f743-124">Click OK.</span></span>
9. <span data-ttu-id="7f743-125">Kattintson a Start parancsra.</span><span class="sxs-lookup"><span data-stu-id="7f743-125">Click Start.</span></span>
10. <span data-ttu-id="7f743-126">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="7f743-126">Click the General tab.</span></span>
11. <span data-ttu-id="7f743-127">Az automatikus BOM-felhasználás mezőben válassza ki a „Soha” értéket.</span><span class="sxs-lookup"><span data-stu-id="7f743-127">In the Automatic BOM consumption field, select 'Never'.</span></span>
12. <span data-ttu-id="7f743-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7f743-128">Click OK.</span></span>
13. <span data-ttu-id="7f743-129">Kattintson a Készre jelentés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f743-129">Click Report as finished.</span></span>
14. <span data-ttu-id="7f743-130">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="7f743-130">Click the General tab.</span></span>
15. <span data-ttu-id="7f743-131">Válassza ki az Igen lehetőséget a Hiba elfogadása mezőben.</span><span class="sxs-lookup"><span data-stu-id="7f743-131">Select Yes in the Accept error field.</span></span>
16. <span data-ttu-id="7f743-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7f743-132">Click OK.</span></span>
17. <span data-ttu-id="7f743-133">A Műveleti panelen kattintson a Raktár elemre.</span><span class="sxs-lookup"><span data-stu-id="7f743-133">On the Action Pane, click Warehouse.</span></span>
18. <span data-ttu-id="7f743-134">Kattintson a Munka részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7f743-134">Click Work details.</span></span>
    * <span data-ttu-id="7f743-135">Amikor a termelési rendelést készként jelentették, a rendszer nem hozott létre munkát a betárolásra.</span><span class="sxs-lookup"><span data-stu-id="7f743-135">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="7f743-136">Ennek az az oka, hogy a munkairányelveket úgy határozzák meg, hogy megakadályozza a munka létrehozását, amikor a rendszer készként jelenti a L0101 terméket a 001 helyen.</span><span class="sxs-lookup"><span data-stu-id="7f743-136">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span>  


