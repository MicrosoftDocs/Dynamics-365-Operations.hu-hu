---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.24 verziójában (2022. február)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.24 új vagy módosított szolgáltatásait írja le.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d7dd3bbb0d1aa701757ad7fa525aba04fe9419c9
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986303"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10024-february-2022"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.24 verziójában (2022. február)

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.24 változatának új vagy módosított szolgáltatásait írja le. Ennek a verziónak 10.0.1084 a buildszáma, és a következő módon érhető el:

- **Kiadás előnézete:** 2021. december
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. január
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. február

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a funkciókat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Szolgáltatásterület | Funkció | További információ | Engedélyezte:   |
|---|---|---|---|
| Elosztott hibrid topológia | [A raktár végrehajtási terhelésének javítása a mérlegegységeken](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Raktérkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md) | Alapértelmezés szerint engedélyezve. |
| Tervezés | [Tervezési optimalizálás támogatása az újrarendelési különbözet és a kiadási árrés esetén](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Biztonsági határok](../master-planning/planning-optimization/safety-margins.md) | Alapértelmezés szerint engedélyezve. |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni, akkor ezt a funkciókezelésben [kell megtenni](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Gyártásvezérlés | Igény szerinti anyagelérhetőségi ellenőrzés a termelési rendelésekre vonatkozóan | Ez a funkció gyorsabbá teszi a termelési rendelések kiadási lapjának megnyitását, amely a **Termelésirányítás** **munkaterületről** érhető el. A rendszer e funkció nélkül automatikusan ellenőrzi, hogy a lap megnyitása után a felsorolt termelési rendelésekhez rendelkezésre állnak-e anyagok, ami nagy számú rendelés esetén jelentős időt is igénybe vehet. Ha ez a funkció engedélyezve van, akkor a rendszer egy eszköztárgombot biztosít, amelynek segítségével az anyagok ellenőrzése csak a kiválasztott rendelésekre és szükség esetén történik meg. |
| Gyártásvezérlés | (Előzetes verzió) Anyagfelhasználás regisztrálása a termelési üzem végrehajtási felületén (nem WMS) | Ez a funkció lehetővé teszi a dolgozók számára, hogy a termelési emelet végrehajtási felületével regisztrálják az anyagfelhasználást, a kötegszámokat és a sorozatszámokat. Ez a funkció csak olyan cikkeket támogat, amelyek nincsenek engedélyezve a speciális raktári folyamatok (WMS) használatára. A WMS-kompatibilis cikkek támogatása egy jövőbeli kiadásra van ütemezve.<p>Egyes gyártóknak, különösen a folyamatiparban használt gyártóknak explicit módon regisztrálniük kell az egyes köteg- vagy termelési rendelésenként felhasznált anyagok mennyiségét. Például a dolgozók a mérleg segítségével leméneklik a munka közben felhasznált anyagok mennyiségét. A teljes anyagkövetés biztosítása érdekében ezeknek a szervezeteknek regisztrálniuk kell azt is, hogy az egyes termékek gyártása során melyik kötegszámokat felhasználták. |
| Gyártásvezérlés | Jelentés befejezettként a raktárkezelési munkaterhelésben, felhőalapú és peremhálózat-léptékű egység esetén | Ez a funkció lehetővé teszi a dolgozók számára a Raktárkezelés mobilalkalmazás használatával, hogy készként jelentsen egy termelési vagy kötegrendelést, amikor az alkalmazás egy felhő vagy peremhálózati egység raktárkezelési terhelésével szemben fut. A további tudnivalókat lásd a Készként [jelentve és a mérlegegységre rakva.](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF) |
| Gyártásvezérlés | Termelési rendelés kezdése a felhő- és szélskála egysége raktárkezelési terhelésére | Ez a funkció lehetővé teszi a dolgozók számára, hogy a Raktárkezelés mobilalkalmazás segítségével elindítsak egy termelési vagy kötegrendelést, amikor az alkalmazás egy felhő vagy peremhálózati egység raktárkezelési terhelésével fut. |
| Raktárkezelés | Új rakománytervezési munkaterületlapok | Két új rakománytervezési munkaterületi lapnak ad lehetőséget: a bejövő rakománytervezési munkaterületet és a **kimenő** **rakománytervezési** munkaterületet. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

A következő súgótémakörök a közelmúltban lettek hozzáadva vagy jelentősen frissítve. Ezek a témakörök nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszban felsoroltak. Előfordulhat azonban, hogy segítenek a meglévő funkciókból további lehetőségeket kihozni.

| Szolgáltatásterület | Új vagy frissített témakörök |
|---|---|
| Költségkezelés | [Készletérték-jelentések](../cost-management/inventory-value-report-storage.md) |
| Költségkezelés | [Készletérték-jelentés – példák és logika](../cost-management/inventory-value-report-examples.md) |
| Alaptervezés | [A Tervezési optimalizálás által nem használt dátum- és időparaméterek](../master-planning/planning-optimization/date-time-used.md) |
| Alaptervezés | [Igény-előrejelzés beállítása](../master-planning/demand-forecasting-setup.md) |
| Alaptervezés | [A biztonsági készlet napló használata a cikkek minimális fedezetének frissítésére](../master-planning/safety-stock-journal.md) |
| Gyártásvezérlés | [A termelési üzem végrehajtási felületének testreszabása](../production-control/production-floor-execution-customize.md) |
| Gyártásvezérlés | [A termelési üzem végrehajtási felületének kialakítása](../production-control/production-floor-execution-styles.md) |
| Értékesítés és marketing | [Értékesítési előzmények adattisztítási teljesítményének javításai](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Raktárkezelés | [Mobileszköz felhasználói fiókjai](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.24 platformfrissítéseket tartalmaz. A további tudnivalókat lásd a Pénzügy és műveletek alkalmazások [10.0.24-es verziójának Platformfrissítései (2021. november).](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md)

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.24 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 és ipari felhők: 2021-es 2. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2021-es 2. kiadási hullám csomag](/dynamics365-release-plan/2021wave2/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [Dynamics 365 Supply Chain Management eltávolított vagy elavult szolgáltatásai](removed-deprecated-features-scm-updates.md) témakör azokat a funkciókat írja le, amelyek el lettek távolítva a Supply Chain Management szolgáltatásól vagy eltávolításuk ütemezve van.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a termékből eltávolítunk egy szolgáltatást, egy eltávolítással kapcsolatos értesítést teszünk közzé a [Dynamics 365 Supply Chain Management eltávolított vagy elavult funkciói](removed-deprecated-features-scm-updates.md) témakörben 12 hónappal az eltávolítás előtt.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
