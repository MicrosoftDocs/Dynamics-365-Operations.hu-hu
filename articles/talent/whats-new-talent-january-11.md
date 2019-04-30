---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2019. január 11.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
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
ms.openlocfilehash: e6a89ba455acbed9724da6826ac4d41c6a481490
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "856138"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-11-2019"></a>Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2019. január 11.)

[!include [banner](includes/banner.md)]

**Build 8.1.2100**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.

## <a name="changes"></a>Változások

### <a name="validate-leave-requests-by-forecasting-available-balance"></a>Szabadság-kérelmek ellenőrzésének a rendelkezésre álló egyenleg becslésével
Ebben a verzióban végrehajtott módosítások engedélyezik az alkalmazottak számára a jövőbeli szabadság idő kérése az aktuális egyenlegükből történő levonás nélkül. Normál munkafolyamat lesz használva minden jövőbeli kéréshez. További tájékoztatásért olvasas el a [Szabadság elhatárolása a ledolgozott órák alapján](leave-accrue-hours-worked.md) című cikket.

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a>Előre jelzett szabadságegyenleg megtekintése az ESS-ben és a Személyekben
Ez a funkció lehetővé teszi, hogy a HR, a vezetők és alkalmazottak megtekintésék a jövőbeli időszakokra vonatkozó szabadságegyenlegeket. Alkalmazottak a jövőbeli egyenleget az **Alkalmazotti önkiszolgáló rendszer** munkaterületen tekinthetik meg és a HR a **Személyek** munkaterületen fér hozzá ugyanezen információkhoz.

### <a name="notifications-for-changing-leave-balances"></a>Szabadságegyenlegek módosításával kapcsolatos értesítések
Szabadságegyenlegek az alkalmazottak aktuális egyenlegét jelenítik meg. Jövőbeli egyenlegek az **Alkalmazotti önkiszolgáló rendszer** és a **Személyek** munkaterületeken érhetők el egy „kezdődátum” beírásával előre jelzett egyenleg kiszámításához.

Navigáció hozzá lett adva az előre jelzett egyenlegek megtekintéséhez, az alábbi területeken:
  - **Szabadságolás** a kártya az **Alkalmazotti önkiszolgáló rendszer** munkaterületen.
  - **Szabadság és a távollét** kártya a **Vezetői önkiszolgáló rendszer** munkaterületen.
  - **Szabadság és a távollét** lap a **Személyek** munkaterületen.

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a>Tizedesek engedélyezése a Változó kompenzációs konstrukciókban (Pénzjutalom).
A változó készpénzjutalom konstrukciók most rugalmasabbak lettek, az összegek és az összegek tizedesjeggyel történ ő felülbírálása terén.

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a>Nem lehet módosítani a dátumokat a Változó kompenzációs tagságokban a terv mentése után
Ez a változtatás lehetővé teszi a terv záró dátumának frissítését (kiterjesztett vagy lejárt) a terv mentése után. Továbbra is aktiválhat vagy deaktiválhat terveket független kezdő és záró dátumoktól.

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a>A bérlistaadatok elérhetők, ha hozzá van rendelve a Bérszámfejtő biztonsági szerepkör
A Bérszámfejtő szerepkör frissítve lett, hogy hozzáférjen a bérlistaadatokhoz a kérelemfolyamat során.

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Az alkalmazotti önkiszolgáló rendszer | Beosztáshierarchia leásás a csempéről nem tudja beolvasni a szülőcsomópontot
Változtatások történtek egy hiba megszűntetése érdekében, amikor beosztáshierarchiákat adtak hozzá új munkaterületekhez és navigáltak a szervezeti struktúrában.

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a>Új ellenőrzési üzenet amikor a személyzeti számsorozat használatban van.
Változás történt, hogy egyértelműsítve legyen, hogy mi a probléma alkalmazott felvétele esetén, ha a következő személyzeti szám használatban van.

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a>Az alkalmazotti önkiszolgáló munkaterület kiválasztva első kezdőlapnak.
Ha az **Alkalmazotti önkiszolgáló rendszer** munkaterület van beállítva kezdeti indítási lapnak a felhasználó számára és a felhasználó nincs hozzárendelve az alkalmazott szerepkörhöz, a rendszer átirányítja az alapértelmezett irányítópultra.

### <a name="termination-reason-code-updates-position-assignment-record"></a>Felmondás okkódja frissíti beosztás-hozzárendelés rekordját
A felmondási okkódja frissíti a beosztási hozzárendelést, amikor megszűnik a munkaviszony és befejeződik a beosztás. 
