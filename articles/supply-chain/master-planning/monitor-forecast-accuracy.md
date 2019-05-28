---
title: Előrejelzés pontosságának megfigyelése
description: Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 for Finance and Operations kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7070c15f9ee23cfdba871af68d1fc5954735651
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556806"
---
# <a name="monitor-forecast-accuracy"></a>Előrejelzés pontosságának megfigyelése

[!include [banner](../includes/banner.md)]

Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 for Finance and Operations kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.

A Finance and Operations a következő típusú előrejelzési pontosságokat számítja ki:

-   Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel. A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.
-   Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága. A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon. 

**Megjegyzés**: amennyiben a Finance and Operations az Igény-előrejelzés Microsoft Azure Machine Learning szolgáltatást veszi igénybe, a belső modell pontosságának kalkulációja a tesztadatokat veszi alapul. A teszt adathalmaz méretének megadásához állítsa be a **TEST\_SET\_SIZE\_PERCENT** paramétert az **Igény-előrejelző** paraméterek oldalon. Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.


<a name="additional-resources"></a>További erőforrások
--------

[Beállított előrejelzés engedélyezése](authorize-adjusted-forecast.md)

[Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor](remove-historical-outliers-calculating-demand-forecast.md)



