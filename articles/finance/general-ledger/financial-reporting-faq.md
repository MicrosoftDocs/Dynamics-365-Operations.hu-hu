---
title: Pénzügyi jelentéskészítés – GYIK
description: Ebben a témakörben más felhasználóknál a pénzügyi jelentéskészítéssel kapcsolatban felmerült kérdésekre adunk választ.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2d49213ea18e09f04b026559bdca49fee1de0ef7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249304"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="dfa12-103">Pénzügyi jelentéskészítés – GYIK</span><span class="sxs-lookup"><span data-stu-id="dfa12-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="dfa12-104">Ebben a témakörben más felhasználóknál a pénzügyi jelentéskészítéssel kapcsolatban felmerült kérdésekre adunk választ.</span><span class="sxs-lookup"><span data-stu-id="dfa12-104">This topic lists questions related to financial reporting that other users have had.</span></span> 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="dfa12-105">Hogyan lehet korlátozni a jelentésekhez való hozzáférést a Fa biztonsági beállítással?</span><span class="sxs-lookup"><span data-stu-id="dfa12-105">How do I restrict access to a report using Tree security?</span></span>

<span data-ttu-id="dfa12-106">Eset: Az USMF bemutatóvállalat mérlegkimutatás készít, és nem szeretné, hogy a pénzügyi jelentéskészítési funkció minden felhasználója megtekinthesse a kimutatást a D365-ben.</span><span class="sxs-lookup"><span data-stu-id="dfa12-106">Scenario: The USMF demo company has a Balance sheet report that it doesn’t want all Financial reporting users to be able to view in D365.</span></span> <span data-ttu-id="dfa12-107">Megoldás: A Fa biztonsági beállítással korlátozhatja az adott jelentéshez való hozzáférést, amelyet így csak bizonyos felhasználók érhetnek el.</span><span class="sxs-lookup"><span data-stu-id="dfa12-107">Solution: You can utilize Tree security to restrict access to a single report so that only certain users can access the report.</span></span> 

1.  <span data-ttu-id="dfa12-108">Jelentkezzen be a Pénzügyi jelentés – Jelentéstervező alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="dfa12-108">Log into Financial Reporter Report Designer</span></span>

2.  <span data-ttu-id="dfa12-109">Hozzon létre egy új fadefiníciót (Fájl | Új | Fadefiníció). a.</span><span class="sxs-lookup"><span data-stu-id="dfa12-109">Create a new Tree Definition (File | New | Tree Definition) a.</span></span>    <span data-ttu-id="dfa12-110">Kattintson duplán az **Összegzés** sorra az **Egység biztonsága** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="dfa12-110">Double-click the **Summary** line in the **Unit Security** column.</span></span>
  <span data-ttu-id="dfa12-111">i.</span><span class="sxs-lookup"><span data-stu-id="dfa12-111">i.</span></span>    <span data-ttu-id="dfa12-112">Kattintson a Felhasználók és csoportok elemre.</span><span class="sxs-lookup"><span data-stu-id="dfa12-112">Click Users and Groups.</span></span>  
          <span data-ttu-id="dfa12-113">1. Válassza ki azokat a felhasználókat vagy csoportokat, amelyeknek szeretne hozzáférést adni a jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="dfa12-113">1.    Select the User(s) or Group that would like to access this report.</span></span> 
          
<span data-ttu-id="dfa12-114">[![felhasználói képernyő](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-114">[![user screen](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span></span>

<span data-ttu-id="dfa12-115">[![biztonsági képernyő](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span><span class="sxs-lookup"><span data-stu-id="dfa12-115">[![security screen](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span></span>

  <span data-ttu-id="dfa12-116">b.</span><span class="sxs-lookup"><span data-stu-id="dfa12-116">b.</span></span>    <span data-ttu-id="dfa12-117">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="dfa12-117">Click **Save**.</span></span>
  
<span data-ttu-id="dfa12-118">[![mentés gomb](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-118">[![save button](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span></span>

3.  <span data-ttu-id="dfa12-119">A Jelentésdefiníció résznél adja meg az új fadefiníciót.</span><span class="sxs-lookup"><span data-stu-id="dfa12-119">In your Report Definition add your new Tree Definition</span></span>

<span data-ttu-id="dfa12-120">[![fadefiníció űrlapja](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span><span class="sxs-lookup"><span data-stu-id="dfa12-120">[![tree definition form](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span></span>

<span data-ttu-id="dfa12-121">A.</span><span class="sxs-lookup"><span data-stu-id="dfa12-121">A.</span></span>  <span data-ttu-id="dfa12-122">A fadefinícióban kattintson a Beállítás elemre, és a „Jelentési egység kiválasztása” résznél jelölje be „Az összes egységgel együtt” jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="dfa12-122">While in the Tree Definition click on Setting and under “Reporting unit selection” check “Include all units”</span></span>

<span data-ttu-id="dfa12-123">[![jelentési egység kiválasztása űrlap](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span><span class="sxs-lookup"><span data-stu-id="dfa12-123">[![reporting unit selection form](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span></span>

<span data-ttu-id="dfa12-124">**Előtte:** [![előtte képernyőkép](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-124">**Before:** [![before screenshot](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span></span>

<span data-ttu-id="dfa12-125">**Utána:** [![utána képernyőkép](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-125">**After:** [![after screenshot](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span></span>

<span data-ttu-id="dfa12-126">Megjegyzés: A fenti üzenet oka az, hogy a felhasználónak az Egység biztonsága alkalmazása után nincs hozzáférése a jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="dfa12-126">Note: Reason for the above message is my user does not have access to that report after applying Unit Security</span></span>



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a><span data-ttu-id="dfa12-127">Hogyan tudom meghatározni, hogy mely számlák nem egyeznek meg az egyenlegeimmel a D365-ben?</span><span class="sxs-lookup"><span data-stu-id="dfa12-127">How do I determine which account(s) do not matching my balances in D365?</span></span>

<span data-ttu-id="dfa12-128">Ha a jelentés értékei nem egyeznek a D365-ben várt értékekkel, az alábbi lépésekkel azonosíthatja az ilyen számlákat, valamint az eltéréseket.</span><span class="sxs-lookup"><span data-stu-id="dfa12-128">When you have a report that doesn't match what you would expect in D365, here are some steps you could take to identify those accounts and the variances.</span></span> 

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="dfa12-129">A Pénzügyi jelentés – Jelentéstervező alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="dfa12-129">In Financial Reporter Report Designer</span></span>

1.  <span data-ttu-id="dfa12-130">Hozzon létre egy új sordefiníciót. a.</span><span class="sxs-lookup"><span data-stu-id="dfa12-130">Create a new Row Definition a.</span></span>    <span data-ttu-id="dfa12-131">Kattintson a Szerkesztés | Sorok beszúrása dimenziókból lehetőségre. i.</span><span class="sxs-lookup"><span data-stu-id="dfa12-131">Click Edit | Insert Rows from Dimensions i.</span></span>  <span data-ttu-id="dfa12-132">Válassza a MainAccount lehetőséget [![Válassza a Főképernyő lehetőséget_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-132">Select MainAccount [![Select Main screen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span></span>
    
    <span data-ttu-id="dfa12-133">ii.</span><span class="sxs-lookup"><span data-stu-id="dfa12-133">ii.</span></span> <span data-ttu-id="dfa12-134">Kattintson az OK gombra. b.</span><span class="sxs-lookup"><span data-stu-id="dfa12-134">Click Ok b.</span></span>    <span data-ttu-id="dfa12-135">Mentse a sordefiníciót.</span><span class="sxs-lookup"><span data-stu-id="dfa12-135">Save the Row Definition</span></span>

2.  <span data-ttu-id="dfa12-136">Hozzon létre új oszlopdefiníciót.     [![Hozzon létre új oszlopdefiníciót](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-136">Create a new Column Definition     [![Create a new column definition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span></span>

3.  <span data-ttu-id="dfa12-137">Hozzon létre új jelentésdefiníciót. a.</span><span class="sxs-lookup"><span data-stu-id="dfa12-137">Create a new Report Definition a.</span></span>    <span data-ttu-id="dfa12-138">Kattintson a Beállítások gombra, és törölje a következőt: [![Beállítási űrlap](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-138">Click Settings and uncheck [![Settings form](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span></span>
   
4.  <span data-ttu-id="dfa12-139">Hozza létre a jelentést.</span><span class="sxs-lookup"><span data-stu-id="dfa12-139">Generate the Report.</span></span> 

5.  <span data-ttu-id="dfa12-140">Exportálja a jelentést Excelbe.</span><span class="sxs-lookup"><span data-stu-id="dfa12-140">Export the Report to Excel.</span></span>

### <a name="in-d365"></a><span data-ttu-id="dfa12-141">A D365-ben:</span><span class="sxs-lookup"><span data-stu-id="dfa12-141">In D365:</span></span> 
1.  <span data-ttu-id="dfa12-142">Kattintson a Főkönyv | Lekérdezések és jelentések | Főkönyvi kivonat lehetőségre. a.</span><span class="sxs-lookup"><span data-stu-id="dfa12-142">Click General Ledger | Inquiries and Reports | Trial Balance a.</span></span>    <span data-ttu-id="dfa12-143">Paraméterek. i.</span><span class="sxs-lookup"><span data-stu-id="dfa12-143">Parameters i.</span></span>  <span data-ttu-id="dfa12-144">Kezdő dátum: a pénzügyi év kezdete. ii.</span><span class="sxs-lookup"><span data-stu-id="dfa12-144">From Date: Start of Fiscal Year ii.</span></span> <span data-ttu-id="dfa12-145">Záró dátum: a jelentés létrehozásának dátuma. iii.</span><span class="sxs-lookup"><span data-stu-id="dfa12-145">To Date: Date you generated the report for iii.</span></span>    <span data-ttu-id="dfa12-146">Pénzügyi dimenziókészlet, „Fő számlakészet” [![Fő számla űrlapja](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span><span class="sxs-lookup"><span data-stu-id="dfa12-146">Financial Dimension Set “Main Account set” [![Main Account Form](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span></span>
      
  <span data-ttu-id="dfa12-147">b.</span><span class="sxs-lookup"><span data-stu-id="dfa12-147">b.</span></span>    <span data-ttu-id="dfa12-148">Kattintson a Számítás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dfa12-148">Click Calculate</span></span>

2.  <span data-ttu-id="dfa12-149">Exportálja a jelentést Excelbe.</span><span class="sxs-lookup"><span data-stu-id="dfa12-149">Export the report to Excel</span></span>

<span data-ttu-id="dfa12-150">Most már a D365 főkönyvi kivonati jelentésébe másolhatja az Excelben létrehozott pénzügyi jelentés, és összehasonlíthatja a „Záró egyenleg” oszlopokat.</span><span class="sxs-lookup"><span data-stu-id="dfa12-150">You should now be able to copy the data from the FR Excel Report and to the D365 Trial Balance report and compare the “Closing Balance” columns.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]