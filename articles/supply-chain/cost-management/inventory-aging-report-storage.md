---
title: Készletkorosítási jelentés tárolása
description: Ez a témakör bemutatja a funkciókat, amelyekkel készletkorosítási jelentést futtathat és űrlap és diagram formájában elérhetővé teheti a kimeneti fájlt.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9148a9032615222a1fdfe453488e716bacadbabc
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275579"
---
# <a name="inventory-aging-report-storage"></a><span data-ttu-id="80ddb-103">Készletkorosítási jelentés tárolása</span><span class="sxs-lookup"><span data-stu-id="80ddb-103">Inventory aging report storage</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="80ddb-104">A Microsoft Dynamics 365 Supply Chain Management szolgáltatásban futtathat **Készletkorosítás jelentéstárolási** jelentést, és a kimeneti fájlt megoszthatja űrlapként és diagramként.</span><span class="sxs-lookup"><span data-stu-id="80ddb-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging report storage** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="80ddb-105">A képernyőn az oszlopok és az összesítő egyenlegek dinamikusan módosulnak, attól függően, hogy milyen elrendezés van beállítva.</span><span class="sxs-lookup"><span data-stu-id="80ddb-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="80ddb-106">A diagram olyan vizuális áttekintést nyújt, amely támogatja a szűrést, és lehetővé teszi a részletekbe való leásást.</span><span class="sxs-lookup"><span data-stu-id="80ddb-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="80ddb-107">Ezenkívül egy **készletkorosítási jelentés** nevű adatentitás lehetővé teszi, hogy a **készletkorosítási jelentéstárolási** jelentés futtatásának eredményeit egy Microsoft Excel fájl vagy egy PDF-fájl formátumában exportálják.</span><span class="sxs-lookup"><span data-stu-id="80ddb-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging report storage** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="80ddb-108">A **készletkorosítási jelentéstárolási** jelentés futtatására szolgáló módszer olyan esetekben hasznos, amikor a kimenet sok sort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="80ddb-108">This method of running an **Inventory aging report storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="80ddb-109">Például a kimenet sok sort fog tartalmazni, ha 50 000 cikket és 300 üzletet készítenek raktárakként, és a készletkorosítást cikk, telephely és raktár szerint kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="80ddb-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="enable-the-inventory-value-storage-report-feature"></a><span data-ttu-id="80ddb-110">A készletérték-tárolási jelentés funkció engedélyezése</span><span class="sxs-lookup"><span data-stu-id="80ddb-110">Enable the Inventory value storage report feature</span></span>

<span data-ttu-id="80ddb-111">A funkció használata előtt engedélyeznie kell azt saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="80ddb-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="80ddb-112">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="80ddb-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="80ddb-113">Itt a funkció a következőként szerepel:</span><span class="sxs-lookup"><span data-stu-id="80ddb-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="80ddb-114">**Modul** – Költségkezelés</span><span class="sxs-lookup"><span data-stu-id="80ddb-114">**Module** - Cost management</span></span>
- <span data-ttu-id="80ddb-115">**Funkció neve** – Készletkorosítási jelentés tárolása</span><span class="sxs-lookup"><span data-stu-id="80ddb-115">**Feature name** - Inventory aging report storage</span></span>

## <a name="run-an-inventory-aging-report-storage"></a><span data-ttu-id="80ddb-116">Készletkorosítási jelentés tárolása futtatása</span><span class="sxs-lookup"><span data-stu-id="80ddb-116">Run an Inventory aging report storage</span></span>

1. <span data-ttu-id="80ddb-117">Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletkorosítási jelentés tárhelye**.</span><span class="sxs-lookup"><span data-stu-id="80ddb-117">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="80ddb-118">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80ddb-118">Select **New**.</span></span>
1. <span data-ttu-id="80ddb-119">Írja be a jelentés egyedi nevét a **Folyamatazonosító – Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="80ddb-119">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="80ddb-120">Válassza ki az **azonosító – ID** jelentést, és szűrje a szükséges módon.</span><span class="sxs-lookup"><span data-stu-id="80ddb-120">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="80ddb-121">A jelentés végrehajtása mindig kötegelt feladatként történik.</span><span class="sxs-lookup"><span data-stu-id="80ddb-121">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="80ddb-122">A kötegelt feladat befejezése után a kimeneti fájl megjelenik a **készletkorosítási jelentés tárhelye** lapján.</span><span class="sxs-lookup"><span data-stu-id="80ddb-122">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="80ddb-123">Ha a kimenetet hagyományos rács elrendezésű képernyőként szeretné megtekinteni, válassza a **részletek megtekintése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="80ddb-123">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="80ddb-124">Ha összegzett diagramként szeretné megjeleníteni a kimenetet, válassza a **diagram megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="80ddb-124">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80ddb-125">A képernyő nem tartalmaz a jelentés elrendezésében megadott részösszegeket.</span><span class="sxs-lookup"><span data-stu-id="80ddb-125">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="80ddb-126">A **készlet korosítási jelentés** adatentitása lehetővé teszi egy **készletkorosítási jelentéstárolási** jelentés kimenetének exportálását, ha szűrőt alkalmaz a **Folyamatazonosító – Név** mezőre az adatkezelési támogatások bármely formájává.</span><span class="sxs-lookup"><span data-stu-id="80ddb-126">The **Inventory aging report** data entity lets you export the output of an **Inventory aging report storage** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
