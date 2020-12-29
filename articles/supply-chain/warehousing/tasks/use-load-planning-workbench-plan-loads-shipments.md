---
title: Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel
description: Ez a témakör bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c37a98a3728cb1233a6e1207975a6b8f23f8120d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429898"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Rakományok és szállítmányok tervezése a Rakománytervezési munkaterülettel

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan használható a rakománytervezési munkaterület egy értékesítési rendeléshez kapcsolódó rakomány létrehozásához. Előfeltételként létrehozzuk az értékesítési rendelést először. Ez az eljárás a szállítási koordinátor napi munkájának része. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-sales-order"></a>Értékesítési rendelés létrehozása
1. Ugorjon a **Navigációs ablaktábla > Modulok > Kintlévőségek > Megrendelések > Minden értékesítési megrendelés** lehetőségre.
2. Válassza az **Új** lehetőséget.
3. A **Vevői számla** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Válassza ki az **US-004** fiókot.
5. Válassza ki az **OK** lehetőséget.
6. A **Cikkszám** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Válassza ki a **A0001** tételt. Az **A0001** engedélyezve van a szállításkezelési folyamathoz.  
8. A **Hely** mezőben kattintson a legördítő gombra a keresőlista megnyitásához, majd válasszon egy tételt.
9. Adjon meg egy számot a **Mennyiség** mezőben.
10. A **Raktár** mezőben ennél a példánál adja meg a „24” értéket. A szállításkezelés és speciális raktárkezelés engedélyezve van ehhez a raktárhoz.  
11. Válassza a **Mentés** lehetőséget.
12. Zárja be a lapot.

## <a name="create-a-new-load"></a>Hozzon létre egy új rakományt
1. Ugorjon a **Navigációs ablaktábla > Modulok > Szállításkezelés > Tervezés > Rakománytervezés munkaterülete** lehetőségre.
2. Válassza ki az **Eladási sorok** fület. Ön most létrehozza a terhelést az újonnan létrehozott értékesítési rendeléshez. Rakományok építhetők kínálat és kereslet alapján beszerzési rendelésekből, átmozgatási rendelésekből és értékesítési rendelésekből.  
3. A Műveleti ablaktáblán válassza ki a **Kínálat és kereslet** lehetőséget.
4. Válassza ki az **Új rakományba** lehetőséget.
5. A **Sablonazonosító betöltése** mezőben kattintson a legördítő gombra a keresőlista megnyitásához. A Rakomány sablon meghatározza a teljes rakomány súlyának és térfogatának maximális mértékét. Például a rakomány sablon jelentheti a konténer vagy teherautó méretét. Válasszon ki egy cikket.
6. Válassza ki az **OK** lehetőséget.

## <a name="rate-and-route-the-load"></a>A rakomány díjazása és útvonaltervezése
1. Válassza ki a **Minősítés és útvonaltervezés** lehetőséget.
2. Válassza ki az **Útvonal-díj munkaterület** lehetőséget.
3. Válassza ki a **Díjközpont** lehetőséget.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. Válassza ki a **Hozzárendelés** lehetőséget.
6. Zárja be a lapot.

