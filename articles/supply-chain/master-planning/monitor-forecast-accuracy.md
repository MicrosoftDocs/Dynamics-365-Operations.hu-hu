---
title: Előrejelzés pontosságának követése
description: Ez a témakör leírja azon előrejelzés pontossági típusokat, melyeket a Dynamics 365 Supply Chain Management kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 60e5425e54f9e0093888f355a51064e7f0057976
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429747"
---
# <a name="monitor-forecast-accuracy"></a>Előrejelzés pontosságának követése

[!include [banner](../includes/banner.md)]

Ez a témakör leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 Supply Chain Management kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.

A Supply Chain Management a következő típusú előrejelzési pontosságokat számítja ki:

-   Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel. A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.
-   Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága. A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon. 

> [!NOTE]
> Amennyiben az Igény-előrejelzés Microsoft Azure gépi tanulási szolgáltatását használja, a belső modell pontosságának számítása a tesztadatokat veszi alapul. A teszt adathalmaz méretének megadásához állítsa be a **TEST\_SET\_SIZE\_PERCENT** paramétert az **Igény-előrejelző** paraméterek oldalon. Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.


<a name="additional-resources"></a>További erőforrások
--------

[Módosított előrejelzés engedélyezése](authorize-adjusted-forecast.md)

[Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]