---
title: Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez
description: Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad95752ce40faaa84747dac9bfbf2887f7a5af42
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444124"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]