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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8eb19ac9ded4dc2a091ff733f2f43cb6cafa1b43
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="monitor-a-master-planning-run"></a>Alaptervezés futtatásának megfigyelése

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


