---
title: A szállító nincs megadva a tervezett rendelések megerősítésekor
description: Amikor tervezett rendeléseket próbál megerősíteni, olyan hibaüzenetet kap, amely szerint nincs megadva szállító.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cf41295045211f8a714194494028922d573c9e9e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294089"
---
# <a name="vendor-isnt-specified-when-planned-orders-are-firmed"></a><span data-ttu-id="5a5c8-103">A szállító nincs megadva a tervezett rendelések megerősítésekor</span><span class="sxs-lookup"><span data-stu-id="5a5c8-103">Vendor isn't specified when planned orders are firmed</span></span>

<span data-ttu-id="5a5c8-104">Hibakód: SYS23532</span><span class="sxs-lookup"><span data-stu-id="5a5c8-104">Error code: SYS23532</span></span>

## <a name="symptoms"></a><span data-ttu-id="5a5c8-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="5a5c8-105">Symptoms</span></span>

<span data-ttu-id="5a5c8-106">Amikor tervezett rendeléseket próbál megerősíteni, a következő hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="5a5c8-106">When you try to firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="5a5c8-107">A szállító nincs megadva</span><span class="sxs-lookup"><span data-stu-id="5a5c8-107">Vendor is not specified</span></span>

## <a name="resolution"></a><span data-ttu-id="5a5c8-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="5a5c8-108">Resolution</span></span>

<span data-ttu-id="5a5c8-109">Szállító megadásához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="5a5c8-109">To specify a vendor, follow these steps.</span></span>

1. <span data-ttu-id="5a5c8-110">Nyissa meg azt a tervezett rendelést, amelynél hiányzik egy szállító.</span><span class="sxs-lookup"><span data-stu-id="5a5c8-110">Open the planned order that is missing a vendor.</span></span>
1. <span data-ttu-id="5a5c8-111">A **Tervezett kínálat** gyorslap **Szállító** mezőjében válasszon ki egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="5a5c8-111">On the **Planned supply** FastTab, in the **Vendor** field, select a vendor.</span></span>
