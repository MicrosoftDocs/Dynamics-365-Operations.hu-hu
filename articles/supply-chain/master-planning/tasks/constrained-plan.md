---
title: Korlátozott terv létrehozása
description: Ez az eljárás bemutatja, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72cddd58b7068e08cddf24df83da8da2f7af7168
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845294"
---
# <a name="generate-a-constrained-plan"></a>Korlátozott terv létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet olyan tervet létrehozni, amely számításba veszi mind az anyagi mind pedig a kapacitásbeli megszorításokat. A terv gondoskodik arról, hogy a gyártás ne induljon el az anyagok elérhetővé válása előtt, és hogy az erőforrások ne legyenek túlfoglalva. 

Ez az eljárás az USMF bemutatócéget használja. Ezt az eljárást a termeléstervező használja.


## <a name="set-up-a-constrained-plan"></a>Korlátozott terv beállítása
1. Kattintson az Alaptervezés parancsra.
2. Kattintson az Alaptervek parancsra.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Példa: StaticPlan  
4. Válassza az Igen lehetőséget a Véges kapacitás mezőben.
5. A Végleges kapacitás időkorlátja mezőbe, írja be: '30'.
6. Bontsa ki az Időkorlátokat a napok szakaszában.
7. Válassza az Igen lehetőséget a Kapacitás mezőben.
8. A Kapacitásütemezési időkorlát (napok) mezőbe írjon be egy számot.
    * Példa: 60  
9. Válassza ki az Igen lehetőséget a Kiszámított késések mezőben.
10. A Kiszámított késések időkorlátja (napok) mezőbe írjon be egy számot.
    * Példa: 60  
11. A Kiszámított késések szakasz kibontása.
12. Válassza ki az Igen lehetőséget a Számított késés hozzáadása a követelménydátumhoz mezőben
13. Válassza ki az Igen lehetőséget a Számított késés hozzáadása a követelménydátumhoz mezőben
14. Válassza ki az Igen lehetőséget a Számított késés hozzáadása a követelménydátumhoz mezőben
15. Zárja be a lapot.

## <a name="create-a-constrained-plan"></a>Korlátozott terv létrehozása
1. Kattintson a Futtatás elemre.
2. Az Alapterv mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki azt a tervet, amelyhez megszorítások állított be.  
3. Kattintson az OK gombra.
    * Ez eltarthat egy ideig.  
4. Kattintson a Tervezett rendelések elemre.

