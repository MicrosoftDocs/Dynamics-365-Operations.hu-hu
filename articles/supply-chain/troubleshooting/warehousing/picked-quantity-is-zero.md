---
title: Nem erősítheti meg a szállítmányt, mert nulla a mennyisége
description: Nem erősítheti meg a szállítmányt, mert nulla a mennyisége
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938482"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a><span data-ttu-id="0e5f0-103">Nem erősítheti meg a szállítmányt, mert nulla a mennyisége</span><span class="sxs-lookup"><span data-stu-id="0e5f0-103">You can't confirm a shipment because there is zero quantity</span></span>

<span data-ttu-id="0e5f0-104">Hibakód: LoadLineWarningUpdatedToZero</span><span class="sxs-lookup"><span data-stu-id="0e5f0-104">Error code: LoadLineWarningUpdatedToZero</span></span>

## <a name="symptoms"></a><span data-ttu-id="0e5f0-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="0e5f0-105">Symptoms</span></span>

<span data-ttu-id="0e5f0-106">Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="0e5f0-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="0e5f0-107">A(z) %1 cikkhez és %2 szállítmányhoz tartozó rakománysor frissült nulla mennyiségre az alulszállítási beállítás miatt, amely nem engedélyezi az adott cikk bármilyen mennyiségének szállítását.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-107">Load line for item %1 and shipment %2 has been updated to have zero quantity due to underdelivery setup allowing not to ship any quantities for this item.</span></span>

<span data-ttu-id="0e5f0-108">Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="0e5f0-109">Ok</span><span class="sxs-lookup"><span data-stu-id="0e5f0-109">Cause</span></span>

<span data-ttu-id="0e5f0-110">A rendszer kiértékeli, hogy a kitárolt mennyiség a várt korlátokon belül van-e, a kitárolt mennyiség, a rakománysor mennyisége és az alulszállítás százalékos aránya alapján.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-110">The system evaluates whether the picked quantity is within the expected limits, based on the picked quantity, load line quantity, and underdelivery percentage.</span></span> <span data-ttu-id="0e5f0-111">Ha a rendszer úgy találja, hogy a rakománysoron kitárolt mennyiség 0 (nulla), akkor nem lehet megerősíteni a szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-111">If the system finds that the picked quantity on the load line is 0 (zero), you can't confirm the shipment.</span></span> <span data-ttu-id="0e5f0-112">Ez a probléma például akkor fordulhat elő, ha a munkát visszavonták, és a rakománysor alulszállítási százaléka 100 százalék.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-112">For example, this issue might occur if work has been canceled, and the underdelivery percentage on the load line is 100 percent.</span></span>

## <a name="resolution"></a><span data-ttu-id="0e5f0-113">Felbontás</span><span class="sxs-lookup"><span data-stu-id="0e5f0-113">Resolution</span></span>

<span data-ttu-id="0e5f0-114">Ellenőrizze a rakománysorokat, hogy az alulszállítás százalékos aránya és mennyiségei összhangban vannak-e a kitárolt munkával.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-114">Check your load lines to make sure that the underdelivery percentage and quantities are aligned with the picked work.</span></span>

1. <span data-ttu-id="0e5f0-115">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0e5f0-116">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="0e5f0-117">A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja az alulszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-117">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="0e5f0-118">Szükség szerint módosítsa az **Alulszállítás** vagy a **Mennyiség mező** értékét.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-118">Adjust the value of the **Underdelivery** field or the **Quantity** field as required.</span></span>

> [!TIP]
> <span data-ttu-id="0e5f0-119">Ha a probléma továbbra sincs megoldva, akkor lehet, hogy a kapcsolódó értékesítési vagy átmozgatási rendeléseken további kitárolási munkát kell végrehajtania, amíg a rendelkezésre álló mennyiség nem igazodik a rakományhoz vagy szállítmányhoz.</span><span class="sxs-lookup"><span data-stu-id="0e5f0-119">If the issue still isn't fixed, you might have to complete more picking work for the related sales orders or transfer orders until the available quantity is aligned with the load or shipment.</span></span>
