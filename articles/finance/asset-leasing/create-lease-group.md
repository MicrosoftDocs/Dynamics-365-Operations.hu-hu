---
title: Lízingcsoport létrehozása
description: Ez a témakör ismerteti a lízingcsoport beállítását. Új lízingcsoportok létrehozásához lízingcsoportokra van szükség.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5d5efb02c95d9368fbc178cfd9bcd7ce088d1c66
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816052"
---
# <a name="create-a-lease-group"></a><span data-ttu-id="1d627-104">Lízingcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d627-104">Create a lease group</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d627-105">Ez a témakör ismerteti a lízingcsoport beállítását.</span><span class="sxs-lookup"><span data-stu-id="1d627-105">This topic explains how to set up lease groups.</span></span> <span data-ttu-id="1d627-106">Új lízingcsoportok létrehozásához lízingcsoportokra van szükség.</span><span class="sxs-lookup"><span data-stu-id="1d627-106">Lease groups are required to create new leases.</span></span> <span data-ttu-id="1d627-107">A lízingkönyvek az egyes lízingcsoportokhoz vannak társítva.</span><span class="sxs-lookup"><span data-stu-id="1d627-107">Lease books are associated with each lease group.</span></span> <span data-ttu-id="1d627-108">A lízingkönyvek határozzák meg az egyes lízingek alapértelmezett könyveit.</span><span class="sxs-lookup"><span data-stu-id="1d627-108">Lease books determine the default books that must be created for each lease.</span></span> <span data-ttu-id="1d627-109">A **Lízing feladás paraméterek** lapon adott számlákat rendelhet egy lízingcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="1d627-109">You can assign specific accounts to a lease group on the **Lease posting parameters** page.</span></span>

## <a name="create-a-lease-book-and-add-a-lease-group"></a><span data-ttu-id="1d627-110">Lízingkönyv létrehozása és lízingcsoport hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1d627-110">Create a lease book and add a lease group</span></span>

1. <span data-ttu-id="1d627-111">Nyissa meg az **Eszközlízing \> Beállítás \> Lízingcsoportok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d627-111">Go to **Asset leasing \> Setup \> Lease groups**.</span></span>
2. <span data-ttu-id="1d627-112">Jelölje be a Műveleti ablaktáblán az **Új** lehetőséget a lízingcsoport létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1d627-112">On the Action Pane, select **New** to add a lease group.</span></span> <span data-ttu-id="1d627-113">A program sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="1d627-113">A line is added to the grid.</span></span>
3. <span data-ttu-id="1d627-114">Az új sorban a **Lízingcsoport** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d627-114">On the new line, in the **Lease group** field, enter a value.</span></span>
4. <span data-ttu-id="1d627-115">A **Leírás** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1d627-115">In the **Description** field, enter a value.</span></span>

<span data-ttu-id="1d627-116">Az imént megadott adatok hozzáadódnak a **Lízingcsoport** mezőhöz a **Lízing hozzáadása** lapon.</span><span class="sxs-lookup"><span data-stu-id="1d627-116">The information that you just entered is added to the **Lease group** field on the **Add lease** page.</span></span>

## <a name="associate-a-book-with-a-lease-group"></a><span data-ttu-id="1d627-117">Könyv társítása lízingcsoporthoz</span><span class="sxs-lookup"><span data-stu-id="1d627-117">Associate a book with a lease group</span></span>

<span data-ttu-id="1d627-118">Miután létrehozta a lízingcsoportokat, minden csoporthoz könyveket rendelhet.</span><span class="sxs-lookup"><span data-stu-id="1d627-118">After you create lease groups, you can assign books to each group.</span></span> <span data-ttu-id="1d627-119">Amikor létrehoz egy lízinget, és hozzárendeli egy lízingcsoporthoz, a rendszer minden olyan könyvhöz létrehoz ütemezési készletet, amely az adott lízingsoporthoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="1d627-119">When you create a lease and assign it to a lease group, the system creates a set of schedules for each book that is associated with that lease group.</span></span>

> [!NOTE]
> <span data-ttu-id="1d627-120">A könyveket be kell állítani, mielőtt egy lízingcsoporthoz rendelhetők lennének.</span><span class="sxs-lookup"><span data-stu-id="1d627-120">Books must be set up before they can be assigned to a lease group.</span></span>

1. <span data-ttu-id="1d627-121">Nyissa meg az **Eszközlízing \> Beállítás \> Lízingcsoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d627-121">Go to **Asset leasing \> Setup \> Lease group**.</span></span>
2. <span data-ttu-id="1d627-122">Jelöljön ki egy lízingcsoportot, majd válassza a **Könyvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1d627-122">Select a lease group, and then select **Books**.</span></span>
3. <span data-ttu-id="1d627-123">Válassza az **Új** lehetőséget, majd a **Könyv típusa** mezőben válassza ki a lízingcsoporthoz hozzárendelni kívánt könyvet.</span><span class="sxs-lookup"><span data-stu-id="1d627-123">Select **New**, and then, in the **Book type** field, select the book to assign to the lease group.</span></span> <span data-ttu-id="1d627-124">Több könyvet is hozzárendelhet egy lízingcsoporthoz, ha a lízinget különböző módon kell elszámolni.</span><span class="sxs-lookup"><span data-stu-id="1d627-124">You can assign multiple books to a lease group if a lease must be accounted for in different ways.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]