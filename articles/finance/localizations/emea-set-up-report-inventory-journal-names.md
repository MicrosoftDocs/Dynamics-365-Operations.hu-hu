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
ms.openlocfilehash: 5b1ee2f7d75897da4cc884e11d2a499ce4016a00
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818283"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="3de24-103">Készletnapló-jelentések</span><span class="sxs-lookup"><span data-stu-id="3de24-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3de24-104">Konfigurálható készletjelentések elektronikus jelentés alapján történő használatakor be kell állítani egy kapcsolatot az adott jelentés és egy naplótípusa között.</span><span class="sxs-lookup"><span data-stu-id="3de24-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="3de24-105">Egy adott jelentés és naplótípus közötti kapcsolat beállításához a **Készletnaplónevek** oldalon (**Készletgazdálkodás** &gt; **Beállítás** &gt; **Naplónevek** &gt; **Készlet**) adja meg a jelentés nevét.</span><span class="sxs-lookup"><span data-stu-id="3de24-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="3de24-106">**Megjegyzés:** támogatott konfigurációk beállításához töltse le a szükséges elektronikus jelentési konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="3de24-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="3de24-107">További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="3de24-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="3de24-108">Az alábbi táblázatban példák találhatók Európában támogatott konfigurációjú készletjelentésekre.</span><span class="sxs-lookup"><span data-stu-id="3de24-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

| <span data-ttu-id="3de24-109">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="3de24-109">Country</span></span>            |    <span data-ttu-id="3de24-110">Jelentés leírása</span><span class="sxs-lookup"><span data-stu-id="3de24-110">Report description</span></span>               | <span data-ttu-id="3de24-111">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="3de24-111">Journal type</span></span>     |    <span data-ttu-id="3de24-112">Formátum-hozzárendelés neve</span><span class="sxs-lookup"><span data-stu-id="3de24-112">Format mapping name</span></span>                  |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="3de24-113">Litvánia, Magyarország</span><span class="sxs-lookup"><span data-stu-id="3de24-113">Lithuania, Hungary</span></span> | <span data-ttu-id="3de24-114">Készletkimutatás-jelentés</span><span class="sxs-lookup"><span data-stu-id="3de24-114">Inventory statement report</span></span>          | <span data-ttu-id="3de24-115">Számlálás</span><span class="sxs-lookup"><span data-stu-id="3de24-115">Counting</span></span>         | <span data-ttu-id="3de24-116">Készletkimutatás (HU, LT)</span><span class="sxs-lookup"><span data-stu-id="3de24-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="3de24-117">Lettország, Lengyelország</span><span class="sxs-lookup"><span data-stu-id="3de24-117">Latvia, Poland</span></span>     | <span data-ttu-id="3de24-118">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3de24-118">Inventory reclassification document</span></span> | <span data-ttu-id="3de24-119">Átvitel</span><span class="sxs-lookup"><span data-stu-id="3de24-119">Transfer</span></span>         | <span data-ttu-id="3de24-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="3de24-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="3de24-121">Észtország</span><span class="sxs-lookup"><span data-stu-id="3de24-121">Estonia</span></span>            | <span data-ttu-id="3de24-122">Készletátsorolási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3de24-122">Inventory reclassification document</span></span> | <span data-ttu-id="3de24-123">Átvitel</span><span class="sxs-lookup"><span data-stu-id="3de24-123">Transfer</span></span>         | <span data-ttu-id="3de24-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="3de24-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="3de24-125">Lengyelország</span><span class="sxs-lookup"><span data-stu-id="3de24-125">Poland</span></span>             | <span data-ttu-id="3de24-126">Belső PW/RW</span><span class="sxs-lookup"><span data-stu-id="3de24-126">Internal PW/RW</span></span>                      | <span data-ttu-id="3de24-127">Mozgás</span><span class="sxs-lookup"><span data-stu-id="3de24-127">Movement</span></span>         | <span data-ttu-id="3de24-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="3de24-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="3de24-129">Lettország</span><span class="sxs-lookup"><span data-stu-id="3de24-129">Latvia</span></span>             | <span data-ttu-id="3de24-130"> Készletmozgási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3de24-130">Inventory movement document</span></span>         | <span data-ttu-id="3de24-131">Mozgás</span><span class="sxs-lookup"><span data-stu-id="3de24-131">Movement</span></span>         | <span data-ttu-id="3de24-132">Mozgás\_LV</span><span class="sxs-lookup"><span data-stu-id="3de24-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="3de24-133">Lettország</span><span class="sxs-lookup"><span data-stu-id="3de24-133">Latvia</span></span>             | <span data-ttu-id="3de24-134">Készletleírási bizonylat</span><span class="sxs-lookup"><span data-stu-id="3de24-134">Inventory write-down document</span></span>       | <span data-ttu-id="3de24-135">Korrekció</span><span class="sxs-lookup"><span data-stu-id="3de24-135">Adjustment</span></span>       | <span data-ttu-id="3de24-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="3de24-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="3de24-137">Lettország</span><span class="sxs-lookup"><span data-stu-id="3de24-137">Latvia</span></span>             | <span data-ttu-id="3de24-138">Szállítás - szállítólevél</span><span class="sxs-lookup"><span data-stu-id="3de24-138">Transfer delivery note</span></span>              | <span data-ttu-id="3de24-139">Átvitel</span><span class="sxs-lookup"><span data-stu-id="3de24-139">Transfer</span></span>         | <span data-ttu-id="3de24-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="3de24-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="3de24-141">Lettország</span><span class="sxs-lookup"><span data-stu-id="3de24-141">Latvia</span></span>             | <span data-ttu-id="3de24-142">Leltáribizonylat-jelentés</span><span class="sxs-lookup"><span data-stu-id="3de24-142">Counting document report</span></span>            | <span data-ttu-id="3de24-143">Számlálás</span><span class="sxs-lookup"><span data-stu-id="3de24-143">Counting</span></span>         | <span data-ttu-id="3de24-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="3de24-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="3de24-145">Lettország</span><span class="sxs-lookup"><span data-stu-id="3de24-145">Latvia</span></span>             | <span data-ttu-id="3de24-146">Leltárlista-jelentés</span><span class="sxs-lookup"><span data-stu-id="3de24-146">Counting list report</span></span>                | <span data-ttu-id="3de24-147">Számlálás</span><span class="sxs-lookup"><span data-stu-id="3de24-147">Counting</span></span>         | <span data-ttu-id="3de24-148">Leltárlista</span><span class="sxs-lookup"><span data-stu-id="3de24-148">Counting list</span></span>                           |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]