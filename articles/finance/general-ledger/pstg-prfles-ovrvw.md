---
title: Feladási profilok áttekintése
description: Ez a cikk bemutatja a feladási profiloknak az Microsoft Dynamics egész 365-ös alkalmazáson való alkalmazáson való alkalmazását.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7ef3be13e82ff3722fc81247b5cd581b0b571b0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876124"
---
# <a name="posting-profiles-overview"></a>Feladási profilok áttekintése

A Pénzügy és a Műveletek alkalmazásokban a feladási profilok segítségével lehet leírni azokat a konfigurációkat, *amelyek* az alallalt számlák fő számlákká való átalakítását írják le, hogy felhasználhatók legyen a főkönyvbe feladott tranzakciókban. Például azt adhatja meg, hogyan alakítható át a vevő fő számlává a kinnlevőségek fő számlává a számla feladása esetén.

Egyes moduloknak és funkcióknak van egy lapja, amely a névben a "feladási profil" szót tartalmazza (**például Vevői feladási** **profil vagy Szállítói feladási profil**). Ezenkívül egyes modulokban többféle lehetőség áll rendelkezésre az akkreátorból létrehozott tranzakciók főkönyvi feladásának konfigurálásához. Például a Gyártásvezérlés **modulban** termelési csoport, erőforrás vagy erőforráscsoport szerint lehet beállítani a feladást.

Ne feledje, hogy számos tranzakciótípus esetében van egy alternatíva a feladási profilokhoz: a feladásdefiníciókhoz. Támogatott dokumentumok esetén feladási profilok helyett feladásdefiníciókat lehet használni a könyvelési bejegyzések fő számláinak és pénzügyi dimenzióinak besorolására. Ha a kötelezettségvállalásokat és az előzetes kötelezettségvállalásokat tervezi használni, akkor egy feladásdefiníció szükséges a könyvelési tételek számláinak meghatározásához.

Mielőtt konfigurálni tudja a feladási profilokat, **a** feladásdefiníciókat vagy az automatikus tranzakciók számláit, **konfigurálnia** kell a számlatükret a konfigurálni kívánt jogi személy főkönyvi lapján.

## <a name="posting-types"></a>Feladási típusok

A Pénzügy és műveletek alkalmazásokban a feladási típus a tartozik és a követel tételek általános kategóriájának meghatározására használható. Ez a kategória független a főkönyv fő számlájától. A főkönyvben minden egyes tartozik és követel tételhez vannak feladási típusok.

Egy bizonylatnak egy vagy több feladási típusa is lehet. Például egy olyan tranzakció, amely egy általános naplón keresztül van feladva, ahol a **számla** és az ellenszámla a főkönyvi számlára van állítva, a tartozik és a **követel** típusú főkönyvi napló lesz. Ezzel szemben a szállítói számláknak több feladási típusa lesz. Ezek a feladási típusok egy sort és **további sorokat tartalmaznak a szállítói egyenleghez, például a főkönyvi naplóhoz**.

A Feladás típusa mező feladási típust **a Bizonylattranzakciók** **lap Általános lapján lehet** megtekinteni.**·**

> [!TIP]
> A Személyre szabás eszköztár **segítségével** hozzáadhatja **a Feladás típusú** **mezőt** az Áttekintés lap rácsához, illetve áthelyezheti azt. Ily módon a bizonylatok megtekintésekor ezt a mezőt könnyebben elérheti vagy megtekintheti.

## <a name="detail-settings-for-a-posting-profile"></a>Feladási profil részletes beállításai 

A feladási profilok konfigurálásakor **a Számlakód** mező meghatározza a beállítás szintjét. A következő lehetőségek érhetők el: **Tábla**, **Csoport** és **Mind**. Az egyeztetés az első egyeztetés után leáll, és a rendelés a legspecifikusabb szintről a legkevésbé specifikus szintre vonatkozik. Bár a **Számlakód** mező neve bizonyos esetekben kissé eltérő lehet, a mező viselkedése és funkciója változatlan marad. Például a készletfeladási profil tartalmaz egy **Cikk-kód** **mezőt és egy Számlakód mezőt**. Mindkét mezőnek van **Tábla**, **Csoport** és **Mind értéke**.

**Ha** egy feladási profilnál üresen hagyja a Fő számla mezőt, és nem konfigurált fő számlát a **Számlák** automatikus tranzakcióhoz lapon, vagy egy modulspecifikus vagy funkcióspecifikus lapon, akkor egy hibaüzenet jelenik meg a feladási típust használó tranzakció feladása során. Az üzenet általában a következő: "Nem \[\] található a feladási típus számlája".

### <a name="table-value"></a>Tábla értéke

A **tábla** értéke a feladási profilhoz társított fő rekordra vonatkozik. Minden táblarekord egy értékhez van megszava. Ezt az értéket kell megadni abban a mezőben, amely a Számlakód **mező után jelenik** meg. A mező neve általában **Számla** **vagy Számla/Csoport száma**. A pontos név a megjelenő laptól függően eltérő lehet.

Ha például vevői feladási profillal dolgozik, **a** Tábla értéke egy adott vevőt képvisel. Ezért ha a Számlakód mezőben **a** Tábla lehetőséget választja, **akkor a Számla/csoport száma mezőben ki kell választania a vevőszámot**.**·**

A **Tábla** érték a legspecifikusabb rekordtípust jelöli. A rendszer mindig ezt az értéket használja, még akkor is, **ha konfigurált egy másik rekordot, amelyben a Csoport** **vagy a Mind** érték van kiválasztva. Ez az érték felülbírálja az **automatikus tranzakciók számlái lapon alapértelmezettként létrehozott értékeket** is.

Nem ajánlott **a** Tábla érték használata a feladási profilok kezelésének elsődleges mechanizmusaként, mert adatminőségi problémák léphetnek fel, ha minden egyes alapadatrekordhoz külön feladási profil van karbantartva. Az egyes alapadatrekordok külön feladási profilját is nehéz karbantartani és egyeztetni. Ehelyett ezt az értéket kell használni a feladási profilok kivételének kezelésére.

### <a name="group-value"></a>Csoportérték

A **Csoport** érték azt a csoportosítási rekordot jelenti, amelyet a feladási profilhoz társított fő rekord támogat. Minden csoportrekord egy értékhez tartozik. Ezt az értéket kell megadni abban a mezőben, amely a Számlakód **mező után jelenik** meg. A mező neve általában **Számla** **vagy Számla/Csoport száma**. A pontos név a megjelenő laptól függően eltérő lehet.

A **Csoport** értékhez először konfigurálni kell egy csoportot, és hozzá kell csatolni a fiók egy vagy több rekordjaihoz. A **Csoport** érték kevésbé specifikus, mint a **tábla** értéke, de konkrétabb, mint a **Mind** érték. Ha nincs beállítva rekord egy táblához, a rendszer megpróbálja megtalálni annak a csoportnak a rekordját, amelyhez a rekord tartozik.

Ha például vevői feladási profillal dolgozik, **·** **és** a Számlakód mezőben a **Csoport lehetőséget választja, a Számla/** csoport száma mezőben ki kell választania egy vevőcsoportot. A vevőcsoport lapon **előre** meg kell adni a vevőcsoportokat, és a vevő létrehozásakor meg kell adnia egy vevőcsoportot.

Ha egy adott feladási típushoz több fő számlát kell nyomon követnie, javasoljuk, **hogy használja a Csoport értéket**. Például van három kinnlevőségekkel folytatott kereskedelmi fő számla: egy a normál vevők, egy az alkalmazottak, és egy a vállalatközi értékesítés. Ebben az esetben javasoljuk, hogy hozzon létre három vevőcsoportot, hogy szegmentálják a vevőket. Ezután mindegyik vevőcsoportot a megfelelő fő számlához kell leképezni a vevői feladási profilban. Az alábbi táblázat a példában a három vevőcsoportot mutatja be.

| Vevőcsoport | Név | Leírás |
|----------------|------|-------------|
| EXT | Külső vevő | Ez a csoport minden szabványos külső vevő esetében használatos. |
| EMP | Alkalmazottak | Ez a csoport az Összes alkalmazottra alkalmazható, aki a vállalattól vásárol. |
| INT | Vállalatközi értékesítés | Ez a csoport minden olyan vállalatközi vevői számlához használható, amely az értékesítési és beszerzési rendelésekkel együtt használatos. |

A feladási profilban ezt követően három sort állíthat be. Minden sorban ki kell választani a Csoport **értékét** és a kapcsolódó fő számlát.

### <a name="all-value"></a>Minden érték

A **Minden** érték azt jelzi, hogy a beállítások minden rekordra érvényesek. Ha a **Számlakód** **mezőBen** a Mind értéket választja, **a Számla/** csoport száma mező nem érhető el, és nem választhat ki egy rekordot, amelynél alkalmazni kell a konfigurációt.

A **Mind** érték a legkevésbé specifikus érték. Csak akkor használatos, ha a rendszer nem talál egyezést a tábla **vagy a csoport értékével** **.** Ha egy bizonyos feladási típushoz **csak** egy fő számlája van, akkor a Mind értéket kell kiválasztania.

Ha például vevői feladási profillal dolgozik, a megadott fő számlák minden olyan vevőre és vevőcsoportra érvényesek, amelyekhez nem tartozik rekord egy adott táblához (vevőhöz) vagy csoporthoz (vevőcsoporthoz).

### <a name="category"></a>Kategória

A készletfeladási profilok egy további értéket is képviselnek, amely az értékesítési vagy beszerzési kategóriára vonatkozik. Ez az érték hasonlít a **Tábla értékre**, mert csak egy meghatározott értékesítési vagy beszerzési kategóriára vonatkozik.

### <a name="default-value"></a>Alapértelmezett érték

Ha nem hoz létre rekordot egy feladási típushoz olyan feladási profilban, ahol **a** **Számlakód** mező értéke Mind, és a rendszer nem talál megfelelő feladásiprofil-rekordot **a** **Csoport** vagy Tábla értékhez, **a** rendszer visszaáll az automatikus tranzakciós számlák lapján megadott alapértelmezett értékre. További tájékoztatás az automatikus tranzakciók [számláinál található](accounts-for-auto-transactions.md).

## <a name="clearing-accounts"></a>Elszámolási számlák

Az elszámolási *számlát gyakran* használják könyvelésben. A 365-ös Microsoft Dynamics alkalmazásokban egyes feladási típusok elszámolószámlák. Más szóval egy másik tranzakció feladása során a számla egyenlege törlődik vagy sztornírozható. Amikor például felad egy beszerzési rendelés termékbevételezését, a termékek becsült költségeinek, valamint a beszerzésirendelés-sorokban foglalt adónak és az esetleges költségeknek az összege lesz feladva kötelezettségként a beszerzési elhatárolás feladási típusba. Később, amikor számláz a beszerzési rendelésen, az egyenleget a beszerzés elhatárolása feladási típusból sztornírozza, és átkerül a Kötelezettségek kereskedelmi számlára.

## <a name="additional-resources"></a>További erőforrások

A Dynamics 365 Pénzügy, Dynamics 365 Supply Chain Management és Dynamics 365 Commerce Dynamics 365 Project Operations számos modul, valamint egy feladási profil vagy további konfiguráció van, amelyek a főkönyvbe való feladás működését szabályják. Az alábbi témakörök segítségével további tudnivalókat olvashat az egyes modulok feladási profiljairól és feladási beállításairól:

- [Számlák automatikus tranzakciókhoz](accounts-for-auto-transactions.md)
- [Kötelezettségek feladása](accts-payble-posting.md)
- [Fogadható számlák feladása](accts-recvble-posting.md)
- [Eszközlízing feladása](../asset-leasing/set-up-lease-posting-accts.md)
- Eszközkezelés feladása (hamarosan)
- Készpénz- és bankkezelés (Hamarosan)
- Devizaátértékelés-feladási számlák (hamarosan)
- Költséggazdálkodás feladása (hamarosan)
- [Tárgyi eszköz feladási profilja](../fixed-assets/tasks/set-up-fixed-asset-posting-profiles.md)
- Vállalatközi könyvelés feladása (hamarosan)
- Készletfeladási profil (hamarosan)
- [Partra áras költség feladása](../../supply-chain/landed-cost/costing-parameters-setup.md)
- [Feladásdefiníciók áttekintése](posting-definitions.md)
- Gyártásvezérlés feladása (hamarosan)
- Projektvezetés és könyvelés feladása (hamarosan)
- Szolgáltatáskezelés feladása (hamarosan)
- Adó feladása (hamarosan)
- Idő és jelenlét feladása (hamarosan)
- Szállításkezelés feladása (hamarosan)
- Visszatérítéskezelés feladási profiljai (hamarosan)
