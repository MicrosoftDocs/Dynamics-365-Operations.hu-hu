---
title: Készletkorosítási jelentés
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
ms.openlocfilehash: 790c8fe3a52bce652227f1cef97eff6496476100
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201620"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="48a19-103">Készletkorosítási jelentés</span><span class="sxs-lookup"><span data-stu-id="48a19-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="48a19-104">A Microsoft Dynamics 365 Supply Chain Management szolgáltatásban futtathat **Készletkorosítás** jelentést, és a kimeneti fájlt megoszthatja űrlapként és diagramként.</span><span class="sxs-lookup"><span data-stu-id="48a19-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="48a19-105">A képernyőn az oszlopok és az összesítő egyenlegek dinamikusan módosulnak, attól függően, hogy milyen elrendezés van beállítva.</span><span class="sxs-lookup"><span data-stu-id="48a19-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="48a19-106">A diagram olyan vizuális áttekintést nyújt, amely támogatja a szűrést, és lehetővé teszi a részletekbe való leásást.</span><span class="sxs-lookup"><span data-stu-id="48a19-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="48a19-107">Ezenkívül egy **készletkorosítási jelentés** nevű adatentitás lehetővé teszi, hogy a **készletkorosítási** jelentés futtatásának eredményeit egy Microsoft Excel fájl vagy egy PDF-fájl formátumában exportálják.</span><span class="sxs-lookup"><span data-stu-id="48a19-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="48a19-108">A **készletkorosítási** jelentés futtatására szolgáló módszer olyan esetekben hasznos, amikor a kimenet sok sort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="48a19-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="48a19-109">Például a kimenet sok sort fog tartalmazni, ha 50 000 cikket és 300 üzletet készítenek raktárakként, és a készletkorosítást cikk, telephely és raktár szerint kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="48a19-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="48a19-110">Készletkorosítási jelentés futtatása</span><span class="sxs-lookup"><span data-stu-id="48a19-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="48a19-111">Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletkorosítási jelentés tárhelye**.</span><span class="sxs-lookup"><span data-stu-id="48a19-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="48a19-112">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="48a19-112">Select **New**.</span></span>
1. <span data-ttu-id="48a19-113">Írja be a jelentés egyedi nevét a **Folyamatazonosító – Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="48a19-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="48a19-114">Válassza ki az **azonosító – ID** jelentést, és szűrje a szükséges módon.</span><span class="sxs-lookup"><span data-stu-id="48a19-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="48a19-115">A jelentés végrehajtása mindig kötegelt feladatként történik.</span><span class="sxs-lookup"><span data-stu-id="48a19-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="48a19-116">A kötegelt feladat befejezése után a kimeneti fájl megjelenik a **készletkorosítási jelentés tárhelye** lapján.</span><span class="sxs-lookup"><span data-stu-id="48a19-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="48a19-117">Ha a kimenetet hagyományos rács elrendezésű képernyőként szeretné megtekinteni, válassza a **részletek megtekintése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="48a19-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="48a19-118">Ha összegzett diagramként szeretné megjeleníteni a kimenetet, válassza a **diagram megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="48a19-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48a19-119">A képernyő nem tartalmaz a jelentés elrendezésében megadott részösszegeket.</span><span class="sxs-lookup"><span data-stu-id="48a19-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="48a19-120">A **készlet korosítási jelentés** adatentitása lehetővé teszi egy **készletkorosítási** jelentés kimenetének exportálását, ha szűrőt alkalmaz a **Folyamatazonosító – Név** mezőre az adatkezelési támogatások bármely formájává.</span><span class="sxs-lookup"><span data-stu-id="48a19-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
