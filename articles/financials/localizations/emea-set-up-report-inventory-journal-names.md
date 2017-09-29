---
title: "Készletnapló-jelentések"
description: "Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: f4bc900e2279abcbaea84e0d4ef7bf2b01f9f039
ms.contentlocale: hu-hu
ms.lasthandoff: 06/29/2017


---

# <a name="inventory-journal-reports"></a><span data-ttu-id="97e65-103">Készletnapló-jelentések</span><span class="sxs-lookup"><span data-stu-id="97e65-103">Inventory journal reports</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="97e65-104">Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.</span><span class="sxs-lookup"><span data-stu-id="97e65-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="97e65-105">Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét.</span><span class="sxs-lookup"><span data-stu-id="97e65-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="97e65-106">**Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="97e65-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="97e65-107">További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span><span class="sxs-lookup"><span data-stu-id="97e65-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span></span> <span data-ttu-id="97e65-108">Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.</span><span class="sxs-lookup"><span data-stu-id="97e65-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>
|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="97e65-109">**Ország**</span><span class="sxs-lookup"><span data-stu-id="97e65-109">**Country**</span></span>        | <span data-ttu-id="97e65-110">**Jelentés leírása**</span><span class="sxs-lookup"><span data-stu-id="97e65-110">**Report description**</span></span>              | <span data-ttu-id="97e65-111">**Napló típusa**</span><span class="sxs-lookup"><span data-stu-id="97e65-111">**Journal type**</span></span> | <span data-ttu-id="97e65-112">**Formátum-hozzárendelés neve**</span><span class="sxs-lookup"><span data-stu-id="97e65-112">**Format mapping name**</span></span>                 |
| <span data-ttu-id="97e65-113">Litvánia, Magyarország</span><span class="sxs-lookup"><span data-stu-id="97e65-113">Lithuania, Hungary</span></span> | <span data-ttu-id="97e65-114">Készletkimutatás-jelentés</span><span class="sxs-lookup"><span data-stu-id="97e65-114">Inventory statement report</span></span>          | <span data-ttu-id="97e65-115">Számlálás</span><span class="sxs-lookup"><span data-stu-id="97e65-115">Counting</span></span>         | <span data-ttu-id="97e65-116">Készletkimutatás (HU, LT)</span><span class="sxs-lookup"><span data-stu-id="97e65-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="97e65-117">Lettország, Lengyelország</span><span class="sxs-lookup"><span data-stu-id="97e65-117">Latvia, Poland</span></span>     | <span data-ttu-id="97e65-118">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="97e65-118">Inventory reclassification document</span></span> | <span data-ttu-id="97e65-119">Átvitel</span><span class="sxs-lookup"><span data-stu-id="97e65-119">Transfer</span></span>         | <span data-ttu-id="97e65-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="97e65-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="97e65-121">Észtország</span><span class="sxs-lookup"><span data-stu-id="97e65-121">Estonia</span></span>            | <span data-ttu-id="97e65-122">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="97e65-122">Inventory reclassification document</span></span> | <span data-ttu-id="97e65-123">Átvitel</span><span class="sxs-lookup"><span data-stu-id="97e65-123">Transfer</span></span>         | <span data-ttu-id="97e65-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="97e65-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="97e65-125">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="97e65-125">Poland</span></span>             | <span data-ttu-id="97e65-126">Belső PW/RW</span><span class="sxs-lookup"><span data-stu-id="97e65-126">Internal PW/RW</span></span>                      | <span data-ttu-id="97e65-127">Mozgás</span><span class="sxs-lookup"><span data-stu-id="97e65-127">Movement</span></span>         | <span data-ttu-id="97e65-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="97e65-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="97e65-129">Lettország</span><span class="sxs-lookup"><span data-stu-id="97e65-129">Latvia</span></span>             | <span data-ttu-id="97e65-130"> Készletmozgási bizonylat</span><span class="sxs-lookup"><span data-stu-id="97e65-130">Inventory movement document</span></span>         | <span data-ttu-id="97e65-131">Mozgás</span><span class="sxs-lookup"><span data-stu-id="97e65-131">Movement</span></span>         | <span data-ttu-id="97e65-132">Mozgás\_LV</span><span class="sxs-lookup"><span data-stu-id="97e65-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="97e65-133">Lettország</span><span class="sxs-lookup"><span data-stu-id="97e65-133">Latvia</span></span>             | <span data-ttu-id="97e65-134">Készletleírási bizonylat</span><span class="sxs-lookup"><span data-stu-id="97e65-134">Inventory write-down document</span></span>       | <span data-ttu-id="97e65-135">Korrekció</span><span class="sxs-lookup"><span data-stu-id="97e65-135">Adjustment</span></span>       | <span data-ttu-id="97e65-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="97e65-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="97e65-137">Lettország</span><span class="sxs-lookup"><span data-stu-id="97e65-137">Latvia</span></span>             | <span data-ttu-id="97e65-138">Szállítás - szállítólevél</span><span class="sxs-lookup"><span data-stu-id="97e65-138">Transfer delivery note</span></span>              | <span data-ttu-id="97e65-139">Átvitel</span><span class="sxs-lookup"><span data-stu-id="97e65-139">Transfer</span></span>         | <span data-ttu-id="97e65-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="97e65-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="97e65-141">Lettország</span><span class="sxs-lookup"><span data-stu-id="97e65-141">Latvia</span></span>             | <span data-ttu-id="97e65-142">Leltáribizonylat-jelentés</span><span class="sxs-lookup"><span data-stu-id="97e65-142">Counting document report</span></span>            | <span data-ttu-id="97e65-143">Számlálás</span><span class="sxs-lookup"><span data-stu-id="97e65-143">Counting</span></span>         | <span data-ttu-id="97e65-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="97e65-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="97e65-145">Lettország</span><span class="sxs-lookup"><span data-stu-id="97e65-145">Latvia</span></span>             | <span data-ttu-id="97e65-146">Leltárlista-jelentés</span><span class="sxs-lookup"><span data-stu-id="97e65-146">Counting list report</span></span>                | <span data-ttu-id="97e65-147">Számlálás</span><span class="sxs-lookup"><span data-stu-id="97e65-147">Counting</span></span>         | <span data-ttu-id="97e65-148">Leltárlista</span><span class="sxs-lookup"><span data-stu-id="97e65-148">Counting list</span></span>                           |






