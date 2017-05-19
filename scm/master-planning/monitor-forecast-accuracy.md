---
title: "Előrejelzés pontosságának megfigyelése"
description: "Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 for Operations kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 7e470e05d9acb1e7417d0d77655be99e94d15e1d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="monitor-forecast-accuracy"></a>Előrejelzés pontosságának megfigyelése

[!include[banner](../includes/banner.md)]


Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 for Operations kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.

A Microsoft Dynamics 365 for Operations a következő típusú előrejelzési pontosságokat számítja ki:

-   Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel. A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.
-   Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága. A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon. 

**Megjegyzés:** amennyiben a Dynamics 365 for Operations az Igény-előrejelző Microsoft Azure Machine Learning szolgáltatást veszi igénybe, a belső modell pontosságának kalkulációja a tesztadatokat veszi alapul. A teszt adathalmaz méretének megadásához állítsa be a **TEST\_SET\_SIZE\_PERCENT** paramétert az **Igény-előrejelző** paraméterek oldalon. Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.


<a name="see-also"></a>Lásd még
--------

[Beállított előrejelzés engedélyezése](authorize-adjusted-forecast.md)

[Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor](remove-historical-outliers-calculating-demand-forecast.md)




