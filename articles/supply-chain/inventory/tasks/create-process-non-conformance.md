---
title: "Szabálytalanság létrehozása és feldolgozása"
description: "Ezekkel a lépésekkel végrehajthatja a szabálytalanság kezelését, a meglévő minőségi rendelés alapján."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e5187c44aac881273900b2fc0ca91045a65cd838
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-process-a-conformance"></a>Szabálytalanság létrehozása és feldolgozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ezekkel a lépésekkel végrehajthatja a szabálytalanság kezelését, a meglévő minőségi rendelés alapján. Ezt a felvételt futtathatja az USMF bemutató vállalatban, és használhatja a javasolt értékeket. Ezt az eljárást általában a minőségi adminisztrátor végzi.  Előfeltételként futtassa az „Áruk minőségének vizsgálata” feladatrögzítést. A szabálytalanság jóváhagyásának feldolgozását a feladat rögzítését futtató felhasználónak rendelkeznie kell hozzárendelt „Név” értékkel a Felhasználók lapon. A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.


## <a name="select-a-quality-order"></a>Minőségi rendelés kiválasztása
1. Ugrás a Minőségi rendelések elemhez.
2. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a „Vizsgálja meg az áruk minőségét” tevékenységfelvétel alapján létrejött minőségi rendelést.  

## <a name="create-a-nonconformance"></a>Kattintson a Szabálytalanság létrehozása elemre.
1. Kattintson a Lekérdezések elemre.
2. Kattintson a Szabálytalanságok elemre.
3. Kattintson az Új lehetőségre.
4. A Probléma típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki az ellenőrzési eljárás során található problémát.  
5. A Probléma típusa mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Kattintson az OK gombra.

## <a name="approvereject-a-nonconformance"></a>Szabálytalanság jóváhagyása/elutasítása
1. Kattintson a Funkciók elemre.
2. Kattintson A szabálytalanság jóváhagyása elemre.
    * Ebben a példában hagyja jóvá a szabálytalanságot. A jóváhagyott szabálytalanságokat társíthatja a kapcsolódó műveletekhez az olyan munka rögzítése érdekében, amely a szabálytalanság kezelésének része, illetve a javítás kezelési feldolgozásának a része.  
3. Kattintson az Igen gombra.

## <a name="create-a-correction-action"></a>Javító művelet létrehozása
1. Kattintson a Korrekciók elemre.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. A Személyes szám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson a Kiválasztás lehetőségre.
7. Kattintson a Csatolás elemre.
    * Hozzon létre egy megjegyzést a javításhoz. Ebben a példában a művelet a szállítóval való kapcsolatfelvétel a szabálytalansági eset megvitatása céljából.  
8. Kattintson az Új lehetőségre.
9. Kattintson a Megjegyzés elemre.
    * Ne feledje, hogy a jelentés beállításától függően a különféle dokumentumtípusokat kinyomtathatja a szabálytalanság kezeléséhez kapcsolódó jelentéseken.  
10. A Leírás mezőben adjon meg egy értéket.
11. Zárja be a lapot.

## <a name="maintain-a-correction"></a>Korrekció kezelése
1. Kattintson a Befejezés jelölése gombra.
2. Kattintson az OK gombra.
3. Zárja be a lapot.

## <a name="close-a-nonconformance"></a>Szabálytalanság lezárása
1. Kattintson a Funkciók elemre.
2. Kattintson A szabálytalanság lezárása elemre.
3. Kattintson az Igen gombra.
4. Zárja be a lapot.
5. Zárja be a lapot.

