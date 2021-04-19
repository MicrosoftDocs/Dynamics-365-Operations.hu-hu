---
title: Hullámsablonok
description: Ez a témakör leírja, hogyan állíthatja be azokat a feltételeket, amelyek meghatározzák, hogy egy hullám manuálisan vagy automatikusan lesz-e feldolgozva, és hogy milyen munka jön létre a raktár részére a hullám feldolgozásakor.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b02283a6e0a4ef0d61be8b66f82be8c125028cb0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813627"
---
# <a name="wave-templates"></a>Hullámsablonok

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan állíthatja be azokat a feltételeket, amelyek meghatározzák, hogy egy hullám manuálisan vagy automatikusan lesz-e feldolgozva, és hogy milyen munka jön létre a raktár részére a hullám feldolgozásakor. A feltételeket meghatározásához létrehozhat hullámsablonok illetve olyan lekérdezéseket, amelyek a hullámot értékesítési rendelés, termelési rendelés vagy kanbanok kiadott soraihoz rendelik.

## <a name="settings-for-wave-templates"></a>Hullámsablonok beállításai

Hullámsablon beállításánál az alábbiakat kell megadnia:

- A **Telephely** és a **Raktár**, amelyhez a sablon munkát hoz létre.
- Az a sorrend, amelyben a sablonok kiértékelése történik. A sorrendet, amelyben a sablonok az értékesítési rendelés, a termelési rendelés és a kanbanok kiadott sorraihoz kapcsolódnak. Amikor egy sort kiadnak, a rendszer alkalmazza az első hullámsablont, amelyhez a sor megfelel a feltételeknek. Minél szélesebbek a feltételek, annál valószínűbb, hogy egy sor megfelel a kritériumoknak, ezért a legkonkrétabb feltételekkel rendelkező sablonokat helyezze a lista elejére. A Műveleti panelen található **Mozgatás felfelé** és **Mozgatás lefelé** gombokkal igény szerint átrendezheti a sablonokat a listában.
- Az egyes sablonok által végzett műveletek. A sablon által létrehozott műveleteket végrehajtják a hullám **Metódusok**: ide tartozik a munkák létrehozása és felosztása a különböző hullámsablontípusok között.
- A hullámattribútumok (szűrők), amelyeket alkalmazni kell a használandó hullámsablonra.

> [!NOTE]
> Szükség esetén egy fejlesztő további módszereket is létrehozhat. A metódusok teljes listáját megtekintheti a **Hullámfeldolgozási metódusok** oldalon.

Egyes beállítások a hullámfeldolgozáson stratégiai döntésekit képviselik, a következőképpen:

- Ha a sablont értékesítési rendelések és átmozgatási rendelések cikkeinek szállításához, illetve cikkek termelési rendelések vagy kanbanok céljára való mozgatásához használják.
- Ha egy hullám manuálisan vagy automatikusan kerül feldolgozásra, az alábbiak szerint:

  - **Manuális feldolgozás** – A sor hozzáadódik egy hullámhoz és a készlet lefoglalásra kerül, ugyanakkor rá kell kattintania a **Feldolgozás** elemre az **Összes hullám** listaoldalon ahhoz, hogy a rendelés kitárolási munkáját létrehozza.
  - **Automatikus feldolgozás** – A hullámfeldolgozás egészét vagy részét is automatizálhatja. Ha teljesen automatizálja a hullám feldolgozását, olyan hullám jön létre, amely egy értékesítési rendelés, termelési rendelés vagy kanban létrehozásakor tartalmazza az értékesítési rendelés, termelési rendelés vagy kanban sorát. A cikkek eltűnnek a rendelkezésre álló készletből, és létrejön a kitárolási munka. Ha csak részben automatizálja a hullámfeldolgozást, akkor megadhatja azokat a konkrét értékeket, amelyek elindítják a hullám feldolgozását. Így például megadhatja azt a maximális szállítási súlyt, amely kiváltja a hullámfeldolgozást, amikor a hullám sorainak összsúlya eléri az értéket.

- Amikor nyitott hullámhoz rendel hozzá szállítmányokat. Például ha megígérte vevőjének, hogy a dél előtt leadott rendeléseket 24 órán belül kiszállítja, akkor a hullámsablonban beállíthatja, hogy dél előtt a rendszer automatikusan nyitott hullámhoz rendelje hozzá a rendelési sorokat. A hullám pedig ebben az időpontban automatikusan feldolgozásra kerül.

A hullám feldolgozásakor létrejövő kitárolási munka az adott raktárhoz meghatározott munkasablonon és helyutasításon alapszik. A munkasablon megadja, hogyan jön létre a kitárolási munka, a helyutasítás pedig meghatározza a kitárolási és betárolási helyeket.

## <a name="create-a-wave-template"></a>Hullámsablon létrehozása

Hullámsablon beállításához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Hullámok** \> **Hullámsablonok** pontra.
1. Válassza az **Új** lehetőséget egy új hullámsablon létrehozásához.
1. A **Hullámsablon típusa** mezőben jelöljön ki egyet a következő lehetőségek közül:

    - *Szállítás* – A hullámsablon értékesítési rendelések és átmozgatási rendelések szállításaihoz használható.
    - *Termelési rendelések* – A hullámsablon termelési rendelésekhez való mozgatásokhoz használható.
    - *Kanban* – A hullámsablon kanbanrendelésekhez való mozgatásokhoz használható.

1. A **Hullámsablon neve** és a **Hullámsablon leírása** mezőkben adja meg a hullámsablon nevét és leírását.

    > [!NOTE]
    > Ha egynél több sablont hoz létre egy raktárhoz, akkor a **Hullámsablon sorrendje** mező száma azt a sorrendet, hogy melyik sablont alkalmazza a rendszer a feltételek teljesülése esetén. A sablonok sorrendjének átrendezéséhez válassza a **Mozgatás felfelé** vagy **Mozgatás lefelé** lehetőséget.

1. A **Telephely** és a **Raktár** mezőkben rendre adja meg a telephelyet és a raktárat, amelyekhez a hullámsablon hullámokat és kitárolási munkát hoz létre.
1. Ha automatizálni szeretné a hullámfeldolgozást, szükség szerint adja meg a következő beállításokat:

    - **Hullámlétrehozás automatizálása** – Állítsa *Igen* értékre hogy a rendszer automatikusan hozzon létre hullámot, amikor egy értékesítési rendelés, termelési rendelés vagy kanban kiadásra kerül a raktárba.
    - **Hozzárendelés nyitott hullámokhoz** – Állítsa ezt *Igen* értékre, ha a sorok kiadásákor a rendszer automatikusan hozzárendelje a sorokat egy nyitott hullámhoz. A rendszer a hullámsablon lekérdezésszűrője alapján rendeli hozzá a sorokat a hullámokhoz.
    - **Hullám feldolgozása raktárba való kiadáskor** – Állítsa ezt *Igen* értékre, ha automatikusan fel szeretné dolgozni a hullámot, és létre szeretné hozni a munkát, amikor a sort kiadják a raktárba.
    - **Hullám automatikus feldolgozása küszöbértéken** – Állítsa ezt *Igen* értékre, hogy a rendszer automatikusan feldolgozza a hullámot, amikor annak értékei elérik a súlyra, szállítmányra vagy sorokra vonatkozóan a **Hullámküszöbértékek** mezőcsoportban beállított küszöbértékeket. Ez a beállítás csak akkor aktív, ha a *Szállítás* beállítás van kiválasztva a **Hullámsablon típusa** mezőben.
    - **Hullámkiadás automatizálása** – Állítsa ezt *Igen* értékre, hogy automatikusan kiadja a hullámot. A rendszer létrehozza a kitárolási munkát, ami hozzáférhetővé vélik a mobileszközökön.
    - **Feltöltési munka kiadásának automatizálása** – Állítsa ezt a lehetőséget *Igen* értékre, hogy a rendszer automatiksuan létrehozza és kiadja az igényalapú feltöltési munkát. Hozzá kell adnia az újratöltési hullámmódszert a hullámsablonhoz, majd létrehozni az újratöltési sablont a *Hullámigény* típussal. **Feltöltési sablonok** lapjának feltöltési sablon beállítása. Ehhez hozzá kell adnia az újratöltés módszert a hullámsablonhoz.
    - **Hullámfeldolgozás folytatása, ha a munkalétrehozás sikertelen** – Ha *Igen* értékre van állítva, akkor a rendszer üres helyet fog használni, ha nem tud készletet foglalni a helyutasítás által javasolt helyen (például, mert a készlet már nem érhető el). Ha a beállítás *Nem*, a hullám meghiúsul, ha a rendszer nem tudja lefoglalni a készletet.

1. Szükség szerint állítsa be a **Hullámküszöbértékek** mezőcsoportot:
    - **Hullámsúly-küszöbérték** - Adja meg azt a maximális súlyt, amit egy hullám tartalmazhat.
    - **Szállítási küszöbérték** – Adja meg a hullámban szereplő szállítmányok maximális számát.
    - **Sorküszöbérték** – Adja meg a hullámban szereplő sorok maximális számát.

1. Az **Alapértelmezett értékek** mezőcsoportban válassza ki, melyik hullámattribútumot kívánja használni a hullámsablonban kiegészítő feltételként. A hullámattribútumokat további feltételek, például konkrét vevő nevének hullámsablonhoz való hozzárendelésére használhatja. Ezeket az attribútumtípusokat az **Attribútumtípusok** oldalon hozhatja létre. 

1. Állítsa be a **Hullámértesítési házirendet** arra a házirendre, amelyet az adott sablont használó hullámokhoz kapcsolódó értesítések létrehozásához használni szeretne. A hullámértesítési házirendet például a [Hullámvégrehajtási értesítésekben](wave-execution-notifications.md) találja meg.

1. A **Metódusok** gyorslapon a **Kiválasztott metódusok** panel felsorolja a kiválasztott hullámsablonhoz tartozó metódusokat. A sablon által létrehozott műveleteket végrehajtó hullámmetódusokat: ide tartozik a munkák létrehozása és felosztása a különböző hullámsablontípusok között. Ezeket a műveleteket hullámlépésnek is nevezik. A hullámmetódusok minden hullámsablontípushoz előre vannak definiálva. Az előre meghatározott hullámmódszerek nem távolíthatók el, azonban a módszerek sorrendje megváltoztatható, és további módszerek is hozzáadhatók. Így például ha szállításhoz hoz létre egy hullámsablont, ahhoz újratöltési és tárolóra bontási módszereket is hozzáadhat. A hullámalapú tárolóra bontás hozzáadható egy hullámmódszer-sorozathoz, hogy így meghatározza a hullámsablon által feldolgozott sorok tárolóra bontását. Kiegészítő módszer hozzáadásához kövesse az alábbi lépéseket:

    - A **Fennmaradó metódusok** panelen válasszon ki egy metódust, majd válassza a **Bal** nyilat, hogy hozzáadja azt a **Kiválasztott metódusok** ablaktáblához.
    - A sorrend módosításához válasszon ki egy módszert, majd válassza a **Fel** vagy a **Le** nyilat.

    > [!NOTE]
    > Egy módszer hozzáadásakor az automatikusan a megfelelő helyen jelenik meg a lépések sorrendjében.

1. Ha be szeretné állítani azt a lekérdezést, amely a kiadott sorokat egy megfelelő hullámhoz fogja hozzárendelni, válassza a **Lekérdezés szerkesztése** lehetőséget a műveletpanelen.
1. A hullámsablon beállításainak érvényességét ellenőrizheti, ha a **Sablon ellenőrzése** elemre kattint.
