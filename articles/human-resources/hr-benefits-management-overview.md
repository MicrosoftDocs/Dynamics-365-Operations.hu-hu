---
title: Juttatáskezelés áttekintése
description: A juttatáskezelés funkció áttekintése a Dynamics 365 Human Resources alkalmazásban. Az alkalmazottak számára kiterjesztett juttatási lehetőségeket kínálhat könnyen használható online felületen.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 91a4425b4f020f90843bb3b0b280b7ee28463670
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230154"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="ab916-104">Juttatáskezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="ab916-104">Benefits management overview</span></span>

<span data-ttu-id="ab916-105">A versenyképesség megőrzéséhez juttatások széles választékát kell nyújtania, hogy felkeltse a legjobb alkalmazottak figyelmét, és meg is tudja tartani őket.</span><span class="sxs-lookup"><span data-stu-id="ab916-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="ab916-106">A szokásos juttatások, például az orvosi és a fogászati biztosítás mellett kiterjesztett szolgáltatásokat is kínálhat, például bevezetési támogatást, rekreációs programokat és ruházati pótlékokat.</span><span class="sxs-lookup"><span data-stu-id="ab916-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="ab916-107">A Microsoft Dynamics 365 Human Resources juttatáskezelés funkciója rugalmas megoldást kínál, amely a juttatási lehetőségek széles választékát támogatja.</span><span class="sxs-lookup"><span data-stu-id="ab916-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="ab916-108">A Human Resources szolgáltatás tartalmaz egy egyszerűen használható alkalmazotti felületet is, amelyen bemutathatja az ajánlatait.</span><span class="sxs-lookup"><span data-stu-id="ab916-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="ab916-109">A bővített juttatási konstrukciók lehetővé teszik egyedi juttatási konstrukciók létrehozását és kezelését, valamint összetett juttatásmérték-táblázatok és beágyazott szintek támogatását.</span><span class="sxs-lookup"><span data-stu-id="ab916-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="ab916-110">Az alkalmazotti élmény javításához könnyen készíthet juttatási programokat, csomagokat és automatikus igénylési szabályokat.</span><span class="sxs-lookup"><span data-stu-id="ab916-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="ab916-111">A rugalmas jóváírási programok lehetővé teszik az arányosítást a nyugdíjazás és az egyéb élettartam-események támogatásához.</span><span class="sxs-lookup"><span data-stu-id="ab916-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="ab916-112">A számos jogosultsági szabály biztosítja, hogy a megfelelő juttatásokat tudja szolgáltatni a megfelelő alkalmazottak számára.</span><span class="sxs-lookup"><span data-stu-id="ab916-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="ab916-113">A juttatások online regisztrálása könnyen használható megoldást nyújt az alkalmazottaknak.</span><span class="sxs-lookup"><span data-stu-id="ab916-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="ab916-114">A minősített életesemények feldolgozása támogatja a jövőbeli életeseményeket.</span><span class="sxs-lookup"><span data-stu-id="ab916-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="ab916-115">Ha szeretne hozzáférni a bemutató adatokhoz, újra kell telepítenie a tesztkörnyezetét.</span><span class="sxs-lookup"><span data-stu-id="ab916-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="ab916-116">Juttatáskezelés – ismert problémák</span><span class="sxs-lookup"><span data-stu-id="ab916-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="ab916-117">Rugalmas jóváírási programok</span><span class="sxs-lookup"><span data-stu-id="ab916-117">Flex credit programs</span></span>

<span data-ttu-id="ab916-118">A flex credit programhoz meghatározott teljes hitelkeret nem jelenik meg a **Dolgozói juttatási tervek** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="ab916-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="ab916-119">Ha egy rugalmas jóváírási programot úgy állított be, hogy **Nincs**arányosítási szabálya legyen, akkor egy hibát kap a **Dolgozói juttatási terv** képernyőn a tervek kiválasztása és megerősítése során.</span><span class="sxs-lookup"><span data-stu-id="ab916-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="ab916-120">Juttatáskezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="ab916-120">Enable Benefits management</span></span>

<span data-ttu-id="ab916-121">A cikk azt írja le, hogyan lehet bekapcsolni funkciókat a Human Resources szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="ab916-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="ab916-122">Arról is tájékoztat, hogy a Human Resources szolgáltatásban melyik meglévő funkciók lesznek lecserélve vagy letiltva, amikor bekapcsolja a juttatáskezelést.</span><span class="sxs-lookup"><span data-stu-id="ab916-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab916-123">Miután engedélyezte a juttatások kezelését egy **Termelési** környezetben, azt nem lehet letiltani.</span><span class="sxs-lookup"><span data-stu-id="ab916-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="ab916-124">Azt ajánljuk , hogy a **Termelési** környezetben történő engedélyezése előtt engedélyezze és tesztelje a juttatások kezelését egy **Teszt** környezetben.</span><span class="sxs-lookup"><span data-stu-id="ab916-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="ab916-125">Jelentősen különböznek egymástól a korábbi Juttatási funkciók és az új Juttatáskezelés funkciók – ezek további beállításokat igényelnek, és a termelésbe történő helyezés előtt tesztelni kell azokat.</span><span class="sxs-lookup"><span data-stu-id="ab916-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="ab916-126">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="ab916-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="ab916-127">Alkalmazottak adatainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-127">Configure employee information</span></span>

<span data-ttu-id="ab916-128">Ahhoz, hogy az alkalmazottakat juttatásokhoz lehessen regisztrálni, meg kell adnia a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="ab916-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="ab916-129">A **Fix kompenzációs konstrukcióban** egy alkalmazottat be kell regisztrálni a kezdő dátumra, és ki kell választania egy **Juttatásfizetési gyakoriságot** a **Foglalkoztatás részletei** részben a **Dolgozó** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="ab916-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="ab916-130">Ha olyan juttatási tervet hoz létre, amely nemen vagy életkoron alapuló arányokat használ, akkor meg kell adnia a születési dátumot és a nemet az alkalmazott számára a juttatási költség kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="ab916-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="ab916-131">A juttatáskezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-131">Configure Benefits management</span></span>

<span data-ttu-id="ab916-132">Az alkalmazottak juttatási konstrukcióinak létrehozása előtt konfigurálnia kell a konstrukciókhoz tartozó beállításokat.</span><span class="sxs-lookup"><span data-stu-id="ab916-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="ab916-133">A juttatáskezelés paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="ab916-134">Jogosultsági szabályok és beállítások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="ab916-135">A személyes kapcsolattartó jogosultsági beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="ab916-136">Fedezeti lehetőségek létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab916-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="ab916-137">Fizetési gyakoriságok beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="ab916-138">Életesemények típusának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="ab916-139">Költségvetési terv típusai</span><span class="sxs-lookup"><span data-stu-id="ab916-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="ab916-140">Okkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="ab916-141">Számkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="ab916-142">Díjak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="ab916-143">Levonások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="ab916-144">Várakozási napok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="ab916-145">Várakozási időszakok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="ab916-146">Kerekítési szabályok beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="ab916-147">Alkalmazási kategóriák létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab916-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="ab916-148">Foglalkoztatási típusok beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="ab916-149">Alkalmazotti önkiszolgáló rendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="ab916-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="ab916-150">Juttatási konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="ab916-150">Create benefit plans</span></span>

<span data-ttu-id="ab916-151">Ezek a cikkek a juttatási konstrukciók létrehozását ismertetik, beleértve a csomagokat és a rugalmas jóváírási programokat.</span><span class="sxs-lookup"><span data-stu-id="ab916-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="ab916-152">Juttatási tervek beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="ab916-153">Rugalmas hitelprogramok beállítása</span><span class="sxs-lookup"><span data-stu-id="ab916-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="ab916-154">Juttatási tervek feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ab916-154">Process benefit plans</span></span>

<span data-ttu-id="ab916-155">Néhány módosítását fel kell dolgoznia, hogy aktiválja azokat.</span><span class="sxs-lookup"><span data-stu-id="ab916-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="ab916-156">Felvételi jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ab916-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="ab916-157">Élettartam-események feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ab916-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="ab916-158">Élettartam-események módosításainak feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ab916-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="ab916-159">Élettartam-eseményekre vonatkozó jogosultságok feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ab916-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="ab916-160">Mértékmódosítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ab916-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

