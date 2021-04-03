---
title: Folyamatszerű gyártás – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani az folyamatszerű gyártás használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71ff5eeb2065a67281393777937d50237ab78d5e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259722"
---
# <a name="troubleshoot-process-manufacturing"></a>Folyamatszerű gyártás – hibaelhárítás

Ez a témakör azt mutatja be, hogyan lehet javítani az folyamatszerű gyártás használata során felmerülő problémákat.

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a>Amikor a feladatkártya-eszközzel részleges mennyiséget jelentek a termelési rendelés utolsó feladatán, a rendelésben szereplő összes előző feladat, amelynek állapota Folyamatban van, automatikusan lezárul.

Ez szándékosan van. A **Termelési rendelés alapértelmezései** lapon a **Készként jelentés** fülön van egy **Útvonal megjelölése befejezettként** lehetőség. Ha ez a témakör *Igen* értékre van állítva, akkor egy útvonalkártya-naplót könyvel, amikor egy dolgozó a munkakártya-eszközt vagy a feladatkártya terminálját használja az utolsó művelet jelentéséhez. Ez a napló befejezettként jelöli meg az összes műveletet, és befejezi az összes termelési feladatot. Ha az **Útvonal megjelölése befejezettként** lehetőség *Igen* értékre van állítva, akkor a rendszer nem veszi figyelembe azt a feladatállapotot, amelyet a dolgozó az utolsó művelet jelentésekor választott. A rendszer azt sem veszi figyelembe, hogy a dolgozó teljes vagy részleges mennyiséget jelent-e.

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a>Amikor készletzárást kísérelek meg, a következő figyelmeztető üzenet jelenik meg: Az %1 egyeztetési időszak végén nem sikerült visszavezetéses költségelszámolás kiszámítását végrehajtani.”

A 10.0.13-as verzió előtti kiadásokban, ha nem használja a lean termelési költségszámítási folyamatot, a következő hibás figyelmeztető üzenet jelenik meg a készletzárás során:

> Készletzárást készül végrehajtani %1. Az %1 egyeztetési időszak végén nem sikerült visszavezetéses költségelszámolás kiszámítását végrehajtani. Ne felejtse el végrehajtani az %1 egyeztetési időszak végén végrehajtani a visszavezetéses költségelszámolás kiszámítását. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás.

A problémát a 10.0.13-as és újabb verzióiban javítottuk. További tájékoztatást a [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296) témakörben talál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]