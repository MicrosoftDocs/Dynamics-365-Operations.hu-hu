--- 
title: "Egy helyre vonatkozó terv létrehozása"
description: "A termeléstervező kiszámítja az anyag és a kapacitásszükségletét egy adott cikk termelésére vonatkozóan."
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
ms.openlocfilehash: d89d34d4d429faf87c70943961f7141a6258d482
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-plan-for-a-site"></a>Egy helyre vonatkozó terv létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

A termeléstervező kiszámítja az anyag és a kapacitásszükségletét egy adott cikk termelésére vonatkozóan. A Forrás javaslatok létrehozása után a rendeléseket azon a telephelyen találja, amelyre vonatkozóan eltervezi és megerősíti a rendeléseket, kezdve a sürgős esetektől. A legtöbb sürgős rendelések azok a rendelések, amelyeket meg kell erősíteni az aktuális napon. Az USMF bemutató vállalati adatainak használatával elvégezheti ezeket a műveleteket.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>Hozzon létre Anyag- és Kapacitástervet egy cikkre vonatkozóan
1. Kattintson az Alaptervezés parancsra.
    * Keresse meg az alapértelmezett irányítópultot.  
2. Kattintson a Futtatás elemre.
3. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
4. Kattintson a Szűrő parancsra.
5. A listában jelölje meg a kiválasztott sort.
6. Érték beírása a Feltétel mezőbe.
    * Példa: D0001  
7. Kattintson az OK gombra.
8. Kattintson az OK gombra.
    * Ez a folyamat eltarthat néhány percig.  
9. Frissítse a lapot..

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>Határozza meg a sürgős tervezett rendeléseket a cikkre vonatkozóan
1. Nyissa meg a cikkszám oszlop szűrőt.
2. Alkalmazzon szűrőt a „Cikkszám” mezőn „D0001” értékkel, az „Ezzel kezdődik” szűrési operátor használatával.
3. Megrendelési dátum oszlopszűrőjének megnyitása.
4. Szűrő alkalmazása a „Rendelés dátuma” mezőben, az aktuális dátum értékével, a „pontosan” szűrési operátor használatával.

## <a name="firm-all-the-urgent-orders-for-the-item"></a>Erősítse meg az összes sürgős tervezett rendelést a cikkre vonatkozóan
1. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
2. Kattintson a Megerősítés gombra.
3. Kattintson az OK gombra.


