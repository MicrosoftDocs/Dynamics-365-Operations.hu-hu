---
title: Felhasználás regisztrálása
description: Ez a témakör azt mutatja be, hogyan lehet felhasználást regisztrálni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 174c816c7a6442b07e4722c03045293b94c59153
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024660"
---
# <a name="register-consumption"></a><span data-ttu-id="233fc-103">Felhasználás regisztrálása</span><span class="sxs-lookup"><span data-stu-id="233fc-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="233fc-104">Ha egy munkarendelésen befejeződött egy karbantartási feladat, következő lépésként el kell végezni a felhasználási regisztrációkat és a naplók feladását.</span><span class="sxs-lookup"><span data-stu-id="233fc-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="233fc-105">Regisztráció a következő felhasználási típusokon végezhető el: órák, cikkek és kiadások.</span><span class="sxs-lookup"><span data-stu-id="233fc-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="233fc-106">A program a különböző felhasználási típusokat a **Munkarendelési naplók** lapon regisztrálja és adja fel.</span><span class="sxs-lookup"><span data-stu-id="233fc-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="233fc-107">A program az **Eszközkezelés modulban** található naplóbeállítást használja a **Projektvezetés és könyvelés** modulban feltüntetett órák, cikkek és kiadások külön naplóinak a létrehozásához és feladásához.</span><span class="sxs-lookup"><span data-stu-id="233fc-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="233fc-108">Előfordulhat, hogy egy munkarendelésben lehetősége van hozzáadni vagy törölni előrejelzési sorokat.</span><span class="sxs-lookup"><span data-stu-id="233fc-108">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="233fc-109">A munkarendelés életciklus-állapotának beállítása, a kapcsolódó projekttípus és a projekt típusára vonatkozó szakaszszabályok határozzák meg, hogy a naplósorok hozzáadhatók-e a naplóhoz, vagy szerkeszthetők-e.</span><span class="sxs-lookup"><span data-stu-id="233fc-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="233fc-110">A munkarendelés életciklus-állapotáról és a kapcsolódó projektszakaszokról itt talál további információt: [A Projektvezetés és könyveléssel való integráció](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="233fc-110">Read more about work order lifecycle states and related project stages in [Integration to project management and accounting](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="233fc-111">A munkarendelés életciklus-állapotára vonatkozó naplókhoz automatikus feladás is beállítható.</span><span class="sxs-lookup"><span data-stu-id="233fc-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="233fc-112">További információt itt talál: [Munkarendelés életciklus-állapotai](../setup-for-work-orders/work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="233fc-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="233fc-113">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="233fc-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="233fc-114">Válassza ki a munkarendelést, majd kattintson a **Naplók** elemre.</span><span class="sxs-lookup"><span data-stu-id="233fc-114">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="233fc-115">A **Másolás előrejelzésből** lehetőségre kattintva átviheti azokat az előrejelzési sorokat, amelyek a munkarendeléshez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="233fc-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="233fc-116">Kiválaszthatja az átvinni kívánt felhasználási típusokat.</span><span class="sxs-lookup"><span data-stu-id="233fc-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="233fc-117">A **Sor hozzáadása** gombra kattintva és a sor adatainak kitöltésével több felhasználási sort is hozzáadhat a megfelelő gyorslaphoz, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="233fc-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="233fc-118">A **Naplók ellenőrzése** elemre kattintva ellenőrizheti a naplósorokat feladás előtt.</span><span class="sxs-lookup"><span data-stu-id="233fc-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="233fc-119">A **Naplók feladása** gombra kattintva feladhatja a naplósorokat.</span><span class="sxs-lookup"><span data-stu-id="233fc-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="233fc-120">A felhasználási naplók feladását követően frissítheti a munkarendelés életciklus-állapotát, például „Befejezettre”, és ezzel jelezheti, hogy a munkarendelés befejeződött.</span><span class="sxs-lookup"><span data-stu-id="233fc-120">After you've posted the consumption journals, you can update the work order lifecycle state, for example to "Ended", to indicate that the work order has been completed.</span></span>

- <span data-ttu-id="233fc-121">A **Munkarendelési naplók** lap tetején található **Megjelenítés** mezőben válassza ki a megjeleníteni kívánt naplósorokat a következők közül: Összes, Nincs feladva vagy Feladva.</span><span class="sxs-lookup"><span data-stu-id="233fc-121">In the **Show** field placed at the top of the **Work order journals** page, select which journal lines you want to see: All, Not posted, or Posted.</span></span> <span data-ttu-id="233fc-122">A feladott naplóknál ki van pipálva a **Feladva** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="233fc-122">Posted journals have a check mark in the **Posted** check box.</span></span>  
- <span data-ttu-id="233fc-123">Amikor a munkarendelési naplóban cikksorok jönnek létre, a program automatikusan átviszi a cikkhez tartozó termékdimenziókat és nyomon követési dimenziókat a napló sorába.</span><span class="sxs-lookup"><span data-stu-id="233fc-123">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="233fc-124">Az alábbi képernyőkép azt szemlélteti, hogyan kell a **Munkarendelési naplók** elemben óra- és cikkregisztrációkat elvégezni egy munkarendelésnél.</span><span class="sxs-lookup"><span data-stu-id="233fc-124">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![1. ábra](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="233fc-126">A munkarendelések óráinak több munkarendelési feladattal történő megosztása</span><span class="sxs-lookup"><span data-stu-id="233fc-126">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="233fc-127">Ha a munkarendelés több munkarendelési feladatot is tartalmaz, akkor a munkaórák regisztrálhatók az **Órák megosztása** funkció segítségével, ami azt jelenti, hogy az egyes munkarendelési feladatokban egyenletesen lehet felosztani az egyórás regisztrációs sort.</span><span class="sxs-lookup"><span data-stu-id="233fc-127">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="233fc-128">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="233fc-128">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="233fc-129">Válassza ki a munkarendelést, majd kattintson a **Naplók** elemre.</span><span class="sxs-lookup"><span data-stu-id="233fc-129">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="233fc-130">Válassza ki a megosztani kívánt óraregisztrációs sort, majd kattintson az **Órák megosztása**elemre.</span><span class="sxs-lookup"><span data-stu-id="233fc-130">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="233fc-131">A **Munkarendelés karbantartási feladataihoz tartozó megosztott órák** párbeszédpanelen a bejelentkezett dolgozó neve automatikusan megjelenik a **Dolgozó** mezőben.</span><span class="sxs-lookup"><span data-stu-id="233fc-131">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="233fc-132">Szükség esetén másik dolgozót is kiválaszthat.</span><span class="sxs-lookup"><span data-stu-id="233fc-132">If required, you can select another worker.</span></span>

5. <span data-ttu-id="233fc-133">Válasszon ki egy kategóriát az óraregisztrációhoz a **Kategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="233fc-133">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="233fc-134">Írja be a megosztandó munkaórák számát  az **Órák** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="233fc-134">Insert number of work hours to be split in the **Hours** field.</span></span>

![2. ábra](media/02-consumption.png)

7. <span data-ttu-id="233fc-136">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="233fc-136">Click **OK**.</span></span>

<span data-ttu-id="233fc-137">*Példa:* az alábbi képernyőképen három munkarendelési feladatot tartalmazó munkarendeléshez tartozó naplósorok láthatók.</span><span class="sxs-lookup"><span data-stu-id="233fc-137">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="233fc-138">A három munkaórát tartalmazó első sor már fel van osztva, és minden munkarendelésnél egy munkaóra van regisztrálva.</span><span class="sxs-lookup"><span data-stu-id="233fc-138">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="233fc-139">Miután létrehozta a három órás regisztrációs sort, eldöntheti, mi legyen az eredeti óraregisztrációs sorral (a példa első sorával).</span><span class="sxs-lookup"><span data-stu-id="233fc-139">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="233fc-140">Megtarthatja, de akár törölheti is.</span><span class="sxs-lookup"><span data-stu-id="233fc-140">You can keep it as is or delete it.</span></span> 

![3. ábra](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="233fc-142">Felhasználási regisztrációk pénzügyi dimenziói</span><span class="sxs-lookup"><span data-stu-id="233fc-142">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="233fc-143">Felhasználási regisztrációk végrehajtásakor a rendszer egy megadott sorrendben hozzáadja a regisztrációkhoz a különböző regisztrációtípusokhoz kapcsolódó pénzügyi dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="233fc-143">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

<span data-ttu-id="233fc-144">*Óra- és kiadásregisztrációk:* először a napló fejlécében szereplő pénzügyi dimenziókat adja hozzá a program, ha vannak ilyen dimenziók.</span><span class="sxs-lookup"><span data-stu-id="233fc-144">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="233fc-145">Következő lépésként a kapcsolódó munkarendelés-projekt pénzügyi dimenzióinak felvételére kerül sor.</span><span class="sxs-lookup"><span data-stu-id="233fc-145">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="233fc-146">Végezetül az erőforrás (dolgozó) pénzügyi dimenzióit adja hozzá a program.</span><span class="sxs-lookup"><span data-stu-id="233fc-146">Finally, financial dimensions from the resource (worker) are added.</span></span>

<span data-ttu-id="233fc-147">*Cikkregisztrációk:* először a napló fejlécében szereplő pénzügyi dimenziókat adja hozzá a program, ha vannak ilyen dimenziók.</span><span class="sxs-lookup"><span data-stu-id="233fc-147">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="233fc-148">Majd a kapcsolódó munkarendelés-projekt pénzügyi dimenzióinak felvételére kerül sor.</span><span class="sxs-lookup"><span data-stu-id="233fc-148">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="233fc-149">A következő lépés a hely pénzügyi dimenzióinak felvétele.</span><span class="sxs-lookup"><span data-stu-id="233fc-149">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="233fc-150">Végezetül a cikk pénzügyi dimenzióit adja hozzá a program.</span><span class="sxs-lookup"><span data-stu-id="233fc-150">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="233fc-151">A program mindhárom regisztrációtípusnál ellenőrzi a pénzügyi dimenzió kombinációját, és az érvénytelen kombinációkat üresen hagyja.</span><span class="sxs-lookup"><span data-stu-id="233fc-151">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="233fc-152">Ez a szokásos beállítás a Finance and Operations megoldásban.</span><span class="sxs-lookup"><span data-stu-id="233fc-152">This is standard setup in Finance and Operations.</span></span>

