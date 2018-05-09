---
title: "A tároló tömegének és térfogatának feltüntetése a rakományon"
description: "Ez a témakör a tároló tömegének és térfogatának feltüntetése a rakományon funkció beállítását és alkalmazását írja le."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5b0d8c8a3985d1f49a493615b3c69a9dbe65635f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="include-container-weight-and-volume-on-load"></a><span data-ttu-id="5a325-103">A tároló tömegének és térfogatának feltüntetése a rakományon</span><span class="sxs-lookup"><span data-stu-id="5a325-103">Include container weight and volume on load</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a325-104">A tároló tömegének és térfogatának feltüntetése a rakományon funkció világosan jelzi a rakományba bekerülő tárolók összsúlyát és térfogatát.</span><span class="sxs-lookup"><span data-stu-id="5a325-104">The functionality for including the container weight and volume on a load gives a clear representation of the total weight and volume of containers and items that are going on a load.</span></span>

<span data-ttu-id="5a325-105">A rakomány egyetlen szállítmányt vagy több szállítmányt tartalmaz, és ezek a szállítmányok egy vagy több értékesítési rendeléshez tartozó egyedi cikkeket tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="5a325-105">A load contains a single shipment or multiple shipments, and these shipments contain distinct items that belong to a single sales order or multiple sales orders.</span></span> <span data-ttu-id="5a325-106">A cikkek tárolása tárolón belül történik, a tárolókat rakományba töltjük be.</span><span class="sxs-lookup"><span data-stu-id="5a325-106">The items are stored inside a container, and containers are loaded on a load.</span></span> <span data-ttu-id="5a325-107">A rakomány tárolón kívüli cikkeket is tartalmazhat.</span><span class="sxs-lookup"><span data-stu-id="5a325-107">Items that are outside a container can also be part of a load.</span></span> <span data-ttu-id="5a325-108">Ezek a feltételek alapján a rendszer kiszámítja a rakomány súlyát és térfogatát, figyelembe véve a tárolók és a cikkek mennyiségét és súlyát egyaránt.</span><span class="sxs-lookup"><span data-stu-id="5a325-108">Based on these conditions, the system calculates values for the weight and volume on the load by considering the weight and volume of both containers and items.</span></span>

<span data-ttu-id="5a325-109">Ha a számított értékek nem pontosak, módosíthatja őket – írja be a rakomány súlyának és térfogatának tényleges értékét.</span><span class="sxs-lookup"><span data-stu-id="5a325-109">If the calculated values aren’t precise, you can adjust them by entering the actual values for the weight and volume on the load.</span></span> <span data-ttu-id="5a325-110">A súly és térfogat értéke szállításkezelő folyamatokban használatos.</span><span class="sxs-lookup"><span data-stu-id="5a325-110">The values for the weight and volume are used in transportation management processes.</span></span> <span data-ttu-id="5a325-111">Például az értékek szerepelnek a díj és útvonal munkaterületen, ahol segítségével meghatározható a rakományok díja és útvonala, illetve használatos szállítási ajánlatoknál és járművezetői bejelentkezéseknél is.</span><span class="sxs-lookup"><span data-stu-id="5a325-111">For example, the values are used in the rate route workbench, where they help define the rate and route for loads, and they are also used for transportation tenders and driver check-in.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="5a325-112">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="5a325-112">Where it applies</span></span>

<span data-ttu-id="5a325-113">A tároló tömegének és térfogatának feltüntetése a rakományon funkció a szállításkezelési folyamatokra vonatkozik, például a díj és útvonal munkaterületen, szállítási ajánlatoknál és járművezetők bejelentkezésénél.</span><span class="sxs-lookup"><span data-stu-id="5a325-113">The functionality for including the container weight and volume on a load applies in transportation management processes, such as the rate route workbench, transportation tenders, and driver check-in.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="5a325-114">Hogyan van beállítva</span><span class="sxs-lookup"><span data-stu-id="5a325-114">How it is set up</span></span>

<span data-ttu-id="5a325-115">A rakománynál figyelembe veendő tárolók számának kiszámítása a tároló súlya és térfogata és a tároló százalékos kihasználtsága alapján történik.</span><span class="sxs-lookup"><span data-stu-id="5a325-115">The number of containers that should be considered for a load is calculated based on the weight and volume of the container, and on the percentage of the container is used.</span></span>

-   <span data-ttu-id="5a325-116">A tároló súlyának és térfogatának beállításához kattintson **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolótípusok** elemre.</span><span class="sxs-lookup"><span data-stu-id="5a325-116">To set the weight and volume for a container, click **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>

-   <span data-ttu-id="5a325-117">A tároló százalékos kihasználtsága beállításához kattintson a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolócsoportok** elemre, majd írjon be egy értéket a **Tároló százalékos kihasználtsága** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5a325-117">To set the container utilization percentage, click **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**, and then enter a value in the **Container utilization percentage** field.</span></span>

