---
title: Szabadság és távollét kezelése
description: Ez a témakör a Szabadság- és távollét kezelési modulról ad áttekintést.
author: andreabichsel
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3376a9aec5c0003e9cc7c076c4d221a697df61ce
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461427"
---
# <a name="leave-and-absence-management"></a><span data-ttu-id="23924-103">Szabadság és távollét kezelése</span><span class="sxs-lookup"><span data-stu-id="23924-103">Leave and absence management</span></span>

<span data-ttu-id="23924-104">A **Szabadság- és távollét kezelése** modul rugalmas keretrendszert biztosít a távollétet kezelő folyamat meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="23924-104">The **Leave and absence management** module offers a flexible framework for defining the absence management process.</span></span> <span data-ttu-id="23924-105">Szabadság- és távolléti tervek hozhatók létre annak meghatározásához, hogyan történik az alkalmazottak elhatárolása vagy szabadságolása.</span><span class="sxs-lookup"><span data-stu-id="23924-105">Leave and absence plans can be created to determine how employees accrue or are granted time off.</span></span> <span data-ttu-id="23924-106">Amint regisztrálnak egy tervbe, az alkalmazottak távolléti kérelmeket nyújthatnak be a vezetőkhöz jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="23924-106">After employees are enrolled in a plan, they can submit time-off requests for approval by managers.</span></span> <span data-ttu-id="23924-107">A szabadság nyomon követése lehetővé teszi, hogy az első szintű vezető és az emberi erőforrás (HR) vezető egyaránt megtekinthessék, ki van szabadságon, és mennyi ideje van még hátra.</span><span class="sxs-lookup"><span data-stu-id="23924-107">Leave tracking lets both first-level managers and Human Resources (HR) managers see who is taking time off and how much time off each employee still has.</span></span>  

<span data-ttu-id="23924-108">A Szabadság és távollét kezelése a következő funkciókkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="23924-108">Leave and absence management provides the following features:</span></span> 

- <span data-ttu-id="23924-109">**Szabadság- és távolléttípusok meghatározása**</span><span class="sxs-lookup"><span data-stu-id="23924-109">**Define leave and absence types.**</span></span>

    <span data-ttu-id="23924-110">A Szabadságtípusok meghatározzák az alkalmazottak számára elérhető különböző típusú távolléteket.</span><span class="sxs-lookup"><span data-stu-id="23924-110">Leave types define the various types of absences that employees can report.</span></span> <span data-ttu-id="23924-111">Mivel ezek a típusok a felhasználó által definiáltak, testreszabhatóak a szervezet számára.</span><span class="sxs-lookup"><span data-stu-id="23924-111">Because these types are user-defined, they can be tailored to your organization.</span></span> <span data-ttu-id="23924-112">Néhány jellemző Szabadságtípus a fizetett szabadság (PTO), szabadság, rövid távú fogyatékosság, esküdtszéki kötelezettség (ez a szabadságtípus csak az Egyesült Államokra jellemző) és gyász.</span><span class="sxs-lookup"><span data-stu-id="23924-112">Some typical leave types include paid time off (PTO), leave, short-term disability, jury duty (this leave type is specific to the United States), and bereavement.</span></span> 

- <span data-ttu-id="23924-113">**Határozza meg a vállalkozásához illeszkedő szabadság- és távolléti terveket.**</span><span class="sxs-lookup"><span data-stu-id="23924-113">**Define leave and absence plans that are tiered to fit your business.**</span></span>

    <span data-ttu-id="23924-114">A szabadság- és távolléti tervek úgy határozhatók meg, hogy a könyvelés meghatározott gyakorisággal történjen, például éves, havi vagy félhavi gyakorisággal.</span><span class="sxs-lookup"><span data-stu-id="23924-114">Leave and absence plans can be defined so that accrual occurs at specific frequencies, such as annually, monthly, or semimonthly.</span></span> <span data-ttu-id="23924-115">A tervek meghatározhatók támogatásként, ahol egyetlen könyvelés történik egy meghatározott dátumon.</span><span class="sxs-lookup"><span data-stu-id="23924-115">Plans can also be defined as a grant, where a single accrual occurs on a specific date.</span></span> 

    <span data-ttu-id="23924-116">A szabadságtervek gyakran tartalmaznak rétegeket, ahol bizonyos alkalmazottcsoportok további juttatásokat kapnak a vállalatnál eltöltött idejük alapján.</span><span class="sxs-lookup"><span data-stu-id="23924-116">Leave plans often contain tiers, where some groups of employees receive additional benefits, based on the amount of time that they have been with the organization.</span></span> <span data-ttu-id="23924-117">A felhasználó által definiált rétegek lehetővé teszik a további juttatási órákba történő automatikus beléptetést a meghatározott dátumfeltételek alapján.</span><span class="sxs-lookup"><span data-stu-id="23924-117">These user-defined tiers enable automatic enrollment in additional benefit hours, based on the date criteria that are defined.</span></span> <span data-ttu-id="23924-118">A szabadságtervek beállíthatók úgy is, hogy maximális átviteli összeget vagy minimális egyenleget érvényesítsenek, megakadályozva, hogy az alkalmazottak az összegyűjtött juttatási órákat meghaladó juttatási óraszámot használjanak.</span><span class="sxs-lookup"><span data-stu-id="23924-118">Leave plans can also be configured to enforce a maximum carry-over amount or a minimum balance, to prevent employees from using more benefit hours than they have accrued.</span></span> 

    <span data-ttu-id="23924-119">A tipikus szabadságtervek közé tartoznak a többszintű tervek, amelyek az új alkalmazottaknak 80 órás fizetett szabadságot adnak, és 60 hónapos munkavégzés után 120 órát.</span><span class="sxs-lookup"><span data-stu-id="23924-119">Typical leave plans include tiered plans that grant a benefit of 80 hours of PTO to new employees but a benefit of 120 hours after 60 months of service.</span></span> <span data-ttu-id="23924-120">A további tervek mozgatható szabadságolást vagy a pozícióalapú juttatásokat tartalmazhatnak, például csak az ügyvezetőknek járó juttatási órákat.</span><span class="sxs-lookup"><span data-stu-id="23924-120">Additional plans might grant floating holidays or position-based benefits, such as executive-only benefit hours.</span></span>

- <span data-ttu-id="23924-121">**Vegye fel az alkalmazottakat a szabadság- és távolléti tervekbe egyénileg vagy a feladatfeltételek alapján történő tömeges hozzárendeléssel.**</span><span class="sxs-lookup"><span data-stu-id="23924-121">**Enroll employees in leave and absence plans individually or through mass assignment that is based on job criteria.**</span></span>

    <span data-ttu-id="23924-122">Több feladattal kapcsolatos szűrő használható egy alkalmazotti csoport szabadságtervhez történő hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="23924-122">Several job-related filters can be used to assign a group of employees to a leave plan.</span></span> <span data-ttu-id="23924-123">A HR-vezetők megtekintheti, hogy az alkalmazott milyen szabadság- és távolléti tervbe van felvéve.</span><span class="sxs-lookup"><span data-stu-id="23924-123">HR managers can view an employee to see what leave and absence plans the employee is enrolled in.</span></span> <span data-ttu-id="23924-124">Alternatív megoldásként a HR-vezetők megtekinthetik az összes tervet és a kapcsolódó alkalmazotti jogosultságokat.</span><span class="sxs-lookup"><span data-stu-id="23924-124">Alternatively, HR managers can view all plans and the related employee enrollments.</span></span>

- <span data-ttu-id="23924-125">**Szabadság- és távolléti tervek felfüggesztése**</span><span class="sxs-lookup"><span data-stu-id="23924-125">**Suspend leave and absence plans.**</span></span>

    <span data-ttu-id="23924-126">A szabadság- és távolléti tervek felfüggeszthetők ezek inaktívvá tétele és a további könyvelések megakadályozása érdekében.</span><span class="sxs-lookup"><span data-stu-id="23924-126">Leave and absence plans can be suspended to make them inactive and prevent additional accruals.</span></span> <span data-ttu-id="23924-127">A könyvelést a rendszer az alkalmazott munkaviszonyának befejeződésekor felfüggeszti.</span><span class="sxs-lookup"><span data-stu-id="23924-127">Accruals are suspended for employees if their employment ends.</span></span>  

- <span data-ttu-id="23924-128">**Jogosultságok és támogatások állíthatók be.**</span><span class="sxs-lookup"><span data-stu-id="23924-128">**Adjust entitlements and grants.**</span></span>

    <span data-ttu-id="23924-129">Az alkalmazott magasabb tervszintbe vehető fel egy dolgozóspecifikus dátum segítségével, amely felülírja az alkalmazott alapértelmezett ajánlatát.</span><span class="sxs-lookup"><span data-stu-id="23924-129">An employee can be enrolled in a higher plan tier by using a worker-specific date to override the employee's default plan offering.</span></span> <span data-ttu-id="23924-130">Az alkalmazottak manuálisan módosíthatják szabadság- és távolléti egyenlegüket a felvétel időpontjában, vagy a HR-es tetszőleges időpontban manuálisan helyesbítheti az adatokat.</span><span class="sxs-lookup"><span data-stu-id="23924-130">Employees can receive a manual adjustment to their leave and absence balance at the time of plan enrollment, or HR can make a manual adjustment at any time.</span></span> 

- <span data-ttu-id="23924-131">**Használjon munkafolyamatot a távolléti kérésekre.**</span><span class="sxs-lookup"><span data-stu-id="23924-131">**Apply a workflow to time-off requests.**</span></span>

     <span data-ttu-id="23924-132">A munkafolyamatot testre szabhatja és a távolléti kérelmekre alkalmazhatja a szervezete követelményeinek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="23924-132">A workflow can be customized and applied to time-off requests to meet the organization’s requirements.</span></span>  

- <span data-ttu-id="23924-133">**Kövesse nyomon az alkalmazottak távolléti egyenlegét.**</span><span class="sxs-lookup"><span data-stu-id="23924-133">**Track employee absence balances.**</span></span>

    <span data-ttu-id="23924-134">Az alkalmazottak, a felettesük és a HR-es megtekinthetik a szabadság- és távolléti egyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="23924-134">Employees, their manager, and HR can view leave and absence balances.</span></span> <span data-ttu-id="23924-135">A HR-vezető interaktív jelentések segítségével nyomon követheti a tervbe való belépés és távollét egyenlegét típus szerint.</span><span class="sxs-lookup"><span data-stu-id="23924-135">HR can use interactive reports to track plan enrollments and time-off balances by type.</span></span> 

- <span data-ttu-id="23924-136">**Távolléti kérelmek beadása.**</span><span class="sxs-lookup"><span data-stu-id="23924-136">**Submit time-off requests.**</span></span>

    <span data-ttu-id="23924-137">Az alkalmazottak távolléti kérelmeket nyújthatnak be a rendelkezésre álló órák számához képest.</span><span class="sxs-lookup"><span data-stu-id="23924-137">Employees can submit time-off requests against their available hours.</span></span> <span data-ttu-id="23924-138">A kérelmek egyszerű egynapos kérelmek vagy több napos kérelmek lehetnek, amelyek többféle szabadság- és távolléti típust tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="23924-138">Requests can be simple single-day requests or multiple-day requests that include multiple leave and absence types.</span></span> <span data-ttu-id="23924-139">Ha a munkafolyamat nincs engedélyezve, a rendszer automatikusan jóváhagyja a kéréseket.</span><span class="sxs-lookup"><span data-stu-id="23924-139">If a workflow isn't enabled, the requests are automatically approved.</span></span> <span data-ttu-id="23924-140">Ha munkafolyamat engedélyezve van, a jóváhagyás lehet automatikus vagy be lehet állítani egy láttamozást a munkafolyamat-konfigurációjától függően.</span><span class="sxs-lookup"><span data-stu-id="23924-140">If a workflow is enabled, the approval can be automatic, or it can require sign-off, depending on the workflow configuration.</span></span>
