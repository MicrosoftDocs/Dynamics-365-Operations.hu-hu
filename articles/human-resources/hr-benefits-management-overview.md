---
title: Juttatáskezelés – áttekintés
description: A juttatáskezelés Dynamics 365 Human Resources szolgáltatásbeli előzetes funkciójának áttekintése. Az alkalmazottak számára kiterjesztett juttatási lehetőségeket kínálhat könnyen használható online felületen.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029463"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="efabb-104">Juttatáskezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="efabb-104">Benefits management overview</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="efabb-105">A versenyképesség megőrzéséhez juttatások széles választékát kell nyújtania, hogy felkeltse a legjobb alkalmazottak figyelmét, és meg is tudja tartani őket.</span><span class="sxs-lookup"><span data-stu-id="efabb-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="efabb-106">A szokásos juttatások, például az orvosi és a fogászati biztosítás mellett kiterjesztett szolgáltatásokat is kínálhat, például bevezetési támogatást, rekreációs programokat és ruházati pótlékokat.</span><span class="sxs-lookup"><span data-stu-id="efabb-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="efabb-107">A Microsoft Dynamics 365 Human Resources juttatáskezelésének előzetes funkciója rugalmas megoldást kínál, amely a juttatási lehetőségek széles választékát támogatja.</span><span class="sxs-lookup"><span data-stu-id="efabb-107">The Benefits management preview feature in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="efabb-108">A Human Resources szolgáltatás tartalmaz egy egyszerűen használható alkalmazotti felületet is, amelyen bemutathatja az ajánlatait.</span><span class="sxs-lookup"><span data-stu-id="efabb-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="efabb-109">A bővített juttatási konstrukciók lehetővé teszik egyedi juttatási konstrukciók létrehozását és kezelését, valamint összetett juttatásmérték-táblázatok és beágyazott szintek támogatását.</span><span class="sxs-lookup"><span data-stu-id="efabb-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="efabb-110">Az alkalmazotti élmény javításához könnyen készíthet juttatási programokat, csomagokat és automatikus igénylési szabályokat.</span><span class="sxs-lookup"><span data-stu-id="efabb-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="efabb-111">A rugalmas jóváírási programok lehetővé teszik az arányosítást a nyugdíjazás és az egyéb élettartam-események támogatásához.</span><span class="sxs-lookup"><span data-stu-id="efabb-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="efabb-112">A számos jogosultsági szabály biztosítja, hogy a megfelelő juttatásokat tudja szolgáltatni a megfelelő alkalmazottak számára.</span><span class="sxs-lookup"><span data-stu-id="efabb-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="efabb-113">A juttatások online regisztrálása könnyen használható megoldást nyújt az alkalmazottaknak.</span><span class="sxs-lookup"><span data-stu-id="efabb-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="efabb-114">A minősített élettartam-események feldolgozása együttműködik az alkalmazotti önkiszolgáló rendszerrel, és a jövőbeli élettartam-eseményeket is támogatja.</span><span class="sxs-lookup"><span data-stu-id="efabb-114">Qualified life event processing integrates with Employee self service, and also supports future life events.</span></span>

<span data-ttu-id="efabb-115">Ha szeretne hozzáférni a bemutató adatokhoz, újra kell telepítenie a tesztkörnyezetét.</span><span class="sxs-lookup"><span data-stu-id="efabb-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

<span data-ttu-id="efabb-116">Közvetlen visszajelzést vagy hibajelentést a következő címre küldhet: D365BenefitsPreview@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="efabb-116">You can provide direct feedback or report issues to:  D365BenefitsPreview@microsoft.com.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="efabb-117">Juttatáskezelés – ismert problémák</span><span class="sxs-lookup"><span data-stu-id="efabb-117">Benefits management known issues</span></span>

### <a name="eligibility-processing"></a><span data-ttu-id="efabb-118">Jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efabb-118">Eligibility processing</span></span>

<span data-ttu-id="efabb-119">Ha jogosultságokat futtat olyan juttatásokra, amelyek 1–5x-ös fizetést, a fizetés százalékát és a fix összeg fedezeti összegét használják, akkor a **Juttatási részletek** beállítás dátumát az **Alkalmazott kezdési dátuma** értékre kell állítania az **Alkalmazási előzmények** között.</span><span class="sxs-lookup"><span data-stu-id="efabb-119">When running eligibility for benefits that use a 1-5X Salary, % of Salary, and Flat Amount coverage amount, you must set the **Benefit details** date to the **Employee start date** in **Employment history**.</span></span> <span data-ttu-id="efabb-120">Meg kell adnia a **Ledolgozott órák**, a **Fizetési gyakoriság** és a **Évi juttatások fizetési összege** értéket is.</span><span class="sxs-lookup"><span data-stu-id="efabb-120">You must also include **Hours worked**, **Payment frequency**, and **Annual benefits salary amount**.</span></span> <span data-ttu-id="efabb-121">Ha a dolgozónak fix kompenzációja van, adja meg a **Ledolgozott órák** és a **Fizetési gyakoriság** értéket.</span><span class="sxs-lookup"><span data-stu-id="efabb-121">If the worker has fixed compensation, enter **Hours worked** and **Payment frequency**.</span></span> <span data-ttu-id="efabb-122">A rendszer kiszámítja az éves fizetés összegét.</span><span class="sxs-lookup"><span data-stu-id="efabb-122">The annual salary amount will calculate.</span></span> <span data-ttu-id="efabb-123">Ha az alkalmazott bérezéses, akkor a **Ledolgozott órák** értéket nem kell megadni.</span><span class="sxs-lookup"><span data-stu-id="efabb-123">If the employee is salaried, you don't need to enter **Hours worked**.</span></span> <span data-ttu-id="efabb-124">Javasoljuk, hogy új dolgozók létrehozásakor először adja meg a fix kompenzációt.</span><span class="sxs-lookup"><span data-stu-id="efabb-124">We recommend that when creating new workers, enter fixed compensation first.</span></span> <span data-ttu-id="efabb-125">A juttatás részleteire vonatkozó rekord frissítéséhez lépjen a következőre: **Dolgozó > Dolgozói előzmények > Foglalkoztatás részletei**.</span><span class="sxs-lookup"><span data-stu-id="efabb-125">To update the benefit details record, navigate to **Worker > Worker history > Employment details**.</span></span> <span data-ttu-id="efabb-126">Állítsa be a dátumot a dolgozó kezdési dátumára.</span><span class="sxs-lookup"><span data-stu-id="efabb-126">Adjust the date to the worker's start date.</span></span>

### <a name="employee-self-service"></a><span data-ttu-id="efabb-127">Alkalmazotti önkiszolgáló rendszer</span><span class="sxs-lookup"><span data-stu-id="efabb-127">Employee self-service</span></span>

<span data-ttu-id="efabb-128">A rendszer nem számítja ki az alkalmazotti összeget az életbiztosítás fedezeti összegének frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="efabb-128">Employee amount doesn't calculate when updating the coverage amount for life insurance.</span></span> <span data-ttu-id="efabb-129">Például ha egy alkalmazottnak életbiztosítási csomagot ajánl fel, akkor egészen 50 000 dollár fedezeti összegig választhatnak 0,36 dollár/1000 dollár fedezeti költségen.</span><span class="sxs-lookup"><span data-stu-id="efabb-129">For example, when an employee is offered a life insurance plan, they can select up to $50,000 in coverage at a cost of $.36 per $1,000 of coverage.</span></span>  <span data-ttu-id="efabb-130">Amikor az alkalmazott frissíti a fedezet összegét, az alkalmazotthoz kapcsolódó költség nulla marad.</span><span class="sxs-lookup"><span data-stu-id="efabb-130">When the employee updates the coverage amount, the employee’s associated cost remains at zero.</span></span>

<span data-ttu-id="efabb-131">Olyan juttatási konstrukció esetében, amely csak az adott konstrukciótípus egyszeri kiválasztását teszi lehetővé, a felhasználó hibaüzenetet kap, ha a konstrukció kiválasztása után megpróbálja lemondani a konstrukciót.</span><span class="sxs-lookup"><span data-stu-id="efabb-131">For a benefit plan that only allows a single selection of that plan type, the user receives an error if they attempt to waive a plan after selecting a plan.</span></span> <span data-ttu-id="efabb-132">Például egy felhasználó kiválaszt egy egyészségügyi konstrukciót, és kosárba teszi.</span><span class="sxs-lookup"><span data-stu-id="efabb-132">For example, a user selects a medical plan and places it in their cart.</span></span> <span data-ttu-id="efabb-133">A felhasználó ezután kiválasztja a **Lemondás** lehetőséget, ezzel lemondva a másik egészségügyi konstrukciót.</span><span class="sxs-lookup"><span data-stu-id="efabb-133">The user then selects **Waive** for another medical plan.</span></span> <span data-ttu-id="efabb-134">A felhasználó hibaüzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="efabb-134">The user will receive an error.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="efabb-135">Juttatáskezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="efabb-135">Enable Benefits management</span></span>

<span data-ttu-id="efabb-136">A juttatáskezelés előzetes funkció, és csak **Teszt** környezetekben érhető el.</span><span class="sxs-lookup"><span data-stu-id="efabb-136">Benefits management is a preview feature, and is only available in **Sandbox** environments.</span></span> <span data-ttu-id="efabb-137">Ezek a cikkek azt írják le, hogyan lehet bekapcsolni az előzetes funkciókat a Human Resources szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="efabb-137">These articles describe how to turn on preview features in Human Resources.</span></span> <span data-ttu-id="efabb-138">Arról is tájékoztatást adnak, hogy a Human Resources szolgáltatásban melyik meglévő funkciók lesznek lecserélve vagy letiltva, amikor bekapcsolja a juttatáskezelést.</span><span class="sxs-lookup"><span data-stu-id="efabb-138">They also tell which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

- [<span data-ttu-id="efabb-139">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="efabb-139">Manage features</span></span>](hr-admin-manage-features.md)
- [<span data-ttu-id="efabb-140">Előzetes funkció: juttatások kezelése</span><span class="sxs-lookup"><span data-stu-id="efabb-140">Preview feature: Benefits management</span></span>](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a><span data-ttu-id="efabb-141">A juttatáskezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-141">Configure Benefits management</span></span>

<span data-ttu-id="efabb-142">Az alkalmazottak juttatási konstrukcióinak létrehozása előtt konfigurálnia kell a konstrukciókhoz tartozó beállításokat.</span><span class="sxs-lookup"><span data-stu-id="efabb-142">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="efabb-143">A juttatáskezelés paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-143">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="efabb-144">Jogosultsági szabályok és beállítások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-144">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="efabb-145">A személyes kapcsolattartó jogosultsági beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-145">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="efabb-146">Fedezeti beállítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="efabb-146">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="efabb-147">Fizetési gyakoriságok beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-147">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="efabb-148">Élettartamesemény-típusok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-148">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="efabb-149">Konstrukciótípusok létrehozása</span><span class="sxs-lookup"><span data-stu-id="efabb-149">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="efabb-150">Okkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-150">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="efabb-151">Szintkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-151">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="efabb-152">Mértékek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-152">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="efabb-153">Levonások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-153">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="efabb-154">Várakozási napok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-154">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="efabb-155">Várakozási időszakok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-155">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="efabb-156">Kerekítési szabályok beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-156">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="efabb-157">Foglalkoztatási kategóriák létrehozása</span><span class="sxs-lookup"><span data-stu-id="efabb-157">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="efabb-158">Foglalkoztatási típusok beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-158">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="efabb-159">Alkalmazotti önkiszolgáló rendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-159">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="efabb-160">Juttatási konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="efabb-160">Create benefit plans</span></span>

<span data-ttu-id="efabb-161">Ezek a cikkek a juttatási konstrukciók létrehozását ismertetik, beleértve a csomagokat és a rugalmas jóváírási programokat.</span><span class="sxs-lookup"><span data-stu-id="efabb-161">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="efabb-162">Juttatási konstrukciók beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-162">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="efabb-163">Dolgozói juttatási konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="efabb-163">Create worker benefit plans</span></span>](hr-benefits-plans-worker.md)
- [<span data-ttu-id="efabb-164">Rugalmas jóváírási programok beállítása</span><span class="sxs-lookup"><span data-stu-id="efabb-164">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)
- [<span data-ttu-id="efabb-165">Jövőbeli élettartam-események konfigurálása</span><span class="sxs-lookup"><span data-stu-id="efabb-165">Configure future life events</span></span>](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="efabb-166">Juttatási konstrukciók feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efabb-166">Process benefit plans</span></span>

<span data-ttu-id="efabb-167">Néhány módosítását fel kell dolgoznia, hogy aktiválja azokat.</span><span class="sxs-lookup"><span data-stu-id="efabb-167">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="efabb-168">Felvételi jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efabb-168">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="efabb-169">Élettartam-események feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efabb-169">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="efabb-170">Élettartam-események módosításainak feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efabb-170">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="efabb-171">Élettartam-eseményekre vonatkozó jogosultságok feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efabb-171">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="efabb-172">Mértékmódosítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efabb-172">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

