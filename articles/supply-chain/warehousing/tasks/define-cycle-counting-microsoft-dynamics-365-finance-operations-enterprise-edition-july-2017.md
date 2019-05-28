---
title: 'Ciklikus leltározás meghatározása '
description: A ciklikus leltározás egy olyan raktározási folyamat, amelyet az aktuális készlet cikkeinek ellenőrzésére használhat.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2832547f81b0153d42ac4664184f18bd66f1acdd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571678"
---
# <a name="define-cycle-counting"></a>Ciklikus leltározás meghatározása  

[!include [task guide banner](../../includes/task-guide-banner.md)]

A ciklikus leltározás egy olyan raktározási folyamat, amelyet az aktuális készlet cikkeinek ellenőrzésére használhat. A feladatrögzítés megmutatja, hogy miként: állíthatja be az alapértelmezett leltározási feladat prioritását; engedélyezhet egy mobileszköz menüpontot a kitárolási és leltározási műveletekhez, engedélyezhet egy leltározási küszöbértéket, ha egy hely üressé válik, engedélyezhet egy ciklikus leltározási tervet egy adott raktárban található adott cikkhez. Általában a raktárvezető végzi el ezeket a feladatokat. Ezt a folyamatot az USMF bemutatócégen vagy saját adatain is elvégezheti.


## <a name="set-the-priority-of-counting-work"></a>A leltározási munka prioritásának beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési paraméterekre.
2. Kattintson a Ciklikus leltározás lapra.
3. A Ciklikus leltározási munka alapértelmezett prioritása mezőben adjon meg egy számot.
    * Ez a lépés megváltoztatja a ciklikus leltározási munka prioritását a raktárban folyó más típusú munkákhoz képest. Ha kisebb számot ad meg a többi típusú munkához megadott számoknál, növeli a ciklikus leltározási feladat prioritását.  
4. Kattintson a Mentés gombra.
5. Zárja be a lapot.

## <a name="enable-the-mobile-device"></a>Mobileszköz engedélyezése
1. Ugrás a Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemekre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Menüelem neve mezőbe.
4. Érték beírása a Címmezőbe.
5. A Mód mezőben válassza ki a „Munka” lehetőséget.
6. A Meglévő munka használata lehetőséget állítsa Igenre.
    * Ha az Igen lehetőséget választja, a mobileszköz menüpont használata esetén a rendszer megvizsgálja a meglévő munkát.  
7. Az Irányítja mezőben válassza a „Rendszer által irányított” lehetőséget.
    * Amikor a „Rendszer által irányított” lehetőség van kijelölve, a rendszer a raktári dolgozót a munkaosztályokban megadott nyitott munkákhoz irányítja. (Ezeket a munkaosztályokat a későbbiekben hozzuk létre.)  
8. Bontsa ki vagy csukja össze a Munkaosztályok szakaszt.
    * Most létrehozunk két felhasználható munkaosztályt, amelyeket ezzel a mobileszköz menüponttal használ. A menüpont használata esetén megtörténik a munkaosztályok lekérdezése, és a legmagasabb prioritású munka megjelenik a felhasználó számára.  
9. Kattintson az Új lehetőségre.
10. A Munkaosztály-azonosító mezőbe írjon be egy értéket.
11. Kattintson az Új lehetőségre.
12. A Munkaosztály-azonosító mezőbe írjon be egy értéket.
13. Kattintson a Mentés gombra.
14. Zárja be a lapot.
15. Ugrás a Raktárkezelés > Beállítás Mobileszköz > Mobileszköz menüre.
16. Keresse meg és jelölje ki a kívánt rekordot a listán.
17. A fán válassza ki az „éppen létrehozott menüpont” lehetőséget.
18. Kattintson a Szerkesztés lehetőségre.
19. Kattintson a nyílra a menüpont menühöz való hozzáadásához.
20. Kattintson a Mentés gombra.

## <a name="create-a-counting-threshold"></a>Leltározási küszöbérték létrehozása
1. Ugorjon a Raktárkezelés > Beállítás > Ciklikus leltározás > Ciklikus leltározási küszöbértékei menüpontra.
2. Kattintson az Új lehetőségre.
3. A Ciklikus leltározási küszöbérték azonosítója mezőbe írjon be egy értéket.
4. A Ciklikus leltározás végrehajtása azonnal lehetőséget állítsa Igenre.
5. A Leírás mezőben adjon meg egy értéket.
6. Kattintson a Mentés gombra.
7. Kattintson a Hely kiválasztása lehetőségre.
8. A listában jelölje meg a kiválasztott sort.
9. A Feltételek mezőben válasszon ki egy értéket.
10. Kattintson az OK gombra.
11. Zárja be a lapot.

## <a name="create-a-cycle-count-plan"></a>Ciklikus leltározási terv létrehozása
1. Ugorjon a Raktárkezelés > Beállítás > Ciklikus leltározás > Ciklikus leltározási tervek lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Ciklikus leltározási terv azonosítója mezőbe írjon be egy értéket.
4. Írjon egy értéket a „Leírás” mezőbe.
5. A Ciklikus leltározások maximális száma mezőbe írjon be egy számot.
6. Kattintson a Mentés gombra.
7. Kattintson a Hely kiválasztása lehetőségre.
8. A listában jelölje meg a kiválasztott sort.
9. A Feltételek mezőben válasszon ki egy értéket.
10. Kattintson az OK gombra.
11. A Ciklikus leltárok közötti idő mezőben adjon meg egy számot.
    * Ha például a Ciklikus leltárok közötti idő mező megadott beállítása 5, a ciklikus leltározási munka ötnaponként készül. Azonban ha a ciklikus leltári munka a harmadik napon kerül feldolgozásra, a rendszer a következő leltározási munkát öt nappal az utolsó ciklikus leltár feldolgozása után, a 8. napon hozza létre.  
12. Kattintson a Mentés gombra.
13. Kattintson az Új lehetőségre.
14. Adjon meg egy számot a Sorozatszám mezőben.
    * A rendezési sorrend a legkisebb számtól a legnagyobb számig tart. Az értéknek nullánál (0) nagyobbnak kell lennie.  
15. A listában jelölje meg a kiválasztott sort.
16. A Leírás mezőben adjon meg egy értéket.
17. Kattintson a Mentés gombra.
18. Kattintson a Terméklekérdezés megadása lehetőségre.
19. A listában jelölje meg a kiválasztott sort.
20. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
21. Kattintson az OK gombra.
22. Zárja be a lapot.

