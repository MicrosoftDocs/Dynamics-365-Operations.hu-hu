---
title: Juttatáskezelés áttekintése
description: A juttatáskezelés funkció áttekintése a Dynamics 365 Human Resources alkalmazásban. Az alkalmazottak számára kiterjesztett juttatási lehetőségeket kínálhat könnyen használható online felületen.
author: andreabichsel
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4ad94d81d7e8bedd3622b3e073e431bc4abaafff
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924230"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="795ed-104">Juttatáskezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="795ed-104">Benefits management overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="795ed-105">A versenyképesség megőrzéséhez juttatások széles választékát kell nyújtania, hogy felkeltse a legjobb alkalmazottak figyelmét, és meg is tudja tartani őket.</span><span class="sxs-lookup"><span data-stu-id="795ed-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="795ed-106">A szokásos juttatások, például az orvosi és a fogászati biztosítás mellett kiterjesztett szolgáltatásokat is kínálhat, például bevezetési támogatást, rekreációs programokat és ruházati pótlékokat.</span><span class="sxs-lookup"><span data-stu-id="795ed-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="795ed-107">A Microsoft Dynamics 365 Human Resources juttatáskezelés funkciója rugalmas megoldást kínál, amely a juttatási lehetőségek széles választékát támogatja.</span><span class="sxs-lookup"><span data-stu-id="795ed-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="795ed-108">A Human Resources szolgáltatás tartalmaz egy egyszerűen használható alkalmazotti felületet is, amelyen bemutathatja az ajánlatait.</span><span class="sxs-lookup"><span data-stu-id="795ed-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="795ed-109">A bővített juttatási konstrukciók lehetővé teszik egyedi juttatási konstrukciók létrehozását és kezelését, valamint összetett juttatásmérték-táblázatok és beágyazott szintek támogatását.</span><span class="sxs-lookup"><span data-stu-id="795ed-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="795ed-110">Az alkalmazotti élmény javításához könnyen készíthet juttatási programokat, csomagokat és automatikus igénylési szabályokat.</span><span class="sxs-lookup"><span data-stu-id="795ed-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="795ed-111">A rugalmas jóváírási programok lehetővé teszik az arányosítást a nyugdíjazás és az egyéb élettartam-események támogatásához.</span><span class="sxs-lookup"><span data-stu-id="795ed-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="795ed-112">A számos jogosultsági szabály biztosítja, hogy a megfelelő juttatásokat tudja szolgáltatni a megfelelő alkalmazottak számára.</span><span class="sxs-lookup"><span data-stu-id="795ed-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="795ed-113">A juttatások online regisztrálása könnyen használható megoldást nyújt az alkalmazottaknak.</span><span class="sxs-lookup"><span data-stu-id="795ed-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="795ed-114">A minősített életesemények feldolgozása támogatja a jövőbeli életeseményeket.</span><span class="sxs-lookup"><span data-stu-id="795ed-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="795ed-115">Ha szeretne hozzáférni a bemutató adatokhoz, újra kell telepítenie a tesztkörnyezetét.</span><span class="sxs-lookup"><span data-stu-id="795ed-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

>[!NOTE]
><span data-ttu-id="795ed-116">Most már testre szabhatja a Juttatások kezelése űrlapot.</span><span class="sxs-lookup"><span data-stu-id="795ed-116">You can now customize Benefits management forms.</span></span> <span data-ttu-id="795ed-117">A juttatási tervek **Fedezeti beállítás** űrlapjához mostantól a fedezeti díjakkal kapcsolatos egyéni mezőket is hozzáadhatja.</span><span class="sxs-lookup"><span data-stu-id="795ed-117">You can now add custom fields related to coverage rates to the **Coverage option** form for benefit plans.</span></span> <span data-ttu-id="795ed-118">További információkért az egyéni mezők felhasználásáról lásd: [Egyéni mezők](hr-developer-custom-fields.md).</span><span class="sxs-lookup"><span data-stu-id="795ed-118">For more information about working with custom fields, see [Custom fields](hr-developer-custom-fields.md).</span></span>
><span data-ttu-id="795ed-119">![Juttatások kezelésében egyéni mezők](media/hr-benefits-management-custom-fields.png)</span><span class="sxs-lookup"><span data-stu-id="795ed-119">![Benefits management custom fields](media/hr-benefits-management-custom-fields.png)</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="795ed-120">Juttatáskezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="795ed-120">Enable Benefits management</span></span>

<span data-ttu-id="795ed-121">A témakör azt írja le, hogyan lehet bekapcsolni funkciókat a Human Resources szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="795ed-121">This topic describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="795ed-122">Arról is tájékoztat, hogy a Human Resources szolgáltatásban melyik meglévő funkciók lesznek lecserélve vagy letiltva, amikor bekapcsolja a juttatáskezelést.</span><span class="sxs-lookup"><span data-stu-id="795ed-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="795ed-123">Miután engedélyezte a juttatások kezelését egy **Termelési** környezetben, azt nem lehet letiltani.</span><span class="sxs-lookup"><span data-stu-id="795ed-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="795ed-124">Azt ajánljuk , hogy a **Termelési** környezetben történő engedélyezése előtt engedélyezze és tesztelje a juttatások kezelését egy **Teszt** környezetben.</span><span class="sxs-lookup"><span data-stu-id="795ed-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="795ed-125">Jelentősen különböznek egymástól a korábbi Juttatási funkciók és az új Juttatáskezelés funkciók – ezek további beállításokat igényelnek, és a termelésbe történő helyezés előtt tesztelni kell azokat.</span><span class="sxs-lookup"><span data-stu-id="795ed-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="795ed-126">Szolgáltatások kezelése</span><span class="sxs-lookup"><span data-stu-id="795ed-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="795ed-127">Alkalmazottak adatainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-127">Configure employee information</span></span>

<span data-ttu-id="795ed-128">Ahhoz, hogy az alkalmazottakat juttatásokhoz lehessen regisztrálni, meg kell adnia a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="795ed-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="795ed-129">A **Fix kompenzációs konstrukcióban** egy alkalmazottat be kell regisztrálni a kezdő dátumra, és ki kell választania egy **Juttatásfizetési gyakoriságot** a **Foglalkoztatás részletei** részben a **Dolgozó** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="795ed-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="795ed-130">Ha van olyan alkalmazottja, aki kiegészítő kompenzációt kap, mint a jutalékok, akkor az alkalmazotti rekordból származó **Juttatások évi fizetése** összegét veheti fel.</span><span class="sxs-lookup"><span data-stu-id="795ed-130">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="795ed-131">Az emberi erőforrások a fix kompenzációs éves összeg helyett a fedezeti összegek meghatározásakor a **Juttatások évi fizetésének** összegét fogják használni.</span><span class="sxs-lookup"><span data-stu-id="795ed-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="795ed-132">A **juttatások évi fizetésének** érvényesnek kell lennie az alkalmazott kezdő dátumától vagy a juttatási időszak kezdetével, amelyik a legújabb.</span><span class="sxs-lookup"><span data-stu-id="795ed-132">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="795ed-133">Ha egy alkalmazottnál egy fix kompenzációs és juttatás éves fizetési összege is rögzítve van, akkor a juttatások évi fizetését használják a fedezeti összegek meghatározására.</span><span class="sxs-lookup"><span data-stu-id="795ed-133">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="795ed-134">Ha olyan juttatási tervet hoz létre, amely nemen vagy életkoron alapuló arányokat használ, akkor meg kell adnia a születési dátumot és a nemet az alkalmazott számára a juttatási költség kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="795ed-134">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="795ed-135">A juttatáskezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-135">Configure Benefits management</span></span>

<span data-ttu-id="795ed-136">Az alkalmazottak juttatási konstrukcióinak létrehozása előtt konfigurálnia kell a konstrukciókhoz tartozó beállításokat.</span><span class="sxs-lookup"><span data-stu-id="795ed-136">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="795ed-137">A juttatáskezelés paramétereinek beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-137">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="795ed-138">Jogosultsági szabályok és beállítások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-138">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="795ed-139">A személyes kapcsolattartó jogosultsági beállításainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-139">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="795ed-140">Fedezeti lehetőségek létrehozása</span><span class="sxs-lookup"><span data-stu-id="795ed-140">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="795ed-141">Fizetési gyakoriságok beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-141">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="795ed-142">Életesemények típusának konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-142">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="795ed-143">Költségvetési terv típusai</span><span class="sxs-lookup"><span data-stu-id="795ed-143">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="795ed-144">Okkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-144">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="795ed-145">Számkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-145">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="795ed-146">Díjak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-146">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="795ed-147">Levonások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-147">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="795ed-148">Várakozási napok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-148">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="795ed-149">Várakozási időszakok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-149">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="795ed-150">Kerekítési szabályok beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-150">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="795ed-151">Alkalmazási kategóriák létrehozása</span><span class="sxs-lookup"><span data-stu-id="795ed-151">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="795ed-152">Foglalkoztatási típusok beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-152">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="795ed-153">Alkalmazotti önkiszolgáló rendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="795ed-153">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="795ed-154">Juttatási konstrukciók létrehozása</span><span class="sxs-lookup"><span data-stu-id="795ed-154">Create benefit plans</span></span>

<span data-ttu-id="795ed-155">Ezek a cikkek a juttatási konstrukciók létrehozását ismertetik, beleértve a csomagokat és a rugalmas jóváírási programokat.</span><span class="sxs-lookup"><span data-stu-id="795ed-155">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="795ed-156">Juttatási tervek beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-156">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="795ed-157">Rugalmas hitelprogramok beállítása</span><span class="sxs-lookup"><span data-stu-id="795ed-157">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="795ed-158">Juttatási tervek feldolgozása</span><span class="sxs-lookup"><span data-stu-id="795ed-158">Process benefit plans</span></span>

<span data-ttu-id="795ed-159">Néhány módosítását fel kell dolgoznia, hogy aktiválja azokat.</span><span class="sxs-lookup"><span data-stu-id="795ed-159">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="795ed-160">Felvételi jogosultság feldolgozása</span><span class="sxs-lookup"><span data-stu-id="795ed-160">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="795ed-161">Élettartam-események feldolgozása</span><span class="sxs-lookup"><span data-stu-id="795ed-161">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="795ed-162">Élettartam-események módosításainak feldolgozása</span><span class="sxs-lookup"><span data-stu-id="795ed-162">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="795ed-163">Élettartam-eseményekre vonatkozó jogosultságok feldolgozása</span><span class="sxs-lookup"><span data-stu-id="795ed-163">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="795ed-164">Mértékmódosítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="795ed-164">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]