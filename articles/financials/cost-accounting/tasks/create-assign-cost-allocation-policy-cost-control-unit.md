--- 
title: "Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez"
description: "Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 82319d8d9c7b567f98dfd0e591cb99079fb577b7
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez. Ez a felvétel az USP2 bemutató vállalati adatait használja.


## <a name="create-a-policy"></a>Irányelv létrehozása
1. Lépjen a Költségkönyvelés > Irányelvek > Költségfelosztási irányelvek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Irányelv neve mezőbe.
4. A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a szervezetet.  
5. A Statisztikai dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
6. Kattintson a Mentés gombra.

## <a name="create-allocation-rules"></a>Felosztási szabályok létrehozása
1. Kattintson az Új lehetőségre.
2. A listában jelölje meg a kiválasztott sort.
3. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
4. Válassza az Összes lehetőséget a Költség működése mezőben.
5. A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.
6. Kattintson az Új lehetőségre.
7. A listában jelölje meg a kiválasztott sort.
8. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
9. Válassza az Összes lehetőséget a Költség működése mezőben.
10. A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.
11. Kattintson az Új lehetőségre.
12. A listában jelölje meg a kiválasztott sort.
13. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
14. Válassza az Összes lehetőséget a Költség működése mezőben.
15. A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.
    * Folytassa, amíg létrehozza az összes szabályt.  
16. Kattintson a Mentés gombra.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Irányelv hozzárendelése egy költség-ellenőrzőegységhez
1. Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.
    * A szabályok naprakészek. Egy felhasználó vagy a rendszer lejártnak minősítheti szabályokat, ha újabb verziót hoz létre.  
5. A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.
6. Kattintson a Mentés gombra.


