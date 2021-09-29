---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. szeptember 6.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. szeptember 6-i kiadásban.
author: marcelbf
ms.date: 09/06/2021
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
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2add53b4b014cb65caacff03bf175078d2b70d8f
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485907"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. szeptember 6.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a téma a Microsoft Dynamics 365 Human Resources új, megváltozott vagy hamarosan megjelenő funkcióit ismerteti.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókról és azok várható nyilvános megjelenési dátumáról további információkat a [Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/) című fejezetben talál.

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4443-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| A szabadságkezelés engedélyezése a távollét-kezelőnek | [A szabadságkezelés engedélyezése a távollét-kezelőnek](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Ebben a kiadásban frissítjük a távollétkezelő munkaterület nézetét. További információért lásd: [A távollétkezelő szerepkörének konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Melléklet követelményének konfigurálása szabadságtípusonként | [Melléklet követelményének konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168108) |
| Szabadság-mértékegységek konfigurálása szabadságtípusonként | [Szabadság-mértékegységek konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a hibajavításokat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Kiadás száma | Probléma | Leírás |
|---|---|---|
| 610128 | Hiba történt az adatok közzététele közben a HcmDiscussionOverallCommentEntity használata során | Amikor egy Excel-munkafüzetből adatokat ad közzé a HcmDiscussionOverralCommentEntity entitásba, a következő hiba jelentkezik: "Nem található HcmTopicOverrall típusú adatforrásrekord." |
| 589073 | EEO-1 "Nem specifikus" és üres értékeket a **Nem** mezőnél „Nő” értéknek számítja. | Ha **Férfi** értéket nem adja meg a **Nem** mezőben, akkor a EEO-1 jelentés alapértelmezetten a **Nő** értékét hozza létre. |
| 589617 | Ha a felhasználói szerepkörök egy adott jogi személyre vannak korlátozva, akkor nem jelennek meg a Szabadidő-egyenlegek, a Vásárlásra rendelkezésre álló és az Értékesítésre elérhető egyenlegek. | Ha a felhasználó (alkalmazotti szerepkör) egy meghatározott jogi személyre van korlátozva, a **Szabadságegyenelegek** kártyán és a **Vásárolható** és **Eladható** mezőkben. |
| 604310 | A távollétkezelő lapot el kell rejteni, ha a felhasználóhoz nincs távolléti hierarchia rendelve. | Egy adott jogi személy esetén a **Távollétkezelő** lapot el kell rejteni az önkiszolgáló portálon, hacsak nincs engedélyezve a vállalatközi paraméter, és legalább egy távolléti hierarchia nincs társítva a felhasználóhoz. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- és kikapcsolásával kapcsolatos további információkért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md) |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Az alkalmazottak kifizetésre készként való jelölésének engedélyezése | [Az alkalmazottak kifizetésre készként való jelölésének engedélyezése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Kifizetésre kész](/dynamics365/human-resources/hr-compensation-payroll) |
| A Jogosultság egyéni mezői |[Egyéni mezők támogatása a jogosultságok feldolgozásában](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Egyéni mezők használata a jogosultsági feldolgozásban](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>Hamarosan

A tervbe vett funkciók és azok tervezett kiadásainak teljes listáját lásd: [A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkció | Részletek |
|---|---|
| Platform frissítése erre: 10.0.21 (45) | A 10.0.21-es platformfrissítés bevezetése a tervek szerint a 2021. október 4-i szolgáltatási kiadással kezdődik. További információért lásd: [Platformfrissítések a Finance and Operations alkalmazások 10.0.21-es verziójához (2021. október](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)). |
| Juttatási kimutatás | Juttatások kimutatása az alkalmazott aktuális juttatási adatainak megtekintéséhez. A további tudnivalókat lásd a [Juttatási kimutatás](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) részben a Kiadási hullám dokumentumában. |

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
