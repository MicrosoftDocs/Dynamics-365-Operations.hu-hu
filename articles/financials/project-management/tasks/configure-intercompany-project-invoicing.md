--- 
title: "Vállalatközi projektszámlázás konfigurálása"
description: "Ez az eljárás bemutatja, hogyan állíthatja be a projektek számlázását két vállalat között a szervezeten belül."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: cd871f1182217bf5cab34c1e38e8f0d9cc3808cd
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="a7846-103">Vállalatközi projektszámlázás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a7846-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a7846-104">Ez az eljárás bemutatja, hogyan állíthatja be a projektek számlázását két vállalat között a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="a7846-104">This procedure shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="a7846-105">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="a7846-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="a7846-106">Ugrás a Kötelezettségek > Szállítók > Minden szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="a7846-106">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="a7846-107">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a7846-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a7846-108">A Művelet panelen kattintson az Általános elemre.</span><span class="sxs-lookup"><span data-stu-id="a7846-108">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="a7846-109">Kattintson a Vállalatközi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7846-109">Click Intercompany.</span></span>
5. <span data-ttu-id="a7846-110">A vállalatközi kereskedelem engedélyezéséhez az Aktív lehetőséget állítsa Igen beállításra.</span><span class="sxs-lookup"><span data-stu-id="a7846-110">Set Active to Yes to enable intercompany trading.</span></span>
6. <span data-ttu-id="a7846-111">A Vevő vállalat mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a7846-111">In the Customer company field, enter or select a value.</span></span>
7. <span data-ttu-id="a7846-112">A Saját számla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a7846-112">In the My account field, enter or select a value.</span></span>
8. <span data-ttu-id="a7846-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7846-113">Click Save.</span></span>
9. <span data-ttu-id="a7846-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7846-114">Close the page.</span></span>
10. <span data-ttu-id="a7846-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7846-115">Close the page.</span></span>
11. <span data-ttu-id="a7846-116">Nyissa meg a Projektvezetés és könyvelés > Beállítások > Projektvezetési és könyvelési paraméterek pontot.</span><span class="sxs-lookup"><span data-stu-id="a7846-116">Go to Project management and accounting > Setup > Project management and accounting parameters.</span></span>
12. <span data-ttu-id="a7846-117">Kattintson a vállalatközi fülre.</span><span class="sxs-lookup"><span data-stu-id="a7846-117">Click the Intercompany tab.</span></span>
13. <span data-ttu-id="a7846-118">Mozgassa a csúszkát az Igen lehetőséghez a vállalatközi erőforrás-ütemezés és időnyilvántartások engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7846-118">Move the slider to Yes to enable intercompany resource scheduling and timesheets.</span></span>
14. <span data-ttu-id="a7846-119">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a7846-119">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="a7846-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7846-120">Click New.</span></span>
16. <span data-ttu-id="a7846-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a7846-121">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="a7846-122">A Kölcsönbe vevő jogi személy mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a7846-122">In the Borrowing legal entity field, enter or select a value.</span></span>
18. <span data-ttu-id="a7846-123">Jelölje be az Elhatárolt bevétel jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="a7846-123">Select the Accrue revenue check box.</span></span>
19. <span data-ttu-id="a7846-124">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett időnyilvántartás-kategória mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7846-124">In the Default timesheet category field, enter or select a value.</span></span>
20. <span data-ttu-id="a7846-125">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett kiadáskategória mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7846-125">In the Default expense category field, enter or select a value.</span></span>
21. <span data-ttu-id="a7846-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7846-126">Click Save.</span></span>
22. <span data-ttu-id="a7846-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7846-127">Close the page.</span></span>
23. <span data-ttu-id="a7846-128">Ugrás a projektvezetési és könyvelési > Beállítás > Feladás > Főkönyvi feladás beállítása elemre.</span><span class="sxs-lookup"><span data-stu-id="a7846-128">Go to Project management and accounting > Setup > Posting > Ledger posting setup.</span></span>
24. <span data-ttu-id="a7846-129">Válasszon egy lehetőséget a Főkönyvtípusok mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7846-129">In the Ledger account types field, select an option.</span></span>
25. <span data-ttu-id="a7846-130">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="a7846-130">Click New.</span></span>
26. <span data-ttu-id="a7846-131">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a7846-131">In the list, mark the selected row.</span></span>
27. <span data-ttu-id="a7846-132">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a7846-132">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="a7846-133">A Fő számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7846-133">In the Main account field, specify the desired values.</span></span>
29. <span data-ttu-id="a7846-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7846-134">Click Save.</span></span>
30. <span data-ttu-id="a7846-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7846-135">Close the page.</span></span>
31. <span data-ttu-id="a7846-136">Ugorjon a Projektvezetés és könyvelés > Beállítás > Árak > Transzferár lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7846-136">Go to Project management and accounting > Setup > Prices > Transfer price.</span></span>
32. <span data-ttu-id="a7846-137">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7846-137">Click New.</span></span>
33. <span data-ttu-id="a7846-138">Adja meg a dátumot az Érvényesség dátuma mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7846-138">In the Effective date field, enter a date.</span></span>
34. <span data-ttu-id="a7846-139">A Kölcsönbe vevő jogi személy mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a7846-139">In the Borrowing legal entity field, enter or select a value.</span></span>
35. <span data-ttu-id="a7846-140">Válasszon egy lehetőséget a Transzferármodell mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7846-140">In the Transfer price model field, select an option.</span></span>
36. <span data-ttu-id="a7846-141">Adjon meg egy számot az Árazás mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7846-141">In the Pricing field, enter a number.</span></span>
37. <span data-ttu-id="a7846-142">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a7846-142">Click Save.</span></span>


