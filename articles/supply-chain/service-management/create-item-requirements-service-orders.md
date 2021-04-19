---
title: Cikkszükséglet létrehozása szervizrendelésekhez
description: A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 650d02d2160757d9629e4deb1e9217c85e9d01df
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831626"
---
# <a name="create-item-requirements-for-service-orders"></a>Cikkszükséglet létrehozása szervizrendelésekhez 

[!include [banner](../includes/banner.md)]


Létrehozhat egy szervizrendelést a vevőknek nyújtott szolgáltatások kezelésére és nyomon követésére. A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége. Egy cikkszükséglet azonnali felhasználása történhet közvetlenül a készletből, vagy kezdeményezhető termelési megrendelés az adott cikkre.

Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.

Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik. Egy cikkszükséglet szervizrendelésben való létrehozásához szükséges, hogy a szervizrendelés egy kapcsolódó projekthez társuljon. Miután létrehozta a cikkszükségletet egy szervizrendeléshez, a cikkszükséglet megtekintheti a kiválasztott projekthez kapcsolódó **Projektek** képernyőn.

## <a name="create-an-item-requirement-for-a-service-order"></a>Cikkszükséglet létrehozása szervizrendeléshez

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Válassza ki azt a szervizrendelést, amelyhez cikkszükségletet szeretne létrehozni.

3.  A **Műveleti ablaktábla** **Elküldés lapján** kattintson a **Cikkszükséglet** elemre.

4.  A **Cikkszükséglet** képernyőn írja be a kívánt cikkre vonatkozó megfelelő adatokat. További információk az adott mezőkről: [Cikkszükséglet (képernyő)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))..

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Cikkszükséglet létrehozása szolgáltatási szerződéshez

1.  Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.

2.  Nyissa meg azt a szolgáltatási szerződést, amelyhez cikkszükségletet szeretne létrehozni.

3.  A **Sorok** gyorslapon kattintson a **Hozzáadás** lehetőségre egy új sor létrehozásához.

4.  Válassza ki a **Cikk** elemet a **Tranzakció típusa** mezőben.

5.  A **Cikk beállítása** mezőben válassza ki a **Cikkszükséglet** elemet.

6.  A **Cikkszám** mezőben válassza ki a szolgáltatási szerződéshez szükséges cikket.

7.  A **Sor adatai** gyorslapon, a **Termékdimenziók** lapon a **Hely** mezőben válassza ki a cikkhez tartozó a készlethelyet.

8.  A szolgáltatásiszerződés-sorból szervizrendelés létrehozásához a **Sorok** gyorslapon kattintson a **Szervizrendelések létrehozása** elemre, majd a **Szervizrendelések létrehozása** képernyőn adja meg a lényeges adatokat. 


## <a name="see-also"></a>Lásd még

[Szervizrendelések automatikus létrehozása](create-service-orders-automatically.md).

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]