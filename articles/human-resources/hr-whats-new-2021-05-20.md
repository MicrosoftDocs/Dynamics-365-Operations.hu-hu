---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban 2021. május 20-án
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. május 20-i kiadásban.
author: marcelbf
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4519e90e19d0652f855999d1a73ca64777b53b53465d6065987afc1cf2494187
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731937"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban 2021. május 20-án

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2021. második kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4189-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Platform frissítése erre: 10.0.18 (42) | -- | [Platformfrissítések a Finance and Operations alkalmazás 10.0.18 verziójához (2021. május)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| A Microsoft Teamshez Human Resources app már támogatja a fél napos definíciókat és a napok felosztását | -- | [Szabadságkérelmek kezelése a Teamsben](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakört frissítjök olyan hibajavításokkal, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Probléma |  Leírás |
| --- | --- | --- |
| 583776 | Az alkalmazottak szabadságtervekbe történő tömeges beléptetése ismétlődő rekorddal kapcsolatos hibát okoz | Ezt a hibát a legutóbbi kiadásban kijavítottuk. A szabadságtervekbe történő tömeges beléptetés feldolgozása mostanában nem oloz hibát. |
| 582263 | Az élő esemény feldolgozása nem futtatható az összes dolgozónál egyszerre | Ha az élő események feldolgozásánál üresen hagyja a **Dolgozó** mezőt, a rendszer minden dolgozót feldolgoz. |
| 558383 | Ha nincs kiválasztva alapértelmezett kedvezményezett, az elsődleges kedvezményezett nincs megjelölve 100%-osként | A hibát kijavítottuk, így a felhasználónak csak az elsődleges kedvezményezett váltókapcsolót kell kiválasztania.|
| 509404 | A részleg létszámelemzése nem veszi figyelembe az alkalmazottak részlegek közötti mozgását |Az elemzést frissítettük, hogy szerepeljenek benne az alkalmazottak részlegek közötti mozgásai.|
| 579420 | A rácsok oszlopainak rögzítése még nem lehetne elérhető | A Human Resourcesban nem elérhető **Rácsok oszlopainak rögzítése** funkció elérhetőként szerepelt a Funkciókezelésben. A szolgáltatást eltávolítottuk az engedélyezendő funkciók listájáról. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Egyéni mező támogatása a Juttatások kezelése jogosultsági szabályokban | [Egyéni mezőtámogatás a jogosultságok feldolgozásához](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Jogosultsági szabályok konfigurálása](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Szabadság és távollét munkafolyamat-élmény javításai | [Szabadság és távollét munkafolyamat-élmény javításai](https://go.microsoft.com/fwlink/?linkid=2147528) | [Távollét kérelmezése](hr-employee-self-service-request-time-off.md)|
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md)|
| Szabadságelhatárolási tranzakció auditálása | - | [Szabadságelhatárolási tranzakció auditálása](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Hamarosan

| Funkció | Részletek |
| --- | --- |
|  A szabadságkezelés engedélyezése a távollét-kezelőnek | [A szabadságkezelés engedélyezése a távollét-kezelőnek](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

A tervezett funkciók és az ütemezett kiadásaik teljes listáját lásd: [A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021. első kiadási hullámának áttekintése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
