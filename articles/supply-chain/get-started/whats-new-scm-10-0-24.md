---
title: A Dynamics 365 Supply Chain Management 10.0.24 (2022. február) előzetes verziója
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
ms.openlocfilehash: f6402d7f9f433ca621c475bd62553529943dbe62
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920548"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10024-february-2022"></a>A Dynamics 365 Supply Chain Management 10.0.24 (2022. február) előzetes verziója

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.24 előzetes kiadásának új vagy módosított szolgáltatásait írja le. Ennek a verziónak 10.0.1084 a buildszáma, és a következő módon érhető el:

- **A kiadás előzetese:** 2021. december
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. január
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. február

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a funkciókat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Szolgáltatásterület | Funkció | További információ | Engedélyezte:   |
|---|---|---|---|
| Elosztott hibrid topológia | [Továbbfejlesztett raktárvégrehajtási számítási feladatok a méretezési egységeken](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Raktérkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md) | Alapértelmezés szerint engedélyezve. |
| Tervezés | [Tervezési optimalizálási támogatás az újrarendelési margóhoz és a kibocsátási margóhoz](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Biztonsági határok](../master-planning/planning-optimization/safety-margins.md) | Alapértelmezés szerint engedélyezve. |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha be- vagy kikapcsolni szeretné ezeket a funkciókat, ezt a [funkciókezelésben kell megtennie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Gyártásvezérlés | Igény szerinti anyagelérhetőségi ellenőrzés a termelési rendelésekre vonatkozóan | Ez a funkció gyorsabbá teszi a **Termelési rendelések kiadásához való megnyitását,** amely elérhető a Termelési padló felügyeleti **munkaterületéről**. E funkció nélkül a rendszer automatikusan ellenőrzi, hogy az összes felsorolt gyártási rendeléshez rendelkezésre állnak-e anyagok, amint megnyitja az oldalt, ami jelentős időt vehet igénybe, ha nagyszámú megrendelése van. Ha ez a funkció engedélyezve van, a rendszer eszköztárgombot biztosít, amellyel csak a kiválasztott rendelések esetében és szükség esetén kezdeményezheti az anyagellenőrzést. |
| Gyártásvezérlés | (Előzetes verzió) Anyagfelhasználás regisztrálása a termelési üzem végrehajtási felületén (nem WMS) | Ez a funkció lehetővé teszi a dolgozók számára, hogy a termelési padló végrehajtási felületét használják az anyagfelhasználás, a kötegszámok és a sorozatszámok regisztrálására. Ez a szolgáltatás csak azokat a cikkeket támogatja, amelyek nem engedélyezettek a speciális raktári folyamatok (WMS) használatára. A WMS-kompatibilis elemek támogatása egy jövőbeli kiadásra van ütemezve.<p>Egyes gyártóknak, különösen a feldolgozóiparban lévőknek, kifejezetten regisztrálniuk kell az egyes tételekhez vagy gyártási rendelésekhez felhasznált anyag mennyiségét. A munkavállalók például egy skálát használhatnak a munka közben felhasznált anyag mennyiségének mérésére. A teljes anyagkövetés biztosítása érdekében ezeknek a szervezeteknek regisztrálniuk kell azt is, hogy mely tételszámokat fogyasztották az egyes termékek gyártásakor. |
| Gyártásvezérlés | Jelentés készként a felhő- és peremskálázási egység raktárkezelési számítási feladatán | Ez a funkció lehetővé teszi a dolgozók számára, hogy a Raktárkezelés mobilalkalmazással a gyártási vagy kötegelt rendelést készként jelentsék, amikor az alkalmazás felhő- vagy peremskálás egység raktárkezelési számítási feladatán fut. További információ: [Jelentés befejezettként és elhelyezve egy méretarányos egységen](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF). |
| Gyártásvezérlés | Gyártási rendelés indítása a felhő- és peremskálás egység raktárkezelési számítási feladatán | Ez a funkció lehetővé teszi a dolgozók számára, hogy a Raktárkezelés mobilalkalmazással éles vagy kötegelt rendelést indítsanak, amikor az alkalmazás felhő- vagy peremskálás egység raktárkezelési számítási feladatán fut. |
| Raktárkezelés | Új terheléstervezési munkapad-oldalak | Két új terheléstervezési munkapad-oldalt engedélyez: **Bejövő terheléstervezési munkapad** és Kimenő **terheléstervezési munkapad**. |

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

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Finance and Operations-alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.24 platformfrissítéseket tartalmaz. További tájékoztatás: [Platform-frissítések az Finance and Operations alkalmazások 10.0.24 verziójához (2021. november)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md).

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
