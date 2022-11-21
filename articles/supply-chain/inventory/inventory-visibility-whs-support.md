---
title: Inventory Visibility támogatása WMS-cikkekhez
description: Ez a témakör a raktárkezelési folyamatokban (WMS- cikkeknél) engedélyezett cikkek láthatósági kezelését írja le.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: bed402ecf20c19e81b2687efd90dba600460971a
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762739"
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

Javasoljuk, hogy a WMS szolgáltatást használja a készlet láthatósága érdekében olyan helyzetekben, amikor az alábbi feltételek teljesülnek:

- Az Ellátásilánc-kezelés adatait szinkronizálja a készlet láthatóságával.
- A WMS használatban van az ellátásilánc-kezelésben.
- A felhasználók foglalást kötnek a wmS-cikkekre a raktár szintje alatti szinteken (például az tábla szintjén, mert a raktári munka feldolgozását intézi).

Egyéb helyzetekben a tényleges készlet lekérdezésének eredményei ugyanazok lesznek, függetlenül attól, hogy engedélyezve van-e a Készlet láthatósága speciális WMS szolgáltatás. Ezenkívül a teljesítmény is jobb lesz, ha ilyen helyzetekben nem engedélyezi a szolgáltatást, mivel kevesebb számítás és kisebb járulékos költség van.

## <a name="enable-the-wms-feature-for-inventory-visibility"></a>A WMS szolgáltatás engedélyezése a készlet láthatósága érdekében

Ha engedélyezni szeretné a WMS szolgáltatást a készlet láthatósága érdekében, kövesse ezeket a lépéseket.

1. Jelentkezzen be rendszergazdaként az Ellátásilánc-kezelésbe.
1. A Szolgáltatáskezelés [munkaterület](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) megnyitása és a következő funkciók engedélyezése ebben a sorrendben:

    1. *Készletláthatósági integráció*
    1. *Raktári cikkek engedélyezése a Készletláthatóság funkcióban*

1. Menjen a **Készletgazdálkodás \> Beállítás \> Készletláthatóság integrációs paraméterek** menüpontba.
1. **A WMS-cikkek engedélyezése** lapon állítsa **a WMS-cikkek** engedélyezése lehetőséget Igen *beállításra*.
1. Jelentkezzen be a Power Apps környezetébe, és nyissa meg a **Készletláthatóság** menüpontot.
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

Minden más fizikai intézkedések számítása úgy történik, mint amikor a WMS készlet láthatósági funkciója le van tiltva.

A WMS-cikkekhez [tartozó](https://www.microsoft.com/download/details.aspx?id=43284) cikkekkel kapcsolatos raktári számításokról a Raktárkezelés útmutatója tartalmaz részletes tájékoztatást.

## <a name="on-hand-list-view-and-data-entity-for-wms-items"></a>A WMS-cikkekhez tartozó, az adott cikkhez tartozó, az adott cikkhez tartozó, az adott vállalatnál rendelkezésre lévő listanézet és adatentitás

A **készlet láthatósági összefoglaló lapja** nézetet biztosít az *aktuális készletindex lekérdezésének előzetes betöltési eredményei entitáshoz*. A Készletösszegzés *entitástól* *eltérően az aktuális index lekérdezés előzetes betöltési eredményei* entitás tényleges készletlistát biztosít a kiválasztott dimenziókkal együtt a termékekhez. A készlet láthatósága 15 percenként szinkronizálja az előzetesen betöltött összesített adatokat.

Ha a készlet láthatóságát a WMS-cikkekhez használja, és szeretné megtekinteni a *WMS-cikkek aktuális listáját, javasoljuk,*[hogy engedélyezze a készlet láthatóságának összegzése funkciót (](inventory-visibility-power-platform.md#preload-streamlined-onhand-query) lásd még egy egyszerű aktuális lekérdezés előzetes betöltését). A megfelelő adatentitás Dataverse tárolja a lekérdezés előzetes betöltési eredményét, amely 15 percenként frissül. Az adatentitás neve.`Onhand Index Query Preload Result`

> [!IMPORTANT]
> Az Dataverse entitás csak olvasható. Az adatokat megtekintheti és exportálhatja a készlet láthatósági entitásában, **de nem módosíthatja őket**.

Tilos az Ellátásilánc-kezelés adatforrásban (`fno`) tárolt WMS-cikkmennyiségek módosításait. Ez a viselkedés megfelel a készlet láthatósága egyéb szolgáltatásainak viselkedésének. Ez a korlátozás az ütközések elkerülése érdekében van érvényben.

## <a name="wms-item-compatibility-for-other-functions-in-inventory-visibility"></a>WMS-cikk-kompatibilitás a készlet láthatósága egyéb funkcióihoz

[A WMS-cikkekre](inventory-visibility-reservations.md)[vonatkozó](inventory-visibility-allocation.md) előzetes foglalások és készletfoglalások támogatottak. Az előzetes foglalások és felosztási számításokban a WMS-hez kapcsolódó fizikai intézkedéseket is figyelembe lehet foglalni.

## <a name="calculate-available-to-promise-quantities"></a>Ígérethez rendelkezésre álló mennyiségek kiszámítása

A megoldás teljes mértékben támogatja a [WMS-cikkek](inventory-visibility-available-to-promise.md) ígérethez rendelkezésre álló elemeit. A WMS-specifikus adatokra vonatkozó tptp-számításokat anélkül is be lehet definiálni.
