---
title: "A Feladatrögzítő nemrégiben a szerkesztési funkciók"
description: "Ha Feladatrögzítő segítségével feladat segédvonalak létrehozása, szerkesztheti a fájlokat több hatékonyan a funkció használata a wiki ismertetett."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core
ms.custom: 266464
ms.assetid: b4640e67-4b92-4855-8041-1bfc71aadc47
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: c4f9ac515eab6ed8b194fc8985f6d3fae40ced38
ms.lasthandoff: 03/31/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>A Feladatrögzítő nemrégiben a szerkesztési funkciók

Ha Feladatrögzítő segítségével feladat segédvonalak létrehozása, szerkesztheti a fájlokat több hatékonyan a funkció használata a wiki ismertetett.

Ezek a szolgáltatások érhetők el a **beállítások &gt;Feladatrögzítő &gt;felvétel szerkesztés** menü.

-   Helyezze be a lépéseket a teljes fájl ismételt rögzítése nélkül.
-   Szerelési tevékenység alatt lépések áthelyezése nélkül az egész fájlt újra rögzít.
-   Felvétel név és leírás mezők összecsukása.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Lépések nélkül rerecording a teljes fájl beszúrása
Lépés bárhol most hozzáadása a tevékenység útmutatója lejátszás és felvétel a teljes fájl nélkül.

1.  Jelölje be a lépés után szeretné beszúrni az új lépés. Ellenőrizze, hogy a lépés ki van emelve.

Ahhoz, hogy egy lépés beszúrása Feladatrögzítő nyissa meg a megfelelő oldalra kell rendelkeznünk. A megfelelő oldalra kerül a lapot az új lépés következik be. A Feladatrögzítő rendelkezik olyan mechanizmus, amely azt határozza meg, mi az aktív lap, és a szolgáltatást letiltja, ha nincs megnyitva a megfelelő oldalra. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Ha a megfelelő oldalon **beszúrása lépés** elérhetővé válik.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Kattintson a **beszúrása lépés**.

Amikor rákattint **beszúrása lépés**, Feladatrögzítő rekord üzemmódra vált. A felhasználói felület keresetről most kell elszámolni, és helyben hozzáadott lépések.

3. Kattintson a **le**.

A folyamat tetszőleges számú lépéseket felvételének és áthelyezésének (lásd az alábbi altevékenységeknél) igény szerint tetszőleges számú altevékenységek megismételheti.

4. Ha befejezte a feladat útmutató szerkesztésével, kattintson a **végzett Szerkesztés**, majd válassza a beállítások mentése vagy közzététele a feladat útmutató.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Lépések szerint altevékenységévé áthelyezése nélkül a teljes fájl rerecording
Lejátszás és felvétel a teljes fájl nélkül áthelyezheti egy altevékenységek részben leírtakat. Ha egy meglévő blokk lépések csoportosítani szeretné az altevékenységek lépés és az altevékenységek befejezési lépés is áthelyezhetők.

1.  Jelöljük ki a lépés, amely az áthelyezni kívánt altevékenységek lépés. Győződjön meg arról, hogy a lépés ki van emelve.
2.  Kattintson a három pont, majd **lépés lépés után**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Jelöljük ki a lépés altevékenységek lépés, és a cselekmény, vagy az altevékenységek lépés után áthelyezi. A Feladatrögzítő helyezi a lépés.

4. Az altevékenységek befejezési lépés áthelyezése, jelölje ki azt, kattintson a Kihagyás gombra, kattintson a **lépés lépés után**, és válassza ki a lépés után a záró altevékenységek lépést kell szeretné.

Ha azt szeretné, hogy az első lépés a feladat útmutató egy altevékenységek belül hozzon létre egy, a második lépcsõben altevékenységek lépést, és az első lépésben helyezhet. Hozzáadása, vagy helyezze át a lépéseket és altevékenységek szükség szerint.

5. Ha befejezte a feladat útmutató szerkesztésével, kattintson a **végzett Szerkesztés**, majd válassza a beállítások mentése vagy közzététele a feladat útmutató.

## <a name="collapse-recording-name-and-description"></a>Összecsukás felvétel nevét és leírását.
Kibonthatja és összecsukhatja a **felvétel neve** és **felvétel leírás** mezők. Ezek a mezők össze vannak csukva, amikor további lépéseket a Feladatrögzítő szerkesztése ablaktáblán látható lesz. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Lásd még
--------

[Dokumentáció vagy képzés létrehozása feladatrögzítések segítségével.](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Feladat író gyors áttekintése](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


