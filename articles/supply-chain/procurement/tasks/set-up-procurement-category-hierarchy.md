---
title: Beszerzési kategóriák hierarchiájának beállítása
description: Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát.
author: mkirknel
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eaab2093eb2531b63f27717d828f7064a8f9ed1d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207508"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Beszerzési kategóriák hierarchiájának beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja az új csomópontok létrehozását a beszerzési kategóriák hierarchiájában, és azt, hogyan kell konfigurálni a beszerzési folyamatban használt beszerzési kategóriát. Ezeket a feladatokat jellemzően egy beszerzési vezető végzi el. Az eljárás megkezdése előtt kell lennie egy Beszerzés típusú kategóriahierarchiának. Ha bemutató adatokat használ, ezt az eljárást az USMF vállalatban futtathatja.


## <a name="add-a-new-procurement-category"></a>Új beszerzési kategória hozzáadása
1. Menjen a **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Bizomány > Beszerzési kategóriák** menübe.
2. A Műveleti ablaktáblában kattintson a **Kategóriahierarchia szerkesztése** elemre. Az aktuális beszerzési kategóriák hierarchiája az oldal bal oldalán jelenik meg. Ezzel módosítja a hierarchiát.  
3. A Műveleti ablaktáblában kattintson a **Új kategória-csomópont** elemre. A rendszer alapértelmezés szerint kiválasztja a felső csomópontot. Ha ezzel az eljárással a feladatot útmutatóként futtatja, kattintson a zárolás feloldása gombra, és válasszon másik szülő-csomópontot, amelybe az új csomópontot szeretné beilleszteni. Ezt követően zárolja újra a feladatútmutatót, és kattintson az Új kategória-csomópontra.  
4. Írjon be egy értéket a **Név** mezőbe.
5. Írjon egy értéket a **Leírás** mezőbe.
6. Írjon be egy értéket a **Barátságos név** mezőbe. A baráti név nem kötelező. A kategória keresésekben a kategórianévvel együtt fog megjelenni.  
7. Válassza a **Mentés** lehetőséget.

## <a name="add-products-to-your-new-procurement-category"></a>Termékek hozzáadása az új beszerzési kategóriához
1. Ugorjon a **Beszerzés és forrás > Bizomány >Beszerzési kategóriák** pontra. Jelölje ki az éppen hozzáadott csomópontot. Ha ezt a folyamatot feladat-útmutatóként használja, szükség lehet a feladat-útmutató feloldására a csomópont kiválasztásához.  
2. Váltsa át a **Termékek** szakasz kibontását.
3. Kattintson a **Hozzáadás** gombra a termékek hozzárendeléséhez a beszerzési kategóriához.
4. Válassza ki azokat a termékeket, amelyet hozzá szeretné adni a beszerzési kategóriához.
5. Kattintson a nyílra a termékek **Kiválasztott** táblához való hozzáadásához.
6. Válassza ki az **OK** lehetőséget.
