---
title: A szabálytalanságok problématípusai
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó problématípusokat.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 742edec8570610efe41a2c627efd1df586e0733e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022156"
---
# <a name="problem-types-for-nonconformances"></a><span data-ttu-id="71760-103">A szabálytalanságok problématípusai</span><span class="sxs-lookup"><span data-stu-id="71760-103">Problem types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71760-104">Ez a témakör azt ismerteti, hogyan lehet létrehozni és használni a szabálytalanságokhoz kapcsolódó problématípusokat.</span><span class="sxs-lookup"><span data-stu-id="71760-104">This topic describes how to create and use problem types for nonconformances.</span></span>

<span data-ttu-id="71760-105">A **Problématípusok** oldalon határozhatja meg a különböző szabálytalanságtípusok esetében esetlegesen felmerülő minőségproblémák osztályozását.</span><span class="sxs-lookup"><span data-stu-id="71760-105">You use the **Problem types** page to define a classification of the quality problems that might occur for the various nonconformance types.</span></span> <span data-ttu-id="71760-106">Minden létrehozott problématípushoz meg kell adnia, hogy a problématípus milyen típusú szabálytalanságokkal használható.</span><span class="sxs-lookup"><span data-stu-id="71760-106">For each problem type that you create, you must specify the types of nonconformances that the problem type can be used with.</span></span> <span data-ttu-id="71760-107">A következő szabálytalanságtípusokat állíthatja be:</span><span class="sxs-lookup"><span data-stu-id="71760-107">You can set up the following nonconformance types:</span></span>

- <span data-ttu-id="71760-108">**Belső** – Az ilyen típusú szabálytalanságok az aktuális készlettel (például minőségi rendelések vagy karanténrendelések) kapcsolatosak.</span><span class="sxs-lookup"><span data-stu-id="71760-108">**Internal** – Nonconformances of this type are related to on-hand inventory (for example, quality orders or quarantine orders).</span></span>
- <span data-ttu-id="71760-109">**Vevő** – az ilyen típusú szabálytalanságok értékesítési rendelésekhez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="71760-109">**Customer** – Nonconformances of this type are related to sales orders.</span></span>
- <span data-ttu-id="71760-110">**Szállító** – az ilyen típusú szabálytalanságok beszerzési rendelésekhez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="71760-110">**Vendor** – Nonconformances of this type are related to purchase orders.</span></span>
- <span data-ttu-id="71760-111">**Szervizkérelem** – az ilyen típusú szabálytalanságok a szervizrendelésekhez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="71760-111">**Service request** – Nonconformances of this type are related to service orders.</span></span>
- <span data-ttu-id="71760-112">**Termelés** – Az ilyen típusú szabálytalanságok a kötegelt rendelésekhez vagy termelési rendelésekhez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="71760-112">**Production** – Nonconformances of this type are related to batch orders or production orders.</span></span>
- <span data-ttu-id="71760-113">**Társtermék gyártása** – Az ilyen típusú szabálytalanságok a kötegelt rendelésekhez vagy társtermékekhez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="71760-113">**Co-product production** – Nonconformances of this type are related to batch orders for co-products.</span></span>

<span data-ttu-id="71760-114">Új problématípus létrehozásakor a Műveleti panelen válassza ki a **Szabálytalanságtípusok** lehetőséget a problématípushoz engedélyezett egy vagy több szabálytalanságtípus listájának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="71760-114">When you create a new problem type, select **Non conformance types** on the Action Pane to create a list of one or more nonconformance types that are authorized for the problem type.</span></span> <span data-ttu-id="71760-115">Például egy hibás kódhoz kapcsolódó problématípus minden szabálytalanságtípusra vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="71760-115">For example, a problem type that is related to a defect code might apply to all nonconformance types.</span></span> <span data-ttu-id="71760-116">A vevői panaszokkal kapcsolatos problématípus azonban csak a **Vevő** és **Szervizkérelem** szabálytalanságtípusokra vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="71760-116">However, a problem type that is related to customer complaints might apply only to the **Customer** and **Service request** nonconformance types.</span></span>

## <a name="examples-of-problem-types"></a><span data-ttu-id="71760-117">Néhány példa a problématípusokra</span><span class="sxs-lookup"><span data-stu-id="71760-117">Examples of problem types</span></span>

<span data-ttu-id="71760-118">Az alábbiakban néhány példa látható az olyan problématípusokra, amelyek a különböző szabálytalanságtípusokhoz használhatók:</span><span class="sxs-lookup"><span data-stu-id="71760-118">Here are some examples of scenarios for problem types that can be used with the different nonconformance types:</span></span>

- <span data-ttu-id="71760-119">**Vevő**: Egy vevő panaszt nyújtott be, a vevő visszaküldött egy terméket, vagy nem teljesültek a minőségi specifikációk.</span><span class="sxs-lookup"><span data-stu-id="71760-119">**Customer:** A customer filed a complaint, a customer made a return, or quality specifications weren't met.</span></span>
- <span data-ttu-id="71760-120">**Szállító:** A termék sérült, vagy nem teljesültek a minőségi specifikációk, vagy nem megfelelő termék érkezett.</span><span class="sxs-lookup"><span data-stu-id="71760-120">**Vendor:** The product was damaged, quality specifications weren't met, or the wrong product was received.</span></span>
- <span data-ttu-id="71760-121">**Szervizkérelem**: Nem teljesültek a minőségi specifikációk, egy vevő reklamációt nyújtott be, vagy a gép karbantartást igényel.</span><span class="sxs-lookup"><span data-stu-id="71760-121">**Service request:** Quality specifications weren't met, a customer filed a complaint, or machine maintenance is required.</span></span>
- <span data-ttu-id="71760-122">**Termelés:** Nem teljesültek a minőségi specifikációk, a gépkarbantartásra van szükség, vagy a termék megsérült.</span><span class="sxs-lookup"><span data-stu-id="71760-122">**Production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>
- <span data-ttu-id="71760-123">**Társtermék gyártása:** Nem teljesültek a minőségi specifikációk, a gépkarbantartásra van szükség, vagy a termék megsérült.</span><span class="sxs-lookup"><span data-stu-id="71760-123">**Co-product production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a><span data-ttu-id="71760-124">Problématípus létrehozása és hozzárendelése szabálytalanságtípusokhoz</span><span class="sxs-lookup"><span data-stu-id="71760-124">Create a problem type and assign it to nonconformance types</span></span>

1. <span data-ttu-id="71760-125">Ugorjon a **Készletgazdálkodás \> Beállítás \> Minőségkezelés \> Problématípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="71760-125">Go to **Inventory management \> Setup \> Quality management \> Problem types**.</span></span>
1. <span data-ttu-id="71760-126">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="71760-126">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="71760-127">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="71760-127">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="71760-128">**Problématípus** – A problématípus egyedi azonosítójának vagy nevének megadása.</span><span class="sxs-lookup"><span data-stu-id="71760-128">**Problem type** – Enter a unique ID or name for the problem type.</span></span>
    - <span data-ttu-id="71760-129">**Leírás** – Adja meg a problématípus részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="71760-129">**Description** – Enter a detailed description of the problem type.</span></span>

1. <span data-ttu-id="71760-130">Amíg az új sor még ki van választva, válassza ki a **Szabálytalanságtípusokat** a műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="71760-130">While the new row is still selected, select **Non conformance types** on the Action Pane.</span></span>
1. <span data-ttu-id="71760-131">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="71760-131">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="71760-132">Ezután az új sorhoz állítsa a **Szabálytalanságtípus** mezőt a problématípus számára engedélyezni kívánt szabálytalanságtípusra.</span><span class="sxs-lookup"><span data-stu-id="71760-132">Then, for the new row, set the **Non conformance type** field to the nonconformance type that you want to allow for the problem type.</span></span>
1. <span data-ttu-id="71760-133">Ismételje meg az előző lépést minden további olyan szabálytalanságtípussal, amelyhez engedélyezni szeretné a problématípust.</span><span class="sxs-lookup"><span data-stu-id="71760-133">Repeat the previous step for each additional nonconformance type that you want to authorize for the problem type.</span></span>
1. <span data-ttu-id="71760-134">Zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="71760-134">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71760-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="71760-135">Additional resources</span></span>

- [<span data-ttu-id="71760-136">Minőségkezelés áttekintése</span><span class="sxs-lookup"><span data-stu-id="71760-136">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="71760-137">A minőség- és a szabálytalanságkezelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="71760-137">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="71760-138">A szabálytalanságok jóváhagyásáért felelős dolgozók</span><span class="sxs-lookup"><span data-stu-id="71760-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="71760-139">A szabálytalanságok karanténzónái</span><span class="sxs-lookup"><span data-stu-id="71760-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="71760-140">A szabálytalanságok diagnosztikai típusai</span><span class="sxs-lookup"><span data-stu-id="71760-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="71760-141">Szabálytalanságok minőségi költségei</span><span class="sxs-lookup"><span data-stu-id="71760-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="71760-142">Műveletek szabálytalanságokhoz kapcsolódóan</span><span class="sxs-lookup"><span data-stu-id="71760-142">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="71760-143">Raktári folyamatok minőségkezelése</span><span class="sxs-lookup"><span data-stu-id="71760-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
