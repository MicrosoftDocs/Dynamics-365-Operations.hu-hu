--- 
title: "Időszaki naplók közzététele"
description: "Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok az időszaki napló beolvasásákor minden alkalommal megismétlődnek."
author: aprilolson
manager: AnnBe
ms.date: 02/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 233d145a9d3441ffc2b816b8514e58988b517136
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="post-periodic-journals"></a><span data-ttu-id="82746-103">Időszaki naplók közzététele</span><span class="sxs-lookup"><span data-stu-id="82746-103">Post periodic journals</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="82746-104">Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok az időszaki napló beolvasásákor minden alkalommal megismétlődnek.</span><span class="sxs-lookup"><span data-stu-id="82746-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the periodic journal is retrieved.</span></span> <span data-ttu-id="82746-105">Időszaki napló létrehozásakor határozza meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap).</span><span class="sxs-lookup"><span data-stu-id="82746-105">When you create the periodic journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="82746-106">Ez a feladat útmutató havi ismétlődés időszaki naplót hoz létre.</span><span class="sxs-lookup"><span data-stu-id="82746-106">This task guide will create a periodic journal with a monthly recurrence.</span></span>



1. <span data-ttu-id="82746-107">Ugorjon a Főkönyv > Időszaki feladatok > Időszaki naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="82746-107">Go to General ledger > Periodic tasks > Periodic journals.</span></span>
2. <span data-ttu-id="82746-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82746-108">Click New.</span></span>
3. <span data-ttu-id="82746-109">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82746-109">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="82746-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="82746-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="82746-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82746-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="82746-112">A leírás a későbbi előhíváskor az Időszaki napló neve lesz, ezért adjon neki megfelelő nevet.</span><span class="sxs-lookup"><span data-stu-id="82746-112">The description will be the name of the Periodic journal when retrieved later so make sure to give it a relevant name.</span></span>  
6. <span data-ttu-id="82746-113">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="82746-113">Click Lines.</span></span>
    * <span data-ttu-id="82746-114">Egy Időszaki napló általában több naplósort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="82746-114">A periodic journal will typically include several journal lines.</span></span> <span data-ttu-id="82746-115">Ez az útmutató azonban most csak egy sort ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="82746-115">this task guide will however only add one line.</span></span>  
7. <span data-ttu-id="82746-116">Adja meg a dátumot a Dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="82746-116">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="82746-117">A Dátum mező a napi naplóba történő következő átvitel feladási dátumát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="82746-117">The Date field contains the posting date for the next transfer to the daily journal.</span></span> <span data-ttu-id="82746-118">A naplókhoz, amelyeket havonta előhív, ajánlott a feladás dátumának használata az adott hónapban, általában az időszak első vagy utolsó dátuma.</span><span class="sxs-lookup"><span data-stu-id="82746-118">For journals that will be retrieved each month it is recommended to use the date in the month when it will be posted, typically the first or last date in the period.</span></span> <span data-ttu-id="82746-119">A Dátum mezőt üresen is hagyhatja, és megadhatja a napló visszaolvasásának dátumát, az Üres dátum mező használatával.</span><span class="sxs-lookup"><span data-stu-id="82746-119">It is possible to leave the Date field blank and to give a date when the journal is retrieved, using the Empty date field.</span></span>    <span data-ttu-id="82746-120">A mező automatikusan frissül a következő ismétlődő dátumra, amikor a tranzakciókat előhívják.</span><span class="sxs-lookup"><span data-stu-id="82746-120">The field is automatically updated to the next recurring date when transactions are retrieved.</span></span>  
8. <span data-ttu-id="82746-121">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="82746-121">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="82746-122">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82746-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="82746-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="82746-123">Close the page.</span></span>
11. <span data-ttu-id="82746-124">Adjon meg egy számot a Tartozik mezőben.</span><span class="sxs-lookup"><span data-stu-id="82746-124">In the Debit field, enter a number.</span></span>
12. <span data-ttu-id="82746-125">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="82746-125">In the Offset account field, specify the desired values.</span></span>
13. <span data-ttu-id="82746-126">Válassza a 'Hónapok' lehetőséget az Egység mezőben.</span><span class="sxs-lookup"><span data-stu-id="82746-126">In the Unit field, select 'Months'.</span></span>
14. <span data-ttu-id="82746-127">Az Egységek száma mezőben írja be az 1-es számot.</span><span class="sxs-lookup"><span data-stu-id="82746-127">In the Number of units field, enter '1'.</span></span>
15. <span data-ttu-id="82746-128">Adja meg a dátumot az Utolsó dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="82746-128">In the Last date field, enter a date.</span></span>
    * <span data-ttu-id="82746-129">Az utolsó dátum megadása az előző időszakban megakadályozza, hogy az ismétlődő napló tévedésből a helytelen kezdőidőszakban jöjjön létre.</span><span class="sxs-lookup"><span data-stu-id="82746-129">Entering last date in the preceding period will prevent that the recurring journal by mistake is created in the wrong starting period.</span></span> <span data-ttu-id="82746-130">Az utolsó dátum később minden alkalommal frissül, valahányszor az időszaki naplót a program beolvassa.</span><span class="sxs-lookup"><span data-stu-id="82746-130">Last date will later on be updated each time the periodic journal is retrieved.</span></span>  
16. <span data-ttu-id="82746-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="82746-131">Click Save.</span></span>
17. <span data-ttu-id="82746-132">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="82746-132">Go to Default dashboard.</span></span>
18. <span data-ttu-id="82746-133">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="82746-133">Go to General ledger > Journal entries > General journals.</span></span>
19. <span data-ttu-id="82746-134">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="82746-134">Click New.</span></span>
20. <span data-ttu-id="82746-135">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82746-135">In the Name field, enter or select a value.</span></span>
21. <span data-ttu-id="82746-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="82746-136">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="82746-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="82746-137">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="82746-138">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82746-138">In the Description field, type a value.</span></span>
24. <span data-ttu-id="82746-139">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="82746-139">Click Lines.</span></span>
25. <span data-ttu-id="82746-140">Kattintson az Időszaknapló pontra.</span><span class="sxs-lookup"><span data-stu-id="82746-140">Click Period journal.</span></span>
26. <span data-ttu-id="82746-141">Kattintson a Napló beolvasása manüpontra.</span><span class="sxs-lookup"><span data-stu-id="82746-141">Click Retrieve journal.</span></span>
27. <span data-ttu-id="82746-142">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="82746-142">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="82746-143">A Záró dátum az időszakos bizonylatsor fordulónapjaként szolgál.</span><span class="sxs-lookup"><span data-stu-id="82746-143">The To date serves as the cutoff date for the periodic voucher lines.</span></span> <span data-ttu-id="82746-144">Az ismétlődés beállításától függően, az Utolsó dátum és a Záró dátum ugyanabban a sorban többször is benne lehet a keletkező naplóban.</span><span class="sxs-lookup"><span data-stu-id="82746-144">Based on the recurrence setting, the Last date and To date the same line might be included more than once in the resulting journal.</span></span> <span data-ttu-id="82746-145">A Záró dátum automatikusan frissül attól függően, hogy az időszaki sor mikor került utoljára át a naplóba.</span><span class="sxs-lookup"><span data-stu-id="82746-145">To date is automatically updated based on  session date of the last time the periodic line was transferred to a journal.</span></span>  
28. <span data-ttu-id="82746-146">Az Időszaki naplószám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="82746-146">In the Periodic journal number field, enter or select a value.</span></span>
29. <span data-ttu-id="82746-147">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="82746-147">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="82746-148">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="82746-148">Click OK.</span></span>
    * <span data-ttu-id="82746-149">Az időszaknapló készen áll a felülvizsgálatra, jóváhagyás vagy az elküldésre a követelményektől vagy a beállítástól függően.</span><span class="sxs-lookup"><span data-stu-id="82746-149">The period journal can now be reviewed, approved or posted depending on requirement and setup.</span></span>  


