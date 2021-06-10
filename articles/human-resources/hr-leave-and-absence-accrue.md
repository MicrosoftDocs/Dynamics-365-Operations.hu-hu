---
title: Szabadság- és távolléti tervek halmozódása
description: Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.
author: andreabichsel
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 86ca63b1703faa6f57ed2e5591c89a5e84363481
ms.sourcegitcommit: 318e406b84d43381d450272eb83c5eea9c5cf1c0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059473"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="8c56f-103">Szabadság- és távolléti tervek halmozódása</span><span class="sxs-lookup"><span data-stu-id="8c56f-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8c56f-104">Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.</span><span class="sxs-lookup"><span data-stu-id="8c56f-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="8c56f-105">Több alkalmazott szabadságának és távollétének elhatárolása</span><span class="sxs-lookup"><span data-stu-id="8c56f-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="8c56f-106">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="8c56f-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8c56f-107">A **Szabadság kezelése** alatt válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="8c56f-108">Megjelenik a **Szabadság- és távolléti tervek elhatárolása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="8c56f-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="8c56f-109">Az **Elhatárolás kezdete** részben válassza a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.</span><span class="sxs-lookup"><span data-stu-id="8c56f-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="8c56f-110">Ha minden vállalatnál szeretné futtatni az elhatárolást, válassza az **Összes vállalat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="8c56f-111">Ha egyetlen szabadsági tervhez szeretné feldolgozni az elhatárolást, válassza a **Nem** lehetőséget az **Összes konstrukció** alatt, majd válasszon egy **Szabadságkonstrukciót**.</span><span class="sxs-lookup"><span data-stu-id="8c56f-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="8c56f-112">Ha az összes vállalatot választja, akkor nem választhat ki egyéni szabadságtervet.</span><span class="sxs-lookup"><span data-stu-id="8c56f-112">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="8c56f-113">Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="8c56f-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

    1. <span data-ttu-id="8c56f-114">Információk megadása az elhatárolási folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="8c56f-114">Enter information for the accrual process.</span></span>
    2. <span data-ttu-id="8c56f-115">Ismétlődő feladat beállításához válassza az **Ismétlődés** lehetőséget, adja meg az ismétlődés adatait, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8c56f-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and then select **OK**.</span></span>
    3. <span data-ttu-id="8c56f-116">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8c56f-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>
    4. <span data-ttu-id="8c56f-117">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-117">Select **OK**.</span></span> <span data-ttu-id="8c56f-118">Az elhatárolási folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="8c56f-118">The accrual process will run with the parameters you set.</span></span> 

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="8c56f-119">Egy alkalmazott szabadságának és távollétének elhatárolása</span><span class="sxs-lookup"><span data-stu-id="8c56f-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="8c56f-120">Az alkalmazott rekordján válassza a **Szabadság** elemet.</span><span class="sxs-lookup"><span data-stu-id="8c56f-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="8c56f-121">Válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="8c56f-122">Megjelenik a **Szabadság- és távolléti tervek elhatárolása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="8c56f-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="8c56f-123">Az **Elhatárolás kezdete** részben válassza a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.</span><span class="sxs-lookup"><span data-stu-id="8c56f-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="8c56f-124">Ha minden vállalatnál szeretné futtatni az elhatárolást, válassza az **Összes vállalat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="8c56f-125">Ha egyetlen szabadsági tervhez szeretné feldolgozni az elhatárolást, válassza a **Nem** lehetőséget az **Összes konstrukció** alatt, majd válasszon egy **Szabadságkonstrukciót**.</span><span class="sxs-lookup"><span data-stu-id="8c56f-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="8c56f-126">Ha az összes vállalatot választja, akkor nem választhat ki egyéni szabadságtervet.</span><span class="sxs-lookup"><span data-stu-id="8c56f-126">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="8c56f-127">Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="8c56f-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="8c56f-128">Információk megadása az elhatárolási folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="8c56f-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="8c56f-129">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8c56f-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="8c56f-130">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8c56f-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="8c56f-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-131">Select **OK**.</span></span> <span data-ttu-id="8c56f-132">Az elhatárolási folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="8c56f-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="8c56f-133">Több alkalmazott szabadság- és távollét-elhatárolásának törlése</span><span class="sxs-lookup"><span data-stu-id="8c56f-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="8c56f-134">Törli az adott tervhez és dátumtartományhoz tartozó elhatárolási rekordokat.</span><span class="sxs-lookup"><span data-stu-id="8c56f-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="8c56f-135">Az elhatárolásnak aznapi vagy jövőbeli dátummal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="8c56f-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="8c56f-136">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="8c56f-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8c56f-137">A **Szabadság kezelése** alatt válassza a **Szabadság- és távolléti tervek elhatárolásának törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="8c56f-138">A **Szabadság- és távolléti tervek elhatárolásának törlése** párbeszédpanelen válassza ki a **Szabadságterv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span>

4. <span data-ttu-id="8c56f-139">Ha szükséges, válassza az **Egyenleg-helyesbítések törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="8c56f-140">Adja meg vagy válassza ki a **Szabadság elhatárolási dátumát**.</span><span class="sxs-lookup"><span data-stu-id="8c56f-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="8c56f-141">Ennek a dátumnak ma vagy a jövőben kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8c56f-141">This date has to be either today or in the future.</span></span>

6. <span data-ttu-id="8c56f-142">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-142">Select **OK**.</span></span> <span data-ttu-id="8c56f-143">Az elhatárolási folyamat a megadott paraméterekkel töröl elhatárolásokat.</span><span class="sxs-lookup"><span data-stu-id="8c56f-143">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="8c56f-144">Egy alkalmazott szabadság- és távollét-elhatárolásának törlése</span><span class="sxs-lookup"><span data-stu-id="8c56f-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="8c56f-145">Az alkalmazott rekordján válassza a **Szabadság** elemet.</span><span class="sxs-lookup"><span data-stu-id="8c56f-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="8c56f-146">Válassz a **Szabadság- és távolléti tervek elhatárolásának törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="8c56f-147">A **Szabadság- és távolléti tervek elhatárolásának törlése** párbeszédpanelen válassza ki a **Szabadságterv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span>

4. <span data-ttu-id="8c56f-148">Ha szükséges, válassza az **Egyenleg-helyesbítések törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="8c56f-149">Adja meg vagy válassza ki a **Szabadság elhatárolási dátumát**.</span><span class="sxs-lookup"><span data-stu-id="8c56f-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="8c56f-150">Ennek a dátumnak ma vagy a jövőben kell lennie.</span><span class="sxs-lookup"><span data-stu-id="8c56f-150">This date must be either today or in the future.</span></span>

6. <span data-ttu-id="8c56f-151">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-151">Select **OK**.</span></span> <span data-ttu-id="8c56f-152">Az elhatárolási folyamat a megadott paraméterekkel töröl elhatárolásokat.</span><span class="sxs-lookup"><span data-stu-id="8c56f-152">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="8c56f-153">A szabadságelhatárolási és -törlési folyamatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="8c56f-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="8c56f-154">**Szabadságelhatárolás auditálása** megjelenít minden egyes alkalmat, amikor elhatárolást futtatott vagy törölt egy vagy az összes munkavállalóhoz.</span><span class="sxs-lookup"><span data-stu-id="8c56f-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="8c56f-155">Az dátum és a műveletet végrehajtó személy is meg lesz jelenítve.</span><span class="sxs-lookup"><span data-stu-id="8c56f-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="8c56f-156">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="8c56f-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8c56f-157">A **Szabadság kezelése** alatt válassza a **Szabadságelhatárolás auditálásának törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8c56f-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="preview-leave-accrual-transaction-auditing"></a><span data-ttu-id="8c56f-158">(Előzetes verzió) Szabadságelhatárolási tranzakció auditálása</span><span class="sxs-lookup"><span data-stu-id="8c56f-158">(Preview) Leave accrual transaction auditing</span></span>

[!include [Preview feature](includes/preview-feature.md)]

<span data-ttu-id="8c56f-159">Ez az előzetes verziójú funkció segít a szabadságokat és a távolléteket kezelőknek áttekinteni a szabadság- és a távollétkönyvelési tranzakciókat, amelyek egy alkalmazott távolléti egyenlegével kapcsolatosak egy adott távolléttípusnál.</span><span class="sxs-lookup"><span data-stu-id="8c56f-159">This preview feature helps leave and absence managers understand the leave and absence accrual transactions related to an employee’s time off balances for a specific leave type.</span></span>

<span data-ttu-id="8c56f-160">A tranzakció részleteinek megtekintése:</span><span class="sxs-lookup"><span data-stu-id="8c56f-160">To view transaction details:</span></span>

1. <span data-ttu-id="8c56f-161">Az alkalmazott rekordján válassza a **Szabadság** elemet.</span><span class="sxs-lookup"><span data-stu-id="8c56f-161">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="8c56f-162">Válassza a **Szabadság megtekintése** lehetőséget, majd lépjen az **Egyenlegek** lapra.</span><span class="sxs-lookup"><span data-stu-id="8c56f-162">Select **View time off**, and then select the **Balances** tab.</span></span>

<span data-ttu-id="8c56f-163">Az adott szabadságtípushoz kapcsolódó könyvelési tranzakciók megtekintéséhez válassza ki a numerikus értéket az **Aktuális egyenleg** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="8c56f-163">To view the accrual transactions related to a specific leave type, select the numerical value in the **Current balance** column.</span></span>

<span data-ttu-id="8c56f-164">Adott könyvelési összegek tranzakciós részleteinek megtekintéséhez válasszon ki egy könyvelési sort, nyissa meg a **Kapcsolódó információ** panelt a jobb oldalon, majd a **Tranzakció részletei** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8c56f-164">To view the transaction details for a specific accrual amount, select an accrual row, open the **Related information** panel on the right, and then open the **Transaction details** section.</span></span> <span data-ttu-id="8c56f-165">Megjelenik a Tranzakció részletei szakasz:</span><span class="sxs-lookup"><span data-stu-id="8c56f-165">The Transaction details section displays:</span></span>

- <span data-ttu-id="8c56f-166">Az alkalmazott távolléttípusára vonatkozó egyenleg módosításai</span><span class="sxs-lookup"><span data-stu-id="8c56f-166">Changes to the employee’s leave type balance</span></span>
- <span data-ttu-id="8c56f-167">A foglalkoztatás adott könyvelési időszakra vonatkozó részletei</span><span class="sxs-lookup"><span data-stu-id="8c56f-167">Employment details for that specified accrual period</span></span>
- <span data-ttu-id="8c56f-168">A könyvelési időszak és a díjak részletei</span><span class="sxs-lookup"><span data-stu-id="8c56f-168">Details about the accrual period and rates</span></span>
- <span data-ttu-id="8c56f-169">A szabadságterv konfigurációin végrehajtott módosítások</span><span class="sxs-lookup"><span data-stu-id="8c56f-169">Any changes made to leave plan configurations</span></span>

![Szabadságelhatárolási tranzakció auditálásának megjelenítése](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a><span data-ttu-id="8c56f-171">Lásd még</span><span class="sxs-lookup"><span data-stu-id="8c56f-171">See also</span></span>

[<span data-ttu-id="8c56f-172">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="8c56f-172">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="8c56f-173">Szabadság- és távolléti terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="8c56f-173">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
