---
title: Visszavezetési költségelszámolási számítási hiba készletzáráskor
description: Előfordulhat, hogy a korábbi verziókban visszavezetési költségelszámolási számítási hiba történt a készletzárás során. A probléma ki lett javítva.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ae92b7121998d6b1ba2f08ea5736c55637867fbf
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476537"
---
# <a name="backflush-costing-calculation-error-during-inventory-closing"></a>Visszavezetési költségelszámolási számítási hiba készletzáráskor

## <a name="symptoms"></a>Tünetek

A 10.0.13-as verzió előtti kiadásokban, ha nem használja a lean termelési költségszámítási folyamatot, a következő hibás figyelmeztető üzenet jelenik meg a készletzárás során:

> Készletzárást készül végrehajtani %1. Az %1 egyeztetési időszak végén nem sikerült visszavezetéses költségelszámolás kiszámítását végrehajtani. Ne felejtse el végrehajtani az %1 egyeztetési időszak végén végrehajtani a visszavezetéses költségelszámolás kiszámítását. A készletekre, az eladott áruk beszerzési értékére és az eltérésekre vonatkozó becslések nem lehetnek helyesek az alfőkönyv vagy a főkönyv modulban mindaddig, amíg nem történt meg a végrehajtás.

## <a name="resolution"></a>Megoldás

A problémát a 10.0.13-as és újabb verzióiban javítottuk. További tájékoztatást a [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296) témakörben talál.
