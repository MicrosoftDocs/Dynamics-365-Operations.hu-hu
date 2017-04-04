---
title: "Monitor előrejelzés pontossága"
description: "A cikk ismerteti a Microsoft Dynamics 365 műveletek számítja ki, és bemutatja, hogy miként tekintheti meg a pontossági előrejelzési pontosság típusú."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d3f88a4fa54217cea909c54955de05e2175db0cd
ms.lasthandoff: 03/29/2017


---

# <a name="monitor-forecast-accuracy"></a>Monitor előrejelzés pontossága

A cikk ismerteti a Microsoft Dynamics 365 műveletek számítja ki, és bemutatja, hogy miként tekintheti meg a pontossági előrejelzési pontosság típusú.

365 Dynamics műveletek számítja ki a következő típusú előrejelzés pontossága:

-   Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel. A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.
-   Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága. A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon. 

**Megjegyzés:** a Dynamics 365 műveletek igény-előrejelzés Microsoft Azure gép Learning szolgáltatás használatakor kiszámítása belső modell pontosságának a vizsgálati adatkészlet alapul. Vizsgálati adatkészlet méretének megadásához állítsa a **teszt\_meg\_mérete\_SZÁZALÉK** paraméter a **igény-előrejelzés paraméterek** lap. Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.


<a name="see-also"></a>Lásd még
--------

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


