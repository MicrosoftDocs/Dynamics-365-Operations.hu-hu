---
title: "Előrejelzés pontosságának megfigyelése"
description: "Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 for Finance and Operations kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2f9482a9906ad6c607d275769ac06b29b22c25d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="monitor-forecast-accuracy"></a>Előrejelzés pontosságának megfigyelése

[!include[banner](../includes/banner.md)]


Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 for Finance and Operations kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.

A Finance and Operations a következő típusú előrejelzési pontosságokat számítja ki:

-   Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel. A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.
-   Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága. A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon. 

**Megjegyzés:** amennyiben a Finance and Operations az Igény-előrejelző Microsoft Azure Machine Learning szolgáltatást veszi igénybe, a belső modell pontosságának kalkulációja a tesztadatokat veszi alapul. A teszt adathalmaz méretének megadásához állítsa be a **TEST\_SET\_SIZE\_PERCENT** paramétert az **Igény-előrejelző** paraméterek oldalon. Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.


<a name="see-also"></a>Lásd még
--------

[Beállított előrejelzés engedélyezése](authorize-adjusted-forecast.md)

[Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor](remove-historical-outliers-calculating-demand-forecast.md)




