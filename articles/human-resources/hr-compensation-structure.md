---
title: Kompenzációs struktúra kialakítása
description: Ez a cikk végigvezeti a fix kompenzációs konstrukció létrehozásának és az alkalmazottak konstrukcióba való regisztrálásának folyamatán alkalmazhatósági szabályokon keresztül.
author: andreabichsel
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abdca618aa544e32b68f4bbf2578afb9ef1a5905
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052889"
---
# <a name="develop-a-compensation-structure"></a><span data-ttu-id="05cb6-103">Kompenzációs struktúra kialakítása</span><span class="sxs-lookup"><span data-stu-id="05cb6-103">Develop a compensation structure</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="05cb6-104">Ez a cikk végigvezeti a fix kompenzációs konstrukció létrehozásának és az alkalmazottak konstrukcióba való regisztrálásának folyamatán alkalmazhatósági szabályokon keresztül.</span><span class="sxs-lookup"><span data-stu-id="05cb6-104">This article walks you through creating a fixed compensation plan and enrolling employees in the plan through eligibility rules.</span></span> <span data-ttu-id="05cb6-105">Ez a cikk a USMF bemutató adatait használja, és a kompenzációs és juttatási vezetőket érinti.</span><span class="sxs-lookup"><span data-stu-id="05cb6-105">This article uses the USMF demo data and applies to Compensation and Benefits Managers.</span></span>

## <a name="create-a-fixed-compensation-plan"></a><span data-ttu-id="05cb6-106">Fix kompenzációs konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="05cb6-106">Create a fixed compensation plan</span></span>

1. <span data-ttu-id="05cb6-107">Válassza a **Kompenzációkezelés** pontot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-107">Select **Compensation management**.</span></span>

2. <span data-ttu-id="05cb6-108">Válassza a **Fix kompenzációs konstrukciók** elemet.</span><span class="sxs-lookup"><span data-stu-id="05cb6-108">Select **Fixed compensation plans**.</span></span>

3. <span data-ttu-id="05cb6-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05cb6-109">Select **New**.</span></span>

4. <span data-ttu-id="05cb6-110">A **Konstrukció** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-110">In the **Plan** field, enter a value.</span></span>

5. <span data-ttu-id="05cb6-111">A **Leírás** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-111">In the **Description** field, enter a value.</span></span>

6. <span data-ttu-id="05cb6-112">Adja meg a dátumot az **Érvényesség dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="05cb6-112">In the **Effective date** field, enter a date.</span></span>

7. <span data-ttu-id="05cb6-113">A **Típus** mezőben válassza ki, hogy a Fix kompenzációs konstrukció **Sáv**, **Osztály** vagy **Lépés** típusú konstrukció legyen.</span><span class="sxs-lookup"><span data-stu-id="05cb6-113">In the **Type** field, select whether the fixed compensation plan is a **Band**, **Grade**, or **Step** plan.</span></span>

8. <span data-ttu-id="05cb6-114">Az **Ajánlás engedélyezve** jelölőnégyzet alapértelmezett értékként viselkedik minden olyan műveletnél, amelyet ehhez konstrukcióhoz hozzáadtak a Feldolgozási eseményben.</span><span class="sxs-lookup"><span data-stu-id="05cb6-114">The **Recommendation allowed** checkbox acts as a default value for any actions added to this plan in a Process event.</span></span> <span data-ttu-id="05cb6-115">Az ajánlások engedélyezése lehetővé teszi, hogy a kiszámított irányösszeget a kompenzációs feldolgozásakor felülbírálhassa.</span><span class="sxs-lookup"><span data-stu-id="05cb6-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>

9. <span data-ttu-id="05cb6-116">**Tartományon kívüliség tűréshatára** mező lehetővé teszi, hogy megadja, hogyan szeretné kezelni a megadott kompenzációs struktúratartományon kívül eső kompenzációs összegeket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-116">The **Out of range tolerance** field allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span> <span data-ttu-id="05cb6-117">A **Tartományon kívüliség tűréshatár** mező **Egyik sem** értékre való állításával bármely kompenzációs összeget használhatja.</span><span class="sxs-lookup"><span data-stu-id="05cb6-117">Setting the **Out of range tolerance** field to **None** allows you to use any compensation amount.</span></span> <span data-ttu-id="05cb6-118">A **Puha tűréshatár** figyelmezteti a felhasználót, ha a kompenzáció összege kisebb, mint a minimális hivatkozási pont összege, vagy nagyobb, mint a maximális összege, az adott szint esetében.</span><span class="sxs-lookup"><span data-stu-id="05cb6-118">**Soft tolerance** warns users if the compensation amount is less than the minimum or greater than the maximum reference point amounts for that level.</span></span> <span data-ttu-id="05cb6-119">A felhasználók figyelmen kívül hagyhatják a figyelmeztetést és folytathatják a folyamatot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-119">Users can ignore the warning and continue.</span></span> <span data-ttu-id="05cb6-120">A **Kemény tűréshatár** hibát generál, ha az alkalmazott kompenzációja a minimális és maximális hivatkozási pontokon kívül van beállítva az adott szint esetében, és automatikusan korrigálja az alkalmazott kompenzációját, hogy az a tartományba essen.</span><span class="sxs-lookup"><span data-stu-id="05cb6-120">**Hard tolerance** generates an error if an employee's compensation is outside the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>

10. <span data-ttu-id="05cb6-121">A **Felvételi szabály** mező egy alkalmazott kompenzációját számítja ki a feldolgozási esemény során.</span><span class="sxs-lookup"><span data-stu-id="05cb6-121">The **Hire rule** field calculates an employee's compensation during a process event.</span></span> <span data-ttu-id="05cb6-122">A **Százalék** **Felvételi szabály** azt a növekedést számítja ki, amelyet arra az időszakra arányosítanak, amennyire a dolgozót a ciklusban alkalmazták.</span><span class="sxs-lookup"><span data-stu-id="05cb6-122">A **Hire rule** of **Percent** calculates an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>

11. <span data-ttu-id="05cb6-123">Érték beírása a **Pénznem** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="05cb6-123">In the **Currency** field, type a value.</span></span>

12. <span data-ttu-id="05cb6-124">A **Fizetési díjalap átalakítása** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-124">In the **Pay rate conversion** field, enter or select a value.</span></span>

13. <span data-ttu-id="05cb6-125">Bontsa ki a **Tartomány-kihasználtsági mátrix** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="05cb6-125">Expand the **Range utilization matrix** section.</span></span> <span data-ttu-id="05cb6-126">Tetszés szerint hozzáadhat tartománykihasználtsági rekordokat, hogy az alkalmazottak gyorsabban eljuthassanak a középső pontjukig, és lassabban érjék el tartományuk maximumát.</span><span class="sxs-lookup"><span data-stu-id="05cb6-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>

14. <span data-ttu-id="05cb6-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05cb6-127">Select **Save**.</span></span> <span data-ttu-id="05cb6-128">Ez lehetővé teszi a **Kompenzáció beállítása** gombot, és folytathatja a kompenzációs struktúra definiálását a konstrukcióhoz.</span><span class="sxs-lookup"><span data-stu-id="05cb6-128">This enables the **Set up compensation** button and continue defining your compensation structure for the plan.</span></span>

15. <span data-ttu-id="05cb6-129">Válassza a **Kompenzáció beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05cb6-129">Select **Set up compensation**.</span></span> <span data-ttu-id="05cb6-130">Kompenzációs struktúrát az alábbi három módszer egyikével hozhat létre:</span><span class="sxs-lookup"><span data-stu-id="05cb6-130">You can create a compensation structure by using one of these three methods:</span></span>

    - <span data-ttu-id="05cb6-131">Teljesen új struktúra létrehozása hivatkozási pontok csoportjának kiválasztásával és a szintek hozzáadásával saját struktúra létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="05cb6-131">Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span>
    - <span data-ttu-id="05cb6-132">Kompenzációs struktúra másolása egy kiindulási pontként szolgáló meglévő tervből, majd annak egy új tervre történő módosítása.</span><span class="sxs-lookup"><span data-stu-id="05cb6-132">Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span>
    - <span data-ttu-id="05cb6-133">Egy meglévő kompenzációs rács kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="05cb6-133">Select an existing compensation grid.</span></span> <span data-ttu-id="05cb6-134">Ha a kompenzációs rácsot már használja egy másik terv, a rácson végzett módosítások is megjelennek a másik tervben.</span><span class="sxs-lookup"><span data-stu-id="05cb6-134">If another plan already uses the compensation grid, the other plan also reflects any changes you make to the grid.</span></span>

16. <span data-ttu-id="05cb6-135">Válassza az **Új kompenzációs mátrix létrehozása egy meglévőből** elemet.</span><span class="sxs-lookup"><span data-stu-id="05cb6-135">Select **Create new from existing compensation matrix**.</span></span>

17. <span data-ttu-id="05cb6-136">A **Másolás rácsból** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-136">In the **Copy from grid** field, enter or select a value.</span></span> <span data-ttu-id="05cb6-137">Az új kompenzációs rács nevét tetszés szerint módosíthatja, amit a kiválasztott rács másolataként hoz létre.</span><span class="sxs-lookup"><span data-stu-id="05cb6-137">Optionally, you can change the name of the new compensation grid that you create by copying the selected grid.</span></span>

18. <span data-ttu-id="05cb6-138">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05cb6-138">Select **OK**.</span></span>

19. <span data-ttu-id="05cb6-139">Válassza a **Tömeges módosítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05cb6-139">Select **Mass change**.</span></span> <span data-ttu-id="05cb6-140">A **Tömeges módosítás** az egy vagy több szinthez vagy hivatkozási pontokhoz tartozó százalék- vagy fixösszegnövelés alkalmazása által lehetővé teszi a kompenzációs mátrix összegek karbantartását.</span><span class="sxs-lookup"><span data-stu-id="05cb6-140">**Mass change** allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels or reference points.</span></span>

20. <span data-ttu-id="05cb6-141">A **Kiigazítás összege** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-141">In the **Adjustment amount** field, enter a number.</span></span>

21. <span data-ttu-id="05cb6-142">A listában jelölje meg az összes sort, vagy törölje a jelölésüket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-142">In the list, mark or unmark all rows.</span></span>

22. <span data-ttu-id="05cb6-143">Kattintson az **Alkalmazás a rácsra** elemre.</span><span class="sxs-lookup"><span data-stu-id="05cb6-143">Click **Apply to grid**.</span></span>

23. <span data-ttu-id="05cb6-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-144">Close the page.</span></span> <span data-ttu-id="05cb6-145">A kompenzációs struktúra létrehozása után kiválaszthatja, hogy mely hivatkozási pontokat használja a Fix kompenzációs konstrukció Ellenőrzőpontjaként.</span><span class="sxs-lookup"><span data-stu-id="05cb6-145">After you create the compensation structure, you can select which of the reference points to use as the control point for the fixed compensation plan.</span></span> <span data-ttu-id="05cb6-146">Az ellenőrzőpont az alkalmazott Kompenzációs arányának kiszámítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="05cb6-146">The control point is used to calculate an employee's Compa Ratio.</span></span>

24. <span data-ttu-id="05cb6-147">Az **Ellenőrzőpont** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-147">In the **Control point** field, enter or select a value.</span></span>

25. <span data-ttu-id="05cb6-148">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a><span data-ttu-id="05cb6-149">Hozzon létre egy alkalmazhatósági szabályt az új fix kompenzációs konstrukcióhoz</span><span class="sxs-lookup"><span data-stu-id="05cb6-149">Create an eligibility rule for the fixed compensation plan</span></span>

<span data-ttu-id="05cb6-150">Az új fix kompenzációs konstrukció nem rendelhető alkalmazotthoz, amíg az alkalmazhatósági szabályokat nem határoztak meg a konstrukcióhoz.</span><span class="sxs-lookup"><span data-stu-id="05cb6-150">You can't assign a fixed compensation plan to an employee until you define eligibility rules for the plan.</span></span>  

1. <span data-ttu-id="05cb6-151">Válassa az **Alkalmazhatósági szabályok** pontot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-151">Select **Eligibility rules**.</span></span>

2. <span data-ttu-id="05cb6-152">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="05cb6-152">Select **New**.</span></span>

3. <span data-ttu-id="05cb6-153">Az **Alkalmazhatóság** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-153">In the **Eligibility** field, enter a value.</span></span>

4. <span data-ttu-id="05cb6-154">A **Leírás** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-154">In the **Description** field, enter a value.</span></span>

5. <span data-ttu-id="05cb6-155">Adja meg a dátumot az **Érvényesség dátuma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="05cb6-155">In the **Effective date** field, enter a date.</span></span> <span data-ttu-id="05cb6-156">Az alkalmazhatósági szabályok mind a fix, mind pedig a változó kompenzációs konstrukciókban használhatók.</span><span class="sxs-lookup"><span data-stu-id="05cb6-156">Both fixed and variable compensation plans use eligibility rules.</span></span> <span data-ttu-id="05cb6-157">A **Típus** mezőben válassza ki a konstrukció típusát.</span><span class="sxs-lookup"><span data-stu-id="05cb6-157">In the **Type** field, select the type of plan.</span></span>

6. <span data-ttu-id="05cb6-158">A **Terv** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="05cb6-158">In the **Plan** field, enter or select a value.</span></span> <span data-ttu-id="05cb6-159">Válassza ki azokat a feltételeket, amelyeknek egy alkalmazottnak meg kell felelnie annak érdekében, hogy a kompenzációs konstrukció érvényes legyen rá.</span><span class="sxs-lookup"><span data-stu-id="05cb6-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="05cb6-160">A feltételek a következők lehetnek:</span><span class="sxs-lookup"><span data-stu-id="05cb6-160">Criteria can include:</span></span>

    - <span data-ttu-id="05cb6-161">**Részleg**</span><span class="sxs-lookup"><span data-stu-id="05cb6-161">**Department**</span></span>
    - <span data-ttu-id="05cb6-162">**Szakszervezet**</span><span class="sxs-lookup"><span data-stu-id="05cb6-162">**Labor union**</span></span>
    - <span data-ttu-id="05cb6-163">**Hely** (**Kompenzációs régió**)</span><span class="sxs-lookup"><span data-stu-id="05cb6-163">**Location** (**Compensation region**)</span></span>
    - <span data-ttu-id="05cb6-164">**Munka**</span><span class="sxs-lookup"><span data-stu-id="05cb6-164">**Job**</span></span>
    - <span data-ttu-id="05cb6-165">**Funkció**</span><span class="sxs-lookup"><span data-stu-id="05cb6-165">**Function**</span></span>
    - <span data-ttu-id="05cb6-166">**Feladattípus**</span><span class="sxs-lookup"><span data-stu-id="05cb6-166">**Job type**</span></span>
    - <span data-ttu-id="05cb6-167">**Kompenzációs szint**</span><span class="sxs-lookup"><span data-stu-id="05cb6-167">**Compensation level**</span></span>
    
    <span data-ttu-id="05cb6-168">Az alkalmazottnak minden megadott feltételt teljesítenie kell ahhoz, hogy a kompenzációs konstrukció érvényes legyen rá.</span><span class="sxs-lookup"><span data-stu-id="05cb6-168">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="05cb6-169">Ha nem ad meg feltétel, minden alkalmazottra érvényes a kompenzációs konstrukció.</span><span class="sxs-lookup"><span data-stu-id="05cb6-169">If you don't specify any criteria, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="05cb6-170">Ha egy alkalmazott nem felel meg az alkalmazhatósági szabályban megadott feltételeknek, vagy egy alkalmazhatósági szabály nem volt megadva a kompenzációs konstrukcióhoz, a kompenzációs konstrukció nem fog megjelenni a keresésben az alkalmazotthoz tartozó Fix kompenzációs rekord létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="05cb6-170">If an employee doesn't meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan won't appear in the lookup when you create a fixed compensation record for an employee.</span></span>

7. <span data-ttu-id="05cb6-171">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-171">Close the page.</span></span>

8. <span data-ttu-id="05cb6-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="05cb6-172">Close the page.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]