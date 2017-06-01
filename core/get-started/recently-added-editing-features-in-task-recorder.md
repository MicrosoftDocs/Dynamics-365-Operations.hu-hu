---
title: "A feladatrögzítő nemrégiben hozzáadott szerkesztési funkciói"
description: "Ha a feladatrögzítő segítségével hoz létre feladat-útmutatókat, hatékonyabban szerkesztheti a fájlokat a témakörben ismertetett funkció használatával."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 272856c01074a352e3945f29e9cdf7655aaf22ba
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>A feladatrögzítő nemrégiben hozzáadott szerkesztési funkciói

[!include[banner](../includes/banner.md)]


Ha a feladatrögzítő segítségével hoz létre feladat-útmutatókat, hatékonyabban szerkesztheti a fájlokat a témakörben ismertetett funkció használatával.

Ezek a szolgáltatások a **Beállítások &gt; Feladatrögzítő &gt; Felvétel szerkesztés** menüben érhetők el.

-   Szúrja be a lépéseket a teljes fájl ismételt rögzítése nélkül.
-   Mozgassa a lépéseket egy alfeladat alá az egész fájl ismételt rögzítése nélkül.
-   Csukja össze a Felvétel neve és leírása mezőket.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Szúrja be a lépéseket a teljes fájl ismételt rögzítése nélkül.
Most már bárhol hozzáadhat lépést a feladat-útmutatóhoz a teljes fájl lejátszása vagy ismételt rögzítése nélkül.

1.  Jelölje be a lépés, amely után szeretné beszúrni az új lépést. Ellenőrizze, hogy a lépés ki van emelve.

Ahhoz, hogy egy lépést beszúrjon a Feladatrögzítő, nyissa meg a megfelelő oldalt. A megfelelő oldal az az oldal, amelyen az új lépés következik be. A Feladatrögzítő rendelkezik egy olyan mechanizmussal, amely azt határozza meg, hogy melyik az aktív oldal, és a szolgáltatást letiltja, ha nincs megnyitva a megfelelő oldal. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Ha a megfelelő oldalon van, elérhetővé válik a **Lépés beszúrása**.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Kattintson a **Lépés beszúrása** lehetőségre.

Amikor rákattint a **Lépés beszúrása** lehetőségre, a Feladatrögzítő rögzítési üzemmódra vált. A felhasználói felületen végzett minden művelet rögzítve lesz, és helyben hozzáadott lépéssé válik.

3. Kattintson az **Állj** lehetőségre.

A folyamat megismételhető, tetszőleges számú lépés hozzáadására vagy alfeladat áthelyezésére van lehetőség (lásd az alábbiakat az alfeladatokra vonatkozóan).

4. Ha befejezte a feladat-útmutató szerkesztését, kattintson a **Szerkesztés kész** lehetőségre, majd válassza a beállítások egyikét a feladat-útmutató mentéséhez vagy közzétételéhez.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Mozgassa a lépéseket egy alfeladat alá az egész fájl ismételt rögzítése nélkül.
A lépéseket egy alfeladat alá mozgathatja az egész fájl ismételt rögzítése nélkül. Ha egy meglévő lépésblokkot csoportosítani szeretne, az altevékenység-lépést és az altevékenység befejezési lépését is áthelyezheti.

1.  Jelölje ki az áthelyezni kívánt lépést vagy alfeladat lépést. Ellenőrizze, hogy a lépés ki van emelve.
2.  Kattintson a három pont, majd a **Lépés mögé helyezése** lehetőségre.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Jelölje ki a lépést vagy az altevékenység-lépést, amely mögé a lépést vagy az altevékenység-lépést szeretné áthelyezni. A Feladatrögzítő áthelyezi a lépést.

4. Az altevékenység befejezési lépésének áthelyezéséhez jelölje ki a lépést, kattintson a három pontra, kattintson a **Lépés mögé helyezése** lehetőségre, és válassza ki a lépést, amely mögé az altevékenység befejezési lépést szeretné áthelyezni.

Ha azt szeretné, hogy az első lépés a feladat-útmutatóba egy altevékenységen belül legyen, második lépésként hozzon létre egy altevékenységek lépést, és az első lépést helyezze át ide. Szükség szerint bármennyi lépést vagy altevékenységet hozzáadhat.

5. Ha befejezte a feladat-útmutató szerkesztését, kattintson a **Szerkesztés kész** lehetőségre, majd válassza a beállítások egyikét a feladat-útmutató mentéséhez vagy közzétételéhez.

## <a name="collapse-recording-name-and-description"></a>Csukja össze a Felvétel neve és leírását.
Kibonthatja és összecsukhatja a **Felvétel neve** és **Felvétel leírása** mezőket. Amikor ezek a mezők össze vannak csukva, további lépések lesznek láthatók a Feladatrögzítő szerkesztése ablaktáblán. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Lásd még
--------

[Dokumentáció vagy képzés létrehozása feladatrögzítések segítségével.](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Feladatrögzítő gyors áttekintése](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)




