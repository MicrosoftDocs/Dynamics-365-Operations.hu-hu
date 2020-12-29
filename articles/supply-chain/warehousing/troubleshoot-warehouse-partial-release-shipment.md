---
title: Részleges kiadások és részleges szállítmányok – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a részleges kiadásokat és a részleges szállításokat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e89a430f90374733b23fadaf53f5bab598d67d62
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645948"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a><span data-ttu-id="b29f9-103">Részleges kiadások és részleges szállítmányok – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="b29f9-103">Troubleshoot partial releases and partial shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b29f9-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a részleges kiadásokat és a részleges szállításokat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="b29f9-104">This topic describes how to fix common issues that you might encounter while you work with partial releases and partial shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a><span data-ttu-id="b29f9-105">Egy értékesítési rendelés kiadási állapota még az értékesítési rendelés számlázása után is részlegesen jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b29f9-105">The release status of a sales order remains Partially released even after the sales order is invoiced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b29f9-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="b29f9-106">Issue description</span></span>

<span data-ttu-id="b29f9-107">Egy értékesítési rendelés szállítási rendelés, de egy vagy több cikknek más a szállítási módja.</span><span class="sxs-lookup"><span data-stu-id="b29f9-107">A sales order is a delivery order, but one or more items on it have a different mode of delivery.</span></span> <span data-ttu-id="b29f9-108">A rendelés számlázása után a program továbbra is *Részlegesen kiadott* kiadási állapotú.</span><span class="sxs-lookup"><span data-stu-id="b29f9-108">After the order is invoiced, it still has a release status of *Partially released*.</span></span>

<span data-ttu-id="b29f9-109">Például egy értékesítési rendelésnek két eleme van: egy szállításra és egy kitárolásra.</span><span class="sxs-lookup"><span data-stu-id="b29f9-109">For example, a sales order has two items: one for delivery and one for pickup.</span></span> <span data-ttu-id="b29f9-110">A szállítás és a kitárolás is megtörtént.</span><span class="sxs-lookup"><span data-stu-id="b29f9-110">Both the delivery and the pickup have been done.</span></span> <span data-ttu-id="b29f9-111">Ennélfogva mindkét sor számlázva van.</span><span class="sxs-lookup"><span data-stu-id="b29f9-111">Therefore, both lines have been invoiced.</span></span> <span data-ttu-id="b29f9-112">A kiadási állapot azonban továbbra is *Részleges kiadásként* jelenik meg, ami félrevezető.</span><span class="sxs-lookup"><span data-stu-id="b29f9-112">However, the release status is still shown as *Partially released*, which is misleading.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b29f9-113">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="b29f9-113">Issue resolution</span></span>

<span data-ttu-id="b29f9-114">A kiadás állapota csak azokra a rendelési sorokra vonatkozik, amelyeknél a cikkek engedélyezve vannak a raktárkezelésben.</span><span class="sxs-lookup"><span data-stu-id="b29f9-114">The release status applies only to order lines where the items are enabled for warehouse management.</span></span> <span data-ttu-id="b29f9-115">Emiatt a kiadási állapot továbbra is *Részlegesen kiadott* marad ebben a forgatókönyvben.</span><span class="sxs-lookup"><span data-stu-id="b29f9-115">Therefore, the release status remains *Partially released* in this scenario.</span></span> <span data-ttu-id="b29f9-116">A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás.</span><span class="sxs-lookup"><span data-stu-id="b29f9-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="b29f9-117">A kiadási állapot frissítéséhez egy kiterjesztés adható a szállítólevél és a számlázási folyamat részeként.</span><span class="sxs-lookup"><span data-stu-id="b29f9-117">An extension could be added as part of the packing slip and invoicing process to update the release status.</span></span>
