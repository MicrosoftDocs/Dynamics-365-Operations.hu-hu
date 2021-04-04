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
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8548fa9f64a579816e51bbd7ad9f63db290eaa38
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244207"
---
# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="6ed34-103">Előrejelzés pontosságának követése</span><span class="sxs-lookup"><span data-stu-id="6ed34-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ed34-104">Ez a témakör leírja azon előrejelzés pontossági típusokat, melyeket a Microsoft Dynamics 365 Supply Chain Management kiszámol, majd megmagyarázza, hogyan tekintheti meg a pontosság értékeit.</span><span class="sxs-lookup"><span data-stu-id="6ed34-104">This topic describes the types of forecast accuracy that Microsoft Dynamics 365 Supply Chain Management calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="6ed34-105">A Supply Chain Management a következő típusú előrejelzési pontosságokat számítja ki:</span><span class="sxs-lookup"><span data-stu-id="6ed34-105">Supply Chain Management calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="6ed34-106">Múltbéli előrejelzés pontossága, az alaptervezés által használt múltbéli előrejelzés összehasonlítása a múltbéli igényekkel.</span><span class="sxs-lookup"><span data-stu-id="6ed34-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="6ed34-107">A múltbéli előrejelzés pontosságának értékeiért (abszolút értékek, valamint százalékos értékek) kattintson a **Pontosság megjelenítése** gombra az **Igény-előrejelzés részletek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="6ed34-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="6ed34-108">Az előrejelzések létrehozásához használt előrejelző modell előrelátható pontossága.</span><span class="sxs-lookup"><span data-stu-id="6ed34-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="6ed34-109">A pontosság százalékos értékét megtekintheti a **Modell adatok - MAPE** opció alatt, az **Igény-előrejelzés adatok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="6ed34-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="6ed34-110">Amennyiben az Igény-előrejelzés Microsoft Azure gépi tanulási szolgáltatását használja, a belső modell pontosságának számítása a tesztadatokat veszi alapul.</span><span class="sxs-lookup"><span data-stu-id="6ed34-110">If you use the Demand forecasting Microsoft Azure Machine Learning, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="6ed34-111">A teszt adathalmaz méretének megadásához állítsa be a **TEST\_SET\_SIZE\_PERCENT** paramétert az **Igény-előrejelző** paraméterek oldalon.</span><span class="sxs-lookup"><span data-stu-id="6ed34-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="6ed34-112">Ha a beállított érték például **20**, akkor a belső modell pontosságának kiszámításához a múltbéli adatok utolsó 20 százaléka lesz alapul véve.</span><span class="sxs-lookup"><span data-stu-id="6ed34-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="6ed34-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6ed34-113">Additional resources</span></span>
--------

[<span data-ttu-id="6ed34-114">Módosított előrejelzés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6ed34-114">Authorize an adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="6ed34-115">Kiugró értékek eltávolítása a tranzakciók előzményadataiból igény-előrejelzés számításakor</span><span class="sxs-lookup"><span data-stu-id="6ed34-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]