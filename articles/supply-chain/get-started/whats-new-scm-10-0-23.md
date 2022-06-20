---
title: Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.23 szolgáltatásban (2022. január)
description: Ez a témakör a Microsoft Dynamics 365 Supply Chain Management 10.0.23 rendszer új vagy módosult funkcióit ismerteti.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: acffe97cf1844f16a70c716a7f2078b1e9a072d1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849474"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Új vagy módosult elemek a Dynamics 365 Supply Chain Management 10.0.23 szolgáltatásban (2022. január)

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a funkciókat, amelyek vagy újak, vagy módosulnak a Microsoft Dynamics 365 Supply Chain Management 10.0.23-as verziójában. Ennek a verziónak 10.0.1037 a buildszáma, és a következő módon érhető el:

- **A kiadás előzetes verziója** 2021. október
- **A kiadás általános elérhetővé tétele (saját frissítés):** 2021. december
- **A kiadás általános elérhetővé tétele (automatikus frissítés):** 2022. január

## <a name="features-included-in-this-release"></a>A verzióban található funkciók

Ez a kiadás a következő táblázatban felsorolt funkciókat tartalmazza: A *Funkció* oszlop a [kiadási tervre](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features) mutató hivatkozásokat tartalmaz, amelyeken látható az egyes funkciók hivatalos kiadási dátuma. A *További tudnivalók* oszlopban további részletek és/vagy a kapcsolódó dokumentációra mutató hivatkozások találhatóak. A funkciók bekapcsolásának meghatározásához lásd az *Engedélyező* oszlopban. A funkciókezelés használatávall kapcsolatos további tudnivalókat lásd [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Előfordulhat, hogy a cikk első közzététele után frissítjük ezt a cikket, hogy szerepeljenek a buildben található funkciók.

| Szolgáltatásterület | Szolgáltatás | További információ | Engedélyezte:   |
|---|---|---|---|
| Globális címjegyzék | A címbeállításban minden országhoz/területhez meg kell határoznia egy alapértelmezett államot/tartományt | Ezzel minden országhoz/területhez meghatározhat egy alapértelmezett államot/tartományt a globális címjegyzék címbeállításában. Ha be van állítva az alapértelmezett állam/tartomány, akkor ez lesz az állam/tartomány mezők alapértelmezett értéke, amikor új megye- vagy városrekordot hoz létre az adott országhoz/régióhoz. Lásd még [Címbeállítás.](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | Alapértelmezés szerint engedélyezve. |
| Készlet&nbsp;és&nbsp;logisztika | [A Warehouse Management mobilalkalmazás feladatainak szüneteltetése](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [Elterelések konfigurálása a mobileszközök menüelemeinek lépéseihez](../warehousing/warehouse-app-detours.md) | Funkciókezelés (*Warehouse Management alkalmazás kitérők*) |
| Készlet&nbsp;és&nbsp;logisztika | [Raktári alkalmazásban előléptetett mezők](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Előléptetett mezők konfigurálása a mobileszközön használt lépésekhez](../warehousing/warehouse-app-promoted-fields.md)| Funkciókezelés: (*Raktári alkalmazásban előléptetett mezők*) |
| Gyártás | [Gyártás-végrehajtási rendszerek integrációja](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [Integráció külső gyártásvégrehajtási rendszerekkel](../production-control/mes-integration.md) | Funkciókezelés (*Gyártás-végrehajtási rendszer integrációja*) |
| Gyártás | [Jelentés a termelési üzem végrehajtási felületéről származó társ- és melléktermékekről](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [A termelési üzem végrehajtási felületének használata dolgozók számára](../production-control/production-floor-execution-use.md) | Funkciókezelés (*Jelentés a termelési üzem végrehajtási felületéről származó társ- és melléktermékekről*) |
| Tervezés | [A tervezésoptimalizálás támogatása a prioritáson alapuló tervezéshez](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [Prioritásokon alapuló tervezés](../master-planning/planning-optimization/priority-based-planning.md) | Funkciókezelés (*prioritásvezérelt MRP-támogatás tervezési optimalizáláshoz*) |

## <a name="feature-enhancements-included-in-this-release"></a>A kiadásban található funkciófejlesztések

Ez a kiadás a következő táblázatban felsorolt új funkciófejlesztéseket tartalmazza. Ezek közül mindegyik fejlesztés egy már meglévő funkciót fejleszt tovább. Mivel fejlesztésekről van szó, nem szerepelnek a [kiadási tervben](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Alapértelmezés szerint mindegyik fejlesztés ki van kapcsolva (hacsak nincs másképpen jelezve), így biztos lehet abban, hogy nem ütköznek a meglévő testreszabásokkal vagy beállításokkal.

Ha bármelyik funkciót be vagy ki szeretné kapcsolni, akkor ezt a [funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) kell megtennie ahol ezek a következő *Funkció neve a funkciókezelésben* oszlopában feltüntetett nevekkel vannak felsorolva.

| Modul | Funkcióneve a funkciókezelésben | További információ |
|---|---|---|
| Eszközkezelés | Ellenszámlák költségekhez a munkarendelési naplókban | Ezzel a funkcióval egy munkarendelési naplóban felsorolt minden költséghez külön ellenszámlát lehet megadni. Általában minden költséghez társíthat egy szállítói számlát, de más számlatípusokat is támogat a rendszer. Két új oszlopot (**Ellenszámla típusa** és **Ellenszámla**) ad hozzá a **Munkarendelési napló** oldal **Költség** gyorslapjához.|
| Költségkezelés | Kapcsolódó bizonylatok létrehozása az elszámolóár kerekítési átértékeléseihez | <p>Pénzügyi készletfeladáskor (például értékesítési rendelés számlája vagy készlettranzakció) történik, ennek a funkciónak az hatására a rendszer létrehoz egy külön bizonylatot minden kapcsolódó elszámolóáras kerekítési átértékeléshez, és kapcsolódó bizonylatként csatolja a pénzügyi feladási bizonylathoz.</p><p>E funkció nélkül a rendszer ugyanazon bizonylatfeladás elszámolóár-kerekítési átértékeléseit rögzíti. Ez a viselkedés bizonyos esetekben ütköző dátumadatokat is okozhat, mivel az átértékelések a munkamenet vagy a rendszer dátumát használják, míg a pénzügyi feladások a feladási dátumot használják.</p> |
| Készlet- és raktárkezelés | \[Oroszország\] Pénzügyi készlet tranzakcióit érintő Storno feladása az értékesítési rendelések pénzügyi bizonylatán szereplő helyesbítési jelzőnek megfelelően | Ez a funkció hatással van az Oroszországra vonatkozó jóváírás-helyesbítési funkciókra. Lehetővé teszi az értékesítési számlák készlettranzakcióinak feladását a főkönyv javítási lehetőségével összhangban. Ha ez a funkció engedélyezve van, a készlettranzakciók pénzügyi bizonylatán nincs több eltérés a **Javítás** jelölője és a készlettranzakciók **Sztornó** jelölője között. |
| Készlet- és raktárkezelés | (Oroszország) Készletegyenleg-forgalomra vonatkozó jelentés kötegelt számításának futtatása | A Supply Chain Management orosz honosításaihoz ez funkció lehetővé teszi a *Készletegyenleg-forgalomra* vonatkozó jelentés kötegelt futtatását, a jelentés tárolását és a korábban létrehozott jelentések megtekintését. |
| Készlet- és raktárkezelés | (Oroszország) A készletgazdálkodásban előforduló ország- vagy régióspecifikus elsődleges képernyők esetén használjon fordítást a helyi nyelvre | A Supply Chain Management orosz honosításaihoz – ez funkció úgy engedélyezhető, hogy a következő orosz specifikus készletfelvételekben orosz fordításokat használ a termék/cikknevekre és a mértékegységekre:Leltárlista (INV-3),Leltárlista (INV-5),Leltárlista (INV-6). |
| Alaptervezés | Azure Machine Learning szolgáltatás igény-előrejelzéshez | Ez a funkció lehetővé teszi, hogy az Azure számítógép-oktatási szolgáltatás igény-előrejelzéseket generáljon a korábbi adatok alapján. A további tudnivalókat lásd az igény-előrejelzési [beállításoknál](../master-planning/demand-forecasting-setup.md). |
| Beszerzés és forrás | Beszerzési rendelés frissítési előzményeinek tisztítása | Ezzel a funkcióval a beszerzési rendelések frissítéséhez kapcsolódó ideiglenes előzményrekordok tisztítására van lehetőség. Hozzáad egy új **Beszerzési rendelés frissítési előzményeinek tisztítása** nevű gombot a **Minden beszerzési rendelés** lap műveletablakába. Alapértelmezetten ez a paraméter engedélyezett. |
| Gyártásvezérlés | (Előzetes verzió) Automatikusan feladott kitárolási listákhoz engedélyezett raktári anyagok automatikus kitárolása | A funkcióval automatikusan kitárolhatja és feloldhatja a készletdimenziókat az automatikusan feladott, származtatott/visszavezetett kitárolásilista-naplókhoz. |
| Gyártásvezérlés | Nyersanyagok lejáratának ellenőrzése a tervezett felhasználási dátumhoz képest | Ez a funkció módosítja a köteg lejárati dátumának ellenőrzését a termelés során felhasznált nyersanyagok egy kötegének lefoglalása során. Ha ez a funkció engedélyezve van, a rendszer a köteg lejárati dátumát a tervezett felhasználási dátummal (a nyersanyag dátumával) szemben ellenőrzi, a termelési anyagjegyzéksoron vagy a kötegrendelés receptúra sorában meghatározottak szerint. Ha ez a funkció le van tiltva, a program a termelés vagy kötegrendelés tervezett szállítási dátuma szerint (ahogy korábban) ellenőrzi a köteg lejárati dátumát. |
| Értékesítés és marketing | Értékesítésfrissítési előzmények tisztítása kor alapján | Ezzel a funkcióval lehet beállítani **az értékesítési frissítések előzményeinek tisztítási ismétlődő feladat futtatásakor megtartható rekordok maximális** korát. A régebbi rekordok törlődni fognak. Ez hasznos lehet akkor, ha a feladatot rendszeresen futtatásra kell beállítani, mivel a kort a program mindig a feladat futtatásának dátumára viszonyítottan számítja ki. E funkció nélkül csak azt a dátumot állíthatja be, amely a legrégebbit megtartja. További információ az Értékesítési előzmények adatainak [tisztítása ütemezése oldalon található](../sales-marketing/sales-update-history-cleanup-performance-improvements.md). |
| Értékesítés és marketing | A 100 legjelentősebb vevő jelentés teljesítményének javítása | Ez a funkció javítja a **100 legfontosabb** vevői jelentés teljesítményét, azáltal, hogy a jelentést minden vevőn futtatja (ami a célzott felhasználás), ahelyett, hogy engedélyezné az egyéni lekérdezéseket. Ha ez a funkció engedélyezve van, akkor a **100 legfontosabb** jelentés párbeszédpanelén minden **Belefoglalandó rekordok** beállítás le van tiltva. |
| Raktárkezelés | Skálázásiegység-támogatás a kimenő rendelések raktárába való kiadáshoz | Ha ez a funkció engedélyezve van, a kimenő rendelések közvetlenül azon skálázási egységen adhatók ki a központból, ahonnan a rendelések teljesítésre fognak kerülni. |

## <a name="new-and-updated-documentation-resources"></a>Új és frissített dokumentáció-erőforrások

Nemrégiben hozzáadta vagy jelentősen frissítettük a következő súgócikkeket. Ezek a cikkek nem feltétlenül kapcsolódnak az ehhez a verzióhoz hozzáadott új funkciókhoz, mint azt az előző szakaszban felsoroltak. Előfordulhat azonban, hogy segítenek a meglévő funkciókból további lehetőségeket kihozni.

| Szolgáltatásterület | Új vagy frissített cikkek |
|---|---|
| Tervezési változáskezelés | A [Mérnöki attribútumok és mérnöki attribútumok keresése](../engineering-change-management/engineering-attributes-and-search.md) immár leírja, hogyan működik a mérnöki attribútumok öröklése. |
| Alaptervezés | Az [Alaptervezés az igény-előrejelzésekkel](../master-planning/planning-optimization/demand-forecast.md) és [Előrejelzés-csökkentési kulcsok](../master-planning/reduction-keys.md) immár tájékoztatást ad arról, hogyan lehet használni a csökkentési kulcsokat. |
| Alaptervezés | [Biztonsági készlet teljesítése cikkek számára](../master-planning/safety-stock-replenishment.md) immár további tájékoztatást ad a minimum- és maximumkulcsok használatával kapcsolatban. |
| Alaptervezés | A [Készlet-előrejelzések](../master-planning/inventory-forecast.md) mostantól további tájékoztatást tartalmaznak az előrejelzések allokálásáról. |
| Alaptervezés | [Készletütemezés](../master-planning/supply-schedule.md) |
| Raktárkezelés | [Globális mobileszköz-paraméterek](../warehousing/mobile-device-parameters.md) |
| Raktárkezelés | [Horgonyzás](../warehousing/anchoring.md) |
| Értékesítés és marketing | A vállalatközi kereskedelem leírása mostantól részletes, [a](../sales-marketing/intercompany-trade-set-up.md) vállalatközi kereskedelem és a kapcsolódó cikkek beállításával kezdődik. |
| Értékesítés és marketing | [Értékesítési előzmények adattisztítási teljesítményének javításai](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Készletgazdálkodás | A készlet láthatósági dokumentációja ki lett bontva és frissítve lett, [a kapcsolódó cikkek és a készlet láthatósági](../inventory/inventory-visibility.md) bővítményével kezdve. |
| Raktárkezelés | [Mobileszköz felhasználói fiókjai](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>További erőforrások

### <a name="platform-updates-for-finance-and-operations-apps"></a>A Pénzügy és az Üzemeltetés alkalmazás platformfrissítései

A Microsoft Dynamics 365 Supply Chain Management 10.0.23 platformfrissítéseket tartalmaz. A további [tudnivalókat lásd a Pénzügy és műveletek alkalmazások 10.0.23-as verziójának Platformfrissítései (2021. november)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md).

### <a name="bug-fixes"></a>Hibajavítások

Ha további tájékoztatást szeretne kapni a 10.0.23 részét képező frissítésekben található hibajavításokról, lépjen be a Lifecycle Services (LCS) szolgáltatásokba, és tekintse meg a [Tudásbázis cikket](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910).

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
