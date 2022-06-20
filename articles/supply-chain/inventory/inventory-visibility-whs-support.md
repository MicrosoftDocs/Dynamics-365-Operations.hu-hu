---
title: Inventory Visibility támogatása WHS-cikkekhez
description: Ez a témakör a speciális raktári folyamatokban (whS- cikkeknél) engedélyezett cikkek láthatóságát ismerteti.
author: yufeihuang
ms.date: 03/10/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: ec2254d6cf203216acea88fdfb54ad491abdeb49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895670"
---
# <a name="inventory-visibility-support-for-whs-items"></a>Inventory Visibility támogatása WHS-cikkekhez

[!include [banner](../includes/banner.md)]

Ez a témakör a speciális raktári folyamatokban (whS- cikkeknél) engedélyezett cikkek láthatóságát ismerteti. A lehetőséget a Készlet láthatósága beállításhoz hozzáadó funkció neve *Speciális raktárkészlet-zárás*.

## <a name="whs-items"></a>Cikkek va. y

A raktárkezelési folyamatokat olyan cikkek jelentik, amelyek speciális raktári folyamatokhoz vannak engedélyezve, és fel vannak feldolgozva egy olyan raktárban, ahol a raktárkezelési folyamatokat is engedélyezték.

A raktárkezelési folyamatokkal **és a Microsoft** Raktárkezelési modullal kapcsolatos további Dynamics 365 Supply Chain Management tudnivalókat lásd a [Raktárkezelés modulban](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>A funkció hatóköre

A készlet láthatóságának speciális whS funkciója az aktuális készlet lekérdezésen alapuló aktuális mennyiségi számításokkal foglalkozik. A funkció nem célja, hogy a készlet láthatósága segítségével általánosan kezelni tudja a raktárfeldolgozási tevékenységeket. A készlet láthatósága nem teszi elérhetővé a raktárspecifikus fogalmakat a felhasználói számára. Az alábbiakban néhány példát látható az alábbi fogalmakra:

- Foglalási hierarchia
- Azt jelzi, hogy engedélyezve van-e a cikk vagy a raktár raktár.
- Egységszekvencia-csoport egyedi azonosítója
- Raktárspecifikus folyamatok, például szállítmányok, rakományok, hullámok és munka

A készlet láthatósága az Ellátásilánc-kezelésből küldött adatok alapján kiolvassa ezt az információt. A whS-specifikus adatok (más szóval a `WHSInventReserve` tábla adatai) nem láthatók a felhasználók számára.

Ha a Speciális raktárkezelés szolgáltatást használja a készlet láthatóságához, minden lekérdezési eredmény meg fog egyezni az ellátásilánc-kezelésben közvetlenül készített lekérdezések eredményeivel. Azonban nem egyeznek meg a Raktárkezelés mobilalkalmazással készített lekérdezések eredményeivel, mivel a mobilalkalmazásban különböznek egy kissé a számítási logikától.

## <a name="when-to-use-the-feature"></a>Mikor kell használni a funkciót?

Javasoljuk, hogy a Speciális raktárkészlet-zárás funkció használata a készlet láthatósága érdekében olyan helyzetekben, amikor az alábbi feltételek teljesülnek:

- Az Ellátásilánc-kezelés adatait szinkronizálja a készlet láthatóságával.
- Az ellátásilánc-kezelésben whS-t használ.
- A felhasználók a raktári szinttől eltérő szinten foglalják le a raktári cikkek raktári foglalását (például mert raktári munkát használ).

Egyéb helyzetekben a tényleges készlet lekérdezésének eredményei ugyanazok lesznek, függetlenül attól, hogy engedélyezve van-e a Készlet láthatósága speciális raktárkészlet-funkció. Ezenkívül a teljesítmény is jobb lesz, ha ilyen helyzetekben nem engedélyezi a szolgáltatást, mivel kevesebb számítás és kisebb járulékos költség van.

## <a name="enable-the-advanced-whs-feature-for-inventory-visibility"></a>A speciális raktárkészlet-naplózási funkció engedélyezése a készlet láthatósága érdekében

Ha engedélyezni szeretné a speciális raktárkészlet-naplózási szolgáltatást a készlet láthatósága érdekében, kövesse ezeket a lépéseket.

1. Jelentkezzen be rendszergazdaként az Ellátásilánc-kezelésbe.
1. A Szolgáltatáskezelés [munkaterület](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) megnyitása és a következő funkciók engedélyezése ebben a sorrendben:

    1. *Készletláthatósági integráció*
    1. *Raktári cikkek engedélyezése a Készletláthatóság funkcióban*

1. Menjen a **Készletgazdálkodás \> Beállítás \> Készletláthatóság integrációs paraméterek** menüpontba.
1. A WhS Cikkek engedélyezése **lapon állítsa** a WhS cikkek **engedélyezése lehetőséget Igen beállításra** *.*
1. Bejelentkezés a Power Apps alkalmazásba.
1. Nyissa meg **a Konfigurálás** lapot, **majd a Funkciókezelés** lapon kapcsolja be a *SpeciálisWHS szolgáltatást*.
1. Az Ellátásilánc-kezelés területén menjen a Készletkezelés **– Időszakos \> feladatok \>– Készlet láthatósága integrációhoz**.
1. A munkaablakban a Disable **gombra kattintva** ideiglenesen letilthatja a készlet láthatóságát.
1. A munkaablakban válassza **az Engedélyezés** lehetőséget a készlet láthatóságának újra való engedélyezéséhez. A bővítményt újra betölti a rendszer, és ezzel engedélyezi az új funkciót. A raktárkészlet-nyilvántartással kapcsolatos adatok szinkronizálása megkezdődik a készlet láthatóságával.

## <a name="query-on-hand-quantities-of-whs-items"></a>Készleten lévő cikkek mennyiségének lekérdezése

A whS [cikkek lekérdezéséhez ugyanazt az alkalmazásprogramozási felületet (API)](inventory-visibility-api.md) és üzenet szintaxist kell használni, mint a nem whs cikkeknél. Nem kell megadni, hogy a cikk whS vagy nem whs típusú cikk-e. A készlet láthatósága automatikusan megkülönbözteti a cikkeket a tárolt adatok alapján.

A whs cikkek lekérdezései alapvetően megegyezikek a nem whs cikkek eredményeivel. Az az egyetlen különbség `fno`, hogy az adatforrás következő fizikai intézkedések számítása az ellátásilánc-kezelés whS-logikája alapján történik:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Minden más fizikai intézkedések számítása úgy történik, ahogyan akkor történik, amikor a Készlet láthatósága speciális raktárkészlet-funkció nincs engedélyezve.

A raktárkezelési cikkekre [vonatkozó](https://www.microsoft.com/download/details.aspx?id=43284) raktárkezelési számításokról a Raktárkezelés útmutatója tartalmaz részletes tájékoztatást.

Az exportált adatentitások Dataverse még nem frissíthetik a whs cikkek mennyiségét. Az adatentitások között megjelenő mennyiségek mind a nem whs cikkek, mind az olyan mennyiségek esetében helyesek, amelyekre nem hatással van a whS-logika (`AvailPhysical``AvailOrdered` azaz a m.m., kivéve az, `ReservPhysical` és `ReservOrdered``fno` az adatforrás).

Az ellátásilánc-kezelés adatforrásában tárolt raktárkezelési cikkek mennyiségének változtatása tilos. A készlet láthatóságának egyéb szolgáltatásaival kapcsolatban a korlátozás érvényben van, hogy megelőzhetőek az ütközések.

## <a name="soft-reservations-on-whs-items-in-inventory-visibility"></a>Raktárkészlet-cikkekre vonatkozó kötefoglalások a készlet láthatóságában

A whS cikkekre [általában](inventory-visibility-reservations.md) támogatottak az soft foglalások. Az előzetes foglalások számításában a whS-sel kapcsolatos fizikai intézkedések is figyelembeveheti a számítást. 

Ismert korlátozás, hogy *a foglaláshoz* rendelkezésre álló számítás jelenleg nem támogatott a whs cikkeknél. Ezért ha az aktuális dimenziók fölött foglalás történik, ahol nem teljes a foglalás, *akkor helytelen a rendelkezésre álló foglalási* számítás. Az kötetlen foglalásokra nem fog hatással lenni, **ha azCheckAvailForReserv beállítás** le van tiltva az soft [reservation API-ban](inventory-visibility-api.md#create-one-reservation-event).

Ez a megszorítás az olyan funkciókra és testreszabott funkciókra is vonatkozik, amelyek az előzetes foglaláson (például felosztáson) alapulnak.

## <a name="calculate-available-to-promise-quantities"></a>Ígérethez rendelkezésre álló mennyiségek kiszámítása

A megoldás teljes mértékben támogatja az [ígérethez rendelkezésre álló cikkeket](inventory-visibility-available-to-promise.md) a whS cikkekhez. A whs-specifikus adatokra vonatkozó okkal nem számolhat el olyan számításokat, amelyekhez nem szükséges mennyiség számítása.
