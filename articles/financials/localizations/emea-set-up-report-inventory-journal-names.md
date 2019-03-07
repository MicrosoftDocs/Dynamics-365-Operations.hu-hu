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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b7077522e02f6b91d335c70adc26e23524d65aae
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "370838"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="33700-103">Készletnapló-jelentések</span><span class="sxs-lookup"><span data-stu-id="33700-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33700-104">Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.</span><span class="sxs-lookup"><span data-stu-id="33700-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="33700-105">Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét.</span><span class="sxs-lookup"><span data-stu-id="33700-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="33700-106">**Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="33700-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="33700-107">További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="33700-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="33700-108">Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.</span><span class="sxs-lookup"><span data-stu-id="33700-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="33700-109">**Ország**</span><span class="sxs-lookup"><span data-stu-id="33700-109">**Country**</span></span>        | <span data-ttu-id="33700-110">**Jelentés leírása**</span><span class="sxs-lookup"><span data-stu-id="33700-110">**Report description**</span></span>              | <span data-ttu-id="33700-111">**Napló típusa**</span><span class="sxs-lookup"><span data-stu-id="33700-111">**Journal type**</span></span> | <span data-ttu-id="33700-112">**Formátum-hozzárendelés neve**</span><span class="sxs-lookup"><span data-stu-id="33700-112">**Format mapping name**</span></span>                 |
| <span data-ttu-id="33700-113">Litvánia, Magyarország</span><span class="sxs-lookup"><span data-stu-id="33700-113">Lithuania, Hungary</span></span> | <span data-ttu-id="33700-114">Készletkimutatás-jelentés</span><span class="sxs-lookup"><span data-stu-id="33700-114">Inventory statement report</span></span>          | <span data-ttu-id="33700-115">Számlálás</span><span class="sxs-lookup"><span data-stu-id="33700-115">Counting</span></span>         | <span data-ttu-id="33700-116">Készletkimutatás (HU, LT)</span><span class="sxs-lookup"><span data-stu-id="33700-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="33700-117">Lettország, Lengyelország</span><span class="sxs-lookup"><span data-stu-id="33700-117">Latvia, Poland</span></span>     | <span data-ttu-id="33700-118">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="33700-118">Inventory reclassification document</span></span> | <span data-ttu-id="33700-119">Átvitel</span><span class="sxs-lookup"><span data-stu-id="33700-119">Transfer</span></span>         | <span data-ttu-id="33700-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="33700-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="33700-121">Észtország</span><span class="sxs-lookup"><span data-stu-id="33700-121">Estonia</span></span>            | <span data-ttu-id="33700-122">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="33700-122">Inventory reclassification document</span></span> | <span data-ttu-id="33700-123">Átvitel</span><span class="sxs-lookup"><span data-stu-id="33700-123">Transfer</span></span>         | <span data-ttu-id="33700-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="33700-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="33700-125">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="33700-125">Poland</span></span>             | <span data-ttu-id="33700-126">Belső PW/RW</span><span class="sxs-lookup"><span data-stu-id="33700-126">Internal PW/RW</span></span>                      | <span data-ttu-id="33700-127">Mozgás</span><span class="sxs-lookup"><span data-stu-id="33700-127">Movement</span></span>         | <span data-ttu-id="33700-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="33700-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="33700-129">Lettország</span><span class="sxs-lookup"><span data-stu-id="33700-129">Latvia</span></span>             | <span data-ttu-id="33700-130"> Készletmozgási bizonylat</span><span class="sxs-lookup"><span data-stu-id="33700-130">Inventory movement document</span></span>         | <span data-ttu-id="33700-131">Mozgás</span><span class="sxs-lookup"><span data-stu-id="33700-131">Movement</span></span>         | <span data-ttu-id="33700-132">Mozgás\_LV</span><span class="sxs-lookup"><span data-stu-id="33700-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="33700-133">Lettország</span><span class="sxs-lookup"><span data-stu-id="33700-133">Latvia</span></span>             | <span data-ttu-id="33700-134">Készletleírási bizonylat</span><span class="sxs-lookup"><span data-stu-id="33700-134">Inventory write-down document</span></span>       | <span data-ttu-id="33700-135">Korrekció</span><span class="sxs-lookup"><span data-stu-id="33700-135">Adjustment</span></span>       | <span data-ttu-id="33700-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="33700-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="33700-137">Lettország</span><span class="sxs-lookup"><span data-stu-id="33700-137">Latvia</span></span>             | <span data-ttu-id="33700-138">Szállítás - szállítólevél</span><span class="sxs-lookup"><span data-stu-id="33700-138">Transfer delivery note</span></span>              | <span data-ttu-id="33700-139">Átvitel</span><span class="sxs-lookup"><span data-stu-id="33700-139">Transfer</span></span>         | <span data-ttu-id="33700-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="33700-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="33700-141">Lettország</span><span class="sxs-lookup"><span data-stu-id="33700-141">Latvia</span></span>             | <span data-ttu-id="33700-142">Leltáribizonylat-jelentés</span><span class="sxs-lookup"><span data-stu-id="33700-142">Counting document report</span></span>            | <span data-ttu-id="33700-143">Számlálás</span><span class="sxs-lookup"><span data-stu-id="33700-143">Counting</span></span>         | <span data-ttu-id="33700-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="33700-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="33700-145">Lettország</span><span class="sxs-lookup"><span data-stu-id="33700-145">Latvia</span></span>             | <span data-ttu-id="33700-146">Leltárlista-jelentés</span><span class="sxs-lookup"><span data-stu-id="33700-146">Counting list report</span></span>                | <span data-ttu-id="33700-147">Számlálás</span><span class="sxs-lookup"><span data-stu-id="33700-147">Counting</span></span>         | <span data-ttu-id="33700-148">Leltárlista</span><span class="sxs-lookup"><span data-stu-id="33700-148">Counting list</span></span>                           |





