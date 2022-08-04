---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.25. (2022. április ) szolgáltatásban
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.25 rendszer új vagy módosult funkcióit ismerteti.
author: kamaybac
ms.date: 03/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c54534ae32aa037f36a16600a058bca6d433002c
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/15/2022
ms.locfileid: "9167731"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10025-april-2022"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.25. (2022. április ) szolgáltatásban

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.25-ös verziójában. Ennek a verziónak 10.0.1149 a buildszáma, és a következő módon érhető el:

- **Előzetes kiadás:** 2022. február
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. március
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. április

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk első közzététele után frissítjük ezt a cikket, hogy szerepeljenek a buildben található funkciók.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Készlet&nbsp;és&nbsp;logisztika | [Veszélyes anyagok fejlesztései](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | Hamarosan | Funkciókezelés:<br>*Veszélyes anyagok fejlesztései* |
| Készlet&nbsp;és&nbsp;logisztika | [Csomagolási munka a csomagolási állomásokhoz](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | Hamarosan | Funkciókezelés:<br>*Csomagolási munka a csomagolási állomásokhoz* |
| Készlet&nbsp;és&nbsp;logisztika | [Vonalkódok beolvasása a raktárban a GS1 formátumszabványok alapján](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [GS1-vonalkódok és QR-kódok](../warehousing/gs1-barcodes.md) | Funkciókezelés:<br>*GS1-vonalkódok beolvasása* |
| Gyártás | [Anyagfelhasználás és -foglalások a termelési emelet végrehajtási felületén](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [A termelési üzem végrehajtási felületének használata dolgozók számára](../production-control/production-floor-execution-use.md) | Funkciókezelés:<br>*Anyagfelhasználás regisztrálása a termelési emelet végrehajtási felületén (nem WMS)*<br><br>Illetve:<br><br>Funkciókezelés:<br>*(Előnézet) Anyagfelhasználás regisztrálása a termelési üzem végrehajtási felületén (WMS-kompatibilis)* |
| Tervezés | [Tervezési optimalizálás központosított naptár karbantartása](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-centralized-calendar-maintenance) | [Naptárak és alaptervezés](../master-planning/supply-chain-calendars-master-planning.md) | Alapértelmezés szerint engedélyezve |
| Tervezés | [Tervezési optimalizálási javaslatok a meglévő készlet optimalizálása érdekében](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Műveletkérő üzenetek](../master-planning/action-messages.md) | Alapértelmezés szerint engedélyezve |
| Tervezés | Tervezett rendelések egyszerűsítve | [Tervezett rendelések egyszerűsítve](../master-planning/planning-optimization/planned-orders-simplified.md ) | Funkciókezelés:<br>*Tervezett rendelések egyszerűsítve* |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni [, akkor ezt a funkciókezelésben kell megtenni.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Készlet- és raktárkezelés | (Lengyelország) Engedélyezze több egységes vámáru-nyilatkozati számla kapcsolását egy beszerzésirendelés-sorhoz, egy egységes vámáru-nyilatkozaton belül | Ez a funkció lehetővé teszi a beszerzésirendelés-sorok felosztását és egyetlen adminisztratív dokumentumhoz (egységes egységes dokumentum) való csatolását, amikor a beszerzési rendelés sorait több különböző számlára (például különböző szállítmányok számára) adva fel. |
| Beszerzés és forrás | Több beszerzési igénylés konszolidálása egyetlen beszerzési rendelésben, könyvelési dátum alapján | Ez a funkció lehetővé teszi több beszerzési igénylés egyetlen beszerzési rendelésbe történő konszolidálását, ha a különböző beszerzési igénylések könyvelési dátuma eltérő. A beszerzési rendelések létrehozására és az igénykonszolidációra vonatkozó beszerzési irányelvszabályok beállításával automatizálható az igénylési soroknak a beszerzési rendelés szintjén könyvelési dátum szerinti csoportosítására vonatkozó döntés. A beszerzési rendelés könyvelési dátum szerinti konszolidációja nem támogatott, ha engedélyezve van a költségvetés-ellenőrzés, mert a könyvelési dátum költségvetési foglalások és kötelezettségvállalás esetén használatos. Ezért azt meg kell őrizni a beszerzési igénylésről a beszerzési rendelésre való átállás során. |
| Beszerzés és forrás | Örökölt alapértelmezett ajánlatkérési válaszmező-beállítások megjelenítése | Ez a funkció visszaállítja az ajánlatkérésre adott korábbi alapértelmezett válaszmező-beállításokat, amelyeket korábban eltávolítottak a felhasználói felületről. Ezek a beállítások nem biztosítanak a dobozból semmilyen funkciót, de igény szerint testreszabhatók. Akkor engedélyezze ezt a funkciót, ha a szervezet már hozzáadott funkciókat az alapértelmezett ajánlatkérési mező beállításaihoz, vagy tervezi. Ha ez a funkció engedélyezve van, **akkor a beállítások eléréséhez el kell férni a Beszerzés és forrás paraméterei lapra,** **megnyitva az Ajánlatkérés lapot,** és be kell választani az Alapértelmezett ajánlatkérés válaszmezőit **.** |
| Beszerzés és forrás | A szállító pénzügyi dimenzióinak egyesítése aktív dimenziókapcsolatú pénzügyi dimenzióval a beszerzési rendelésen | Ezzel a funkcióval a beszerzési igénylés jóváhagyása után egyesítheti az aktív dimenziókapcsolat-dimenziókkal működő szállítók pénzügyi dimenzióit, amennyiben kapcsolatot ad meg a pénzügyi dimenzió és a hely készletdimenzió között. A beszerzési rendelések létrehozása és az igénykonszolidáció beszerzési irányelvszabályai a beszerzési rendelés fejlécének szintjén lévő, aktív dimenziókapcsolattal működő szállítók pénzügyi dimenzióinak egyesítésére vonatkozó döntést lehet hozni. |
| Gyártásvezérlés | (Oroszország) Alapértelmezett helybeállítás engedélyezése a termelési receptúrához/anyagjegyzékhez, valamint automatikus GTD-foglalás/-felhasználás a termelésben | Ez a funkció további beállításokat ad az importált nyersanyagokból való termeléshez (csak orosz honosítás):<ul><li>Beállítás a termelési képletek és az anyagjegyzékek automatikus alapértelmezett helyének beállításával mind az erőforráscsoportokban, mind a raktárakban.</li><li>A nyersanyagok automatikus foglalása *a WMS által aktivált raktárak GTD-szám* dimenziója alapján, a nem WMS foglalási algoritmus szerint. Ez akkor érvényes, ha a nyersanyag-kitárolásra vonatkozó munkaházirend Soha beállítású, és a raktár, a hely és a cikkszám beállítása megegyezik *a* **·** *termelési* rendelés (kötegrendelés) készlettranzakcióival.</li><li>Nyersanyagok automatikus felhasználás *GTD-szám dimenzió* szerint a kitárolási lista feladása során, a korábban ismertetett beszerzett foglalásnak megfelelően.</li></ul> |
| Raktárkezelés | (Előnézet) Skálázási egység támogatása bejövő és kimenő raktári rendelésekhez | A funkció hatására a rendszer létrehozza a kimenő raktári rendeléseket a raktárba történő kiadási folyamat során, és bejövő raktári rendeléseket hoz létre az áthozott rendelések kiszállítva történő feladása során. A rendszer ezután szinkronizálja az egyes bejövő vagy kimenő raktári rendeléseket a rendelés szállításáért vagy fogadásáért felelős mérlegegységével. Ne feledje, hogy a funkció engedélyezése után frissíteni kell a raktár-végrehajtási terheléseket. További információk: [Raktárkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Ehhez a *funkcióhoz szükség van az ASN-szolgáltatásból* való kivezetésre, és lehetővé teszi az átvezetési rendelések fogadását a Raktárkezelés mobilalkalmazás tábla bevételi folyamatának használatával. |

## <a name="feature-state-changes-in-this-release"></a>Funkcióállapot-változások ebben a verzióban

Az alábbi táblázat felsorolja azokat a funkciókat, amelyek kötelezővé vagy alapértelmezés szerint 10.0.25-től indulnak. A 10.0.25-ös frissítés után a rendszer automatikusan bekapcsolja ezeket a funkciókat. A kötelező szolgáltatások nem kikapcsolhatók, [de az alapértelmezés szerint bekapcsolt funkciók a Funkciókezelés segítségével továbbra is kikapcsolhatóak](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A táblázat felsorolja azokat a funkciókat is, amelyek korábban nyilvános előnézetben voltak, de a 10.0.25-ös verzióban általánosan elérhetővé váltak, ami azt jelenti, hogy ajánlott őket éles környezetben használni. Ezek a funkciók alapértelmezés szerint ki vannak kapcsolva, hacsak nincs jelezve más, [ezért](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) használatukhoz a Funkciókezelést kell használni.

| Modul | Funkció neve | Funkció állapota |
| --- | --- | --- |
| Eszközkezelés | [A munkarendelések karbantartási terv futtatása közbeni csoportosítására vonatkozó szabályok alkalmazása](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | Általánosan elérhető |
| Eszközkezelés | [Számlálón alapuló karbantartási fejlesztések](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | Általánosan elérhető |
| Költségkezelés | [Költségszámítási szint](../cost-management/cost-calculation-level.md) | Általánosan elérhető |
| Költségkezelés | Felhasználó által definiált kötegszám beállításának engedélyezése a készletzárás sztornírozásához | Általánosan elérhető |
| Költségkezelés | [Készletzárás folyamatának részletei](whats-new-scm-10-0-21.md) | Általánosan elérhető |
| Költségkezelés | [A pénzügyi dimenziók alapértelmezett értékeire vonatkozó beállítások a készlet elszámolóárának átértékeléséhez](../cost-management/manage-standard-cost-updates.md) | Általánosan elérhető |
| Költségkezelés | Készletérték-jelentés adatainak tisztítása | Alapértelmezés szerint be |
| Költségkezelés | [Készletérték-jelentés tárolója](../cost-management/inventory-value-report-storage.md) | Alapértelmezés szerint be |
| Költségkezelés | Készletzárási napló megjelenítése rácsban | Alapértelmezés szerint be |
| Tervezési változáskezelés | [Változáskezelés engedélyezése meglévő termékek esetében](../engineering-change-management/change-management-existing-products.md) | Alapértelmezés szerint be |
| Tervezési változáskezelés | [Tervezési változáskezelés](../engineering-change-management/product-engineering-overview.md) | Alapértelmezés szerint be |
| Tervezési változáskezelés | [Tervezési értesítések a termelés számára](../engineering-change-management/engineering-change-management.md) | Alapértelmezés szerint be |
| Tervezési változáskezelés | [Továbbfejlesztett attribútumöröklődés a tervezési változáskezeléshez](../engineering-change-management/engineering-attributes-and-search.md) | Alapértelmezés szerint be |
| Tervezési változáskezelés | [Receptúrák és összetevőik módosításainak kezelése](../engineering-change-management/manage-formula-changes.md) | Alapértelmezés szerint be |
| Tervezési változáskezelés | [Termékkészültségi ellenőrzések](../engineering-change-management/product-readiness.md) | Alapértelmezés szerint be |
| Tervezési változáskezelés | [Változatlétrehozás tervezési termékekhez](../engineering-change-management/engineering-variants.md) | Alapértelmezés szerint be |
| Készlet- és raktárkezelés | Navigálás az anyagjegyzéksorok anyagjegyzék-verziójához | Kötelező |
| Alaptervezés | [Kötegelhető megerősítés és konszolidáció a tervezett tömeges és csomagolt kötegelt rendelésekhez](whats-new-scm-10-0-20.md) | Általánosan elérhető |
| Alaptervezés | Erőforrás-tervezés karbantartással | Általánosan elérhető |
| Alaptervezés | Az Alapterv beállítása varázsló szolgáltatásainak engedélyezése | Kötelező |
| Alaptervezés | [Előrejelzési modell kiválasztása az Igény-előrejelzés részletei oldalon](../master-planning/manual-adjustments-baseline-forecast.md) | Kötelező |
| Alaptervezés | [Alaptervezés előrehaladásának megjelenítése](../master-planning/tasks/monitor-master-planning-run.md) | Kötelező |
| Alaptervezés | [Tervezett rendelések párhuzamos megerősítése](../master-planning/planning-optimization/planned-order-firming.md) | Kötelező |
| Alaptervezés | [Tervezett rendelés megerősítése szűréssel](../master-planning/planning-optimization/planned-order-firming.md) | Alapértelmezés szerint be |
| Alaptervezés | [Mentett nézetek tervezett rendelésekhez](saved-views-scm.md) | Alapértelmezés szerint be |
| Beszerzés és forrás | Beszerzési igénylés felosztásának visszaállítása gomb letiltása | Általánosan elérhető |
| Beszerzés és forrás | [Beszerzéssel kapcsolatos munkafolyamatok visszaállításának engedélyezése](whats-new-scm-10-0-20.md) | Általánosan elérhető |
| Beszerzés és forrás | Az elfogadott beszerzési rendelések kötegelt megerősítése a szállítói együttműködésből | Kötelező |
| Beszerzés és forrás | Beszerzési szerződés Lezárt állapota | Kötelező |
| Beszerzés és forrás | Sorok hozzáadása a beszerzési szerződéshez társított beszerzési rendelési számlákhoz | Alapértelmezés szerint be |
| Beszerzés és forrás | Megrendelt mennyiség mező hozzáadása a Termékbevételezés feladása oldalhoz | Alapértelmezés szerint be |
| Beszerzés és forrás | [A szállítók beszerzési kategóriákra való jelentkezésének engedélyezése szállítói együttműködésen keresztül](../procurement/category-requests-from-vendors.md) | Alapértelmezés szerint be |
| Beszerzés és forrás | Beszerzési rendelésekből származó kezdő összegek és felső határok | Alapértelmezés szerint be |
| Beszerzés és forrás | Költségek beállítása helyhez és raktárhoz | Alapértelmezés szerint be |
| Beszerzés és forrás | Beszerzési illeték számításának engedélyezése az éves tarifa alapján | Alapértelmezés szerint be |
| Beszerzés és forrás | [Beszerzési szerződésért felelős fél](../procurement/purchase-agreements.md) | Alapértelmezés szerint be |
| Beszerzés és forrás | [Mentett nézetek beszerzési rendelésekhez](saved-views-scm.md) | Alapértelmezés szerint be |
| Termékinformációk kezelése | [Alapértelmezett rendelési mennyiségek szigorú ellenőrzése](../production-control/default-order-settings.md) | Kötelező |
| Termékinformációk kezelése | Darabjegyzék-jelentés előzetes feldolgozása az időtúllépés elkerülése érdekében | Alapértelmezés szerint be |
| Termékinformációk kezelése | Alapértelmezett pénzügyi dimenziók külön cikksablonok használata esetén | Alapértelmezés szerint be |
| Termékinformációk kezelése | Termékdimenzió-csoportok engedélyezése az elemsablonokban | Alapértelmezés szerint be |
| Termékinformációk kezelése | Termékváltozatok neveinek újragenerálása az elnevezési rendszer alapján | Alapértelmezés szerint be |
| Termékinformációk kezelése | [Változatjavaslatok oldalának fejlesztései](../pim/tasks/create-predefined-product-variants.md) | Alapértelmezés szerint be |
| Gyártásvezérlés | Továbbfejlesztett termelési tényleges súly szerinti mennyiséggel való kitárolás | Általánosan elérhető |
| Gyártásvezérlés | A Szünet vége új gombja felkerült a feladatkártya termináljára | Kötelező |
| Gyártásvezérlés | [Az azonosítótábla-szám automatikus létrehozásának engedélyezése, amikor a feladatkártya eszközében befejezettként jelentik](../production-control/production-floor-execution-configure.md) | Kötelező |
| Gyártásvezérlés | Alvállalkozói cikkek részleges bevételezésének engedélyezése és probléma kijavítása a Szállító típusú anyagjegyzéksorok selejtszámításával | Kötelező |
| Gyártásvezérlés | [A feladatkártya-eszköz és a feladatkártya-terminál zárolására alkalmas funkció az eszközök fertőtlenítése érdekében](../production-control/production-floor-execution-configure.md) | Kötelező |
| Gyártásvezérlés | A Jóváhagyás és az Átviteli feladatok párbeszédpanelek javításai | Kötelező |
| Gyártásvezérlés | [A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla](../production-control/production-floor-execution-configure.md) | Kötelező |
| Gyártásvezérlés | [Címke nyomtatása a Feladatkártya eszközéből](../production-control/production-floor-execution-configure.md) | Kötelező |
| Gyártásvezérlés | [Termelési üzem végrehajtása](../production-control/production-floor-execution-configure.md) | Kötelező |
| Gyártásvezérlés | [A termelési üzem végrehajtási felületére vonatkozó eszközkezelési funkció](../production-control/production-floor-execution-configure.md) | Alapértelmezés szerint be |
| Gyártásvezérlés | [Feladatkeresés a gyártóüzem végrehajtási interfészén](../production-control/production-floor-execution-configure.md) | Alapértelmezés szerint be |
| Gyártásvezérlés | [Alapértelmezett termelési foglalás felülbírálása](../production-control/override-default-reservation-principle.md) | Alapértelmezés szerint be |
| Gyártásvezérlés | [Teljes sorozatszám, köteg- és azonosítótáblaszám megjelenítése a termelési üzem végrehajtási felületén](whats-new-scm-10-0-21.md) | Alapértelmezés szerint be |
| Értékesítés és marketing | [Értékesítési rendelés részleteinek teljesítményjavítása](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Általánosan elérhető |
| Értékesítés és marketing | Értékesítési ajánlat részleteinek teljesítményjavítása | Általánosan elérhető |
| Értékesítés és marketing | Értékesítési rendelés hivatkozott adatexportálási irányelve | Kötelező |
| Értékesítés és marketing | [Értékesítési rendelésről beszerzésirendelés-sorra mutató hivatkozás esetén érvényes törlési irányelv](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | Kötelező |
| Értékesítés és marketing | [Értékesítési ajánlat hivatkozott adatexportálási irányelve](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| Kötelező |
| Értékesítés és marketing | [Kapcsolattartó személy adatentitás-exportálásának optimalizálása](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Alapértelmezés szerint be |
| Értékesítés és marketing | Keresés engedélyezése az értékesítési árajánlat dokumentumbevezető és dokumentum-összefoglaló mezőinél | Alapértelmezés szerint be |
| Értékesítés és marketing | [A 100 legjelentősebb vevő jelentés teljesítményének javítása](whats-new-scm-10-0-23.md) | Alapértelmezés szerint be |
| Értékesítés és marketing | Becsült vevői egyenleg újraszámítása | Alapértelmezés szerint be |
| Értékesítés és marketing | [Értékesítési visszárurendelés-sor regisztrálása decimális pontossággal, tényleges súllyal vagy anélkül](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Alapértelmezés szerint be |
| Értékesítés és marketing | [Mentett nézetek értékesítéshez és marketinghez](saved-views-scm.md) | Alapértelmezés szerint be |
| Értékesítés és marketing | Egykattintásos értékesítésirendelés-megerősítés | Alapértelmezés szerint be |
| Raktárkezelés | [Áttárolási sablonok helyutasításokkal](../warehousing/planned-cross-docking.md) | Általánosan elérhető |
| Raktárkezelés | [Zárolt készletet mintaként tartalmazó minőségi rendelésekből várt bevételezések letiltása](../inventory/inventory-blocking.md) | Általánosan elérhető |
| Raktárkezelés | Azonosítótábla bevételezési előzményei | Általánosan elérhető |
| Raktárkezelés | [Anyagkezelési berendezések kezelői felülete](../warehousing/mhax.md) | Általánosan elérhető |
| Raktárkezelés | [Mennyiségek lekerekítése a legközelebbi értékesítési egységre a raktárba való kiadáskor](whats-new-scm-10-0-19.md) | Általánosan elérhető |
| Raktárkezelés | Skálázási egység támogatása a raktári alkalmazás munkalistáihoz | Általánosan elérhető |
| Raktárkezelés | Szállítmányhullám-címke részletei | Általánosan elérhető |
| Raktárkezelés | [Gyorsabb API használata a csomagolási állomáson lévő zárási/újranyitási tárolókhoz](whats-new-scm-10-0-21.md) | Általánosan elérhető |
| Raktárkezelés | [Feltöltési feladatokhoz kiválasztott sablonok ellenőrzése](whats-new-scm-10-0-20.md) | Általánosan elérhető |
| Raktárkezelés | Meglévő azonnali feltöltési munka (egységek között) használatának engedélyezése a feltöltési sablon számára | Kötelező |
| Raktárkezelés | A GUID azonosítók automatikus hozzárendelése a whs felhasználó létrehozásakor | Kötelező |
| Raktárkezelés | A termékváltozatok és nyomon követési dimenziók rögzítése a raktárkezelési alkalmazásban a rakománycikkek bevételezése során | Kötelező |
| Raktárkezelés | [A nyomon követési dimenziók által szabályozott cikkek készletállapotának módosítása](../inventory/inventory-statuses.md) | Kötelező |
| Raktárkezelés | [Munkagyűjtő módosítása a munkán](../warehousing/change-work-pool-on-work.md) | Kötelező |
| Raktárkezelés | [Fürtpozíció tele](../warehousing/cluster-position-full.md) | Kötelező |
| Raktárkezelés | [Fürt betárolása funkció](../warehousing/putaway-clusters.md) | Kötelező |
| Raktárkezelés | [Megerősítés és áthelyezés](../warehousing/confirm-and-transfer.md) | Kötelező |
| Raktárkezelés | [Kimenő szállítmányok jóváhagyása kötegelt feladatokból](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | Kötelező |
| Raktárkezelés | [Annak szabályozása, hogy megjelenjen-e bevételezési összesítő oldal a mobileszközökön](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Kötelező |
| Raktárkezelés | [Manuális készletmozgási művelet halasztott feldolgozása](../warehousing/deferred-processing-manual-inventory-movement.md) | Kötelező |
| Raktárkezelés | Ne engedélyezze olyan rakományok létrehozására, amelyek nem engedik meg a hullámterhelés-létrehozási sablon követelményeit | Kötelező |
| Raktárkezelés | [Bővített azonosítótábla-címkeelrendezések](../warehousing/document-routing-layout-for-license-plates.md) | Kötelező |
| Raktárkezelés | [Összes művelet kiértékelése több raktározási egység helyutasításai esetében](/troubleshoot/dynamics-365/supply-chain/warehousing/evaluate-multiple-location-directive-actions) | Kötelező |
| Raktárkezelés | A Teljes érték mező elrejtése a „Minden rakomány” és a „Rakomány részletei” lapon | Kötelező |
| Raktárkezelés | Azonosítótábla-címke buildkonfigurációja | Kötelező |
| Raktárkezelés | Rakománysor manuális helyesbítése rendszergazdák vagy hasonló megbízható felhasználók számára | Kötelező |
| Raktárkezelés | [Hely azonosítótáblájának elhelyezése](../warehousing/location-license-plate-positioning.md) | Kötelező |
| Raktárkezelés | [Hely és termékdimenzió kombinálása](../warehousing/location-product-dimension-mixing.md) | Kötelező |
| Raktárkezelés | A mobileszközzel történő készletmozgatás készletállapota mező szerkeszthetővé tétele | Kötelező |
| Raktárkezelés | Manuális értékesítési sor kitárolási szolgáltatása felügyeleti vagy hasonló megbízható felhasználók számára | Kötelező |
| Raktárkezelés | [Az átmozgatási rendelés által leszállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárakban](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Kötelező |
| Raktárkezelés | A nem egyértelmű „Hely/azonosítótábla” nevek feloldásának kérése | Kötelező |
| Raktárkezelés | [Minőség-ellenőrzés](../warehousing/quality-check.md) | Kötelező |
| Raktárkezelés | [Felhasználói beállítások, ikonok és lépéscímek az új raktárkezelési alkalmazáshoz](../warehousing/install-configure-warehouse-management-app.md) | Kötelező |
| Raktárkezelés | [További helyzóna](../warehousing/additional-location-zones.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Átmozgatási rendelések létrehozása és feldolgozása a raktári alkalmazásból](../warehousing/create-transfer-order-from-warehouse-app.md) | Alapértelmezés szerint be |
| Raktárkezelés | Gyors ellenőrzés engedélyezése raktárkezelési mobileszközökhöz | Alapértelmezés szerint be |
| Raktárkezelés | [A raktárkezelés készleten lévő tételek karbantartására vonatkozó feladatának maximális végrehajtási ideje](../warehousing/onhand-cleanup.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Kimenő munkaterhelések megjelenítése](../warehousing/outbound-workload-visualization.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Raktári alkalmazás eseményeinek feldolgozása](../warehousing/warehouse-app-events.md) | Alapértelmezés szerint be |
| Raktárkezelés | [A rakománytervezési munkaterület mentett nézetei](saved-views-scm.md) | Alapértelmezés szerint be |
| Raktárkezelés | [A munka részleteit tartalmazó oldal mentett nézete](saved-views-scm.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Hullámfeldolgozás mentett nézete](saved-views-scm.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Rakományfeldolgozás mentett nézetei](saved-views-scm.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Szállítmányfeldolgozás mentett nézetei](saved-views-scm.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Hullámkötegelt feladat részletei](../warehousing/wave-processing.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Hullámvégrehajtási értesítések](../warehousing/wave-execution-notifications.md) | Alapértelmezés szerint be |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A pénzügyi és az üzemeltetési alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.25 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és műveleti alkalmazások (2022. április 10.) 10.0.25-ös verziójának platformfrissítései.](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md)

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.25 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

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

