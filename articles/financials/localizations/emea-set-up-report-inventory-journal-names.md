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
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852410"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="bacf7-103">Készletnapló-jelentések</span><span class="sxs-lookup"><span data-stu-id="bacf7-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bacf7-104">Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.</span><span class="sxs-lookup"><span data-stu-id="bacf7-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="bacf7-105">Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét.</span><span class="sxs-lookup"><span data-stu-id="bacf7-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="bacf7-106">**Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="bacf7-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="bacf7-107">További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="bacf7-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="bacf7-108">Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.</span><span class="sxs-lookup"><span data-stu-id="bacf7-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="bacf7-109">**Ország**</span><span class="sxs-lookup"><span data-stu-id="bacf7-109">**Country**</span></span>        | <span data-ttu-id="bacf7-110">**Jelentés leírása**</span><span class="sxs-lookup"><span data-stu-id="bacf7-110">**Report description**</span></span>              | <span data-ttu-id="bacf7-111">**Napló típusa**</span><span class="sxs-lookup"><span data-stu-id="bacf7-111">**Journal type**</span></span> | <span data-ttu-id="bacf7-112">**Formátum-hozzárendelés neve**</span><span class="sxs-lookup"><span data-stu-id="bacf7-112">**Format mapping name**</span></span>                 |
| <span data-ttu-id="bacf7-113">Litvánia, Magyarország</span><span class="sxs-lookup"><span data-stu-id="bacf7-113">Lithuania, Hungary</span></span> | <span data-ttu-id="bacf7-114">Készletkimutatás-jelentés</span><span class="sxs-lookup"><span data-stu-id="bacf7-114">Inventory statement report</span></span>          | <span data-ttu-id="bacf7-115">Számlálás</span><span class="sxs-lookup"><span data-stu-id="bacf7-115">Counting</span></span>         | <span data-ttu-id="bacf7-116">Készletkimutatás (HU, LT)</span><span class="sxs-lookup"><span data-stu-id="bacf7-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="bacf7-117">Lettország, Lengyelország</span><span class="sxs-lookup"><span data-stu-id="bacf7-117">Latvia, Poland</span></span>     | <span data-ttu-id="bacf7-118">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="bacf7-118">Inventory reclassification document</span></span> | <span data-ttu-id="bacf7-119">Átvitel</span><span class="sxs-lookup"><span data-stu-id="bacf7-119">Transfer</span></span>         | <span data-ttu-id="bacf7-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="bacf7-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="bacf7-121">Észtország</span><span class="sxs-lookup"><span data-stu-id="bacf7-121">Estonia</span></span>            | <span data-ttu-id="bacf7-122">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="bacf7-122">Inventory reclassification document</span></span> | <span data-ttu-id="bacf7-123">Átvitel</span><span class="sxs-lookup"><span data-stu-id="bacf7-123">Transfer</span></span>         | <span data-ttu-id="bacf7-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="bacf7-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="bacf7-125">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="bacf7-125">Poland</span></span>             | <span data-ttu-id="bacf7-126">Belső PW/RW</span><span class="sxs-lookup"><span data-stu-id="bacf7-126">Internal PW/RW</span></span>                      | <span data-ttu-id="bacf7-127">Mozgás</span><span class="sxs-lookup"><span data-stu-id="bacf7-127">Movement</span></span>         | <span data-ttu-id="bacf7-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="bacf7-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="bacf7-129">Lettország</span><span class="sxs-lookup"><span data-stu-id="bacf7-129">Latvia</span></span>             | <span data-ttu-id="bacf7-130"> Készletmozgási bizonylat</span><span class="sxs-lookup"><span data-stu-id="bacf7-130">Inventory movement document</span></span>         | <span data-ttu-id="bacf7-131">Mozgás</span><span class="sxs-lookup"><span data-stu-id="bacf7-131">Movement</span></span>         | <span data-ttu-id="bacf7-132">Mozgás\_LV</span><span class="sxs-lookup"><span data-stu-id="bacf7-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="bacf7-133">Lettország</span><span class="sxs-lookup"><span data-stu-id="bacf7-133">Latvia</span></span>             | <span data-ttu-id="bacf7-134">Készletleírási bizonylat</span><span class="sxs-lookup"><span data-stu-id="bacf7-134">Inventory write-down document</span></span>       | <span data-ttu-id="bacf7-135">Korrekció</span><span class="sxs-lookup"><span data-stu-id="bacf7-135">Adjustment</span></span>       | <span data-ttu-id="bacf7-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="bacf7-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="bacf7-137">Lettország</span><span class="sxs-lookup"><span data-stu-id="bacf7-137">Latvia</span></span>             | <span data-ttu-id="bacf7-138">Szállítás - szállítólevél</span><span class="sxs-lookup"><span data-stu-id="bacf7-138">Transfer delivery note</span></span>              | <span data-ttu-id="bacf7-139">Átvitel</span><span class="sxs-lookup"><span data-stu-id="bacf7-139">Transfer</span></span>         | <span data-ttu-id="bacf7-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="bacf7-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="bacf7-141">Lettország</span><span class="sxs-lookup"><span data-stu-id="bacf7-141">Latvia</span></span>             | <span data-ttu-id="bacf7-142">Leltáribizonylat-jelentés</span><span class="sxs-lookup"><span data-stu-id="bacf7-142">Counting document report</span></span>            | <span data-ttu-id="bacf7-143">Számlálás</span><span class="sxs-lookup"><span data-stu-id="bacf7-143">Counting</span></span>         | <span data-ttu-id="bacf7-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="bacf7-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="bacf7-145">Lettország</span><span class="sxs-lookup"><span data-stu-id="bacf7-145">Latvia</span></span>             | <span data-ttu-id="bacf7-146">Leltárlista-jelentés</span><span class="sxs-lookup"><span data-stu-id="bacf7-146">Counting list report</span></span>                | <span data-ttu-id="bacf7-147">Számlálás</span><span class="sxs-lookup"><span data-stu-id="bacf7-147">Counting</span></span>         | <span data-ttu-id="bacf7-148">Leltárlista</span><span class="sxs-lookup"><span data-stu-id="bacf7-148">Counting list</span></span>                           |





