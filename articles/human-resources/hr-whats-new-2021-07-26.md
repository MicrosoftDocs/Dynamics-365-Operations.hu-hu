---
title: A Dynamics 365 Human Resources új vagy módosult elemei (2021. július 26.)
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2021. július 26-án.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6c7211135733f45a9841ae5a80607b01999d7c69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870929"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>A Dynamics 365 Human Resources új vagy módosult elemei (2021. július 26.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör az új, módosított vagy hamarosan érkező funkciókat írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókról és azok várható nyilvános megjelenési dátumáról további információkat a [Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/) című fejezetben talál.

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4384-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Platform update 10.0.20 | -- | [A Pénzügy és műveletek alkalmazások 10.0.20-as verziójának platformfrissítései (augusztus 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. A cikk első közzététele után frissíthet egy hibajavítást, amely a javításokat tartalmazza a buildben.

| Kiadás száma | Probléma |  Leírás |
| --- | --- | --- |
| 600422 | A bérlista címének érvényesítése sikertelen a Kifizetésre kész funkcióhoz. | Az érvényesítés frissítésre került, így csak egy "Bérlista helye" típusú címre és csak egy "Bérlista munkahelye" típusú címre van szükség. |
| 601226 | Adatintegrációs probléma: A bérlista-integrációs exportprojekt nem rendelkezik teljes küldési lehetőséggel | A Ceridian DayForce bérlista-integrációja teljes küldés helyett növekményes küldést hajtott végre. A Ceridian megköveteli, hogy mindig teljes legyen a frissítés. Ez a probléma most már javítva van, az adatexport projektben lévő entitások többé nem fognak növekményes küldésre váltani. |
| 602272 | Az Alkalmazotti önkiszolgáló Employee Self Service munkaterülethez hozzáadott csempék most hiányoznak, és már nem lehet hozzá csempéket adni | Megoldottuk a személyre szabási problémát az Alkalmazotti önkiszolgáló szolgáltatásnál. Új csempéket lehet hozzáadni a nézethez, és minden meglévő személyre szabás látható lesz a felhasználók számára |
| 600711 | A félnapos meghatározás-kiválasztási mező engedélyezve van az egész napos szabadságkérelmeknél | Ez a probléma már javítva van, és a félnapos meghatározási mező csak akkor lesz engedélyezve, ha a munkavállalók olyan szabadságtípust választanak, ahol a félnapos meghatározás engedélyezve van, és fél nap a kiválasztott mennyiség |
| 602208 | Az elhatárolási mérték egységei napok helyett órákat jelenítenek meg | Ez a probléma most már javítva van. A **Szabadság** űrlapon a megfelelő szabadságegység (órák vagy napok) jelenik meg az **Elhatárolási mérték** oszlopban. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md)|
|  A szabadságkezelés engedélyezése a távollét-kezelőnek | [A szabadságkezelés engedélyezése a távollét-kezelőnek](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Ezzel a kiadással frissítjük a távollétkezelő munkaterületének nézetét. További információért lásd: [A távollétkezelő szerepkörének konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168107).|
|  Melléklet követelményének konfigurálása szabadságtípusonként | [Melléklet követelményének konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Szabadság-mértékegységek konfigurálása szabadságtípusonként | [Szabadság-mértékegységek konfigurálása szabadságtípusonként](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Szabadság- és távolléttípusok konfigurálása](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Az alkalmazottak kifizetésre készként való jelölésének engedélyezése | [Az alkalmazottak kifizetésre készként való jelölésének engedélyezése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Kifizetésre kész](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Hamarosan

A tervbe vett funkciók és azok tervezett kiadásainak teljes listáját lásd: [A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
