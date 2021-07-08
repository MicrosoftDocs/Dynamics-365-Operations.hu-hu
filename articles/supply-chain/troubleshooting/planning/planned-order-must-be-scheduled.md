---
title: A tervezett termelési rendelést ütemezni kell a megerősítés előtt
description: Amikor tervezett rendelést próbál megerősíteni, olyan hibaüzenet jelenik meg, amely szerint a rendelést ütemezni kell a megerősítés előtt.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294096"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a><span data-ttu-id="55509-103">A tervezett termelési rendelést ütemezni kell a megerősítés előtt</span><span class="sxs-lookup"><span data-stu-id="55509-103">Planned production order must be scheduled before it can be firmed</span></span>

<span data-ttu-id="55509-104">Hibakód: SYS309802</span><span class="sxs-lookup"><span data-stu-id="55509-104">Error code: SYS309802</span></span>

## <a name="symptoms"></a><span data-ttu-id="55509-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="55509-105">Symptoms</span></span>

<span data-ttu-id="55509-106">Amikor tervezett rendelést próbál megerősíteni, a következő hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="55509-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="55509-107">A tervezett termelési rendelést megerősítés előtt ütemezni kell.</span><span class="sxs-lookup"><span data-stu-id="55509-107">The planned production order must be scheduled before it can be firmed.</span></span>

## <a name="cause"></a><span data-ttu-id="55509-108">Ok</span><span class="sxs-lookup"><span data-stu-id="55509-108">Cause</span></span>

<span data-ttu-id="55509-109">Az ütemezett kezdő és záró dátum nem lehet üres.</span><span class="sxs-lookup"><span data-stu-id="55509-109">The scheduled start and end dates can't be blank.</span></span>

## <a name="resolution"></a><span data-ttu-id="55509-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="55509-110">Resolution</span></span>

<span data-ttu-id="55509-111">A tervezett rendelés kezdő és záró dátumának megadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="55509-111">To specify start and end dates for the planned order, follow these steps.</span></span>

1. <span data-ttu-id="55509-112">Ugorjon az **Alaptervezés \> Alaptervezés \> Tervezett rendelések** pontra.</span><span class="sxs-lookup"><span data-stu-id="55509-112">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="55509-113">Nyissa meg a megfelelő tervezett rendelést.</span><span class="sxs-lookup"><span data-stu-id="55509-113">Open the relevant planned order.</span></span>
1. <span data-ttu-id="55509-114">Az **Általános** gyorslap **Ütemezett** szakaszában adja meg a **Kezdő dátum** és a **Záró dátum** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="55509-114">On the **General** FastTab, in the **Scheduled** section, specify dates in the **Start date** and **End date** fields.</span></span>
