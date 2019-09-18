---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. május 6.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c541bac532e878c8493a60d95c05c9104d4b96e1
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741544"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-6-2019"></a><span data-ttu-id="ee2f0-103">Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. május 6.)</span><span class="sxs-lookup"><span data-stu-id="ee2f0-103">What's new or changed in Dynamics 365 for Talent (May 6, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ee2f0-104">Ez a témakör a Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-104">This topic describes features that are either new or changed in Dynamics 365 for Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="ee2f0-105">Változások az Attract-ben</span><span class="sxs-lookup"><span data-stu-id="ee2f0-105">Changes in Attract</span></span>

### <a name="select-optional-documents-upon-offer-creation"></a><span data-ttu-id="ee2f0-106">Választható dokumentumok kiválasztása ajánlat létrehozásakor</span><span class="sxs-lookup"><span data-stu-id="ee2f0-106">Select optional documents upon offer creation</span></span>

<span data-ttu-id="ee2f0-107">Ha kiválaszt egy ajánlaticsomag-sablont, akkor most a program felkéri, hogy válassza ki a megfelelő, választható dokumentumokat a sablonból.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-107">When you select an offer package template, Attract now prompts you to select the applicable, optional documents from that package template.</span></span> <span data-ttu-id="ee2f0-108">Az ajánlat előkészítése közben más opcionális dokumentumokat is hozzáadhat.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-108">You can add other optional documents while preparing the offer.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="ee2f0-109">Változások az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="ee2f0-109">Changes in Onboard</span></span>

<span data-ttu-id="ee2f0-110">Ebben a verzióban kisebb hibajavítások találhatók a Dynamics 365 Talent: Onboard alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-110">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="ee2f0-111">A Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="ee2f0-111">Changes in Core HR</span></span>

<span data-ttu-id="ee2f0-112">A szakaszban ismertetett módosítások a 8.1.2282-ös buildre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-112">Changes described in this section apply to build number 8.1.2282.</span></span> <span data-ttu-id="ee2f0-113">A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-113">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="platform-update-26"></a><span data-ttu-id="ee2f0-114">26-as platformfrissítés</span><span class="sxs-lookup"><span data-stu-id="ee2f0-114">Platform update 26</span></span>

<span data-ttu-id="ee2f0-115">26. Platform frissítésével kapcsolatos további tudnivalókat lásd: [Előnézeti funkciók a Dynamics 365 for Finance and Operations 26. platformfrissítésében (2019. május)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span><span class="sxs-lookup"><span data-stu-id="ee2f0-115">For additional details about Platform update 26, see [Preview features in Dynamics 365 for Finance and Operations platform update 26 (May 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26).</span></span> 

### <a name="common-data-service-entity-support-for-custom-fields"></a><span data-ttu-id="ee2f0-116">Common Data Service entitás-támogatás egyéni mezőkhöz</span><span class="sxs-lookup"><span data-stu-id="ee2f0-116">Common Data Service entity support for custom fields</span></span>

<span data-ttu-id="ee2f0-117">A heti kiadásban a következő entitások már támogatják az egyéni mezőket: Juttatási számítás gyakorisága, Juttatási számítási mértéke, Juttatás típusa, Munkanaptár, Munkanaptár-szünnap, Fizetési ciklus és Dolgozóazonosító típusok.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-117">In this week's release, the following entities now support custom fields: Benefit calc frequency, Benefit calc rate, Benefit type, Work calendar, Work calendar holiday, Pay cycle, and Worker identification types.</span></span>

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a><span data-ttu-id="ee2f0-118">Tömeges felvétel elhagyása, a rangsorolás alapja "Szolgálati idő" értékre állítása nem frissíti a kezdeti elhatárolási mértéket (318526)</span><span class="sxs-lookup"><span data-stu-id="ee2f0-118">Leave mass enrollment, changing the tier basis to "Seniority date" doesn't refresh the initial accrual rate (318526)</span></span>

<span data-ttu-id="ee2f0-119">Az alkalmazottak tömeges felvételekor és a szintek alapjának módosításakor a kezdeti elhatárolás most a kiválasztott szintalapot tükrözi.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-119">When you mass enroll employees and change the tier basis, the initial accrual now reflects the tier basis that you selected.</span></span>

### <a name="workflow-showing-duplicate-place-holders-313636"></a><span data-ttu-id="ee2f0-120">Ismétlődő tárolókat megjelenítő munkafolyamat (313636)</span><span class="sxs-lookup"><span data-stu-id="ee2f0-120">Workflow showing duplicate place holders (313636)</span></span>

<span data-ttu-id="ee2f0-121">Az ebben a verzióban bekövetkező változtatások a munkafolyamatok értesítéseinek elküldésekor kiküszöbölik a helyőrzők duplikálását.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-121">Changes in this release eliminate duplication of placeholders when workflow notifications are sent.</span></span>

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a><span data-ttu-id="ee2f0-122">A Dimenzió mezők nem frissülnek a „Megnyitás Excel alkalmazásban” használata során (176261).</span><span class="sxs-lookup"><span data-stu-id="ee2f0-122">Dimension fields aren't updated when using "Open in Excel" (176261)</span></span>

<span data-ttu-id="ee2f0-123">Ebben a verzióban most frissítheti a pénzügyi dimenziót a **Megnyitás Excelalkalmazás** funkcióval a **Dolgozó** lapon.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-123">With this release, you can now update financial dimension using **Open in Excel** from the **Worker** page.</span></span> 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a><span data-ttu-id="ee2f0-124">A dolgozó részére a Common Data Service megoldásban létrehozott cím nincs szinkronizálva a Talent alkalmazással (317555).</span><span class="sxs-lookup"><span data-stu-id="ee2f0-124">Worker address created in Common Data Service isn't synced to Talent (317555)</span></span>

<span data-ttu-id="ee2f0-125">Ezzel a módosítással a Common Data Service megoldásban létrehozott címeket a Talent Core HR frissíti.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-125">With this change, addresses created in Common Data Service are updated in Talent Core HR.</span></span>


## <a name="in-preview"></a><span data-ttu-id="ee2f0-126">Előnézetben</span><span class="sxs-lookup"><span data-stu-id="ee2f0-126">In preview</span></span>

### <a name="new-page-to-validate-position-hierarchy-data"></a><span data-ttu-id="ee2f0-127">Új oldal a beosztás-hierarchia adatainak ellenőrzéséhez</span><span class="sxs-lookup"><span data-stu-id="ee2f0-127">New page to validate position hierarchy data</span></span>

<span data-ttu-id="ee2f0-128">A személyzeti osztály munkatársai (HR) és a rendszergazdák most ellenőrizni tudják a vezetői hierarchiát a véletlenül importált körkörös hivatkozások tekintetében.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-128">Human resources (HR) and administrators can now validate the managerial hierarchy for any circular references that might have inadvertently been imported.</span></span> <span data-ttu-id="ee2f0-129">Ezt az új lapot a **Szervezeti adminisztráció > Hivatkozások > Beosztások > Beosztáshierarchia ellenőrzése** helyről érheti el.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-129">You can access this new page from **Organizational administration > Links > Positions > Position hierarchy validation**.</span></span>

### <a name="specify-reason-codes-on-leave-types"></a><span data-ttu-id="ee2f0-130">Okkódok meghatározása a távollét típusaihoz</span><span class="sxs-lookup"><span data-stu-id="ee2f0-130">Specify reason codes on leave types</span></span>

<span data-ttu-id="ee2f0-131">A szervezeteknek kiegészítő információkra lehet szüksége a szabadságkérelmekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-131">Organizations might require additional information about time-off requests.</span></span> <span data-ttu-id="ee2f0-132">Immár megadhat okkódokat egy adott távolléttípushoz, és megengedheti az alkalmazottak számára okkód választását szabadságkérelmükhöz.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-132">You can now specify reason codes for leave types and let employees select a reason code on their time-off requests.</span></span>

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a><span data-ttu-id="ee2f0-133">Okkódok kérése adott szabadságtípusokhoz a távollétkérelmek során</span><span class="sxs-lookup"><span data-stu-id="ee2f0-133">Require reason codes for specific leave types on time-off requests</span></span>

<span data-ttu-id="ee2f0-134">Előfordulhat, hogy a szervezetek okkódok beállítását kérik, bizonyos távolléttípusokhoz, amikor a munkavállalók távolléti kérelmeket nyújtanak be.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-134">Organizations might require reason codes for specific leave types when employees submit time-off requests.</span></span> <span data-ttu-id="ee2f0-135">Ez a követelmény a vállalat szabályzata vagy a törvényi követelmények miatt állhat fenn.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-135">This requirement might exist because of company policy or regulatory requirements.</span></span> <span data-ttu-id="ee2f0-136">Immár meghatározhatja, mely szabadságtípusokhoz szükséges okkód, és alkalmazottaktól megkövetelheti okkód megadását a szabadságtípushoz a távollétkérelmekhez.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-136">You can now specify which leave types require a reason code, and you can require that employees provide a reason code for the leave type on their time-off requests.</span></span>

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a><span data-ttu-id="ee2f0-137">Egy szabadság és a távolléti tranzakciólista átadása a HR-nek</span><span class="sxs-lookup"><span data-stu-id="ee2f0-137">Provide a leave and absence transaction list for HR</span></span>

<span data-ttu-id="ee2f0-138">Az alkalmazotti szabadidő követésének képessége és a szabadidő kiszámításának ismerete azon túl. hogy segít a HR-nek alkalmazott kérdések megválaszolásában, pontos szabadságmegítéléseket biztosít a munkavállalóknak.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-138">The ability to track employee time off and understand how time off is calculated not only helps HR answer employee questions, but also helps ensure accurate time-off awards for employees.</span></span> <span data-ttu-id="ee2f0-139">HR új nézetet kap a tranzakciókhoz (támogatások, könyvelések, helyesbítések és kérelmek) így a HR munkatársai láthatják az egyenlegek okait.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-139">HR now has a new view into the transactions (grants, accruals, adjustments, and requests), so that HR staff can view the reasons behind balances.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="ee2f0-140">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="ee2f0-140">Coming soon</span></span>

### <a name="indicate-instance-type-when-provisioning-talent"></a><span data-ttu-id="ee2f0-141">Példány típusának jelzése a Talent kiépítése alkalmával</span><span class="sxs-lookup"><span data-stu-id="ee2f0-141">Indicate instance type when provisioning Talent</span></span>

<span data-ttu-id="ee2f0-142">Ha egy új Talent példányt telepít akkor jelezheti, hogy a példány típusa **Termelési** vagy **Védőfal**típusú, és lehetővé teszi az új szolgáltatások korai tesztelését.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-142">When provisioning a new instance of Talent, you will be able to indicate whether the instance type is **Production** or **Sandbox**, allowing for early testing of new features.</span></span> <span data-ttu-id="ee2f0-143">Minden létező Talent példányt a termelési példány típusára lesz frissítve.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-143">All existing Talent instances will be updated to the Production instance type.</span></span> <span data-ttu-id="ee2f0-144">Ha azt szeretné, hogy a meglévő példányok frissítve legyenek a védőfal példányra, forduljon a támogatáshoz a módosítási kérelem kezdeményezéséhez.</span><span class="sxs-lookup"><span data-stu-id="ee2f0-144">If you want one of your existing instances to be updated to the Sandbox instance type, please contact Support to initiate the change request.</span></span>
