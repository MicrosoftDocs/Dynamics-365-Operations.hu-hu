--- 
title: "Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel"
description: "Ez az eljárás bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 982c746de1329be435d9047d4057cba100475b1b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához. Előfeltételként létrehozzuk az értékesítési rendelést először. Ez az eljárás a szállítási koordinátor napi munkájának része. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-sales-order"></a>Értékesítési rendelés létrehozása
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Válassza a US-004 fiókot.
5. Kattintson az OK gombra.
6. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Válassza az A0001 elemet.
    * Az A0001 engedélyezve a szállításkezelési folyamathoz.  
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
9. Adjon meg egy számot a Mennyiség mezőben.
10. A Raktár mezőbe írja be a 24 értéket.
    * Ebben a példában válassza ki a 24. raktárat. A szállításkezelés és speciális raktárkezelés engedélyezve van ehhez a raktárhoz.  
11. Kattintson a Mentés gombra.
12. Zárja be a lapot.

## <a name="create-a-new-load"></a>Hozzon létre egy új rakományt
1. Ugorjon a Szállításkezelés > Tervezés > Rakománytervező munkaterület elemre.
2. Kattintson az Értékesítési sorok fülre.
    * Most létrehozza a terhelést az újonnan létrehozott értékesítési rendeléshez. Rakományok építhetők kínálat és kereslet alapján beszerzési rendelésekből, átmozgatási rendelésekből és értékesítési rendelésekből.  
3. A műveleti ablaktáblán kattintson a Kínálat és kereslet elemre.
4. Kattintson az Áthelyezés új rakományba gombra.
5. A Sablonazonosító betöltése mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A Rakomány sablon meghatározza a teljes rakomány súlyának és térfogatának maximális mértékét. Például a rakomány sablon jelentheti a konténer vagy teherautó méretét.  
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Kattintson az OK gombra.

## <a name="rate-and-route-the-load"></a>A rakomány díjazása és útvonaltervezése
1. Kattintson a Minősítés és útvonaltervezés pontra.
2. Kattintson az Útvonaldíj munkaterület pontra.
3. Kattintson a Díjközpont pontra.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. Kattintson a Hozzárendelés gombra.
6. Zárja be a lapot.
7. Zárja be a lapot.


