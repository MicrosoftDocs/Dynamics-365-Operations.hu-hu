---
title: Beütemezett kanbanfeladatok mozgatása
description: Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik.
author: johanhoffmann
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c1b6ea92a1e3b16df6678030957c3fa407c15b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568015"
---
# <a name="move-scheduled-kanban-jobs"></a>Beütemezett kanbanfeladatok mozgatása

[!include [banner](../../includes/banner.md)]

Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás a kanbanokkal dolgozó üzemirányítási felügyelő vagy termeléstervező munkáját segíti.

## <a name="select-scheduled-kanban-jobs"></a>Válasszon ki ütemezett kanbanfeladatokat. 

1. Ugorjon a **Gyártásvezérlés > Kanban > Kanbanfeladat ütemezése** lehetőségre. 

2. A **Munkacella** mezőben kattintson a legördülő menüre a keresőlista megnyitásához. 

3. A listában jelölje meg a kiválasztott sort. 
   - Jelölje ki az 1250 munkacellát. 
4. Kattintson a **Kiválasztás** lehetőségre. 

5. A **Feladatállapot megjelenítése** mezőben válassza ki az **Ütemezett** lehetőséget. Ez úgy szűri a feladatok listáját, hogy csak az ütemezett kanbanfeladatok jelennek meg. 

## <a name="move-kanban-jobs-to-a-different-period"></a>Kanbanfeladatok áthelyezése egy másik tervezési időszakba. 

1. Keresse meg és jelölje ki a kívánt rekordot a listán. Válasszon egy olyan feladatot, amelynek állapota **Tervezett feladat**, például a **Tervezett időszak** mezőben 2012. december 20-ra tervezett feladatot. Majd helyezze át a feladatot az előző időszakba. 

2. Kattintson az **Előző időszak** elemre. 

3. Kattintson a **Vége** gombra, amellyel a feladat átkerül az előző időszak feladatlistájának végére, mint utolsó feladat. 

4. Keresse meg és jelölje ki a kívánt rekordot a listán. Válasszon egy olyan feladatot, amelynek állapota **Tervezett feladat**, például a **Tervezett időszak** mezőben 2012. december 18-ra tervezett feladatot. Majd helyezze át a feladatot az következő időszakba. 

5. Kattintson a **Következő időszak** lehetőségre. 

6. Kattintson a **Kezdete** gombra, amellyel a feladat átkerül a feladatlista elejére, mint az előző időszak első feladata. 

## <a name="move-a-job-within-a-period"></a>Egy feladat áthelyezése időszakon belül. 

1. Keresse meg és jelölje ki a kívánt rekordot a listán. Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a **Tervezett időszak** mezőben 2012. december 19-ra tervezett második feladatot. Majd helyezze át a feladatot az előző időszakon belül. 

2. Kattintson az **Előre** lehetőségre. Figyelje meg, hogy a feladat egy sorral lentebb került a listán. 

3. Kattintson a **Vissza** lehetőségre. Figyelje meg, hogy a feladat egy sorral fentebb került a listán.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]