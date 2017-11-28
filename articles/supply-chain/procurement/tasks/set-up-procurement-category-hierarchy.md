--- 
title: "Beszerzési kategóriák hierarchiájának beállítása"
description: "Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát."
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6ad5c8552a6989e9093d0b1325754bc0f6d19372
ms.openlocfilehash: 4541d029c9c3be3ee42332e5d8ff183dd503f13e
ms.contentlocale: hu-hu
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a>Beszerzési kategóriák hierarchiájának beállítása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát. Ezeket a feladatokat jellemzően egy beszerzési vezető végzi el. Az eljárás megkezdése előtt kell lennie egy Beszerzés típusú kategóriahierarchiának. Ha bemutató adatokat használ, ezt az eljárást az USMF vállalatban futtathatja.


## <a name="add-a-new-procurement-category"></a>Új beszerzési kategória hozzáadása
1. Ugorjon a Beszerzés és forrás > Beszerzési kategóriák pontra.
2. Kattintson a Kategóriahierarchiák szerkesztése pontra.
    * Az aktuális beszerzési kategóriák hierarchiája az oldal bal oldalán jelenik meg. Ezzel módosítja a hierarchiát.  
3. Kattintson az Új kategória-csomópont gombra.
    * A rendszer alapértelmezés szerint kiválasztja a felső csomópontot. Ha ezzel az eljárással a feladatot útmutatóként futtatja, kattintson a zárolás feloldása gombra, és válasszon másik szülő-csomópontot, amelybe az új csomópontot szeretné beilleszteni. Ezt követően zárolja újra a feladatútmutatót, és kattintson az Új kategória-csomópontra.  
4. Írjon be egy értéket a Név mezőbe.
5. A Leírás mezőben adjon meg egy értéket.
6. Írjon be egy értéket a Barátságos név mezőbe.
    * A baráti név nem kötelező. A kategória keresésekben a kategórianévvel együtt fog megjelenni.  
7. Kattintson a Mentés gombra.

## <a name="add-products-to-your-new-procurement-category"></a>Termékek hozzáadása az új beszerzési kategóriához
1. Ugorjon a Beszerzés és forrás > Beszerzési kategóriák pontra.
    * Jelölje ki az éppen hozzáadott csomópontot. Ha ezt a folyamatot feladat-útmutatóként használja, szükség lehet a feladat-útmutató feloldására a csomópont kiválasztásához.  
2. Váltsa át a Termékek szakasz kibontását.
3. Kattintson a Hozzáadás gombra a termékek hozzárendeléséhez a beszerzési kategóriával.
4. Válassza ki azt a terméket, amelyet hozzá szeretné adni a beszerzési kategóriához.
5. Kattintson a nyílra a termék kiválasztásához.
6. Válasszon egy másik terméket, amelyet hozzá szeretné adni a beszerzési kategóriához.
7. Kattintson a nyílra a termék kiválasztásához.
8. Kattintson az OK gombra.

## <a name="add-approved-and-preferred-vendors"></a>Jóváhagyott és preferált szállítók hozzáadása
1. Módosítsa a Szállítók szakasz bővítését.
2. Kattintson a Hozzáadás gombra.
    * Szállítót adhat hozzá egy beszerzési kategóriához és megadhatja, hogy a szállító preferált vagy csak jóváhagyott legyen-e a kategóriában. Egy szállító kategóriából történő törlésekor a szállítóval történt előzménytranzakciók nem törlődnek.   
3. Keresse meg az a beszállítót, amelyet hozzá szeretné adni a kategóriához.
4. Kattintson a nyílra a beszállító kiválasztásához.
5. Kattintson az OK gombra.
6. Válassza ki a módosítani kívánt beszállítói sort.
7. A Beszállítói állapot mezőben válasszon ki egy opciót.
    * A szállító kiválasztása beállítása a Kategória-irányelvszabályban azt szabályozza, hogy az elsődleges, a jóváhagyott, illetve valamennyi szállító elérhető-e a beszerzési igénylésekben.   

## <a name="add-additional-information-to-the-category"></a>További adatok hozzáadása a kategóriához
1. Váltsa át a Szállítóértékelési feltétel csoport kibontását.
    * Ez a lap lehetővé teszi annak meghatározását, hogy melyik kritériumokkal szemben lesznek a beszerzési kategóriához tartozó szállítók mérve. Ehhez kattintson a Hozzáadás gombra, és válassza ki azt a szállítóértékelési csoportot, amely tartalmazza a kívánt feltételeket.  
2. Váltsa át a Kérdőívek szakasz kibontását.
    * Ezen a lapon hozzáadhat kérdőíveket, amelyek megjelennek az igénylésen, mindaddig, amíg a Tevékenység típusának az „Igénylés”-t választja. A kérelmezőnek ki kell töltenie egy kérdőívet, mielőtt beküld egy kérelmet a beszerzési kategóriához tartozó termékek igénylése előtt.  
3. Váltsa át a Cikkáfacsoport szakasz kibontását.
4. A Cikkáfacsoport: mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Áfacsoport kiválasztása.
6. Váltsa át a Kategóriaoldal szakasz kibontását.
    * A kategóriaoldalak a Kategóriahierarchia oldalon jönnek létre. Adatokat tartalmaznak a beszerzési kategóriáról, például az egy kategórián belüli terméktípus adatait, egy kategórián belüli termékek képeit, vagy bejelentéseket, például a kategórián belül elérhető kedvezményeket. A kategóriaoldalon lévő információk megjelennek a beszerzési igényléseken.  
7. Zárja be a lapot.


