---
title: A műveletek ütemezésének beállításai
description: Ez a témakör leírja a műveletek ütemezési beállításait. A műveletek ütemezését arra használhatja, hogy általános időbeli becslést készítsen a termelési folyamatról.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198123
ms.assetid: d680d7be-da64-4132-89fe-ad2fa59afb77
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f042b5d2b06d6dc880195a3c0c7bb62e41b1d006
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011097"
---
# <a name="operations-scheduling-options"></a>A műveletek ütemezésének beállításai

[!include [banner](../includes/banner.md)]

Ez a témakör leírja a műveletek ütemezési beállításait. A műveletek ütemezését arra használhatja, hogy általános időbeli becslést készítsen a termelési folyamatról.

A műveleti ütemezés a következő adatokat számítja ki a terhelési rendelés esetén:

-   Beállítja a termelési rendelés és az egyes műveletek kezdő és záró dátumát.
-   Erőforrásokat rendel hozzá a műveletekhez.

Több beállítás határozza meg, hogyan történik a termelési ütemezés kiszámítása. Ezeket a beállításokat a **Műveletek ütemezése** lapon határozhatja meg. A következő információk az ütemezési beállításokra vonatkoznak.

## <a name="operations-scheduling"></a>Műveletek ütemezése
### <a name="scheduling-direction"></a>Ütemezési irány

Az ütemezés iránya alapvető jellemző az ütemezési folyamatban. A termelés ütemezhető a dátumokat megelőző időszakra és a dátumokat követő időszakra is, az időzítési és ütemezési követelményeknek megfelelően.

-   **Előre ütemezés**– A termelést minél korábbi indításra ütemezheti. A termelés kezdési dátuma lehet az adott nap, másnap vagy bármilyen megadott jövőbeni dátum. A termelés kezdetét a lehető legkorábbra ütemezi a program, és attól előre számítva a lehető legkorábbi befejezési dátumig veszi tervbe.
-   **Visszafelé ütemezés** – A termelést minél későbbi indításra ütemezheti. Az ütemezés azon a dátumon alapul, amelyen a termelést be kell fejezni, és innen számítja vissza a lehető legkésőbbi időpontot, amikor a termelést a határidőből való kifutás nélkül el lehet indítani.

Az alábbi lehetőségek közül választhat:

-   **A mai dátumtól későbbre** – Ütemezés az aktuális dátumtól. (Az aktuális dátum a rendszer dátuma.)
-   **Előre a tervezett indítástól** – Ütemezés egy korábbi kezdő dátumtól. Ha nincs korábbi ütemezés, az ütemezés iránya az aktuális dátumtól előre van.
-   **A tervezés dátumától előre** – Ütemezés az **Ütemezési dátum** mezőben megadott dátumtól kezdve. Ha nem határoz meg ütemezési dátumot, az ütemezés iránya az aktuális dátumtól előre van.
-   **A szállítási dátumtól visszafelé** – Ütemezés visszafelé a termelési rendeléshez megadott szállítási dátumtól. Ha bejelöli ezt a lehetőséget, de nincs megadva szállítási dátum, akkor a szállítási dátum az aktuális dátum.
-   **Vissza a tervezett befejezéstől** – Ütemezés visszafelé egy korábban kiszámított záró dátumtól. Ha nincs korábbi ütemezés, az aktuális dátum lesz a záró dátum.
-   **A tervezés dátumától visszafelé** – Ütemezés visszafelé az **Ütemezési dátum** mezőben megadott dátumtól kezdve. Ha nem ad meg ütemezési dátumot, a program az aktuális dátumot fogja alkalmazni. A termelési rendelés művelettől visszafelé számolt ütemezési dátumát az utolsó követelményszámításkor számítja ki a rendszer. Ha a termelési rendeléshez nincs megadva dátum, az aktuális rendszerdátum lesz a műveleti dátum.
-   **Visszafelé a határidőügylet dátumától** – Ütemezés a termelési rendeléshez a legutóbbi követelményszámításkor kiszámított határidőügylet dátumától visszafelé. Ha a termelési rendeléshez nincs megadva határidőügylet-dátum, az aktuális rendszerdátum lesz a műveleti dátum.
-   **Utolsó ütemezés szerint** – A program menti a műveletek ütemezéséhez és a feladatütemezéshez kapcsolódóan a kiválasztott ütemezési irányt és dátumot. Ennek köszönhetően választhatja ezt a lehetőséget a következő ütemezéshez. Ha a termelési rendeléshez nincs korábbi ütemezés, akkor az ütemezés az aktuális rendszerdátumtól visszafelé történik..
-   **A holnapi dátumtól későbbre** – Ütemezés a mai dátumot eggyel követő naptól.
-   **Előre az előző feladattól** – Ennek a lehetőségnek csak a feladatütemezésnél van jelentősége. Ha ezt az ütemezési irányt választja a műveletek ütemezéséhez, a termelési rendelés az aktuális dátumtól előre lesz ütemezve. A feladatütemezésben az ütemezés egy feladatra történik, és a rendszer ehhez a feladathoz ütemezi a termelés összes többi feladatát.
-   **Vissza az előző feladattól** – Ennek a lehetőségnek csak a feladatütemezésnél van jelentősége. Ha ezt az irányt választja a műveletek ütemezésére, a tervezett rendeléseket az aktuális dátumtól visszafelé ütemezi a program. A feladatütemezésben az ütemezés egy feladatra történik, és a rendszer ehhez a feladathoz ütemezi a termelés összes többi feladatát.

### <a name="scheduling-date"></a>Ütemezési dátum

Ez a dátum **Az ütemezési dátumtól előre** és **Az ütemezési dátumtól visszafelé** ütemezési irány esetében alkalmazható. Az ütemezés ettől a dátumtól visszafelé, vagy ettől a dátumtól előre történik. A további tudnivalókat lásd az előző, „Ütemezési irány” című fejezetben.

### <a name="recalculate-bom-levels"></a>Anyagjegyzékszintek újraszámítása

Ha bejelöli az **Anyagjegyzékszintek újraszámítása** lehetőséget, a kiválasztott anyagjegyzék (AJ) szintjeit újraszámolja a rendszer a helyes ütemezési sorrend biztosítása érdekében.

## <a name="limitations"></a>Korlátozások
### <a name="finite-capacity"></a>Véges kapacitás

Az ütemezést a termeléshez szükséges erőforrások rendelkezésre állása határozza meg. Ha nincs elég kapacitás, a termelési rendelés elhúzódhat vagy akár le is állhat. Ha már alkalmazta a véges kapacitás lehetőséget a műveletek ütemezéséhez, az erőforrásokra alapozó meglévő kapacitásfoglalások számítanak, és az a kapacitás nem elérhetőként jelenik meg. A termelési rendelést a szükséges erőforrások kapacitásának rendelkezésre állása határozza meg. A Műveletek ütemezése lehetőség a műveletek meghatározott sorrendje segítségével határozza meg a termelési útvonal műveleteinek sorrendjét. A Műveletek ütemezése lehetőség a termelési útvonalon megadott műveletidők alapján foglal le erőforráscsoport-kapacitásokat. Az erőforráscsoportok kapacitása megfelel az erőforráscsoportokban levő összes erőforrás kapacitása összegének.

### <a name="finite-material"></a>Véges anyagmennyiség

Az ütemezés a termeléshez szükséges anyagok rendelkezésre állásától is függ. Az összetevők elégtelen rendelkezésre állása is lassíthatja a termelést. Az ütemezés az anyagok felhasználása alapján is végrehajtható. Adja meg a termeléshez feltétlenül szükséges anyagokat a kevésbé kritikus anyagok helyett. Az ilyen típusú ütemezést véges anyagmennyiséggel történő ütemezésnek is nevezik. Véges anyagok megadásakor a rendszer a termelést a rendelkezésre álló anyagok alapján ütemezi. **Megjegyzés:** Ha egyszerre optimalizálja a kapacitást és az anyagokat, a termelés számítása úgy történik, hogy mindkét megszorításnak megfeleljen. A rendszer figyelembe veszi a kapacitás és az anyagok rendelkezésre állását, a termelési rendelés műveletei nem kezdődnek el mindaddig, amíg mindkettő rendelkezésre nem áll a szükséges időpontban és mennyiségben. Jelölje be ezt a jelölőnégyzetet, ha azt akarja, hogy az ütemezés során a rendszer az anyagokat korlátozott mennyiségűnek tekintse. Ha az anyagok korlátozottak, a rendszer figyelembe veszi az adott időpontra érvényes anyagfedezetet. Másképpen fogalmazva, az ütemezés tekintetbe veszi a cikkek számított határidőit. Az ütemezés lefoglalja a nyersanyagokat, és elvégzi az aktuális termelés alábontását. Ha többször történik ütemezés, akkor csak az első ütemezés végez alábontást és foglalást. Ha megváltoztatja a termelési anyagjegyzéket vagy az útvonalat, a következő ütemezés elvégzi az alábontást. Az alábontás feltételezi, hogy az anyagok ugyanazon a napon szükségesek. Mivel a termelés ütemezése nem az alapütemezés lebontásakor történik, a cikkek rendelkezésre állásának legjobb becslése az aktuális dátum lesz. Az alábontás ezután ellenőrzi, hogy a cikkek valóban rendelkezésre állnak-e. Ha a cikkek rendelkezésre állnak, lehetséges a termelés követelményeinek kielégítése. Ha a cikkek az aktuális dátumig nem állnak rendelkezésre, akkor egy tervezett rendelés, majd ehhez egy eltolt kiválasztás készül. Ha a tervezett rendeléshez beállítja az automatikus megerősítést, akkor automatikusan megerősítődik a beszerzéshez vagy termeléshez tartozó tervezett rendelés. A rendszer a termelés állapotát automatikusan a **Fedezeti csoportok** párbeszédpanel **Kért termelési állapot** mezőjében megadott állapotra módosítja. Ha törli a jelet a jelölőnégyzetből, az anyagok mindig rendelkezésre állónak számítanak. Ennek megfelelően az ütemezés nem veszi figyelembe, hogy az anyagok az igényléskor rendelkezésre állnak-e.

### <a name="finite-property"></a>Véges tulajdonság

Jelölje be ezt a jelölőnégyzetet, ha azt akarja, hogy a feladatütemezés figyelje a tulajdonságokra vonatkozó követelményeket.

### <a name="keep-production-unit"></a>Termelési egység megtartása

Adja meg, hogy az ütemezési motor csak a termelési egységen már megadott erőforrásokat ütemezze.

### <a name="keep-warehouse-from-resource"></a>Raktár kezdeti erőforrásának megtartása

Megadhatja, hogy az ütemezési motor csak olyan erőforrásokat ütemezzen, amelyek az erőforráson megadott bemeneti raktárhoz tartoznak.

## <a name="references"></a>Hivatkozások
### <a name="schedule-references"></a>Hivatkozások ütemezése

Amikor a hivatkozások a termelési rendelésektől függnek, ezeket altermelésnek is nevezik. Az altermelések a termelési rendelés beütemezett részeként is ütemezhetők. Jelölje be ezt a jelölőnégyzetet, ha az altermelések ütemezésének alapjául a fő termelés ütemezése szolgál. A fő termeléshez képest az erre épülő termelések ütemezése későbbre, a mögöttes termeléseké pedig visszafelé történik. A termelési rendelés hivatkozásait a **Termelési rendelés** lap **Hivatkozási szint** mezőjében tekintheti meg.

### <a name="synchronize-references"></a>Hivatkozások szinkronizálása

Szinkronizálhatja a hivatkozásokat a termeléssel. Ha ez a beállítás van kiválasztva, akkor a termelési ütemezés módosításakor az altermelések dátuma is megváltozik és ehhez igazodik. Ha a termelési rendelésnek egy vagy több altermelése van, érdemes az altermelések és a fő termelés együttes ütemezése. Ilyenkor a fő termelés nem indítható el mindaddig, amíg a kapcsolódó altermelések be nem fejeződnek. Ezért jelölje be ezt a jelölőnégyzetet, ha az altermelések ütemezésének alapjául a kiválasztott termelés kezdési és befejezési ideje szolgál. Ezt a jelölőnégyzet csak akkor választhatja ki, ha a **Hivatkozások ütemezése** jelölőnégyzet is be van jelölve.

## <a name="cancellation"></a>Érvénytelenítés
### <a name="cancel-queue-time"></a>Várakozási idő érvénytelenítése

A várakozási idő ütemezésből történő kizárásához jelölje be ezt a jelölőnégyzetet.

### <a name="cancel-setup"></a>Beállítás érvénytelenítése

A beállítási idő ütemezésből történő kizárásához jelölje be ezt a jelölőnégyzetet.

### <a name="cancel-process"></a>Folyamat érvénytelenítése

A futtatási idő ütemezésből történő kizárásához jelölje be ezt a jelölőnégyzetet.

### <a name="cancel-overlap"></a>Átfedés érvénytelenítése

Az átfedési idő ütemezésből történő kizárásához jelölje be ezt a jelölőnégyzetet.

### <a name="cancel-transport"></a>Szállítás érvénytelenítése

A szállítási idő ütemezésből történő kizárásához jelölje be ezt a jelölőnégyzetet.

## <a name="set-default"></a>Alapértelmezett
A jelenlegi értékeket alapértelmezett értékekként mentheti. Két lehetőség létezik:

-   Beállítás saját alapértelmezettként
-   Beállítás alapértelmezett mindenkinek


<a name="additional-resources"></a>További erőforrások
--------

[Műveletek ütemezése](operations-scheduling.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]