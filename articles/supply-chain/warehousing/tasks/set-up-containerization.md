---
title: Tárolóra bontás beállítása
description: Ez a témakör azt mutatja be, hogy hogyan lehet automatizálni a szállítmányok tárolóra bontását a Raktárkezelésben.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f28be8993d5fc0a1632cf7a534808e64980c09b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977038"
---
# <a name="set-up-containerization"></a>Tárolóra bontás beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogy hogyan lehet automatizálni a szállítmányok tárolóra bontását a Raktárkezelésben. Az automatizált tárolóra bontás folyamat tárolókat és a szállítmányok kitárolási munkáját hozza létre, amikor a rendszer feldolgozza a hullámot és amikor a munkasorokat a tárolókhoz illeszkedő mennyiségekre lehet felosztani. Ez megkönnyíti a raktári dolgozóknak a cikkek egyenesen a kiválasztott tárolóba történő kitárolását. A kézi csomagolási folyamathoz képest olyan feladatok, mint például a tárolók létrehozása, a cikkek társítása, és a rendszer által automatizált tárolók lezárása. Ez az eljárás az USMF bemutató vállalatot használja, amelyet a raktárvezető végez.


## <a name="set-up-a-wave-template"></a>Állítsa be a hullámsablon lehetőséget
1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Hullámok > Hullámsablonok** lehetőségre.
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Hullámsablon neve** mezőben.
4. Adjon meg egy értéket a **Hullámsablon leírása** mezőben.
5. A **Hely** mezőben adjon meg vagy válasszon ki egy értéket.
6. A **Raktár** mezőben adjon meg vagy válasszon ki egy értéket.
7. Bontsa ki a **Módszerek** szakaszt. A **Kiválasztott módszerek** ablaktábláján megtalálhatóak a kiválasztott hullámsablon típusára vonatkozó módszerek. A hullámsablonnak tartalmaznia kell a tárolóra bontás módszert.  
8. A **Hullámlépés kódja** mezőben írjon be egy értéket. Adjon meg egy hullámlépéskódot a hozzáadott módra vonatkozóan, amely bármilyen kód lehet. Egynél többször is hozzáadhatja a módszert, illetve különböző hullámlépéskódokat társíthat. Ehhez válassza ki a **Megismételhető ennél a metódusnál** lehetőséget a **Hullámfeldolgozási metódusok** lapon.  
9. Válassza a **Mentés** lehetőséget.
10. Zárja be a lapot.

## <a name="set-up-a-container-type"></a>Tárolótípus beállítása
1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Tárolók > Tárolótípusok** lehetőségre. Meghatározhatja a tárolóit a **Tárolótípusok** lapon. Konfigurálhatja a tárolók fizikai dimenzióit, többek között a csomagolási súlyát, az össztömegét, a maximális térfogatát, a hosszúságát, a szélességét és a magasságát. Ebben a példában három különböző méretű doboz található.  
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket a **Tároló típuskódja** mezőben.
4. Adjon meg egy számot a **Tárasúly** mezőben.
5. Adjon meg egy számot a **Maximális súly** mezőben.
6. A **Térfogat** mezőben adjon meg egy számot.
7. Adjon meg egy számot a **Hosszúság** mezőben.
8. Adjon meg egy számot a **Szélesség** mezőben.
9. Adjon meg egy számot a **Magasság** mezőben.
10. Írjon egy értéket a **Leírás** mezőbe.
11. Válassza a **Mentés** lehetőséget.
13. Ismételje meg a 2–11. lépést két alkalommal a három teljes tárolótípus létrehozásához.
14. Zárja be a lapot.

## <a name="set-up-a-container-group"></a>Tárolócsoport beállítása
1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Tárolók > Tárolócsoportok** lehetőségre.
2. A Műveleti ablaktáblán kattintson az **Új** elemre. A tárolótípusokat logikai alapon csoportokba vonhatja össze. Minden csoportban meghatározhatja a tárolók csomagolásának sorrendjét és a tárolók feltöltésének százalékát. A rendszer a cikkek méretadatai alapján dönti el, hogy bele fog-e férni egy adott tárolóba. Az alkalmazás azt a tárolót használja, amely legközelebb áll a kérdéses cikk méretéhez. Ha egy csoportban több tárolótípus is van, akkor érdemes őket méretsorrendbe rendezni, úgy, hogy a legnagyobb tároló legyen a lista tetején 1-es számmal, a legkisebb pedig az utolsó.    
3. Adja meg a korábban létrehozott értéket a **Tárolócsoport azonosítója** mezőben.
4. Írjon egy értéket a **Leírás mezőbe**.
5. Ismételje meg a 2–4. lépést a korábban létrehozott mindhárom típusú tároló esetében.
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a lapot.

## <a name="set-up-a-container-build-template"></a>Tárolóépítési sablon beállítása
1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Tárolók > Tárolóépítési sablonok** lehetőségre.
2. Válassza az **Új** lehetőséget. A tárolóépítési sablon azon alapul, amelyen a tároló-létrehozási folyamatait elvégzik. Minden egyes tárolóépítési sablon meghatároz egy hullámsablon által használandó tároló-létrehozási folyamatot. A **Szerkesztési lekérdezés** beállítással meghatározhatja azokat a feltételeket, amelyek alapján a kiválasztott sablonokat feldolgozza. Például az is lehetséges, hogy csak a Tárolóra bontást futtatja a bizonyos vevőkre, a termékekre vagy a raktárakra vonatkozóan, vagy hozzáadhatja a sablonokhoz a megfeleltetési lekérdezési tartományokat. A **Hullámlépéskód** mező a tárolóépítési sablon a hullámsablonban található lépésekhez történő kapcsolódásának módját jelenti. Amikor végrehajtja a rendszer a hullámot, meghatározza, hogy a rendszer mely tárolóépítési sablon(ok)at használja fel a Tárolóra bontás folyamatának kezdeményezésére. Az Alap lekérdezéstípusok mezőben meghatározza a becsomagolni kívánt terméket és a szűrőlekérdezés alapját. 
3. Adjon meg egy értéket a **Tárolósablon azonosítója** mezőben.
4. A **Tárolócsoport azonosítója** mezőben adjon meg vagy válasszon ki egy értéket.
5. A **Hullámlépés kódja** mezőben írjon be egy értéket.
6. Jelölje be a **Kitárolások szétosztásának engedélyezése** jelölőnégyzetet.
7. Válassza a **Mentés** lehetőséget.
8. Válassza ki a **Tárolóvegyesítési megszorítások** lehetőséget. A Vegyítési logika felbontásai lehetővé teszik a szabályok felállítását a felosztási sorok tárolóba való csomagolásához. Például ha hozzáadja a **Cikkszám mezőt**, amikor a rendszer a cikkeket a tárolóhoz rendeli, egy új tárolót hoz létre egy új cikkszám esetén. A rendszer így megakadályozza, hogy a munkavállalók két különböző vevőhöz tartozó felosztási sort ugyanabba a tárolóba csomagoljanak.  
9. Válassza az **Új** lehetőséget.
10. Válasszon ki egy lehetőséget a **Tábla** mezőben.
11. A **Mezőválasztás** mezőben adjon meg vagy válasszon ki egy értéket.
12. Válassza ki az **OK** lehetőséget.

