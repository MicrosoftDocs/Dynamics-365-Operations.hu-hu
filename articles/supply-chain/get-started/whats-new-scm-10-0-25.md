---
title: A Dynamics 365 Supply Chain Management 10.0.25 előzetes verziója (2022. április)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.25 új vagy módosított szolgáltatásait írja le.
author: kamaybac
ms.date: 02/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 0ce9bc4685542cf691d862c0fec76f3f7b40c6b6
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087320"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10025-april-2022"></a>A Dynamics 365 Supply Chain Management 10.0.25 előzetes verziója (2022. április)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.25 előzetes kiadásának új vagy módosított szolgáltatásait írja le. Ennek a verziónak 10.0.1149 a buildszáma, és a következő módon érhető el:

- **Előzetes kiadás:** 2022. február
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. március
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. április

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a funkciókat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Szolgáltatásterület | Funkció | További információ | Engedélyezte:   |
|---|---|---|---|
| Készlet&nbsp;és&nbsp;logisztika | Veszélyes anyagok fejlesztései | Ezek a fejlesztések a veszélyes anyagok meglévő funkcióira épülnek, hogy jobban segítsék a vállalatokat abban, hogy megfeleljenek a helyi előírásoknak, amikor veszélyes anyagokat szállítanak különböző földrajzi területeken. <!-- KFM: Update to 2022w1 link when published -->| Funkciókezelés:<br>*Veszélyes anyagok fejlesztései* |
| Készlet&nbsp;és&nbsp;logisztika | Csomagolási munka a csomagolási állomásokhoz | Ez a funkció nagymértékben javítja a csomagolási és szállítási műveletek rugalmasságát és mozgékonyságát. A csomagolási folyamat során a raktári dolgozók mostantól csomagolhatnak és szállíthatnak egyedi csomagokat, amelyek ugyanahhoz a szállítmányhoz és rakományhoz kapcsolódnak. Az ugyanazon szállítmány részét képező rendelési sorokat nem feltétlenül kell együtt szállítani, ha egyes tételek azonnal szállításra készek. Egyetlen rendelés több csomagban is becsomagolható és kiszállításra kerülhet, különböző szállítási időpontokban, ezáltal csökkentve a várakozási időt és növelve az agilitást.<!-- KFM: Update to 2022w1 link when published --> | Funkciókezelés:<br>*Csomagolási munka a csomagolási állomásokhoz* |
| Készlet&nbsp;és&nbsp;logisztika | [Vonalkódok beolvasása a raktárban a GS1 formátumszabványok alapján](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) <!-- KFM: Update to 2022w1 link when published --> | [GS1-vonalkódok és QR-kódok](../warehousing/gs1-barcodes.md) | Funkciókezelés:<br>*GS1-vonalkódok beolvasása* |
| Gyártás | [Anyagfelhasználás és foglalások a termelési szint végrehajtási felületén](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [A termelési üzem végrehajtási felületének használata dolgozók számára](../production-control/production-floor-execution-use.md) | Funkciókezelés:<br>*(Előnézet) Anyagfelhasználás regisztrálása a termelési üzem végrehajtási felületén (WMS-kompatibilis)* |
| Gyártás | [Regisztrálja az anyagfelhasználást a mértékegységeken](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/register-material-consumption-scale-units) | [Gyártási végrehajtás munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-manufacturing.md) | Funkciókezelés:<br>*Anyagfelhasználás regisztrálása a mobilalkalmazáson egy skálázási egységben* |
| Tervezés | [Tervezés Optimalizálási javaslatok a meglévő kínálat optimalizálására](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Műveletkérő üzenetek](../master-planning/action-messages.md) | Alapértelmezés szerint engedélyezve |
| Tervezés | Tervezett rendelések egyszerűsítve | [Tervezett rendelések egyszerűsítve](../master-planning/planning-optimization/planned-orders-simplified.md ) | Funkciókezelés:<br>*Tervezett rendelések egyszerűsítve* |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha be- vagy kikapcsolni szeretné ezeket a funkciókat, ezt itt kell megtennie [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Készlet- és raktárkezelés | (Lengyelország) Engedélyezze több egységes vámáru-nyilatkozati számla kapcsolását egy beszerzésirendelés-sorhoz, egy egységes vámáru-nyilatkozaton belül | Ezzel a funkcióval feloszthatja a beszerzési rendelési sorokat, és egyetlen adminisztratív dokumentumhoz (SAD) kapcsolhatja őket, amikor ezeket a beszerzési rendelési sorokat több különböző számlához (például különböző szállítmányokhoz) könyvelték. |
| Beszerzés és forrás | Több beszerzési igénylés konszolidálása egyetlen beszerzési rendelésben, könyvelési dátum alapján | Ez a szolgáltatás lehetővé teszi több beszerzési igény egyetlen beszerzési rendelésbe történő összevonását, ha a különböző beszerzési igények eltérő elszámolási dátummal rendelkeznek. Beszerzési rendelés létrehozása és keresletkonszolidációs beszerzési szabályzat szabályai beállíthatók az igénylési sorok számviteli dátum szerinti csoportosítására vonatkozó döntés automatizálására a beszerzési rendelés szintjén. A beszerzési rendelés könyvelési dátum szerinti konszolidációja nem támogatott, ha a költségvetés-ellenőrzés engedélyezve van, mert a könyvelési dátumot a költségvetési foglalásokhoz és megterhelésekhez használják. Ezért meg kell őrizni a beszerzési igényről a beszerzési megrendelésre való áttérés során. |
| Beszerzés és forrás | Beszerzési igénylés felosztásának visszaállítása gomb letiltása | Ez a funkció letiltja a **Visszaállítás** gombot a **Számviteli elosztás** oldal a felülvizsgálat alatt álló beszerzési igényekhez. |
| Beszerzés és forrás | Örökölt alapértelmezett ajánlatkérési válaszmező-beállítások megjelenítése | Ez a funkció újra bevezeti a korábbi alapértelmezett ajánlatkérési (RFQ) válaszmezőbeállításokat, amelyeket korábban eltávolítottak a felhasználói felületről. Ezek a beállítások a dobozból nem biztosítanak semmilyen funkcionalitást, de szükség szerint testreszabhatók. Engedélyezze ezt a funkciót, ha szervezete már hozzáadott funkciókat az alapértelmezett ajánlatkérés-válaszmezőbeállításokhoz, vagy ezt tervezi. Ha ez a funkció engedélyezve van, a beállításokat a következő oldalon érheti el **Beszerzési és beszerzési paraméterek** oldal megnyitásával a **Ajánlatkérés** fület, és válassza ki **Alapértelmezett ajánlatkérési válaszmezők**. |
| Beszerzés és forrás | A szállító pénzügyi dimenzióinak egyesítése aktív dimenziókapcsolatú pénzügyi dimenzióval a beszerzési rendelésen | Ez a funkció lehetővé teszi az aktív dimenzióhivatkozás pénzügyi dimenziókkal rendelkező szállítók pénzügyi dimenzióinak összevonását a beszerzési igény jóváhagyása után, ha kapcsolatot hoz létre egy pénzügyi dimenzió és a helyszíni készletdimenzió között. Beszerzési rendelés-létrehozási és keresletkonszolidációs beszerzési szabályokat lehet beállítani, hogy meghozzák a döntést a beszerzési rendelés fejléc szintjén aktív dimenziólink pénzügyi dimenzióval rendelkező szállítók pénzügyi dimenzióinak összevonásáról. |
| Gyártásvezérlés | (Oroszország) Az alapértelmezett helybeállítás engedélyezése a termelési képlethez/BOM-hoz és az automatikus GTD-foglaláshoz/-fogyasztáshoz a termelésben | A funkció további lehetőségeket tesz lehetővé az importált nyersanyagokból történő gyártáshoz (csak orosz lokalizáció):<ul><li>Lehetőség a termelési képletek és anyagjegyzékek automatikus alapértelmezett helyének beállítására mind az erőforráscsoportokon, mind a raktárakon.</li><li>Az alapanyagok automatikus lefoglalása a *GTD szám* dimenzió a WMS által aktivált raktárakban a nem WMS foglalási algoritmus szerint. Ez azokra az esetekre vonatkozik, amikor a munkapolitika *Nyersanyag szedés* -vel létezik **Munkaalkotási módszer** állítva *Soha* és a raktár, hely és cikkszám beállítás megegyezik a gyártási (kötegelt) rendelés készlettranzakcióival.</li><li>Automatikus alapanyag-felhasználás által *GTD szám* méret a komissiózási lista feladáskor, a korábban leírt megszerzett foglalás szerint.</li></ul> |
| Raktárkezelés | Zárolt készletet mintaként tartalmazó minőségi rendelésekből várt bevételezések letiltása | Ez a szolgáltatás megakadályozza, hogy a rendszer elvárt bevételezési tranzakciókat hozzon létre olyan minőségi rendelésekhez, amelyek blokkolt állapotú készletmintát vesznek. Mivel a blokkolt készlet nem érhető el, ez a funkció eltávolítja a várt bevételeket. Ez segít abban, hogy a készlet ne végződjön több letiltási állapottal, ami adatintegritási problémákat okozhat. |
| Raktárkezelés | (Előnézet) Skálázási egység támogatása bejövő és kimenő raktári rendelésekhez | Ez a funkció arra készteti a rendszert, hogy kimenő raktári rendeléseket hozzon létre a raktárba történő kiadás folyamata során, és bejövő raktári rendeléseket hozzon létre, amikor az átviteli rendeléseket leszállított állapotban adják fel. A rendszer ezután minden bejövő vagy kimenő raktári rendelést szinkronizál a rendelés szállításáért vagy fogadásáért felelős mérlegegységgel. Vegye figyelembe, hogy a funkció engedélyezése után frissíteni kell a raktári végrehajtási munkaterheléseket. További információk: [Raktárkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Ez a funkció megköveteli a *Válassza le az elhelyezett munkát az ASN-ekről* funkció, és lehetővé teszi az átutalási megbízások fogadását a Raktárkezelés mobilalkalmazásban a rendszámfogadási folyamat segítségével. |

## <a name="feature-state-changes-in-this-release"></a>A szolgáltatás állapotának változásai ebben a kiadásban

Az alábbi táblázat azokat a szolgáltatásokat sorolja fel, amelyek a 10.0.25-től kezdve kötelezővé váltak vagy alapértelmezés szerint bekapcsoltak. Mindezek a szolgáltatások automatikusan bekapcsolódnak a rendszeren, amint frissít a 10.0.25-ös verzióra. A kötelező funkciókat nem lehet kikapcsolni, de az alapértelmezés szerint bekapcsolt funkciókat továbbra is ki lehet kapcsolni [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A táblázat azokat a funkciókat is felsorolja, amelyek korábban nyilvános előnézetben voltak, de a 10.0.25-ben általánosan elérhetővé váltak, ami azt jelenti, hogy mostantól éles környezetben is használhatók. Ezek a szolgáltatások alapértelmezés szerint ki vannak kapcsolva, hacsak nincs másképp jelezve, ezért használnia kell [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) hogy engedélyezze őket, ha használni szeretné őket.

| Modul | Funkció neve | Funkció állapota |
| --- | --- | --- |
| Eszközkezelés | Szabályok alkalmazása munkarendelések csoportosítására karbantartási terv futtatása közben | Általánosan elérhető |
| Eszközkezelés | Számlálón alapuló karbantartási fejlesztések | Általánosan elérhető |
| Költségkezelés | Költségszámítási szint | Általánosan elérhető |
| Költségkezelés | Felhasználó által definiált kötegszám beállításának engedélyezése a készletzárás sztornírozásához | Általánosan elérhető |
| Költségkezelés | Készletzárás folyamatának részletei | Általánosan elérhető |
| Költségkezelés | A pénzügyi dimenziók alapértelmezett értékeire vonatkozó beállítások a készlet elszámolóárának átértékeléséhez | Általánosan elérhető |
| Költségkezelés | Készletérték-jelentés adatainak tisztítása | Alapértelmezés szerint be |
| Költségkezelés | Készletérték-jelentés tárolója | Alapértelmezés szerint be |
| Költségkezelés | Készletzárási napló megjelenítése rácsban | Alapértelmezés szerint be |
| Tervezési változáskezelés | Változáskezelés engedélyezése meglévő termékek esetében | Alapértelmezés szerint be |
| Tervezési változáskezelés | Tervezési változáskezelés | Alapértelmezés szerint be |
| Tervezési változáskezelés | Tervezési értesítések a termelés számára | Alapértelmezés szerint be |
| Tervezési változáskezelés | Továbbfejlesztett attribútumöröklődés a tervezési változáskezeléshez | Alapértelmezés szerint be |
| Tervezési változáskezelés | Receptúrák és összetevőik módosításainak kezelése | Alapértelmezés szerint be |
| Tervezési változáskezelés | Termékkészültségi ellenőrzések | Alapértelmezés szerint be |
| Tervezési változáskezelés | Változatlétrehozás tervezési termékekhez | Alapértelmezés szerint be |
| Készlet- és raktárkezelés | Navigáció a BOM-verzióhoz a BOM-sorokból | Kötelező |
| Alaptervezés | Kötegelhető megerősítés és konszolidáció a tervezett tömeges és csomagolt kötegelt rendelésekhez | Általánosan elérhető |
| Alaptervezés | Erőforrás-tervezés karbantartással | Általánosan elérhető |
| Alaptervezés | Az alapterv beállítási varázsló funkcióinak engedélyezése | Kötelező |
| Alaptervezés | Előrejelzési modell kiválasztása az Igény-előrejelzés részletei oldalon | Kötelező |
| Alaptervezés | Alaptervezés előrehaladásának megjelenítése | Kötelező |
| Alaptervezés | Tervezett rendelések párhuzamos megerősítése | Kötelező |
| Alaptervezés | Tervezett rendelés megerősítése szűréssel | Alapértelmezés szerint be |
| Alaptervezés | Tervezett rendelések mentett nézete | Alapértelmezés szerint be |
| Beszerzés és forrás | Beszerzési igénylés felosztásának visszaállítása gomb letiltása | Általánosan elérhető |
| Beszerzés és forrás | Beszerzéssel kapcsolatos munkafolyamatok visszaállításának engedélyezése | Általánosan elérhető |
| Beszerzés és forrás | Az elfogadott beszerzési rendelések kötegelt megerősítése a szállítói együttműködésből | Kötelező |
| Beszerzés és forrás | Beszerzési szerződés Lezárt állapota | Kötelező |
| Beszerzés és forrás | Sorok hozzáadása a beszerzési szerződéshez társított beszerzési rendelési számlákhoz | Alapértelmezés szerint be |
| Beszerzés és forrás | Megrendelt mennyiség mező hozzáadása a Termékbevételezés feladása oldalhoz | Alapértelmezés szerint be |
| Beszerzés és forrás | A szállítók beszerzési kategóriákra való jelentkezésének engedélyezése szállítói együttműködésen keresztül | Alapértelmezés szerint be |
| Beszerzés és forrás | Beszerzési rendelésekből származó kezdő összegek és felső határok | Alapértelmezés szerint be |
| Beszerzés és forrás | Költségek beállítása helyhez és raktárhoz | Alapértelmezés szerint be |
| Beszerzés és forrás | Beszerzési illeték számításának engedélyezése az éves tarifa alapján | Alapértelmezés szerint be |
| Beszerzés és forrás | Beszerzési szerződésért felelős fél | Alapértelmezés szerint be |
| Beszerzés és forrás | Mentett nézetek beszerzési rendelésekhez | Alapértelmezés szerint be |
| Termékinformációk kezelése | Alapértelmezett rendelési mennyiségek szigorú ellenőrzése | Kötelező |
| Termékinformációk kezelése | Darabjegyzék-jelentés előzetes feldolgozása az időtúllépés elkerülése érdekében | Alapértelmezés szerint be |
| Termékinformációk kezelése | Alapértelmezett pénzügyi dimenziók külön cikksablonok használata esetén | Alapértelmezés szerint be |
| Termékinformációk kezelése | Termékdimenzió-csoportok engedélyezése az elemsablonokban | Alapértelmezés szerint be |
| Termékinformációk kezelése | Termékváltozatok neveinek újragenerálása az elnevezési rendszer alapján | Alapértelmezés szerint be |
| Termékinformációk kezelése | Változatjavaslatok oldalának fejlesztései | Alapértelmezés szerint be |
| Gyártásvezérlés | Továbbfejlesztett termelési tényleges súly szerinti mennyiséggel való kitárolás | Általánosan elérhető |
| Gyártásvezérlés | A Munkakártya-terminál oldalon egy új gomb került a szünet leállításához | Kötelező |
| Gyártásvezérlés | Az azonosítótábla-szám automatikus létrehozásának engedélyezése, amikor a feladatkártya eszközében befejezettként jelentik | Kötelező |
| Gyártásvezérlés | Engedélyezze az alvállalkozásba kötött cikkek részleges átvételét, és javítsa ki a Szállító típusú anyagjegyzék-sorok selejtszámítási problémáját | Kötelező |
| Gyártásvezérlés | A feladatkártya-eszköz és a feladatkártya-terminál zárolására alkalmas funkció az eszközök fertőtlenítése érdekében | Kötelező |
| Gyártásvezérlés | A Jóváhagyás és az Átviteli feladatok párbeszédpanelek javításai | Kötelező |
| Gyártásvezérlés | A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla | Kötelező |
| Gyártásvezérlés | Címke nyomtatása a Feladatkártya eszközéből | Kötelező |
| Gyártásvezérlés | Termelési üzem végrehajtása | Kötelező |
| Gyártásvezérlés | A termelési üzem végrehajtási felületére vonatkozó eszközkezelési funkció | Alapértelmezés szerint be |
| Gyártásvezérlés | Feladatkeresés a gyártóüzem végrehajtási interfészén | Alapértelmezés szerint be |
| Gyártásvezérlés | Alapértelmezett termelési foglalás felülbírálása | Alapértelmezés szerint be |
| Gyártásvezérlés | Teljes sorozatszám, köteg- és azonosítótáblaszám megjelenítése a termelési üzem végrehajtási felületén | Alapértelmezés szerint be |
| Értékesítés és marketing | Értékesítési rendelés részleteinek teljesítményjavítása | Általánosan elérhető |
| Értékesítés és marketing | Értékesítési ajánlat részleteinek teljesítményjavítása | Általánosan elérhető |
| Értékesítés és marketing | Értékesítési rendelés hivatkozott adatexportálási irányelve | Kötelező |
| Értékesítés és marketing | Értékesítési rendelésről beszerzésirendelés-sorra mutató hivatkozás esetén érvényes törlési irányelv | Kötelező |
| Értékesítés és marketing | Értékesítési ajánlat hivatkozott adatexportálási irányelve | Kötelező |
| Értékesítés és marketing | Kapcsolattartó személy adatentitás-exportálásának optimalizálása | Alapértelmezés szerint be |
| Értékesítés és marketing | Keresés engedélyezése az értékesítési árajánlat dokumentumbevezető és dokumentum-összefoglaló mezőinél | Alapértelmezés szerint be |
| Értékesítés és marketing | A 100 legjelentősebb vevő jelentés teljesítményének javítása | Alapértelmezés szerint be |
| Értékesítés és marketing | Becsült vevői egyenleg újraszámítása | Alapértelmezés szerint be |
| Értékesítés és marketing | Értékesítési visszárurendelés-sor regisztrálása decimális pontossággal, tényleges súllyal vagy anélkül | Alapértelmezés szerint be |
| Értékesítés és marketing | Mentett nézetek értékesítéshez és marketinghez | Alapértelmezés szerint be |
| Értékesítés és marketing | Egykattintásos értékesítésirendelés-megerősítés | Alapértelmezés szerint be |
| Raktárkezelés | Áttárolási sablonok helyutasításokkal | Általánosan elérhető |
| Raktárkezelés | Zárolt készletet mintaként tartalmazó minőségi rendelésekből várt bevételezések letiltása | Általánosan elérhető |
| Raktárkezelés | Azonosítótábla bevételezési előzményei | Általánosan elérhető |
| Raktárkezelés | Mennyiségek lekerekítése a legközelebbi értékesítési egységre a raktárba való kiadáskor | Általánosan elérhető |
| Raktárkezelés | Skálázási egység támogatása a raktári alkalmazás munkalistáihoz | Általánosan elérhető |
| Raktárkezelés | Szállítmányhullám-címke részletei | Általánosan elérhető |
| Raktárkezelés | Gyorsabb API használata a csomagolási állomáson lévő zárási/újranyitási tárolókhoz | Általánosan elérhető |
| Raktárkezelés | Feltöltési feladatokhoz kiválasztott sablonok ellenőrzése | Általánosan elérhető |
| Raktárkezelés | Meglévő azonnali feltöltési munka (egységek között) használatának engedélyezése a feltöltési sablon számára | Kötelező |
| Raktárkezelés | A GUID-k automatikus hozzárendelése a WHS-felhasználók létrehozásához | Kötelező |
| Raktárkezelés | A termékváltozatok és nyomon követési dimenziók rögzítése a raktárkezelési alkalmazásban a rakománycikkek bevételezése során | Kötelező |
| Raktárkezelés | A nyomon követési dimenziók által szabályozott cikkek készletállapotának módosítása | Kötelező |
| Raktárkezelés | Munkagyűjtő módosítása a munkán | Kötelező |
| Raktárkezelés | Fürtpozíció tele | Kötelező |
| Raktárkezelés | Fürt betárolása funkció | Kötelező |
| Raktárkezelés | Megerősítés és áthelyezés | Kötelező |
| Raktárkezelés | Kimenő szállítmányok megerősítése kötegelt feladatokból | Kötelező |
| Raktárkezelés | Annak szabályozása, hogy megjelenjen-e bevételezési összesítő oldal a mobileszközökön | Kötelező |
| Raktárkezelés | Manuális készletmozgási művelet halasztott feldolgozása | Kötelező |
| Raktárkezelés | Ne engedje meg olyan terhelések létrehozását, amelyek nem felelnek meg a hullámterhelés építési sablon követelményeinek | Kötelező |
| Raktárkezelés | Bővített azonosítótábla-címkeelrendezések | Kötelező |
| Raktárkezelés | Összes művelet kiértékelése több raktározási egység helyutasításai esetében | Kötelező |
| Raktárkezelés | A Teljes érték mező elrejtése a „Minden rakomány” és a „Rakomány részletei” lapon | Kötelező |
| Raktárkezelés | Azonosítótábla-címke buildkonfigurációja | Kötelező |
| Raktárkezelés | Rakománysor manuális helyesbítése rendszergazdák vagy hasonló megbízható felhasználók számára | Kötelező |
| Raktárkezelés | Hely azonosítótáblájának elhelyezése | Kötelező |
| Raktárkezelés | Hely és termékdimenzió kombinálása | Kötelező |
| Raktárkezelés | A mobileszközzel történő készletmozgatás készletállapota mező szerkeszthetővé tétele | Kötelező |
| Raktárkezelés | Manuális értékesítési sor kitárolási szolgáltatása felügyeleti vagy hasonló megbízható felhasználók számára | Kötelező |
| Raktárkezelés | Az átmozgatási rendelés által leszállított azonosítótáblák használatának megakadályozása a célraktártól eltérő raktárakban | Kötelező |
| Raktárkezelés | A nem egyértelmű „Hely/azonosítótábla” nevek feloldásának kérése | Kötelező |
| Raktárkezelés | Minőség-ellenőrzés | Kötelező |
| Raktárkezelés | Felhasználói beállítások, ikonok és lépéscímek az új raktárkezelési alkalmazáshoz | Kötelező |
| Raktárkezelés | További helyzóna | Alapértelmezés szerint be |
| Raktárkezelés | Átmozgatási rendelések létrehozása és feldolgozása a raktári alkalmazásból | Alapértelmezés szerint be |
| Raktárkezelés | Gyors ellenőrzés engedélyezése raktárkezelési mobileszközökhöz | Alapértelmezés szerint be |
| Raktárkezelés | Cikk-konszolidáció helyének kihasználtsága | Alapértelmezés szerint be |
| Raktárkezelés | A raktárkezelés készleten lévő tételek karbantartására vonatkozó feladatának maximális végrehajtási ideje | Alapértelmezés szerint be |
| Raktárkezelés | Kimenő munkaterhelések megjelenítése | Alapértelmezés szerint be |
| Raktárkezelés | Raktári alkalmazás eseményeinek feldolgozása | Alapértelmezés szerint be |
| Raktárkezelés | A rakománytervezési munkaterület mentett nézetei | Alapértelmezés szerint be |
| Raktárkezelés | A munka részleteit tartalmazó oldal mentett nézete | Alapértelmezés szerint be |
| Raktárkezelés | Hullámfeldolgozás mentett nézete | Alapértelmezés szerint be |
| Raktárkezelés | Rakományfeldolgozás mentett nézetei | Alapértelmezés szerint be |
| Raktárkezelés | Szállítmányfeldolgozás mentett nézetei | Alapértelmezés szerint be |
| Raktárkezelés | Hullámkötegelt feladat részletei | Alapértelmezés szerint be |
| Raktárkezelés | Hullámvégrehajtási értesítések | Alapértelmezés szerint be |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platformfrissítések a Finance and Operations alkalmazásokhoz

A Microsoft Dynamics 365 Supply Chain Management 10.0.25 platformfrissítéseket tartalmaz. További információért lásd [Platformfrissítések a Finance and Operations alkalmazások 10.0.25-ös verziójához (2022. április)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.25 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

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
