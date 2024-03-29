---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.20 szolgáltatásban (2021. augusztus)
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy Dynamics 365 Supply Chain Management újak, vagy módosulnak a 10.0.20-as dokumentumban.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d99a7a7d0261ba0afd19efbb237dff329527723d
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219154"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10020-august-2021"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.20 szolgáltatásban (2021. augusztus)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.20-as verziójában. Ennek a verziónak 10.0.886 a buildszáma, és a következő módon érhető el:

- **Kiadás előzetes verziója:** 2021. május
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2021. július
- **A kiadás nyilvános megjelenése (automatikus frissítés):** 2021. augusztus

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: A *Funkció* oszlop a [kiadási tervre](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features) mutató hivatkozásokat tartalmaz, amelyeken látható az egyes funkciók hivatalos kiadási dátuma. A *További tudnivalók* oszlopban további részletek és/vagy a kapcsolódó dokumentációra mutató hivatkozások találhatóak.

Ezen szolgáltatások többségét a használat előtt engedélyezni kell a [Funkciók kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) alatt.

| Szolgáltatásterület | Funkció | További információ |
|---|---|---|
| Készlet&nbsp;és&nbsp;logisztika | [Értékesítési rendelés részleteinek teljesítményjavítása](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Ez a funkció válaszképesebbé teszi a felhasználói felületet az értékesítési rendelések – különösen a sok sorból álló rendelések – megnyitásakor. |
| Gyártás | [Folyamatautomatizálási folyamatok meghívása minőségi rendelések létrehozásához](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [Folyamatautomatizálási folyamatok meghívása minőségi rendelések létrehozásához](../production-control/process-automation-quality-orders.md ) |
| Gyártás | [Továbbfejlesztett termelési üzem végrehajtási felület gyártáshoz](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [A termelési üzem végrehajtási felületének konfigurálása](../production-control/production-floor-execution-configure.md) |
| Tervezés | [Végtelen kapacitás ütemezése a tervezési optimalizáláshoz](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | [Ütemezés végtelen kapacitással](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Termékinformációk kezelése | [Receptúrák és összetevők változásainak kezelése](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [Receptúrák és receptúra-összetevők változásainak kezelése](../engineering-change-management/manage-formula-changes.md) |
| Termékinformációk kezelése | [Termékkészültségi ellenőrzések](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [Termékkészenlét](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal. Ha e funkciók bármelyikét használni szeretné, kifejezetten engedélyeznie kell a [Funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funkció&nbsp;neve&nbsp;a Funkció-&nbsp;kezelésben | További információ |
|---|---|---|
| Alaptervezés | A helyesbített igény-előrejelzés párhuzamos engedélyezése | Ez a funkció engedélyezi a módosított igény-előrejelzés párhuzamos engedélyezését a **Módosított igény-előrejelzés** oldalon. A funkció célja az, hogy javítsa a teljesítményt, amikor nagy számú előrejelzés van engedélyezve. Az engedélyezés során a felhasználó megadhatja a **Szálak számát** az engedélyezési párbeszédpanelen. |
| Alaptervezés | Kötegelhető megerősítés és konszolidáció a tervezett tömeges és csomagolt kötegelt rendelésekhez | Ez a funkció lehetővé teszi, hogy kötegelt feladattal erősítsen meg és konszolidáljon tervezett tömeges és csomagolás rendeléseket. |
| Gyártásvezérlés | Általános útvonalak másolása | Ez a funkció a nem cikkspecifikus útvonalak másolására szolgáló útvonal-másolási funkciót tökéletesíti. Lehetővé teszi a rendszer számára, hogy minden releváns információt (például a helyet, az útvonal csoportját, a forrásszükségletet és a különböző időpontokat) frissítsen, miután az útvonalmásoló funkcióval felülírták a cikkhez még hozzá nem rendelt útvonalat. |
| Gyártásvezérlés | Kapcsolódó erőforrás-követelmények frissítése útvonalművelet módosulásakor | Ez a funkció lehetővé teszi a rendszer számára, hogy frissítse a kapcsolódó erőforrás-követelményeket, miután egy felhasználó módosítja egy meglévő útvonallépéshez tartozó műveletet. |
| Termékinformációk kezelése | Az anyagjegyzék-jelentés előzetes feldolgozása az időtúllépés megakadályozásához | Ez a funkció az anyagjegyzék-jelentés előre történő feldolgozását teszi lehetővé. Ezzel elkerülhető az időtúllépés, ha nagy a jelentéssel járó adatterhelés. |
| Beszerzés és forrás | Beszerzéssel kapcsolatos munkafolyamatok visszaállításának engedélyezése | Ez az előzetes verziójú funkció lehetővé teszi, hogy a következő munkafolyamatokat visszaállítsa piszkozat állapotúra: Beszerzési rendelés, Szállítói módosítás és Beszerzési igénylések. |
| Szállításkezelés | Szállítóiszámla-napló létrehozásának engedélyezése fuvarszámla elvetése esetén | Ha ez a funkció engedélyezve van, akkor a szállítói kifizetések beállításának használata esetén csak egyeztetési okok miatt jön létre a megfelelő szállítói számlanapló. Ellenkező esetben a számlanapló mindig létrejön. |
| Raktárkezelés | Feltöltési feladatokhoz kiválasztott sablonok ellenőrzése | Ezzel a funkcióval biztosítható, hogy a felhasználók érvényes feltöltési sablonokat válasszanak a feltöltési feladat beállításakor. Megakadályozza, hogy a felhasználók sablon nélkül hozzanak létre feltöltési feladatot, és olyan *Hullámigény* típusú sablonokat válasszanak ki, amelyek nem hoznak létre feltöltési munkát, és amelyeknek hosszú ideig tarthat a feldolgozása. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

Nemrégiben hozzáadta vagy jelentősen frissítettük a következő súgócikkeket. A program nem feltétlenül kapcsolódik ehhez a kiadáshoz hozzáadott új funkcióhoz, amint az az előző részben szerepel, de segítséget jelenthet a meglévő szolgáltatások kiválasztásában.

| Szolgáltatásterület | Új vagy frissített cikkek |
|---|---|
| Tervezési változáskezelés | [A termék életciklusának állapotai és tranzakciói](../engineering-change-management/product-lifecycle-state-transactions.md) |
| Készletgazdálkodás | [Készletláthatósági bővítmény](../inventory/inventory-visibility.md)<br><br>[Minőség- és szabálytalanságkezelés – áttekintés](../inventory/quality-management-processes.md) (valamint az összes kapcsolódó minőségkezelési cikk) |
| Beszerzés és forrás | [Szállítói minősítés karbantartása](../../finance/public-sector/manage-vendor-certification.md) |
| Gyártásvezérlés | [A termelési üzem végrehajtási felületének kialakítása](../production-control/production-floor-execution-styles.md) |
| Raktárkezelés | [Lépésikonok és címek hozzárendelése a Warehouse Management mobilalkalmazáshoz](../warehousing/step-icons-titles.md)<br><br>[Kézi készletmozgás halasztott feldolgozása](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A pénzügyi és az üzemeltetési alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.20 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és üzemeltetési alkalmazások 10.0.20-as verziójának Platformfrissítései (2021. július)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.20 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8). 

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: 2021-es 1. hullám tervei

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Lásd: [Dynamics 365: 2021-as 1. frissítési hullám tervét](/dynamics365-release-plan/2021wave1/). A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [cikk Eltávolított Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) vagy elavult funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva, illetve amelyek már el vannak távolítva vagy elavultak az Ellátásilánc-kezeléshez.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

