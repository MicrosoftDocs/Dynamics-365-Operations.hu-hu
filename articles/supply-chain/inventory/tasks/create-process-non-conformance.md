---
title: Szabálytalanság létrehozása és feldolgozása
description: Ez a témekör ismerteti, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4525e79cb388cc9bbcfe1d038a53cf53916a678c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008079"
---
# <a name="create-and-process-a-conformance"></a>Szabálytalanság létrehozása és feldolgozása

[!include [banner](../../includes/banner.md)]

Ez a témekör ismerteti, hogy hogyan hajtsa végre a szabálytalanság kezelését, a meglévő minőségi rendelés alapján. Ezt a felvételt futtathatja az USMF bemutató vállalatban, és használhatja a javasolt értékeket. Ezt az eljárást általában a minőségi adminisztrátor végzi.  Előfeltételként hajtsa végre a következő utasításait: [Áruk minőségének vizsgálata](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md). A szabálytalanság jóváhagyásának feldolgozását a feladat rögzítését futtató felhasználónak rendelkeznie kell hozzárendelt „Név” értékkel a Felhasználók lapon. A dokumentummegjegyzések használatához a felhasználónak rendelkeznie kell a Dokumentumkezeléssel, amelyet a felhasználói beállításokban kell aktiválni.


## <a name="select-a-quality-order"></a>Minőségi rendelés kiválasztása
1. A navigációs ablaktáblán lépjen a **Modulok > Készletgazdálkodás > Időszakos feladatok > Minőségkezelés > Minőségi rendelések** részre.
2. A listában válassza ki az itt létrejött minőségi rendelést: [Áruk minőségénak vizsgálata](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).  

## <a name="create-a-nonconformance"></a>Kattintson a Szabálytalanság létrehozása elemre.
1. A műveleti panelen válassza a **Lekérdezések** elemet.
2. Válassza a **Szabálytalanságok** elemet.
3. Válassza az **Új** lehetőséget.
4. A **Probléma típusa** mező legördülő menüjében válassza ki az ellenőrzési folyamat során talált problémát.  
5. Válassza ki az **OK** lehetőséget.

## <a name="approvereject-a-nonconformance"></a>Szabálytalanság jóváhagyása/elutasítása
1. Válassza a **Funkciók** lehetőséget.
2. Válassza a **Szabálytalanság jóváhagyása** elemet. Ebben a példában hagyja jóvá a szabálytalanságot. A jóváhagyott szabálytalanságokat társíthatja a kapcsolódó műveletekhez az olyan munka rögzítése érdekében, amely a szabálytalanság kezelésének része, illetve a javítás kezelési feldolgozásának a része, ahogy ebben a témakörben.  
3. Válassza ki az **Igen** lehetőséget.

## <a name="create-a-correction-action"></a>Javító művelet létrehozása
1. Válassza a **Helyesbítések** elemet.
2. Válassza az **Új** lehetőséget.
3. Az új sor **Személyzeti szám** mezőjében válassza ki a kívánt rekordot a legördülő menüből.
4. Kattintson a **Kiválasztás** lehetőségre.
5. Válassza a **Csatolás** elemet. Hozzon létre egy megjegyzést a javításhoz. Ebben a példában a művelet a szállítóval való kapcsolatfelvétel a szabálytalansági eset megvitatása céljából.  
6. Válassza az **Új** lehetőséget.
7. Válassza a **Megjegyzés** lehetőséget. A jelentés beállításától függően a különféle dokumentumtípusokat kinyomtathatja a szabálytalanság kezeléséhez kapcsolódó jelentéseken.  
8. Írjon egy értéket a **Leírás** mezőbe.
9. Zárja be a lapot.

## <a name="maintain-a-correction"></a>Korrekció kezelése
1. Válassza a **Megjelölés készként** lehetőséget.
2. Válassza ki az **OK** lehetőséget.
3. Zárja be a lapot.

## <a name="close-a-nonconformance"></a>Szabálytalanság lezárása
1. Válassza a **Funkciók** lehetőséget.
2. Válassza a **Szabálytalanság lezárása** elemet.
3. Válassza ki az **Igen** lehetőséget.
4. Zárja be a lapokat.
