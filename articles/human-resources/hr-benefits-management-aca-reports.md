---
title: Affordable Care Act-jelentések készítése a Juttatáskezelésben
description: Ez a témakör azt ismerteti, hogyan követheti a Juttatáskezelés funkcióval a 1095-B és az 1095-C űrlapon az ACA munkáltatói felhatalmazás keretén belül jelentett információkat.
author: andreabichsel
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 1417232baeaf03721bd0b25cc3f9fd5f750c65d5
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052265"
---
# <a name="generate-aca-reports-in-benefits-management"></a><span data-ttu-id="0ec3f-103">ACA-jelentések készítése a Juttatáskezelésben</span><span class="sxs-lookup"><span data-stu-id="0ec3f-103">Generate ACA reports in Benefits management</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0ec3f-104">A Juttatáskezelés funkcióval követheti a 1095-B és az 1095-C űrlapon az ACA munkáltatói felhatalmazás keretén belül jelentett információkat.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-104">Benefits management helps you track information that is reported on Form 1095-B and Form 1095-C for the Affordable Care Act (ACA) employer mandate.</span></span> <span data-ttu-id="0ec3f-105">A régi **Juttatások** munkaterületen történő ACA jelentéskészítési képességhez hasonlóan ez a funkció csak az Egyesült Államokban érvényes jogi személyekre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-105">Like the ACA reporting capability in the old **Benefits** workspace, this functionality applies only to legal entities in the United States.</span></span>

<span data-ttu-id="0ec3f-106">A funkció használatához először be kell kapcsolnia a **Speciális juttatások kezelése** funkciót.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-106">To use this functionality, you must first turn on **Advanced Benefits Management**.</span></span> <span data-ttu-id="0ec3f-107">A további tudnivalókat, többek között a juttatások kezelésével kapcsolatos fontos figyelmeztetéseket lásd: [Juttatáskezelés funkció engedélyezése vagy letiltása](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span><span class="sxs-lookup"><span data-stu-id="0ec3f-107">For more information, including important caveats about Benefits management, see [Enable or disable Benefits management](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ec3f-108">Az ACA-jelentéskészítés csak a **Juttatáskezelés** munkaterületről vagy a régi **Juttatások** munkaterületről használható, mindkettőből nem.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-108">You can use ACA reporting only from either the **Benefits management** workspace or the old **Benefits** workspace, not from both.</span></span> <span data-ttu-id="0ec3f-109">Ha például a Juttatáskezelés szolgáltatásra vált, az ACA-jelentéskészítés csak a **Juttatáskezelés** munkaterületről érhető el, a régi **Juttatások** munkaterületről nem.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-109">For example, if you switched to Benefits management, ACA reporting is available only from the **Benefits management** workspace, not from the old **Benefits** workspace.</span></span>
>
> <span data-ttu-id="0ec3f-110">Ha egy beléptetési év közepén vált a Juttatáskezelés beállításra, az egész évre vonatkozóan helyesen kell konfigurálnia az alkalmazotti adatokat a Juttatáskezelés eszközben.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-110">If you switch to Benefits management in the middle of an enrollment year, you must correctly configure employee data for the whole year in Benefits management.</span></span> <span data-ttu-id="0ec3f-111">Ezzel a módszerrel biztosíthatja, hogy pontos jelentési adatokat kapjon az egész évre.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-111">In this way, you ensure that you will receive accurate reporting information for the whole year.</span></span>

## <a name="getting-started"></a><span data-ttu-id="0ec3f-112">Első lépések</span><span class="sxs-lookup"><span data-stu-id="0ec3f-112">Getting started</span></span>

<span data-ttu-id="0ec3f-113">Az adatoknak az 1095 űrlapok esetében történő nyomon követéséhez először létre kell hozni egy vagy több Affordable Care fedezeti csoportot.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-113">To track information for 1095 forms, first create one or more Affordable Care coverage groups.</span></span> <span data-ttu-id="0ec3f-114">Ezek a csoportok a következő információkat jelzik:</span><span class="sxs-lookup"><span data-stu-id="0ec3f-114">These groups indicate the following information:</span></span>

- <span data-ttu-id="0ec3f-115">Az alkalmazottnak nyújtott fedezeti ajánlat</span><span class="sxs-lookup"><span data-stu-id="0ec3f-115">The offer of coverage that was provided to an employee</span></span>
- <span data-ttu-id="0ec3f-116">Az alkalmazott részesedése a legkisebb költségalapú havi díjból, ha költség magasabb a szövetségi szegénységi küszöbnél</span><span class="sxs-lookup"><span data-stu-id="0ec3f-116">The employee's share of the lowest-cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="0ec3f-117">A munkáltató által használt Safe Harbor, ha van ilyen</span><span class="sxs-lookup"><span data-stu-id="0ec3f-117">The safe harbor that is used by the employer, if applicable</span></span>

<span data-ttu-id="0ec3f-118">Az Affordable Care fedezeti csoportok segítségével több olyan alkalmazotti rekord adatait kezelheti, amelyekre ugyanazok a feltételek vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-118">Affordable Care coverage groups help you manage this information for multiple employee records that have the same conditions.</span></span> <span data-ttu-id="0ec3f-119">A csoportokat egyszerűen hozzárendelheti egy vagy több alkalmazotthoz.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-119">You can easily assign groups to one or more employees.</span></span>

### <a name="create-or-edit-an-affordable-care-coverage-group"></a><span data-ttu-id="0ec3f-120">Affordable Care fedezeti csoport létrehozása vagy szerkesztése</span><span class="sxs-lookup"><span data-stu-id="0ec3f-120">Create or edit an Affordable Care coverage group</span></span>

1. <span data-ttu-id="0ec3f-121">A **Juttatáskezelés** munkaterületen válassza az **Affordable Care fedezeti csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-121">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>

    ![Az Affordable Care fedezeti csoport kiválasztása](./media/hr-benefits-management-aca-coverage-group.png)

2. <span data-ttu-id="0ec3f-123">Válassza az **Új** lehetőséget, ha új Affordable Care fedezeti csoportot szeretne létrehozni vagy a **Szerkesztés** lehetőséget egy meglévő csoport módosításához.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-123">Select **New** to create a new Affordable Care coverage group or **Edit** to change an existing group.</span></span>

    ![Új vagy Szerkesztés kiválasztása](./media/hr-benefits-management-aca-new.png)

3. <span data-ttu-id="0ec3f-125">Állítsa be a következő mezőket.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-125">Set the following fields.</span></span>

    | <span data-ttu-id="0ec3f-126">Mező</span><span class="sxs-lookup"><span data-stu-id="0ec3f-126">Field</span></span> | <span data-ttu-id="0ec3f-127">Leírás</span><span class="sxs-lookup"><span data-stu-id="0ec3f-127">Description</span></span> |
    |---|---|
    | <span data-ttu-id="0ec3f-128">Név</span><span class="sxs-lookup"><span data-stu-id="0ec3f-128">Name</span></span> | <span data-ttu-id="0ec3f-129">Adja meg a csoport nevét.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-129">Enter a name for the group.</span></span> |
    | <span data-ttu-id="0ec3f-130">Leírás</span><span class="sxs-lookup"><span data-stu-id="0ec3f-130">Description</span></span> | <span data-ttu-id="0ec3f-131">A csoport leírásának megadása.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-131">Enter a description of the group.</span></span> |
    | <span data-ttu-id="0ec3f-132">Jogosultságra vonatkozó ajánlat</span><span class="sxs-lookup"><span data-stu-id="0ec3f-132">Offer of coverage</span></span> | <span data-ttu-id="0ec3f-133">Az alkalmazottaknak, házastársuknak vagy partnerüknek és eltartottaiknak nyújtott fedezet.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-133">The coverage that is offered to employees, their spouse or partner, and their dependents.</span></span> |
    | <span data-ttu-id="0ec3f-134">Alkalmazott költségmegosztása</span><span class="sxs-lookup"><span data-stu-id="0ec3f-134">Employee share of cost</span></span> | <span data-ttu-id="0ec3f-135">Az az összeg, amelyért az alkalmazott felelős.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-135">The amount that the employee is responsible for.</span></span> |
    | <span data-ttu-id="0ec3f-136">4980H alkalmazható szakasza, Safe Harbor</span><span class="sxs-lookup"><span data-stu-id="0ec3f-136">Applicable section 4980H safe harbor</span></span> | <span data-ttu-id="0ec3f-137">A 4980H Safe Harbor vagy az átmeneti mentesség kódja.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-137">The 4980H safe harbor or transition relief code.</span></span> |
    | <span data-ttu-id="0ec3f-138">A terv kezdő hónapja</span><span class="sxs-lookup"><span data-stu-id="0ec3f-138">Plan start month</span></span> | <span data-ttu-id="0ec3f-139">Válassza ki azt a naptári hónapot, amikor a juttatási terv éve elkezdődik.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-139">Select the calendar month when your benefit plan year begins.</span></span> |
    | <span data-ttu-id="0ec3f-140">Csoport érvényességének kezdete</span><span class="sxs-lookup"><span data-stu-id="0ec3f-140">Group valid from</span></span> | <span data-ttu-id="0ec3f-141">A rekord érvényességének első dátuma.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-141">The first date when this record is valid.</span></span> |
    | <span data-ttu-id="0ec3f-142">Csoport érvényességi tartománya</span><span class="sxs-lookup"><span data-stu-id="0ec3f-142">Group valid through</span></span> | <span data-ttu-id="0ec3f-143">A rekord érvényességének utolsó dátuma.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-143">The last date when this record is valid.</span></span> <span data-ttu-id="0ec3f-144">Ha nincs lejárati dátum, akkor a **Soha** lehetőséget írja be.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-144">If there is no expiration date, enter **Never**.</span></span> |

    ![Fedezeti csoport létrehozása](./media/hr-benefits-management-aca-new-group.png)

4. <span data-ttu-id="0ec3f-146">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-146">Select **Save**.</span></span>

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a><span data-ttu-id="0ec3f-147">Több alkalmazott hozzárendelése egy Affordable Care fedezeti csoporthoz</span><span class="sxs-lookup"><span data-stu-id="0ec3f-147">Assign multiple employees to an Affordable Care coverage group</span></span>

1. <span data-ttu-id="0ec3f-148">A **Juttatáskezelés** munkaterületen válassza az **Affordable Care fedezeti csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-148">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>
2. <span data-ttu-id="0ec3f-149">Válassza ki azt a csoportot, amelyhez alkalmazottakat szeretne rendelni.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-149">Select the group to assign employees to.</span></span>
3. <span data-ttu-id="0ec3f-150">Válassza a **Tömeges hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-150">Select **Mass assignment**.</span></span>

    ![A Tömeges hozzárendelés lehetőség kiválasztása](./media/hr-benefits-management-aca-mass-assignment.png)

4. <span data-ttu-id="0ec3f-152">Válassza ki az alkalmazottakat a listából, majd válassza a **Hozzárendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-152">Select employees in the list, and then select **Assign**.</span></span>

    ![Kiválasztott alkalmazottak hozzárendelése egy csoporthoz](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a><span data-ttu-id="0ec3f-154">Fedezeti lehetőségek több változatának karbantartása</span><span class="sxs-lookup"><span data-stu-id="0ec3f-154">Maintain multiple versions of coverage options</span></span>

<span data-ttu-id="0ec3f-155">A fedezeti csoportok több változatának karbantartása lehetséges.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-155">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="0ec3f-156">Ha valami változás történik a szervezetben vagy a felkínált juttatásokban, akkor a csoport információit naprakészen tarthatja anélkül, hogy új csoportot kell létrehoznia és alkalmazottakat kellene hozzárendelnie.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-156">When something changes in your organization or the benefits that are offered, you can keep the group's information up to date without having to create a new group and reassign employees to it.</span></span>

<span data-ttu-id="0ec3f-157">Az Affordable Care fedezeti csoportok létrehozása után tömegesen rendelheti hozzájuk az alkalmazottakat.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-157">After you've created Affordable Care coverage groups, you can mass-assign employees to them.</span></span> <span data-ttu-id="0ec3f-158">Az alkalmazottakat egyesével is hozzárendelheti a csoportokhoz, és jelezheti, hogy az ACA-adatokat nyomon követhetik-e és lejelentik-e.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-158">You can also individually assign employees to groups, and indicate whether ACA information is tracked and reported.</span></span>

<span data-ttu-id="0ec3f-159">Ha nem kell egy alkalmazott ACA-adatait nyomon követnie és jelentenie, a **Jogosultság bejelentése** lehetőséget **Nem** értékre állíthatja.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-159">If you don't have to track and report ACA information for an employee, you can set the **Report coverage** option to **No**.</span></span> <span data-ttu-id="0ec3f-160">Előfordulhat például, hogy olyan részmunkaidős alkalmazottak is vannak, akiknek nincs szükségük az ACA-jelentéskészítésre.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-160">For example, you might have part-time employees who don't require ACA reporting.</span></span>

### <a name="override-default-values-for-an-employee"></a><span data-ttu-id="0ec3f-161">Alkalmazott alapértelmezett értékeinek felülbírálása</span><span class="sxs-lookup"><span data-stu-id="0ec3f-161">Override default values for an employee</span></span>

<span data-ttu-id="0ec3f-162">Az Affordable Care fedezeti csoporthoz hozzárendelt alkalmazottak esetében a következő beállításokat módosíthatja az olyan hónapokra, amelyekben eltérő értékekre van szükség:</span><span class="sxs-lookup"><span data-stu-id="0ec3f-162">For employees who are assigned to an Affordable Care coverage group, you can change the following options for any months that require different values:</span></span>

- <span data-ttu-id="0ec3f-163">Jogosultságra vonatkozó ajánlat</span><span class="sxs-lookup"><span data-stu-id="0ec3f-163">Offer of coverage</span></span>
- <span data-ttu-id="0ec3f-164">Alkalmazott költségmegosztása</span><span class="sxs-lookup"><span data-stu-id="0ec3f-164">Employee share of cost</span></span>
- <span data-ttu-id="0ec3f-165">4980H alkalmazható szakasza, Safe Harbor</span><span class="sxs-lookup"><span data-stu-id="0ec3f-165">Applicable section 4980H safe harbor</span></span>

> [!NOTE]
> <span data-ttu-id="0ec3f-166">A 2020-as ACA-jelentésekhez az 1095-C űrlapon a munkahelyi és az otthoni irányítószámot is le kell jelenteni.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-166">For 2020 ACA reports, you must report both work and home ZIP Codes on Form 1095-C.</span></span> <span data-ttu-id="0ec3f-167">A program az aktuális aktív helyek alapján automatikusan kitölti az értékeket.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-167">Values are automatically filled in, based on current active locations.</span></span> <span data-ttu-id="0ec3f-168">Ha bármelyik hely más volt az év bármely részében, felül kell bírálnia az értéket.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-168">If either location was different during any part of the year, you must override the value.</span></span> <span data-ttu-id="0ec3f-169">Az 1095-C jelentés **Irányítószám** mezője (17. sor) csak akkor van kitöltve, ha a **Jogosultságra vonatkozó ajánlat** kódja **1L** és **1Q** közötti értékeket tartalmaz az alábbiak szerint:</span><span class="sxs-lookup"><span data-stu-id="0ec3f-169">The **ZIP Code** field (line 17) of the 1095-C report is filled in only if the **Offer of coverage** code contains **1L** through **1Q**, as follows:</span></span>
>
> - <span data-ttu-id="0ec3f-170">**1L, 1M vagy 1N:** az elsődleges lakóhely irányítószáma</span><span class="sxs-lookup"><span data-stu-id="0ec3f-170">**1L, 1M, or 1N:** The primary residence ZIP Code</span></span>
> - <span data-ttu-id="0ec3f-171">**1O, 1P, 1Q:** az elsődleges munkahely irányítószáma</span><span class="sxs-lookup"><span data-stu-id="0ec3f-171">**1O, 1P, 1Q:** The primary work ZIP Code</span></span>

<span data-ttu-id="0ec3f-172">A következő lépésekkel kivételeket adhat meg egy Affordable Care fedezeti csoport bármely értékére.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-172">To enter exceptions for any values of an Affordable Care coverage group, follow these steps.</span></span>

1. <span data-ttu-id="0ec3f-173">A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások**, majd a **Dolgozók** elemet.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-173">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>
2. <span data-ttu-id="0ec3f-174">A listából válassza ki az alkalmazottat.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-174">Select the employee in the list.</span></span>
3. <span data-ttu-id="0ec3f-175">A **Foglalkoztatás** lap **További információk** szakaszában válassza az **Affordable Care fedezet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-175">On the **Employment** tab, in the **More information** section, select **Affordable Care coverage**.</span></span>

    ![Egyetlen alkalmazott beállításainak módosítása](./media/hr-benefits-management-aca-change-single-employee.png)

4. <span data-ttu-id="0ec3f-177">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-177">Select **Edit**.</span></span>
5. <span data-ttu-id="0ec3f-178">Minden, változtatást igénylő hónap esetén jelölje be az **Alapértelmezett érték felülbírálása** jelölőnégyzetet, majd szükség szerint módosítsa a többi értéket.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-178">For each month that requires changes, select the **Override default** check box, and then change the other values as required.</span></span>

    ![Alapértelmezett értékek felülbírálása](./media/hr-benefits-management-aca-override-default.png)

6. <span data-ttu-id="0ec3f-180">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-180">Select **Save**.</span></span>

## <a name="report-health-care-coverage"></a><span data-ttu-id="0ec3f-181">Egészségügyi fedezeti jelentés</span><span class="sxs-lookup"><span data-stu-id="0ec3f-181">Report health care coverage</span></span>

<span data-ttu-id="0ec3f-182">Nyomon kell követni a teljes munkaidős és részmunkaidős alkalmazottaknak a munkáltató által biztosított, a munkavállaló által fizetett ellátását.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-182">You must track any employer-sponsored, self-insured health care coverage for full-time and part-time employees.</span></span> <span data-ttu-id="0ec3f-183">Az összes alkalmazottat és eltartottjaikat meg kell adni annak a hónapnak az 1095-C jelentésében, amelyben a csomag vonatkozik rájuk.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-183">Include each employee, together with their dependents, on the 1095-C report for the months when they were covered.</span></span>

<span data-ttu-id="0ec3f-184">Azt, hogy a juttatácsomagot jelenteni kell-e, kövesse a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-184">To indicate whether a benefit plan must be reported, follow these steps.</span></span>

1. <span data-ttu-id="0ec3f-185">A **Juttatáskezelés** munkaterületen válassza a **Juttatási tervek** elemet.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-185">In the **Benefits management** workspace, select **Benefit plans**.</span></span>
2. <span data-ttu-id="0ec3f-186">Válassza ki a jelenteni kívánt juttatási tervet.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-186">Select the benefit plan to report.</span></span>
3. <span data-ttu-id="0ec3f-187">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-187">Select **Edit**.</span></span>
4. <span data-ttu-id="0ec3f-188">Állítsa a **Jelentve az Affordable Care Act értelmében** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-188">Set the **Reported under the Affordable Care Act** option to **Yes**.</span></span>

    ![Egészségügyi fedezeti jelentés](./media/hr-benefits-management-aca-report-coverage.png)

5. <span data-ttu-id="0ec3f-190">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-190">Select **Save**.</span></span>

<span data-ttu-id="0ec3f-191">Ha az alkalmazott egy eltartottra vonatkozóan egészségügyi fedezetet választ, az eltartott fedezeti időszakát az eltartott beléptetésének vagy eltávolításának dátuma határozza meg.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-191">If an employee chooses health care coverage for a dependent, the dependent's coverage period is determined by the date when the dependent was enrolled or removed.</span></span> <span data-ttu-id="0ec3f-192">Az eltartottak fedezeti dátumának számítása automatikusan azon az időszakon alapul, amikor az eltartott jogosultságokkal rendelkezett és aktív volt a csomagban a beléptetési év során.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-192">Coverage dates for dependents are automatically calculated based on the period when the dependent was eligible and active in a plan during the enrollment year.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="0ec3f-193">1095-B és 1095-C űrlapok létrehozása</span><span class="sxs-lookup"><span data-stu-id="0ec3f-193">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="0ec3f-194">Lehetőség van az ACA 1095-B és 1095-C űrlapok létrehozására és a továbbításukra az összes alkalmazottnak.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-194">You can generate ACA 1095-B and 1095-C forms, and then distribute them to each of your employees.</span></span> <span data-ttu-id="0ec3f-195">Elektronikusan is generálhat 1095-C űrlapot és a megfelelő 1094-C benyújtandó fájlokat az IRS (Internal Revenue Service) számára.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-195">You can also electronically generate Form 1095-C and the corresponding 1094-C transmittal files to send to the Internal Revenue Service (IRS).</span></span>

1. <span data-ttu-id="0ec3f-196">A **Juttatáskezelés** munkaterületen válassza az **ACA 1095-B űrlap** vagy az **ACA 1095-C űrlap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-196">In the **Benefits management** workspace, select **ACA 1095-B form** or **ACA 1095-C form**.</span></span>
2. <span data-ttu-id="0ec3f-197">Szükség szerint módosítsa a paramétereket, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-197">Change the parameters as required, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ec3f-198">Ha több mint 500 alkalmazottnak nyomtat 1095-C űrlapot, egynél több PDF-fájlt fog kapni.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-198">If you're printing 1095-C forms for more than 500 employees, you will receive more than one PDF file.</span></span> <span data-ttu-id="0ec3f-199">Javasoljuk, hogy a **Dokumentumkezelés paraméterei** lapon a **Maximális fájlméret megabájtban** mező értékét **150**-re növelje.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-199">We recommend that you increase the value of the **Maximum file size in megabytes** field on the **Document management parameters** page to **150**.</span></span> <span data-ttu-id="0ec3f-200">(Az oldal gyors megnyitásához használhatja a navigációs sáv keresőmezőjét.)</span><span class="sxs-lookup"><span data-stu-id="0ec3f-200">(To quickly open that page, you can use the search field on the navigation bar.)</span></span>
    >
    > ![A maximális fájlméret módosítása](./media/hr-benefits-management-aca-maximum-file-size.png)

3. <span data-ttu-id="0ec3f-202">A jelentések állapotának ellenőrzésére és megtekintésére használja a navigációs sáv keresőmezőjét az **Elektronikus jelentéskészítési feladatok** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-202">To check the status of your reports and view them, use the search field on the navigation bar to open the **Electronic reporting jobs** page.</span></span>

    ![Az Elektronikus jelentéskészítési feladatok oldal keresése](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. <span data-ttu-id="0ec3f-204">Válassza ki a megtekinteni kívánt jelentést, majd válassza a **Fájlok megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-204">Select the report to view, and then select **Show files**.</span></span>

    ![Fájlok megjelenítése](./media/hr-benefits-management-aca-show-files.png)

5. <span data-ttu-id="0ec3f-206">Válassza ki a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-206">Select **Open**.</span></span>

    ![Fájl megnyitása](./media/hr-benefits-management-aca-open-file.png)

6. <span data-ttu-id="0ec3f-208">Nyissa meg az irányítószámot a böngésző ablakának alján látható értesítési sávról, majd válassza ki a jelentést.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-208">From the Notification bar that appears at the bottom of the browser window, open the zip file, and then select the report.</span></span> <span data-ttu-id="0ec3f-209">Megtekintheti vagy kinyomtathatja a PDF-fájlt.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-209">You can view or print the PDF file.</span></span>

    ![Minta: 1095-C űrlap](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a><span data-ttu-id="0ec3f-211">ACA-fedezeti információk megtekintése</span><span class="sxs-lookup"><span data-stu-id="0ec3f-211">View ACA coverage information</span></span>

<span data-ttu-id="0ec3f-212">A **Dolgozói Affordable Care jogosultság** oldal a következő adatokat jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="0ec3f-212">The **Worker Affordable Care coverage** page shows the following information:</span></span>

- <span data-ttu-id="0ec3f-213">Az egyes fedezeti csoportokhoz hozzárendelt alkalmazottak</span><span class="sxs-lookup"><span data-stu-id="0ec3f-213">Employees who are assigned to each coverage group</span></span>
- <span data-ttu-id="0ec3f-214">Azok az alkalmazottak, akiknek nem kell szerepelniük a jelentésben</span><span class="sxs-lookup"><span data-stu-id="0ec3f-214">Employees who don't have to be included on a report</span></span>
- <span data-ttu-id="0ec3f-215">Nem hozzárendelt alkalmazottak</span><span class="sxs-lookup"><span data-stu-id="0ec3f-215">Unassigned employees</span></span>

<span data-ttu-id="0ec3f-216">Az adatok megtekintéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-216">To view this information, follow these steps.</span></span>

1. <span data-ttu-id="0ec3f-217">A **Juttatáskezelés** munkaterületen válassza az **Dolgozói Affordable Care fedezeti jogosultság** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-217">In the **Benefits management** workspace, select **Worker Affordable Care coverage**.</span></span>
2. <span data-ttu-id="0ec3f-218">A **Csoport neve** mezőben válasszon ki egy csoportot.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-218">In the **Group name** field, select a group.</span></span>

    ![ACA-fedezet megtekintése](./media/hr-benefits-management-aca-view-coverage.png)

<span data-ttu-id="0ec3f-220">Ha az Affordable Care fedezeti csoport bármely alapértelmezett értékét felülírták, egy csillag jelenik meg a módosított érték mellett.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-220">If any default values from the Affordable Care coverage group have been overridden, an asterisk appears next to the value that was changed.</span></span> <span data-ttu-id="0ec3f-221">Ha az értékek a tizenkét hónap mindegyikében megegyeznek, és nem bírálták felül őket, az értéket a rendszer a **Mind a 12 hónap** oszlopba nyomtatja.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-221">If the values for all 12 months are the same and haven't been overridden, the value appears in the **All 12 months** column.</span></span>

<span data-ttu-id="0ec3f-222">Azok az alkalmazottak is megtekinthetők, akik az ACA szerint nem bejelentendők, és akik esetében nincs szükség 1095-C űrlapra.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-222">You can view employees who are marked as not ACA-reportable, and who won't require a Form 1095-C.</span></span> <span data-ttu-id="0ec3f-223">A **Szűrés alapja:** mezőben válassza **Az ACA szerint nem bejelentendő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-223">In the **Filter by** field, select **Not ACA reportable**.</span></span>

<span data-ttu-id="0ec3f-224">Megtekintheti azokat az alkalmazottakat, akik nincsenek csoporthoz rendelve, vagy akik lejárt csoporthoz vannak hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-224">You can view employees who aren't assigned to a group, or who are assigned to an expired group.</span></span> <span data-ttu-id="0ec3f-225">A **Szűrés alapja:** mezőben válassza a **Nem hozzárendelt vagy lejárt csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-225">In the **Filter by** field, select **Unassigned or expired group**.</span></span>

### <a name="export-to-excel"></a><span data-ttu-id="0ec3f-226">Exportálás Excel-fájlba</span><span class="sxs-lookup"><span data-stu-id="0ec3f-226">Export to Excel</span></span>

<span data-ttu-id="0ec3f-227">Ha a listák bármelyikét exportálni szeretné Microsoft Excel alkalmazásba, kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-227">To export any of the lists to Microsoft Excel, follow these steps.</span></span>

1. <span data-ttu-id="0ec3f-228">Válassza a **Megnyitás Microsoft Office-ban** gombot.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-228">Select the **Open in Microsoft Office** button.</span></span>
2. <span data-ttu-id="0ec3f-229">Válassza a **HCM Human Resources ideiglenes tábla belső használatra** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-229">Select **HCM Human Resources temporary table for internal use**.</span></span>
3. <span data-ttu-id="0ec3f-230">Válassza a **Letöltés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-230">Select **Download**.</span></span>

### <a name="view-aca-reportable-dependents"></a><span data-ttu-id="0ec3f-231">ACA szerint bejelentendő eltartottak megtekintése</span><span class="sxs-lookup"><span data-stu-id="0ec3f-231">View ACA-reportable dependents</span></span>

<span data-ttu-id="0ec3f-232">Ha kötelező jelentenie az eltartott személyeket, mert munkáltatóként a munkavállaló által fizetett egészségügyi biztosítást nyújt, lehetőség van a juttatási csomagok által lefedett, **ACA szerint bejelentendő** megjelölésű eltartottak megtekintésére.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-232">If you must report covered individuals because you provide self-insured coverage, you can view dependents who are covered under benefit plans that are marked as **ACA reportable**.</span></span> <span data-ttu-id="0ec3f-233">A Művelet ablaktáblán válassza **Az eltartott fedezetének megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-233">On the Action Pane, select **View Dependent coverage**.</span></span>

![Eltartott fedezetének megtekintése](./media/hr-benefits-management-aca-view-dependent-coverage.png)

<span data-ttu-id="0ec3f-235">Megjelennek az alkalmazott eltartottakkal kapcsolatos fedezeti adatai.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-235">Coverage information for the employee's dependents is shown.</span></span>

![Függő fél jogosultsága](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> <span data-ttu-id="0ec3f-237">Az oldalon csak az **ACA szerint bejelentendő** típusú megjelölt juttatási tervek jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="0ec3f-237">The page shows only benefits plans that are marked as **ACA reportable**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]