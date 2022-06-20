---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.22 alkalmazásban (2021. november)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.22 rendszer új vagy módosult funkcióit ismerteti.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 53f1670454ef505e61e96b16990d913473b46bf4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849503"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10022-november-2021"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.22 alkalmazásban (2021. november)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.22-es verziójában. Ennek a verziónak 10.0.995 a buildszáma, és a következő módon érhető el:

- **Kiadás előzetes verziója:** 2021. szeptember
- **A kiadás nyilvános megjelenése (önkiszolgáló frissítés):** 2021. október
- **A kiadás nyilvános megjelenése (automatikus frissítés):** 2021. november

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: A *Funkció* oszlop a [kiadási tervre](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features) mutató hivatkozásokat tartalmaz, amelyeken látható az egyes funkciók hivatalos kiadási dátuma. A *További tudnivalók* oszlopban további részletek és/vagy a kapcsolódó dokumentációra mutató hivatkozások találhatóak. A funkciók bekapcsolásának meghatározásához lásd az *Engedélyező* oszlopban. A funkciókezelés használatávall kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Előfordulhat, hogy a cikk első közzététele után frissítjük ezt a cikket, hogy szerepeljenek a buildben található funkciók.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Tervezés | [A tervezésoptimalizálás támogatása képesség alapú erőforrás-felosztáshoz](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Ütemezés képességen alapuló erőforrás-kijelöléssel](../master-planning/planning-optimization/capability-based-scheduling.md) | Funkciókezelés (*Végtelen kapacitásütemezés a tervezési optimalizáláshoz*) |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal. Ha e funkciók bármelyikét használni szeretné, kifejezetten engedélyeznie kell a [Funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Elosztott hibrid topológia | *(Nincs szükség funkciókezelésre.)* | <p>Ez a kiadás kibővíti a raktárkezelési munkaterhelés kimenő rakománytervezési lehetőségeit a felhő- és peremskálaegységek esetén.</p><p>További információk: [Raktárkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Tervezési változáskezelés | Változatlétrehozás tervezési termékekhez | <p>Ezzel a funkcióval egy termék színe, mérete, stílusa és konfigurációdimenziói alapján több változat is létrehozható egy mérnöki termékhez.</p><p>További tájékoztatás: [Változatok létrehozása tervezési termékekhez](../engineering-change-management/engineering-variants.md).</p> |
| Készlet- és raktárkezelés | Készletláthatósági integráció foglalási ellenszámlával | <p>Ez a funkció csak akkor engedélyezhető, ha engedélyezve van a *Készletláthatóság integrációja* funkció. Ezzel a funkcióval a készlet láthatóságán végzett ellenfoglalásokat lehet kiegyenlítetni.</p><p>További információért lásd a [Készletláthatósági foglalások](../inventory/inventory-visibility-reservations.md) című részt.</p> |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

Nemrégiben hozzáadta vagy jelentősen frissítettük a következő súgócikkeket. Ezek a cikkek nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszban felsoroltak. Előfordulhat azonban, hogy segítenek a meglévő funkciókból további lehetőségeket kihozni.

| Szolgáltatásterület | Új vagy frissített cikkek |
|---|---|
| Tervezési változáskezelés | [A tervezési változáskezelés áttekintése](../engineering-change-management/product-engineering-overview.md) most felsorolja a funkciókezelésben elérhető összes kapcsolódó, választható funkciót. |
| Alaptervezés | [Igény-előrejelzés beállítása](../master-planning/demand-forecasting-setup.md) |
| Alaptervezés | [Nettó követelmények és igénykövetési információ a Tervezési optimalizálással](../master-planning/planning-optimization/net-requirements.md) |
| Raktárkezelés | [A kiadás raktárba](../warehousing/release-to-warehouse-process.md) részletes áttekintést nyújt a raktárba való kiadás teljes folyamatról. |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.22 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügy és műveletek alkalmazások 10.0.22-es verziójának Platformfrissítései (2021. november)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.22 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 és ipari felhők: 2021-es 2. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2021-es 2. kiadási hullám csomag](/dynamics365-release-plan/2021wave2/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [cikk Eltávolított Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) vagy elavult funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva, illetve amelyek már el vannak távolítva vagy elavultak az Ellátásilánc-kezeléshez.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
