---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.26 szolgáltatásban (2022. május)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.26 új vagy módosított szolgáltatásait ismerteti.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: dd98b22a2dfcd8cad62bdef2d31ac2880b3422f8
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334715"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10026-may-2022"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.26 szolgáltatásban (2022. május)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.26-os verziójában. Ennek a verziónak 10.0.1192 a buildszáma, és a következő módon érhető el:

- **Kiadás előzetes verziója:** 2022. március
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. április
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. május

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk első közzététele után frissítjük ezt a cikket, hogy szerepeljenek a buildben található funkciók.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Készlet és logisztika | [Készlet-láthatósági lekérdezés a speciális raktárkezelési cikkek támogatásához](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | [Inventory Visibility támogatása WMS-cikkekhez](../inventory/inventory-visibility-whs-support.md) | Funkciókezelés:<br>*Raktári cikkek engedélyezése a Készletláthatóság funkcióban* |
| Készlet és logisztika | [Ígérethez rendelkezésre áll a készlet láthatósági bővítménye számára](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | [A készlet láthatósága – az aktuális készlet változásának ütemezése, amely ígérethez rendelkezésre áll](../inventory/inventory-visibility-available-to-promise.md) | Szolgáltatáskonfiguráció által engedélyezve |
| Gyártás | [A termelési emelet végrehajtási felületének cikkekkel súlyozott súlya](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [A termelési üzem végrehajtási felületének használata dolgozók számára](../production-control/production-floor-execution-use.md) | Funkciókezelés:<br>*Jelentés a termelési üzem végrehajtási felületéről származó tényleges súly szerinti cikkekről* |
| Gyártás | A saját feladatok lap a termelési üzem végrehajtási felületén <!-- KFM: Add link to release plan when available --> | [A termelési üzem végrehajtási felületének használata dolgozók számára](../production-control/production-floor-execution-use.md) | Funkciókezelés:<br>*A saját feladatok lap a termelési üzem végrehajtási felületén* |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni [, akkor ezt a funkciókezelésben kell megtenni.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Beszerzés és forrás | A raktári termékek regisztrált mennyiségének és a nem raktározott termékek maradékénak feladása a nyugtákhoz és a szállítói számlákhoz | Ez a funkció módosítja a nem raktári termékek (például szolgáltatások) mennyiségének feladási mennyiségét a szállítói számlák és a bejövő szállítmányok beszerzési rendelésekkel szembeni feldolgozásakor. A funkció *a* *bevételezések* és a szállítói számlák feladására vonatkozó Regisztrált mennyiség beállítás viselkedését módosítja úgy, hogy módosítja azt, hogy megfeleljen a regisztrált mennyiség viselkedésének, valamint az értékesítési csomagjegyzékek mennyiségének feladásakor már megadott nem raktári termékek beállításának.<br><br>Ha a Regisztrált mennyiség és szolgáltatások mennyisége beállítással ad fel termékbevételezést vagy szállítói számlát, akkor a rendszer feladja a raktárzott termékek regisztrált mennyiségét, és a nem raktárzott termékek fennmaradó mennyiségét (beleértve a *szolgáltatásokat* és a nem szolgáltatásokat is). E szolgáltatás nélkül a rendszer továbbra is a raktári termékek regisztrált mennyiségét adja fel (beleértve a raktári cikkként beállított szolgáltatásokat), de mindig a nem készleten lévő szolgáltatási termékek teljes rendelt mennyiségét adja fel (*figyelmen* kívül hagyja a Szolgáltatás típusú, nem készleten lévő termékeket). |
| Beszerzés és forrás | Nyomon követési dimenziók szinkronizálása vállalatközi értékesítési és beszerzésirendelési-sorokban | Ezzel a funkcióval szabályozható, hogy a sorozatszám- és kötegszám-követési dimenziók szinkronizálva vannak-e a vállalatközi értékesítési és beszerzésirendelés-sorok között. Új beállításokat **ad** **·** **hozzá** a vevőkhöz és szállítókhoz a Vállalatközi beállítási lap beszerzési rendelésekkel és értékesítési rendelésekkel kapcsolatos irányelveit is. Ezenkívül frissíti néhány kapcsolódó, közeli beállítás nevét is.<br><br>Ha raktárkezelési folyamatokat (WMS) használ, ne feledje, hogy ez a funkció csak akkor szinkronizálja a köteg- és sorozatszámokat, ha a dimenziók a cél foglalási hierarchiájában a hely fölött vannak. |
| Termékinformációk kezelése | Termékattribútum-értékek tisztítása | Ez a funkció hozzáad egy **Termékattribútum-értékek** tisztítása nevű ismétlődő feladatot, amely tisztítja az olyan termékattribútum-értékrekordokat, amelyek már nem termékkategórián keresztül kapcsolódnak egy termékhez sem. |
| Készlet- és raktárkezelés | (Oroszország) Eltérések megakadályozása GTD-k kiadásakor az olyan beszerzési rendeléseknél, amelyekhez WMS-hez engedélyezett cikkek tartoznak | Ez a funkció csak az orosz honosításhoz használható. Megakadályozza az orosz vámárunyilatkozat-számok (GTD-k) kiadása során a raktárkezelési folyamatokhoz engedélyezett cikkeket magukban foglaló importrendelések (GTD) ellentmondásait. A GTD-kiadási folyamat módosítja az egyéni naplóban szereplő számlák kapcsolódó készlettranzakcióinak néhány készletdimenzió-értékét, ami eltéréseket okozhat a beszerzési rendelés munkarekordjai és a beszerzés készlettranzakciói között. Ha ez a funkció engedélyezve van, akkor a GTD-kiadási folyamat olyan helyesbítési munkát generál, amely kiküszöböli az ilyen eltéréseket. |
| Raktárkezelés | GS1 vonalkódok továbbfejlesztett elemzője | Ez a funkció továbbfejlesztett elemzőt ad a GS1 szimbólumadatokhoz. Az új elemző a GS1 Általános specifikáció algoritmust valósítja meg a GS1 szimbólumok elemzési funkcióval, és megerősített adatellenőrzést biztosít. További információ a [GS1 vonalkód beolvasásában található](../warehousing/gs1-barcodes.md). |
| Raktárkezelés | Warehouse Management alkalmazás – üres GTD | Ez a funkció csak az orosz honosításhoz használható. Lehetővé teszi a Raktárkezelés mobilalkalmazást használó dolgozók számára, hogy szükség esetén üresen hagyják az orosz vámárunyilatkozat-számokat (GTD-ket). Ha a GTD nyomon követési dimenzió úgy van beállítva, hogy üres értékeket engedélyezzen, a rendszer elfogadja az üres értékeket az aktuális készlet rendelkezésre álló készletének megfelelő készletműveletek GTD-értékeként. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

Nemrégiben hozzáadta vagy jelentősen frissítettük a következő súgócikkeket. Ezek a cikkek nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszok felsorolják. Előfordulhat azonban, hogy segítenek a meglévő funkciókból további lehetőségeket kihozni.

| Szolgáltatásterület | Új vagy frissített cikkek |
|---|---|
| Költségkezelés | A frissített példák és diagramok a következő cikkekhez hozzáadva:<ul><li>[FIFO tényleges értékkel és jelöléssel](../cost-management/fifo-physical-value-marking.md)</li><li>[LIFO tényleges értékkel és jelöléssel](../cost-management/lifo-physical-value-marking.md)</li><li>[LIFO dátum tényleges értékkel és jelöléssel](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Mozgóátlagon alapuló önköltségi ár](../cost-management/running-average-cost-price.md)</li><li>[Súlyozott átlag tényleges értékkel és jelöléssel](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A pénzügyi és az üzemeltetési alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.26 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és műveleti alkalmazások (2022. május 10.) 10.0.26-os verziójának Platformfrissítései.](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md)

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.26 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 és ipari felhők: 2022-es 1. kiadási hullám csomag

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Tekintse meg a [Dynamics 365 és ipari felhők: 2022-es 1. kiadási hullám csomag](/dynamics365-release-plan/2022wave1/) tartalmát. A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [cikk Eltávolított Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) vagy elavult funkciói olyan funkciókat írnak le, amelyek már el vannak távolítva, illetve amelyek már el vannak távolítva vagy elavultak az Ellátásilánc-kezeléshez.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a funkciót eltávolítanának a termékből, [Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) az értékcsökkenési értesítés 12 hónappal az eltávolítás előtt törlődik az Eltávolított vagy elavult funkciókból.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

