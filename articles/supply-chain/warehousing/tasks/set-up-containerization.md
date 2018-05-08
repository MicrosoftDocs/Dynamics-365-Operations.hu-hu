--- 
title: "Tárolóra bontás beállítása"
description: "Ez az eljárás azt mutatja be, hogy hogyan lehet automatizálni a szállítmányok tárolóra bontását a Raktárkezelésben."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 76334f7ee4efe33df4a86aaa11a59748387cec89
ms.openlocfilehash: c5faf926071dec5d2ddc1c9e921a98ecd0754917
ms.contentlocale: hu-hu
ms.lasthandoff: 11/02/2017

---
# <a name="set-up-containerization"></a>Tárolóra bontás beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás azt mutatja be, hogy hogyan lehet automatizálni a szállítmányok tárolóra bontását a Raktárkezelésben. Az automatizált tárolóra bontás folyamat tárolókat és a szállítmányok kitárolási munkáját hozza létre, amikor a rendszer feldolgozza a hullámot és amikor a munkasorokat a tárolókhoz illeszkedő mennyiségekre lehet felosztani. Ez megkönnyíti a raktári dolgozóknak a cikkek egyenesen a kiválasztott tárolóba történő kitárolását. A kézi csomagolási folyamathoz képest olyan feladatok, mint például a tárolók létrehozása, a cikkek társítása, és a rendszer által automatizált tárolók lezárása. Ez az eljárás az USMF bemutató vállalatot használja, amelyet a raktárvezető végez.


## <a name="set-up-a-wave-template"></a>Állítsa be a hullámsablon lehetőséget
1. Ugorjon a Raktárkezelés > Beállítás > Hullám > Hullámsablonok pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Hullámsablon mezőbe.
4. Írjon be egy értéket a Hullámsablon leírása mezőbe.
5. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
6. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
7. Bontsa ki a Módszerek szakaszt.
    * A kiválasztott módszerek ablaktábláján megtalálhatóak a kiválasztott hullámsablon típusára vonatkozó módszerek. A hullámsablonnak tartalmaznia kell a tárolóra bontás módszert.  
8. Keresse meg és jelölje ki a kívánt rekordot a listán.
9. A Hullámlépés kódja mezőben írjon be egy értéket.
    * Adjon meg egy hullámlépéskódot a hozzáadott módra vonatkozóan, amely bármilyen kód lehet. Egynél többször is hozzáadhatja a módszert, illetve különböző hullámlépéskódokat társíthat. Ehhez válassza ki a Megismételhető ennél a metódusnál a Hullámfeldolgozási módokban lapot.  
10. Kattintson a Mentés gombra.
11. Zárja be a lapot.

## <a name="set-up-a-container-type"></a>Tárolótípus beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolótípusok pontra.
    * Meghatározhatja a tárolóit a Tárolótípusok lapon. Konfigurálhatja a tárolók fizikai dimenzióit, többek között a csomagolási súlyát, az össztömegét, a maximális térfogatát, a hosszúságát, a szélességét és a magasságát. Ebben a példában három különböző méretű doboz található.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Tároló típuskódja mezőbe.
4. Adjon meg egy számot a Tárasúly mezőben.
5. Adjon meg egy számot a Maximális súly mezőben.
6. A Térfogat mezőben adjon meg egy számot.
7. Adjon meg egy számot a Hosszúság mezőben.
8. Adjon meg egy számot a Szélesség mezőben.
9. Adjon meg egy számot a Magasság mezőben.
10. A Leírás mezőben adjon meg egy értéket.
11. Kattintson a Mentés gombra.
12. Kattintson az Új lehetőségre.
13. Írjon be egy értéket a Tároló típuskódja mezőbe.
14. A Leírás mezőben adjon meg egy értéket.
15. Adjon meg egy számot a Tárasúly mezőben.
16. Adjon meg egy számot a Maximális súly mezőben.
17. A Térfogat mezőben adjon meg egy számot.
18. Adjon meg egy számot a Hosszúság mezőben.
19. Adjon meg egy számot a Szélesség mezőben.
20. Adjon meg egy számot a Magasság mezőben.
21. Kattintson a Mentés gombra.
22. Kattintson az Új lehetőségre.
23. Írjon be egy értéket a Tároló típuskódja mezőbe.
24. A Leírás mezőben adjon meg egy értéket.
25. Adjon meg egy számot a Tárasúly mezőben.
26. Adjon meg egy számot a Maximális súly mezőben.
27. A Térfogat mezőben adjon meg egy számot.
28. Adjon meg egy számot a Hosszúság mezőben.
29. Adjon meg egy számot a Szélesség mezőben.
30. Adjon meg egy számot a Magasság mezőben.
31. Kattintson a Mentés gombra.
32. Zárja be a lapot.

## <a name="set-up-a-container-group"></a>Tárolócsoport beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolócsoport azonosítója pontra.
2. Kattintson az Új lehetőségre.
    * A tárolótípusokat logikai alapon csoportokba vonhatja össze. Minden egyes csoportra vonatkozóan határozza meg azt a sorrendet, amelyben a tárolók feltöltését elvégzi és a tárolók százalékát a kitöltéshez. A rendszer a cikk méretének dimenziói alapján határozza meg, hogy elfér-e a tárolóban. Az alkalmazás azt a tárolót használja, amely legközelebb áll a kérdéses cikk méretéhez. Ha egy csoportban több tárolótípus is van, akkor érdemes őket méretsorrendbe rendezni, úgy, hogy a legnagyobb tároló legyen a lista tetején 1-es számmal, a legkisebb pedig az utolsó.    
3. Írjon be egy értéket a Tárolócsoport azonosítója mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson az Új elemre.
6. A listában jelölje meg a kiválasztott sort.
7. A tárolótípus mezőben adjon meg vagy válasszon ki egy értéket.
8. Kattintson az Új elemre.
9. A listában jelölje meg a kiválasztott sort.
10. A tárolótípus mezőben adjon meg vagy válasszon ki egy értéket.
11. Kattintson az Új elemre.
12. A listában jelölje meg a kiválasztott sort.
13. A tárolótípus mezőben adjon meg vagy válasszon ki egy értéket.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.

## <a name="set-up-a-container-build-template"></a>Tárolóépítési sablon beállítása
1. Ugorjon a Raktárkezelés > Beállítás > Tárolók > Tárolóépítési sablonok pontra.
2. Kattintson az Új lehetőségre.
    * A tárolóépítési sablon azon alapul, amelyen a tároló-létrehozási folyamatait elvégzik. Minden egyes tárolóépítési sablon meghatároz egy hullámsablon által használandó tároló-létrehozási folyamatot. A szerkesztési lekérdezés beállítással meghatározhatja azokat a feltételeket, amelyek alapján a kiválasztott sablonokat feldolgozza. Például az is lehetséges, hogy csak a Tárolóra bontást futtatja a bizonyos vevőkre, a termékekre vagy a raktárakra vonatkozóan, vagy hozzáadhatja a sablonokhoz a megfeleltetési lekérdezési tartományokat. A Hullámlépéskód mező a tárolóépítési sablon a hullámsablonban található lépésekhez történő kapcsolódásának módját jelenti. Amikor végrehajtja a rendszer a hullámot, meghatározza, hogy a rendszer mely tárolóépítési sablon(ok)at használja fel a Tárolóra bontás folyamatának kezdeményezésére. Az Alap lekérdezéstípusok mezőben meghatározza a becsomagolni kívánt terméket és a szűrőlekérdezés alapját.  
3. A listában jelölje meg a kiválasztott sort.
4. Írjon be egy értéket a Tárolósablon azonosítója mezőbe.
5. A Tárolócsoport azonosítója mezőben adjon meg, vagy válasszon ki egy értéket.
6. A Hullámlépés kódja mezőben írjon be egy értéket.
7. Jelölje be a Kitárolások szétosztásának engedélyezése jelölőnégyzetet.
8. Kattintson a Mentés gombra.
9. Kattintson a Tárolóvegyesítési megszorítások lehetőségre.
    * A Vegyítési logika felbontásai lehetővé teszik a szabályok felállítását a felosztási sorok tárolóba való csomagolásához. Például ha hozzáadja a Cikkszám mezőt, amikor a rendszer a cikkeket a tárolóhoz rendeli, egy új tárolót hoz létre egy új cikkszám esetén. A rendszer így megakadályozza, hogy a munkavállalók két különböző vevőhöz tartozó felosztási sort ugyanabba a tárolóba csomagoljanak.  
10. Kattintson az Új lehetőségre.
11. Válasszon ki egy lehetőséget a Tábla mezőben.
12. A Mezőválasztás mezőben adjon meg vagy válasszon ki egy értéket.
13. Kattintson az OK gombra.


