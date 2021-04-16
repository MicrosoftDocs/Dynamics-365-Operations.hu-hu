---
title: Okkódok beállítása
description: A Dynamics 365 Human Resources okkódokat használ annak elmagyarázása érdekében, hogy miért változnak az alkalmazottak juttatásai.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ee74cb8b11c9b72940448077ee485ade4c0b7a39
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801047"
---
# <a name="set-up-reason-codes"></a><span data-ttu-id="dfddf-103">Okkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="dfddf-103">Set up reason codes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="dfddf-104">A Dynamics 365 Human Resources okkódokat használ annak elmagyarázása érdekében, hogy miért változnak az alkalmazottak juttatásai.</span><span class="sxs-lookup"><span data-stu-id="dfddf-104">Dynamics 365 Human Resources uses reason codes to explain why an employee’s benefits are changing.</span></span>

> [!NOTE]
> <span data-ttu-id="dfddf-105">2021 januárjától az okkódok a **Személyzetkezelés** munkaterületre kerülnek a **Juttatáskezelés** munkaterület helyett.</span><span class="sxs-lookup"><span data-stu-id="dfddf-105">As of January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="dfddf-106">További információk: [Okkódok manuális áttelepítése a Személyzetkezelés munkaterületre](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span><span class="sxs-lookup"><span data-stu-id="dfddf-106">For more information, see [Manually migrate reason codes to Personnel management](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span></span>

## <a name="create-reason-codes"></a><span data-ttu-id="dfddf-107">Okkódok létrehozása</span><span class="sxs-lookup"><span data-stu-id="dfddf-107">Create reason codes</span></span>

1. <span data-ttu-id="dfddf-108">A **Személyzetkezelés** munkaterületen (vagy a **Juttatáskezelés** munkaterületen, ha az okkódok még nincsenek áttelepítve), válassza a **Hivatkozások** lehetőséget, majd válassza az **Okkódok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dfddf-108">In the **Personnel management** workspace (or **Benefits management** workspace if your reason codes haven't yet migrated), select **Links**, and then select **Reason codes**.</span></span>

2. <span data-ttu-id="dfddf-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dfddf-109">Select **New**.</span></span>

3. <span data-ttu-id="dfddf-110">Adjon meg értékeket a következő mezőkben:</span><span class="sxs-lookup"><span data-stu-id="dfddf-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="dfddf-111">Mező</span><span class="sxs-lookup"><span data-stu-id="dfddf-111">Field</span></span> | <span data-ttu-id="dfddf-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="dfddf-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="dfddf-113">**Okkód**</span><span class="sxs-lookup"><span data-stu-id="dfddf-113">**Reason code**</span></span> | <span data-ttu-id="dfddf-114">Egyedi név, amellyel azonosíthatja, hogy az alkalmazott milyen okból módosítja a juttatási konstrukciós regisztrációját.</span><span class="sxs-lookup"><span data-stu-id="dfddf-114">A unique name to identify the reason an employee would change a benefit plan enrollment.</span></span> |
   | <span data-ttu-id="dfddf-115">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="dfddf-115">**Description**</span></span> | <span data-ttu-id="dfddf-116">Az okkód leírása.</span><span class="sxs-lookup"><span data-stu-id="dfddf-116">A description of the reason code.</span></span> |

4. <span data-ttu-id="dfddf-117">Az **Alkalmazandó forgatókönyvek** pontban állítsa a **Juttatáskezelés** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="dfddf-117">Under **Applicable scenarios**, set **Benefits management** to **Yes**.</span></span> <span data-ttu-id="dfddf-118">(Nem alkalmazandó, ha az okkódokat még nem telepítette át a **Személyzetkezelés** munkaterületre.)</span><span class="sxs-lookup"><span data-stu-id="dfddf-118">(Not applicable if your reason codes haven't yet migrated to the **Personnel management** workspace.)</span></span>

5. <span data-ttu-id="dfddf-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dfddf-119">Select **Save**.</span></span>

## <a name="manually-migrate-reason-codes-to-personnel-management"></a><span data-ttu-id="dfddf-120">Okkódok manuális áttelepítése a Személyzetkezelés munkaterületre</span><span class="sxs-lookup"><span data-stu-id="dfddf-120">Manually migrate reason codes to Personnel management</span></span>

<span data-ttu-id="dfddf-121">2021 januárjától az okkódok a **Személyzetkezelés** munkaterületre kerülnek a **Juttatáskezelés** munkaterület helyett.</span><span class="sxs-lookup"><span data-stu-id="dfddf-121">In January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="dfddf-122">A legtöbb okkódadat automatikusan áttelepítésre kerül a környezetben.</span><span class="sxs-lookup"><span data-stu-id="dfddf-122">Most reason code data will automatically migrate in your environment.</span></span> <span data-ttu-id="dfddf-123">Előfordulhat, hogy néhány okkódadat nem kerül áttelepítésre.</span><span class="sxs-lookup"><span data-stu-id="dfddf-123">Some reason code data might not migrate.</span></span> <span data-ttu-id="dfddf-124">Például az okkódok most már legfeljebb 15 karakterből állhatnak, így a 15 karakternél hosszabb okkódok nem kerülnek automatikusan áttelepítésre.</span><span class="sxs-lookup"><span data-stu-id="dfddf-124">For example, reason codes now have a 15-character maximum, so any reason codes longer than 15 characters won't migrate automatically.</span></span>

<span data-ttu-id="dfddf-125">A **Juttatáskezelés** munkaterület **Hivatkozások** lapján megjelenik egy dokumentum, amely tájékoztatja az áttelepítésről, illetve arról, hogy van-e olyan okkód, amely nem került áttelepítésre.</span><span class="sxs-lookup"><span data-stu-id="dfddf-125">You'll see a banner on the **Links** page of the **Benefits management** workspace informing you about the migration and whether any reason codes didn't migrate.</span></span>

1. <span data-ttu-id="dfddf-126">Az **Okkódok** lehetőségben megtekintheti az áttelepítési állapottal kapcsolatos részleteket.</span><span class="sxs-lookup"><span data-stu-id="dfddf-126">Select **Reason codes** for details about migration status.</span></span>

   <span data-ttu-id="dfddf-127">[![Okkódok](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span><span class="sxs-lookup"><span data-stu-id="dfddf-127">[![Reason codes](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span></span>

2. <span data-ttu-id="dfddf-128">Válasszon ki egy olyan okkódot, amelynél az áttelepítés sikertelen volt.</span><span class="sxs-lookup"><span data-stu-id="dfddf-128">Select a reason code that failed to migrate.</span></span>

   <span data-ttu-id="dfddf-129">[![Okkód áttelepítési állapota](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span><span class="sxs-lookup"><span data-stu-id="dfddf-129">[![Reason code migration status](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span></span>

3. <span data-ttu-id="dfddf-130">Válassza az **Okkód áttelepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dfddf-130">Select **Migrate reason code**.</span></span>

   <span data-ttu-id="dfddf-131">[![Okkód áttelepítése](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span><span class="sxs-lookup"><span data-stu-id="dfddf-131">[![Migrate reason code](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span></span>

4. <span data-ttu-id="dfddf-132">A **Juttatási okkód áttelepítése** ablakban két lehetőség áll rendelkezésre a Személyzetkezelés okkódjának leképezésére:</span><span class="sxs-lookup"><span data-stu-id="dfddf-132">In the **Benefit reason code migration** pane, you have two options for mapping to a Personnel management reason code:</span></span>

   - <span data-ttu-id="dfddf-133">A Személyzetkezelésben létező okkód használatához válasszon egyet a **Meglévő okkód használata** legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="dfddf-133">To use an existing reason code in Personnel management, choose one from the **Use existing reason code** dropdown.</span></span>
     > [!NOTE]
     > <span data-ttu-id="dfddf-134">A Személyzetkezelés eszközben csak akkor használhat meglévő okkódot, ha még nincs rá áttelepítve másik Juttatáskezelési okkód.</span><span class="sxs-lookup"><span data-stu-id="dfddf-134">You can only use an existing reason code in Personnel management if another Benefits management reason code hasn't already migrated to it.</span></span>
   - <span data-ttu-id="dfddf-135">Ha új okkódot kell létrehozni a Személyzetkezelés eszközben, írjon be egy újat az **Új okkód** pontba, majd adjon meg egy leírást az **Új leírás** lehetőségben.</span><span class="sxs-lookup"><span data-stu-id="dfddf-135">To create a new reason code in Personnel management, enter a new one in **New reason code**, and then enter a description in **New description**.</span></span>

   <span data-ttu-id="dfddf-136">[![Leképezés a Személyzetkezelés egy okkódjára](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span><span class="sxs-lookup"><span data-stu-id="dfddf-136">[![Map to a Personnel management reason code](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span></span>

<span data-ttu-id="dfddf-137">Miután megtörtént az okkódok áttelepítése a Személyzetkezelés eszközbe, a Juttatáskezelés funkcióban való használatuk beállítása automatikusan **Igen** lesz.</span><span class="sxs-lookup"><span data-stu-id="dfddf-137">After reason codes migrate to Personnel management, the option for using them in Benefits management is automatically set to **Yes**.</span></span>

<span data-ttu-id="dfddf-138">[![Okkód használata a Juttatáskezelés eszközben](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span><span class="sxs-lookup"><span data-stu-id="dfddf-138">[![Use reason code in Benefits management](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]