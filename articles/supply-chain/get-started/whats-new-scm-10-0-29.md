---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management szolgáltatásban – 10.0.29. (2022. október)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.29 verziójában új vagy módosult funkciókat ismerteti.
author: kamaybac
ms.date: 08/12/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d12932f35b3b451577d38948f60bc3a73c10e2a0
ms.sourcegitcommit: 86c0562ce1ecdf7937125c0f5a6771f178b459e7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714833"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10029-october-2022"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management szolgáltatásban – 10.0.29. (2022. október)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.29-es verziójában. Ennek a verziónak a buildszáma több 10.0.1326, és a következő ütemezésben érhető el:

- **Előzetes kiadás:** 2022. augusztus
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2022. szeptember
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. október

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: Előfordulhat, hogy a cikk frissítése a cikk eredeti közzététele után a buildhez hozzáadott funkciókat is tartalmazza.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Készlet és logisztika | [A WMS-cikkek felosztása és foglalása a készlet láthatósága érdekében](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/allocate-reserve-whs-items-inventory-visibility) | Hamarosan | Alapértelmezés szerint engedélyezve |
| Készlet és logisztika | [Előrehozott aktuális készletlisták](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/query-inventory-visibility-summary-entity) | [A Készletláthatóság alkalmazás használata](../inventory/inventory-visibility-power-platform.md) | Szolgáltatáskonfiguráció által engedélyezve |
| Készítés rendelésre ellátás automatizálása | [Készítés rendelésre ellátás automatizálása](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-to-order-supply-automation) | [Készítés rendelésre ellátás automatizálása](../master-planning/make-to-order-supply-automation.md) | Funkciókezelés:<br>*Készítés rendelésre ellátás automatizálása* |
| Tervezés | [DDMRP részletes információk megtekintése és alkalmazása](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/view-apply-detailed-insights-ddmrp) | [Igényvezérelt anyagigény-tervezés – áttekintés](../master-planning/planning-optimization/ddmrp-overview.md) | Funkciókezelés:<br>*(Előzetes verzió) DDMRP a Tervezési optimalizáláshoz* |
| Gyártásvezérlés | [Késztermékek ténylegesen elérhetővé tétele a naplókba való feladás előtt](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-finished-goods-physically-before-posting) | [Késztermékek ténylegesen elérhetővé tétele a naplókba való feladás előtt](../production-control/deferred-posting.md) | Funkciókezelés:<br>*(Előzetes verzió) Késztermékek ténylegesen elérhetővé tétele a naplókba való feladás előtt* |
| Raktárkezelés | [Vonatkozó adatok keresni a raktári mobilalkalmazáson belül](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/look-up-relevant-data-within-warehouse-mobile-app) | [Adatok lekérdezése a Warehouse Management mobilalkalmazás-kitérők segítségével](../warehousing/warehouse-app-data-inquiry.md) | Funkciókezelés:<br>*Warehouse Management alkalmazás adatkérési folyamata* |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be szeretné kapcsolni, akkor ezt a [funkciókezelésben kell megtenni.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Költségkezelés | Függőben lévő társtermék-árkalkuláció optimalizálása | Ez a funkció ütközést old meg, amely akkor fordulhat elő, ha a társtermék árát több szál alapján számítják ki. A rendszer így biztosan csak egyszer számítja ki a társtermék árát. A program ennek a számításnak az eredményét használja az összes többi számítás bemeneteként. Ha már létezik függő ár, a használt ár lesz az. |
| Alaptervezés | Tranzakciók csoportosítása a Tervezés optimalizálása keretében | Ez a funkció csökkentheti azon tervezett rendelések számát, amelyek egyetlen értékesítésirendelés-sor ellátásához jönnek létre a tervezési optimalizálás használata esetén. Ha ez a funkció be van kapcsolva, a tervezési optimalizálás egyetlen szükségletbe csoportosítja egy rendelési sor minden készlettranzakcióját a teljes mennyiségre. (Ez a viselkedés megfelel a beépített tervezőmotor viselkedésének.) A készlet és az igények külön vannak csoportosítva. Ennek megfelelően a funkció segítséget nyújt a tranzakció volumenének csökkentéséhez a tranzakciók felosztása és az olyan dimenziók (például kötegszámok vagy sorozatszámok) használata esetén, amelyek nem fedezeti dimenziók. |
| Beszerzés és forrás | Szállító várakoztatott állapotba helyezése a beszerzési rendelésekhez | Ezzel a funkcióval a szállítót fel lehet függesni a beszerzési rendelésekért. Hozzáad egy új beszerzésirendelés-típust *·*, amely a szállítót a beszerzési rendelések számára visszatartottként jelöli meg. Nem hozhat létre új beszerzési rendeléseket olyan szállítók számára, amelyek beszerzési rendelésekhez vannak függve, de folytathatja a nyitott számlákat és kifizetéseket ezeknél a szállítóknál. |
| Értékesítés és marketing | Sor nettó összegének kiszámítása importra | Ezzel a *funkcióval* szabályozható, hogy a rendszer újraszámírja-e a sorösszegeket, amikor OData vagy kettős írású adatok használatával importálja az adatokat az értékesítési rendelés soraiból, *·* *az* értékesítésiajánlat-sorokból vagy a visszárurendelés-sorokból. Csak akkor van **hatása**, ha a kereskedelmi megállapodások értékelési irányelvei is érvényben vannak, amelyek korlátozzák az értékesítésirendelés-sorok, értékesítésiajánlat-sorok és/vagy visszárurendelés-sorok Nettó összeg mezőjének módosításait. Hozzáad egy "Sor nettó **összegének** **számítása" nevű beállítást a Kinnlevőségek > Beállítás > Kinnlevőségek paraméterei lapon**. Ha ez a beállítás *Igen*, a rendszer szükség esetén mindig újraszámja a sorösszegeket (ezáltal figyelmen kívül hagyja a sor nettó összegére vonatkozó kereskedelmi megállapodás értékelési irányelveit). *Ha* a beállítás Nem, a rendszer soha nem számítja ki automatikusan a sor nettó összegét, még akkor sem, ha a sor árának, mennyiségének és/vagy engedményének bejövő változtatása azt feltételezi, hogy a sor nettó összegét újra kell számítani. Ez a funkció alapértelmezés szerint engedélyezve van, és kezdetben **a Sor nettó összegének számítása értéket Igen beállításra állítja** *.* A *"Nincs* " beállítás megegyezik a rendszer viselkedésével a 10.0.23-as verzió előtt, és a rendszer főként az örökölt integrációs helyzetek támogatásához biztosítja.<br><br>A további tudnivalókat [lásd a sorok nettó összegének újraszámítása értékesítési rendelések, ajánlatok és visszaküldések importálása esetén](../sales-marketing/calc-line-net-amounts-import.md). |
| Értékesítés és marketing | Értékesítési összegek kiszámítása több szál segítségével | Ez a funkció a párhuzamos feldolgozás engedélyezésével javíthatja a teljesítményt, amikor kiszámítja egy köteg értékesítési összegeit. A funkció új szálszám **mezőt** ad hozzá az **Értékesítési összegek számítása párbeszédpanelhez**. Ha a számítás kötegben való futtatását választja, akkor ebben a mezőben beállíthatja a szálak maximális számát. *Ha 0 (nulla*) *vagy 1* értékre állítja az értéket, egyetlen szálat használ a rendszer. Az 1 feletti értékek többszálasozást engedélyeznek. |
| Értékesítés és marketing | Manuálisan bevitt vállalatközi árak és engedmények frissítése | Ez a funkció támogatja a vállalatközi rendelések manuális módosítási irányelveit. Magában foglalja a manuális módosítási irányelvek átvitelét a vállalatközi értékesítési és beszerzési rendelések között. Korábban a manuális módosítási irányelvek csak a nem vállalatközi rendeléseknél voltak támogatottak. Ha ez a funkció engedélyezve van, akkor a rendszer lehetőséget biztosít az árak és engedmények frissítésére, miután vállalatközi rendelés módosításait mentheti. Ezzel a beállítással eldöntheti, hogy az új ár- és engedményadatokat alkalmazza-e a vállalatközi rendelésre, vagy változatlanul hagyja a rendelést. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

Nemrégiben hozzáadta vagy jelentősen frissítettük a következő súgócikkeket. Ezek a cikkek nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszok felsorolják. Ugyanakkor előfordulhat, hogy a meglévő szolgáltatásokból többet lehet kihozni.

| Szolgáltatásterület | Új vagy frissített cikkek |
|---|---|
| Alaptervezés, CTP | [Értékesítési rendelés szállítási dátumának számítása az ígérhető használatával](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md) |
| Alaptervezés, DDMRP | [Igényvezérelt anyagigény-tervezés – áttekintés](../master-planning/planning-optimization/ddmrp-overview.md)<br>[A DDMRP szolgáltatás bekapcsolása a rendszerhez](../master-planning/planning-optimization/ddmrp-enable.md)<br>[Készletpozicionálás](../master-planning/planning-optimization/ddmrp-inventory-positioning.md)<br>[Bufferprofil és -szintek](../master-planning/planning-optimization/ddmrp-buffer-profile-and-levels.md)<br>[Igényvezérelt tervezés](../master-planning/planning-optimization/ddmrp-planning.md)<br>[Vizuális és együttműködési végrehajtása](../master-planning/planning-optimization/ddmrp-visual-and-collaborative-execution.md) |
| Raktárkezelés | [Tárolók csomagolása szállításhoz](../warehousing/packing-containers.md)<br>[Csomagolási munka kimenő tárolók csomagolásához és szállítmányok feldolgozásához](../warehousing/packing-work.md) |

## <a name="feature-state-changes-in-this-release"></a>Funkcióállapot-változások ebben a verzióban

Az alábbi táblázat felsorolja azokat a funkciókat, amelyek kötelezővé vagy alapértelmezés szerint a 10.0.29-es verzióba lettek beállítva. Ezeket a funkciókat automatikusan bekapcsolja a rendszer, amint a 10.0.29-es verzióra frissít. A kötelező szolgáltatások nem kikapcsolhatók, [de az alapértelmezés szerint bekapcsolt funkciók a Funkciókezelés segítségével továbbra is kikapcsolhatóak](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A táblázat felsorolja azokat a funkciókat is, amelyek korábban nyilvános előnézetben voltak, de a 10.0.29-es verzióban általánosan elérhetővé váltak. Ez a módosítás arra utal, hogy a funkciók használata éles környezetben már ajánlott. Ezek a funkciók alapértelmezés szerint ki vannak kapcsolva, hacsak nincs jelezve más. Ezért használatukhoz a [Funkciókezelést](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) kell használnia ahhoz, hogy engedélyezze azokat.

| Modul | Funkció neve | Új funkcióállapot |
| --- | --- | --- |
| Eszközkezelés | [A termelési üzem végrehajtási felületére vonatkozó eszközkezelési funkció](../production-control/production-floor-execution-configure.md) | Kötelező |
| Költségkezelés | [Az érvénytelenítés címkéjének módosítása a Zárás állapotban, és helyesbítése Sztornírozás értékre](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/change-terminology-inventory-closing-cancellation-inventory-closing-reverse) | Kötelező |
| Költségkezelés | Anyagjegyzék-számítási részletek tisztítása költségszámítási verziókban | Kötelező |
| Költségkezelés | [Cikkár-összehasonlítás tárolása](../cost-management/compare-item-price.md) | Kötelező |
| Költségkezelés | [Költségszámítási szint](../cost-management/cost-calculation-level.md) | Alapértelmezés szerint be |
| Költségkezelés | Felhasználó által definiált kötegszám beállításának engedélyezése a készletzárás sztornírozásához | Alapértelmezés szerint be |
| Költségkezelés | [Készletzárás folyamatának részletei](whats-new-scm-10-0-21.md) | Alapértelmezés szerint be |
| Költségkezelés | [Készletérték-jelentés tárolója](../cost-management/inventory-value-report-storage.md) | Kötelező |
| Költségkezelés | Készletérték-jelentés adatainak tisztítása | Kötelező |
| Költségkezelés | Mozgóátlag, tartalék költségsorrend | Kötelező |
| Költségkezelés | Készletzárási napló megjelenítése rácsban | Kötelező |
| Költségkezelés | Nem teljesen kiegyenlített tranzakciókkal rendelkező cikkek megjelenítése összesítő formátumban | Kötelező |
| Készlet- és raktárkezelés | Kötegattribútumok üres értékeinek engedélyezése | Kötelező |
| Készlet- és raktárkezelés | Készletátviteli rendelési sorok sorszámának automatikus növekménye | Kötelező |
| Készlet- és raktárkezelés | Átmozgatási rendelés létrehozása az értékesítési sorból | Kötelező |
| Készlet- és raktárkezelés | Készletnaplósor mezőjének letiltása a munkafolyamatban | Kötelező |
| Készlet- és raktárkezelés | Készletminőség-kezelési paraméterek figyelmeztetési funkciójának engedélyezése | Kötelező |
| Készlet- és raktárkezelés | (Kína) Fizikai bevételezési és kibocsátási költségek kizárása a havi átlagköltségből | Alapértelmezés szerint be |
| Készlet- és raktárkezelés | [Készletnapló jóváhagyási munkafolyamata](../inventory/inventory-journal-workflow.md) | Kötelező |
| Készlet- és raktárkezelés | [Aktuális készlet jelentésének tárolása](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/inventory-on-hand-report-storage) | Kötelező |
| Készlet- és raktárkezelés | [Készletkezelésre mentett nézetek](saved-views-scm.md) | Kötelező |
| Készlet- és raktárkezelés | Átátviteli rendelés érvénytelenítése | Kötelező |
| Készlet- és raktárkezelés | Mértékegység és egységmennyiség használata a készletnaplókban | Kötelező |
| Készlet- és raktárkezelés | Készletnapló zárolásának feloldása | Kötelező |
| Gyártás | [Automatikusan feladott kitárolási listákhoz engedélyezett raktári anyagok automatikus kitárolása](whats-new-scm-10-0-23.md) | Általánosan elérhető |
| Gyártás | Készletdimenziók megjelenítésének engedélyezése az anyaglistában a termelési útvonal műveleteihez | Kötelező |
| Gyártás | [Engedélyezze, hogy a köteg-és sorozatszámokat megadhassa befejezettként a Feladatkártya eszközéből](../production-control/report-finished-job-device.md) | Alapértelmezés szerint be |
| Gyártás | Továbbfejlesztett termelési tényleges súly szerinti mennyiséggel való kitárolás | Alapértelmezés szerint be |
| Gyártás | [Feladatkeresés a gyártóüzem végrehajtási interfészén](../production-control/production-floor-execution-configure.md) | Kötelező |
| Gyártás | [Gyártás-végrehajtási rendszer integrációja](../production-control/mes-integration.md) | Alapértelmezés szerint be |
| Gyártás | [Saját nap nézet a termelési üzem végrehajtási felületéhez](../production-control/production-floor-execution-configure.md) | Alapértelmezés szerint be |
| Gyártás | [Igény szerinti anyagelérhetőségi ellenőrzés a termelési rendelésekre vonatkozóan](whats-new-scm-10-0-24.md) | Alapértelmezés szerint be |
| Gyártás | [Alapértelmezett termelési foglalás felülbírálása](../production-control/override-default-reservation-principle.md) | Kötelező |
| Gyártás | [Anyagfelhasználás regisztrálása a termelési üzem végrehajtási felületén (nem WMS)](../production-control/production-floor-execution-configure.md) | Általánosan elérhető |
| Gyártás | [Jelentés a termelési üzem végrehajtási felületéről származó tényleges súly szerinti cikkekről](../production-control/production-floor-execution-configure.md) | Általánosan elérhető |
| Gyártás | [Jelentés a termelési üzem végrehajtási felületéről származó társ- és melléktermékekről](../production-control/production-floor-execution-configure.md) | Alapértelmezés szerint be |
| Gyártás | [Jelentés a tervezési cikkekről a termelési üzem végrehajtási felületében](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | Alapértelmezés szerint be |
| Gyártás | [A gyártásvezérlés mentett nézetei](saved-views-scm.md) | Kötelező |
| Gyártás | [Teljes sorozatszám, köteg- és azonosítótáblaszám megjelenítése a termelési üzem végrehajtási felületén](../production-control/production-floor-execution-configure.md) | Kötelező |
| Gyártás | [Nyersanyagok lejáratának ellenőrzése a tervezett felhasználási dátumhoz képest](whats-new-scm-10-0-23.md) | Alapértelmezés szerint be |
| Alaptervezés | [Tervezésoptimalizálás automatikus megerősítése](../master-planning/planning-optimization/planned-order-firming.md) | Kötelező |
| Alaptervezés | [Kötegelhető megerősítés és konszolidáció a tervezett tömeges és csomagolt kötegelt rendelésekhez](whats-new-scm-10-0-20.md) | Alapértelmezés szerint be |
| Alaptervezés | [Az aktuális készlettel rendelkező cikkek felvétele az előzetes feldolgozási szűrők engedélyezése esetén](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled) | Alapértelmezés szerint be |
| Alaptervezés | [Végtelen kapacitás ütemezése a tervezési optimalizáláshoz](../master-planning/planning-optimization/infinite-capacity-planning.md) | Alapértelmezés szerint be |
| Alaptervezés | [Tervezésoptimalizálási árrések](../master-planning/planning-optimization/safety-margins.md) | Kötelező |
| Alaptervezés | [Negatív napok a tervezési optimalizáláshoz](../master-planning/planning-optimization/delay-tolerance.md) | Kötelező |
| Alaptervezés | [A helyesbített igény-előrejelzés párhuzamos engedélyezése](whats-new-scm-10-0-20.md) | Kötelező |
| Alaptervezés | [Tervezett rendelés megerősítése szűréssel](../master-planning/planning-optimization/planned-order-firming.md) | Kötelező |
| Alaptervezés | [Tervezett termelési rendelések a Tervezési optimalizáláshoz](../master-planning/planning-optimization/production-planning.md) | Kötelező |
| Alaptervezés | [Beszerzésre vonatkozó kereskedelmi megállapodások a tervezési optimalizáláshoz](../master-planning/planning-optimization/purchase-trade-agreement.md) | Kötelező |
| Alaptervezés | [Mentett nézetek tervezett rendelésekhez](saved-views-scm.md) | Kötelező |
| Beszerzés és forrás | Költségek beszerzési rendelésekből és összegekbe | Kötelező |
| Beszerzés és forrás | Beszerzési igénylés elosztási alaphelyzetbe állítása gomb letiltása | Alapértelmezés szerint be |
| Beszerzés és forrás | [Beszerzéssel kapcsolatos munkafolyamatok visszaállításának engedélyezése](whats-new-scm-10-0-20.md) | Alapértelmezés szerint be |
| Beszerzés és forrás | [A beszerzésirendelési-sorok számának korlátozása kötegelt feladatonként](whats-new-scm-10-0-27.md) | Alapértelmezés szerint be |
| Beszerzés és forrás | [A szállító pénzügyi dimenzióinak egyesítése aktív dimenziókapcsolatú pénzügyi dimenzióval a beszerzési rendelésen](whats-new-scm-10-0-25.md) | Kötelező |
| Beszerzés és forrás | [A raktári termékek regisztrált mennyiségének és a nem raktározott termékek maradékénak feladása a nyugtákhoz és a szállítói számlákhoz](whats-new-scm-10-0-26.md) | Általánosan elérhető |
| Beszerzés és forrás | [Az általános költségvetési foglalások túlfoglalásának megakadályozása, ha több beszerzési igénylés van a munkafolyamatban](whats-new-scm-10-0-21.md) | Alapértelmezés szerint be |
| Beszerzés és forrás | [Beszerzési szerződésért felelős fél](../procurement/purchase-agreements.md) | Kötelező |
| Beszerzés és forrás | [Mentett nézetek beszerzési rendelésekhez](saved-views-scm.md) | Kötelező |
| Termékinformációk kezelése | Darabjegyzék-jelentés előzetes feldolgozása az időtúllépés elkerülése érdekében | Kötelező |
| Termékinformációk kezelése | Alapértelmezett pénzügyi dimenziók külön cikksablonok használata esetén | Kötelező |
| Termékinformációk kezelése | Termékdimenzió-csoportok engedélyezése az elemsablonokban | Kötelező |
| Termékinformációk kezelése | Cikk–vonalkód entitás fejlesztései | Kötelező |
| Termékinformációk kezelése | Termékváltozatok neveinek újragenerálása az elnevezési rendszer alapján | Kötelező |
| Termékinformációk kezelése | [Kiadott termékekhez tartozó mentett nézet](saved-views-scm.md) | Kötelező |
| Termékinformációk kezelése | [Változatjavaslatok oldalának fejlesztései](../pim/tasks/create-predefined-product-variants.md) | Kötelező |
| Értékesítés és marketing | [Értékesítési rendelés költségeinek felosztása](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/miscellaneous-charges-enhancements) | Kötelező |
| Értékesítés és marketing | Értékesítésfrissítési rendelés előzményeinek tisztítása | Kötelező |
| Értékesítés és marketing | [Értékesítésfrissítési előzmények tisztítása kor alapján](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) | Kötelező |
| Értékesítés és marketing | [Kapcsolattartó személy adatentitás-exportálásának optimalizálása](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Kötelező |
| Értékesítés és marketing | Összengedménycsoport másolása értékesítési jóváíráshoz | Kötelező |
| Értékesítés és marketing | [Keresés engedélyezése az értékesítési árajánlat dokumentumbevezető és dokumentum-összefoglaló mezőinél](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Kötelező |
| Értékesítés és marketing | [A 100 legjelentősebb vevő jelentés teljesítményének javítása](whats-new-scm-10-0-23.md) | Kötelező |
| Értékesítés és marketing | Az előzmények adattisztítási feladatai tartalmazzák a várakozó rekordokat is | Kötelező |
| Értékesítés és marketing | Az értékesítésirendelési-sorok számának korlátozása kötegelt feladatonként | Alapértelmezés szerint be |
| Értékesítés és marketing | [A feladásra kiválasztható értékesítési rendelések számának korlátozása](whats-new-scm-10-0-21.md) | Kötelező |
| Értékesítés és marketing | Becsült vevői egyenleg újraszámítása | Kötelező |
| Értékesítés és marketing | [Értékesítési visszárurendelés-sor regisztrálása decimális pontossággal, tényleges súllyal vagy anélkül](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Kötelező |
| Értékesítés és marketing | [Az értékesítés és marketing modul mentett nézetei](saved-views-scm.md) | Kötelező |
| Értékesítés és marketing | [Egykattintásos értékesítésirendelés-megerősítés](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation) | Kötelező |
| Szállításkezelés | Fuvarlevelek fuvarszámlasorokkal történő megfeleltetésének engedélyezése a feladott szállítóiszámla-napló visszavonása nélkül | Alapértelmezés szerint be |
| Szállításkezelés | [Szállítóiszámla-napló létrehozásának engedélyezése fuvarszámla elvetése esetén](whats-new-scm-10-0-20.md) | Alapértelmezés szerint be |
| Szállításkezelés | [Kis csomagok szállítása](../warehousing/small-parcel-shipping.md) | Kötelező |
| Szállításkezelés | [USMCA-eredettanúsítvány dokumentuma](../transportation/usmca-certification-of-origin.md) | Alapértelmezés szerint be |
| Raktárkezelés | [További helyzóna](../warehousing/additional-location-zones.md) | Kötelező |
| Raktárkezelés | [Munka érvénytelenítése](../warehousing/cancel-warehouse-work.md) | Kötelező |
| Raktárkezelés | [Szállítmány konszolidálása](../warehousing/configure-shipment-consolidation-policies.md) | Kötelező |
| Raktárkezelés | [Átmozgatási rendelések létrehozása és feldolgozása a raktári alkalmazásból](../warehousing/create-transfer-order-from-warehouse-app.md) | Kötelező |
| Raktárkezelés | Áttárolási sablonok helyutasításokkal | Alapértelmezés szerint be |
| Raktárkezelés | [Betárolási munka elválasztása ASN-ekből](whats-new-scm-10-0-21.md) | Kötelező |
| Raktárkezelés | [Halasztott Put műveletek](../warehousing/deferred-processing-manual-inventory-movement.md) | Kötelező |
| Raktárkezelés | Halasztott betárolás – tároló | Alapértelmezés szerint be |
| Raktárkezelés | Elhalasztott behatárolás feldolgozása – engedélyezés az auditnapló-sablon funkcióhoz, ahol az indítóesemény beállítása Korábbi | Kötelező |
| Raktárkezelés | [Zárolt készletet mintaként tartalmazó minőségi rendelésekből várt bevételezések letiltása](../inventory/inventory-blocking.md) | Alapértelmezés szerint be |
| Raktárkezelés | Gyors ellenőrzés engedélyezése raktárkezelési mobileszközökhöz | Kötelező |
| Raktárkezelés | [GS1 vonalkódok továbbfejlesztett elemzője](../warehousing/gs1-barcodes.md) | Általánosan elérhető |
| Raktárkezelés | [Rugalmas, rendelésben vállalt azonosítótábla-foglalás](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Kötelező |
| Raktárkezelés | [Rugalmas raktárszintű dimenziófoglalás](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Kötelező |
| Raktárkezelés | [Cikk-konszolidáció helyének kihasználtsága](../warehousing/item-consolidation-location-utilization.md) | Alapértelmezés szerint be |
| Raktárkezelés | Azonosítótábla bevételezési előzményei | Alapértelmezés szerint be |
| Raktárkezelés | [Manuális szállítmánykonszolidáció](../warehousing/consolidate-shipments-manual-workbench.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Manuális transzfersor kitárolási szolgáltatása felügyeleti vagy hasonló megbízható felhasználók számára](whats-new-scm-10-0-28.md) | Általánosan elérhető |
| Raktárkezelés | [Anyagkezelési berendezések kezelői felülete](../warehousing/mhax.md) | Kötelező |
| Raktárkezelés | [Új rakománytervezési munkaterületlapok](whats-new-scm-10-0-24.md) | Általánosan elérhető |
| Raktárkezelés | [Kimenő munkaterhelések megjelenítése](../warehousing/outbound-workload-visualization.md) | Kötelező |
| Raktárkezelés | [Tervezett áttárolás](../warehousing/planned-cross-docking.md) | Kötelező |
| Raktárkezelés | [Raktári alkalmazás eseményeinek feldolgozása](../warehousing/warehouse-app-events.md) | Kötelező |
| Raktárkezelés | A társtermék és a melléktermék betárolási munkasablonjára vonatkozó lekérdezés fejlesztése | Kötelező |
| Raktárkezelés | [Mennyiségek lekerekítése a legközelebbi értékesítési egységre a raktárba való kiadáskor](whats-new-scm-10-0-19.md) | Kötelező |
| Raktárkezelés | [A rakománytervezési munkaterület mentett nézetei](saved-views-scm.md) | Kötelező |
| Raktárkezelés | [A munka részleteit tartalmazó oldal mentett nézete](saved-views-scm.md) | Kötelező |
| Raktárkezelés | [Hullámfeldolgozás mentett nézete](saved-views-scm.md) | Kötelező |
| Raktárkezelés | [Rakományfeldolgozás mentett nézetei](saved-views-scm.md) | Kötelező |
| Raktárkezelés | [Szállítmányfeldolgozás mentett nézetei](saved-views-scm.md) | Kötelező |
| Raktárkezelés | [GS1-vonalkódok beolvasása](../warehousing/gs1-barcodes.md) | Általánosan elérhető |
| Raktárkezelés | Szállítmányhullám-címke részletei | Kötelező |
| Raktárkezelés | [Vegyes egységek a helyen](whats-new-scm-10-0-21.md) | Kötelező |
| Raktárkezelés | [Gyorsabb API használata a csomagolási állomáson lévő zárási/újranyitási tárolókhoz](whats-new-scm-10-0-21.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Feltöltési feladatokhoz kiválasztott sablonok ellenőrzése](whats-new-scm-10-0-20.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Raktári alkalmazásban előléptetett mezők](../warehousing/warehouse-app-promoted-fields.md) | Kötelező |
| Raktárkezelés | [A raktári alkalmazás lépéseinek útmutatója](../warehousing/mobile-app-titles-instructions.md) | Kötelező |
| Raktárkezelés | [Raktári hely állapota](../warehousing/warehouse-location-status.md) | Kötelező |
| Raktárkezelés | [A Warehouse Management alkalmazás kerülőútjai](../warehousing/warehouse-app-detours.md) | Alapértelmezés szerint be |
| Raktárkezelés | [Hullámkötegelt feladat részletei](../warehousing/wave-processing.md) | Kötelező |
| Raktárkezelés | [Hullámvégrehajtási értesítések](../warehousing/wave-execution-notifications.md) | Kötelező |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.29 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügyi és műveletalkalmazások platformfrissítései a 10.0.29-es verzióhoz (2022. október)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md).

### <a name="bug-fixes"></a>Hibajavítások

A 10.0.29-es verzióba bekerülő frissítések hibajavításával kapcsolatos információk megtekintéséhez jelentkezzen be a Lifecycle Services (LCS) [alkalmazásba, és tekintse meg a tudásbáziscikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

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
