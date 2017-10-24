--- 
title: "Jelentéskészítés egy mobil feladatvégző eszközön elért haladásról"
description: "Ez az eljárással megmutatja, hogyan indíthat termelési feladatot és jelentheti az előrehaladását a feladateszköz-regisztrációs űrlapon."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: acbedc6d27624d9a8d1e6fb9bb0d9abed1b4377f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="report-progress-on-a-mobile-job-device"></a><span data-ttu-id="20792-103">Jelentéskészítés egy mobil feladatvégző eszközön elért haladásról</span><span class="sxs-lookup"><span data-stu-id="20792-103">Report progress on a mobile job device</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="20792-104">Ez az eljárással megmutatja, hogyan indíthat termelési feladatot és jelentheti az előrehaladását a feladateszköz-regisztrációs űrlapon.</span><span class="sxs-lookup"><span data-stu-id="20792-104">This procedure shows you how to start and report progress on a production job in the job device registration form.</span></span>



<span data-ttu-id="20792-105">Ezen eljárás futtatásához rendszergazdai vagy gépkezelői szerepkört kell társítani a felhasználói fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="20792-105">To be able to run this procedure you must have the System administator or Machine Operator role associated with the user account.</span></span>

1. <span data-ttu-id="20792-106">Ugrás a Gyártásvezérlés > Gyártásvégrehajtási > Feladatkártya eszköze részre.</span><span class="sxs-lookup"><span data-stu-id="20792-106">Go to Production control > Manufacturing execution > Job card device.</span></span>
2. <span data-ttu-id="20792-107">A WorkerTextField mezőben adja meg egy dolgozó belépőkártyáját.</span><span class="sxs-lookup"><span data-stu-id="20792-107">In the WorkerTextField field, enter the badge of a worker.</span></span> <span data-ttu-id="20792-108">Az USMF bemutatóadat esetében írja be: hogy „123”, Christina Portra.</span><span class="sxs-lookup"><span data-stu-id="20792-108">In the USMF demo data type '123' for Christina Portra..</span></span>
3. <span data-ttu-id="20792-109">Kattintson a Bejelentkezés elemre.</span><span class="sxs-lookup"><span data-stu-id="20792-109">Click Log in.</span></span>
4. <span data-ttu-id="20792-110">Kattintson a Szűrő gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-110">Click the Filter button.</span></span>
5. <span data-ttu-id="20792-111">Jelölje be a Konfigurációs szűrő alkalmazása jelölőnégyzetet vagy törölje a jelölését.</span><span class="sxs-lookup"><span data-stu-id="20792-111">Check or uncheck the Apply configuration filter check box.</span></span> <span data-ttu-id="20792-112">Ha beállít egy szűrőt, használhatja az USMF 110-es termelési egységét.</span><span class="sxs-lookup"><span data-stu-id="20792-112">If you set a filter you can use production unit 110 in USMF.</span></span>
6. <span data-ttu-id="20792-113">A Termelési egység mezőben válassza az erőforráscsoportot, amelynek a termelési feladatain a dolgozó dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="20792-113">In the Production unit field, select the ressource group for which production jobs the worker can work on.</span></span>
7. <span data-ttu-id="20792-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="20792-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="20792-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-115">Click OK.</span></span>
9. <span data-ttu-id="20792-116">Kattintson a Feladat kezdése gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-116">Click the Start job button.</span></span>
10. <span data-ttu-id="20792-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-117">Click OK.</span></span>
11. <span data-ttu-id="20792-118">Kattintson az Előrehaladás jelentése gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-118">Click the Report progress button.</span></span>
12. <span data-ttu-id="20792-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-119">Click OK.</span></span>
13. <span data-ttu-id="20792-120">Kattintson a Következő feladat gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-120">Click the Next job button.</span></span>
14. <span data-ttu-id="20792-121">Kattintson a Minden termelési feladat áttekintéséhez társítva gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-121">Click the Assigned to see an overview of all production jobs button.</span></span>
15. <span data-ttu-id="20792-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="20792-122">Close the page.</span></span>
16. <span data-ttu-id="20792-123">Kattintson a Szünet gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-123">Click the Break button.</span></span>
17. <span data-ttu-id="20792-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="20792-124">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="20792-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-125">Click OK.</span></span>
19. <span data-ttu-id="20792-126">Kattintson a Távozás gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-126">Click the Leaving button.</span></span>
20. <span data-ttu-id="20792-127">Válassza a Kijelentkezés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="20792-127">Select to log out.</span></span>
21. <span data-ttu-id="20792-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-128">Click OK.</span></span>
22. <span data-ttu-id="20792-129">A WorkerTextField mezőben jelentkezzen be újra.</span><span class="sxs-lookup"><span data-stu-id="20792-129">In the WorkerTextField field, log in again.</span></span> <span data-ttu-id="20792-130">A USMF bemutatóadatok esetében választhatja az „123” dolgozót.</span><span class="sxs-lookup"><span data-stu-id="20792-130">You can select worker '123' in USMF demo data.</span></span>
23. <span data-ttu-id="20792-131">Kattintson a Bejelentkezés elemre.</span><span class="sxs-lookup"><span data-stu-id="20792-131">Click Log in.</span></span>
24. <span data-ttu-id="20792-132">Kattintson a Szünet befejezése elemre.</span><span class="sxs-lookup"><span data-stu-id="20792-132">Click Stop break.</span></span>
25. <span data-ttu-id="20792-133">Kattintson a Tevékenység gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-133">Click the Activity button.</span></span>
26. <span data-ttu-id="20792-134">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-134">Click Cancel.</span></span>
27. <span data-ttu-id="20792-135">Kattintson a Távozás gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-135">Click the Leaving button.</span></span>
28. <span data-ttu-id="20792-136">Válassza a Kijelentkezés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="20792-136">Select to clock out.</span></span>
29. <span data-ttu-id="20792-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20792-137">Click OK.</span></span>
30. <span data-ttu-id="20792-138">Válasszon egy okot, hogy miért jelentkezik ki korán.</span><span class="sxs-lookup"><span data-stu-id="20792-138">Select a reason why you are clocking out early.</span></span>

