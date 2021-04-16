---
title: Eszközlízingelési konvenciók
description: Ez a témakör a lízingbe adott eszközökre vonatkozó konvenciókat írja le.
author: moaamer
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e6450438a6e8c594590df3cc4502895913f50d01
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842394"
---
# <a name="asset-leasing-conventions"></a><span data-ttu-id="d7eee-103">Eszközlízingelési konvenciók</span><span class="sxs-lookup"><span data-stu-id="d7eee-103">Asset leasing conventions</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d7eee-104">Ez a témakör a lízingbe adott eszközökre vonatkozó konvenciókat írja le.</span><span class="sxs-lookup"><span data-stu-id="d7eee-104">This topic describes conventions for leased assets.</span></span> <span data-ttu-id="d7eee-105">A lízingelési konvenciók segítségével lehet meghatározni egy lízingkönyv kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="d7eee-105">Leasing conventions are used to determine the commencement date of a lease book.</span></span> <span data-ttu-id="d7eee-106">Ha a lízingmegállapodás értéke **Nincs**, a kezdő dátum megegyezik a lízing kezdő dátumának dátumával (amely a **Lízing kezdő dátuma** mező értéke).</span><span class="sxs-lookup"><span data-stu-id="d7eee-106">If the leasing convention is set to **None**, the commencement date is the same as the start date for the lease (that is, the value of the **Lease start date** field).</span></span> <span data-ttu-id="d7eee-107">Ha a lízingmegállapodás beállítása **Teljes hónap**, a kezdési dátum annak a hónapnak az első napja, amelybe a lízing kezdő dátuma esik.</span><span class="sxs-lookup"><span data-stu-id="d7eee-107">If the leasing convention is set to **Full month**, the commencement date is the first day of the month that the lease's start date falls in.</span></span>

<span data-ttu-id="d7eee-108">A kezdő dátum határozza meg a kötelezettség amortizációja és az eszköz értékcsökkenése ütemezésének időszakának kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="d7eee-108">The commencement date determines the start date of the period for the liability amortization and asset depreciation schedules.</span></span> <span data-ttu-id="d7eee-109">A kamatráfordítási és értékcsökkenési kiadások feladása a megfelelő ütemezések időszakának záró dátumával történik.</span><span class="sxs-lookup"><span data-stu-id="d7eee-109">Interest expenses and depreciation expenses are posted on the period end date of the corresponding schedules.</span></span> <span data-ttu-id="d7eee-110">A kezdeti megjelenítés és a naplóbejegyzés kiigazításának feladása a kezdő dátum napján kezdődik.</span><span class="sxs-lookup"><span data-stu-id="d7eee-110">The initial recognition and adjustment journal entry are posted on the commencement date.</span></span>

> [!NOTE]
> <span data-ttu-id="d7eee-111">A lízingelési konvenciókkal kapcsolatos funkciót be kell kapcsolni a Funkciókezelés segítségével.</span><span class="sxs-lookup"><span data-stu-id="d7eee-111">The feature for leasing conventions must be turned on through Feature Management.</span></span> <span data-ttu-id="d7eee-112">A **Funkciókezelés** munkaterületen keresse meg és válassza ki az **Eszközkezelési lízingelési konvenciók** funkciót, majd válassza ki az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7eee-112">In the **Feature management** workspace, find and select the feature that is named **Leasing convention for asset leasing** feature, and then select **Enable now**.</span></span>

<span data-ttu-id="d7eee-113">A lízingelési konvenciókat a lízingeszköz-könyv beállításaihoz rendeli hozzá a program.</span><span class="sxs-lookup"><span data-stu-id="d7eee-113">Leasing conventions are assigned to the setup for a lease asset book.</span></span>

<span data-ttu-id="d7eee-114">A következő lépéseket követve tekintse meg vagy rendelje hozzá a lízingelési konvenciót.</span><span class="sxs-lookup"><span data-stu-id="d7eee-114">To view or assign the leasing convention, follow these steps.</span></span>

1. <span data-ttu-id="d7eee-115">Nyissa meg az **Eszközlízing \> Beállítás \> Lízingkönyvek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7eee-115">Go to **Asset leasing \> Setup \> Lease books**.</span></span>
2. <span data-ttu-id="d7eee-116">A **Lízingelési konvenció** mezőben válassza a következő értékek egyikét:</span><span class="sxs-lookup"><span data-stu-id="d7eee-116">In the **Leasing convention** field, select one of the following values.</span></span>

    | <span data-ttu-id="d7eee-117">Lízingmegállapodás</span><span class="sxs-lookup"><span data-stu-id="d7eee-117">Leasing convention</span></span> | <span data-ttu-id="d7eee-118">Leírás</span><span class="sxs-lookup"><span data-stu-id="d7eee-118">Description</span></span> |
    |--------------------|-------------|
    | <span data-ttu-id="d7eee-119">None</span><span class="sxs-lookup"><span data-stu-id="d7eee-119">None</span></span>               | <span data-ttu-id="d7eee-120">A kötelezettség amortizációjának és az eszköz értékcsökkenésének ütemezése a lízing kezdő dátumával kezdődik, mivel a kezdő dátum megegyezik a lízing kezdő dátumával.</span><span class="sxs-lookup"><span data-stu-id="d7eee-120">The liability amortization and asset depreciation schedules start on the lease's start date, because the commencement date equals the lease's start date.</span></span> <span data-ttu-id="d7eee-121">A záró dátum egy hónappal később van.</span><span class="sxs-lookup"><span data-stu-id="d7eee-121">The end date is one month later.</span></span> <span data-ttu-id="d7eee-122">Ez a lízingelési konvenció nem garantálja a kamat feladását minden hónap utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="d7eee-122">This leasing convention doesn't guarantee that the interest will be posted on the last day of each month.</span></span> |
    | <span data-ttu-id="d7eee-123">Teljes hónap</span><span class="sxs-lookup"><span data-stu-id="d7eee-123">Full month</span></span>         | <span data-ttu-id="d7eee-124">Olyan lízingek esetén, amelyek kezdő dátuma a hónap bármely napján esedékes, a kötelezettség amortizációjának és az eszköz értékcsökkenésének ütemezései az adott hónap első napján kezdik el a kiadásokat elhatárolni.</span><span class="sxs-lookup"><span data-stu-id="d7eee-124">For leases that have a start date that occurs at any time during the month, the liability amortization and asset depreciation schedules start to accrue expenses on the first day of that month.</span></span> <span data-ttu-id="d7eee-125">Ez a lízingelési konvenció gondoskodik arról, hogy a kamatot minden hónap utolsó napján elhatárolják az egész hónapra.</span><span class="sxs-lookup"><span data-stu-id="d7eee-125">This leasing convention ensures that interest is accrued on the last day of each month for the whole month.</span></span> |

3. <span data-ttu-id="d7eee-126">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7eee-126">Select **Save**.</span></span>

<span data-ttu-id="d7eee-127">Lízing létrehozásakor minden egyes könyv kezdő dátumát a program automatikusan beírja a lízinghez megadott kezdő dátum és a könyvhöz megadott lízingelési konvenció alapján.</span><span class="sxs-lookup"><span data-stu-id="d7eee-127">When a lease is created, the commencement date of each book is automatically entered based on the start date that is entered for the lease and the leasing convention that is specified for the book.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]