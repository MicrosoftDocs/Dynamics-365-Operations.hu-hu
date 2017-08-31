--- 
title: "Költségösszegzési irányelv létrehozása"
description: "Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
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
ms.openlocfilehash: 51fabc8fe17a45d104be5da806d7076bcf9c5dbb
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-cost-rollup-policy"></a>Költségösszegzési irányelv létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat. Az eljárás létrehozásához az USP2 bemutatóadatokat használtuk.


## <a name="create-a-policy"></a>Irányelv létrehozása
1. Lépjen a Költségkönyvelés > Irányelvek > Költségösszegzési irányelvek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Irányelv neve mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a Költségösszesítés CC lehetőséget.  
6. A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a Költségösszesítés CC lehetőséget.  
7. Kattintson a Mentés gombra.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Költségösszegzési irányelv szabályainak létrehozása
1. Kattintson az Új lehetőségre.
2. A listában jelölje meg a kiválasztott sort.
3. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a 007 lehetőséget.  
4. A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a Költségösszesítés CE lehetőséget.  
5. A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.
    * Ebben a példában rendelje a CC-007 másodlagos költségösszetevőt a költséghelyhez.  
6. Kattintson az Új lehetőségre.
7. A listában jelölje meg a kiválasztott sort.
8. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a 008 lehetőséget.  
9. A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a Költségösszesítés CE lehetőséget.  
10. A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.
    * Ebben a példában rendelje a CC-008 másodlagos költségösszetevőt a költséghelyhez.  
11. Kattintson az Új lehetőségre.
12. A listában jelölje meg a kiválasztott sort.
13. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a 009 lehetőséget.  
14. A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a Költségösszesítés CE lehetőséget.  
15. A Másodlagos költségösszetevő mezőben adjon meg vagy válasszon ki egy értéket.
    * Ebben a példában rendelje a CC-009 másodlagos költségösszetevőt a költséghelyhez.  
    * Folytassa, amíg minden költséghely a hozzá tartozó másodlagos költségösszetevőhöz van rendelve.  
16. Kattintson a Mentés gombra.


