---
title: Pénzügyi jelentéskészítés – GYIK
description: Ebben a témakörben más felhasználóknál a pénzügyi jelentéskészítéssel kapcsolatban felmerült kérdésekre adunk választ.
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
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923025"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="dd82e-103">Pénzügyi jelentéskészítés – GYIK</span><span class="sxs-lookup"><span data-stu-id="dd82e-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="dd82e-104">Ez a témakör a pénzügyi jelentéskészítéssel kapcsolatos gyakran ismételt kérdésekre ad választ.</span><span class="sxs-lookup"><span data-stu-id="dd82e-104">This topic provides answers to frequently asked questions about financial reporting.</span></span> 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="dd82e-105">Hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítással?</span><span class="sxs-lookup"><span data-stu-id="dd82e-105">How do I restrict access to a report using tree security?</span></span>

<span data-ttu-id="dd82e-106">A következő példák bemutatják, hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítással.</span><span class="sxs-lookup"><span data-stu-id="dd82e-106">The following example shows how to restrict access to a report using tree security.</span></span>

<span data-ttu-id="dd82e-107">Az USMF bemutatóvállalat mérlegkimutatás készít, amelyhez a pénzügyi jelentéskészítési funkció nem minden felhasználójának kellene hozzáférnie.</span><span class="sxs-lookup"><span data-stu-id="dd82e-107">The USMF demo company has a Balance sheet report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="dd82e-108">A hozzáférés korlátozása érdekében a fa biztonsági beállítással korlátozhatja az adott jelentéshez való hozzáférést, amelyet így csak bizonyos felhasználók érhetnek el.</span><span class="sxs-lookup"><span data-stu-id="dd82e-108">To restrict access, you can use tree security to restrict access to a single report so that only certain users can access the report.</span></span> <span data-ttu-id="dd82e-109">A hozzáférés korlátozásához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="dd82e-109">Follow these steps to restrict access:</span></span> 

1. <span data-ttu-id="dd82e-110">Jelentkezzen be a Pénzügyi jelentés – Jelentéstervező alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="dd82e-110">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="dd82e-111">Hozzon létre új fadefiníciót.</span><span class="sxs-lookup"><span data-stu-id="dd82e-111">Create a new tree definition.</span></span> <span data-ttu-id="dd82e-112">Lépjen a **Fájl > Új > Fadefiníció** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dd82e-112">Go to **File > New > Tree Definition**.</span></span>
3. <span data-ttu-id="dd82e-113">Kattintson duplán az **Összegzés** sorra az **Egység biztonsága** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="dd82e-113">Double-click the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="dd82e-114">Válassza ki a **Felhasználók és csoportok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-114">Select **Users and Groups**.</span></span>  
5. <span data-ttu-id="dd82e-115">Válassza ki azokat a felhasználókat vagy csoportokat, amelyeknek hozzá kell férnie ehhez a jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="dd82e-115">Select the users or groups that need access to this report.</span></span> 
6. <span data-ttu-id="dd82e-116">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-116">Select **Save**.</span></span>
7. <span data-ttu-id="dd82e-117">A jelentésdefinícióban adja meg az új fadefiníciót.</span><span class="sxs-lookup"><span data-stu-id="dd82e-117">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="dd82e-118">A fadefinícióban válassza ki a **Beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-118">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="dd82e-119">A **Jelentési egység kiválasztása** pont alatt válassza az **Összes egységgel együtt** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-119">Under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a><span data-ttu-id="dd82e-120">Hogyan tudom meghatározni, hogy mely számlák nem egyeznek meg az egyenlegeimmel?</span><span class="sxs-lookup"><span data-stu-id="dd82e-120">How do I identify which accounts do not match my balances?</span></span>

<span data-ttu-id="dd82e-121">Ha a jelentés egyenlegei nem egyeznek meg, az alábbi lépésekkel azonosíthatja a számlákat és az eltéréseket.</span><span class="sxs-lookup"><span data-stu-id="dd82e-121">If you have a report that doesn't have matching balances, here are some steps you can take to identify each of the accounts and variances.</span></span> 

<span data-ttu-id="dd82e-122">**A Pénzügyi jelentés – Jelentéstervező alkalmazás**</span><span class="sxs-lookup"><span data-stu-id="dd82e-122">**Financial Reporter Report Designer**</span></span>
1. <span data-ttu-id="dd82e-123">A Pénzügyi jelentés – Jelentéstervező alkalmazásban hozzon létre egy új sordefiníciót.</span><span class="sxs-lookup"><span data-stu-id="dd82e-123">In Financial Reporter Report Designer, create a new row definition.</span></span> 
2. <span data-ttu-id="dd82e-124">Válassza ki a **Szerkesztés > Sorok beszúrása dimenziókból** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-124">Select **Edit > Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="dd82e-125">Válassza ki a **Főszámla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-125">Select **MainAccount**.</span></span>  
4. <span data-ttu-id="dd82e-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-126">Select **OK**.</span></span>
5. <span data-ttu-id="dd82e-127">Mentse a sordefiníciót.</span><span class="sxs-lookup"><span data-stu-id="dd82e-127">Save the row definition.</span></span>
6. <span data-ttu-id="dd82e-128">Hozzon létre egy új oszlopdefiníciót</span><span class="sxs-lookup"><span data-stu-id="dd82e-128">Create a new column definition</span></span>
7. <span data-ttu-id="dd82e-129">Hozzon létre új jelentésdefiníciót.</span><span class="sxs-lookup"><span data-stu-id="dd82e-129">Create a new report definition.</span></span>
8. <span data-ttu-id="dd82e-130">Válassza ki a **Beállítások** lehetőséget és törölje az opció kijelölését.</span><span class="sxs-lookup"><span data-stu-id="dd82e-130">Select **Settings** and unmark this option.</span></span>  
9. <span data-ttu-id="dd82e-131">Hozza létre a jelentést.</span><span class="sxs-lookup"><span data-stu-id="dd82e-131">Generate the report.</span></span> 
10. <span data-ttu-id="dd82e-132">Exportálja a jelentést a Microsoft Excel szoftverbe.</span><span class="sxs-lookup"><span data-stu-id="dd82e-132">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="dd82e-133">**Dynamics 365 Finance**</span><span class="sxs-lookup"><span data-stu-id="dd82e-133">**Dynamics 365 Finance**</span></span> 
1. <span data-ttu-id="dd82e-134">A Dynamics 365 Finance szolgáltatásban lépjen a **Főkönyv > Lekérdezések és jelentések > Főkönyvi kivonat** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dd82e-134">In Dynamics 365 Finance, go to **General Ledger > Inquiries and Reports > Trial Balance**.</span></span>
2. <span data-ttu-id="dd82e-135">A következő paraméterek beállítása:</span><span class="sxs-lookup"><span data-stu-id="dd82e-135">Set the following parameters:</span></span>
   - <span data-ttu-id="dd82e-136">**Kezdő dátum** – Adja meg a pénzügyi év kezdetét.</span><span class="sxs-lookup"><span data-stu-id="dd82e-136">**From Date** - Enter the start of the fiscal year.</span></span>
   - <span data-ttu-id="dd82e-137">**Záró dátum** – Adja meg a dátumot, amelyhez létrehozza a jelentést.</span><span class="sxs-lookup"><span data-stu-id="dd82e-137">**To Date** - Enter the date you are generating the report for.</span></span>
   - <span data-ttu-id="dd82e-138">**Pénzügyi dimenzió** – Állítsa ezt a mezőt a **Fő számlakészet** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dd82e-138">**Financial Dimension** - Set this field to **Main Account set**.</span></span>
 3. <span data-ttu-id="dd82e-139">Válassza ki a **Számítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dd82e-139">Select **Calculate**.</span></span>
 4. <span data-ttu-id="dd82e-140">Exportálja a jelentést a Microsoft Excel szoftverbe.</span><span class="sxs-lookup"><span data-stu-id="dd82e-140">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="dd82e-141">Most már a főkönyvi kivonati jelentésbe másolhatja az Excelben létrehozott pénzügyi jelentést, hogy összehasonlítsa a **Záró egyenleg** oszlopokat.</span><span class="sxs-lookup"><span data-stu-id="dd82e-141">You should now be able to copy the data from the Financial Reporter Excel report to the Trial Balance report, so you can compare the **Closing Balance** columns.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]