---
title: Inventory Visibility támogatása WMS-cikkekhez
description: Ez a témakör a raktárkezelési folyamatokban (WMS- cikkeknél) engedélyezett cikkek láthatósági kezelését írja le.
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
ms.openlocfilehash: 54ce637d2d7b590988f7590eae5248276bcc4b96
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066610"
---
# <a name="inventory-visibility-support-for-wms-items"></a>Inventory Visibility támogatása WMS-cikkekhez

[!include [banner](../includes/banner.md)]

Ez a témakör a raktárkezelési folyamatokhoz (WMS) engedélyezett cikkek láthatósági kezelését írja le. A lehetőséget a Készlet láthatósága beállításhoz hozzáadó funkció neve *Speciális WMS*.

## <a name="wms-items"></a>WMS-cikkek

A WMS-cikk olyan cikk, amely engedélyezve van a WMS számára, és fel van feldolgozva egy olyan raktárban, ahol a WMS is engedélyezett.

A WMS **rendszerről és a Microsoft Raktárkezelési** modulról a Raktárkezelés Dynamics 365 Supply Chain Management [modullal kapcsolatos további tudnivalókat lásd](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>A funkció hatóköre

A készlet láthatóságának speciális WMS-funkciója az aktuális készlet lekérdezésen alapuló aktuális mennyiségi számításokkal foglalkozik. A funkció nem célja, hogy a készlet láthatósága segítségével általánosan kezelni tudja a raktárfeldolgozási tevékenységeket. A készlet láthatósága nem teszi elérhetővé a raktárspecifikus fogalmakat a felhasználói számára. Az alábbiakban néhány példát látható az alábbi fogalmakra:

- Foglalási hierarchia
- Azt jelzi, hogy engedélyezve van-e a cikk vagy raktár a WMS-szolgáltatásban.
- Egységszekvencia-csoport egyedi azonosítója
- Raktárspecifikus folyamatok, például szállítmányok, rakományok, hullámok és munka

A készlet láthatósága az Ellátásilánc-kezelésből küldött adatok alapján kiolvassa ezt az információt. A WMS-specifikus adatok (más szóval a `WHSInventReserve` tábla adatai) nem láthatók a felhasználók számára.

Ha a Speciális WMS szolgáltatást használja a készlet láthatóságához, minden lekérdezési eredmény meg fog egyezni az ellátásilánc-kezelésben közvetlenül készített lekérdezések eredményeivel. Azonban nem egyeznek meg a Raktárkezelés mobilalkalmazással készített lekérdezések eredményeivel, mivel a mobilalkalmazásban különböznek egy kissé a számítási logikától.

## <a name="when-to-use-the-feature"></a>Mikor kell használni a funkciót?

Javasoljuk, hogy a Speciális WMS szolgáltatás használata a készlet láthatósága érdekében olyan helyzetekben, amikor az alábbi feltételek teljesülnek:

- Az Ellátásilánc-kezelés adatait szinkronizálja a készlet láthatóságával.
- A WMS használatban van az ellátásilánc-kezelésben.
- A felhasználók a raktárszinttől eltérő szinten foglalják le a WMS-cikkeket (például mert raktári munkát használ).

Egyéb helyzetekben a tényleges készlet lekérdezésének eredményei ugyanazok lesznek, függetlenül attól, hogy engedélyezve van-e a Készlet láthatósága speciális WMS szolgáltatás. Ezenkívül a teljesítmény is jobb lesz, ha ilyen helyzetekben nem engedélyezi a szolgáltatást, mivel kevesebb számítás és kisebb járulékos költség van.

## <a name="enable-the-advanced-wms-feature-for-inventory-visibility"></a>A Speciális WMS szolgáltatás engedélyezése a készlet láthatósága érdekében

Ha engedélyezni szeretné a Speciális WMS szolgáltatást a készlet láthatósága érdekében, kövesse ezeket a lépéseket.

1. Jelentkezzen be rendszergazdaként az Ellátásilánc-kezelésbe.
1. A Szolgáltatáskezelés [munkaterület](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) megnyitása és a következő funkciók engedélyezése ebben a sorrendben:

    1. *Készletláthatósági integráció*
    1. *Raktári cikkek engedélyezése a Készletláthatóság funkcióban*

1. Menjen a **Készletgazdálkodás \> Beállítás \> Készletláthatóság integrációs paraméterek** menüpontba.
1. **A WMS-cikkek engedélyezése** lapon állítsa **a WMS-cikkek** engedélyezése lehetőséget Igen *beállításra*.
1. Bejelentkezés a Power Apps alkalmazásba.
1. Nyissa meg **a Konfigurálás** lapot, **majd a Funkciókezelés** lapon kapcsolja be a *SpeciálisWHS szolgáltatást*.
1. Az Ellátásilánc-kezelés területén menjen a Készletkezelés **– Időszakos \> feladatok \>– Készlet láthatósága integrációhoz**.
1. A munkaablakban a Disable **gombra kattintva** ideiglenesen letilthatja a készlet láthatóságát.
1. A munkaablakban válassza **az Engedélyezés** lehetőséget a készlet láthatóságának újra való engedélyezéséhez. A bővítményt újra betölti a rendszer, és ezzel engedélyezi az új funkciót. A WMS-sel kapcsolatos adatok szinkronizálása megkezdődik a készlet láthatóságával.

## <a name="query-on-hand-quantities-of-wms-items"></a>A WMS-cikkek készleten lévő mennyiségének lekérdezése

A WMS-cikkek [lekérdezéséhez ugyanazt az alkalmazásprogramozási felületet (API)](inventory-visibility-api.md) és üzenet szintaxist kell használni, mint a nem WMS-cikkekhez. Nem kell megadni, hogy egy cikk WMS-cikk vagy nem WMS-cikk-e. A készlet láthatósága automatikusan megkülönbözteti a cikkeket a tárolt adatok alapján.

A WMS-cikkek lekérdezéseiből származó eredmények alapvetően megegyezik a nem WMS-cikkek eredményeivel. Az az egyetlen különbség, `fno` hogy az adatforrás következő fizikai intézkedések számítása az Ellátásilánc-kezelés WMS-logikája alapján történik:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Minden más fizikai intézkedések számítása úgy történik, ahogyan akkor történik, amikor a Készlet láthatósága speciális WMS szolgáltatás nincs engedélyezve.

A WMS-cikkekhez [tartozó](https://www.microsoft.com/download/details.aspx?id=43284) cikkekkel kapcsolatos raktári számításokról a Raktárkezelés útmutatója tartalmaz részletes tájékoztatást.

Az exportált adatentitások Dataverse még nem frissítheti a WMS-cikkek mennyiségét. Az adatentitások által látható mennyiségek mind a nem WMS-cikkek, mind az olyan mennyiségek esetében helyesek, amelyekre nem hatással van a WMS-logika (`AvailPhysical``AvailOrdered` azaz a intézkedések, kivéve az, `ReservPhysical` és `ReservOrdered``fno` az adatforrás).

Tilos az ellátásilánc-kezelés adatforrásában tárolt WMS-cikkmennyiségek módosításait. A készlet láthatóságának egyéb szolgáltatásaival kapcsolatban a korlátozás érvényben van, hogy megelőzhetőek az ütközések.

## <a name="soft-reservations-on-wms-items-in-inventory-visibility"></a>A WMS-cikkekre vonatkozó soft foglalások a készlet láthatóságában

A WMS-cikkekre [általánosan](inventory-visibility-reservations.md) támogatott az előzetes lefoglalás. Az előzetes foglalási számításokban a WMS-hez kapcsolódó fizikai intézkedéseket is figyelembe lehet foglalni. 

A WMS-cikkeknél *jelenleg* nem támogatott a foglaláshoz rendelkezésre álló számítás. Ezért ha az aktuális dimenziók fölött foglalás történik, ahol nem teljes a foglalás, *akkor helytelen a rendelkezésre álló foglalási* számítás. Az kötetlen foglalásokra nem fog hatással lenni, **ha azCheckAvailForReserv beállítás** le van tiltva az soft [reservation API-ban](inventory-visibility-api.md#create-one-reservation-event).

Ez a megszorítás az olyan funkciókra és testreszabott funkciókra is vonatkozik, amelyek az előzetes foglaláson (például felosztáson) alapulnak.

## <a name="calculate-available-to-promise-quantities"></a>Ígérethez rendelkezésre álló mennyiségek kiszámítása

A megoldás teljes mértékben támogatja a [WMS-cikkek](inventory-visibility-available-to-promise.md) ígérethez rendelkezésre álló elemeit. A WMS-specifikus adatokra vonatkozó tptp-számításokat anélkül is be lehet definiálni.
