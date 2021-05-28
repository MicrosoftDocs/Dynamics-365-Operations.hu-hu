---
title: Hullám létrehozása és feldolgozása
description: Ez a témakör azt írja le, hogyan lehet létrehozni, feldolgozni és felszabadítani terhelési, szállítási, termelési vagy kanban megrendeléshez tartozó kitárolási munkát.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, WHSParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage, WHSProdWaveTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 4bf47b15b668a37f12edb3dbb842d19655fac97a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019027"
---
# <a name="wave-creation-and-processing"></a>Hullám létrehozása és feldolgozása

[!include [banner](../includes/banner.md)]

Ez a témakör azt írja le, hogyan lehet létrehozni, feldolgozni és felszabadítani terhelési, szállítási, termelési vagy kanban megrendeléshez tartozó kitárolási munkát. A hullámok a következő típusú rendelésekhez hozhatók létre:

- **Értékesítési rendelések** – szállítási hullámok használata értékesítési rendelésekből származó sorok hozzáadásához. Amikor egy értékesítési rendelést kiad a raktárba, az értékesítési rendelés sorait szerepeltetheti a hullámban.
- **Termelési rendelések** – termelési hullámok használata a termékhez tartozó darabjegyzékből (DBJ) származó sorok hozzáadásához.
- **Kanban rendelések** – a kanban hullámok a kanban rendelésből származó kitárolási lista sorait tartalmazzák.

Az értékesítési és a kanban rendelésekhez, a készletet a rendelés raktárból történő kiadása előtt le kell foglalni. Ellenkező esetben a cikkek vagy a felosztási sorok nem dolgozhatók fel a hullámban. A termelési rendelések azonban egy kicsit rugalmasabbak. Termelési rendelések esetén az alábbi lehetőségek közül választhat:

- Minden anyagot le kell foglalni, mielőtt egy megrendelést ki lehet adni a raktárba.
- Engedje, hogy a termelési megrendeléseket akkor is ki lehessen adni a raktárból, ha nem foglalható le minden anyag. Ha ezt a lehetőséget választja, akkor manuálisan meg kell ismételnie a raktárba kiadás folyamatát, amikor további anyagok rendelkezésre állnak. Ez például hasznos, ha a termelés megkezdéséhez szükséges anyagok rendelkezésére állnak, a további anyagok beérkezésére pedig tud várni.

Megadhatja, hogy alapértelmezett módon melyik termelésirendelés-beállítást használja a rendszer a **Anyagfoglalás követelményei** mezőben a **Termelés vezérési paraméterei** oldalon. Viszont egy adott termelési rendelés beállítását szükség szerint módosíthatja. További információkért lásd: [Raktár paraméterei hullámfeldolgozáshoz](wave-warehouse-parameters.md).

## <a name="create-and-process-a-wave"></a>Hullám létrehozása és feldolgozása

A következő diagram megjeleníti a folyamatot azzal kapcsolatban, hogy a szállítási hullámokat hogyan hozzák létre, dolgozzák fel és adják ki. A számok a szakaszban később tárgyalt szakaszoknak felelnek meg.

![A hullám létrehozásának folyamata](media/wave-processing-diagram.png "A hullám létrehozásának folyamata")

### <a name="prerequisites"></a>Előfeltételek

A kezdés előtt egy hullámsablonnak elérhetőnek kell lennie a létrehozni kívánt hullámtípushoz (szállítás, termelés vagy kanban). A hullámsablon számos beállítást hoz létre a hullám létrehozásához és feldolgozásához, beleértve azt is, hogy mely lépéseket kell manuálisan elvégezni, és melyeket automatikusan. További tájékoztatás: [Hullámsablonok](wave-templates.md).

### <a name="create-a-wave"></a>Hullám létrehozása

#### <a name="automatically-create-waves-based-on-warehouse-and-order-type"></a>Hullámok automatikus létrehozása a raktár és a rendelés típusa alapján

Hullámok automatikus létrehozásához állítsa be az egyes vonatkozó rendeléstípusra és raktárra vonatkozó [Hullámsablonokat](wave-templates.md). Győződjön meg arról, hogy minden sablon esetén a **Hullámlétrehozás automatizálása** beállítás értéke *Igen*.

#### <a name="manually-create-waves"></a>Hullámok manuális létrehozása

Hullám manuális létrehozásához kövesse az alábbi lépéseket:

1. Győződjön meg róla, hogy a [Hullámsablonok](wave-templates.md) beállítása miatt nem hoz létre automatikusan egy hullámot a raktárhoz és a rendeléstípushoz, ahol ezt manuálisan szeretné végrehajtani.
1. A létrehozandó hullám típusától függően, tegye a következők valamelyikét:

    - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Szállítmányhullámok** \> **Összes hullámok** menübe. A műveleti ablaktáblán válassza a **Hullám** lehetőséget.
    - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Termelési hullámok** \> **Összes termelési hullám** menübe. A műveleti ablaktáblán válassza a **Termelési hullám** lehetőséget.
    - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Kanbanhullámok** \> **Összes kanbanhullám** menübe. A műveleti ablaktáblán válassza a **Hullám létrehozása** lehetőséget.

1. A **Leírás** mezőben adja meg a hullám rövid leírását. Ennek érdemes utalnia a hullámban feldolgozott folyamatra.

1. A **Hullámsablon neve** mezőben válassza ki a hullámtípus létrehozásához használandó hullámsablont. A hullámsablon tartalmazza azokat a hullámmódszereket, amelyek végre fogják hajtani a műveleteket, például a hullámban végzett munka létrehozását. A szállítási hullám sablonja tartalmazhat például rakományokat létrehozó és sorokat hullámokba osztó módszereket, feltöltést, de akár kitárolási munkát is létrehozhat a hullámban.

1. Ha a hullám további lekérdezési feltételeként hullámattribútumokat kíván használni, válassza ki az attribútumokat a **Hullámattribútumok** mezőben.

### <a name="specify-what-to-include-in-a-wave"></a>Adja meg, mi szerepeljen a hullámban

A hullám létrehozása után készen áll arra, hogy tartalmat adjon hozzá.

> [!NOTE]
> Szükség esetén sorokat adhat hozzá egy hullámhoz, még akkor is, ha az már feldolgozásra került, amíg még nem adták ki.

#### <a name="automatically-specify-what-to-include-in-a-wave"></a>Automatikusan adja meg, mi szerepeljen a hullámban

Hullámok automatikus létrehozásához állítsa be az egyes vonatkozó rendeléstípusra és raktárra vonatkozó [Hullámsablonokat](wave-templates.md). Győződjön meg arról, hogy minden sablon esetén a **Hullámlétrehozás automatizálása** beállítás értéke *Igen*. Másik lehetőségként a sablon automatikusan hozzárendelhet sorokat bármely minősített nyitott hullámhoz, ha a **Hozzárendelés nyitott hullámokhoz** beállítás értéke *Igen*.

#### <a name="manually-specify-what-to-include-in-a-wave"></a>Manuálisan adja meg, mi szerepeljen a hullámban

Ha egy hullám létrejött, de még nem adták ki, manuálisan megadhatja, hogy mit tartalmazzon. Sorok hozzáadása egy hullámhoz manuálisan:

1. Attól függően, hogy milyen típusú hullámhoz szeretne sorokat adni, tegye a következők egyikét:

    - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Szállítmányhullámok** \> **Összes hullámok** menübe. A műveleti ablaktáblán válassza a **Hullám** lehetőséget.
    - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Termelési hullámok** \> **Összes termelési hullám** menübe. A műveleti ablaktáblán válassza a **Termelési hullám** lehetőséget.
    - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Kanbanhullámok** \> **Összes kanbanhullám** menübe. A műveleti ablaktáblán válassza a **Hullám létrehozása** lehetőséget.

1. Válassza ki a hullámot. A Műveleti ablak fülön válassza a következő lehetőségek valamelyikét:

      - **Szállítmányok karbantartása**
      - **Termelések karbantartása**
      - **Kanbanfeladat kitárolási listájának karbantartása**

1. Az ablak felső részében válassza ki azt a sort, amelyet hozzá szeretne adni a hullámhoz, majd válassza a **Hozzáadás hullámhoz** lehetőséget. A sor át fog kerülni a **Hullámsorok** gyorslapra.

    Mindegyik sorra ismételje meg ezt a lépést. Az összes sor hozzáadásához válassza az **Összes hozzáadása** lehetőséget.

    > [!TIP]
    > Gyorsan megtalálhat egy adott rendelést a szállítmányhullámokhoz, ha egyéni szűrőt választ a **Hullámszűrőkód** mezőben. A hullámszűrő kódok, amelyeket a **Hullámszűrők** űrlapon tud létrehozni, a szállítmány lekérdezési feltételeit tartalmazzák. Termelési hullámok vagy kanbanhullámok esetében nem érhető el a mező.
    > A **Hullámban** oszlopban lévő zöld pipa jelzi, hogy a szállítmányt hozzáadta a hullámhoz.

### <a name="process-the-wave-to-create-the-picking-work"></a>Hullám feldolgozása kitárolási munka létrehozásához

Miután létrehozott egy hullámot, és tartalmazza az összes szükséges sort, készen áll a feldolgozásra a megfelelő kitárolási munka létrehozásához.

#### <a name="automatically-process-a-wave"></a>Hullám automatikus feldolgozása

A hullám automatikus feldolgozásához állítsa be a megfelelő [Hullámsablonokat](wave-templates.md) a szükséges automatikus feldolgozási lehetőségekkel.

#### <a name="manually-process-a-wave"></a>Hullám manuális feldolgozása

Csak akkor dolgozhat fel egy hullámot, amikor a **Hullámállapot** *Létrehozva*. A hullám feldolgozása után a **Hullámállapot** *Várakoztatva* állapotra módosul.

Egy olyan hullám manuális feldolgozásához, amely az összes kötelező tartalommal rendelkezik, kövesse ezeket a lépéseket:

1. A feldolgozandó hullám típusától függően, tegye a következők egyikét:

    - Válassza a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Szállítmányhullámok** \> **Összes hullámok** menüpontot. A műveleti ablaktáblán válassza a **Hullám** lehetőséget.
    - Válassza a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Termelési hullámok** \> **Összes termelési hullám** menüpontot. A műveleti ablaktáblán válassza a **Termelési hullám** lehetőséget.
    - Válassza a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Kanbanhullámok** \> **Összes kanbanhullám** menüpontot. A műveleti ablaktáblán válassza a **Hullám létrehozása** lehetőséget.

1. Válassza ki a feldolgozandó hullámot. A Művelet ablaktáblán válassza ki a **Folyamat** elemet.

### <a name="release-the-wave-to-the-warehouse-to-start-picking-and-packing"></a>A kitárolás és csomagolás elindításához adja ki a hullámot a raktárba

Kiadás előtt fel kell dolgoznia a hullámot. Miután kiadta a hullámot, a kitárolási munka elérhető a raktárban. Kiadás után megszakíthatja a hullámot, hogy új sorokat adjon hozzá, de a sorokat már nem módosíthatja.

#### <a name="automatically-release-a-wave"></a>Hullám automatikus kiadása

A hullám automatikus feldolgozásához állítsa be a megfelelő [Hullámsablonokat](wave-templates.md) a szükséges automatikus feldolgozási lehetőségekkel.

#### <a name="manually-release-a-wave"></a>Hullám manuális kiadása

Egy hullám manuális kiadásához kövesse az alábbi lépéseket:

1. A kiadni kívánt hullám típusától függően, tegye a következők egyikét:

      - Válassza a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Szállítmányhullámok** \> **Összes hullámok** menüpontot. A műveleti ablaktáblán válassza a **Hullám** lehetőséget.
      - Válassza a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Termelési hullámok** \> **Összes termelési hullám** menüpontot. A műveleti ablaktáblán válassza a **Termelési hullám** lehetőséget.
      - Válassza a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Kanbanhullámok** \> **Összes kanbanhullám** menüpontot. A műveleti ablaktáblán válassza a **Hullám létrehozása** lehetőséget.

1. Válassza ki a kiadandó hullámot. A műveleti ablaktáblán válassza a **Hullám kiadása** lehetőséget.

## <a name="containerize-a-wave"></a>Hullám tárolóra bontása

Az automatikus tárolóra bontási folyamat a hullám feldolgozásakor létrehozza a tárolókat és a kitárolási munkát. A beállítással kapcsolatos részleteket a [Tárolóra bontás](wave-containerization.md) részben találja.

## <a name="work-with-the-scheduled-work-creation"></a>Az ütemezett munkalétrehozás használata

Ha a *Munka létrehozásának ütemezése* funkció engedélyezve van, akkor a hullámfeldolgozás tervezett munkát hoz létre, amelyet végül az új munka-létrehozási folyamat fog alkalmazni. A munka létrehozása során a rendszer letiltja a munkát az *egész szervezetre kiterjedő munkazárolási* funkcióval. További információk [Munka létrehozásának ütemezése hullám közben](configure-wave-schedule-work-creation.md).

Az alábbi folyamatábra bemutatja, hogyan jön létre tervezett munka a hullámfeldolgozás során.

![Munka létrehozásának ütemezése](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Tervezett munka

A **Tervezett munka részletei** lap (**Raktárkezelés \> Munka \> Tervezett munka részletei**) a hullámfeldolgozás során kezdetben létrehozott tervezett munka adatait jeleníti meg. A következő **Folyamatállapot** értékek érhetők el:

- **Várakozás** – a tervezett munka várakozik a munka létrehozására.
- **Kész** – a tervezett munkát használták munka létrehozására.
- **Sikertelen** – a hullámfeldolgozás nem sikerült. A tervezett munka **Sikertelen** állapotban lehet tényleges munkával vagy anélkül. Ha a tényleges munkalétrehozási folyamat sikertelen, a tényleges munka *Visszavonva* állapotú marad.

### <a name="batch-job-for-the-work-creation-process"></a>Kötegelt feladat a munkalétrehozási folyamathoz

A hullámok feldolgozásához szükséges kötegelt feladatok megtekintéséhez jelölje ki a **Kötegelt feladatok** lehetőséget a **Minden hullám** oldal műveletablakában.

Innen megtekintheti a kötegelt feladatok minden egyes adatát a kötegeltfeladat-azonosítókhoz.

## <a name="cancel-a-wave"></a>A hullám megszakítása

Szükség esetén megszakíthat egy feldolgozott hullámot. Egy létrehozott hullám és kitárolási munka megszakításához kövesse az alábbi lépéseket:

1. A megszakítani kívánt hullám típusától függően, tegye a következők egyikét:

      - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Szállítmányhullámok** \> **Összes hullámok** menübe.
      - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Termelési hullámok** \> **Összes termelési hullám** menübe.
      - Ugorjon a **Raktárkezelés** \> **Gyakori** \> **Hullámok** \> **Kanbanhullámok** \> **Összes kanbanhullám** menübe.

1. Válassza ki a megszakítandó hullámot. A Művelet panelen a **Munka** lapon válassza a **Megszakítás** menüpontot.

## <a name="review-wave-batch-job-details"></a>Hullám kötegelt feladatához tartozó részletek áttekintése

A **Hullám kötegelt feladatához tartozó részletek** oldalon vizsgálja meg a bármely hullámhoz társított kötegelt feladatokat és kapcsolódó feladatokat. Ez különösen akkor hasznos, ha egy sikertelen hullám hibaelhárítását végzi. A funkció nélkül általánosságban csak rendszergazdáknak van hozzáférésük a kötegelt feladat részleteihez. A **Hullám kötegelt feladatához tartozó részletek** oldal elérhetővé tehető nem rendszergazda felhasználók számára, és írásvédett megtekintési jogosultságot biztosít a kötegelt feladatokhoz és kapcsolódó feladatokhoz.

### <a name="enable-the-wave-batch-job-details-page"></a>A Hullám kötegelt feladatához tartozó részletek oldal engedélyezése

Ha a rendszer még nem tartalmazza a **Hullám kötegelt feladatához tartozó részletek** oldalt, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalra, és kapcsolja be a *Hullám kötegelt feladatához tartozó részletek* funkciót.

### <a name="use-the-wave-batch-job-details-page"></a>A Hullám kötegelt feladatához tartozó részletek oldal használata

A **Hullám kötegelt feladatához tartozó részletek** oldal kombinálja a kötegelt feladatokat és a kötegelt feladathoz tartozó feladatokat, így megtekintheti az összes hullámlépést anélkül, hogy oda-vissza kellene lépnie az egyetlen kötegelt feladat és a kötegelt feladatok listája között. Az oldal ezenkívül hozzáférést biztosít a kötegnaplóhoz, és ha rendelkezik a megfelelő engedélyekkel, tartalmaz egy hivatkozást a **Kötegelt feladatok** oldalhoz.

A lap megnyitásához jelöljön ki egy hullámot több különböző hullámoldal közül, majd válassza a **Hullám kötegelt feladatához tartozó részletek** elemet a Műveleti ablaktáblán.

## <a name="review-load-validation-and-error-messages"></a>Ellenőrzési és hibaüzenetek betöltésének ellenőrzése

A hullámfeldolgozás során a rendszer ellenőrzi és megjeleníti a hullám minden egyes rakománysorának állapotát. Ha nem történik figyelmeztetés, akkor továbblép a következő hullámlépésre. Ha figyelmeztetések történnek, az a következő hibát mutatja, miután befejezte a teljes hullám ellenőrzését:

> Érvénytelen rakománysorokat észlelt a rendszer a hullámban. Távolítsa el az érvénytelen rakománysorokat.

Ezután áttekintheti a hullám egyes rakománysorainak végleges állapotát, és kijavíthatja az összes figyelmeztetést, mielőtt újra próbálkozik. Ez lehetővé teszi, hogy a hullám újrafeldolgozása előtt egyszerre foglalkozzon az összes figyelmeztetéssel. (A korábbi kiadásokban a rendszer az első figyelmeztetés után leállította a hullám feldolgozását, így egyszerre csak egy figyelmeztetést tudott kijavítani.)

Az, ahogy a rendszer megjeleníti a hullámfeldolgozási állapot üzeneteit, attól függ, hogy hogyan állította be a **Hullámfeldolgozási előzmények naplójának létrehozása** beállítást a **Raktárkezelési paraméterek** oldalon.

- Ha a **Hullámfeldolgozási előzmények naplójának létrehozása** beállítás értéke *Nem*, a rakománysor állapotüzenetei megjelennek az **Információs naplóban**.
- Ha a **Hullámfeldolgozási előzmények naplójának létrehozása** beállítás értéke *Igen*, a rakománysor állapotüzenetei megjelennek a **Hullámfeldolgozási előzmények naplója** oldalon. A napló megtekintéséhez lépjen a **Raktárkezelés \> Kimenő hullámok \> Hullámfeldolgozási előzmények naplója** részre.

## <a name="additional-resources"></a>További erőforrások

- [A hullámfeldolgozás konfigurálása – példa](tasks/configure-wave-processing.md)
- [Hullámsablonok](wave-templates.md)
- [Tárolóra bontás](wave-containerization.md)