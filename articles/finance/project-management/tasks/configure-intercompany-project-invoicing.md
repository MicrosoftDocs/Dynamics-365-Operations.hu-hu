---
title: Vállalatközi projektszámlázás konfigurálása
description: Ez a témakör bemutatja, hogyan állíthatja be a projektek számlázását két vállalat között a szervezeten belül.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174443"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="1f2c6-103">Vállalatközi projektszámlázás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1f2c6-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f2c6-104">Ez a témakör bemutatja, hogyan állíthatja be a projektek számlázását két vállalat között a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="1f2c6-105">Ez a feladat az USSI-adatkészletet használja.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="1f2c6-106">A Navigációs ablaktáblán válassza a **Modulok > Kötelezettségek > Szállítók > Összes beszállító** elemet.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="1f2c6-107">A kívánt rekord megkeresése és kijelölése az **Összes beszállító** listában.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="1f2c6-108">A Művelet ablaktáblán válassza ki az **Általános** elemet.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="1f2c6-109">Válassza a **Vállalatközi** elemet.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="1f2c6-110">A vállalatközi kereskedelem engedélyezéséhez az **Aktív** lehetőséget állítsa **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="1f2c6-111">A **Vevő vállalat** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="1f2c6-112">A **Saját számla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="1f2c6-113">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-113">Select **Save**.</span></span>
9. <span data-ttu-id="1f2c6-114">A kezdőlaphoz való visszatéréshez zárja be az oldalakat.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="1f2c6-115">A navigációs ablaktáblán menjen ide: **Modulok > Projektvezetés és könyvelés > Beállítás > Projektvezetés és könyvelés paraméterei**.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="1f2c6-116">Válassza ki a **Vállalatközi** lapot.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="1f2c6-117">Mozgassa a csúszkát az **Igen** lehetőséghez a vállalatközi erőforrás-ütemezés és időnyilvántartások engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="1f2c6-118">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="1f2c6-119">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-119">Select **New**.</span></span>
15. <span data-ttu-id="1f2c6-120">A **Kölcsönbe vevő jogi személy** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="1f2c6-121">Jelölje be az **Elhatárolt bevétel** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="1f2c6-122">Adjon meg vagy válasszon ki egy értéket az **Alapértelmezett időnyilvántartás-kategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="1f2c6-123">Adjon meg vagy válasszon ki egy értéket az **Alapértelmezett kiadáskategória** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="1f2c6-124">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-124">Select **Save**.</span></span>
20. <span data-ttu-id="1f2c6-125">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-125">Close the page.</span></span>
21. <span data-ttu-id="1f2c6-126">A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Feladás > Főkönyvi feladás beállítása** részre.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="1f2c6-127">Válasszon egy lehetőséget a **Főkönyvtípusok** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="1f2c6-128">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-128">Select **New**.</span></span>
24. <span data-ttu-id="1f2c6-129">Az új sor **Fő számla** mezőjében adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="1f2c6-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-130">Select **Save**.</span></span>
26. <span data-ttu-id="1f2c6-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-131">Close the page.</span></span>
27. <span data-ttu-id="1f2c6-132">A navigációs ablakban lépjen a **Modulok > Projektvezetés és könyvelés > Beállítás > Árak > Transzferár** részre.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="1f2c6-133">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-133">Select **New**.</span></span>
29. <span data-ttu-id="1f2c6-134">Adja meg a dátumot az **Érvényesség dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="1f2c6-135">A **Kölcsönbe vevő jogi személy** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="1f2c6-136">Válasszon egy lehetőséget a **Transzferármodell** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="1f2c6-137">Adjon meg egy számot az **Árazás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="1f2c6-138">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f2c6-138">Select **Save**.</span></span>

