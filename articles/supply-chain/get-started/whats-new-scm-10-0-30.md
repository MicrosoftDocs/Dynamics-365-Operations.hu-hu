---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.30 alkalmazásban (2022. november)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.30 verziójában új vagy módosult funkciókat ismerteti.
author: kamaybac
ms.date: 09/08/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-09-08
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2983c113487934fd0751efcef9129e1f28d8dce8
ms.sourcegitcommit: 86c0562ce1ecdf7937125c0f5a6771f178b459e7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714798"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10030-november-2022"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.30 alkalmazásban (2022. november)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.30-as verziójában. Ennek a verziónak a buildszáma több 10.0.1362, és a következő ütemezésben érhető el:

- **Kiadás előzetes verziója:** 2022. szeptember
- **A kiadás nyilvános megjelenése (önkiszolgáló frissítés):** 2022. október
- **A kiadás nyilvános megjelenése (automatikus frissítés):** 2022. november

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk frissítése a cikk eredeti közzététele után a buildhez hozzáadott funkciókat is tartalmazza.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Gyártás | [Intelligencia (Intelligence) által tartalmazott berendezések figyelése](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/monitor-equipment-sensor-data-intelligence) | [Sensor Data Intelligence – kezdőlap](../sensor-data-intelligence/sdi-home-page.md) | Funkciókezelés:<br>*(Előzetes verzió) Érzékelő-adatintelligencia* |
| Raktárkezelés | [Többszintű hiba a Raktárkezelés mobilalkalmazásban](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/multi-level-detours-warehouse-management-mobile-app) | [Elterelések konfigurálása a mobileszközök menüelemeinek lépéseihez](../warehousing/warehouse-app-detours.md) | Funkciókezelés:<br>*Többszintű megkerülések a Warehouse Management mobilalkalmazáshoz* |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni, akkor ezt a [funkciókezelésben kell megtenni.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Gyártásvezérlés | Aktuális készletadatok a kiadási oldalon lévő termelési rendelésekben | Oszlop hozzáadása a kiadáshoz használt **termelési rendelések oldal sortételének aktuális készletmennyiségére**. |
| Szállításkezelés | Szállítmányok hozzárendelése a kapcsolódó útvonalszegmenshez | Ez a funkció lehetővé teszi a rendszer számára, hogy pontosabban felossa a szállítási költségeket, például olyan rakományok esetén, amelyek több szállítmányt szállítanak különböző szegmenscélok felé egy útvonalon. Az egyes szállítmányokat a legmegfelelőbb útvonalszegmenshez rendeli hozzá a szállítmány és a szegmens célcímei alapján. A funkció ezután a rakomány teljes fuvarköltségének arányában számítja ki az egyes szállítmányok fuvarköltségét, amely a szállítmány relatív súlya, térfogata, mennyisége és távolsága alapján van kiszámítva. Ez a funkció csak a Szállításkezelés (TMS) modullal kezelt szállítmányra vonatkozik. |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.30 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügy és műveletek alkalmazások 10.0.30-as verziójának Platformfrissítései (2022. november)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Hibajavítások

A 10.0.30 verzióba foglalt frissítések hibajavításával kapcsolatos információk megtekintéséhez jelentkezzen be a Lifecycle Services (LCS) [alkalmazásba, és tekintse meg a tudásbáziscikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 és ipari felhők: 2022-es 1. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2022-es 2. kiadási hullám csomag](/dynamics365-release-plan/2022wave2/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [cikk Eltávolított Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) vagy elavult funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva, illetve amelyek már el vannak távolítva vagy elavultak az Ellátásilánc-kezeléshez.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
