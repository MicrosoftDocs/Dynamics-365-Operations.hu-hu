---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2019. január 23.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 135be837a82af8cee22d83c015a78da3b89b7978
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304622"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a><span data-ttu-id="53756-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2019. január 23.)</span><span class="sxs-lookup"><span data-stu-id="53756-103">What's new or changed in Dynamics 365 for Talent Core HR (January 23, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="53756-104">**Build 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="53756-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="53756-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="53756-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="53756-106">Változások</span><span class="sxs-lookup"><span data-stu-id="53756-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="53756-107">Az alkalmazotti fix kompenzáció importálása nem működik, ha új fix kompenzációs rekordot hoznak létre</span><span class="sxs-lookup"><span data-stu-id="53756-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="53756-108">Egy változtatás történt az alkalmazotti fix kompenzációs entitással kapcsolatosan a kompenzáció szintjének lekéréséhe az importálás során.</span><span class="sxs-lookup"><span data-stu-id="53756-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="53756-109">Ezen kiadás előtt egy üzenetben jelezte, hogy a szint szükséges.</span><span class="sxs-lookup"><span data-stu-id="53756-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="53756-110">A minimális egyenleg mező eltávolítása a szabadságkérelem párbeszédpanelből</span><span class="sxs-lookup"><span data-stu-id="53756-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="53756-111">A **Minimális egyenleg** mező el lett távolítva a **Szabadságkérelem** párbeszédpanelből.</span><span class="sxs-lookup"><span data-stu-id="53756-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="53756-112">Ez a módosítás érinti minden olyan területet, ahol szabadságot lehet igényelni.</span><span class="sxs-lookup"><span data-stu-id="53756-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="53756-113">Az adatok frissítése minden esetben nem frissült a kompenzációs szinteknél</span><span class="sxs-lookup"><span data-stu-id="53756-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="53756-114">Módosítás történt a fix kompenzációs konstrukciók kompenzációs szintjének frissítése terén.</span><span class="sxs-lookup"><span data-stu-id="53756-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="53756-115">Ez a módosítás feltölti adatokkal a kompenzációs szintet a munkavállalóhoz rendelt feladat fix terveinél.</span><span class="sxs-lookup"><span data-stu-id="53756-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="53756-116">Csak akkor érhetők el a Bérlistaadatok a Változások kezelése oldalon, ha Rendszergazdaként van bejelentkezve</span><span class="sxs-lookup"><span data-stu-id="53756-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="53756-117">Ez a módosítás bérszámfejtő szerepkörrel rendelkező alkalmazottak számára hozzáférést biztosít a bérlistaadatokhoz a **Módosítások idősora > Változások kezelése** lapon a beosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="53756-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="53756-118">Feladat mezők alapértelmezettek a beosztásokhoz</span><span class="sxs-lookup"><span data-stu-id="53756-118">Job fields default to positions</span></span>
<span data-ttu-id="53756-119">Egy beosztás feladatának módosításakor feladat mezők alapértelmezettek lesznek a beosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="53756-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="53756-120">Egy figyelmeztető üzenet jelenik meg, hogy fogadja el az alapértelmezett értékeket, vagy tartsa meg a meglévő értékeket ezekben a mezőkben.</span><span class="sxs-lookup"><span data-stu-id="53756-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="53756-121">Próbaidőszak és a naptár jövőben felvett alkalmazottak számára nem láthatók.</span><span class="sxs-lookup"><span data-stu-id="53756-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="53756-122">Ezzel a módosítással a **Próbaidő** és a **Naptár** mezők hozzá lettek adva a **Változások kezelése** oldalra jövőbeni és korábbi alkalmazottak adatbevitelének engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="53756-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23"></a><span data-ttu-id="53756-123">23-es platformfrissítés</span><span class="sxs-lookup"><span data-stu-id="53756-123">Platform update 23</span></span>
<span data-ttu-id="53756-124">Kisebb hibajavítások a 23-as platformfrissítés részeként.</span><span class="sxs-lookup"><span data-stu-id="53756-124">Minor bug fixes have been included as part of Platform update 23.</span></span> <span data-ttu-id="53756-125">További tudnivalókért lásd: [Újdonságok és változások a Dynamics 365 for Finance and Operations 23-as platformfrissítésében (2019. január)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="53756-125">For more information, see [What's new or changed in Dynamics 365 for Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 
