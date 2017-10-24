---
title: "Költségvetési tervezés igazoló dokumentumai"
description: "Az igazoló dokumentumok háttérmagyarázatokat biztosítanak arra az esetre, ha valaki egy költségvetést kikérve rákérdez, miért van szükség az adott költségvetésre."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2e711b14b202d477bd3f4bda09977fd33979fc94
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="budget-planning-justification-documents"></a><span data-ttu-id="c8cd5-103">Költségvetési tervezés igazoló dokumentumai</span><span class="sxs-lookup"><span data-stu-id="c8cd5-103">Budget planning justification documents</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c8cd5-104">Az igazoló dokumentumok háttérmagyarázatokat biztosítanak arra az esetre, ha valaki egy költségvetést kikérve rákérdez, miért van szükség az adott költségvetésre.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="c8cd5-105">A költségvetés-kezelő Microsoft Wordben létrehoz egy költségvetésiterv-sablont, és azt hozzárendeli a jelenlegi költségvetés-tervezési folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="c8cd5-106">A költségvetés tulajdonosai ezt követően megnyithatják a sablont, és az adatokat automatikusan kitölthetik Wordben a költségvetési kérelmük alapján.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="c8cd5-107">Ezután további szöveget vagy adatokat adhatnak hozzá a személyre szabott igazló dokumentumok mentése és a költségvetési tervhez való csatolása előtt.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="c8cd5-108">A Microsoft Dynamics Office Microsoft Word-bővítményének beállítása</span><span class="sxs-lookup"><span data-stu-id="c8cd5-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="c8cd5-109">Nyisson meg egy új Microsoft Word-dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="c8cd5-110">Kattintson a **Beillesztés** elemre a szalagon, majd kattintson a **Tár** elemre.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="c8cd5-111">Keresse meg a Microsoft Dynamics Office bővítményt, és kattintson a **Hozzáadás** elemre.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="c8cd5-112">A Word programban a jobb oldali ablaktáblában kattintson a **Kiszolgáló adatainak hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="c8cd5-113">Írja be vagy illessze be a kiszolgáló URL-címét, majd kattintson a **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="c8cd5-114">Az indoklás sablon megadása Microsoft Wordben</span><span class="sxs-lookup"><span data-stu-id="c8cd5-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="c8cd5-115">Bejelentkezés után kattintson a **Tervezés** elemre a Microsoft Dynamics Office-bővítményben.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="c8cd5-116">A fejlécadatokhoz használja a **Mezők hozzáadása** gombot.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="c8cd5-117">Válassza ki a BudgetPlanJustification entitás-adatforrást, majd kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="c8cd5-118">**Megjegyzés:** erre az entitásra minden igazoló dokumentum esetén szükség van.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="c8cd5-119">Más entitások is használhatók, de a Microsoft Dynamics 365 for Finance and Operations, Enterprise editionbe való visszatöltés sikertelen lesz, ha ez az entitás nincs felvéve.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-119">Other entities can be used but the upload back to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="c8cd5-120">Adja hozzá a BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter és DocumentNumber címkéket és értékeket a Word-dokumentumban.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="c8cd5-121">**Megjegyzés:** szükség esetén használhatja saját egyéni címkéit a szabványos címkék helyett.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="c8cd5-122">Kattintson a **Kész** elemre a fejléc befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="c8cd5-123">A sorszintű részletes költségvetésiterv-összegekhez kattintson a **Tábla hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="c8cd5-124">Ismét válassza ki a BudgetPlanJustification entitás-adatforrást, majd kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="c8cd5-125">Adja hozzá az EffectiveDate, ScenarioName, AccountDisplayValue és AccountingCurrencyExpenseAmount elemekhez tartozó mezőket.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="c8cd5-126">**Megjegyzés:** ha megjegyzések elérhetők hozzáadásra az egyedi költségvetésiterv-sorokon belül, ezek itt adhatók hozzá a táblához.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="c8cd5-127">Adja hozzá a további utasításokat a végfelhasználó számára, és végezzen el minden szükséges formázást vagy stílusbeállítást a dokumentumon.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="c8cd5-128">Mentse el a dokumentumot a helyi számítógépre, és a folytatás előtt zárja be a fájlt.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="c8cd5-129">A költségvetés-tervezési folyamat beállítása az indoklási sablon használatára</span><span class="sxs-lookup"><span data-stu-id="c8cd5-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="c8cd5-130">A Finance and Operationsben lépjen a **Költségvetés készítése** &gt; **Beállítás** &gt; **Költségvetés-tervezés** &gt; **Igazoló dokumentum sablonjai** elemre.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-130">In Finance and Operations, go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="c8cd5-131">Kattintson a **Új** lehetőségre, és keresse meg az újonnan létrehozott Microsoft Word-dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="c8cd5-132">Adja meg a sablon megjelenítendő nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-132">Enter a template display name and description.</span></span> <span data-ttu-id="c8cd5-133">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-133">Click **OK**.</span></span>
4.  <span data-ttu-id="c8cd5-134">Lépjen a következőhöz: **Költségvetés-készítés** &gt; **Beállítás** &gt; **Költségvetés****-tervezés** &gt; **Költségvetés-tervezési folyamat**.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="c8cd5-135">Válassza ki a folyamatot, ahol az indoklási sablont használni kívánja, majd kattintson a **Szerkesztés** elemre.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="c8cd5-136">Az **Igazoló dokumentum sablonja** mezőben válassza ki a megfelelő sablont, és mentse el.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="c8cd5-137">Személyre szabott igazoló dokumentumok szerkesztése és mentése</span><span class="sxs-lookup"><span data-stu-id="c8cd5-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="c8cd5-138">A Finance and Operationsben hozzon létre egy új költségvetési tervet, vagy nyisson meg egy meglévő költségvetési tervet.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-138">In Finance and Operations, create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="c8cd5-139">Az **Indoklás** legördülő menüben válassza az **Új igazolás létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="c8cd5-140">Miután kitöltötte az adatokat, az **Indoklás** legördülő menüből töltse fel a személyre szabott dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="c8cd5-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>




