---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. október 16.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
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
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d5f2aea5fcc81d0b4c1d8a392a3e56c888440a94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461373"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-16-2018"></a><span data-ttu-id="31e17-103">Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. október 16.)</span><span class="sxs-lookup"><span data-stu-id="31e17-103">What's new or changed in Dynamics 365 Talent - Core HR (October 16, 2018)</span></span>

<span data-ttu-id="31e17-104">**Build 8.1.1067**</span><span class="sxs-lookup"><span data-stu-id="31e17-104">**Build 8.1.1067**</span></span>

<span data-ttu-id="31e17-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="31e17-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-managers-to-update-time-off-requests"></a><span data-ttu-id="31e17-106">A távollétkérelmek frissítésének engedélyezése a vezetők számára</span><span class="sxs-lookup"><span data-stu-id="31e17-106">Allow managers to update time off requests</span></span>

<span data-ttu-id="31e17-107">Az alkalmazotti távollétkérelmeket kell frissíteni kell a munkafolyamatban történő jóváhagyást követően.</span><span class="sxs-lookup"><span data-stu-id="31e17-107">Employee time off requests may need to be updated after they are approved through the workflow.</span></span> <span data-ttu-id="31e17-108">Sok esetben a vezető végzi ezeket a frissítéseket, az alkalmazott nevében.</span><span class="sxs-lookup"><span data-stu-id="31e17-108">In many cases, the manager makes these updates on the employee’s behalf.</span></span> <span data-ttu-id="31e17-109">Ez a funkció lehetővé teszi a vezetőknek a távollét frissítését vagy a távollétkérelmek visszavonását a munkavállalóik nevében.</span><span class="sxs-lookup"><span data-stu-id="31e17-109">This new feature provides the ability for managers to update time off or cancel time off requests on behalf of their employees.</span></span> <span data-ttu-id="31e17-110">Ezt a funkciót a **Munka más nevében** paraméter szabályozza, amely az **Emberi erőforrások - paraméterek** oldalon állítható be.</span><span class="sxs-lookup"><span data-stu-id="31e17-110">This capability is controlled by the **Work on behalf** parameter that can be set on the **Human Resource Parameters** page.</span></span> 
 
## <a name="allow-hr-to-update-time-off-requests"></a><span data-ttu-id="31e17-111">A távollétkérelmek frissítésének engedélyezése a HR számára</span><span class="sxs-lookup"><span data-stu-id="31e17-111">Allow HR to update time off requests</span></span>

<span data-ttu-id="31e17-112">Hasonlóan a fenti funkcióhoz, szükséges lehet, hogy a HR frissítse a a munkavállalók távollétkérelmét miután azok jóváhagyták-e a munkafolyamaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="31e17-112">Similar to the feature above, employee time off requests may need to be updated by HR after they have been previously approved through the workflow.</span></span> <span data-ttu-id="31e17-113">Ez a funkció lehetővé teszi a HR-felhasználók számára a távollétkérelmek frissítését.</span><span class="sxs-lookup"><span data-stu-id="31e17-113">This feature provides the ability for HR users to update time off requests.</span></span> <span data-ttu-id="31e17-114">Ez a képesség a **Személyek** munkaterületen és a **Dolgozó** lapon kapcsolható be a **Távollét megtekintése** beállítással.</span><span class="sxs-lookup"><span data-stu-id="31e17-114">The capability is enabled in the **People** workspace and on the **Worker** page, using a new option called **View time off**.</span></span> <span data-ttu-id="31e17-115">Ezeken az oldalakon HR felhasználók megtekinthetik és frissíthetik a távollét-tranzakciókat, hasonlóan ahhoz, ahogy a vezetők elvégezhetik ezeket a műveleteket.</span><span class="sxs-lookup"><span data-stu-id="31e17-115">On those pages, HR users can view requests and update time off transactions, similar to how managers can perform these actions.</span></span>

<span data-ttu-id="31e17-116">A biztonsági feladat, amely szabályozza a hozzáférést ehhez a funkcióhoz a következő:</span><span class="sxs-lookup"><span data-stu-id="31e17-116">The security duty that controls access to this functionality is:</span></span>
- <span data-ttu-id="31e17-117">Feladat: Dolgozóspecifikus szabadság- és távolléti folyamatok karbantartása</span><span class="sxs-lookup"><span data-stu-id="31e17-117">Duty: Maintain worker-specific leave and absence processes.</span></span>
- <span data-ttu-id="31e17-118">Jogosultság: Szabadság- és távolléti kérelmek karbantartása az összes dolgozó számára</span><span class="sxs-lookup"><span data-stu-id="31e17-118">Privilege: Maintain leave and absence requests for all workers.</span></span>

## <a name="other-changes"></a><span data-ttu-id="31e17-119">Egyéb változtatások</span><span class="sxs-lookup"><span data-stu-id="31e17-119">Other changes</span></span>
<span data-ttu-id="31e17-120">Ebben a verzióban a következő frissítések történtek :</span><span class="sxs-lookup"><span data-stu-id="31e17-120">The following updates have been made in this release:</span></span>
- <span data-ttu-id="31e17-121">Dolgozók felvételi műveletekkel kapcsolatos módosítások, hogy azok ne „ragadjanak be” a **Munkafolyamat befejezve** állapotba.</span><span class="sxs-lookup"><span data-stu-id="31e17-121">Changes to worker hire actions so that they are no longer "stuck" in **Workflow complete** state.</span></span>
- <span data-ttu-id="31e17-122">Alkalmazotti rekord mostantól a foglalkoztatás kezdő dátuma nélkül is létrehozható.</span><span class="sxs-lookup"><span data-stu-id="31e17-122">Employment record can now be created without an employment start date.</span></span>
- <span data-ttu-id="31e17-123">A Dynamics 365 Talent regisztrációs dátuma, amely megjelenik az Alkalmazotti önkiszolgáló rendszer, mostantól alkalmazza az időzóna eltolását a dátumhoz képest.</span><span class="sxs-lookup"><span data-stu-id="31e17-123">The Dynamics 365 Talent registration date for a course shown in Employee self-service now applies the time zone offset to the date.</span></span>
- <span data-ttu-id="31e17-124">Excel-fájlok importálhatók többször is hibák nélkül az **Alkalmazott entitás** használatával.</span><span class="sxs-lookup"><span data-stu-id="31e17-124">Excel files can be imported multiple times without any errors using **Employee Entity**.</span></span>

## <a name="known-issue"></a><span data-ttu-id="31e17-125">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="31e17-125">Known issue</span></span>

- <span data-ttu-id="31e17-126">**Probléma**:Egy új csatolmány hozzáadásakor egy dolgozóhoz az **Új** és **Szerkesztés** gombok szürkén jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="31e17-126">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="31e17-127">**Megoldás:** A melléklet lap megnyitása, előtt ellenőrizze, hogy az adatterületek a **Dolgozó** lapon le vannak-e zárva.</span><span class="sxs-lookup"><span data-stu-id="31e17-127">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="31e17-128">Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="31e17-128">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="31e17-129">(Ezt a problémát kijavítjuk a következő platformfrissítéssel.)</span><span class="sxs-lookup"><span data-stu-id="31e17-129">(This issue will be fixed in the next platform update.)</span></span>
