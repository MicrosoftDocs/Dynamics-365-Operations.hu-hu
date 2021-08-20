---
title: A Dynamics 365 Supply Chain Management 10.0.21 előzetes verziója (2021. október)
description: Ez a témakör a Dynamics 365 Supply Chain Management 10.0.21 új vagy módosított szolgáltatásait írja le.
author: kamaybac
ms.date: 08/02/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 517411512760374f1d1fd3b8ea3615563c47202c2e847569d00cb17a94657630
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012037"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10021-october-2021"></a>A Dynamics 365 Supply Chain Management 10.0.21 előzetes verziója (2021. október)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.21 előzetes kiadásának új vagy módosított szolgáltatásait írja le. Ennek a verziónak 10.0.960 a buildszáma, és a következő módon érhető el:

- **Előzetes kiadás:** 2021. augusztus
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2021. szeptember
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2021. október

## <a name="known-deployment-issue"></a>Ismert telepítési probléma
Az IaaS 10.0.21-es kiadásának telepítésekor a következő telepítési figyelmeztetés jelenik meg:

**Figyelmeztetés kódja:** 95017

**Figyelmeztető üzenet:** A [SetupDiagnostics] parancsfájl végrehajtása sikertelen volt az VM-mel szemben

A telepítés a figyelmeztetés ellenére is működni fog, azonban a Lifecycle Services (LCS) következő ismert problémái fordulhatnak elő:

-   A **Környezet figyelése** lapon nem jelenik meg a **Részletes verzióinformációk megtekintése** hivatkozás, így nem fogja látni a környezetben telepített modulok adott verzióit. Az adatok nélkül a további gyorsjavítások sikertelenek lehetnek, mert a gyorsjavításokat alkalmazó folyamat ezeket az adatokat használja annak ellenőrzésére, hogy teljesülnek-e a modulverzió előfeltételei. Mivel a PEAP/Preview build nem használható termelésben, és nem alkalmazható gyorsjavítások, ennek a hatásnak minimálisnak kell lennie.
-   Az SQL Insights alatti **Környezetfigyelés** lap **Teljesítménymetrikák** és **Indexelemzés** lapjai nem jelenítnek meg adatokat. A **Környezetfigyelés** minden egyéb szolgáltatása a várakozásoknak megfelelően működik.
-   A **Teljes rendszerdiagnosztika** oldal nem lesz elérhető. Az éjszakai gyűjtőfutások állapotára és a szabályai által észlelhető problémákra vonatkozó társított adatok szintén nem fognak megjelenni.

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: A *Funkció* oszlop a [kiadási tervre](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features) mutató hivatkozásokat tartalmaz, amelyeken látható az egyes funkciók hivatalos kiadási dátuma. A *További tudnivalók* oszlopban további részletek és/vagy a kapcsolódó dokumentációra mutató hivatkozások találhatóak.

Ezen szolgáltatások többségét a használat előtt engedélyezni kell a [Funkciók kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) alatt. A felsorolt szolgáltatások egy része továbbra is előnézeti módban van, mások azonban már általánosan elérhetők.

| Szolgáltatásterület | Funkció | További információ |
|---|---|---|
| Készlet&nbsp;és&nbsp;logisztika | [A Global Inventory Accounting bővítmény a Dynamics 365 Supply Chain Management alkalmazáshoz](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Globális készletkönyvelési kezdőlapja](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Készlet&nbsp;és&nbsp;logisztika | [Az ellenszámlákhoz kapcsolódó kódok használatával törtöné készlethelyesbítések feladása](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Készletleltár okkódjai](../warehousing/reason-codes-for-counting-journals.md) |
| Készlet&nbsp;és&nbsp;logisztika | [Értékesítési ajánlat hivatkozott adatexportálási irányelve](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Válassza ki, hogy az ajánlatok által hivatkozott adatok változásai miatt a ezek ajánlatok (vagy sorok) be legyenek-e foglalva a következő növekményes exportálásba. A növekményes exportálások gyorsabban futnak, ha úgy dönt, hogy nem foglal bele ilyen árajánlatokat vagy sorokat.<br><br>Ez a funkció a **Kinnlevőségek paraméterei** oldalon hozzáadja az **Értékesítési ajánlatok hivatkozott adatainak kihagyása a változáskövetés során** nevű beállítást. |
| Készlet&nbsp;és&nbsp;logisztika | [Vonalkódok beolvasása a raktárban a GS1 formátumszabványok alapján](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | *Hamarosan*<!-- KFM: Add doc link when ready. --> |
| Készlet&nbsp;és&nbsp;logisztika | Lezárt pályázat <!-- KFM: Add RP link when available --> | *Hamarosan*<!-- KFM: Add doc link when ready. --> |
| Készlet&nbsp;és&nbsp;logisztika | [Levonásokkal és a tényleges súllyal kapcsolatos továbbfejlesztések a Visszatérítések kezeléséhez](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [A levonások kezelése a levonás munkaterületről](../rebate-management/deduction-workbench.md )<br><br>[Visszatérítések feldolgozása, felülvizsgálata és feladása](../rebate-management/process-review-post.md)<br><br>[Visszatérítés-kezelési ajánlatok](../rebate-management/rebate-management-deals.md) |
| Készlet&nbsp;és&nbsp;logisztika | [A raktári alkalmazás lépéseinek útmutatója](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | *Hamarosan*<!-- KFM: Add doc link when ready --> |
| Készlet&nbsp;és&nbsp;logisztika | [Partraszállási költség munkaszünetei és nyomon követési frissítései](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Betárolás frissítéskövetése](../landed-cost/update-tracking-putaway.md )<br><br>[Úton lévő áruk feldolgozása](../landed-cost/in-transit-processing.md) |
| Alaptervezés | [Negatív napok a tervezési optimalizáláshoz](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Késés tűréshatára (negatív napok)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal. Ha e funkciók bármelyikét használni szeretné, kifejezetten engedélyeznie kell a [Funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Szolgáltatásterület | Funkció&nbsp;neve&nbsp;a Funkció-&nbsp;kezelésben | További információ |
|---|---|---|
| Költségkezelés | Készletzárás folyamatának részletei | Ez az előzetes verziójú funkció lehetővé teszi a készletzárás előrehaladásának részletes megtekintését. |
| Alaptervezés | (Előzetes verzió) Prioritásvezérelt MRP-támogatás Tervezési optimalizáláshoz | Ez a Tervezési optimalizálási előnézeti funkció lehetővé teszi, hogy az alaptervezést az újrarendelési ponttal vezérelt tervezési prioritással vezérelje. A kiemelt változások közé tartoznak a következők: **Tervezési prioritás** mező az értékesítésirendelés-sorokban, a beszerzésirendelés-sorokban, az igény-előrejelzésben és a tervezett rendelésekben; egy új fedezetkód-beállítás; **Cikkfedezet mező** az újrarendelési ponthoz; Az alaptervezés beállítási képernyői a tervezési prioritás beállításának szabályozásához; A tervezési optimalizálási és a tervezési optimalizálási számítás logikája a tervezési prioritás beállítását figyelembe veszi. |
| Beszerzés és forrás | Az általános költségvetési foglalások túlfoglalásának megakadályozása, ha több beszerzési igénylés van a munkafolyamatban | Ez az előnézeti funkció javítja a hibaellenőrzést, ha a felhasználók olyan beszerzési igényléseket küldnek és hagynak jóvá, amelyek túllépik egy általános költségvetési foglalási sor fennmaradó egyenlegét. Így megelőzhető az általános költségvetési foglalások túlfoglalása, amikor több beszerzési igénylés van a munkafolyamatban. |
| Gyártásvezérlés | Teljes sorozatszám, köteg- és azonosítótáblaszám megjelenítése a termelési üzem végrehajtási felületén | Ez a funkció jobb felületet biztosít a termelési üzem végrehajtási felületén a sorozatszám-, köteg- és azonosítótáblák listáinak megtekintéséhez. A megjelenítés a korlátozott karakterszámú kártyanézetről egy olyan listanézetre változik, amely elegendő helyet biztosít a teljes értékek megjelenítéséhez. A lista adott számok keresésére is lehetőséget biztosít. |
| Raktárkezelés | Betárolási munka elválasztása ASN-ekből | Ez a funkció akkor szükséges, ha előzetes kiszállítási értesítéseket (ASN-eket) küld és fogad, amikor egy skálázási egységre (elosztott topológia részeként) Warehouse Management terhelést futtat. Új adatbázistáblát ad hozzá a betárolási munkához szükséges információk tárolására. Ezt az információt korábban az ASN-ként is használt táblák tárolták. |
| Raktárkezelés | Vegyes egységek a helyen | Lehetővé teszi a rendszer számára, hogy többféle egysége tartalmazó elemeket (például dobozokat és eseteket) helyezzen el különböző helyekre. Ez a funkció minden egyes elhelyezést sablonsornál lehetővé teszi annak eldöntését, hogy a sor cikkeit vegyes egységű vagy egy egységgel rendelkező helyekre kell eltárolni. |
| Raktárkezelés | Gyorsabb API használata a csomagolási állomáson lévő zárási/újranyitási tárolókhoz | Ha ez az előzetes funkció engedélyezve van, akkor a tárolókhoz kapcsolódó készlettranzakciók egy új, kis terhelésű folyamattal jönnek létre, amely javítja a tárolók lezárásának és ismételt megnyitásának teljesítményét a manuális csomagolóállomás-feldolgozás során. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

A következő súgótémakörök a közelmúltban lettek hozzáadva vagy jelentősen frissítve. A program nem feltétlenül kapcsolódik ehhez a kiadáshoz hozzáadott új funkcióhoz, amint az az előző részben szerepel, de segítséget jelenthet a meglévő szolgáltatások kiválasztásában.

| Szolgáltatásterület | Új vagy frissített témakörök |
|---|---|
| Alaptervezés | [Készlet-előrejelzések](../master-planning/inventory-forecast.md) |
| Alaptervezés | [A Tervezési optimalizálás által nem használt paraméterek](../master-planning/planning-optimization/not-used-parameters.md) |
| Alaptervezés | [Feltöltési módok és mennyiség módosítása](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Alaptervezés | [Ütemezés végtelen kapacitással](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Alaptervezés | [Tervelőzmények és tervezési naplók megtekintése](../master-planning/planning-optimization/plan-history-logs.md) |
| Raktárkezelés | [Tároló csomagolási stratégiái](../warehousing/container-packing-strategy-overview.md) |
| Raktárkezelés | [Ciklikus leltározás – példa forgatókönyvek](../warehousing/cycle-counting-scenarios.md) |
| Raktárkezelés | [Bejövő ASN-ek importálása a V2 adatentitáson keresztül](../warehousing/import-asn-v2-data-entity.md) |
| Raktárkezelés | [Értékesítési és átmozgatási rendeléseknél az előírtnál nagyobb mennyiségek kitárolása](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Raktárkezelés | [Hullámcímke-nyomtatás ütemezése hullám közben](../warehousing/configure-task-based-wave-label-printing.md) |
| Raktárkezelés | [Újdonságok és változások a Warehouse Management mobilalkalmazásban](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Finance and Operations-alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.21 platformfrissítéseket tartalmaz. További tájékoztatás: [Platform-frissítések az Finance and Operations alkalmazások 10.0.21 verziójához (2021. október)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.21 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

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
