---
title: Pénzügyi jelentéskészítés – GYIK
description: Ez a témakör a pénzügyi jelentéskészítéssel kapcsolatos néhány gyakran ismételt kérdésre ad választ.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266633"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="d57d3-103">Pénzügyi jelentéskészítés – GYIK</span><span class="sxs-lookup"><span data-stu-id="d57d3-103">Financial reporting FAQ</span></span>

<span data-ttu-id="d57d3-104">Ez a témakör a pénzügyi jelentéskészítéssel kapcsolatos gyakran ismételt kérdésekre ad választ.</span><span class="sxs-lookup"><span data-stu-id="d57d3-104">This topic provides answers to frequently asked questions about Financial reporting.</span></span>

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a><span data-ttu-id="d57d3-105">Hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítás használatával?</span><span class="sxs-lookup"><span data-stu-id="d57d3-105">How do I restrict access to a report by using tree security?</span></span>

<span data-ttu-id="d57d3-106">A következő példák bemutatják, hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítás használatával.</span><span class="sxs-lookup"><span data-stu-id="d57d3-106">The following example shows how to restrict access to a report by using tree security.</span></span>

<span data-ttu-id="d57d3-107">Az USMF bemutatóvállalat **mérlegkimutatást** készít, amelyhez a pénzügyi jelentéskészítési funkció nem minden felhasználójának kellene hozzáférnie.</span><span class="sxs-lookup"><span data-stu-id="d57d3-107">The USMF demo company has a **Balance sheet** report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="d57d3-108">A fa biztonsági beállítással korlátozhatja az adott jelentéshez való hozzáférést, amelyet így csak bizonyos felhasználók érhetnek el.</span><span class="sxs-lookup"><span data-stu-id="d57d3-108">You can use tree security to restrict access to a single report so that only specific users can access it.</span></span>

1. <span data-ttu-id="d57d3-109">Bejelentkezés a Financial Reporter Report Designer alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="d57d3-109">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="d57d3-110">Válassza a **Fájl \> Új \> Fadefiníció** lehetőséget egy új fadefiníció létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d57d3-110">Select **File \> New \> Tree Definition** to create a new tree definition.</span></span>
3. <span data-ttu-id="d57d3-111">Koppintson duplán (vagy kattintson duplán) az **Összegzés** sorra az **Egység biztonsága** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="d57d3-111">Double-tap (or double-click) the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="d57d3-112">Válassza ki a **Felhasználók és csoportok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-112">Select **Users and Groups**.</span></span>
5. <span data-ttu-id="d57d3-113">Válassza ki azokat a felhasználókat vagy csoportokat, amelyeknek hozzá kell férnie a jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="d57d3-113">Select the users or groups that require access to the report.</span></span>
6. <span data-ttu-id="d57d3-114">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-114">Select **Save**.</span></span>
7. <span data-ttu-id="d57d3-115">A jelentésdefinícióban adja meg az új fadefiníciót.</span><span class="sxs-lookup"><span data-stu-id="d57d3-115">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="d57d3-116">A fadefinícióban válassza ki a **Beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-116">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="d57d3-117">Majd a **Jelentési egység kiválasztása** pont alatt válassza az **Összes egységgel együtt** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-117">Then, under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a><span data-ttu-id="d57d3-118">Hogyan tudom meghatározni, hogy mely számlák nem egyeznek meg az egyenlegeimmel?</span><span class="sxs-lookup"><span data-stu-id="d57d3-118">How do I identify which accounts don't match my balances?</span></span>

<span data-ttu-id="d57d3-119">Ha a jelentés egyenlegei nem egyeznek meg, az alábbi eljárásokkal azonosíthatja a számlát és az eltérést.</span><span class="sxs-lookup"><span data-stu-id="d57d3-119">If you have a report that doesn't have matching balances, use the following procedures to identify each account and variance.</span></span>

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="d57d3-120">Itt: Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="d57d3-120">In Financial Reporter Report Designer</span></span>

1. <span data-ttu-id="d57d3-121">Hozzon létre egy új sordefiníciót.</span><span class="sxs-lookup"><span data-stu-id="d57d3-121">Create a new row definition.</span></span>
2. <span data-ttu-id="d57d3-122">Válassza ki a **Szerkesztés \> Sorok beszúrása dimenziókból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-122">Select **Edit \> Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="d57d3-123">Válassza ki a **Főszámla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-123">Select **MainAccount**.</span></span>
4. <span data-ttu-id="d57d3-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-124">Select **OK**.</span></span>
5. <span data-ttu-id="d57d3-125">Mentse a sordefiníciót.</span><span class="sxs-lookup"><span data-stu-id="d57d3-125">Save the row definition.</span></span>
6. <span data-ttu-id="d57d3-126">Hozzon létre egy új oszlopdefiníciót.</span><span class="sxs-lookup"><span data-stu-id="d57d3-126">Create a new column definition.</span></span>
7. <span data-ttu-id="d57d3-127">Hozzon létre új jelentésdefiníciót.</span><span class="sxs-lookup"><span data-stu-id="d57d3-127">Create a new report definition.</span></span>
8. <span data-ttu-id="d57d3-128">Válassza ki a **Beállítások** lehetőséget és törölje az opció kijelölését.</span><span class="sxs-lookup"><span data-stu-id="d57d3-128">Select **Settings** and unmark this option.</span></span>
9. <span data-ttu-id="d57d3-129">Hozza létre a jelentést.</span><span class="sxs-lookup"><span data-stu-id="d57d3-129">Generate the report.</span></span> 
10. <span data-ttu-id="d57d3-130">Exportálja a jelentést a Microsoft Excel szoftverbe.</span><span class="sxs-lookup"><span data-stu-id="d57d3-130">Export the report to Microsoft Excel.</span></span>

### <a name="in-dynamics-365-finance"></a><span data-ttu-id="d57d3-131">Itt: Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="d57d3-131">In Dynamics 365 Finance</span></span>

1. <span data-ttu-id="d57d3-132">Lépjen a **Főkönyv \> Lekérdezések és jelentések \> Főkönyvi kivonat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d57d3-132">Go to **General ledger \> Inquiries and reports \> Trial balance**.</span></span>
2. <span data-ttu-id="d57d3-133">Állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="d57d3-133">Set the following fields:</span></span>

    - <span data-ttu-id="d57d3-134">**Kezdő dátum** – Adja meg a pénzügyi év kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="d57d3-134">**From Date** – Enter the start date of the fiscal year.</span></span>
    - <span data-ttu-id="d57d3-135">**Záró dátum** – Adja meg a dátumot, amelyhez létrehozza a jelentést.</span><span class="sxs-lookup"><span data-stu-id="d57d3-135">**To Date** – Enter the date that you're generating the report for.</span></span>
    - <span data-ttu-id="d57d3-136">**Pénzügyi dimenzió** – Állítsa ezt a mezőt a **Fő számlakészlet** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d57d3-136">**Financial Dimension** – Set this field to **Main Account set**.</span></span>

3. <span data-ttu-id="d57d3-137">Válassza ki a **Számítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d57d3-137">Select **Calculate**.</span></span>
4. <span data-ttu-id="d57d3-138">Exportálja a jelentést Excelbe.</span><span class="sxs-lookup"><span data-stu-id="d57d3-138">Export the report to Excel.</span></span>

<span data-ttu-id="d57d3-139">Most már a **főkönyvi kivonati** jelentésbe másolhatja az Excelben létrehozott pénzügyi jelentést, hogy összehasonlítsa a **Záró egyenleg** oszlopokat.</span><span class="sxs-lookup"><span data-stu-id="d57d3-139">You should now be able to copy the data from the Financial Reporter Excel report to the **Trial Balance** report, so that you can compare the **Closing Balance** columns.</span></span>

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a><span data-ttu-id="d57d3-140">Amikor jelentést tervezek a Report Designerben, vagy amikor pénzügyi jelentést készítek, a következő üzenet jelenik meg: „A műveletet nem lehet végrehajtani az adatszolgáltató keretrendszerében fellépő probléma miatt.”</span><span class="sxs-lookup"><span data-stu-id="d57d3-140">When I design a report in Report Designer, or when I generate a financial report, I received the following message: "The operation could not be completed due to a problem in the data provider framework."</span></span> <span data-ttu-id="d57d3-141">Hogyan reagáljak rá?</span><span class="sxs-lookup"><span data-stu-id="d57d3-141">How should I respond?</span></span>

<span data-ttu-id="d57d3-142">Az üzenet azt jelzi, hogy hiba történt, amikor a rendszer megpróbálta lekérni a pénzügyi metaadatokat az adatpiacról a Pénzügyi jelentéskészítés használata közben.</span><span class="sxs-lookup"><span data-stu-id="d57d3-142">The message indicates that an issue occurred when the system tried to retrieve financial metadata from the data mart while you were using Financial reporting.</span></span> <span data-ttu-id="d57d3-143">Erre a problémára kétféleképpen tud reagálni:</span><span class="sxs-lookup"><span data-stu-id="d57d3-143">There are two ways to respond to this issue:</span></span>

- <span data-ttu-id="d57d3-144">Tekintse át az adatok integrációs állapotát a Report Designerben lévő **Eszközök \> Integráció állapota** segítségével.</span><span class="sxs-lookup"><span data-stu-id="d57d3-144">Review the integration status of the data by going to **Tools \> Integration status** in Report Designer.</span></span> <span data-ttu-id="d57d3-145">Ha az integráció még nem fejeződött be, várjon, amíg befejeződik.</span><span class="sxs-lookup"><span data-stu-id="d57d3-145">If the integration is incomplete, wait for it to be completed.</span></span> <span data-ttu-id="d57d3-146">Ezután próbálja meg újra elvégezni azt, amit az üzenet megjelenésekor szeretett volna.</span><span class="sxs-lookup"><span data-stu-id="d57d3-146">Then retry what you were doing when you received the message.</span></span>
- <span data-ttu-id="d57d3-147">Forduljon az ügyfélszolgálathoz a probléma azonosítása és megoldása érdekében.</span><span class="sxs-lookup"><span data-stu-id="d57d3-147">Contact Support to identify and work through the issue.</span></span> <span data-ttu-id="d57d3-148">Inkonzisztens adatok lehetnek a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="d57d3-148">There might be inconsistent data in the system.</span></span> <span data-ttu-id="d57d3-149">A támogatási szakemberek segítséget tudnak nyújtani a kiszolgálón lévő probléma azonosításában, és a frissítéshez szükséges konkrét adatok megkeresésében.</span><span class="sxs-lookup"><span data-stu-id="d57d3-149">Support engineers can help you identify that issue on the server and find the specific data that might require an update.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
