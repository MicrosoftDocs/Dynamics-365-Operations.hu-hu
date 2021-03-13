---
title: Előzményadatok importálása az igény-előrejelzésekhez
description: Ahhoz, hogy pontos igény-előrejelzéseket kaphasson, cikkenként vagy cikkfelosztási kulcsonként kell rendelkeznie a korábbi igényadatokkal. Ez a témakör azt ismerteti, hogy miként használhatja az adatentitásokat a korábbi igényadatok bármely rendszerből való importálására annak érdekében, hogy Ön több igény-előrejelzési adattal rendelkezhessen.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: d6ba2e1a3a884d29bff491f914aa2d5f9ece2b84
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154227"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="82694-104">Előzményadatok importálása az igény-előrejelzésekhez</span><span class="sxs-lookup"><span data-stu-id="82694-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82694-105">Az igény-előrejelzések pontosságának biztosítása érdekében minél több adatra van szükség a korábbi igényekről cikkenként vagy cikkfelosztási kulcsonként.</span><span class="sxs-lookup"><span data-stu-id="82694-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="82694-106">Ha a korábbi igényadatok még nincsenek importálva, használja a **Korábbi külső igény** (ReqDemPlanHistoricalExternalDemandEntity) adatentitást a Dynamics 365 Supply Chain Management szolgáltatásban az importálásukhoz.</span><span class="sxs-lookup"><span data-stu-id="82694-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="82694-107">Az **Adatkezelés** munkaterületen megtekintheti az entitás összes mezőjének áttekintését.</span><span class="sxs-lookup"><span data-stu-id="82694-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="82694-108">Nyissa meg az **Adatkezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="82694-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="82694-109">Válassza ki az **Adatentitások** mozaikot.</span><span class="sxs-lookup"><span data-stu-id="82694-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="82694-110">Keresse ki a **Korábbi külső igény** entitáslistáját.</span><span class="sxs-lookup"><span data-stu-id="82694-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="82694-111">Válassza ki a **Célmezők** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82694-111">Select **Target fields**.</span></span> <span data-ttu-id="82694-112">A következő entitásmezők kötelezőek: hely (**DeliveringSiteId**), dátum (**DemandDate**), mennyiség (**DemandQuantity**), továbbá vagy a cikkszám (**ItemNumber**), vagy a cikkfelosztási kulcs (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="82694-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="82694-113">Az adatentitás használatához rendelkeznie kell egy olyan Microsoft Excel fájllal vagy CSV-fájllal, amely tartalmazza a korábbi igényadatokat.</span><span class="sxs-lookup"><span data-stu-id="82694-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="82694-114">Az alábbi példa az adatok CSV-fájlból való importálását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="82694-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="82694-115">Az adatok importálásával és az adatok importálás utáni tisztításával kapcsolatos további tudnivalókat lásd az [Adatimportálási és -exportálási feladatok áttekintése](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) és a kapcsolódó témakörökben.</span><span class="sxs-lookup"><span data-stu-id="82694-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

## <a name="example"></a><span data-ttu-id="82694-116">Példa</span><span class="sxs-lookup"><span data-stu-id="82694-116">Example</span></span>

<span data-ttu-id="82694-117">A következő fájlt példaként használhatja.</span><span class="sxs-lookup"><span data-stu-id="82694-117">You can use the following file as an example.</span></span> <span data-ttu-id="82694-118">Töltse le a [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/) fájlt.</span><span class="sxs-lookup"><span data-stu-id="82694-118">Download the [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/).</span></span> <span data-ttu-id="82694-119">Ez a fájl a D0001 cikk korábbi igényadatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="82694-119">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="82694-120">Csak a következő kötelező mezők szerepelnek benne: hely, mennyiség és az igény dátuma.</span><span class="sxs-lookup"><span data-stu-id="82694-120">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="82694-121">Válassza ki azt a vállalatot, amelyikbe a korábbi igényadatokat importálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="82694-121">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="82694-122">Nyissa meg az **Adatkezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="82694-122">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="82694-123">Válassza ki az **Importálás** mozaikot.</span><span class="sxs-lookup"><span data-stu-id="82694-123">Select the **Import** tile.</span></span>
4. <span data-ttu-id="82694-124">Adjon meg egy nevet az importálási projektnek, mint például a következőt: **A D0001 cikk korábbi igényének importálása**.</span><span class="sxs-lookup"><span data-stu-id="82694-124">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="82694-125">A **Forrásadatok formátuma** mezőben válassza ki az importált fájl formátumát.</span><span class="sxs-lookup"><span data-stu-id="82694-125">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="82694-126">Ennél a példánál a HistoricalDemandData fájl importálásához jelölje be a **CSV** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82694-126">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="82694-127">Az **Entitásnév** mezőben válassza a **Korábbi külső igény** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82694-127">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="82694-128">Mentse a fájlt a számítógépre, majd töltse fel.</span><span class="sxs-lookup"><span data-stu-id="82694-128">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="82694-129">Válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="82694-129">Select **Import**.</span></span>
9. <span data-ttu-id="82694-130">A **Végrehajtás összefoglalása** lap automatikusan megnyílik.</span><span class="sxs-lookup"><span data-stu-id="82694-130">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="82694-131">Ellenőrizze az importált adatokat a lapon.</span><span class="sxs-lookup"><span data-stu-id="82694-131">Verify the imported data on the page.</span></span>

<span data-ttu-id="82694-132">A korábbi igényadatok importálása után létrehozhatja az igény-előrejelzést.</span><span class="sxs-lookup"><span data-stu-id="82694-132">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="82694-133">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="82694-133">Additional resources</span></span>

[<span data-ttu-id="82694-134">Statisztikai kiinduló előrejelzés létrehozása</span><span class="sxs-lookup"><span data-stu-id="82694-134">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)  
[<span data-ttu-id="82694-135">Adatimportálási és -exportálási feladatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="82694-135">Data import and export jobs overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)
