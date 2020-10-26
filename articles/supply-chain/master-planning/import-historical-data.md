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
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c66481b1dd8650960cad2947425c1e6c7450afcb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982821"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="7ccbb-104">Előzményadatok importálása az igény-előrejelzésekhez</span><span class="sxs-lookup"><span data-stu-id="7ccbb-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ccbb-105">Az igény-előrejelzések pontosságának biztosítása érdekében minél több adatra van szükség a korábbi igényekről cikkenként vagy cikkfelosztási kulcsonként.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="7ccbb-106">Ha a korábbi igényadatok még nincsenek importálva, használja a **Korábbi külső igény** (ReqDemPlanHistoricalExternalDemandEntity) adatentitást a Dynamics 365 Supply Chain Management szolgáltatásban az importálásukhoz.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="7ccbb-107">Az **Adatkezelés** munkaterületen megtekintheti az entitás összes mezőjének áttekintését.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="7ccbb-108">Nyissa meg az **Adatkezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="7ccbb-109">Kattintson az **Adatentitások** mozaikra.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-109">Click the **Data entities** tile.</span></span>
3. <span data-ttu-id="7ccbb-110">Keresse ki a **Korábbi külső igény** entitáslistáját.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-110">Search the entity list for **Historical external demand** .</span></span>
4. <span data-ttu-id="7ccbb-111">Kattintson a **Célmezők** pontra.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-111">Click **Target fields** .</span></span> <span data-ttu-id="7ccbb-112">A következő entitásmezők kötelezőek: hely ( **DeliveringSiteId** ), dátum ( **DemandDate** ), mennyiség ( **DemandQuantity** ), továbbá vagy a cikkszám ( **ItemNumber** ), vagy a cikkfelosztási kulcs ( **ProductAllocationKeyId** ).</span><span class="sxs-lookup"><span data-stu-id="7ccbb-112">The following entity fields are mandatory: site ( **DeliveringSiteId** ), date ( **DemandDate** ), quantity ( **DemandQuantity** ), and either item number ( **ItemNumber** ) or item allocation key ( **ProductAllocationKeyId** ).</span></span>

<span data-ttu-id="7ccbb-113">Az adatentitás használatához rendelkeznie kell egy olyan Microsoft Excel fájllal vagy CSV-fájllal, amely tartalmazza a korábbi igényadatokat.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="7ccbb-114">Az alábbi példa az adatok CSV-fájlból való importálását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-114">The following example shows how to import the data from a CSV file.</span></span>

## <a name="example"></a><span data-ttu-id="7ccbb-115">Példa</span><span class="sxs-lookup"><span data-stu-id="7ccbb-115">Example</span></span>

<span data-ttu-id="7ccbb-116">A következő fájlt példaként használhatja.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-116">You can use the following file as an example.</span></span> <span data-ttu-id="7ccbb-117">Töltse le a [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast) fájlt.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-117">Download the [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span></span> <span data-ttu-id="7ccbb-118">Ez a fájl a D0001 cikk korábbi igényadatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-118">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="7ccbb-119">Csak a következő kötelező mezők szerepelnek benne: hely, mennyiség és az igény dátuma.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-119">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="7ccbb-120">Válassza ki azt a vállalatot, amelyikbe a korábbi igényadatokat importálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-120">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="7ccbb-121">Nyissa meg az **Adatkezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-121">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="7ccbb-122">Kattintson az **Importálás** mozaikra.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-122">Click the **Import** tile.</span></span>
4. <span data-ttu-id="7ccbb-123">Adjon meg egy nevet az importálási projektnek, mint például a következőt: **A D0001 cikk korábbi igényének importálása** .</span><span class="sxs-lookup"><span data-stu-id="7ccbb-123">Enter a name for the import project, such as **Import historical demand for item D0001** .</span></span>
5. <span data-ttu-id="7ccbb-124">A **Forrásadatok formátuma** mezőben válassza ki az importált fájl formátumát.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-124">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="7ccbb-125">Ennél a példánál a HistoricalDemandData fájl importálásához jelölje be a **CSV** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-125">To import the HistoricalDemandData file for this example, select **CSV** .</span></span>
6. <span data-ttu-id="7ccbb-126">Az **Entitásnév** mezőben válassza a **Korábbi külső igény** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-126">In the **Entity name** field, select **Historical external demand** .</span></span>
7. <span data-ttu-id="7ccbb-127">Mentse a fájlt a számítógépre, majd töltse fel.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-127">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="7ccbb-128">Kattintson az **Importálás** gombra.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-128">Click **Import** .</span></span>
9. <span data-ttu-id="7ccbb-129">A **Végrehajtás összefoglalása** lap automatikusan megnyílik.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-129">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="7ccbb-130">Ellenőrizze az importált adatokat a lapon.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-130">Verify the imported data on the page.</span></span>

<span data-ttu-id="7ccbb-131">A korábbi igényadatok importálása után létrehozhatja az igény-előrejelzést.</span><span class="sxs-lookup"><span data-stu-id="7ccbb-131">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ccbb-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7ccbb-132">Additional resources</span></span>

[<span data-ttu-id="7ccbb-133">Statisztikai kiinduló előrejelzés létrehozása</span><span class="sxs-lookup"><span data-stu-id="7ccbb-133">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)
