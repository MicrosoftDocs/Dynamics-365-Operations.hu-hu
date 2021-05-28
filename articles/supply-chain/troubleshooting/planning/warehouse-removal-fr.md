---
title: A Raktári igényelőrejelzés-dimenzió nem távolítható el az előrejelzési sorokból
description: A Raktári igényelőrejelzés-dimenzió nem távolítható el az előrejelzési sorokból.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026578"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a><span data-ttu-id="fe55c-103">A Raktári igényelőrejelzés-dimenzió nem távolítható el az előrejelzési sorokból</span><span class="sxs-lookup"><span data-stu-id="fe55c-103">You can't remove the Warehouse demand forecast dimension from forecast lines</span></span>

<span data-ttu-id="fe55c-104">Tudásbáziscikk száma: 4614408</span><span class="sxs-lookup"><span data-stu-id="fe55c-104">KB number: 4614408</span></span>

## <a name="symptoms"></a><span data-ttu-id="fe55c-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="fe55c-105">Symptoms</span></span>

<span data-ttu-id="fe55c-106">Ez a probléma akkor fordul elő, ha nincs hozzárendelve a **Raktár** dimenzió az **Igény-előrejelzési** laphoz az **Igény-előrejelzés paraméter** oldalon.</span><span class="sxs-lookup"><span data-stu-id="fe55c-106">This issue occurs when the **Warehouse** dimension isn't assigned on the **Forecast dimensions** tab of the **Demand forecasting parameter** page.</span></span> <span data-ttu-id="fe55c-107">Ettől függetlenül megjelenik a **Raktár** oszlop az **Igény-előrejelzés** oldalon(**Alaptervezés \> Előrejelzés \> Manuális előrejelzés entitás \> Igény-előrejelzés sorok**).</span><span class="sxs-lookup"><span data-stu-id="fe55c-107">Nevertheless, the **Warehouse** column is shown on the **Demand forecast** page (**Master planning \> Forecasting \> Manual forecast entity \> Demand forecast lines**).</span></span>

## <a name="resolution"></a><span data-ttu-id="fe55c-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="fe55c-108">Resolution</span></span>

<span data-ttu-id="fe55c-109">Az **Igény-előrejelzési paraméter** lap **Előrejelzési dimenziók** lapján megadott beállítások nincsenek hatással az **Igény-előrejelzés** lapra.</span><span class="sxs-lookup"><span data-stu-id="fe55c-109">The settings on the **Forecast dimensions** tab of the **Demand forecasting parameter** page don't affect the **Demand forecast** page.</span></span> <span data-ttu-id="fe55c-110">A módosított igény-előrejelzésben generált és látható kiinduló előrejelzést szabályozzák.</span><span class="sxs-lookup"><span data-stu-id="fe55c-110">They control the baseline forecast that is generated and shown in the adjusted demand forecast.</span></span> <span data-ttu-id="fe55c-111">Nem ellenőrzik azonban a "valódi" igény-előrejelzéshez szükséges dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="fe55c-111">However, they don't control the dimensions that are required for the "real" demand forecast.</span></span> <span data-ttu-id="fe55c-112">Ha a **Módosított igény-előrejelzés** oldalon megjelenő rekordokat jóváhagyásával, akkor ezeket "valódi" előrejelzési bejegyzésekké konvertálhatja egy előrejelzési modellben.</span><span class="sxs-lookup"><span data-stu-id="fe55c-112">By authorizing the records that are shown on the **Adjusted demand forecast** page, you can convert them to "real" forecast entries for a forecast model.</span></span> <span data-ttu-id="fe55c-113">Ez a modell ezután használható az alaptervezésben.</span><span class="sxs-lookup"><span data-stu-id="fe55c-113">That model can then be used for master planning.</span></span>

<span data-ttu-id="fe55c-114">Az **Igény-előrejelzés** lapon az igény-előrejelzési sorokban megjelenő "valódi" előrejelzés dimenziói részei a készletdimenzióknak.</span><span class="sxs-lookup"><span data-stu-id="fe55c-114">On the **Demand forecast** page, the dimensions for the "real" forecast that are shown on the demand forecast lines are part of the inventory dimensions.</span></span> <span data-ttu-id="fe55c-115">(Ez a viselkedés hasonlít az értékesítésirendelés-sorok viselkedésére.) Ha a rendszer nem úgy van beállítva, hogy kötelező készletdimenzióként használja a **Raktárat**, akkor az oszlop elrejtéséhez testreszabhatja az oldalt.</span><span class="sxs-lookup"><span data-stu-id="fe55c-115">(This behavior resembles the behavior for sales order lines.) If your system isn't set up to use **Warehouse** as a mandatory inventory dimension, you can customize the page to hide the column.</span></span>
