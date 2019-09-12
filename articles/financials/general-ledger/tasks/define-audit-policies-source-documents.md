---
title: Naplózási házirendek meghatározása a forrásbizonylatok számára
description: Ez a témakör bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6b0fa28d778a4d9fa1f718b1d50bf1dce00be00
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914830"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="5d350-103">Naplózási házirendek meghatározása a forrásbizonylatok számára</span><span class="sxs-lookup"><span data-stu-id="5d350-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d350-104">Ez a témakör bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok.</span><span class="sxs-lookup"><span data-stu-id="5d350-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="5d350-105">A példa költségjelentéseket használ szállodai költségtípussal.</span><span class="sxs-lookup"><span data-stu-id="5d350-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="5d350-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5d350-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="5d350-107">A könyvvizsgáló szerepkör tartalmazza a megfelelő engedélyeket ezen műveletek elvégzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="5d350-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="5d350-108">A navigációs ablakban nyissa meg **Modulokat > Könyvvizsgálati munkaterület > Beállítás > Irányelv-szabály típusa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="5d350-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-109">Select **New**.</span></span>
3. <span data-ttu-id="5d350-110">Írjon be egy értéket a **Szabály neve** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5d350-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="5d350-111">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5d350-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="5d350-112">A **Lekérdezés neve** mezőben válassza ki a **Költségjelentés** sort</span><span class="sxs-lookup"><span data-stu-id="5d350-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="5d350-113">A **lekérdezés típusa** mezőben válassza ki az **Összesítés** parancsot</span><span class="sxs-lookup"><span data-stu-id="5d350-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="5d350-114">A **Jogi személy** mezőben válasszon egy **Jogi személyt**.</span><span class="sxs-lookup"><span data-stu-id="5d350-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="5d350-115">A **Dokumentum dátumreferenciája** mezőben válassza ki a **Módosítás dátuma és időpontja** elemet</span><span class="sxs-lookup"><span data-stu-id="5d350-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="5d350-116">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-116">Select **Save**.</span></span>
10. <span data-ttu-id="5d350-117">A navigációs ablakban nyissa meg **Modulokat > Könyvvizsgálati munkaterület > Beállítás > Auditirányelvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="5d350-118">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-118">Select **New**.</span></span>
12. <span data-ttu-id="5d350-119">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5d350-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="5d350-120">Bontsa ki az **Irányelv szervezetei** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5d350-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="5d350-121">A fán válassza ki a **Contoso Szórakozás rendszer USA** majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="5d350-122">A fán válassza ki a **Contoso Consulting USA** majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="5d350-123">A fán válassza ki a **Contoso Retail USA** majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="5d350-124">Csukja be az **Irányelv szervezetei** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5d350-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="5d350-125">Bontsa ki az **Irányelvszabályok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5d350-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="5d350-126">A listában keresse meg és válassza ki a korábban létrehozott Irányelvszabályt.</span><span class="sxs-lookup"><span data-stu-id="5d350-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="5d350-127">Válassza ki az **Irányelvszabály létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="5d350-128">Az **Érvényesség dátuma** mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="5d350-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="5d350-129">Válassza ki a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="5d350-129">Select **Filter**.</span></span>
23. <span data-ttu-id="5d350-130">A listában válassza ki a **Költségkategória** sort, és adja meg a **Szálloda** adatait</span><span class="sxs-lookup"><span data-stu-id="5d350-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="5d350-131">A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5d350-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="5d350-132">Válassza ki az **Összesítés** lapot.</span><span class="sxs-lookup"><span data-stu-id="5d350-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="5d350-133">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-133">Select **Add**.</span></span>
27. <span data-ttu-id="5d350-134">A listában válassza ki a **Tranzakció összege** mezőértékét</span><span class="sxs-lookup"><span data-stu-id="5d350-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="5d350-135">A **Mező** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5d350-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="5d350-136">Az **Összesítő funkcióban** válassza ki az **Összeg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="5d350-137">A **Csoportosítás alapja** lap kiválasztása</span><span class="sxs-lookup"><span data-stu-id="5d350-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="5d350-138">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-138">Select **Add**.</span></span>
32. <span data-ttu-id="5d350-139">A listából válasszon egy **Alkalmazott** értéket.</span><span class="sxs-lookup"><span data-stu-id="5d350-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="5d350-140">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-140">Select **Add**.</span></span>
34. <span data-ttu-id="5d350-141">A listából válasszon egy **Költségkategória** értéket.</span><span class="sxs-lookup"><span data-stu-id="5d350-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="5d350-142">A **Mező** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5d350-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="5d350-143">Válassza a **Rendelkezik** lapot.</span><span class="sxs-lookup"><span data-stu-id="5d350-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="5d350-144">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-144">Select **Add**.</span></span>
38. <span data-ttu-id="5d350-145">**Tranzakcióösszegek** kijelölése.</span><span class="sxs-lookup"><span data-stu-id="5d350-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="5d350-146">A **Mező** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5d350-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="5d350-147">Az **Összesítő funkcióban** válassza ki az **Összeg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="5d350-148">A **Feltétel** mezőbe írja be a `>2000` értéket.</span><span class="sxs-lookup"><span data-stu-id="5d350-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="5d350-149">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-149">Select **OK**.</span></span>
43. <span data-ttu-id="5d350-150">Válassza a **Teszt** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-150">Select **Test**.</span></span>
44. <span data-ttu-id="5d350-151">A **Bizonylatkijelölés kezdő dátuma** mezőben adjon meg egy dátumot és egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="5d350-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="5d350-152">A **Bizonylatkijelölés záró dátuma** mezőben adjon meg egy dátumot és egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="5d350-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="5d350-153">Válassza a **Teszt futtatása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-153">Select **Run test**.</span></span>
47. <span data-ttu-id="5d350-154">A Művelet panelen kattintson a **Könyvvizsgálati irányelv** elemre.</span><span class="sxs-lookup"><span data-stu-id="5d350-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="5d350-155">Válassza a **További beállítások** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="5d350-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="5d350-156">A **Kezdő dátum** mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="5d350-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="5d350-157">A **Záró dátum** mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="5d350-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="5d350-158">Válassza a **Köteg** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="5d350-158">Select **Batch**.</span></span>
52. <span data-ttu-id="5d350-159">Bontsa ki a **Futtatás a háttérben** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5d350-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="5d350-160">Válassza az **Igen** lehetőséget a **Kötegelt feldolgozás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="5d350-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="5d350-161">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-161">Select **OK**.</span></span>
55. <span data-ttu-id="5d350-162">A navigációs ablakban nyissa meg **Modulok > Könyvvizsgálati munkaterület > Beállítás > Auditesetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5d350-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="5d350-163">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5d350-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="5d350-164">Bontsa ki a **Társítások** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5d350-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="5d350-165">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5d350-165">In the list, find and select the desired record.</span></span>

