---
title: Készletkorosítási jelentés
description: Ez a témakör bemutatja a funkciókat, amelyekkel készletkorosítási jelentést futtathat és űrlap és diagram formájában elérhetővé teheti a kimeneti fájlt.
author: AndersGirke
manager: AnnBe
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 21411c104c854224ff3689dc8e080b88d9fc7d23
ms.sourcegitcommit: 9267608347c9781fb4ba70f1384ca24da69c716d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2019
ms.locfileid: "2810251"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="10736-103">Készletkorosítási jelentés</span><span class="sxs-lookup"><span data-stu-id="10736-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="10736-104">A Microsoft Dynamics 365 Supply Chain Management szolgáltatásban futtathat **Készletkorosítás** jelentést, és a kimeneti fájlt megoszthatja űrlapként és diagramként.</span><span class="sxs-lookup"><span data-stu-id="10736-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="10736-105">A képernyőn az oszlopok és az összesítő egyenlegek dinamikusan módosulnak, attól függően, hogy milyen elrendezés van beállítva.</span><span class="sxs-lookup"><span data-stu-id="10736-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="10736-106">A diagram olyan vizuális áttekintést nyújt, amely támogatja a szűrést, és lehetővé teszi a részletekbe való leásást.</span><span class="sxs-lookup"><span data-stu-id="10736-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="10736-107">Ezenkívül egy **készletkorosítási jelentés** nevű adatentitás lehetővé teszi, hogy a **készletkorosítási** jelentés futtatásának eredményeit egy Microsoft Excel fájl vagy egy PDF-fájl formátumában exportálják.</span><span class="sxs-lookup"><span data-stu-id="10736-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="10736-108">A **készletkorosítási** jelentés futtatására szolgáló módszer olyan esetekben hasznos, amikor a kimenet sok sort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="10736-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="10736-109">Például a kimenet sok sort fog tartalmazni, ha 50 000 cikket és 300 üzletet készítenek raktárakként, és a készletkorosítást cikk, telephely és raktár szerint kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="10736-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="10736-110">Készletkorosítási jelentés futtatása</span><span class="sxs-lookup"><span data-stu-id="10736-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="10736-111">Lépjen a **Költséggazdálkodás \> Lekérdezések és jelentések \> Készletkorosítási jelentés tárhelye**.</span><span class="sxs-lookup"><span data-stu-id="10736-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="10736-112">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10736-112">Select **New**.</span></span>
1. <span data-ttu-id="10736-113">Írja be a jelentés egyedi nevét a **Folyamatazonosító – Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="10736-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="10736-114">Válassza ki az **azonosító – ID** jelentést, és szűrje a szükséges módon.</span><span class="sxs-lookup"><span data-stu-id="10736-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="10736-115">A jelentés végrehajtása mindig kötegelt feladatként történik.</span><span class="sxs-lookup"><span data-stu-id="10736-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="10736-116">A kötegelt feladat befejezése után a kimeneti fájl megjelenik a **készletkorosítási jelentés tárhelye** lapján.</span><span class="sxs-lookup"><span data-stu-id="10736-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="10736-117">Ha a kimenetet hagyományos rács elrendezésű képernyőként szeretné megtekinteni, válassza a **részletek megtekintése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="10736-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="10736-118">Ha összegzett diagramként szeretné megjeleníteni a kimenetet, válassza a **diagram megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10736-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="10736-119">A képernyő nem tartalmaz a jelentés elrendezésében megadott részösszegeket.</span><span class="sxs-lookup"><span data-stu-id="10736-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="10736-120">A **készlet korosítási jelentés** adatentitása lehetővé teszi egy **készletkorosítási** jelentés kimenetének exportálását, ha szűrőt alkalmaz a **Folyamatazonosító – Név** mezőre az adatkezelési támogatások bármely formájává.</span><span class="sxs-lookup"><span data-stu-id="10736-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
