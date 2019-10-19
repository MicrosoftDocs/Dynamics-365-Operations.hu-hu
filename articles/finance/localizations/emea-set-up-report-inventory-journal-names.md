---
title: Készletnapló-jelentések
description: Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d051c8ab7f15f69dd06db0986c3151b61d595b6d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175769"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="a55df-103">Készletnapló-jelentések</span><span class="sxs-lookup"><span data-stu-id="a55df-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a55df-104">Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.</span><span class="sxs-lookup"><span data-stu-id="a55df-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="a55df-105">Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét.</span><span class="sxs-lookup"><span data-stu-id="a55df-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="a55df-106">**Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="a55df-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="a55df-107">További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="a55df-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="a55df-108">Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.</span><span class="sxs-lookup"><span data-stu-id="a55df-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="a55df-109">**Ország**</span><span class="sxs-lookup"><span data-stu-id="a55df-109">**Country**</span></span>        | <span data-ttu-id="a55df-110">**Jelentés leírása**</span><span class="sxs-lookup"><span data-stu-id="a55df-110">**Report description**</span></span>              | <span data-ttu-id="a55df-111">**Napló típusa**</span><span class="sxs-lookup"><span data-stu-id="a55df-111">**Journal type**</span></span> | <span data-ttu-id="a55df-112">**Formátum-hozzárendelés neve**</span><span class="sxs-lookup"><span data-stu-id="a55df-112">**Format mapping name**</span></span>                 |
| <span data-ttu-id="a55df-113">Litvánia, Magyarország</span><span class="sxs-lookup"><span data-stu-id="a55df-113">Lithuania, Hungary</span></span> | <span data-ttu-id="a55df-114">Készletkimutatás-jelentés</span><span class="sxs-lookup"><span data-stu-id="a55df-114">Inventory statement report</span></span>          | <span data-ttu-id="a55df-115">Számlálás</span><span class="sxs-lookup"><span data-stu-id="a55df-115">Counting</span></span>         | <span data-ttu-id="a55df-116">Készletkimutatás (HU, LT)</span><span class="sxs-lookup"><span data-stu-id="a55df-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="a55df-117">Lettország, Lengyelország</span><span class="sxs-lookup"><span data-stu-id="a55df-117">Latvia, Poland</span></span>     | <span data-ttu-id="a55df-118">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="a55df-118">Inventory reclassification document</span></span> | <span data-ttu-id="a55df-119">Átvitel</span><span class="sxs-lookup"><span data-stu-id="a55df-119">Transfer</span></span>         | <span data-ttu-id="a55df-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="a55df-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="a55df-121">Észtország</span><span class="sxs-lookup"><span data-stu-id="a55df-121">Estonia</span></span>            | <span data-ttu-id="a55df-122">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="a55df-122">Inventory reclassification document</span></span> | <span data-ttu-id="a55df-123">Átvitel</span><span class="sxs-lookup"><span data-stu-id="a55df-123">Transfer</span></span>         | <span data-ttu-id="a55df-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="a55df-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="a55df-125">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="a55df-125">Poland</span></span>             | <span data-ttu-id="a55df-126">Belső PW/RW</span><span class="sxs-lookup"><span data-stu-id="a55df-126">Internal PW/RW</span></span>                      | <span data-ttu-id="a55df-127">Mozgás</span><span class="sxs-lookup"><span data-stu-id="a55df-127">Movement</span></span>         | <span data-ttu-id="a55df-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="a55df-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="a55df-129">Lettország</span><span class="sxs-lookup"><span data-stu-id="a55df-129">Latvia</span></span>             | <span data-ttu-id="a55df-130"> Készletmozgási bizonylat</span><span class="sxs-lookup"><span data-stu-id="a55df-130">Inventory movement document</span></span>         | <span data-ttu-id="a55df-131">Mozgás</span><span class="sxs-lookup"><span data-stu-id="a55df-131">Movement</span></span>         | <span data-ttu-id="a55df-132">Mozgás\_LV</span><span class="sxs-lookup"><span data-stu-id="a55df-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="a55df-133">Lettország</span><span class="sxs-lookup"><span data-stu-id="a55df-133">Latvia</span></span>             | <span data-ttu-id="a55df-134">Készletleírási bizonylat</span><span class="sxs-lookup"><span data-stu-id="a55df-134">Inventory write-down document</span></span>       | <span data-ttu-id="a55df-135">Korrekció</span><span class="sxs-lookup"><span data-stu-id="a55df-135">Adjustment</span></span>       | <span data-ttu-id="a55df-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="a55df-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="a55df-137">Lettország</span><span class="sxs-lookup"><span data-stu-id="a55df-137">Latvia</span></span>             | <span data-ttu-id="a55df-138">Szállítás - szállítólevél</span><span class="sxs-lookup"><span data-stu-id="a55df-138">Transfer delivery note</span></span>              | <span data-ttu-id="a55df-139">Átvitel</span><span class="sxs-lookup"><span data-stu-id="a55df-139">Transfer</span></span>         | <span data-ttu-id="a55df-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="a55df-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="a55df-141">Lettország</span><span class="sxs-lookup"><span data-stu-id="a55df-141">Latvia</span></span>             | <span data-ttu-id="a55df-142">Leltáribizonylat-jelentés</span><span class="sxs-lookup"><span data-stu-id="a55df-142">Counting document report</span></span>            | <span data-ttu-id="a55df-143">Számlálás</span><span class="sxs-lookup"><span data-stu-id="a55df-143">Counting</span></span>         | <span data-ttu-id="a55df-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="a55df-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="a55df-145">Lettország</span><span class="sxs-lookup"><span data-stu-id="a55df-145">Latvia</span></span>             | <span data-ttu-id="a55df-146">Leltárlista-jelentés</span><span class="sxs-lookup"><span data-stu-id="a55df-146">Counting list report</span></span>                | <span data-ttu-id="a55df-147">Számlálás</span><span class="sxs-lookup"><span data-stu-id="a55df-147">Counting</span></span>         | <span data-ttu-id="a55df-148">Leltárlista</span><span class="sxs-lookup"><span data-stu-id="a55df-148">Counting list</span></span>                           |





