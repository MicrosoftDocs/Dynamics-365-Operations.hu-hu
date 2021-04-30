---
title: Kötelezettség-, eszköz- és költségtranzakciók megtekintése
description: Ez a témakör a lízingbe adott eszköz tranzakcióinak megtekintését ismerteti. Ezek a tranzakciók magukban foglalják a lízingkötelezettséggel kapcsolatos tranzakciókat és a feladott végrehajtási költségtranzakciókat.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 55b8019db6abdb3bd5ecdb6eadc4f7443f2bf071
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881638"
---
# <a name="view-liability-asset-and-expense-transactions"></a><span data-ttu-id="421bd-104">Kötelezettség-, eszköz- és költségtranzakciók megtekintése</span><span class="sxs-lookup"><span data-stu-id="421bd-104">View liability, asset, and expense transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="421bd-105">Ez a témakör a lízingbe adott eszköz tranzakcióinak megtekintését ismerteti.</span><span class="sxs-lookup"><span data-stu-id="421bd-105">This topic explains how to view transactions for a leased asset.</span></span> <span data-ttu-id="421bd-106">Ezek a tranzakciók magukban foglalják a lízingkötelezettséggel kapcsolatos tranzakciókat és a feladott végrehajtási költségtranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="421bd-106">These transactions include lease liability transactions and executory expense transactions that have been posted.</span></span> <span data-ttu-id="421bd-107">A kötelezettség és a használatijog-eszköz (ROU) könyv szerinti értékeit több jelentésben is felhasználják.</span><span class="sxs-lookup"><span data-stu-id="421bd-107">The carrying values of the liability and right-of-use (ROU) asset are used on several reports.</span></span> <span data-ttu-id="421bd-108">A korrekciós értékek kiszámítására is szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="421bd-108">They are also used to calculate adjustment values.</span></span>

## <a name="liability-transactions"></a><span data-ttu-id="421bd-109">Kötelezettség tranzakciói</span><span class="sxs-lookup"><span data-stu-id="421bd-109">Liability transactions</span></span>

<span data-ttu-id="421bd-110">A lízingkötelezettség-tranzakciók megtekintéséhez válasszon ki egy lízinget a **Lízing összegzése** lapon, majd válassza a **Könyvek** lehetőséget a lízingrekordhoz csatolt könyvek megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="421bd-110">To view the lease liability transactions, select a lease on the **Lease summary** page, and then select **Books** to open the books that are attached to the lease record.</span></span> <span data-ttu-id="421bd-111">A kezdeti megjelenítés, a számla vagy a kamatnapló feladása után válassza a **Kötelezettségtranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="421bd-111">After an initial recognition, an invoice, or an interest journal has been posted, select **Liability transactions**.</span></span>

<span data-ttu-id="421bd-112">A **Kötelezettségtranzakciók** lap azokat a tranzakciókat jeleníti meg, amelyek növelik vagy csökkentik a lízingkötelezettséget.</span><span class="sxs-lookup"><span data-stu-id="421bd-112">The **Liability transactions** page shows the transactions that either increase or decrease the lease liability.</span></span> <span data-ttu-id="421bd-113">Az ezen az oldalon szereplő negatív összegek a standard alkalmazásban szereplő jóváírási tranzakciókat jelölik.</span><span class="sxs-lookup"><span data-stu-id="421bd-113">Negative amounts on this page represent credit transactions in the standard application.</span></span> <span data-ttu-id="421bd-114">A kamatelhatárolások negatív értékként jelennek meg, és növelik a teljes lízingkötelezettséget.</span><span class="sxs-lookup"><span data-stu-id="421bd-114">Any interest accruals are shown as negative values and increase the total lease liability.</span></span> <span data-ttu-id="421bd-115">A lízingkiigazítások a lízingkönyv jellegétől és hatásától függően pozitív vagy negatív értékként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="421bd-115">Any lease adjustments are shown as positive or negative values, depending on the nature and impact of the lease book.</span></span> <span data-ttu-id="421bd-116">A kiválasztott lízing lízingkötelezettség aktuális nettó teljes egyenlege az oldal bal alsó sarkában látható.</span><span class="sxs-lookup"><span data-stu-id="421bd-116">The current net total balance of the lease liability for the selected lease is shown at the bottom left of the page.</span></span>

## <a name="asset-transactions"></a><span data-ttu-id="421bd-117">Eszköztranzakciók</span><span class="sxs-lookup"><span data-stu-id="421bd-117">Asset transactions</span></span>

<span data-ttu-id="421bd-118">A lízingeszköz-tranzakciók megtekintéséhez válasszon ki egy lízinget a **Lízing összegzése** lapon, majd válassza a **Könyvek** lehetőséget a lízingrekordhoz csatolt lízingkönyvek megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="421bd-118">To view the lease asset transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="421bd-119">Majd válassza a **Eszköztranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="421bd-119">Then select **Asset transactions**.</span></span>

<span data-ttu-id="421bd-120">Az **Eszköztranzakció** lap azokat a tranzakciókat jeleníti meg, amelyek növelik vagy csökkentik a lízingeszközt és a halmozott értékcsökkenési számlákat.</span><span class="sxs-lookup"><span data-stu-id="421bd-120">The **Asset transaction** page shows the transactions that either increase or decrease the lease asset and accumulated depreciation accounts.</span></span> <span data-ttu-id="421bd-121">A tartozási értékek pozitív értékként, a jóváírások pedig negatív értékként jelennek meg, mint a **Kötelezettségtranzakciók** lapon.</span><span class="sxs-lookup"><span data-stu-id="421bd-121">Debits are shown as positive values, and credits are shown as negative values, as on the **Liability transactions** page.</span></span> <span data-ttu-id="421bd-122">A könyvelt kezdeti megjelenítés és a következő halmozott értékcsökkenés az oldal bal alsó sarkában jelenik meg eszközegyenlegként.</span><span class="sxs-lookup"><span data-stu-id="421bd-122">The posted initial recognition and the next of accumulated depreciation are shown at the bottom left of the page as the asset balance.</span></span> 

## <a name="expenses-transactions"></a><span data-ttu-id="421bd-123">Költségtranzakciók</span><span class="sxs-lookup"><span data-stu-id="421bd-123">Expenses transactions</span></span>

<span data-ttu-id="421bd-124">A lízingköltség-tranzakciók megtekintéséhez válasszon ki egy lízinget a **Lízing összegzése** lapon, majd válassza a **Könyvek** lehetőséget a lízingrekordhoz csatolt lízingkönyvek megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="421bd-124">To view the lease expense transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="421bd-125">Majd válassza ki a **Költségtranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="421bd-125">Then select **Expense transactions**.</span></span>

<span data-ttu-id="421bd-126">A **Költségtranzakciók** lap a lízinggel szemben feladott összes költséget megjeleníti, például a kamatköltségeket, az értékcsökkenési költségeket és a végrehajtási költségeket.</span><span class="sxs-lookup"><span data-stu-id="421bd-126">The **Expense transactions** page shows all the expenses that have been posted against the lease, such as interest expenses, depreciation expenses, and any executory costs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
