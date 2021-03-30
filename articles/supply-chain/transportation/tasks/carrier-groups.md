---
title: Szállítmányozói csoportok
description: Ez a témakör az adatok beállítását írja le a szállítmányozói csoportokhoz.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 95517153dda06cecf8e57b1f9b080aa07966c111
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247262"
---
# <a name="carrier-groups"></a><span data-ttu-id="98644-103">Szállítmányozói csoportok</span><span class="sxs-lookup"><span data-stu-id="98644-103">Carrier groups</span></span>

<span data-ttu-id="98644-104">A szállítmányozói csoport a szállítmányozók és a szállítási szolgáltatások gyűjteménye.</span><span class="sxs-lookup"><span data-stu-id="98644-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="98644-105">Minden szállítmányozói csoport meghatározza a hozzá tartozó szállítmányozók és szállítmányozói szolgáltatások preferált sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="98644-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="98644-106">Ha ugyanahhoz az útvonalszegmenshez több szállítmányozó és szállítási szolgáltatás is létezik, az útvonaltervben vagy az útvonal-útmutatóban megadhat egy szállítmányozói csoportot egy adott szállítmányozó és szállítói szolgáltatás helyett.</span><span class="sxs-lookup"><span data-stu-id="98644-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="98644-107">Szállítmányozói csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="98644-107">Create a carrier group</span></span>

1. <span data-ttu-id="98644-108">Ugorjon a **Szállításkezelés &gt; Beállítás &gt; Szállítmányozók &gt; Szállítmányozói csoport** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="98644-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="98644-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98644-109">Select **New**.</span></span>
1. <span data-ttu-id="98644-110">A **szállítmányozói csoport** mezőbe írja be a csoport egyedi azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="98644-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="98644-111">A **Név** mezőbe írja be a csoport ismertető nevét.</span><span class="sxs-lookup"><span data-stu-id="98644-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="98644-112">A **Részletek** gyorslapon adjon hozzá egy sort, és válasszon ki egy szállítmányozót és egy szállítmányozói szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="98644-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="98644-113">Ismételje ezt a lépést addig, amíg nem adott hozzá annyi szállítmányozót, amennyi szükséges a csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="98644-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="98644-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="98644-114">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]