---
title: Munkarendelés ütemezése megadott dátumra és időpontra
description: Ez a cikk bemutatja, hogyan lehet ütemezni egy munkarendelést egy adott dátumra és időpontra az Eszközkezelésben.
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
ms.openlocfilehash: ec7e300f60f76aaa467238d7a2c2a199fdeafeed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857924"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Munkarendelés ütemezése megadott dátumra és időpontra

[!include [banner](../../includes/banner.md)]

 

Ha egy munkarendelést meghatározott napon *és* időpontban kell ütemezni, felülbírálhatja az alap ütemezési folyamatot az Eszközkezelés modulban, és létrehozhat egy meghatározott ütemezést a munkarendeléshez.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. A munkarendelés listán kattintson a munkarendelés azonosítójára a **Munkarendelés** oszlopban.

3. Kattintson a **Szerkesztés** lehetőségre.

4. A **Munkarendelés fejléce** gyorslapon adja meg a kezdő és záró dátumot a **Várható kezdés** és a **Várható befejezés** mezőben.

    ![1. ábra](media/05-work-order-scheduling.png)

5. Az **Általános** lapon kattintson az **Ütemezés** elemre a szokásos ütemezési folyamat használatához, vagy kattintson a **Küldés** gombra, ha a munkarendelést egy adott dolgozóhoz szeretné hozzárendelni.

6. Ha szeretné felülírni a meglévő kapacitásfoglalásokat annak érdekében, hogy a munkarendelést a várható időszakra ütemezze a program, az alábbi ábrán látható módon végezze el az elemek kiválasztását a **Munkarendelés ütemezése** párbeszédablakon > a **Véges kapacitás** szakaszban. Ez azt jelenti, hogy az ütemezési folyamat figyelmen kívül hagyja a meglévő kapacitásfoglalásokat, mert a munkarendelésnek a várható időpontban kell kezdődnie.

    ![2. ábra](media/06-work-order-scheduling.png)

7. Az ütemezés megkezdéséhez kattintson az **OK** gombra.

8. Ha az ütemezési folyamat dupla foglalást eredményez, akkor üzenet jelenik meg a képernyőn, és módosíthatja a kapcsolódó munkarendeléseket.

>[!NOTE]
>A karbantartási dolgozót akkor tudja a munkarendeléshez ütemezni, ha elérhető a várt kezdő dátumon és időpontban. A  dolgozó elérhetősége beállítás itt érhető el: [Dolgozó naptára](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]