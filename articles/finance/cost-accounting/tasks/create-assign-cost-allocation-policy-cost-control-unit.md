---
title: Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez
description: Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez.
author: twheeloc
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5082f4e80958ddb1e4a79bfe46df4a621f10fc40
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734247"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Költségfelosztási irányelv létrehozása egy költségellenőrző-egységhez

[!include [banner](../../includes/banner.md)]

Ezzel az eljárással létrehozhat és hozzárendelhet egy költségfelosztási irányelvet és a kapcsolódó szabályokat egy költségellenőrző egységhez. Ez a felvétel az USP2 bemutató vállalati adatait használja.


## <a name="create-a-policy"></a>Irányelv létrehozása
1. Menjen a Költségfelosztási **irányelvek > a > irányelveihez**.
2. Kattintson az **Új** elemre.
3. A Házirend **neve mezőbe** írjon be egy értéket.
4. A Költségobjektum **dimenzióhierarchia mezőben** adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a szervezetet.  
5. A Statisztikai **dimenzió mezőben** adjon meg vagy válasszon ki egy értéket.
6. Kattintson a **Mentés** gombra.

## <a name="create-allocation-rules"></a>Felosztási szabályok létrehozása
1. Kattintson az **Új** elemre.
2. A listában jelölje meg a kiválasztott sort.
3. A Költségobjektum-dimenzió **hierarchia csomópont mezőjében** adjon meg vagy válasszon ki egy értéket.
4. A Költség viselkedése **mezőben** válassza az "Összesen" lehetőséget.
5. Írjon be **vagy** válasszon ki egy értéket a Felosztás alapmezőben.
6. Kattintson az **Új** elemre.
7. A listában jelölje meg a kiválasztott sort.
8. A Költségobjektum-dimenzió **hierarchia csomópont mezőjében** adjon meg vagy válasszon ki egy értéket.
9. A Költség viselkedése **mezőben** válassza az "Összesen" lehetőséget.
10. Írjon be **vagy** válasszon ki egy értéket a Felosztás alapmezőben.
11. Kattintson az **Új** elemre.
12. A listában jelölje meg a kiválasztott sort.
13. A Költségobjektum-dimenzió **hierarchia csomópont mezőjében** adjon meg vagy válasszon ki egy értéket.
14. A Költség viselkedése **mezőben** válassza az "Összesen" lehetőséget.
15. Írjon be **vagy** válasszon ki egy értéket a Felosztás alapmezőben.
    * Folytassa, amíg létrehozza az összes szabályt.  
16. Kattintson a **Mentés** gombra.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Irányelv hozzárendelése egy költség-ellenőrzőegységhez
1. Kattintson a **Költségellenőrzési egység Irányelv-hozzárendelései hivatkozásra**.
2. Kattintson az **Új** elemre.
3. A listában jelölje meg a kiválasztott sort.
4. Adjon meg **egy** dátumot az Érvényesség a könyvelési dátumtól mezőben.
    * A szabályok naprakészek. Egy felhasználó vagy a rendszer lejártnak minősítheti szabályokat, ha újabb verziót hoz létre.  
5. A Költségellenőrzési **egység mezőben** adjon meg vagy válasszon ki egy értéket.
6. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
