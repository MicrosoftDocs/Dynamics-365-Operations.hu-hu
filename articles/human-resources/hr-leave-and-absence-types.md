---
title: Szabadság- és távolléttípusok konfigurálása
description: Beállíthatja, hogy az alkalmazottak milyen típusú szabadságot vehetnek igénybe a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1802938f54a1d78e6ea60572a76177a037192ae0
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428593"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="e5824-103">Szabadság- és távolléttípusok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e5824-103">Configure leave and absence types</span></span>

<span data-ttu-id="e5824-104">A Dynamics 365 Human Resources szabadságtípusai határozzák meg az alkalmazottak számára elérhető különböző típusú távolléteket.</span><span class="sxs-lookup"><span data-stu-id="e5824-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="e5824-105">A szabadságtípusokat a szervezet igényeihez igazíthatja.</span><span class="sxs-lookup"><span data-stu-id="e5824-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="e5824-106">Példák a szabadságtípusokra:</span><span class="sxs-lookup"><span data-stu-id="e5824-106">Examples of leave types include:</span></span>

- <span data-ttu-id="e5824-107">Fizetett szabadság (PTO)</span><span class="sxs-lookup"><span data-stu-id="e5824-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="e5824-108">Fizetés nélküli szabadság</span><span class="sxs-lookup"><span data-stu-id="e5824-108">Unpaid leave</span></span>
- <span data-ttu-id="e5824-109">Fizetett szabadság</span><span class="sxs-lookup"><span data-stu-id="e5824-109">Paid vacation</span></span>
- <span data-ttu-id="e5824-110">Betegszabadság</span><span class="sxs-lookup"><span data-stu-id="e5824-110">Sick leave</span></span>
- <span data-ttu-id="e5824-111">Betegszabadság</span><span class="sxs-lookup"><span data-stu-id="e5824-111">Medical leave</span></span>
- <span data-ttu-id="e5824-112">Családi okokból történő</span><span class="sxs-lookup"><span data-stu-id="e5824-112">Family leave</span></span>
- <span data-ttu-id="e5824-113">Rövid távú fogyatékosság</span><span class="sxs-lookup"><span data-stu-id="e5824-113">Short-term disability</span></span>
- <span data-ttu-id="e5824-114">Haláleset miatti szabadság</span><span class="sxs-lookup"><span data-stu-id="e5824-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="e5824-115">Szabadságtípus hozzáadása</span><span class="sxs-lookup"><span data-stu-id="e5824-115">Add a leave type</span></span>

1. <span data-ttu-id="e5824-116">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="e5824-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="e5824-117">A **Beállítás**területen válassza a **Szabadság- és távolléttípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e5824-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="e5824-118">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e5824-118">Select **New**.</span></span>

4. <span data-ttu-id="e5824-119">Írjon be a szabadságtípus nevét a **Típus** mezőbe, válasszon egy munkafolyamatot a **Munkafolyamat-azonosító** listáról, és adja meg a leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e5824-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="e5824-120">Az **Általános** lapon válassza ki a **Nincs**, az **Ütemezett** vagy a **Nem ütemezett** elemet a **Kategória** legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="e5824-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="e5824-121">Válasszon bevételkódot a **Bevételkód** legördülő listáról.</span><span class="sxs-lookup"><span data-stu-id="e5824-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="e5824-122">**Az okkódot meg kell adni** beállításnál válassza ki, hogy szeretné-e előírni az okkód megadását.</span><span class="sxs-lookup"><span data-stu-id="e5824-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="e5824-123">Ha elő szeretné írni az okkódok használatát, akkor fel kell vennie ilyen kódokat.</span><span class="sxs-lookup"><span data-stu-id="e5824-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="e5824-124">Az **Okkódok** területen válassza a **Hozzáadás** elemet, válasszon egy okkódot, és jelölje be a mellette található **Engedélyezve** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="e5824-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="e5824-125">A **Hozzáférés korlátozása a kijelölt szerepkörökre** beállításnál válassza ki, hogy szeretné-e korlátozni a hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="e5824-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="e5824-126">Ezután a **Szabadságtípus biztonsági szerepkörei** beállításnál válassza ki a biztonsági szerepköröket.</span><span class="sxs-lookup"><span data-stu-id="e5824-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="e5824-127">A biztonsági szerepkörök a jelen eljárás korábbi pontján, a **Munkafolyamat-azonosító** beállításnál kiválasztott munkafolyamatban határozhatók meg.</span><span class="sxs-lookup"><span data-stu-id="e5824-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="e5824-128">A **Felfüggesztési kapcsolatok** alatt válassza ki, hogy szeretné, hogy ez a szabadságtípus felfüggesztene egy másik szabadságtípust, vagy ezt a szabadságtípust függesztené fel egy másik.</span><span class="sxs-lookup"><span data-stu-id="e5824-128">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="e5824-129">Ha egy szabadságkérelem kerül elküldésre a felfüggesztő szabadságtípusra, akkor egy szabadságfelfüggesztés automatikusan létrehozásra kerül a felfüggesztett szabadságléttípusra.</span><span class="sxs-lookup"><span data-stu-id="e5824-129">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="e5824-130">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e5824-130">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="e5824-131">A szabadságtípus-szabályok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e5824-131">Configure leave type rules</span></span>

1. <span data-ttu-id="e5824-132">Adja meg a szabadságtípus kerekítési beállításait.</span><span class="sxs-lookup"><span data-stu-id="e5824-132">Set rounding options for the leave type.</span></span> <span data-ttu-id="e5824-133">Választási lehetőségek: **Nincs**, **Fel**, **Le** és **Legközelebbi**.</span><span class="sxs-lookup"><span data-stu-id="e5824-133">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="e5824-134">A szabadságtípus kerekítési pontosságát is megadhatja.</span><span class="sxs-lookup"><span data-stu-id="e5824-134">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="e5824-135">Adja meg a szabadságtípus **Munkaszünet-korrekció** beállítását.</span><span class="sxs-lookup"><span data-stu-id="e5824-135">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="e5824-136">Ha bejelöli ezt a lehetőséget, akkor a Human Resources szolgáltatás a munkanapra eső napok száma alapján határozza meg, hogyan kell elszámolni a szabadságtípus távolléti idejét.</span><span class="sxs-lookup"><span data-stu-id="e5824-136">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="e5824-137">Ha például karácsony napja hétfőre esik, akkor a Human Resources szolgáltatás levon egy napot a szabadságtípusból a könyvelés feldolgozásakor.</span><span class="sxs-lookup"><span data-stu-id="e5824-137">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="e5824-138">A szabadnapokat a munkaidőnaptárban állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="e5824-138">You set holidays in the working time calendar.</span></span> <span data-ttu-id="e5824-139">További információ: [Munkaidőnaptár létrehozása](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="e5824-139">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="e5824-140">Állítsa be a szabadság típusaként az **Átvihető szabadságtípust**.</span><span class="sxs-lookup"><span data-stu-id="e5824-140">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="e5824-141">Ha ezt a lehetőséget választja, akkor az átvitt egyenlegek átkerülnek a megadott szabadságtípusba.</span><span class="sxs-lookup"><span data-stu-id="e5824-141">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="e5824-142">Az átvitt szabadságtípust is figyelembe kell venni a szabadság- és a távolléti tervben.</span><span class="sxs-lookup"><span data-stu-id="e5824-142">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="e5824-143">Adja meg a szabadságtípus **Lejárati szabályait**.</span><span class="sxs-lookup"><span data-stu-id="e5824-143">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="e5824-144">Ha beállítja ezt a lehetőséget, akkor a napok vagy hónapok egységét is megadhatja, és megadhatja a lejárat időtartamát.</span><span class="sxs-lookup"><span data-stu-id="e5824-144">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="e5824-145">Beállíthatja a lejárat szabályának érvényességi dátumát is.</span><span class="sxs-lookup"><span data-stu-id="e5824-145">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="e5824-146">A lejárati időpontokban meglévő szabadságegyenlegeket a szabadság típusából kivonja a program, és ez a szabadságegyenlegében tükröződik.</span><span class="sxs-lookup"><span data-stu-id="e5824-146">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
 
## <a name="see-also"></a><span data-ttu-id="e5824-147">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e5824-147">See also</span></span>

- [<span data-ttu-id="e5824-148">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="e5824-148">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="e5824-149">Szabadság- és távolléti terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="e5824-149">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="e5824-150">Munkaidőnaptár létrehozása</span><span class="sxs-lookup"><span data-stu-id="e5824-150">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="e5824-151">Szabadság felfüggesztése</span><span class="sxs-lookup"><span data-stu-id="e5824-151">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)

