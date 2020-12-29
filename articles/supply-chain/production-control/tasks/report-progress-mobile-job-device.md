---
title: Jelentéskészítés egy mobil feladatvégző eszközön elért haladásról
description: Ez az eljárással megmutatja, hogyan indíthat termelési feladatot és jelentheti az előrehaladását a feladateszköz-regisztrációs űrlapon.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationTouch, JmgRegistrationTouchUserConfiguration, JmgRegistrationTouchStart, JmgRegistrationTouchReportFeedback, JmgRegistrationTouchAssignedJobs, JmgRegistrationTouchBreak, JmgRegistrationTouchLeave, JmgRegistrationTouchIndirectActivity, JmgDialogForm, JmgRegistrationTouchReportProgress, JmgFeedbackWizard, JmgJobBundleProdFeedback
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 34067902f05546b5c420feca633f77f16033ed2c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429502"
---
# <a name="report-progress-on-a-mobile-job-device"></a><span data-ttu-id="9352b-103">Jelentéskészítés egy mobil feladatvégző eszközön elért haladásról</span><span class="sxs-lookup"><span data-stu-id="9352b-103">Report progress on a mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9352b-104">Ez az eljárással megmutatja, hogyan indíthat termelési feladatot és jelentheti az előrehaladását a feladateszköz-regisztrációs űrlapon.</span><span class="sxs-lookup"><span data-stu-id="9352b-104">This procedure shows you how to start and report progress on a production job in the job device registration form.</span></span>



<span data-ttu-id="9352b-105">Ezen eljárás futtatásához rendszergazdai vagy gépkezelői szerepkört kell társítani a felhasználói fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="9352b-105">To be able to run this procedure you must have the System administator or Machine Operator role associated with the user account.</span></span>

1. <span data-ttu-id="9352b-106">Ugrás a Gyártásvezérlés > Gyártásvégrehajtási > Feladatkártya eszköze részre.</span><span class="sxs-lookup"><span data-stu-id="9352b-106">Go to Production control > Manufacturing execution > Job card device.</span></span>
2. <span data-ttu-id="9352b-107">A WorkerTextField mezőben adja meg egy dolgozó belépőkártyáját.</span><span class="sxs-lookup"><span data-stu-id="9352b-107">In the WorkerTextField field, enter the badge of a worker.</span></span> <span data-ttu-id="9352b-108">Az USMF bemutatóadat esetében írja be: hogy „123”, Christina Portra.</span><span class="sxs-lookup"><span data-stu-id="9352b-108">In the USMF demo data type '123' for Christina Portra..</span></span>
3. <span data-ttu-id="9352b-109">Kattintson a Bejelentkezés elemre.</span><span class="sxs-lookup"><span data-stu-id="9352b-109">Click Log in.</span></span>
4. <span data-ttu-id="9352b-110">Kattintson a Szűrő gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-110">Click the Filter button.</span></span>
5. <span data-ttu-id="9352b-111">Jelölje be a Konfigurációs szűrő alkalmazása jelölőnégyzetet vagy törölje a jelölését.</span><span class="sxs-lookup"><span data-stu-id="9352b-111">Check or uncheck the Apply configuration filter check box.</span></span> <span data-ttu-id="9352b-112">Ha beállít egy szűrőt, használhatja az USMF 110-es termelési egységét.</span><span class="sxs-lookup"><span data-stu-id="9352b-112">If you set a filter you can use production unit 110 in USMF.</span></span>
6. <span data-ttu-id="9352b-113">A Termelési egység mezőben válassza az erőforráscsoportot, amelynek a termelési feladatain a dolgozó dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="9352b-113">In the Production unit field, select the ressource group for which production jobs the worker can work on.</span></span>
7. <span data-ttu-id="9352b-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9352b-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="9352b-115">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-115">Click OK.</span></span>
9. <span data-ttu-id="9352b-116">Kattintson a Feladat kezdése gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-116">Click the Start job button.</span></span>
10. <span data-ttu-id="9352b-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-117">Click OK.</span></span>
11. <span data-ttu-id="9352b-118">Kattintson az Előrehaladás jelentése gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-118">Click the Report progress button.</span></span>
12. <span data-ttu-id="9352b-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-119">Click OK.</span></span>
13. <span data-ttu-id="9352b-120">Kattintson a Következő feladat gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-120">Click the Next job button.</span></span>
14. <span data-ttu-id="9352b-121">Kattintson a Minden termelési feladat áttekintéséhez társítva gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-121">Click the Assigned to see an overview of all production jobs button.</span></span>
15. <span data-ttu-id="9352b-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9352b-122">Close the page.</span></span>
16. <span data-ttu-id="9352b-123">Kattintson a Szünet gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-123">Click the Break button.</span></span>
17. <span data-ttu-id="9352b-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="9352b-124">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="9352b-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-125">Click OK.</span></span>
19. <span data-ttu-id="9352b-126">Kattintson a Távozás gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-126">Click the Leaving button.</span></span>
20. <span data-ttu-id="9352b-127">Válassza a Kijelentkezés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9352b-127">Select to log out.</span></span>
21. <span data-ttu-id="9352b-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-128">Click OK.</span></span>
22. <span data-ttu-id="9352b-129">A WorkerTextField mezőben jelentkezzen be újra.</span><span class="sxs-lookup"><span data-stu-id="9352b-129">In the WorkerTextField field, log in again.</span></span> <span data-ttu-id="9352b-130">A USMF bemutatóadatok esetében választhatja az „123” dolgozót.</span><span class="sxs-lookup"><span data-stu-id="9352b-130">You can select worker '123' in USMF demo data.</span></span>
23. <span data-ttu-id="9352b-131">Kattintson a Bejelentkezés elemre.</span><span class="sxs-lookup"><span data-stu-id="9352b-131">Click Log in.</span></span>
24. <span data-ttu-id="9352b-132">Kattintson a Szünet befejezése elemre.</span><span class="sxs-lookup"><span data-stu-id="9352b-132">Click Stop break.</span></span>
25. <span data-ttu-id="9352b-133">Kattintson a Tevékenység gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-133">Click the Activity button.</span></span>
26. <span data-ttu-id="9352b-134">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-134">Click Cancel.</span></span>
27. <span data-ttu-id="9352b-135">Kattintson a Távozás gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-135">Click the Leaving button.</span></span>
28. <span data-ttu-id="9352b-136">Válassza a Kijelentkezés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9352b-136">Select to clock out.</span></span>
29. <span data-ttu-id="9352b-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9352b-137">Click OK.</span></span>
30. <span data-ttu-id="9352b-138">Válasszon egy okot, hogy miért jelentkezik ki korán.</span><span class="sxs-lookup"><span data-stu-id="9352b-138">Select a reason why you are clocking out early.</span></span>

