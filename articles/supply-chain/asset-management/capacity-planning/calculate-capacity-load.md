---
title: Kapacitásterhelés kiszámítása
description: Ez a cikk bemutatja, hogyan lehet kiszámítani a kapacitásterhelést az eszközkezelésben.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 95d1e38db8e4658a57f36139836264b87d525e61
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016130"
---
# <a name="calculate-capacity-load"></a>Kapacitásterhelés kiszámítása

[!include [banner](../../includes/banner.md)]


Az Eszközkezelés modulban kiszámíthatja a kapacitás terhelését a következőn:

- karbantartási ütemezési sorok  
- még nem ütemezett munkarendelések  
- ütemezett munkarendelések

Ez akkor lehet hasznos, ha egy adott időszakra vonatkozóan szeretne áttekintést kapni a várható kapacitáskihasználásról. A kapacitás terhelésének számítása minden tárgyi eszköznél vagy a kiválasztott tárgyi eszközön végezhető el. Számításokat végezhet a karbantartási állásidők vagy a munkavégzési gyűjtők esetében is.

1. **·** > **·** > **·** **·** > **·** > **·** / **Kattintson** az Eszközkezelés – Kapacitásterhelés lekérdezése vagy Az Eszközkezelés munkarendelések > Minden munkarendelési pool aktív munkarendelési > > Kapacitásterhelés listában válassza ki a **munkarendelési** készletet, **·** > **·** > **·** / **·** **vagy az Eszközkezelés - karbantartás - leállási tevékenységek minden karbantartási leállási tevékenység > Válasszon karbantartási tevékenységet a > Kapacitásterhelés** gomb listájában.

2. A **Kapacitásterhelés kiszámítása** párbeszédablakban válasszon ki egy időszakot a számításhoz a **Kezdő dátum/idő** és a **Záró dátum/idő** mezőben.

3. Ha a számításban szerepeltetni szeretné a karbantartási ütemezés sorait, válassza az „Igen” beállítást a **Karbantartási ütemezés befoglalása** gombbal.

4. Ha a számításban szerepeltetni szeretné a munkarendelés feladatokat, válassza az „Igen” beállítást a **Munkarendelés befoglalása** gombbal.

5. A **Szint** mezőben adhatja meg, hogy a kapacitásterhelési sorok milyen részletesen jelenítse meg a munkavégzési helyszíneket. 

    Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a karbantartási ütemezés minden munkavégzési helyszínhez tartozó sora és munkarendelése a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. 
    
    Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a karbantartási ütemezési minden sorát és minden munkarendelést megjelenít az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

6. Kattintson az **OK** gombra az számítás indításához.

7. A **Csoportosítási szempont...** csoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A lenti képen a kiválasztott **Csoportosítási szempont** gombokat kék színnel kiemeli a program. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

    ![1. ábra](media/01-capacity-planning.png)

>[!NOTE]
>Ha csak az ütemezett munkarendelésekre vonatkozó kapacitástervezésre szeretne koncentrálni, lásd: [Kapacitásterhelés számítása ütemezett munkarendeléseken](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]