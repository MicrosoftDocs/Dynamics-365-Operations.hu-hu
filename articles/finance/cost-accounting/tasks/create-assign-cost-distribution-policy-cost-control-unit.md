---
title: Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez
description: A Költségfelosztási szabályok segítségével feloszthatja egy kollektív költséghelyen pénzügyileg leltározott költségeket.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9230410d7b8cd4c94fdab5465e542e16fd286c530a8189d5cd1eca825bb1faf4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772851"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez

[!include [banner](../../includes/banner.md)]

A Költségfelosztási szabályok segítségével feloszthatja egy kollektív költséghelyen pénzügyileg leltározott költségeket. A költségkönyvelő meggyőződik arról, hogy a rendszer a költséget a kiválasztott felosztási alap szerint osztja el a költséghelyek között. Az irányelv és a kapcsolódó szabályok a költség-ellenőrzőegységhez vannak rendelve. Ez a feladat-útmutató egy példa segítségével mutatja be a költségfelosztási irányelv és a kapcsolódó szabályok létrehozásást.


## <a name="create-a-policy"></a>Irányelv létrehozása
1. Lépjen a Költségkönyvelés > Irányelvek > Költségfelosztási irányelvek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Irányelv neve mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a szervezetet.  
6. A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a CDS P/L lehetőséget.  
7. A Statisztikai dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza a Statisztikai elemek lehetőséget.  
8. Kattintson a Mentés gombra.

## <a name="create-rules-for-the-policy"></a>Az irányelv szabályainak létrehozása
1. Kattintson az Új lehetőségre.
2. A listában jelölje meg a kiválasztott sort.
3. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Bontsa ki a hierarchiát a 094 kiválasztásához.  
4. A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza az Egyéb működési költségek lehetőséget, majd válassza a 605110 Tisztítás lehetőséget.  
5. A Költség működése mezőben válasszon egy lehetőséget.
    * Válassza a Rögzített költség lehetőséget.  
6. A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.
7. Kattintson az Új lehetőségre.
8. A listában jelölje meg a kiválasztott sort.
9. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Bontsa ki a hierarchiát a 094 kiválasztásához.  
10. A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza az Egyéb működési költségek lehetőséget, majd válassza a 605150 Bérlet lehetőséget.  
11. A Költség működése mezőben válasszon egy lehetőséget.
    * Válassza a Rögzített költség lehetőséget.  
12. A Felosztás alapja mezőben adjon meg vagy válasszon ki egy értéket.
13. Kattintson a Mentés gombra.

## <a name="assign-rules-to-a-cost-control-unit"></a>Szabályok hozzárendelése egy költség-ellenőrzőegységhez
1. Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.
2. Kattintson az Új lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.
    * Válassza ki szeptember 1-jét az érvényes pénzügyi évben.  
5. A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.
6. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]