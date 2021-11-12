---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.22 alkalmazásban (2021. november)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.22 új vagy módosított szolgáltatásait írja le.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a4f9e5a4a318ceaa45b6919e394e1ff335bfb193
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678835"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10022-november-2021"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.22 alkalmazásban (2021. november)

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.22 változatának új vagy módosított szolgáltatásait írja le. Ennek a verziónak 10.0.995 a buildszáma, és a következő módon érhető el:

- **Kiadás előzetes verziója:** 2021. szeptember
- **A kiadás nyilvános megjelenése (önkiszolgáló frissítés):** 2021. október
- **A kiadás nyilvános megjelenése (automatikus frissítés):** 2021. november

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: A *Funkció* oszlop a [kiadási tervre](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features) mutató hivatkozásokat tartalmaz, amelyeken látható az egyes funkciók hivatalos kiadási dátuma. A *További tudnivalók* oszlopban további részletek és/vagy a kapcsolódó dokumentációra mutató hivatkozások találhatóak. A funkciók bekapcsolásának meghatározásához lásd az *Engedélyező* oszlopban. A funkciókezelés használatávall kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a funkciókat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Szolgáltatásterület | Funkció | További információ | Engedélyezte:   |
|---|---|---|---|
| Tervezés | [A tervezésoptimalizálás támogatása képesség alapú erőforrás-felosztáshoz](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Ütemezés képességen alapuló erőforrás-kijelöléssel](../master-planning/planning-optimization/capability-based-scheduling.md) | Funkciókezelés (*Végtelen kapacitásütemezés a tervezési optimalizáláshoz*) |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal. Ha e funkciók bármelyikét használni szeretné, kifejezetten engedélyeznie kell a [Funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Költségkezelés | Kapcsolódó bizonylatok létrehozása elszámolóár kerekítési átértékeléseihez | <p>Pénzügyi készletfeladáskor (például értékesítési rendelés számlája vagy készlettranzakció) történik, ennek a funkciónak az hatására a rendszer létrehoz egy külön bizonylatot minden kapcsolódó elszámolóáras kerekítési átértékeléshez, és kapcsolódó bizonylatként csatolja a pénzügyi feladási bizonylathoz.</p><p>E funkció nélkül a rendszer ugyanazon bizonylatfeladás elszámolóár-kerekítési átértékeléseit rögzíti. Ez a viselkedés bizonyos esetekben ütköző dátumadatokat is okozhat, mivel az átértékelések a munkamenet vagy a rendszer dátumát használják, míg a pénzügyi feladások a feladási dátumot használják.</p> |
| Elosztott hibrid topológia | *(Nincs szükség funkciókezelésre.)* | <p>Ez a kiadás kibővíti a raktárkezelési munkaterhelés kimenő rakománytervezési lehetőségeit a felhő- és peremskálaegységek esetén.</p><p>További információk: [Raktárkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Tervezési változáskezelés | Változatlétrehozás tervezési termékekhez | <p>Ezzel a funkcióval egy termék színe, mérete, stílusa és konfigurációdimenziói alapján több változat is létrehozható egy mérnöki termékhez.</p><p>További tájékoztatás: [Változatok létrehozása tervezési termékekhez](../engineering-change-management/engineering-variants.md).</p> |
| Készlet- és raktárkezelés | Készletláthatósági integráció foglalási ellenszámlával | <p>Ez a funkció csak akkor engedélyezhető, ha engedélyezve van a *Készletláthatóság integrációja* funkció. Ezzel a funkcióval a készlet láthatóságán végzett ellenfoglalásokat lehet kiegyenlítetni.</p><p>További információért lásd a [Készletláthatósági foglalások](../inventory/inventory-visibility-reservations.md) című részt.</p> |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

A következő súgótémakörök a közelmúltban lettek hozzáadva vagy jelentősen frissítve. Ezek a témakörök nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszban felsoroltak. Előfordulhat azonban, hogy segítenek a meglévő funkciókból további lehetőségeket kihozni.

| Szolgáltatásterület | Új vagy frissített témakörök |
|---|---|
| Tervezési változáskezelés | [A tervezési változáskezelés áttekintése](../engineering-change-management/product-engineering-overview.md) most felsorolja a funkciókezelésben elérhető összes kapcsolódó, választható funkciót. |
| Alaptervezés | [Igény-előrejelzés beállítása](../master-planning/demand-forecasting-setup.md) |
| Alaptervezés | [Nettó követelmények és igénykövetési információ a Tervezési optimalizálással](../master-planning/planning-optimization/net-requirements.md) |
| Raktárkezelés | [A kiadás raktárba](../warehousing/release-to-warehouse-process.md) részletes áttekintést nyújt a raktárba való kiadás teljes folyamatról. |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Finance and Operations-alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.22 platformfrissítéseket tartalmaz. További tájékoztatás: [Platform-frissítések az Finance and Operations alkalmazások 10.0.22 verziójához (2021. november)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.22 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

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
