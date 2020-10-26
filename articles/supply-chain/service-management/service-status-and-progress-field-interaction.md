---
title: A szolgáltatási állapot és az állapotjelző mező közötti kapcsolat
description: A Szervizrendelések képernyőn a szervizrendelés fejlécének Folyamat mezője a teljes szervizrendelés, míg az Állapot mező az egyes szervizrendelési sorok állapotát mutatja.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a94f2df6a4ddb71a29ff951dfe38618ac7762783
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975488"
---
# <a name="service-status-and-progress-field-interaction"></a><span data-ttu-id="3801a-103">A szolgáltatási állapot és az állapotjelző mező közötti kapcsolat</span><span class="sxs-lookup"><span data-stu-id="3801a-103">Service status and progress field interaction</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="3801a-104">A **Szervizrendelések** képernyőn a szervizrendelés fejlécének **Folyamat** mezője a teljes szervizrendelés, míg az **Állapot** mező az egyes szervizrendelési sorok állapotát mutatja.</span><span class="sxs-lookup"><span data-stu-id="3801a-104">In the **Service orders** form, the **Progress** field on the service order header reflects the status of the whole service order, and the **Status** reports the status of individual service order lines.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3801a-105">Folyamat</span><span class="sxs-lookup"><span data-stu-id="3801a-105">Progress</span></span></p></th>
<th><p><span data-ttu-id="3801a-106">1. sor állapota</span><span class="sxs-lookup"><span data-stu-id="3801a-106">Line 1 Status</span></span></p></th>
<th><p><span data-ttu-id="3801a-107">2. sor állapota</span><span class="sxs-lookup"><span data-stu-id="3801a-107">Line 2 Status</span></span></p></th>
<th><p><span data-ttu-id="3801a-108">3. sor állapota</span><span class="sxs-lookup"><span data-stu-id="3801a-108">Line 3 Status</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3801a-109"><strong>Folyamatban</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-109"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-110"><strong>Létrehozva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-110"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-111"><strong>Létrehozva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-111"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-112"><strong>Létrehozva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-112"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3801a-113"><strong>Folyamatban</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-113"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-114"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-114"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-115"><strong>Létrehozva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-115"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-116"><strong>Létrehozva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-116"><strong>Created</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3801a-117"><strong>Folyamatban</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-117"><strong>In process</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-118"><strong>Létrehozva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-118"><strong>Created</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-119"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-119"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-120"><strong>Feladva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-120"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3801a-121"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-121"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-122"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-122"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-123"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-123"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-124"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-124"><strong>Canceled</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3801a-125"><strong>Feladva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-125"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-126"><strong>Feladva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-126"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-127"><strong>Feladva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-127"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-128"><strong>Feladva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-128"><strong>Posted</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3801a-129"><strong>Feladva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-129"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-130"><strong>Feladva</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-130"><strong>Posted</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-131"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-131"><strong>Canceled</strong></span></span></p></td>
<td><p><span data-ttu-id="3801a-132"><strong>Törölve</strong></span><span class="sxs-lookup"><span data-stu-id="3801a-132"><strong>Canceled</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3801a-133">A szervizrendelés folyamatban van, ha minden sor **Létrehozva** állapotú, és még mindig folyamatban levőnek számít, ha egyes sorok **Törölve** vagy **Feladva** állapotúak.</span><span class="sxs-lookup"><span data-stu-id="3801a-133">The progress of a service order is in process if all lines have the status **Created** ; it is still in process if some of the lines have a status of **Canceled** or **Posted** .</span></span>

<span data-ttu-id="3801a-134">Ha egy szervizrendelés összes sor **Feladva** állapotúnak van megjelölve, a rendelés **Feladva** állapotú.</span><span class="sxs-lookup"><span data-stu-id="3801a-134">If all lines in a service order are marked as **Posted** , the progress of the status order is **Posted** .</span></span> <span data-ttu-id="3801a-135">Ha egyes sorok **Feladva** , mások **Törölve** állapotúak, a folyamat továbbra is **Feladva** állapotú.</span><span class="sxs-lookup"><span data-stu-id="3801a-135">If some lines are **Posted** and some are **Canceled** , the progress is still **Posted** .</span></span>

  


