---
title: Affordable Care Act (ACA) jelentések létrehozása
description: Az Affordable Care Act (ACA) jelentéskészítés létrehoz egy 1095-B és egy 1095-C űrlapot, támogatva az ACA **munkáltatói felhatalmazás** részét.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: f46a8efefd8e41c08bf4de49cfec856dc0a86da1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468035"
---
# <a name="generate-aca-reports"></a><span data-ttu-id="284bc-103">ACA-jelentések generálása</span><span class="sxs-lookup"><span data-stu-id="284bc-103">Generate ACA reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="284bc-104">Az Affordable Care Act (ACA) jelentéskészítés létrehoz egy 1095-B és egy 1095-C űrlapot, támogatva az ACA **munkáltatói felhatalmazás** részét.</span><span class="sxs-lookup"><span data-stu-id="284bc-104">Affordable Care Act (ACA) reporting generates forms 1095-B and 1095-C in support of the **Employer Mandate** portion of the Affordable Care Act.</span></span>

> [!NOTE]
> <span data-ttu-id="284bc-105">Az ACA-jelentéskészítés csak az Egyesült Államokban engedélyezett jogi személyek esetén.</span><span class="sxs-lookup"><span data-stu-id="284bc-105">ACA reporting is only enabled for legal entities in the United States.</span></span>

## <a name="getting-started"></a><span data-ttu-id="284bc-106">Első lépések</span><span class="sxs-lookup"><span data-stu-id="284bc-106">Getting started</span></span>

<span data-ttu-id="284bc-107">Az adatoknak az 1095-B és 1095-C űrlapok esetében történő nyomon követéséhez először létre kell hozni egy vagy több Affordable Care fedezeti csoportot.</span><span class="sxs-lookup"><span data-stu-id="284bc-107">To track information for forms 1095-B and 1095-C, you must first create one or more Affordable care coverage groups.</span></span> <span data-ttu-id="284bc-108">Az Affordable Care fedezeti csoportok a következő állapotra utalnak:</span><span class="sxs-lookup"><span data-stu-id="284bc-108">Affordable Care coverage groups indicate:</span></span>

- <span data-ttu-id="284bc-109">Az alkalmazott fedezeti ajánlata</span><span class="sxs-lookup"><span data-stu-id="284bc-109">The offer of coverage for an employee</span></span>
- <span data-ttu-id="284bc-110">Az alkalmazott részesedése a legkisebb költségalapú havi díjból, ha költség magasabb a szövetségi szegénységi küszöbnél</span><span class="sxs-lookup"><span data-stu-id="284bc-110">The employee’s share of the lowest cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="284bc-111">A munkáltató által használt Safe Harbor, ha van ilyen</span><span class="sxs-lookup"><span data-stu-id="284bc-111">Safe Harbor used by the employer, if applicable</span></span>

<span data-ttu-id="284bc-112">Az Affordable Care fedezeti csoportok használata lehetővé teszi az adatok kezelését ezeknek a mezőknek az esetében anélkül, hogy minden alkalmazotti rekordot módosítani kellene abban az esetben, amikor a feltételek ugyanazok.</span><span class="sxs-lookup"><span data-stu-id="284bc-112">Affordable Care coverage groups allow you to manage the information for these fields without changing every employee record where the conditions are the same.</span></span> <span data-ttu-id="284bc-113">Az Affordable Care fedezeti csoportokat egyszerűen hozzárendelheti egy vagy több alkalmazotthoz az oldal **Tömeges hozzárendelés** funkciójával.</span><span class="sxs-lookup"><span data-stu-id="284bc-113">You can easily assign Affordable Care coverage groups to one or more employees by using the **Mass assign** option on the page.</span></span>

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a><span data-ttu-id="284bc-114">Fedezeti csoportok több változatának karbantartása</span><span class="sxs-lookup"><span data-stu-id="284bc-114">Maintaining multiple versions of a coverage group</span></span>

<span data-ttu-id="284bc-115">A fedezeti csoportok több változatának karbantartása lehetséges.</span><span class="sxs-lookup"><span data-stu-id="284bc-115">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="284bc-116">Ez a funkció anélkül teszi lehetővé a módosításokat, hogy új csoportot kelljen létrehozni és alkalmazottakat kelljen hozzárendelni a csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="284bc-116">This functionality allows you to make changes without having to create a new group and reassign employees to it.</span></span> 

<span data-ttu-id="284bc-117">Miután létrehozta az ACA fedezeti csoportokat, tömegesen hozzárendelheti a csoportokat az alkalmazottakhoz a **Tömeges hozzárendelés** lehetőséggel.</span><span class="sxs-lookup"><span data-stu-id="284bc-117">After you’ve created ACA coverage groups, you can mass assign the groups to employees with the **Mass assignment** option.</span></span> <span data-ttu-id="284bc-118">Azt is jelezheti külön-külön, hogy kell-e követni és jelenteni az ACA-adatokat, és hozzárendelhet egy alkalmazottat egy Afordable Care fedezeti csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="284bc-118">You can also individually indicate whether to track and report ACA information, and assign an employee to an Affordable Care coverage group.</span></span>

<span data-ttu-id="284bc-119">Nem kell nyomon követni az ACA bizonyos fedezeti adatait, például a részmunkaidős alkalmazottak esetében.</span><span class="sxs-lookup"><span data-stu-id="284bc-119">You don't need to track some ACA coverage information, such as for part-time employees.</span></span> <span data-ttu-id="284bc-120">Ebben az esetben állítsa a **Jogosultság bejelentése** mezőt **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="284bc-120">In this case, set the **Report coverage** field to **No**.</span></span> <span data-ttu-id="284bc-121">Annak ellenére, hogy minden, nyomon követhető ACA-információval rendelkező alkalmazottat hozzá kell rendelnie egy Affordable Care fedezeti csoporthoz, az alábbi értékeket továbbra is módosíthatja a különböző értékekkel rendelkező hónapokra vonatkozóan:</span><span class="sxs-lookup"><span data-stu-id="284bc-121">Although you must assign each employee with trackable ACA information to an Affordable Care coverage group, you can still change the following options for months with different values:</span></span>

- <span data-ttu-id="284bc-122">**Jogosultságra vonatkozó ajánlat**</span><span class="sxs-lookup"><span data-stu-id="284bc-122">**Offer of coverage**</span></span>
- <span data-ttu-id="284bc-123">**Alkalmazott költségmegosztása**</span><span class="sxs-lookup"><span data-stu-id="284bc-123">**Employee share of cost**</span></span>
- <span data-ttu-id="284bc-124">**Safe Harbor**</span><span class="sxs-lookup"><span data-stu-id="284bc-124">**Safe Harbor**</span></span>

<span data-ttu-id="284bc-125">Kivételek megadásához bármely Affordable Care fedezeti csoport értékének esetében kattintson a **Dolgozó részletes adatai** oldalon található **Affordable Care fedezet** lehetőségre, amely a **További információk** szakaszban található a **Foglalkoztatás** lapon.</span><span class="sxs-lookup"><span data-stu-id="284bc-125">To enter exceptions for Affordable Care coverage group values, select the **Affordable Care Coverage** link on the **Worker detail** page under the **Additional information** section on the **Employment tab**.</span></span>

## <a name="reporting-health-care-coverage"></a><span data-ttu-id="284bc-126">Egészségügyi fedezeti jelentés</span><span class="sxs-lookup"><span data-stu-id="284bc-126">Reporting health care coverage</span></span>

<span data-ttu-id="284bc-127">Annak a nyomon követése mellett, hogy egészségbiztosítást ajánlottak fel teljes munkaidős alkalmazottak számára, ha a munkáltató a munkáltató által támogatott, a munkavállaló által fizetett egészségügyi biztosítást kínál, amelyre az alkalmazott fel van iratkozva (függetlenül attól, hogy a foglalkoztatottsági állapota teljes munkaidős vagy részmunkaidős), további információt kell jelenteni a 1095-C űrlapon.</span><span class="sxs-lookup"><span data-stu-id="284bc-127">In addition to tracking health insurance coverage offered to full-time employees, if the employer offers employer-sponsored self-insured health coverage for which the employee is enrolled (regardless of whether their employment status is full-time or part-time), additional information needs to be reported on the 1095-C.</span></span> <span data-ttu-id="284bc-128">A munkáltató által támogatott juttatási csomagban részesülő összes alkalmazottat (és eltartottjaikat) meg kell adni annak a hónapnak a jelentésében, amelyben a csomag vonatkozik rájuk.</span><span class="sxs-lookup"><span data-stu-id="284bc-128">Each employee (including dependents) covered by the employer-sponsored benefit plans needs to be included on the report for the months they were covered.</span></span> 

<span data-ttu-id="284bc-129">Azt, hogy minden juttatácsomagot jelenteni kell-e, az **ACA szerint bejelentendő** négyzet bejelölésével adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="284bc-129">You can indicate whether or not each benefit plan must be reported by selecting the **ACA reportable** check box.</span></span>

<span data-ttu-id="284bc-130">Ezenkívül, ha az alkalmazott úgy döntött, hogy a juttatás kiterjedjen eltartottjai bármelyikére, minden egyes alkalmazott esetében megadhatja azokat a dátumokat, amikor a juttatás kiterjedt az eltartottra a **Juttatások kezelése** lapon.</span><span class="sxs-lookup"><span data-stu-id="284bc-130">In addition, if employees have chosen to have any of their dependents covered under a benefit, you can indicate the dates the dependent was covered for each employee on the **Maintain benefits** page.</span></span> <span data-ttu-id="284bc-131">Ha jelezni szeretné, hogy az eltartott jogosult a juttatásra, kattintson a **Szerkesztés** gombra az **Eltartottak** gyorslap műveleti ablaktáblájában.</span><span class="sxs-lookup"><span data-stu-id="284bc-131">To indicate that the dependent is covered under the benefit, select the **Edit** button in the action pane of the **Dependents** fast tab.</span></span>

<span data-ttu-id="284bc-132">A **Függő fél jogosultsági dátumának kezelése** lapon adhatja meg a dátumokat, amikor a juttatás vonatkozott az eltartottra.</span><span class="sxs-lookup"><span data-stu-id="284bc-132">On the **Dependent coverage date manager** page, you can indicate the dates the dependent was covered by the benefit.</span></span> <span data-ttu-id="284bc-133">Ha ezen a lapon dátumokat ad meg, ezzel automatikusan bejelöli a **Fedezve** jelölőnégyzetet a **Juttatások karbantartása** oldalon.</span><span class="sxs-lookup"><span data-stu-id="284bc-133">Entering dates on this page will automatically select the **Covered** checkbox on the **Maintain benefits** page.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="284bc-134">1095-B és 1095-C űrlapok létrehozása</span><span class="sxs-lookup"><span data-stu-id="284bc-134">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="284bc-135">Lehetőség van a 1095-B és 1095-C űrlapok létrehozására a terméken belül, és a továbbításukra az összes alkalmazottnak.</span><span class="sxs-lookup"><span data-stu-id="284bc-135">You can also generate 1095-B and 1095-C forms from within the product, and distribute them to each of your employees.</span></span> <span data-ttu-id="284bc-136">A rendszer elektronikusan is generálhat 1095-C űrlapokat és az 1094-C IRS benyújtandó fájlokat.</span><span class="sxs-lookup"><span data-stu-id="284bc-136">The system can also electronically generate 1095-C forms and the 1094-C IRS transmittal files.</span></span>  

<span data-ttu-id="284bc-137">A 1095-C űrlap létrehozásakor adja meg a megfelelő adóévet, és jelölje, hogy szükséges-e társadalombiztosítási számok maszkolása.</span><span class="sxs-lookup"><span data-stu-id="284bc-137">When generating the 1095-C form, enter the appropriate tax year and indicate if social security numbers should be masked.</span></span> <span data-ttu-id="284bc-138">Ha több mint 500 alkalmazottnak nyomtat 1095-C űrlapot, egynél több PDF-fájlt fog kapni.</span><span class="sxs-lookup"><span data-stu-id="284bc-138">If you're printing 1095-C forms for more than 500 employees, you'll receive more than one PDF file.</span></span> <span data-ttu-id="284bc-139">Azt ajánljuk, hogy növelje meg a **Maximális fájlméret** értékét a **Dokumentumkezelés paraméterei** ablakban 150 MB-ra.</span><span class="sxs-lookup"><span data-stu-id="284bc-139">It’s recommended that you increase the **Maximum file size** in the **Document management parameters** window to 150 MB.</span></span>

## <a name="viewing-information"></a><span data-ttu-id="284bc-140">Információk megtekintése</span><span class="sxs-lookup"><span data-stu-id="284bc-140">Viewing information</span></span>

<span data-ttu-id="284bc-141">A **Dolgozói Affordable Care jogosultság** oldalon tekintheti meg, hogy mely alkalmazottak vannak hozzárendelve az egyes fedezeti csoportokhoz, mely alkalmazottakat nem kell feltüntetni a jelentésekben, és mely alkalmazottak nincsenek hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="284bc-141">You can use the **Worker Affordable Care coverage** page to see which employees have been assigned to each coverage group, which employees don’t need to be included on a report, and which employees are unassigned.</span></span>

<span data-ttu-id="284bc-142">Ha az Affordable Care fedezeti csoport bármely alapértelmezett értékét felülírták, csillag jelenik meg a módosított érték mellett.</span><span class="sxs-lookup"><span data-stu-id="284bc-142">If any of the default values from the Affordable Care coverage group have been overridden, an asterisk will appear next to the value that was changed.</span></span> <span data-ttu-id="284bc-143">Ha az értékek a tizenkét hónap mindegyikében megegyeznek, és nem lettek felülbírálva, az értéket a rendszer a **Mind a 12 hónap** oszlopba nyomtatja.</span><span class="sxs-lookup"><span data-stu-id="284bc-143">If the values for all 12 months are the same and haven’t been overridden, the value will print in the **All 12 months** column.</span></span>

<span data-ttu-id="284bc-144">A lekérdezés ablak segítségével megtekintheti, hogy mely alkalmazottaknál található meg az a jelölés, hogy nem kell jelenteni őket az ACA vonatkozásában.</span><span class="sxs-lookup"><span data-stu-id="284bc-144">You can also use the inquiry window to understand which employees have been flagged as not ACA reportable.</span></span> <span data-ttu-id="284bc-145">Nem kell követni, hogy felkínáltak-e nekik fedezetet, és nem szükséges kiadni számukra az 1095-C űrlapot az év végén.</span><span class="sxs-lookup"><span data-stu-id="284bc-145">You don’t need to track whether coverage was offered to them and won't need to issue a 1095-C to them at the end of the year.</span></span> <span data-ttu-id="284bc-146">**Az ACA szerint nem bejelentendő** lehetőség kiválasztásával a **Szűrés alapja:** mezőben létre lehet hozni azoknak az alkalmazottaknak a listáját, akik nem kapnak 1095-C űrlapot.</span><span class="sxs-lookup"><span data-stu-id="284bc-146">Select **Not ACA reportable** in the **Filter by** field to generate a list of all employees who won't receive a 1095-C.</span></span>

<span data-ttu-id="284bc-147">Ezenkívül megtekinthető az összes hozzárendelés nélküli alkalmazott (az **ACA-jogosultság bejelentése** mező üres), valamint azok az alkalmazottak, akik olyan Affordable Care fedezeti csoporthoz vannak hozzárendelve, amely az **Év** mezőben kiválasztott évre nézve lejárt.</span><span class="sxs-lookup"><span data-stu-id="284bc-147">In addition, you can view any employees who are unassigned (the **ACA Report coverage** field is empty) or who have been assigned to an Affordable Care coverage group that is expired for the year selected in the **Year** field.</span></span>

<span data-ttu-id="284bc-148">A bármely szűrési beállítás segítségével létrehozott alkalmazottlisták az Excel programba exportálhatók.</span><span class="sxs-lookup"><span data-stu-id="284bc-148">You can export lists of employees that were generated using any of the filtering options to Excel.</span></span>

<span data-ttu-id="284bc-149">Ha jelentenie kell az eltartott személyeket, mert munkáltatóként a munkavállaló által fizetett egészségügyi biztosítást nyújt, lehetőség van a juttatási csomagok által lefedett, **ACA szerint bejelentendő** megjelölésű eltartottak megtekintésére.</span><span class="sxs-lookup"><span data-stu-id="284bc-149">If you need to report covered individuals because you provide self-insured coverage, you can view any dependents covered under benefit plans marked as **ACA reportable**.</span></span> <span data-ttu-id="284bc-150">Válassza **A függő fél jogosultságának megtekintése** lehetőséget a műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="284bc-150">Select **View Dependent coverage** on the action pane.</span></span>

> [!NOTE]
> <span data-ttu-id="284bc-151">A lekérdezési ablakban csak az **ACA szerint bejelentendő** megjelölésű juttatáscsomagok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="284bc-151">Only benefit plans marked as **ACA reportable** display in the inquiry window.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]