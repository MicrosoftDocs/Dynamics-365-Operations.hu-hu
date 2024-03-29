---
title: Műveletek ütemezése
description: Ez a cikk a műveletek ütemezésére vonatkozó információkat tartalmaz. A műveletek ütemezését arra használhatja, hogy általános időbeli becslést készítsen a termelési folyamatról.
author: johanhoffmann
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198073
ms.assetid: 12c28b11-80aa-4668-b15b-724cb24890bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b9ae31b288831d2f3b85bf1996206221e0bdbbd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871891"
---
# <a name="operations-scheduling"></a>Műveletek ütemezése

[!include [banner](../includes/banner.md)]

Ez a cikk a műveletek ütemezésére vonatkozó információkat tartalmaz. A műveletek ütemezését arra használhatja, hogy általános időbeli becslést készítsen a termelési folyamatról.

A termelést műveleti szinten és feladatszinten is ütemezheti. A műveletütemezés a feladatütemezéssel szemben nem biztosítja az útvonalhoz tartalmazó termelési műveletek feladatokká való lebontását. Ha további részleteket szeretne beemelni az ütemezésbe, például az aktuális kapacitás adatait, a műveletütemezés futtatása után futtathatja a feladatütemezést. Csak a feladatütemezést is futtathatja. A feladatütemezést általában az üzemben végrehajtott egyes feladatok ütemezésére használják, rendszerint azonnal vagy rövid távú jelleggel.

## <a name="components-of-operations-scheduling"></a>A műveletütemezés összetevői
A műveletütemezés fő összetevői: az ütemezési irány, az erőforrások kapacitása és az anyag szerinti optimalizálás. A műveletek ütemezésének használata esetén a következő célokat érheti el:

-   A tervezési módszer vezérlése (ütemezés egy megadott dátumtól számítva visszafelé vagy előre).
-   Optimalizálja az erőforrás-felhasználást a termelésnek az erőforrások kapacitása alapján történő ütemezésével. Ez a megközelítés segít annak felismerésében, hogy mikor van szükség másodlagos erőforrások használatára.
-   Optimalizálja az anyaghasználatot a termelésnek a szükséges anyagok elérhetősége alapján történő ütemezésével.
-   Ütemezi és szinkronizálja a hivatkozási termeléseket. A hivatkozási termelések dátumai a termelési rendelés ütemezése szerint módosulnak.

A műveletütemezés futtatása előtt becslést kell futtatnia a termelési rendelés költségéről. Ha nem futtatta a becslést, az automatikusan lefut a műveletütemezést megelőzően. A műveletütemezés a következő adatokat határozza meg:

-   A termelésre tervezett termék
-   A termék konfigurációja
-   A termelésben részt vevő mennyiségek
-   A termelés kezdő és záró dátuma
-   A termelési tevékenységeket végrehajtó erőforrások kapacitásfoglalásai

A beállítási idő, a feldolgozási idő és a futtatási idő megadása a termelési műveletekben van megadva. Miután futtatja a műveletek ütemezését, a termelési rendelés állapota **Ütemezett**, és minden művelet a termelési útvonal által megadott sorrendben van ütemezve. Ugyanakkor azonban a rendszer csak a művelet időtartamát veszi figyelembe. A kezdő és záró időpont nincs ütemezve.

## <a name="scheduling-direction-and-date"></a>Ütemezés iránya és dátuma
Az ütemezés iránya alapvető jellemző az ütemezési folyamatban. A termelés ütemezhető a dátumokat megelőző időszakra és a dátumokat követő időszakra is, az időzítési és ütemezési követelményeknek megfelelően.

-   **Előre az ütemezési dátumtól kezdve** – A termelést minél korábbi indításra ütemezheti. A termelés kezdési dátuma lehet az adott nap, másnap vagy bármilyen jövőbeni dátum. A termelés a lehető legkorábbi kezdő és befejező időpontra van ütemezve.
-   **Visszafelé az ütemezési dátumtól kezdve** – A termelést minél későbbi indításra ütemezheti. A visszafelé ütemezés a termelés befejezési dátumán alapul. Azon a dátumon alapul, amelyen a termelést be kell fejezni, és innen számítja vissza a lehető legkésőbbi időpontot, amikor a termelést a még időben be lehet fejezni.

## <a name="resource-scheduling"></a>Erőforrás-ütemezés.
Műveletütemezés futtatásakor a termelési útvonal minden művelete a művelethez megadott erőforráshoz van ütemezve. Ezenkívül minden művelet időtartama a termékútvonalon belül van definiálva. Ha egy művelet egy erőforráscsoporthoz van megadva, az ütemezés kapacitást foglal a csoportnál. A feladatok ütemezésével ellentétben a műveletek ütemezése nem választja ki a konkrét erőforrásokat a csoportban. Ha véges kapacitással dolgozik, úgy az ütemezés az adott termelés elvégzéséhez szükséges erőforrások rendelkezésre állásának függvénye. A műveletek ütemezése során a termelési útvonal műveletei által meghatározott sorrendben történik. Az ütemezési lehetőség a termelési útvonalon megadott műveletidők alapján foglal le erőforráscsoport-kapacitásokat. A részt vevő erőforrások elérhető kapacitásának összege meghatározza az erőforráscsoport kapacitását. Az erőforrások kapcsán korábban lekötött kapacitásokat a rendszer nem elérhető kapacitásként veszi figyelembe. Ha nincs elég rendelkezésre álló kapacitás a termeléshez, úgy a rendszer késleltetheti vagy le is állíthatja a termelési rendeléseket. Megadhatja a termelésben részt vevő erőforrások várható hatékonyságát is. A hatékonyságot az erőforráson kifejezett százalékban adhatja meg. A hatékonysági százalék korrigálja az erőforrás teljesítményét. Ez a kiigazítás befolyásolja az erőforrásra lefoglalt időt. Az erőforrást használó műveletek átfutási ideje is ennek megfelelően kerül módosításra.

## <a name="operations-scheduling-and-master-planning"></a>Műveletek ütemezése és alaptervezés
A műveletek ütemezése az alaptervezést is elindítja, valamint meghatározza az anyagszükséglet-számításokat. A műveletek ütemezése a következő adatokat veszi figyelembe:

-   **Visszanaplózott termelések** – Olyan termékek, amelyek termelését már tervezték, kiadták vagy elindították
-   **Anyagok rendelkezésre állása** – Készlet, altermelések, beszállítók
-   **Kapacitás rendelkezésre állása** – A termeléshez szükséges erőforrások

> [!NOTE]
> Ha többszálas alaptervezést és műveletütemezést használ, akkor a rendszer nem veszi figyelembe a véges kapacitást. 

## <a name="cancellations"></a>Visszavonások
Műveletütemezés futtatásakor törölheti az útvonal meghatározott részeit. Ide tartozik például a várakozási idő, a beállítási idő, a feldolgozási idő, az átfedési idő és a szállítási idő.

## <a name="finite-materials"></a>Véges anyagmennyiség
Ha véges anyagokkal dolgozik, az ütemezés a termeléshez szükséges anyagok rendelkezésre állásától is függ. Ha nincs elég elérhető összetevő a termeléshez, a termelés elhúzódhat. Az ütemezést az anyagok felhasználására alapozhatja úgy, hogy meghatározza, melyek a termeléshez feltétlenül szükséges anyagok. Ha az optimalizálás az erőforrások kapacitása és anyagok rendelkezésre állásától is függ, a rendszer a termelést ezen megszorítások alapján számolja ki. A termelési rendelés nem ütemezhető amíg a kapacitás és az anyagok egyszerre és a szükséges mennyiségben nem állnak rendelkezésre.

## <a name="additional-resources"></a>További erőforrások

[A műveletek ütemezésének beállításai](operation-scheduling-options.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]