---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. március 14.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 03/14/2019
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
ms.search.validFrom: 2019-03-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a3bb5792e6395e6fe593691f050cae03362cf659
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528621"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-14-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. március 14.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben
Vannak kisebb hibajavítások ebben a verzióban.

## <a name="changes-in-onboarding"></a>Változások az Onboarding alkalmazásban
Vannak kisebb hibajavítások ebben a verzióban.

## <a name="changes-in-core-hr"></a>A Core HR módosításai
**Build 8.1.2186**

### <a name="performance-management-not-working-in-all-scenarios-when-using-duplicate-security-roles"></a>Ismétlődő biztonsági szerepkörök használata esetén nem minden esetben a Teljesítménymenedzsment
Az ebben a verzióban végrehajtott módosítások engedélyezik a teljesítménykezelési forgatókönyveket, amikor nem megszokott, ismétlődő szerepkörök vannak használva.

### <a name="mass-assign-checklists-to-workers"></a>Ellenőrzőlisták tömeges hozzárendelése dolgozókhoz
Ezzel a módosítással immár kiválaszthat több alkalmazottat, és egyszerre rendelhet hozzá ellenőrzőlistákat ezekhez az alkalmazottakhoz. 

### <a name="platform-update-24-for-finance-and-operations"></a>A Finance and Operations 24-es platformfrissítése
A Finance and Operations 24-es platformfrissítéssel kapcsolatos részleteket lásd a [Újdonságok és változások a Finance and Operations 24. platformfrissítésében (2019. március)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24). A 24-es platformfrissítés jelentős változásai a következők: 

- Engedélyezve van az értesítések a Talent megoldásban.
- A frissített navigációs sáv mostantól igazodik az Office fejléchez.

### <a name="office-location-update-switches-the-context-to-the-top-of-the-worker-list"></a>Iroda helyének frissítése átvált a dolgozók listájának tetejére
Az aktuális kiadással az iroda helyének módosítása nem váltja át a dolgozó kontextusát, akit megtekint, amikor irodai helyet rendel hozzá.

### <a name="position-assignment-end-date-doesnt-display-correctly-on-worker-hire-and-transfer-actions"></a>Beosztás megbízás záró dátuma nem megfelelően jelenik meg a dolgozók felvételi és átviteli műveleteinél
A Beosztás-hozzárendelése záró dátumok immár megfelelően jelennek meg a felhasználó preferált időzónája alapján műveletek használata esetén.

### <a name="common-data-service-job-entity-doesnt-allow-job-type-and-job-function-fields-to-update"></a>A Common Data Service feladatentitás nem engedélyezi a beosztás típusa és beosztás funkciója mezők frissítését
A Common Data Service entitások immár helyesen szinkronizálnak, ha a Common Data Service használatával vannak frissítve.

## <a name="coming-soon"></a>Hamarosan

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Haladó kompenzációs biztonsági (fix és változó)
Számos vállalatnál a kompenzációkért és juttatásokért felelős vezetők előfordulhat, hogy csak a bizonyos kompenzációs rekordokhoz férnek hozzá. Ezek a vezetőkhöz és regionális alkalmazottak hoz tartozhatnak. Ez a módosítás lehetővé teszi a HR számára kompenzációs tervek kezelését és karbantartását a szervezet különböző alkalmazottcsoportjaihoz. A fix és változó kompenzációs tervek, amelyeket hozzárendelhet biztonsági szerepkörökhöz, határozzák meg a hozzáférést ezekhez a tervekhez és a hozzájuk kapcsolódó alkalmazotti adatokhoz, például fizetés és bónuszrekordok. Csak a hozzáférést kapott szerepkörök dolgozhatnak fel kompenzációt azokhoz a munkavállalókhoz.

###  <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez
A Finance and Operations 24-ös platformfrissítésével a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket küldenek ki a kapcsolattartóknak, ha egy esemény kezdeményezi azt.

### <a name="duplicate-employee-check-interface-changes"></a>Duplikált alkalmazottak ellenőrzése: Felhasználói felület módosításai
Ez a módosítással az ismétlődések észleli a program, amikor névmezőket ad meg, és egy állapot jelenik meg a találatok számával. A hivatkozás kiválasztásával megnyithat egy új lapot, hogy megállapítsa, hogy használja-e az észlelt egyezést. Az adatbevitel megzavarása elkerülése érdekében az ismétlődéseket tartalmazó űrlap nem nyílik meg automatikusan.
