---
title: Költségösszegzési irányelv létrehozása
description: Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff37655150596a4be8088e20b43f626f97262aba
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3137845"
---
# <a name="create-a-cost-rollup-policy"></a>Költségösszegzési irányelv létrehozása

[!include [banner](../../includes/banner.md)]

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

