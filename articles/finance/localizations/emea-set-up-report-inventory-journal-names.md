---
title: Készletnapló-jelentések
description: Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: kfend
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e05f9f79d13793eaf847264ba7f5ce7266fbadcf
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894683"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="3d277-103">Készletnapló-jelentések</span><span class="sxs-lookup"><span data-stu-id="3d277-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d277-104">Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.</span><span class="sxs-lookup"><span data-stu-id="3d277-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="3d277-105">Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét.</span><span class="sxs-lookup"><span data-stu-id="3d277-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="3d277-106">**Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="3d277-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="3d277-107">További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="3d277-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="3d277-108">Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.</span><span class="sxs-lookup"><span data-stu-id="3d277-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

| <span data-ttu-id="3d277-109">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="3d277-109">Country</span></span>            |    <span data-ttu-id="3d277-110">Jelentés leírása</span><span class="sxs-lookup"><span data-stu-id="3d277-110">Report description</span></span>               | <span data-ttu-id="3d277-111">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="3d277-111">Journal type</span></span>     |    <span data-ttu-id="3d277-112">Formátum-hozzárendelés neve</span><span class="sxs-lookup"><span data-stu-id="3d277-112">Format mapping name</span></span>                  |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="3d277-113">Litvánia, Magyarország</span><span class="sxs-lookup"><span data-stu-id="3d277-113">Lithuania, Hungary</span></span> | <span data-ttu-id="3d277-114">Készletkimutatás-jelentés</span><span class="sxs-lookup"><span data-stu-id="3d277-114">Inventory statement report</span></span>          | <span data-ttu-id="3d277-115">Számlálás</span><span class="sxs-lookup"><span data-stu-id="3d277-115">Counting</span></span>         | <span data-ttu-id="3d277-116">Készletkimutatás (HU, LT)</span><span class="sxs-lookup"><span data-stu-id="3d277-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="3d277-117">Lettország, Lengyelország</span><span class="sxs-lookup"><span data-stu-id="3d277-117">Latvia, Poland</span></span>     | <span data-ttu-id="3d277-118">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3d277-118">Inventory reclassification document</span></span> | <span data-ttu-id="3d277-119">Átvitel</span><span class="sxs-lookup"><span data-stu-id="3d277-119">Transfer</span></span>         | <span data-ttu-id="3d277-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="3d277-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="3d277-121">Észtország</span><span class="sxs-lookup"><span data-stu-id="3d277-121">Estonia</span></span>            | <span data-ttu-id="3d277-122">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3d277-122">Inventory reclassification document</span></span> | <span data-ttu-id="3d277-123">Átvitel</span><span class="sxs-lookup"><span data-stu-id="3d277-123">Transfer</span></span>         | <span data-ttu-id="3d277-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="3d277-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="3d277-125">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="3d277-125">Poland</span></span>             | <span data-ttu-id="3d277-126">Belső PW/RW</span><span class="sxs-lookup"><span data-stu-id="3d277-126">Internal PW/RW</span></span>                      | <span data-ttu-id="3d277-127">Mozgás</span><span class="sxs-lookup"><span data-stu-id="3d277-127">Movement</span></span>         | <span data-ttu-id="3d277-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="3d277-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="3d277-129">Lettország</span><span class="sxs-lookup"><span data-stu-id="3d277-129">Latvia</span></span>             | <span data-ttu-id="3d277-130"> Készletmozgási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3d277-130">Inventory movement document</span></span>         | <span data-ttu-id="3d277-131">Mozgás</span><span class="sxs-lookup"><span data-stu-id="3d277-131">Movement</span></span>         | <span data-ttu-id="3d277-132">Mozgás\_LV</span><span class="sxs-lookup"><span data-stu-id="3d277-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="3d277-133">Lettország</span><span class="sxs-lookup"><span data-stu-id="3d277-133">Latvia</span></span>             | <span data-ttu-id="3d277-134">Készletleírási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3d277-134">Inventory write-down document</span></span>       | <span data-ttu-id="3d277-135">Korrekció</span><span class="sxs-lookup"><span data-stu-id="3d277-135">Adjustment</span></span>       | <span data-ttu-id="3d277-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="3d277-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="3d277-137">Lettország</span><span class="sxs-lookup"><span data-stu-id="3d277-137">Latvia</span></span>             | <span data-ttu-id="3d277-138">Szállítás - szállítólevél</span><span class="sxs-lookup"><span data-stu-id="3d277-138">Transfer delivery note</span></span>              | <span data-ttu-id="3d277-139">Átvitel</span><span class="sxs-lookup"><span data-stu-id="3d277-139">Transfer</span></span>         | <span data-ttu-id="3d277-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="3d277-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="3d277-141">Lettország</span><span class="sxs-lookup"><span data-stu-id="3d277-141">Latvia</span></span>             | <span data-ttu-id="3d277-142">Leltáribizonylat-jelentés</span><span class="sxs-lookup"><span data-stu-id="3d277-142">Counting document report</span></span>            | <span data-ttu-id="3d277-143">Számlálás</span><span class="sxs-lookup"><span data-stu-id="3d277-143">Counting</span></span>         | <span data-ttu-id="3d277-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="3d277-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="3d277-145">Lettország</span><span class="sxs-lookup"><span data-stu-id="3d277-145">Latvia</span></span>             | <span data-ttu-id="3d277-146">Leltárlista-jelentés</span><span class="sxs-lookup"><span data-stu-id="3d277-146">Counting list report</span></span>                | <span data-ttu-id="3d277-147">Számlálás</span><span class="sxs-lookup"><span data-stu-id="3d277-147">Counting</span></span>         | <span data-ttu-id="3d277-148">Leltárlista</span><span class="sxs-lookup"><span data-stu-id="3d277-148">Counting list</span></span>                           |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]