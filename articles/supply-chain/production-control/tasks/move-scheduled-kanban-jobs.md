--- 
title: "Beütemezett kanbanfeladatok mozgatása"
description: "Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a>Beütemezett kanbanfeladatok mozgatása

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás a tervezett kanbanfeldolgozási feladatok másik időszakra történő áthelyezésével foglalkozik. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás a kanbanokkal dolgozó üzemirányítási felügyelő vagy termeléstervező munkáját segíti.


## <a name="select-scheduled-kanban-jobs"></a>Beütemezett kanbanfeladatok kiválasztása
1. Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.
2. !MtCMR!A Munkacella mezőben kattintson a legördítő nyílra a keresőlista megnyitásához. áçêìõý !
3. Markér den valgte række på listen.
    * Jelölje ki az 1250 munkacellát.  
4. Klik på Select.
5. Vælg 'Planlagt' i feltet Display job status.
    * Ez úgy szűri a feladatok listáját, hogy csak az ütemezett kanbanfeladatok jelennek meg.  

## <a name="move-kanban-jobs-to-a-different-period"></a>Kanbanfeladatok áthelyezése egy másik tervezési időszakba
1. Find og vælg den ønskede post på listen.
    * Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a Tervezett időszakban 2012. december 20-ra tervezett feladatot. Majd helyezze át a feladatot az előző időszakba.  
2. Klik på Previous period.
3. Klik på End.
    * Ezzel a feladat átkerül az előző időszak feladatlistájának végére.  
4. Find og vælg den ønskede post på listen.
    * Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a Tervezett időszakban 2012. december 18-ra tervezett feladatot. Majd helyezze át a feladatot az következő időszakba.  
5. Klik på Next period.
6. Klik på Start.
    * Ezzel a feladat átkerül az előző időszak feladatlistájának elejére.  

## <a name="task-move-a-job-within-a-period"></a>Feladat: Egy feladat áthelyezése időszakon belül
1. Find og vælg den ønskede post på listen.
    * Válasszon egy olyan feladatot, amelynek állapota Tervezett feladat, például a Tervezett időszakban 2012. december 19-ra tervezett feladatot. Majd helyezze át a feladatot az előző időszakon belül.  
2. Klik på Forward.
    * Figyelje meg, hogy a feladat egy sorral lentebb került a listán.  
3. Klik på Backward.
    * Figyelje meg, hogy a feladat egy sorral fentebb került a listán.  


