--- 
title: "Alaptervezés futtatásának megfigyelése"
description: "A termeléstervező látni szeretné, ha valamelyik alaptervezési futtatás folyamatban van."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="monitor-a-master-planning-run"></a>Alaptervezés futtatásának megfigyelése

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

A termeléstervező látni szeretné, ha valamelyik alaptervezési futtatás folyamatban van. Az USMF bemutatócég segítségével végezze el ezt az eljárást.


## <a name="run-master-planning"></a>Alaptervezés futtatása
1. Kattintson az Alaptervezés parancsra.
    * Ezt az alapértelmezett irányítópulton fogja megtalálni.  
2. A Terv mezőben adjon meg vagy válasszon ki egy értéket.
    * Példa: StaticPlan  
3. Kattintson a Futtatás elemre.
4. Válassza az Igen lehetőséget a Követés feldolgozási ideje mezőben.
    * Ha a mező már be van jelölve, hagyja ki ezt a lépést.  
5. Adjon meg egy számot a Szálak száma mezőben.
6. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
7. Kattintson a Szűrő parancsra.
8. A listában jelölje meg a kiválasztott sort.
    * Jelölje be a sort, ahol Mező = Cikk száma.  
9. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
    * Példa: T0001  
10. Kattintson az OK gombra.
11. Kattintson az OK gombra.

## <a name="monitor-the-master-planning-run"></a>Az Alaptervezés futtatásának megfigyelése
1. Kattintson az előzmények lehetőségre.
2. Kattintson a Lekérdezések elemre.
3. Kattintson a Folyamatbeli tevékenység időtartama lehetőségre.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Minden egyes cikkre vonatkozóan áttekintést kaphat arról, hogy mennyi ideig tart az egyes tervezési lépések elvégzése.  


