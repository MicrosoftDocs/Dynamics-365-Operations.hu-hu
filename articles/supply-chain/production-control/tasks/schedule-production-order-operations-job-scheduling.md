---
title: Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése
description: Ez a témakör a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezését ismerteti.
author: ChristianRytt
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3023d6a6fe09c84b47839a2c4b78c37907754ded
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914884"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a témakör a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezését ismerteti. Nem jön létre feladat műveletütemezéssel ugyanakkor feladatütemezéssel létrehozhatók feladatok. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként. Ez az eljárás az elkülönített gyártási környezetben dolgozó termelésvezető, gyártástervező vagy az üzemirányítási felügyelő munkáját segíti.


## <a name="create-a-production-order"></a>Termelési rendelés létrehozása
1. A navigációs ablaktáblán ugorj a **Modulok > Gyártásvezérlés > Termelési rendelések > Minden termelési rendelés**.
2. Válassza ki az **Új termelési rendelés** elemet.
3. Az **Cikkszám** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki a **D0001** cikkszámot.  
4. Válassza a **Létrehozása** lehetőséget.

## <a name="schedule-operations-for-the-production-order"></a>Termelési rendelés műveleteinek ütemezése
1. Jelölje meg az újonnan létrehozott sort.      
2. A műveleti ablaktáblán válassza ki az **Ütemezés** lehetőséget.
3. Válassza ki a **Műveletek ütemezése lehetőséget**.
4. Az **Ütemezés iránya** mezőben válassza ki a **Szállítási dátumtól előre** lehetőséget.
5. Adjon meg egy dátumot az **Ütemezési dátum** mezőben. Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet. Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.  
6. Válassza ki az **OK** lehetőséget.
7. A listában jelölje meg a kiválasztott sort. Ügyeljen rá, hogy a termelés állapota az **Ütemezve** értékre változik. 
8. Válassza ki a **Minden feladat** elemet. Vegye figyelembe, hogy műveletütemezéssel nem hozható létre feladat.  
9. Zárja be a lapot.

## <a name="schedule-jobs-for-the-production-order"></a>Termelési rendelés feladatainak ütemezése
1. A műveleti ablaktáblán válassza ki az **Ütemezés** lehetőséget.
2. Válassza ki a **Feladatok ütemezése** lehetőséget.
3. Az **Ütemezés iránya** mezőben válassza ki a **Szállítási dátumtól előre** lehetőséget.
4. Adjon meg egy dátumot az **Ütemezési dátum** mezőben. Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet. Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.  
5. Válassza ki az **OK** lehetőséget.
6. A műveleti ablaktáblán válassza ki a **Termelési rendelés** elemet.
7. Válassza ki a **Minden feladat** elemet. Vegye figyelembe, hogy az aktív útvonal alapján a feladatütemezéssel 5 feladat jött létre.  

