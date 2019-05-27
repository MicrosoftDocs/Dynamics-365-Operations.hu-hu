---
title: Naplózási házirendek meghatározása a forrásbizonylatok számára
description: Ez az eljárás bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok.
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a82c3e8e8787beb309b75b73cda36f4ca8031d6f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558883"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="7fe96-103">Naplózási házirendek meghatározása a forrásbizonylatok számára</span><span class="sxs-lookup"><span data-stu-id="7fe96-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7fe96-104">Ez az eljárás bemutatja, hogyan állíthatók be és működtethetők könyvvizsgálati irányelvszabályok.</span><span class="sxs-lookup"><span data-stu-id="7fe96-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="7fe96-105">A példa költségjelentéseket használ szállodai költségtípussal.</span><span class="sxs-lookup"><span data-stu-id="7fe96-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="7fe96-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="7fe96-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="7fe96-107">A könyvvizsgáló szerepkör tartalmazza a megfelelő engedélyeket ezen műveletek elvégzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="7fe96-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="7fe96-108">Ugrás a Könyvvizsgálati munkaterület > Beállítás > Irányelvszabály-típus menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="7fe96-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-109">Click New.</span></span>
3. <span data-ttu-id="7fe96-110">Írjon be egy értéket a Szabály neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7fe96-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="7fe96-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7fe96-112">A Lekérdezés neve mezőben válassza ki a Költségjelentés sort</span><span class="sxs-lookup"><span data-stu-id="7fe96-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="7fe96-113">A lekérdezés típusa mezőben válassza ki az Összesítés parancsot</span><span class="sxs-lookup"><span data-stu-id="7fe96-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="7fe96-114">A Jogi személy mezőben válasszon egy Jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="7fe96-115">A Dokumentum dátumreferenciája mezőben válassza ki a Módosítás dátuma és időpontja elemet</span><span class="sxs-lookup"><span data-stu-id="7fe96-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="7fe96-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-116">Click Save.</span></span>
10. <span data-ttu-id="7fe96-117">Ugrás a Könyvvizsgálati munkaterület > Beállítás > Könyvviteli irányelvek menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="7fe96-118">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-118">Click New.</span></span>
12. <span data-ttu-id="7fe96-119">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7fe96-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="7fe96-120">Bontsa ki az Irányelv szervezetei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="7fe96-121">A fán válassza ki a „Contoso Szórakozás rendszer USA” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7fe96-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="7fe96-122">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-122">Click Add.</span></span>
16. <span data-ttu-id="7fe96-123">A fán válassza ki a „Contoso Consulting USA” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7fe96-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="7fe96-124">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-124">Click Add.</span></span>
18. <span data-ttu-id="7fe96-125">A fán válassza ki a „Contoso Retail USA” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7fe96-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="7fe96-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-126">Click Add.</span></span>
20. <span data-ttu-id="7fe96-127">Csukja be az Irányelv szervezetei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="7fe96-128">Bontsa ki az Irányelvszabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="7fe96-129">A listában keresse meg és válassza ki a korábban létrehozott Irányelvszabályt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="7fe96-130">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="7fe96-131">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="7fe96-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="7fe96-132">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-132">Click Filter.</span></span>
26. <span data-ttu-id="7fe96-133">A listában válassza ki a Költségkategória sort, és adja meg a Szálloda adatait</span><span class="sxs-lookup"><span data-stu-id="7fe96-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="7fe96-134">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="7fe96-135">Kattintson az Összesítés fülre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="7fe96-136">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-136">Click Add.</span></span>
30. <span data-ttu-id="7fe96-137">A listában válassza ki a Tranzakció összege mezőértékét</span><span class="sxs-lookup"><span data-stu-id="7fe96-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="7fe96-138">A Mező mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="7fe96-139">Az Összesítő funkcióban válassza ki az „Összeg”lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7fe96-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="7fe96-140">Kattintson a Csoport lapra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="7fe96-141">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-141">Click Add.</span></span>
35. <span data-ttu-id="7fe96-142">A listából válasszon egy Alkalmazott értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="7fe96-143">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-143">Click Add.</span></span>
37. <span data-ttu-id="7fe96-144">A listából válasszon egy Költségkategória értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="7fe96-145">A Mező mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="7fe96-146">Kattintson a Megvan fülre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-146">Click the Having tab.</span></span>
40. <span data-ttu-id="7fe96-147">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-147">Click Add.</span></span>
41. <span data-ttu-id="7fe96-148">Tranzakcióösszegek kijelölése</span><span class="sxs-lookup"><span data-stu-id="7fe96-148">Select Transaction amount</span></span>
42. <span data-ttu-id="7fe96-149">A Mező mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="7fe96-150">Az Összesítő funkcióban válassza ki az „Összeg”lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7fe96-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="7fe96-151">A Feltétel mezőbe írja be a „>2000” értéket.</span><span class="sxs-lookup"><span data-stu-id="7fe96-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="7fe96-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-152">Click OK.</span></span>
46. <span data-ttu-id="7fe96-153">Kattintson a Teszt gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-153">Click Test.</span></span>
47. <span data-ttu-id="7fe96-154">A Bizonylatkijelölés kezdő dátuma mezőben adjon meg egy dátumot és egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="7fe96-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="7fe96-155">A Bizonylatkijelölés záró dátuma mezőben adjon meg egy dátumot és egy időpontot.</span><span class="sxs-lookup"><span data-stu-id="7fe96-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="7fe96-156">Kattintson a Teszt futtatása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-156">Click Run test.</span></span>
50. <span data-ttu-id="7fe96-157">A Művelet panelen kattintson a Könyvvizsgálati irányelv elemre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="7fe96-158">Kattintson a további beállítások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-158">Click Additional options.</span></span>
52. <span data-ttu-id="7fe96-159">A „Kezdő dátum” mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="7fe96-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="7fe96-160">A Záró dátum mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="7fe96-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="7fe96-161">Kattintson a Kötegre.</span><span class="sxs-lookup"><span data-stu-id="7fe96-161">Click Batch.</span></span>
55. <span data-ttu-id="7fe96-162">Bontsa ki a Futtatás a háttérben szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="7fe96-163">Válassza az Igen lehetőséget a Kötegelt feldolgozás mezőben.</span><span class="sxs-lookup"><span data-stu-id="7fe96-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="7fe96-164">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-164">Click OK.</span></span>
58. <span data-ttu-id="7fe96-165">Ugrás a Könyvvizsgálati munkaterület > Könyvvizsgálati esetek menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="7fe96-166">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7fe96-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="7fe96-167">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="7fe96-168">Bontsa ki a Társítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7fe96-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="7fe96-169">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="7fe96-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="7fe96-170">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="7fe96-170">In the list, click the link in the selected row.</span></span>

