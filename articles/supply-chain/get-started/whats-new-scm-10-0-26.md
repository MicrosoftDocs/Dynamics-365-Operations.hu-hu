---
title: A Dynamics 365 Supply Chain Management 10.0.26. előzetes verziója (2022. május)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.26 új vagy módosított szolgáltatásait írja le.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: fae25eb1cb9dd4059b9d49e47cbb0060e717c9bc
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2022
ms.locfileid: "8386917"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10026-may-2022"></a>A Dynamics 365 Supply Chain Management 10.0.26. előzetes verziója (2022. május)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör olyan funkciókat sorol fel, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.26-os előnézeti verziójában. Ennek a verziónak 10.0.1192 a buildszáma, és a következő módon érhető el:

- **Kiadás előzetes verziója:** 2022. március
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. április
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. május

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a funkciókat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Készlet és logisztika | [Készlet-láthatósági lekérdezés a speciális raktárkezelési cikkek támogatásához](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | Hamarosan | Funkciókezelés:<br>*Raktári cikkek engedélyezése a Készletláthatóság funkcióban* |
| Készlet és logisztika | [Ígérethez rendelkezésre áll a készlet láthatósági bővítménye számára](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | Hamarosan | Szolgáltatáskonfiguráció által engedélyezve |
| Gyártás | [A termelési emelet végrehajtási felületének cikkekkel súlyozott súlya](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [A termelési üzem végrehajtási felületének használata dolgozók számára](../production-control/production-floor-execution-use.md) | Funkciókezelés:<br>*(Előzetes verzió) Jelentés a termelési üzem végrehajtási felületéről származó tényleges súly szerinti cikkekről* |
| Gyártás | A saját feladatok lap a termelési üzem végrehajtási felületén <!-- KFM: Add link to release plan when available --> | [A termelési üzem végrehajtási felületének használata dolgozók számára](../production-control/production-floor-execution-use.md) | Funkciókezelés:<br>*A saját feladatok lap a termelési üzem végrehajtási felületén* |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni [, akkor ezt a funkciókezelésben kell megtenni](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Beszerzés és forrás | A raktári termékek regisztrált mennyiségének és a nem raktározott termékek maradékénak feladása a nyugtákhoz és a szállítói számlákhoz | Ez a funkció módosítja a nem raktári termékek (például szolgáltatások) mennyiségének feladási mennyiségét a szállítói számlák és a bejövő szállítmányok beszerzési rendelésekkel szembeni feldolgozásakor. A funkció *a* *bevételezések* és a szállítói számlák feladására vonatkozó Regisztrált mennyiség beállítás viselkedését módosítja úgy, hogy módosítja azt, hogy megfeleljen a regisztrált mennyiség viselkedésének, valamint az értékesítési csomagjegyzékek mennyiségének feladásakor már megadott nem raktári termékek beállításának.<br><br>Ha a Regisztrált mennyiség és szolgáltatások mennyisége beállítással ad fel termékbevételezést vagy szállítói számlát, akkor a rendszer feladja a raktárzott termékek regisztrált mennyiségét, és a nem raktárzott termékek fennmaradó mennyiségét (beleértve a *szolgáltatásokat* és a nem szolgáltatásokat is). E szolgáltatás nélkül a rendszer továbbra is a raktári termékek regisztrált mennyiségét adja fel (beleértve a raktári cikkként beállított szolgáltatásokat), de mindig a nem készleten lévő szolgáltatási termékek teljes rendelt mennyiségét adja fel (*figyelmen* kívül hagyja a Szolgáltatás típusú, nem készleten lévő termékeket). |
| Beszerzés és forrás | Nyomon követési dimenziók szinkronizálása vállalatközi értékesítési és beszerzésirendelési-sorokban | Ezzel a funkcióval szabályozható, hogy a sorozatszám- és kötegszám-követési dimenziók szinkronizálva vannak-e a vállalatközi értékesítési és beszerzésirendelés-sorok között. Új beállításokat **ad** **·** **hozzá** a vevőkhöz és szállítókhoz a Vállalatközi beállítási lap beszerzési rendelésekkel és értékesítési rendelésekkel kapcsolatos irányelveit is. Ezenkívül frissíti néhány kapcsolódó, közeli beállítás nevét is.<br><br>Ha speciális raktárkezelést (WMS) használ, akkor ne feledje, hogy ez a funkció csak akkor szinkronizálja a köteg- és sorozatszámokat, ha a dimenziók a cél foglalási hierarchiájában a hely fölött vannak. |
| Termékinformációk kezelése | Termékattribútum-értékek tisztítása | Ez a funkció hozzáad egy **Termékattribútum-értékek** tisztítása nevű ismétlődő feladatot, amely tisztítja az olyan termékattribútum-értékrekordokat, amelyek már nem termékkategórián keresztül kapcsolódnak egy termékhez sem. |
| Készlet- és raktárkezelés | (Oroszország) Eltérések megakadályozása GTD-k kiadásakor az olyan beszerzési rendeléseknél, amelyekhez WMS-hez engedélyezett cikkek tartoznak | Ez a funkció csak az orosz honosításhoz használható. Megakadályozza az orosz vámárunyilatkozat-számok (GTD-k) kiadása során a magas szintű raktározásra engedélyezett cikkeket is magukban foglaló importbeszeddő rendelések (GTD) ellentmondásait. A GTD-kiadási folyamat módosítja az egyéni naplóban szereplő számlák kapcsolódó készlettranzakcióinak néhány készletdimenzió-értékét, ami eltéréseket okozhat a beszerzési rendelés munkarekordjai és a beszerzés készlettranzakciói között. Ha ez a funkció engedélyezve van, akkor a GTD-kiadási folyamat olyan helyesbítési munkát generál, amely kiküszöböli az ilyen eltéréseket. |
| Raktárkezelés | GS1 vonalkódok továbbfejlesztett elemzője | Ez a funkció továbbfejlesztett elemzőt ad a GS1 szimbólumadatokhoz. Az új elemző a GS1 Általános specifikáció algoritmust valósítja meg a GS1 szimbólumok elemzési funkcióval, és megerősített adatellenőrzést biztosít. |
| Raktárkezelés | Új rakománytervezési munkaterületlapok | Két új rakománytervezési munkaterületi lap hozzáadása: **a bejövő** **rakománytervezési munkaterület és a kimenő rakománytervezési munkaterület**. |
| Raktárkezelés | Warehouse Management alkalmazás – üres GTD | Ez a funkció csak az orosz honosításhoz használható. Lehetővé teszi a Raktárkezelés mobilalkalmazást használó dolgozók számára, hogy szükség esetén üresen hagyják az orosz vámárunyilatkozat-számokat (GTD-ket). Ha a GTD nyomon követési dimenzió úgy van beállítva, hogy üres értékeket engedélyezzen, a rendszer elfogadja az üres értékeket az aktuális készlet rendelkezésre álló készletének megfelelő készletműveletek GTD-értékeként. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

A következő súgótémakörök a közelmúltban lettek hozzáadva vagy jelentősen frissítve. Ezek a témakörök nem feltétlenül kapcsolódnak a kiadáshoz hozzáadott új funkciókhoz, mint azt az előző szakaszok felsorolják. Előfordulhat azonban, hogy segítenek a meglévő funkciókból további lehetőségeket kihozni.

| Szolgáltatásterület | Új vagy frissített témakörök |
|---|---|
| Költségkezelés | A következő témakörökben frissített példák és diagramok voltak hozzáadva:<ul><li>[FIFO tényleges értékkel és jelöléssel](../cost-management/fifo-physical-value-marking.md)</li><li>[LIFO tényleges értékkel és jelöléssel](../cost-management/lifo-physical-value-marking.md)</li><li>[LIFO dátum tényleges értékkel és jelöléssel](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Mozgóátlagon alapuló önköltségi ár](../cost-management/running-average-cost-price.md)</li><li>[Súlyozott átlag tényleges értékkel és jelöléssel](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |
| Beszerzés és forrás | [Beszerzésirendelés-sor adateltérései](../troubleshooting/procurement/purchase-order-line-data-issues.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.26 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügy és műveletek alkalmazások 10.0.26-os verziójának platformfrissítései (2022. május).](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md)<!-- KFM Confirm link -->

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.26 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 és ipari felhők: 2022-es 1. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2022-es 1. kiadási hullám csomag](/dynamics365-release-plan/2022wave1/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [Dynamics 365 Supply Chain Management eltávolított vagy elavult szolgáltatásai](removed-deprecated-features-scm-updates.md) témakör azokat a funkciókat írja le, amelyek el lettek távolítva a Supply Chain Management szolgáltatásól vagy eltávolításuk ütemezve van.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a termékből eltávolítunk egy szolgáltatást, egy eltávolítással kapcsolatos értesítést teszünk közzé a [Dynamics 365 Supply Chain Management eltávolított vagy elavult funkciói](removed-deprecated-features-scm-updates.md) témakörben 12 hónappal az eltávolítás előtt.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
