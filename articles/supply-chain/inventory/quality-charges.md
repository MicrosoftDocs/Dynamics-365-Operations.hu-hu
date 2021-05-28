---
title: Költségek a szabálytalansági műveletekhez kapcsolódóan
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni a szabálytalanságok műveleteihez használható minőségi költségeket.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 382890232bff47a885840af1eb7e91d27bb46cae
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022300"
---
# <a name="charges-for-nonconformance-operations"></a><span data-ttu-id="64d9d-103">Költségek a szabálytalansági műveletekhez kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="64d9d-103">Charges for nonconformance operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64d9d-104">Ez a témakör azt ismerteti, hogyan lehet létrehozni a szabálytalanságok műveleteihez használható minőségi költségeket.</span><span class="sxs-lookup"><span data-stu-id="64d9d-104">This topic describes how to create quality charges that can be used with operations for a nonconformance.</span></span>

<span data-ttu-id="64d9d-105">A **Minőségi költségek** lapot használhatja azon költségtípusok meghatározásához, amelyeket hozzá lehet adni a szabálytalanságok műveleteihez.</span><span class="sxs-lookup"><span data-stu-id="64d9d-105">You use the **Quality charges** page to define the types of charges that can be added to operations for a nonconformance.</span></span> <span data-ttu-id="64d9d-106">A költségekkel nyomon követheti a nem megfelelő termékekért a vevőnek fizetendő díjakat vagy költségeket, illetve azt, hogy a szállító tartozik-e Önnek a nem megfelelő termékek szállításáért.</span><span class="sxs-lookup"><span data-stu-id="64d9d-106">Charges let you track details about fees or charges that you owe to a customer for nonconforming products, or that a vendor owes to you for nonconforming products that you received.</span></span> <span data-ttu-id="64d9d-107">A költségek a külső szállítók vagy szolgáltatások műveleteihez szükséges költségek nyomon követésére is használhatók.</span><span class="sxs-lookup"><span data-stu-id="64d9d-107">You might also use charges to track costs that are required for external vendors or services to perform an operation.</span></span>

## <a name="examples-of-quality-charges"></a><span data-ttu-id="64d9d-108">Példák a minőségi költségekre</span><span class="sxs-lookup"><span data-stu-id="64d9d-108">Examples of quality charges</span></span>

<span data-ttu-id="64d9d-109">Egy gyártó cégnek dolgozik.</span><span class="sxs-lookup"><span data-stu-id="64d9d-109">You work for a manufacturing company.</span></span> <span data-ttu-id="64d9d-110">A vállalat több szállítóval is szerződésben áll.</span><span class="sxs-lookup"><span data-stu-id="64d9d-110">Your company has contracts with several vendors.</span></span> <span data-ttu-id="64d9d-111">Ezek a szerződések a cikkek időben való szállításának, károkkal és termékminőségének szabványait körvonalazzák.</span><span class="sxs-lookup"><span data-stu-id="64d9d-111">Those contracts outline standards for on-time shipment, damages, and product quality for items.</span></span> <span data-ttu-id="64d9d-112">Hasonlóképpen számos vevővel is szerződésben áll a vállalata – a visszaküldéssel, a károkkal és a termékminőséggel kapcsolatos adatokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="64d9d-112">Likewise, several of your customers have agreements with your company about returns, damages, and product quality.</span></span>

<span data-ttu-id="64d9d-113">Az egyes körülményekhez díjszerkezet van definiálva, és a szerződésben meg van határozva.</span><span class="sxs-lookup"><span data-stu-id="64d9d-113">A fee structure is defined for each circumstance and specified in the contract.</span></span> <span data-ttu-id="64d9d-114">A minőségbiztosítási költségeket a különféle költségtípusok, például a *Károk*, a *Késedelmes szállítás* és a *Minőség* lehetőségben is beállíthatja.</span><span class="sxs-lookup"><span data-stu-id="64d9d-114">You can configure quality charges to outline the various types of charges, such as *Damages*, *Late shipment*, and *Quality*.</span></span> <span data-ttu-id="64d9d-115">Szabálytalanság létrehozásakor egy vagy több műveletet kell hozzáadnia.</span><span class="sxs-lookup"><span data-stu-id="64d9d-115">Then, when you create a nonconformance, you add one or more operations.</span></span> <span data-ttu-id="64d9d-116">Minden egyes művelethez a **Költségek** lehetőséget választva határozhatja meg a díjak adatait.</span><span class="sxs-lookup"><span data-stu-id="64d9d-116">For each operation, you select **Charges** to define the details about the fees.</span></span>

## <a name="create-a-quality-charge"></a><span data-ttu-id="64d9d-117">Minőségi költség létrehozása</span><span class="sxs-lookup"><span data-stu-id="64d9d-117">Create a quality charge</span></span>

1. <span data-ttu-id="64d9d-118">Ugorjon a **Készletkezelés \> Beállítás \> Minőségkezelés \> Minőségi költségek** pontra.</span><span class="sxs-lookup"><span data-stu-id="64d9d-118">Go to **Inventory management \> Setup \> Quality management \> Quality charges**.</span></span>
1. <span data-ttu-id="64d9d-119">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="64d9d-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="64d9d-120">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="64d9d-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="64d9d-121">**Költségkód** – Adja meg a minőségi költség egyedi azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="64d9d-121">**Charges code** – Enter a unique ID or name for the quality charge.</span></span>
    - <span data-ttu-id="64d9d-122">**Leírás** – Adja meg a minőségi költség részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="64d9d-122">**Description** – Enter a detailed description of the quality charge.</span></span>

1. <span data-ttu-id="64d9d-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="64d9d-123">Close the page.</span></span>

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a><span data-ttu-id="64d9d-124">Minőségi költség hozzáadása szabálytalansági művelethez</span><span class="sxs-lookup"><span data-stu-id="64d9d-124">Add a quality charge to an operation for a nonconformance</span></span>

<span data-ttu-id="64d9d-125">A szabálytalanságok műveleteinek hozzáadásával és a költségek rájuk való alkalmazásával kapcsolatban lásd: [Műveletek a szabálytalanságokhoz](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="64d9d-125">For details about how to add operations to a nonconformance and apply charges to them, see [Operations for nonconformances](quality-operations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64d9d-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="64d9d-126">Additional resources</span></span>

- [<span data-ttu-id="64d9d-127">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="64d9d-127">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="64d9d-128">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="64d9d-128">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="64d9d-129">A szabálytalanságok jóváhagyásáért felelős dolgozók</span><span class="sxs-lookup"><span data-stu-id="64d9d-129">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="64d9d-130">A szabálytalanságok karanténzónái</span><span class="sxs-lookup"><span data-stu-id="64d9d-130">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="64d9d-131">A szabálytalanságok diagnosztikai típusai</span><span class="sxs-lookup"><span data-stu-id="64d9d-131">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="64d9d-132">Szabálytalanságok minőségi költségei</span><span class="sxs-lookup"><span data-stu-id="64d9d-132">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="64d9d-133">Műveletek szabálytalanságokhoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="64d9d-133">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="64d9d-134">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="64d9d-134">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
