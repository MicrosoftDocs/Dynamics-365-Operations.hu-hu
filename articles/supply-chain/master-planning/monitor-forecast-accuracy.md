---
title: Előrejelzés pontosságának megfigyelése
description: Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Dynamics 365 Supply Chain Management kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.
author: t-benebo
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ebde5ab90b9345b3d6f28ea98650b3b29021c304
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893352"
---
# <a name="monitor-forecast-accuracy"></a>Előrejelzés pontosságának megfigyelése

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti Dynamics 365 Supply Chain Management az előrejelzési pontosság Microsoft által kiszámított típusait, és bemutatja a pontossági értékek megtekintésének a módszerét.

A Supply Chain Management a következő típusú előrejelzési pontosságokat számítja ki:

-   Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel. A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.
-   Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága. A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon. 

> [!NOTE]
> Amennyiben az Igény-előrejelzés Microsoft Azure gépi tanulási szolgáltatását használja, a belső modell pontosságának számítása a tesztadatokat veszi alapul. A teszt adathalmaz méretének megadásához állítsa be a **TEST\_SET\_SIZE\_PERCENT** paramétert az **Igény-előrejelző** paraméterek oldalon. Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.


## <a name="additional-resources"></a>További erőforrások

[Módosított előrejelzés engedélyezése](authorize-adjusted-forecast.md)

[Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]