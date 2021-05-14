---
title: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja a felülszállítás százalékos értékét
description: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja a felülszállítás százalékos értékét
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c9b5ba8dedb927ee049d7e53e9a666902f563f49
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938486"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a><span data-ttu-id="f7bcd-103">Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja a felülszállítás százalékos értékét</span><span class="sxs-lookup"><span data-stu-id="f7bcd-103">You can't confirm a shipment because the quantity exceeds the overdelivery percentage</span></span>

<span data-ttu-id="f7bcd-104">Hibakód: WAX1687</span><span class="sxs-lookup"><span data-stu-id="f7bcd-104">Error code: WAX1687</span></span>

## <a name="symptoms"></a><span data-ttu-id="f7bcd-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="f7bcd-105">Symptoms</span></span>

<span data-ttu-id="f7bcd-106">Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="f7bcd-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="f7bcd-107">A(z) %1 rakomány szállítása nem igazolható vissza, mert a(z) %2 cikk mennyisége meghaladja a felülszállításhoz meghatározott százalékot.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for overdelivery.</span></span>

<span data-ttu-id="f7bcd-108">Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="f7bcd-109">Ok</span><span class="sxs-lookup"><span data-stu-id="f7bcd-109">Cause</span></span>

<span data-ttu-id="f7bcd-110">A rakomány vagy szállítmány mennyisége csak részben lett kitárolva.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="f7bcd-111">A mennyiség jelenleg olyan százalékértékkel nagyobb a kitárolt mennyiségnél, amely kívül esik a megengedett felülszállítási százaléknál.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-111">The quantity currently exceeds the picked quantity by a percentage that is outside the allowed overdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="f7bcd-112">Felbontás</span><span class="sxs-lookup"><span data-stu-id="f7bcd-112">Resolution</span></span>

<span data-ttu-id="f7bcd-113">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="f7bcd-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="f7bcd-114">A rakománysor mennyiségének beállítása.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-114">Set the load line quantity.</span></span>
- <span data-ttu-id="f7bcd-115">A felülszállítás százalékának beállítása.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-115">Set the overdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="f7bcd-116">A rakománysor mennyiségének beállítása</span><span class="sxs-lookup"><span data-stu-id="f7bcd-116">Set the load line quantity</span></span>

<span data-ttu-id="f7bcd-117">A rakománysor mennyiségének beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="f7bcd-118">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f7bcd-119">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="f7bcd-120">A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja a felülszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-120">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="f7bcd-121">A **Sor részletei** gyorslapon válassza ki az **Rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="f7bcd-122">A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** érték), hogy a szállítmány megerősítése elvégezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-overdelivery-percentage"></a><span data-ttu-id="f7bcd-123">A felülszállítás százalékának beállítása</span><span class="sxs-lookup"><span data-stu-id="f7bcd-123">Set the overdelivery percentage</span></span>

<span data-ttu-id="f7bcd-124">Az alulszállítás százalékértékének beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="f7bcd-125">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f7bcd-126">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="f7bcd-127">A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja a felülszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-127">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="f7bcd-128">A **Sor részletei** gyorslapon válassza ki az **Általános** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="f7bcd-129">A **Felülszállítás** mezőben állítsa nagyobb százalékértékre az értéket, amely a rakománymennyiséggel szemben kitárolt mennyiségnek megfelelő, így a szállítmány megerősítése lehetséges.</span><span class="sxs-lookup"><span data-stu-id="f7bcd-129">In the **Overdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
