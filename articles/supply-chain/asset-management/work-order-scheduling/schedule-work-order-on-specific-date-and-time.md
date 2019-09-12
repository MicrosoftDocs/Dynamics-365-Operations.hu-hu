---
title: Munkarendelés ütemezése megadott dátumra és időpontra
description: Ez a témakör azt mutatja be, hogyan lehet munkarendelést ütemezni egy adott dátumra és időpontra az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f818c4c3b669cc94e37cba1e3571c57b5c0dd1b
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887365"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Munkarendelés ütemezése megadott dátumra és időpontra

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Ha egy munkarendelést meghatározott napon *és* időpontban kell ütemezni, felülbírálhatja az alap ütemezési folyamatot az Eszközkezelés modulban, és létrehozhat egy meghatározott ütemezést a munkarendeléshez.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. A munkarendelés listán kattintson a munkarendelés azonosítójára a **Munkarendelés** oszlopban.

3. Kattintson a **Szerkesztés** lehetőségre.

4. A **Munkarendelés fejléce** gyorslapon adja meg a kezdő és záró dátumot a **Várható kezdés** és a **Várható befejezés** mezőben.

![1. ábra](media/05-work-order-scheduling.png)

5. Az **Általános** lapon kattintson az **Ütemezés** elemre a szokásos ütemezési folyamat használatához, vagy kattintson a **Küldés** gombra, ha a munkarendelést egy adott dolgozóhoz szeretné ütemezni.

6. Ha szeretné felülírni a meglévő kapacitásfoglalásokat annak érdekében, hogy a munkarendelést a várható időszakra ütemezze a program, az alábbi ábrán látható módon végezze el az elemek kiválasztását a **Munkarendelés ütemezése** párbeszédablakon > a **Véges kapacitás** szakaszban. Ez azt jelenti, hogy az ütemezési folyamat figyelmen kívül hagyja a meglévő kapacitásfoglalásokat, mert a munkarendelésnek a várható időpontban kell kezdődnie.

![2. ábra](media/06-work-order-scheduling.png)

7. Az ütemezés megkezdéséhez kattintson az **OK** gombra.

8. Ha az ütemezési folyamat dupla foglalást eredményez, akkor üzenet jelenik meg a képernyőn, és módosíthatja a kapcsolódó munkarendeléseket.

>[!NOTE]
>A karbantartási dolgozót akkor tudja a munkarendeléshez ütemezni, ha elérhető a várt kezdő dátumon és időpontban. A  dolgozó elérhetősége beállítás itt érhető el: [Dolgozó naptára](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 

