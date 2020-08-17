---
title: Kimenő szállítmányok jóváhagyása kötegelt feladatokból
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy olyan kötegelt feladatot, amely automatikusan megerősíti a kimenő átmozgatási rendelések szállítását a szállításra kész rakományok számára.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 41dbfb90b7b19c964e725ee0a4c769402414fb17
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/03/2020
ms.locfileid: "3652238"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="798e1-103">Kimenő szállítmányok jóváhagyása kötegelt feladatokból</span><span class="sxs-lookup"><span data-stu-id="798e1-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="798e1-104">Ez a témakör azt mutatja be, hogyan lehet beállítani egy olyan kötegelt feladatot, amely automatikusan megerősíti a kimenő átmozgatási rendelések szállítását a szállításra kész rakományok számára.</span><span class="sxs-lookup"><span data-stu-id="798e1-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="798e1-105">Az itt leírt kötegelt feladat csak átmozgatási rendelések szállítására vonatkozik, az értékesítési rendelésekre nem.</span><span class="sxs-lookup"><span data-stu-id="798e1-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="798e1-106">Kimenő szállítmányok jóváhagyásának engedélyezése a kötegelt feladatok funkcióból</span><span class="sxs-lookup"><span data-stu-id="798e1-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="798e1-107">A funkció használata előtt engedélyeznie kell a saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="798e1-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="798e1-108">A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="798e1-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="798e1-109">A funkció a következőként szerepel:</span><span class="sxs-lookup"><span data-stu-id="798e1-109">The feature is listed as:</span></span>

- <span data-ttu-id="798e1-110">**Modul** - *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="798e1-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="798e1-111">**Funkció neve** - *Kimenő szállítmányok jóváhagyásának engedélyezése a kötegelt feladatok funkcióból*</span><span class="sxs-lookup"><span data-stu-id="798e1-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="798e1-112">Kimenő szállítmányok feldolgozása</span><span class="sxs-lookup"><span data-stu-id="798e1-112">Process outbound shipments</span></span>

<span data-ttu-id="798e1-113">Ha be szeretné állítani, hogy a kimenő szállítmányok jóváhagyását a szállításra kész rakományok számára futtassa az ütemezett kötegelt feladathoz:</span><span class="sxs-lookup"><span data-stu-id="798e1-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="798e1-114">Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Kimenő szállítmányok feldolgozása** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="798e1-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="798e1-115">Megnyílik a **Szállítmány jóváhagyása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="798e1-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="798e1-116">**A szerepeltetni kívánt rekordok** gyorslapján válassza a **szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="798e1-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="798e1-117">Megnyílik a lekérdezéstervező párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="798e1-117">The query editor dialog box opens.</span></span> <span data-ttu-id="798e1-118">A **Tartomány** lapon adjon hozzá egy sort az alábbi értékekkel:</span><span class="sxs-lookup"><span data-stu-id="798e1-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="798e1-119">**Tábla** - *Rakományok*</span><span class="sxs-lookup"><span data-stu-id="798e1-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="798e1-120">**Származtatott tábla** - *Rakományok*</span><span class="sxs-lookup"><span data-stu-id="798e1-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="798e1-121">**Mező** - *Rakomány állapota*</span><span class="sxs-lookup"><span data-stu-id="798e1-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="798e1-122">**Feltételek** - *Betöltött*</span><span class="sxs-lookup"><span data-stu-id="798e1-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="798e1-123">Kattintson az **OK** gombra a **Szállítmány jóváhagyása** párbeszédpanelhez való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="798e1-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="798e1-124">A **Futtatás a háttérben** gyorslapon állítsa a **Kötegelt feldolgozást** **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="798e1-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="798e1-125">A **Futtatás a háttérben** gyorslapon válassz az **Ismétlődés** elemet.</span><span class="sxs-lookup"><span data-stu-id="798e1-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="798e1-126">Megnyílik az **Ismétlődés meghatározása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="798e1-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="798e1-127">Az üzleti tevékenységének megfelelően állítsa be a futási ütemezést.</span><span class="sxs-lookup"><span data-stu-id="798e1-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="798e1-128">Kattintson az **OK** gombra a **Szállítmány jóváhagyása** párbeszédpanelhez való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="798e1-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="798e1-129">Válassza az **OK** gombot a **Szállítmány jóváhagyása** párbeszédpanelen a kötegelt feladat köteg várólistájához adásához.</span><span class="sxs-lookup"><span data-stu-id="798e1-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="798e1-130">További tudnivalókhoz lásd a [Kötegelt feldolgozás áttekintése](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) elemet.</span><span class="sxs-lookup"><span data-stu-id="798e1-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>
