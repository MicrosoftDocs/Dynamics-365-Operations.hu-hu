---
title: Szervizrendelések kombinálása
description: Lehetőség van a szervizrendelések kombinálására
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
ms.openlocfilehash: 17fbed59b1fe7bec80f25f74451872efd61bed62
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977000"
---
# <a name="combine-service-orders"></a><span data-ttu-id="010f4-103">Szervizrendelések kombinálása</span><span class="sxs-lookup"><span data-stu-id="010f4-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="010f4-104">Ha automatikusan hoz létre szervizrendeléssorokat a **Szolgáltatási szerződések** képernyőn, kiválaszthat egyet a következő beállítások közül, hogy megadja a csoportosításuk módját:</span><span class="sxs-lookup"><span data-stu-id="010f4-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="010f4-105">**Szolgáltatási szerződés szerint**</span><span class="sxs-lookup"><span data-stu-id="010f4-105">**By service agreement**</span></span>

  - <span data-ttu-id="010f4-106">**Szervizfeladat szerint**</span><span class="sxs-lookup"><span data-stu-id="010f4-106">**By service task**</span></span>

  - <span data-ttu-id="010f4-107">**Alkalmazott szerint**</span><span class="sxs-lookup"><span data-stu-id="010f4-107">**By employee**</span></span>

  - <span data-ttu-id="010f4-108">**A szolgáltatás tárgya szerint**</span><span class="sxs-lookup"><span data-stu-id="010f4-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="010f4-109">Példa</span><span class="sxs-lookup"><span data-stu-id="010f4-109">Example</span></span>

<span data-ttu-id="010f4-110">Létrehoz egy szolgáltatási szerződést, amelynek kezdő dátuma 2017. 03. 31.</span><span class="sxs-lookup"><span data-stu-id="010f4-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="010f4-111">A **Szervizrendelések kombinálása** mezőben válassza ki a **Szolgáltatási tárgy szerint** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="010f4-111">In the **Combine service orders** field, you specify **By service object** .</span></span> <span data-ttu-id="010f4-112">Ezzel létrehozza a következő szolgáltatásiszerződés-sorokat:</span><span class="sxs-lookup"><span data-stu-id="010f4-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="010f4-113">Szerződéssor száma</span><span class="sxs-lookup"><span data-stu-id="010f4-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="010f4-114">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="010f4-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="010f4-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="010f4-115">Description</span></span></p></th>
<th><p><span data-ttu-id="010f4-116">Intervallum</span><span class="sxs-lookup"><span data-stu-id="010f4-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="010f4-117">A szolgáltatás tárgya</span><span class="sxs-lookup"><span data-stu-id="010f4-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="010f4-118">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="010f4-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="010f4-119">1</span><span class="sxs-lookup"><span data-stu-id="010f4-119">1</span></span></p></td>
<td><p><span data-ttu-id="010f4-120"><strong>Óra</strong></span><span class="sxs-lookup"><span data-stu-id="010f4-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="010f4-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="010f4-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="010f4-122">Heti</span><span class="sxs-lookup"><span data-stu-id="010f4-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="010f4-123">X-1</span><span class="sxs-lookup"><span data-stu-id="010f4-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="010f4-124">2007. 04. 01.</span><span class="sxs-lookup"><span data-stu-id="010f4-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="010f4-125">2</span><span class="sxs-lookup"><span data-stu-id="010f4-125">2</span></span></p></td>
<td><p><span data-ttu-id="010f4-126"><strong>Óra</strong></span><span class="sxs-lookup"><span data-stu-id="010f4-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="010f4-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="010f4-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="010f4-128">Kéthetente</span><span class="sxs-lookup"><span data-stu-id="010f4-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="010f4-129">X-2</span><span class="sxs-lookup"><span data-stu-id="010f4-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="010f4-130">2007. 04. 01.</span><span class="sxs-lookup"><span data-stu-id="010f4-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="010f4-131">3</span><span class="sxs-lookup"><span data-stu-id="010f4-131">3</span></span></p></td>
<td><p><span data-ttu-id="010f4-132"><strong>Óra</strong></span><span class="sxs-lookup"><span data-stu-id="010f4-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="010f4-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="010f4-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="010f4-134">Heti</span><span class="sxs-lookup"><span data-stu-id="010f4-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="010f4-135">X-2</span><span class="sxs-lookup"><span data-stu-id="010f4-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="010f4-136">2007. 04. 01.</span><span class="sxs-lookup"><span data-stu-id="010f4-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="010f4-137">Nincs megadva időkeretet a szolgáltatási szerződés egyik sorához sem.</span><span class="sxs-lookup"><span data-stu-id="010f4-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="010f4-138">Emiatt a szervizrendeléssorok nem kerülnek át másik napra arról a napról, amelyre a számítás után estek.</span><span class="sxs-lookup"><span data-stu-id="010f4-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="010f4-139">Ezután hozzon létre szervizrendeléssorokat a **Szervizrendelések létrehozása** képernyőn, 2007. 04. 01-től 2007. 04. 30-ig.</span><span class="sxs-lookup"><span data-stu-id="010f4-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="010f4-140">Összesen 10 szervizrendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="010f4-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="010f4-141">Mivel a kombinált beállítás, amelyet kiválasztott, **A szolgáltatás tárgya szerint** volt, minden létrehozott szervizrendelésben csak olyan szervizrendeléssorok szerepelnek, melyekben egy meghatározott szolgáltatási objektum szerepel.</span><span class="sxs-lookup"><span data-stu-id="010f4-141">Because the combined setting that you selected was **By service object** , all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="010f4-142">Azok a szervizrendeléssorok, amelyeket a szolgáltatási szerződésből generál, és amelyekben megegyezik a dátum és a szolgáltatási objektum, ugyanabba a szervizrendelésbe kerülnek.</span><span class="sxs-lookup"><span data-stu-id="010f4-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="010f4-143">Ebben a példában a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyőn megadott naptárban nem szerepelnek lezárt napok.</span><span class="sxs-lookup"><span data-stu-id="010f4-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="010f4-144">A szolgáltatási szerződés soraira megadott időkeretek meghatározzák a szervizrendeléssorok szervizrendeléseken történő további csoportosítását.</span><span class="sxs-lookup"><span data-stu-id="010f4-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="010f4-145">Lásd még</span><span class="sxs-lookup"><span data-stu-id="010f4-145">See also</span></span>

[<span data-ttu-id="010f4-146">Szervizrendelések automatikus létrehozása</span><span class="sxs-lookup"><span data-stu-id="010f4-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  


