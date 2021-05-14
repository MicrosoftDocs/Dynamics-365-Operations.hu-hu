---
title: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
description: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938483"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="ff0b8-103">Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki</span><span class="sxs-lookup"><span data-stu-id="ff0b8-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="ff0b8-104">Hibakód: LoadNotPickedAndMrmedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="ff0b8-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="ff0b8-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="ff0b8-105">Symptoms</span></span>

<span data-ttu-id="ff0b8-106">Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="ff0b8-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="ff0b8-107">A(z) %1 rakományhoz szükséges egyes cikkek még nem lettek kitárolva és a végső szállítási helyre áthelyezve.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="ff0b8-108">Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="ff0b8-109">Ok</span><span class="sxs-lookup"><span data-stu-id="ff0b8-109">Cause</span></span>

<span data-ttu-id="ff0b8-110">A rakomány vagy szállítmány jelenleg nem erősíthető meg, mert a következő feltételek valamelyike fennáll:</span><span class="sxs-lookup"><span data-stu-id="ff0b8-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="ff0b8-111">A kapcsolódó munkát még nem választották ki és nem helyezték át a végső szállítási helyre.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="ff0b8-112">A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>

## <a name="resolution"></a><span data-ttu-id="ff0b8-113">Felbontás</span><span class="sxs-lookup"><span data-stu-id="ff0b8-113">Resolution</span></span>

<span data-ttu-id="ff0b8-114">A rakomány vagy szállítmány kapcsolódó értékesítési és átmozgatási rendelésének ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-114">Check the related sales orders or transfer orders for the load or shipment.</span></span> <span data-ttu-id="ff0b8-115">Győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-115">Make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="ff0b8-116">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-116">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="ff0b8-117">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-117">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="ff0b8-118">A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-118">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="ff0b8-119">Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-119">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="ff0b8-120">A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-120">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="ff0b8-121">Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-121">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="ff0b8-122">Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.</span><span class="sxs-lookup"><span data-stu-id="ff0b8-122">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>
