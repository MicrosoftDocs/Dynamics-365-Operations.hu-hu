---
title: Újdonságok és változások a Dynamics 365 Human Resources rendszerben 2021 augusztus 9
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2021. augusztus 9-én.
author: marcelbf
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 58926e5a6c1476db84fa41945dc92196eb24f4bf
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068454"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-9-2021"></a>Újdonságok és változások a Dynamics 365 Human Resources rendszerben 2021 augusztus 9

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Microsoft új, módosított vagy hamarosan érkező funkcióit írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókról és azok várható nyilvános megjelenési dátumáról további információkat a [Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/) című fejezetben talál.

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4393-es buildszámra vonatkoznak.

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a cikk első közzététele után frissítjük ezt a cikket, hogy a hibajavítások is szerepeljenek a buildben.

| Kiadás száma | Probléma | Leírás |
| --- | --- | --- |
| 558385 | Az alapértelmezett kijelölt személy nem kerül kiválasztásra, ha az **Automatikus kijelölt személyek automatikus kiválasztása** opció be van kapcsolva az alapértelmezett kijelölt személyek esetében. | Ez a probléma most már javítva van. A jogosult tervekben automatikusan több alapértelmezett kijelölt személy kerül kiválasztásra, ha a **Humánerőforrás megosztott paraméterek** oldalon a **Kijelölt személyek automatikus kiválasztása** opció be van kapcsolva. |
| 589617 | A **Szabadidő** lapon a **Vásárolható** és az **Eladható** egyenlegek üresek, ha a hozzáférés egy adott vállalatra van korlátozva. | Ez a probléma most már javítva van. A **Szabadidő** oldal helyesen mutatja a **Vásárolható** és az **Eladható** egyenlegeket, ha a felhasználó egy adott vállalatra van korlátozva. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- és kikapcsolásával kapcsolatos további információkért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md)|
| A szabadságkezelés engedélyezése a távollét-kezelőnek | [A szabadságkezelés engedélyezése a távollét-kezelőnek](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Ebben a kiadásban frissítjük a távollétkezelő munkaterület nézetét. További információért lásd: [A távollétkezelő szerepkörének konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Melléklet követelményének konfigurálása szabadságtípusonként | [Melléklet követelményének konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168108)|
| Szabadság-mértékegységek konfigurálása szabadságtípusonként | [Szabadság-mértékegységek konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Az alkalmazottak kifizetésre készként való jelölésének engedélyezése | [Az alkalmazottak kifizetésre készként való jelölésének engedélyezése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Kifizetésre kész](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Hamarosan

A tervbe vett funkciók és azok tervezett kiadásainak teljes listáját lásd: [A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkció | Részletek |
| --- | --- |
| Platform frissítése erre: 10.0.21 (45) | A 10.0.21-es platformfrissítés bevezetése a tervek szerint a 2021. október 4-i szolgáltatási kiadással kezdődik. A további tudnivalókat [lásd a Pénzügyi és műveleti alkalmazások 10.0.21-es verziójának Platformfrissítései (2021. október)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

