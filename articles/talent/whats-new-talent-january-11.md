---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2019. január 11.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
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
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 38be1da69d8443fd76a81f439f000602ddb75bab
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010383"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-january-11-2019"></a><span data-ttu-id="409f7-103">Új vagy módosult elemek a Dynamics 365 Talent: Core HR szolgáltatásban (2019. január 11.)</span><span class="sxs-lookup"><span data-stu-id="409f7-103">What's new or changed in Dynamics 365 Talent: Core HR (January 11, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="409f7-104">**Build 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="409f7-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="409f7-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="409f7-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="409f7-106">Változások</span><span class="sxs-lookup"><span data-stu-id="409f7-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="409f7-107">Szabadság-kérelmek ellenőrzésének a rendelkezésre álló egyenleg becslésével</span><span class="sxs-lookup"><span data-stu-id="409f7-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="409f7-108">Ebben a verzióban végrehajtott módosítások engedélyezik az alkalmazottak számára a jövőbeli szabadság idő kérése az aktuális egyenlegükből történő levonás nélkül.</span><span class="sxs-lookup"><span data-stu-id="409f7-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="409f7-109">Normál munkafolyamat lesz használva minden jövőbeli kéréshez.</span><span class="sxs-lookup"><span data-stu-id="409f7-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="409f7-110">További tájékoztatásért olvasas el a [Szabadság elhatárolása a ledolgozott órák alapján](leave-accrue-hours-worked.md) című cikket.</span><span class="sxs-lookup"><span data-stu-id="409f7-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="409f7-111">Előre jelzett szabadságegyenleg megtekintése az ESS-ben és a Személyekben</span><span class="sxs-lookup"><span data-stu-id="409f7-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="409f7-112">Ez a funkció lehetővé teszi, hogy a HR, a vezetők és alkalmazottak megtekintésék a jövőbeli időszakokra vonatkozó szabadságegyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="409f7-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="409f7-113">Alkalmazottak a jövőbeli egyenleget az **Alkalmazotti önkiszolgáló rendszer** munkaterületen tekinthetik meg és a HR a **Személyek** munkaterületen fér hozzá ugyanezen információkhoz.</span><span class="sxs-lookup"><span data-stu-id="409f7-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="409f7-114">Szabadságegyenlegek módosításával kapcsolatos értesítések</span><span class="sxs-lookup"><span data-stu-id="409f7-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="409f7-115">Szabadságegyenlegek az alkalmazottak aktuális egyenlegét jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="409f7-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="409f7-116">Jövőbeli egyenlegek az **Alkalmazotti önkiszolgáló rendszer** és a **Személyek** munkaterületeken érhetők el egy „kezdődátum” beírásával előre jelzett egyenleg kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="409f7-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="409f7-117">Navigáció hozzá lett adva az előre jelzett egyenlegek megtekintéséhez, az alábbi területeken:</span><span class="sxs-lookup"><span data-stu-id="409f7-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="409f7-118">**Szabadságolás** a kártya az **Alkalmazotti önkiszolgáló rendszer** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="409f7-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="409f7-119">**Szabadság és a távollét** kártya a **Vezetői önkiszolgáló rendszer** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="409f7-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="409f7-120">**Szabadság és a távollét** lap a **Személyek** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="409f7-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="409f7-121">Tizedesek engedélyezése a Változó kompenzációs konstrukciókban (Pénzjutalom).</span><span class="sxs-lookup"><span data-stu-id="409f7-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="409f7-122">A változó készpénzjutalom konstrukciók most rugalmasabbak lettek, az összegek és az összegek tizedesjeggyel történ ő felülbírálása terén.</span><span class="sxs-lookup"><span data-stu-id="409f7-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="409f7-123">Nem lehet módosítani a dátumokat a Változó kompenzációs tagságokban a terv mentése után</span><span class="sxs-lookup"><span data-stu-id="409f7-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="409f7-124">Ez a változtatás lehetővé teszi a terv záró dátumának frissítését (kiterjesztett vagy lejárt) a terv mentése után.</span><span class="sxs-lookup"><span data-stu-id="409f7-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="409f7-125">Továbbra is aktiválhat vagy deaktiválhat terveket független kezdő és záró dátumoktól.</span><span class="sxs-lookup"><span data-stu-id="409f7-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="409f7-126">A bérlistaadatok elérhetők, ha hozzá van rendelve a Bérszámfejtő biztonsági szerepkör</span><span class="sxs-lookup"><span data-stu-id="409f7-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="409f7-127">A Bérszámfejtő szerepkör frissítve lett, hogy hozzáférjen a bérlistaadatokhoz a kérelemfolyamat során.</span><span class="sxs-lookup"><span data-stu-id="409f7-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="409f7-128">Az alkalmazotti önkiszolgáló rendszer | Beosztáshierarchia leásás a csempéről nem tudja beolvasni a szülőcsomópontot</span><span class="sxs-lookup"><span data-stu-id="409f7-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="409f7-129">Változtatások történtek egy hiba megszűntetése érdekében, amikor beosztáshierarchiákat adtak hozzá új munkaterületekhez és navigáltak a szervezeti struktúrában.</span><span class="sxs-lookup"><span data-stu-id="409f7-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="409f7-130">Új ellenőrzési üzenet amikor a személyzeti számsorozat használatban van.</span><span class="sxs-lookup"><span data-stu-id="409f7-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="409f7-131">Változás történt, hogy egyértelműsítve legyen, hogy mi a probléma alkalmazott felvétele esetén, ha a következő személyzeti szám használatban van.</span><span class="sxs-lookup"><span data-stu-id="409f7-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="409f7-132">Az alkalmazotti önkiszolgáló munkaterület kiválasztva első kezdőlapnak.</span><span class="sxs-lookup"><span data-stu-id="409f7-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="409f7-133">Ha az **Alkalmazotti önkiszolgáló rendszer** munkaterület van beállítva kezdeti indítási lapnak a felhasználó számára és a felhasználó nincs hozzárendelve az alkalmazott szerepkörhöz, a rendszer átirányítja az alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="409f7-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="409f7-134">Felmondás okkódja frissíti beosztás-hozzárendelés rekordját</span><span class="sxs-lookup"><span data-stu-id="409f7-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="409f7-135">A felmondási okkódja frissíti a beosztási hozzárendelést, amikor megszűnik a munkaviszony és befejeződik a beosztás.</span><span class="sxs-lookup"><span data-stu-id="409f7-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 
