---
title: Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése
description: Ez az eljárás a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezésére összpontosít.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 4932cfa472c34a16249b226aa4a07b8e5f528053
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838487"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Művelet- és feladatütemezéssel rendelkező termelési rendelés ütemezése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás a műveletütemezés és feladatütemezés termelési rendeléseinek ütemezésére összpontosít. Nem jön létre feladat műveletütemezéssel ugyanakkor feladatütemezéssel létrehozhatók feladatok. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként. Ez az eljárás az elkülönített gyártási környezetben dolgozó termelésvezető, gyártástervező vagy az üzemirányítási felügyelő munkáját segíti.


## <a name="create-a-production-order"></a>Termelési rendelés létrehozása
1. Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.
2. Kattintson az Új termelési rendelés lehetőségre.
3. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a D0001 cikkszámot.  
4. Kattintson a Létrehozás lehetőségre.

## <a name="schedule-operations-for-the-production-order"></a>Termelési rendelés műveleteinek ütemezése
1. A listában jelölje meg a kiválasztott sort.
    * Jelölje ki az imént létrehozott termelési rendelést. A lista tetején kell lennie.      
2. A Művelet panelen kattintson az Ütemezés elemre.
3. Kattintson a Műveletek ütemezése lehetőségre.
4. Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól előre” lehetőséget.
5. Adjon meg egy dátumot az Ütemezési dátum mezőben.
    * Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet. Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.  
6. Kattintson az OK gombra.
7. A listában jelölje meg a kiválasztott sort.
    * Ügyeljen rá, hogy a termelés állapota az Ütemezve értékre változik.  
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Kattintson a Minden feladat elemre.
    * Vegye figyelembe, hogy műveletütemezéssel nem hozható létre feladat.  
10. Zárja be a lapot.

## <a name="schedule-jobs-for-the-production-order"></a>Termelési rendelés feladatainak ütemezése
1. A Művelet panelen kattintson az Ütemezés elemre.
2. Kattintson a Feladatok ütemezése lehetőségre.
3. Az Ütemezés iránya mezőben válassza ki a „Szállítási dátumtól előre” lehetőséget.
4. Adjon meg egy dátumot az Ütemezési dátum mezőben.
    * Jelöljön ki egy jövőbeli dátumot például a mai naphoz egy hetet. Az kiválasztott ütemezési iránnyal a termelési rendelés az aktuális dátumtól előre lesz ütemezve.  
5. Kattintson az OK gombra.
6. A Művelet panelen kattintson a Termelési rendelés elemre.
7. Kattintson a Minden feladat elemre.
    * Vegye figyelembe, hogy az aktív útvonal alapján a feladatütemezéssel 5 feladat jött létre.  

