---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.19-es verziójában (2021. június)
description: Ez a témakör a Dynamics 365 Supply Chain Management 10.0.19 új vagy módosított szolgáltatásait írja le.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c1930a47bc133c411a0e6054aa766322a261064a06ac4cec8dcdd12c126dc7cd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773537"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.19-es verziójában (2021. június)

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.19 változatának új vagy módosított szolgáltatásait írja le. Ennek a verziónak 10.0.837 a buildszáma, és a következő módon érhető el:

- **Előzetes kiadás**: 2021. április
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2021. június
- **A kiadás nyilvános megjelenése (automatikus frissítés):** 2021. június

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: A *Funkció* oszlop a [kiadási tervre](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features) mutató hivatkozásokat tartalmaz, amelyeken látható az egyes funkciók hivatalos kiadási dátuma. A *További tudnivalók* oszlopban további részletek és/vagy a kapcsolódó dokumentációra mutató hivatkozások találhatóak.

Ezen szolgáltatások többségét a használat előtt engedélyezni kell a [Funkciók kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) alatt.

| Szolgáltatásterület | Funkció | További információ |
|---|---|---|
| Készlet&nbsp;és&nbsp;logisztika | [Szállító által elküldött banki adatok jóváhagyása és mentése](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/approve-save-vendor-submitted-bank-details) | [Szállító bankszámlaadatainak karbantartása](../../finance/accounts-payable/maintain-vendor-bank-info.md) |
| Készlet és logisztika | [Kapcsolattartó személy adatentitás-exportálásának optimalizálása](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | Ha ez a funkció engedélyezve van, a hivatkozott adatok módosításai nem okozzák a kapcsolódó kapcsolattartók következő növekményes exportálásba való befoglalását. Ha a funkció le van tiltva, a hivatkozott adatok módosításai a kapcsolódó kapcsolattartók következő növekményes exportálásba való befoglalásával járnak. |
| Készlet és logisztika | [A raktár-végrehajtási képességek növekményes fejlesztése mérlegegységekkel](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Üzenetfeldolgozó üzenetei](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Raktárkészlet helyesbítése](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Raktérkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Készlet és logisztika | [Keresési funkció az Értékesítési ajánlat lapon a Dokumentumbevezetés és Dokumentum-összefoglalás mezőkhöz](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | A funkció keresési szolgáltatást ad hozzá az **Értékesítési ajánlat** oldal **Dokumentumbevezetés** és **Dokumentum összefoglalása** mezőjéhez.<br><br>Alapértelmezetten ez a paraméter engedélyezett. |
| Készlet és logisztika | [Raktár végrehajtása az egyéni hardveren található peremhálózati skálaegységekkel](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Peremskálaegységek telepítése egyéni hardverre a LBD használatával](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Gyártás | [Gyártás végrehajtása az egyéni hardveren található peremhálózati skálaegységekkel](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Peremhálózati skálázási egységek telepítése egyedi hardverre LBD segítségével](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Tervezés | [Végtelen kapacitás ütemezése a tervezési optimalizáláshoz](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | Ez a funkció engedélyezi a korlátlan kapacitással történő kapacitásütemezést a tervezési optimalizáláshoz. E szolgáltatás nélkül a tervezett termelési rendelések az ütemezési időkorláttól függetlenül a kiadott termékek készletéből kapják meg az átfutási időt. |
| Tervezés | Lekérdezés alapú tervezett rendelésmegerősítés | [Biztosra tervezett rendelések](../master-planning/planning-optimization/planned-order-firming.md) |
| Termékinformációk kezelése | [Változatjavaslatok oldalának fejlesztései](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Az előre meghatározott termékváltozatok létrehozása](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt funkciófejlesztéseket tartalmazza: Ezek közül mindegyik egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal. Ha e funkciók bármelyikét használni szeretné, kifejezetten engedélyeznie kell a [Funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Szolgáltatásterület | Funkció&nbsp;neve&nbsp;a Funkció-&nbsp;kezelésben | További információ |
|---|---|---|
| Értékesítés és marketing | Értékesítési előzményadat-tisztítás teljesítményének javítása | Az értékesítési előzményadatok megtisztítása hosszú ideig tart, ha olyan környezetben fut, ahol nagy mennyiségű értékesítést kell frissíteni. Az időtartam csökkentése és a megbízhatóság javítása érdekében ez a funkció rövidebb ideig futó kötegekre osztja fel az adattisztítást. Ahol lehetséges, az adatbázissal kapcsolatos funkciókat a lehető legrövidebb ideig zárolja a rendszer, hogy a tisztítás során ne kelljen csatlakoztatni a tranzakciós táblákat. |
| Értékesítés és marketing | Kért átvételi dátum frissítése a visszaigazolt dátummal vállalatközi rendelések esetén | Ezzel a funkcióval szabályozható, hogy mi történjen az értékesítési és beszerzési dátum mező értékével a vállalatközi közvetlen kiszállítás során. Eldöntheti, hogy a rendszer frissítse-e a kért dátumokat, vagy hagyja ki a frissítést. Ha kihagyja a frissítést, a kért dátumok jelzik a vevő kérését. Ha engedélyezi a frissítést, a kért dátumok (a szállítási dátum ellenőrzése esetén) kezdetben csak a vevő kérését jelzik. A szállítási dátum ellenőrzése – ha nem a *Nincs* érték van megadva – felülbírálja az eredetileg kért értéket. Ezt a beállítást a vállalatközi szállítói vagy a vevői beállítások új **Kért átvételi dátum megerősített dátumkal való frissítése** beállításával lehet megadni.<br><br>Ha a funkció le van tiltva, a rendszer felülírja a szállítási dátum ellenőrzési szabályán alapuló eredeti értékesítési rendelésen lévő kért átvételi dátumot, de a kért szállítási dátum változatlan marad. |
| Raktárkezelés | Mennyiségek lekerekítése a legközelebbi értékesítési egységre a raktárba való kiadáskor | Ez a funkció egy olyan beállítást vesz fel, amely korlátozhatja a rendelési mennyiségeket a raktárba való kiadás esetén. Ha engedélyezve van, a rendszer a rendelési mennyiségeket a legközelebbi egész értékesítési egységre kerekíti, és elutasítja az olyan rendelések kiadását, amelyekben egy értékesítési egységnél kevesebb mennyiség szerepel. |
| Raktárkezelés | Szervezetszintű „Munkalétrehozás ütemezése” hullámmetódusa | A funkció engedélyezése esetén a *Munka létrehozásának ütemezése* hullámmódszer úgy lesz beállítva, hogy párhuzamosan fusson az összes jogi személynél. Mindez további beállításokat is érint. Az összes részlet: [Munka létrehozásának ütemezése hullám közben](../warehousing/configure-wave-schedule-work-creation.md). |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

A következő súgótémakörök a közelmúltban lettek hozzáadva vagy jelentősen frissítve. A program nem feltétlenül kapcsolódik ehhez a kiadáshoz hozzáadott új funkcióhoz, amint az az előző részben szerepel, de segítséget jelenthet a meglévő szolgáltatások kiválasztásában.

| Szolgáltatásterület | Új vagy frissített témakörök |
|---|---|
| Tervezési változáskezelés | [Tervezési változáskezelés GYIK](../engineering-change-management/change-management-faq.md) |
| Beszerzés és forrás | [Szállítók kategóriakérései](../procurement/category-requests-from-vendors.md) |
| Termékinformációk kezelése | [Mértékegység kezelése](../pim/tasks/manage-unit-measure.md)<br><br>[Termékkonfigurációs modell számításai](../pim/config-model-calculations.md) |
| Gyártásvezérlés | [Egyesített számsorozat a feladatazonosítók esetén](../production-control/unified-job-ids.md) |
| Szállításkezelés | [LTL osztályok](../transportation/ltl-class.md)<br><br>[NMFC-kódok](../transportation/nmfc-codes.md) |
| Raktárkezelés | [Raktári kötegelt és sorozatfoglalási hierarchiák hibaelhárítása](../warehousing/troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md) |
| Raktárkezelés, hullám létrehozása és feldolgozása | [Hullám létrehozása és feldolgozása](../warehousing/wave-processing.md)<br><br>[Raktári paraméterek hullámfeldolgozáshoz](../warehousing/wave-warehouse-parameters.md)<br><br>[Hullámsablonok](../warehousing/wave-templates.md)<br><br>[Hullámfelosztás](../warehousing/wave-allocation-method.md)<br><br>[Munka létrehozásának ütemezése a hullám során](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Tárolóra bontás](../warehousing/wave-containerization.md)<br><br>[Hullámvégrehajtási értesítések](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Finance and Operations-alkalmazások platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.19 platformfrissítéseket tartalmaz. További tájékoztatás: [Platformfrissítések a Finance and Operations alkalmazások 10.0.19-es verziójához (2021. június)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.19 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: 2021-es 1. hullám tervei

Kíváncsi a bármelyik üzleti alkalmazásával vagy platformjával kapcsolatos, közelgő és a közelmúltban bevezetett lehetőségekre?

Lásd: [Dynamics 365: 2021-as 1. frissítési hullám tervét](/dynamics365-release-plan/2021wave1/). A részleteket minden apró információmorzsáig bezárólag egyetlen dokumentumban rögzítettük, amelyet felhasználhat a tervezés során.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Eltávolított és elavult Supply Chain Management szolgáltatások

A [Dynamics 365 Supply Chain Management eltávolított vagy elavult szolgáltatásai](removed-deprecated-features-scm-updates.md) témakör azokat a funkciókat írja le, amelyek el lettek távolítva a Supply Chain Management szolgáltatásól vagy eltávolításuk ütemezve van.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Mielőtt a termékből eltávolítunk egy szolgáltatást, egy eltávolítással kapcsolatos értesítést teszünk közzé a [Dynamics 365 Supply Chain Management eltávolított vagy elavult funkciói](removed-deprecated-features-scm-updates.md) témakörben 12 hónappal az eltávolítás előtt.

Olyan módosítások esetén, amelyek csak a fordítási időt érintik, de binárisan kompatibilisek a tesztkörnyezettel és a termelési környezettel, az elavulási idő 12 hónapnál rövidebb lesz. Ezek általában olyan funkcionális frissítések, amelyeket a fordítón kell elvégezni.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
