---
title: 'Ciklikus leltározás meghatározása '
description: A ciklikus leltározás egy olyan raktározási folyamat, amelyet az aktuális készlet cikkeinek ellenőrzésére használhat.
author: Mirzaab
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45107dca67ac13669c468c4c32fb4adfdab2195b
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902146"
---
# <a name="define-cycle-counting"></a>Ciklikus leltározás meghatározása  

[!include [banner](../../includes/banner.md)]

A ciklikus leltározás egy olyan raktározási folyamat, amelyet az aktuális készlet cikkeinek ellenőrzésére használhat. A feladatrögzítés megmutatja, hogy miként: állíthatja be az alapértelmezett leltározási feladat prioritását; engedélyezhet egy mobileszköz menüpontot a kitárolási és leltározási műveletekhez, engedélyezhet egy leltározási küszöbértéket, ha egy hely üressé válik, engedélyezhet egy ciklikus leltározási tervet egy adott raktárban található adott cikkhez. Általában a raktárvezető végzi el ezeket a feladatokat. Ezt a folyamatot az USMF bemutatócégen vagy saját adatain is elvégezheti.


## <a name="set-the-priority-of-counting-work"></a>A leltározási munka prioritásának beállítása
1. Ugrás a **Navigációs ablaktáblán** válassza a **Modulok > Raktárkezelés > Beállítás > Raktárkezelési paraméterek** lehetőséget.
2. Kattintson a **Ciklikus leltározás** lapra.
3. A **Ciklikus leltározási munka alapértelmezett prioritása** mezőben adjon meg egy számot. Ez a lépés megváltoztatja a ciklikus leltározási munka prioritását a raktárban folyó más típusú munkákhoz képest. Ha kisebb számot ad meg a többi típusú munkához megadott számoknál, növeli a ciklikus leltározási feladat prioritását.  
4. Kattintson a **Mentés** gombra.
5. Zárja be a lapot.

## <a name="enable-the-mobile-device"></a>Mobileszköz engedélyezése
1. A **Navigációs ablaktáblán** ugorjon a **Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menüpontjai** elemre.
2. Kattintson az **Új** elemre.
3. Írjon be egy értéket a **Menüelem neve** mezőbe.
4. Érték beírása a **Cím** mezőbe.
5. A **Mód** mezőben válassza ki a „Munka” lehetőséget.
6. A **Meglévő munka használata** lehetőséget állítsa Igenre. Ha az Igen lehetőséget választja, a mobileszköz menüpont használata esetén a rendszer megvizsgálja a meglévő munkát.  
7. Az **Irányítja** mezőben válassza a „Rendszer által irányított” lehetőséget. Amikor a „Rendszer által irányított” lehetőség van kijelölve, a rendszer a raktári dolgozót a munkaosztályokban megadott nyitott munkákhoz irányítja. (Ezeket a munkaosztályokat a későbbiekben hozzuk létre.)  
8. Bontsa ki a **Munkaosztályok** gyorslapot. Most létrehozunk két felhasználható munkaosztályt, amelyeket ezzel a mobileszköz menüponttal használ. A menüpont használata esetén megtörténik a munkaosztályok lekérdezése, és a legmagasabb prioritású munka megjelenik a felhasználó számára.  
9. Kattintson az **Új** elemre.
10. A **Munkaosztály-azonosító** mezőbe írjon be egy értéket.
11. Kattintson az **Új** elemre.
12. A **Munkaosztály-azonosító** mezőbe írjon be egy értéket.
13. A **Műveleti panelen** kattintson a **Mentés** elemre.
14. Zárja be a lapot.
15. A **Navigációs ablaktáblán** ugorjon a **Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menüpontja** elemre.
16. Keresse meg és jelölje ki a kívánt rekordot a listán.
17. A fán válassza ki az „éppen létrehozott menüpont” lehetőséget.
18. Kattintson a **Szerkesztés** lehetőségre.
19. Kattintson a nyílra a menüpont menühöz való hozzáadásához.
20. Kattintson a **Mentés** gombra.

## <a name="create-a-counting-threshold"></a>Leltározási küszöbérték létrehozása
1. A **Navigációs ablakban** nyissa meg a **Modulok > Raktárkezelés > Beállítás > Viklikus leltározási > Viklikus leltározási küszöbértékek** elemet.
2. Kattintson az **Új** elemre.
3. A **Ciklikus leltározási küszöbérték azonosítója** mezőbe írjon be egy értéket.
4. A **Ciklikus leltározás végrehajtása azonnal** lehetőséget állítsa Igenre.
5. Írjon egy értéket a **Leírás** mezőbe.
6. Kattintson a **Mentés** gombra.
7. Kattintson a **Hely kiválasztása** lehetőségre.
8. A listában jelölje meg a kiválasztott sort.
9. A **Feltételek** mezőben válasszon ki egy értéket.
10. Kattintson az **OK** gombra.
11. Zárja be a lapot.

## <a name="create-a-cycle-count-plan"></a>Ciklikus leltározási terv létrehozása
1. A **Navigációs ablakban** nyissa meg a **Modulok > Raktárkezelés > Beállítás > Viklikus leltározási > Ciklikus leltározási tervek** elemet.
2. Kattintson az **Új** elemre.
3. A **Ciklikus leltározási terv azonosítója** mezőbe írjon be egy értéket.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Ciklikus leltározások maximális száma** mezőbe írjon be egy számot.
6. Kattintson a **Mentés** gombra.
7. Kattintson a **Hely kiválasztása** lehetőségre.
8. A listában jelölje meg a kiválasztott sort.
9. A **Feltételek** mezőben válasszon ki egy értéket.
10. Kattintson az **OK** gombra.
11. A **Ciklikus leltárok közötti idő mezőben** adjon meg egy számot. Ha például a **Ciklikus leltárok közötti idő** mező megadott beállítása 5, a ciklikus leltározási munka ötnaponként készül. Azonban ha a ciklikus leltári munka a harmadik napon kerül feldolgozásra, a rendszer a következő leltározási munkát öt nappal az utolsó ciklikus leltár feldolgozása után, a 8. napon hozza létre.  
12. Kattintson a **Mentés** gombra.
13. Kattintson az **Új** elemre.
14. Adjon meg egy számot a **Sorozatszám** mezőben. A rendezési sorrend a legkisebb számtól a legnagyobb számig tart. Az értéknek nullánál (0) nagyobbnak kell lennie.  
15. A listában jelölje meg a kiválasztott sort.
16. Írjon egy értéket a **Leírás** mezőbe.
17. Kattintson a **Mentés** gombra.
18. Kattintson a **Terméklekérdezés** megadása lehetőségre.
19. A listában jelölje meg a kiválasztott sort.
20. A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.
21. Kattintson az **OK** gombra.
22. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]