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
ms.search.form: ReqDemPlanForecastDetails
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d1025619d799cb94af73571f8ca78eca578782f4
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="7bffa-103">Előrejelzés pontosságának megfigyelése</span><span class="sxs-lookup"><span data-stu-id="7bffa-103">Monitor forecast accuracy</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="7bffa-104">Ez a cikk leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 for Finance and Operations kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.</span><span class="sxs-lookup"><span data-stu-id="7bffa-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="7bffa-105">A Finance and Operations a következő típusú előrejelzési pontosságokat számítja ki:</span><span class="sxs-lookup"><span data-stu-id="7bffa-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="7bffa-106">Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel.</span><span class="sxs-lookup"><span data-stu-id="7bffa-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="7bffa-107">A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7bffa-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="7bffa-108">Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága.</span><span class="sxs-lookup"><span data-stu-id="7bffa-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="7bffa-109">A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7bffa-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="7bffa-110">**Megjegyzés:** amennyiben a Finance and Operations az Igény-előrejelző Microsoft Azure Machine Learning szolgáltatást veszi igénybe, a belső modell pontosságának kalkulációja a tesztadatokat veszi alapul.</span><span class="sxs-lookup"><span data-stu-id="7bffa-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="7bffa-111">A teszt adathalmaz méretének megadásához állítsa be a **TEST\_SET\_SIZE\_PERCENT** paramétert az **Igény-előrejelző** paraméterek oldalon.</span><span class="sxs-lookup"><span data-stu-id="7bffa-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="7bffa-112">Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.</span><span class="sxs-lookup"><span data-stu-id="7bffa-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="see-also"></a><span data-ttu-id="7bffa-113">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7bffa-113">See also</span></span>
--------

[<span data-ttu-id="7bffa-114">Beállított előrejelzés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="7bffa-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="7bffa-115">Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor</span><span class="sxs-lookup"><span data-stu-id="7bffa-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)




