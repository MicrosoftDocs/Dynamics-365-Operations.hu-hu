---
title: Kapacitásterhelés számítása ütemezett munkarendeléseken
description: Ez a témakör azt mutatja be, hogyan lehet kapacitásterhelést számolni az ütemezett munkarendelésekre az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 09e0fc17a288a278b7b1feaba8c7b73425aa2d52
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808160"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Kapacitásterhelés számítása ütemezett munkarendeléseken

[!include [banner](../../includes/banner.md)]

 

Az ütemezett munkarendelésekre vonatkozóan kiszámíthatja a kapacitások terhelését, hogy egy adott időszakra vonatkozóan áttekintést kapjon az erőforrásokkal kapcsolatos munkaterhelésről. A számítások a következő erőforrásokon hajthatók végre: karbantartó dolgozók, dolgozói csoportok, segédeszközök és eszközök.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Ütemezés** > **Kapacitásterhelés** elemre.

2. A **Kapacitásterhelés számítása** párbeszédpanel > **Megjelenítés** mezőben válassza ki, hogy melyik terhelési típust szeretné kiszámítani: **Kapacitás**, **Foglalt** vagy **Fennmaradó**.

3. Ha a nullát tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot **Igen** értékre.

4. Válassza ki azokat az erőforrás-típusokat, amelyekhez ki kívánja számítani a kapacitásterhelést a megfelelő aktiváló gombokon az **Igen** kiválasztásával: **Dolgozó**, **Karbantartási dolgozó csoport**, **Segédeszköz** és **Eszköz**.

5. A **Kezdő dátum** mezőben válassza ki a számítás kezdő dátumát.

6. Az **Intervallum** típusa mezőben válassza ki a számítás intervallumát: **Nap**, **Hét**, **Hónap** vagy **Negyedév**.

7. Az **Időszak gyakorisága** mezőbe írja be, hogy hány intervallumot kíván kiszámítani. Ha például a **Nap** beállítás van megadva az időszak gyakoriságának, és a mezőbe az „5” számot írja be, akkor a kezdő dátumtól számított öt nap számítása történik meg.

8. Kattintson az **OK** gombra az számítás indításához.

Az alábbi ábra egy olyan számítás eredményét jeleníti meg, amely három hétre terjed ki a **Foglalt** terheléstípus esetében.

![1. ábra](media/08-work-order-scheduling.png)

[!NOTE]
Ha a számításhoz a **Kapacitás** vagy a **Fennmaradó** terheléstípust választja, akkor ugyanazt az eredményt jeleníti meg a program, ha nem történt foglalás a kiválasztott időszak erőforrásaihoz.

Lásd a [Kapacitásterhelés kiszámítása](../capacity-planning/calculate-capacity-load.md) részt tájékoztatásért a kapacitás terhelésének számításához a karbantartási ütemezés soraiban, és nem az ütemezett munkarendeléseken.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]