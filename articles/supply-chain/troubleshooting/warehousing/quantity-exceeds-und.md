---
title: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja az alulszállítás százalékos értékét
description: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja az alulszállítás százalékos értékét
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm,WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 625003731485329b93f5f9454ccece580c889613
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123819"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a><span data-ttu-id="b5e94-103">Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja az alulszállítás százalékos értékét</span><span class="sxs-lookup"><span data-stu-id="b5e94-103">You can't confirm a shipment because the quantity exceeds the underdelivery percentage</span></span>

<span data-ttu-id="b5e94-104">Hibakód: WAX1686</span><span class="sxs-lookup"><span data-stu-id="b5e94-104">Error code: WAX1686</span></span>

## <a name="symptoms"></a><span data-ttu-id="b5e94-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="b5e94-105">Symptoms</span></span>

<span data-ttu-id="b5e94-106">Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="b5e94-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="b5e94-107">A(z) %1 rakomány szállítása nem igazolható vissza, mert a(z) %2 cikk mennyisége meghaladja az alulszállításhoz meghatározott százalékot.</span><span class="sxs-lookup"><span data-stu-id="b5e94-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for underdelivery.</span></span>

<span data-ttu-id="b5e94-108">Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.</span><span class="sxs-lookup"><span data-stu-id="b5e94-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="b5e94-109">Ok</span><span class="sxs-lookup"><span data-stu-id="b5e94-109">Cause</span></span>

<span data-ttu-id="b5e94-110">A rakomány vagy szállítmány mennyisége csak részben lett kitárolva.</span><span class="sxs-lookup"><span data-stu-id="b5e94-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="b5e94-111">A mennyiség jelenleg olyan százalékértékkel kisebb a kitárolt mennyiségnél, amely kívül esik a megengedett alulszállítási százaléknál.</span><span class="sxs-lookup"><span data-stu-id="b5e94-111">The quantity is currently less than the picked quantity by a percentage that is outside the allowed underdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="b5e94-112">Felbontás</span><span class="sxs-lookup"><span data-stu-id="b5e94-112">Resolution</span></span>

<span data-ttu-id="b5e94-113">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="b5e94-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="b5e94-114">A rakománysor mennyiségének beállítása.</span><span class="sxs-lookup"><span data-stu-id="b5e94-114">Set the load line quantity.</span></span>
- <span data-ttu-id="b5e94-115">Az alulszállítás százalékának beállítása.</span><span class="sxs-lookup"><span data-stu-id="b5e94-115">Set the underdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="b5e94-116">A rakománysor mennyiségének beállítása</span><span class="sxs-lookup"><span data-stu-id="b5e94-116">Set the load line quantity</span></span>

<span data-ttu-id="b5e94-117">A rakománysor mennyiségének beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b5e94-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="b5e94-118">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b5e94-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b5e94-119">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="b5e94-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="b5e94-120">A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja az alulszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="b5e94-120">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="b5e94-121">A **Sor részletei** gyorslapon válassza ki az **Rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5e94-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="b5e94-122">A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** érték), hogy a szállítmány megerősítése elvégezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="b5e94-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-underdelivery-percentage"></a><span data-ttu-id="b5e94-123">Az alulszállítás százalékának beállítása</span><span class="sxs-lookup"><span data-stu-id="b5e94-123">Set the underdelivery percentage</span></span>

<span data-ttu-id="b5e94-124">Az alulszállítás százalékértékének beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b5e94-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="b5e94-125">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b5e94-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b5e94-126">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="b5e94-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="b5e94-127">A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja az alulszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="b5e94-127">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="b5e94-128">A **Sor részletei** gyorslapon válassza ki az **Általános** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5e94-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="b5e94-129">Az **Alulszállítás** mezőben állítsa nagyobb százalékértékre az értéket, amely a rakománymennyiséggel szemben kitárolt mennyiségnek megfelelő, így a szállítmány megerősítése lehetséges.</span><span class="sxs-lookup"><span data-stu-id="b5e94-129">In the **Underdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
