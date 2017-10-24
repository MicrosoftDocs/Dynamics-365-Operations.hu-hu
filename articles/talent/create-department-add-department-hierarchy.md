---
title: "Részleg létrehozása és társítása a szervezeti hierarchiához"
description: "A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli. Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások). A részlegek segítségével hozhatók létre jelentések a működési területekről. A részlegeknek lehet eredménykimutatási felelőssége."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HierarchyDesigner, OMOperatingUnit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adf3dbf8b7ffa906c872a6b66d9cb43eb8e02805
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-department-and-associate-it-with-the-department-hierarchy"></a><span data-ttu-id="068a6-106">Részleg létrehozása és társítása a szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="068a6-106">Create a department and associate it with the department hierarchy</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="068a6-107">A részleg egy működési egység, amely a szervezet egy kategóriáját vagy működési területét képviseli.</span><span class="sxs-lookup"><span data-stu-id="068a6-107">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="068a6-108">Egy részleg a szervezet egy konkrét területen végzett tevékenységeiért felel (például értékesítés, könyvelés, emberi erőforrások).</span><span class="sxs-lookup"><span data-stu-id="068a6-108">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="068a6-109">A részlegek segítségével hozhatók létre jelentések a működési területekről.</span><span class="sxs-lookup"><span data-stu-id="068a6-109">You can use departments to report on functional areas.</span></span> <span data-ttu-id="068a6-110">A részlegeknek lehet eredménykimutatási felelőssége.</span><span class="sxs-lookup"><span data-stu-id="068a6-110">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="068a6-111">Egy részleg költséghelyek egy csoportját is magában foglalhatja.</span><span class="sxs-lookup"><span data-stu-id="068a6-111">A department might include a group of cost centers.</span></span> <span data-ttu-id="068a6-112">A Beosztások hozzárendelhetők részlegekhez.</span><span class="sxs-lookup"><span data-stu-id="068a6-112">Positions can be assigned to departments.</span></span> <span data-ttu-id="068a6-113">Részleg létrehozásához kattintson az **Emberi erőforrások** &gt; **Részlegek** &gt; **Részleg** elemre.</span><span class="sxs-lookup"><span data-stu-id="068a6-113">To create a department, click **Human Resources** &gt; **Departments** &gt; **Department**.</span></span> <span data-ttu-id="068a6-114">Az alábbi táblázat bemutatja a rendelkezésre álló mezőket.</span><span class="sxs-lookup"><span data-stu-id="068a6-114">The following table describes the fields that are available.</span></span>

| <span data-ttu-id="068a6-115">Mező</span><span class="sxs-lookup"><span data-stu-id="068a6-115">Field</span></span>               | <span data-ttu-id="068a6-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="068a6-116">Description</span></span>                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="068a6-117">Név</span><span class="sxs-lookup"><span data-stu-id="068a6-117">Name</span></span>                | <span data-ttu-id="068a6-118">Adja meg a részleg nevét.</span><span class="sxs-lookup"><span data-stu-id="068a6-118">Enter a name for the department.</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="068a6-119">Részleg száma</span><span class="sxs-lookup"><span data-stu-id="068a6-119">Department number</span></span>   | <span data-ttu-id="068a6-120">A rendszer automatikusan létrehozhat egy alapértelmezett értéket, ha egy számsorozat kódja hozzá van rendelve a **Szervezet száma** hivatkozáshoz a **Számsorozatok** lapon.</span><span class="sxs-lookup"><span data-stu-id="068a6-120">A default value might be generated automatically if a number sequence code is assigned to the **Organization number** reference on the **Number sequences** page.</span></span>                                                 |
| <span data-ttu-id="068a6-121">Keresési név</span><span class="sxs-lookup"><span data-stu-id="068a6-121">Search name</span></span>         | <span data-ttu-id="068a6-122">Adja meg a részleg megkeresésére használt nevet vagy rövidítést.</span><span class="sxs-lookup"><span data-stu-id="068a6-122">Enter a name or acronym that can be used to search for the department.</span></span>                                                                                                                                            |
| <span data-ttu-id="068a6-123">Feljegyzés</span><span class="sxs-lookup"><span data-stu-id="068a6-123">Memo</span></span>                | <span data-ttu-id="068a6-124">Itt adjon meg további információkat.</span><span class="sxs-lookup"><span data-stu-id="068a6-124">Enter any additional information here.</span></span>                                                                                                                                                                            |
| <span data-ttu-id="068a6-125">Hierarchiában</span><span class="sxs-lookup"><span data-stu-id="068a6-125">In hierarchy</span></span>        | <span data-ttu-id="068a6-126">A bejelölt jelölőnégyzet mutatja, ha a részleg szerepel a szervezeti hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="068a6-126">A selected check box indicates that the department is included in the department hierarchy.</span></span> <span data-ttu-id="068a6-127">Ezen cikk későbbi részei tartalmaznak információkat azzal kapcsolatban, hogy miként lehet részleget adni a részleghierarchiához.</span><span class="sxs-lookup"><span data-stu-id="068a6-127">For information about how to add a department to the department hierarchy, see the information later in this article.</span></span> |
| <span data-ttu-id="068a6-128">DUNS-szám</span><span class="sxs-lookup"><span data-stu-id="068a6-128">DUNS number</span></span>         | <span data-ttu-id="068a6-129">A DUNS a Data Universal Numbering System számozási rendszer rövidítése.</span><span class="sxs-lookup"><span data-stu-id="068a6-129">DUNS stands for Data Universal Number System.</span></span> <span data-ttu-id="068a6-130">Ez egy a Dun & Bradstreet által kiállított kilencjegyű szám.</span><span class="sxs-lookup"><span data-stu-id="068a6-130">This is a nine-digit number that is issued by Dun & Bradstreet.</span></span>                                                                                                     |
| <span data-ttu-id="068a6-131">Vezető</span><span class="sxs-lookup"><span data-stu-id="068a6-131">Manager</span></span>             | <span data-ttu-id="068a6-132">Adja meg a részleget vezető személyt.</span><span class="sxs-lookup"><span data-stu-id="068a6-132">Enter the persona that manages the department.</span></span>                                                                                                                                                                    |
| <span data-ttu-id="068a6-133">Címek</span><span class="sxs-lookup"><span data-stu-id="068a6-133">Addresses</span></span>           | <span data-ttu-id="068a6-134">Adja meg a részleg címinformációit.</span><span class="sxs-lookup"><span data-stu-id="068a6-134">Add the address information for the department.</span></span> <span data-ttu-id="068a6-135">Adja meg például annak az épületnek a levelezési címét, amelyben a részleg található.</span><span class="sxs-lookup"><span data-stu-id="068a6-135">For example, add the mailing address for the building that the department is located in.</span></span>                                                                          |
| <span data-ttu-id="068a6-136">Kapcsolattartási adatok</span><span class="sxs-lookup"><span data-stu-id="068a6-136">Contact information</span></span> | <span data-ttu-id="068a6-137">Adja meg a részleg kapcsolattartási információit.</span><span class="sxs-lookup"><span data-stu-id="068a6-137">Add contact information for the department.</span></span> <span data-ttu-id="068a6-138">Adja meg például a részleg ügyfélszolgálatának vagy recepciójának telefonszámát.</span><span class="sxs-lookup"><span data-stu-id="068a6-138">For example, add a telephone number for the service desk in the department.</span></span>                                                                                           |

<span data-ttu-id="068a6-139">Egy részleg hozzáadásához a részleghierarchiához, tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="068a6-139">To add a department to the department hierarchy, follow these steps.</span></span>

1.  <span data-ttu-id="068a6-140">Kattintson az **Emberi erőforrások** &gt; **Részlegek** &gt; **Részlegek hierarchiája** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="068a6-140">Click **Human Resources** &gt; **Departments** &gt; **Department hierarchy**.</span></span>
2.  <span data-ttu-id="068a6-141">Kattintson a **Szerkesztés** lehetőségre, majd válassza ki a szervezetet, amely alá a részleg tartozik.</span><span class="sxs-lookup"><span data-stu-id="068a6-141">Click **Edit**, and then select the organization that the department should be under.</span></span>
3.  <span data-ttu-id="068a6-142">Kattintson a **Beszúrás** lehetőségre, és válassza ki a **Részleget** a listából.</span><span class="sxs-lookup"><span data-stu-id="068a6-142">Click **Insert**, and select **Department** in the list.</span></span>
4.  <span data-ttu-id="068a6-143">A megjelenő listából válassza ki a részleget, amelyet hozzá kíván adni a hierarchiához.</span><span class="sxs-lookup"><span data-stu-id="068a6-143">In the list of departments that appears, select the department to add to the hierarchy.</span></span>
5.  <span data-ttu-id="068a6-144">Mentse el a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="068a6-144">Save your changes.</span></span> <span data-ttu-id="068a6-145">Egy üzenet fog kapni arról, hogy létrejött-e a hierarchia egy vázlatverziója.</span><span class="sxs-lookup"><span data-stu-id="068a6-145">You receive a message that a draft version of the hierarchy has been created.</span></span>
6.  <span data-ttu-id="068a6-146">Ha elkészült, kattintson a **Közzététel** lehetőségre a hierarchiatervezőben.</span><span class="sxs-lookup"><span data-stu-id="068a6-146">When you're ready, click **Publish** in the hierarchy designer.</span></span> <span data-ttu-id="068a6-147">Megadhat egy hatályba lépési dátumot, amely azt jelzi, hogy mikor kell közzétenni a hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="068a6-147">You can enter an effective date that indicates when the hierarchy should be published.</span></span> <span data-ttu-id="068a6-148">Ha például a következő naptári év kezdetén kell hozzáadni az új részleget, akkor állítsa a hatálybalépési dátumot a következő év január 1-re.</span><span class="sxs-lookup"><span data-stu-id="068a6-148">For example, to add a new department at the beginning of the next calendar year, set the effective date to January 1 of the new calendar year.</span></span> <span data-ttu-id="068a6-149">A hierarchia módosításai ezen a dátumon lépnek hatályba.</span><span class="sxs-lookup"><span data-stu-id="068a6-149">The changes to the hierarchy will take effect on that date.</span></span>




