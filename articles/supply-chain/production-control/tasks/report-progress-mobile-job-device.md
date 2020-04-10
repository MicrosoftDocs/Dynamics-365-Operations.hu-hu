---
title: Jelentéskészítés egy mobil feladatvégző eszközön elért haladásról
description: Ez az eljárással megmutatja, hogyan indíthat termelési feladatot és jelentheti az előrehaladását a feladateszköz-regisztrációs űrlapon.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationTouch, JmgRegistrationTouchUserConfiguration, JmgRegistrationTouchStart, JmgRegistrationTouchReportFeedback, JmgRegistrationTouchAssignedJobs, JmgRegistrationTouchBreak, JmgRegistrationTouchLeave, JmgRegistrationTouchIndirectActivity, JmgDialogForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70cdd5aff68581af29984e88a16339de921c8ff0
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146652"
---
# <a name="report-progress-on-a-mobile-job-device"></a><span data-ttu-id="9cece-103">Jelentéskészítés egy mobil feladatvégző eszközön elért haladásról</span><span class="sxs-lookup"><span data-stu-id="9cece-103">Report progress on a mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9cece-104">Ez az eljárással megmutatja, hogyan indíthat termelési feladatot és jelentheti az előrehaladását a feladateszköz-regisztrációs űrlapon.</span><span class="sxs-lookup"><span data-stu-id="9cece-104">This procedure shows you how to start and report progress on a production job in the job device registration form.</span></span>



<span data-ttu-id="9cece-105">Ezen eljárás futtatásához rendszergazdai vagy gépkezelői szerepkört kell társítani a felhasználói fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="9cece-105">To be able to run this procedure you must have the System administator or Machine Operator role associated with the user account.</span></span>

1. <span data-ttu-id="9cece-106">Ugrás a Gyártásvezérlés > Gyártásvégrehajtási > Feladatkártya eszköze részre.</span><span class="sxs-lookup"><span data-stu-id="9cece-106">Go to Production control > Manufacturing execution > Job card device.</span></span>
2. <span data-ttu-id="9cece-107">A WorkerTextField mezőben adja meg egy dolgozó belépőkártyáját.</span><span class="sxs-lookup"><span data-stu-id="9cece-107">In the WorkerTextField field, enter the badge of a worker.</span></span> <span data-ttu-id="9cece-108">Az USMF bemutatóadat esetében írja be: hogy „123”, Christina Portra.</span><span class="sxs-lookup"><span data-stu-id="9cece-108">In the USMF demo data type '123' for Christina Portra..</span></span>
3. <span data-ttu-id="9cece-109">Kattintson a Bejelentkezés elemre.</span><span class="sxs-lookup"><span data-stu-id="9cece-109">Click Log in.</span></span>
4. <span data-ttu-id="9cece-110">Kattintson a Szűrő gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-110">Click the Filter button.</span></span>
5. <span data-ttu-id="9cece-111">Jelölje be a Konfigurációs szűrő alkalmazása jelölőnégyzetet vagy törölje a jelölését.</span><span class="sxs-lookup"><span data-stu-id="9cece-111">Check or uncheck the Apply configuration filter check box.</span></span> <span data-ttu-id="9cece-112">Ha beállít egy szűrőt, használhatja az USMF 110-es termelési egységét.</span><span class="sxs-lookup"><span data-stu-id="9cece-112">If you set a filter you can use production unit 110 in USMF.</span></span>
6. <span data-ttu-id="9cece-113">A Termelési egység mezőben válassza az erőforráscsoportot, amelynek a termelési feladatain a dolgozó dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="9cece-113">In the Production unit field, select the ressource group for which production jobs the worker can work on.</span></span>
7. <span data-ttu-id="9cece-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9cece-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="9cece-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-115">Click OK.</span></span>
9. <span data-ttu-id="9cece-116">Kattintson a Feladat kezdése gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-116">Click the Start job button.</span></span>
10. <span data-ttu-id="9cece-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-117">Click OK.</span></span>
11. <span data-ttu-id="9cece-118">Kattintson az Előrehaladás jelentése gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-118">Click the Report progress button.</span></span>
12. <span data-ttu-id="9cece-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-119">Click OK.</span></span>
13. <span data-ttu-id="9cece-120">Kattintson a Következő feladat gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-120">Click the Next job button.</span></span>
14. <span data-ttu-id="9cece-121">Kattintson a Minden termelési feladat áttekintéséhez társítva gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-121">Click the Assigned to see an overview of all production jobs button.</span></span>
15. <span data-ttu-id="9cece-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9cece-122">Close the page.</span></span>
16. <span data-ttu-id="9cece-123">Kattintson a Szünet gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-123">Click the Break button.</span></span>
17. <span data-ttu-id="9cece-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9cece-124">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="9cece-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-125">Click OK.</span></span>
19. <span data-ttu-id="9cece-126">Kattintson a Távozás gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-126">Click the Leaving button.</span></span>
20. <span data-ttu-id="9cece-127">Válassza a Kijelentkezés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9cece-127">Select to log out.</span></span>
21. <span data-ttu-id="9cece-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-128">Click OK.</span></span>
22. <span data-ttu-id="9cece-129">A WorkerTextField mezőben jelentkezzen be újra.</span><span class="sxs-lookup"><span data-stu-id="9cece-129">In the WorkerTextField field, log in again.</span></span> <span data-ttu-id="9cece-130">A USMF bemutatóadatok esetében választhatja az „123” dolgozót.</span><span class="sxs-lookup"><span data-stu-id="9cece-130">You can select worker '123' in USMF demo data.</span></span>
23. <span data-ttu-id="9cece-131">Kattintson a Bejelentkezés elemre.</span><span class="sxs-lookup"><span data-stu-id="9cece-131">Click Log in.</span></span>
24. <span data-ttu-id="9cece-132">Kattintson a Szünet befejezése elemre.</span><span class="sxs-lookup"><span data-stu-id="9cece-132">Click Stop break.</span></span>
25. <span data-ttu-id="9cece-133">Kattintson a Tevékenység gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-133">Click the Activity button.</span></span>
26. <span data-ttu-id="9cece-134">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-134">Click Cancel.</span></span>
27. <span data-ttu-id="9cece-135">Kattintson a Távozás gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-135">Click the Leaving button.</span></span>
28. <span data-ttu-id="9cece-136">Válassza a Kijelentkezés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9cece-136">Select to clock out.</span></span>
29. <span data-ttu-id="9cece-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9cece-137">Click OK.</span></span>
30. <span data-ttu-id="9cece-138">Válasszon egy okot, hogy miért jelentkezik ki korán.</span><span class="sxs-lookup"><span data-stu-id="9cece-138">Select a reason why you are clocking out early.</span></span>

