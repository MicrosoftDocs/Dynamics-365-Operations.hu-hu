---
title: Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez
description: A költségműködés a költségek fix vagy változó osztályozása.
author: twheeloc
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 653bfb69c4ca118c700755cb95a6b349d2c6bbad
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735142"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez

[!include [banner](../../includes/banner.md)]

A költségműködés a költségek fix vagy változó osztályozása. Az irányelvet és a megfelelő szabályokat hozzá kell rendelni egy költségellenőrző egységhez az irányelv hatályba lépése érdekében. Ezzel az eljárással létrehozhat egy irányelvet, majd hozzárendelheti az irányelvet egy költségellenőrző egységhez.


## <a name="create-a-cost-behavior-hierarchy"></a>Költségműködési hierarchia létrehozása
1. Ugrás a Dimenziók **és > dimenziók > dimenzióhierarchiákhoz**.
2. Kattintson az **Új** elemre.
3. Kattintson az **Új** > lehetőségre.
4. A Dimenzióhierarchia **neve** mezőbe írja be a "Költség viselkedése".
5. A Dimenzió **mezőben** adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a Költségösszetevőket.  
6. Kattintson a **Mentés** gombra.
7. Kattintson a Hierarchia **megtekintése elemre**.
8. Kattintson az **Új** elemre.
9. A Csomópont **neve** mezőbe írjon be egy értéket.
    * Adja meg a Rögzített költséget.  
10. A fán jelölje be a „Költségműködés hierarchiája” lehetőséget.
11. Kattintson az **Új** elemre.
12. A Csomópont **neve** mezőbe írjon be egy értéket.
    * Adja meg a Változó költséget.  
13. Kattintson a **Mentés** gombra.
14. A fán jelölje be a „Költségműködés hierarchiája\Rögzített költség” lehetőséget.
15. Kattintson az **Új** elemre.
16. A listában jelölje meg a kiválasztott sort.
17. Adjon meg **vagy válasszon ki egy értéket a From dimenziótag** mezőben.
    * A dimenziótagok tartománya hiányokat tartalmazhat, de a tagok nem fedhetik át egymást.  
18. A To dimenziótag **mezőben** adjon meg vagy válasszon ki egy értéket.
    * A dimenziótagok tartománya hiányokat tartalmazhat, de a tagok nem fedhetik át egymást.  
19. A fán jelölje be a „Költségműködés hierarchiája\Változó költség” lehetőséget.
20. Kattintson az **Új** elemre.
21. A listában jelölje meg a kiválasztott sort.
22. Adjon meg **vagy válasszon ki egy értéket a From dimenziótag** mezőben.
    * A dimenziótagok tartománya hiányokat tartalmazhat, de a tagok nem fedhetik át egymást.  
23. A To dimenziótag **mezőben** adjon meg vagy válasszon ki egy értéket.
    * A dimenziótagok tartománya hiányokat tartalmazhat, de a tagok nem fedhetik át egymást.  
24. Kattintson a **Mentés** gombra.

## <a name="create-the-policy-and-rules"></a>Az irányelv és a szabályok létrehozása
1. Menjen a Költségkönyvelés **> irányelvei > szabályokhoz**.
2. Kattintson az **Új** elemre.
3. A Házirend **neve mezőbe** írjon be egy értéket.
4. A Költségelem **dimenzióhierarchia mezőben** adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a most létrehozott irányelvhierarchiát.  
5. A Költségobjektum **dimenzióhierarchia mezőben** adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a szervezetet.  
6. Kattintson a **Mentés** gombra.
7. Kattintson az **Új** elemre.
8. A listában jelölje meg a kiválasztott sort.
9. A Költségelem **dimenzióhierarchia csomópont mezőjében** adjon meg vagy válasszon ki egy értéket.
    * Bontsa ki a hierarchiát a Változó költség kiválasztásához.  
10. A Költségobjektum-dimenzió **hierarchia csomópont mezőjében** adjon meg vagy válasszon ki egy értéket.
    * Alapértelmezés szerint a változó százalékos értéke 100 százalék.  
11. Kattintson a **Költségellenőrzési egység Irányelv-hozzárendelései hivatkozásra**.
12. Kattintson az **Új** elemre.
13. A listában jelölje meg a kiválasztott sort.
14. Adjon meg **egy** dátumot az Érvényesség a könyvelési dátumtól mezőben.
    * A szabályok naprakészek, és egy felhasználó vagy a rendszer is lejárthat minősíthet egy szabályt, ha annak újabb verziója jön létre.  
15. A Költségellenőrzési **egység mezőben** adjon meg vagy válasszon ki egy értéket.
16. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
