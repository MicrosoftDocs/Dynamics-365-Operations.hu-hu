---
title: Költségösszegzési irányelv létrehozása
description: Ez az eljárás bemutatja, hogyan hozhat létre költségösszegzési irányelvet, valamint a hozzá tartozó szabályokat.
author: panolte
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfadde13c4bed494f6cd7ef63ed0ed6bf996ac61
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714229"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
