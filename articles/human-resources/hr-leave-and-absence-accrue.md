---
title: Szabadság- és távolléti tervek halmozódása
description: Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: aed36a38c5d50767b5ac14ae82ca424f0c835ae0
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5116092"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="dc3f8-103">Szabadság- és távolléti tervek halmozódása</span><span class="sxs-lookup"><span data-stu-id="dc3f8-103">Accrue leave and absence plans</span></span>

<span data-ttu-id="dc3f8-104">Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="dc3f8-105">Több alkalmazott szabadságának és távollétének elhatárolása</span><span class="sxs-lookup"><span data-stu-id="dc3f8-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="dc3f8-106">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dc3f8-107">A **Szabadság kezelése** alatt válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="dc3f8-108">Megjelenik a **Szabadság- és távolléti tervek elhatárolása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="dc3f8-109">Az **Elhatárolás kezdete** részben válassza a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="dc3f8-110">Ha minden vállalatnál szeretné futtatni az elhatárolást, válassza az **Összes vállalat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="dc3f8-111">Ha egyetlen szabadsági tervhez szeretné feldolgozni az elhatárolást, válassza a **Nem** lehetőséget az **Összes konstrukció** alatt, majd válasszon egy **Szabadságkonstrukciót**.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="dc3f8-112">Ha az összes vállalatot választja, akkor nem választhat ki egyéni szabadságtervet.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-112">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="dc3f8-113">Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="dc3f8-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="dc3f8-114">Információk megadása az elhatárolási folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-114">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="dc3f8-115">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="dc3f8-116">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="dc3f8-117">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-117">Select **OK**.</span></span> <span data-ttu-id="dc3f8-118">Az elhatárolási folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-118">The accrual process will run with the parameters you set.</span></span>

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="dc3f8-119">Egy alkalmazott szabadságának és távollétének elhatárolása</span><span class="sxs-lookup"><span data-stu-id="dc3f8-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="dc3f8-120">Az alkalmazott rekordján válassza a **Szabadság** elemet.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="dc3f8-121">Válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="dc3f8-122">Megjelenik a **Szabadság- és távolléti tervek elhatárolása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="dc3f8-123">Az **Elhatárolás kezdete** részben válassza a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="dc3f8-124">Ha minden vállalatnál szeretné futtatni az elhatárolást, válassza az **Összes vállalat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="dc3f8-125">Ha egyetlen szabadsági tervhez szeretné feldolgozni az elhatárolást, válassza a **Nem** lehetőséget az **Összes konstrukció** alatt, majd válasszon egy **Szabadságkonstrukciót**.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="dc3f8-126">Ha az összes vállalatot választja, akkor nem választhat ki egyéni szabadságtervet.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-126">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="dc3f8-127">Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:</span><span class="sxs-lookup"><span data-stu-id="dc3f8-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="dc3f8-128">Információk megadása az elhatárolási folyamathoz.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="dc3f8-129">Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="dc3f8-130">A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="dc3f8-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-131">Select **OK**.</span></span> <span data-ttu-id="dc3f8-132">Az elhatárolási folyamat a megadott paraméterekkel fog futni.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="dc3f8-133">Több alkalmazott szabadság- és távollét-elhatárolásának törlése</span><span class="sxs-lookup"><span data-stu-id="dc3f8-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="dc3f8-134">Törli az adott tervhez és dátumtartományhoz tartozó elhatárolási rekordokat.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="dc3f8-135">Az elhatárolásnak aznapi vagy jövőbeli dátummal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="dc3f8-136">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dc3f8-137">A **Szabadság kezelése** alatt válassza a **Szabadság- és távolléti tervek elhatárolásának törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="dc3f8-138">A **Szabadság- és távolléti tervek elhatárolásának törlése** párbeszédpanelen válassza ki a **Szabadságterv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span> 

4. <span data-ttu-id="dc3f8-139">Ha szükséges, válassza az **Egyenleg-helyesbítések törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="dc3f8-140">Adja meg vagy válassza ki a **Szabadság elhatárolási dátumát**.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="dc3f8-141">Ennek a dátumnak ma vagy a jövőben kell lennie.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-141">This date has to be either today or in the future.</span></span> 

6. <span data-ttu-id="dc3f8-142">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-142">Select **OK**.</span></span> <span data-ttu-id="dc3f8-143">Az elhatárolási folyamat a megadott paraméterekkel töröl elhatárolásokat.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-143">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="dc3f8-144">Egy alkalmazott szabadság- és távollét-elhatárolásának törlése</span><span class="sxs-lookup"><span data-stu-id="dc3f8-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="dc3f8-145">Az alkalmazott rekordján válassza a **Szabadság** elemet.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="dc3f8-146">Válassz a **Szabadság- és távolléti tervek elhatárolásának törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="dc3f8-147">A **Szabadság- és távolléti tervek elhatárolásának törlése** párbeszédpanelen válassza ki a **Szabadságterv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span> 

4. <span data-ttu-id="dc3f8-148">Ha szükséges, válassza az **Egyenleg-helyesbítések törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="dc3f8-149">Adja meg vagy válassza ki a **Szabadság elhatárolási dátumát**.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="dc3f8-150">Ennek a dátumnak ma vagy a jövőben kell lennie.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-150">This date must be either today or in the future.</span></span> 

6. <span data-ttu-id="dc3f8-151">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-151">Select **OK**.</span></span> <span data-ttu-id="dc3f8-152">Az elhatárolási folyamat a megadott paraméterekkel töröl elhatárolásokat.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-152">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="dc3f8-153">A szabadságelhatárolási és -törlési folyamatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="dc3f8-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="dc3f8-154">**Szabadságelhatárolás auditálása** megjelenít minden egyes alkalmat, amikor elhatárolást futtatott vagy törölt egy vagy az összes munkavállalóhoz.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="dc3f8-155">Az dátum és a műveletet végrehajtó személy is meg lesz jelenítve.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="dc3f8-156">A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dc3f8-157">A **Szabadság kezelése** alatt válassza a **Szabadságelhatárolás auditálásának törlése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc3f8-158">Lásd még</span><span class="sxs-lookup"><span data-stu-id="dc3f8-158">See also</span></span>

[<span data-ttu-id="dc3f8-159">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="dc3f8-159">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="dc3f8-160">Szabadság- és távolléti terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="dc3f8-160">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
