---
title: Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez
description: A költségműködés a költségek fix vagy változó osztályozása.
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
ms.openlocfilehash: 16d9dceb4c2a22eab9a5ecb8501393444f20498b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187820"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez

[!include [task guide banner](../../includes/task-guide-banner.md)]

A költségműködés a költségek fix vagy változó osztályozása. Az irányelvet és a megfelelő szabályokat hozzá kell rendelni egy költségellenőrző egységhez az irányelv hatályba lépése érdekében. Ezzel az eljárással létrehozhat egy irányelvet, majd hozzárendelheti az irányelvet egy költségellenőrző egységhez.


## <a name="create-a-cost-behavior-hierarchy"></a>Költségműködési hierarchia létrehozása
1. Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.
2. Kattintson az Új lehetőségre.
3. Kattintson a Létrehozás lehetőségre.
4. A Dimenzióhierarchia neve mezőbe írja be a következőt: „Költségműködés hierarchiája”.
5. A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a Költségösszetevőket.  
6. Kattintson a Mentés gombra.
7. Kattintson a Hierarchia megtekintése lehetőségre.
8. Kattintson az Új lehetőségre.
9. Írjon be egy értéket a Csomópont mezőbe.
    * Adja meg a Rögzített költséget.  
10. A fán jelölje be a „Költségműködés hierarchiája” lehetőséget.
11. Kattintson az Új lehetőségre.
12. Írjon be egy értéket a Csomópont mezőbe.
    * Adja meg a Változó költséget.  
13. Kattintson a Mentés gombra.
14. A fán jelölje be a „Költségműködés hierarchiája\Rögzített költség” lehetőséget.
15. Kattintson az Új lehetőségre.
16. A listában jelölje meg a kiválasztott sort.
17. A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.
    * A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.  
18. A Céldimenziótag mezőben adjon meg, vagy válasszon ki egy értéket.
    * A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.  
19. A fán jelölje be a „Költségműködés hierarchiája\Változó költség” lehetőséget.
20. Kattintson az Új lehetőségre.
21. A listában jelölje meg a kiválasztott sort.
22. A Forrásdimenzió-tag mezőben adjon meg vagy válasszon ki egy értéket.
    * A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.  
23. A Céldimenziótag mezőben adjon meg, vagy válasszon ki egy értéket.
    * A dimenziótagok tartománya tartalmazhat szüneteket, de a tagok nem lehetnek átfedésben.  
24. Kattintson a Mentés gombra.

## <a name="create-the-policy-and-rules"></a>Az irányelv és a szabályok létrehozása
1. Ugorjon a Költségkönyvelés > Irányelvek > Költségműködési irányelvek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Irányelv neve mezőbe.
4. A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a most létrehozott irányelvhierarchiát.  
5. A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a szervezetet.  
6. Kattintson a Mentés gombra.
7. Kattintson az Új lehetőségre.
8. A listában jelölje meg a kiválasztott sort.
9. A Költségösszetevő dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Bontsa ki a hierarchiát a Változó költség kiválasztásához.  
10. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * Alapértelmezés szerint a változó százalékos értéke 100 százalék.  
11. Kattintson a Költség-ellenőrzőegység irányelv-hozzárendelései lehetőségre.
12. Kattintson az Új lehetőségre.
13. A listában jelölje meg a kiválasztott sort.
14. Adja meg a dátumot az Érvényesség kezdete a könyvelés dátumától mezőben.
    * A szabályok naprakészek, és egy felhasználó vagy a rendszer is lejárthat minősíthet egy szabályt, ha annak újabb verziója jön létre.  
15. A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.
16. Kattintson a Mentés gombra.

