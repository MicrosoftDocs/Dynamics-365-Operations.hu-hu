---
title: Előzményadatok importálása az igény-előrejelzésekhez
description: Ahhoz, hogy pontos igény-előrejelzéseket kaphasson, cikkenként vagy cikkfelosztási kulcsonként kell rendelkeznie a korábbi igényadatokkal. Ez a témakör azt ismerteti, hogy miként használhatja az adatentitásokat a korábbi igényadatok bármely rendszerből való importálására annak érdekében, hogy Ön több igény-előrejelzési adattal rendelkezhessen.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301650"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="8a7cf-104">Előzményadatok importálása az igény-előrejelzésekhez</span><span class="sxs-lookup"><span data-stu-id="8a7cf-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a7cf-105">Az igény-előrejelzések pontosságának biztosítása érdekében minél több adatra van szükség a korábbi igényekről cikkenként vagy cikkfelosztási kulcsonként.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="8a7cf-106">Ha a korábbi igényadatok még nincsenek importálva, használja a **Korábbi külső igény** (ReqDemPlanHistoricalExternalDemandEntity) adatentitást a Dynamics 365 Supply Chain Management szolgáltatásban az importálásukhoz.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="8a7cf-107">Az **Adatkezelés** munkaterületen megtekintheti az entitás összes mezőjének áttekintését.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="8a7cf-108">Nyissa meg az **Adatkezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="8a7cf-109">Válassza ki az **Adatentitások** mozaikot.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="8a7cf-110">Keresse ki a **Korábbi külső igény** entitáslistáját.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="8a7cf-111">Válassza ki a **Célmezők** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-111">Select **Target fields**.</span></span> <span data-ttu-id="8a7cf-112">A következő entitásmezők kötelezőek: hely (**DeliveringSiteId**), dátum (**DemandDate**), mennyiség (**DemandQuantity**), továbbá vagy a cikkszám (**ItemNumber**), vagy a cikkfelosztási kulcs (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="8a7cf-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="8a7cf-113">Az adatentitás használatához rendelkeznie kell egy olyan Microsoft Excel fájllal vagy CSV-fájllal, amely tartalmazza a korábbi igényadatokat.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="8a7cf-114">Az alábbi példa az adatok CSV-fájlból való importálását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="8a7cf-115">Az adatok importálásával és az adatok importálás utáni tisztításával kapcsolatos további tudnivalókat lásd az [Adatimportálási és -exportálási feladatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) és a kapcsolódó témakörökben.</span><span class="sxs-lookup"><span data-stu-id="8a7cf-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

<span data-ttu-id="8a7cf-116">Lásd még: [Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md).</span><span class="sxs-lookup"><span data-stu-id="8a7cf-116">See also [Generate a statistical baseline forecast](generate-statistical-baseline-forecast.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]