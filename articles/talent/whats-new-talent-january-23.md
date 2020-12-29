---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2019. január 23.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
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
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f97462f088fc1a3cb94f2a34204fc09f1cd66fb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461348"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-23-2019"></a><span data-ttu-id="30b79-103">Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2019. január 23.)</span><span class="sxs-lookup"><span data-stu-id="30b79-103">What's new or changed in Dynamics 365 Talent - Core HR (January 23, 2019)</span></span>

<span data-ttu-id="30b79-104">**Build 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="30b79-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="30b79-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="30b79-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="30b79-106">Változások</span><span class="sxs-lookup"><span data-stu-id="30b79-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="30b79-107">Az alkalmazotti fix kompenzáció importálása nem működik, ha új fix kompenzációs rekordot hoznak létre</span><span class="sxs-lookup"><span data-stu-id="30b79-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="30b79-108">Egy változtatás történt az alkalmazotti fix kompenzációs entitással kapcsolatosan a kompenzáció szintjének lekéréséhe az importálás során.</span><span class="sxs-lookup"><span data-stu-id="30b79-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="30b79-109">Ezen kiadás előtt egy üzenetben jelezte, hogy a szint szükséges.</span><span class="sxs-lookup"><span data-stu-id="30b79-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="30b79-110">A minimális egyenleg mező eltávolítása a szabadságkérelem párbeszédpanelből</span><span class="sxs-lookup"><span data-stu-id="30b79-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="30b79-111">A **Minimális egyenleg** mező el lett távolítva a **Szabadságkérelem** párbeszédpanelből.</span><span class="sxs-lookup"><span data-stu-id="30b79-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="30b79-112">Ez a módosítás érinti minden olyan területet, ahol szabadságot lehet igényelni.</span><span class="sxs-lookup"><span data-stu-id="30b79-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="30b79-113">Az adatok frissítése minden esetben nem frissült a kompenzációs szinteknél</span><span class="sxs-lookup"><span data-stu-id="30b79-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="30b79-114">Módosítás történt a fix kompenzációs konstrukciók kompenzációs szintjének frissítése terén.</span><span class="sxs-lookup"><span data-stu-id="30b79-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="30b79-115">Ez a módosítás feltölti adatokkal a kompenzációs szintet a munkavállalóhoz rendelt feladat fix terveinél.</span><span class="sxs-lookup"><span data-stu-id="30b79-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="30b79-116">Csak akkor érhetők el a Bérlistaadatok a Változások kezelése oldalon, ha Rendszergazdaként van bejelentkezve</span><span class="sxs-lookup"><span data-stu-id="30b79-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="30b79-117">Ez a módosítás bérszámfejtő szerepkörrel rendelkező alkalmazottak számára hozzáférést biztosít a bérlistaadatokhoz a **Módosítások idősora > Változások kezelése** lapon a beosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="30b79-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="30b79-118">Feladat mezők alapértelmezettek a beosztásokhoz</span><span class="sxs-lookup"><span data-stu-id="30b79-118">Job fields default to positions</span></span>
<span data-ttu-id="30b79-119">Egy beosztás feladatának módosításakor feladat mezők alapértelmezettek lesznek a beosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="30b79-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="30b79-120">Egy figyelmeztető üzenet jelenik meg, hogy fogadja el az alapértelmezett értékeket, vagy tartsa meg a meglévő értékeket ezekben a mezőkben.</span><span class="sxs-lookup"><span data-stu-id="30b79-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="30b79-121">Próbaidőszak és a naptár jövőben felvett alkalmazottak számára nem láthatók.</span><span class="sxs-lookup"><span data-stu-id="30b79-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="30b79-122">Ezzel a módosítással a **Próbaidő** és a **Naptár** mezők hozzá lettek adva a **Változások kezelése** oldalra jövőbeni és korábbi alkalmazottak adatbevitelének engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="30b79-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23-for-finance-and-operations"></a><span data-ttu-id="30b79-123">A Finance and Operations 23-es platformfrissítése</span><span class="sxs-lookup"><span data-stu-id="30b79-123">Platform update 23 for Finance and Operations</span></span>
<span data-ttu-id="30b79-124">Kisebb hibajavítások a Finance and Operations 23-as platformfrissítés részeként.</span><span class="sxs-lookup"><span data-stu-id="30b79-124">Minor bug fixes have been included as part of Platform update 23 for Finance and Operations.</span></span> <span data-ttu-id="30b79-125">További tudnivalókért lásd: [Újdonságok és változások a Dynamics 365 Finance and Operations 23-as platformfrissítésében (2019. január)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="30b79-125">For more information, see [What's new or changed in Dynamics 365 Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 
