---
title: A szabálytalanságok karanténzónái
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó karanténzónákat.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93ca74ec4586fffa3b9156aadab887629283b98a
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956688"
---
# <a name="quarantine-zones-for-nonconformances"></a><span data-ttu-id="2b88b-103">A szabálytalanságok karanténzónái</span><span class="sxs-lookup"><span data-stu-id="2b88b-103">Quarantine zones for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b88b-104">Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó karanténzónákat.</span><span class="sxs-lookup"><span data-stu-id="2b88b-104">This topic describes how to create and use quarantine zones for nonconformances.</span></span>

<span data-ttu-id="2b88b-105">A **Karanténzónák** képernyőn meghatározhatja azokat a zónákat, amelyek a szabálytalanságokhoz társíthatók.</span><span class="sxs-lookup"><span data-stu-id="2b88b-105">You use the **Quarantine zones** page to define zones that can be assigned to nonconformances.</span></span> <span data-ttu-id="2b88b-106">Szabálytalanság létrehozása esetén beállíthatja a **Karanténzóna** és **Karanténtípus** mezőket az **Általános fülön** a **Szabálytalansásgok** lapon.</span><span class="sxs-lookup"><span data-stu-id="2b88b-106">When you create a nonconformance, you can set the **Quarantine zone** and **Quarantine type** fields on the **General** tab of the **Non conformances** page.</span></span> <span data-ttu-id="2b88b-107">A **Karanténzóna** mező általában azt a területet vagy helyet jelzi, ahol a cikk található.</span><span class="sxs-lookup"><span data-stu-id="2b88b-107">The **Quarantine zone** field typically indicates the area or location where the item is located.</span></span> <span data-ttu-id="2b88b-108">A **Karanténtípus** mező *Korlátozottan használható* vagy *Használhatatlanként* értékkel határozza meg a cikket.</span><span class="sxs-lookup"><span data-stu-id="2b88b-108">The **Quarantine type** field defines the item as either *Restricted usage* or *Unusable*.</span></span>

<span data-ttu-id="2b88b-109">Szabálytalanságra vonatkozó szabálytalansági vagy javítási jelentés nyomtatása esetén megtekintheti, hogy a cikk melyik karanténzónában található.</span><span class="sxs-lookup"><span data-stu-id="2b88b-109">When you print a nonconformance or corrections report for a nonconformance, you can view the quarantine zone where the item is located.</span></span>

<span data-ttu-id="2b88b-110">Szabálytalanságra vonatkozó szabálytalanságcímkét is nyomtathat.</span><span class="sxs-lookup"><span data-stu-id="2b88b-110">You can also print a nonconformance tag for a nonconformance.</span></span> <span data-ttu-id="2b88b-111">Ez a jelentés megmutatja a hozzárendelt karanténzónát, és a használattal kapcsolatos információkat, hogy iránymutatást adjon a hibás anyag kezelésére vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="2b88b-111">This report shows the assigned quarantine zone and information about usage to provide guidance about how defective material should be handled.</span></span> <span data-ttu-id="2b88b-112">A karanténzónák egyes esetekben megfelelhetnek bizonyos készletezési helyeknek vagy üzemi erőforrásoknak.</span><span class="sxs-lookup"><span data-stu-id="2b88b-112">The quarantine zones might correspond to inventory locations or operations resources.</span></span>

## <a name="examples-of-quarantine-zones"></a><span data-ttu-id="2b88b-113">Karanténzónák – példák</span><span class="sxs-lookup"><span data-stu-id="2b88b-113">Examples of quarantine zones</span></span>

### <a name="example-1"></a><span data-ttu-id="2b88b-114">1. példa</span><span class="sxs-lookup"><span data-stu-id="2b88b-114">Example 1</span></span>

<span data-ttu-id="2b88b-115">Egy elektronikai gyártóvállalatnál dolgozik, amely televízókat, hangszórókat és médialejátszókat gyárt.</span><span class="sxs-lookup"><span data-stu-id="2b88b-115">You work at an electronics manufacturing company that produces and distributes televisions, speakers, and media players.</span></span> <span data-ttu-id="2b88b-116">Ebben az esetben karanténzónát konfigurálhat, amelyek az egyes terméktípusokat képviselik.</span><span class="sxs-lookup"><span data-stu-id="2b88b-116">In this case, you can configure a quarantine zone to represent each type of product.</span></span>

### <a name="example-2"></a><span data-ttu-id="2b88b-117">2. példa</span><span class="sxs-lookup"><span data-stu-id="2b88b-117">Example 2</span></span>

<span data-ttu-id="2b88b-118">A nem megfelelő cikkek tárolására három rekesz és két állvány használható.</span><span class="sxs-lookup"><span data-stu-id="2b88b-118">Three bins and two racks are used to store items that are nonconforming.</span></span> <span data-ttu-id="2b88b-119">Ebben az esetben öt karanténzónát konfigurálhat, mindegyik rekeszhez és állványhoz egyet.</span><span class="sxs-lookup"><span data-stu-id="2b88b-119">In this case, you can configure five quarantine zones, one for each bin and each rack.</span></span>

## <a name="create-a-quarantine-zone"></a><span data-ttu-id="2b88b-120">Hozzon létre egy új karanténzónát</span><span class="sxs-lookup"><span data-stu-id="2b88b-120">Create a quarantine zone</span></span>

1. <span data-ttu-id="2b88b-121">Ugorjon a **Készletkezelés \> Beállítás \> Minőségkezelés \> Karanténzónák** pontra.</span><span class="sxs-lookup"><span data-stu-id="2b88b-121">Go to **Inventory management \> Setup \> Quality management \> Quarantine zones**.</span></span>
1. <span data-ttu-id="2b88b-122">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="2b88b-122">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="2b88b-123">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="2b88b-123">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="2b88b-124">**Karanténzóna** – Adjon meg egy egyedi azonosítót vagy nevet a karanténzóna számára.</span><span class="sxs-lookup"><span data-stu-id="2b88b-124">**Quarantine zone** – Enter a unique ID or name for the quarantine zone.</span></span>
    - <span data-ttu-id="2b88b-125">**Leírás** – Adja meg a karanténzóna részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="2b88b-125">**Description** – Enter a detailed description of the quarantine zone.</span></span>

1. <span data-ttu-id="2b88b-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="2b88b-126">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b88b-127">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2b88b-127">Additional resources</span></span>

- [<span data-ttu-id="2b88b-128">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="2b88b-128">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="2b88b-129">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="2b88b-129">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="2b88b-130">A szabálytalanságok jóváhagyásáért felelős dolgozók</span><span class="sxs-lookup"><span data-stu-id="2b88b-130">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="2b88b-131">A szabálytalanságok problématípusai</span><span class="sxs-lookup"><span data-stu-id="2b88b-131">Problem types for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="2b88b-132">A szabálytalanságok diagnosztikai típusai</span><span class="sxs-lookup"><span data-stu-id="2b88b-132">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="2b88b-133">Szabálytalanságok minőségi költségei</span><span class="sxs-lookup"><span data-stu-id="2b88b-133">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="2b88b-134">Műveletek szabálytalanságokhoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="2b88b-134">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="2b88b-135">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="2b88b-135">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
