---
title: Csökkentési napok – Példa
description: Csökkentési napok – Példa.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90a2efff0add508ddb3d750bb3ca27ea35bf113a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836062"
---
# <a name="reduction-days-example"></a><span data-ttu-id="833a7-103">Csökkentési napok – Példa</span><span class="sxs-lookup"><span data-stu-id="833a7-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="833a7-104">Előfizetési tranzakciót hozott létre egy vevő karbantartási előfizetéséhez a következő táblázatban foglaltak szerint.</span><span class="sxs-lookup"><span data-stu-id="833a7-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="833a7-105">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="833a7-105">From date</span></span></p></th>
<th><p><span data-ttu-id="833a7-106">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="833a7-106">To date</span></span></p></th>
<th><p><span data-ttu-id="833a7-107">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="833a7-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="833a7-108">Előfizetés típusa</span><span class="sxs-lookup"><span data-stu-id="833a7-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="833a7-109">Project</span><span class="sxs-lookup"><span data-stu-id="833a7-109">Project</span></span></p></th>
<th><p><span data-ttu-id="833a7-110">Kategória</span><span class="sxs-lookup"><span data-stu-id="833a7-110">Category</span></span></p></th>
<th><p><span data-ttu-id="833a7-111">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="833a7-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="833a7-112">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="833a7-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="833a7-113">2011. március 01.</span><span class="sxs-lookup"><span data-stu-id="833a7-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="833a7-114">2011. március 31.</span><span class="sxs-lookup"><span data-stu-id="833a7-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="833a7-115">SZÁM - 2</span><span class="sxs-lookup"><span data-stu-id="833a7-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="833a7-116"><strong>Szabályos</strong></span><span class="sxs-lookup"><span data-stu-id="833a7-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="833a7-117">9013</span><span class="sxs-lookup"><span data-stu-id="833a7-117">9013</span></span></p></td>
<td><p><span data-ttu-id="833a7-118">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="833a7-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="833a7-119">HUF</span><span class="sxs-lookup"><span data-stu-id="833a7-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="833a7-120">200,00</span><span class="sxs-lookup"><span data-stu-id="833a7-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="833a7-121">Az ügyfél bejelenti, hogy két napig (március 10-e és március 11-e) nem igényli a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="833a7-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="833a7-122">Ön elfogadja, hogy az előfizetést e két nappal csökkenti.</span><span class="sxs-lookup"><span data-stu-id="833a7-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="833a7-123">Az alábbi táblázatban foglaltaknak megfelelően létrehoz egy új, **Csökkentési napok** típusú tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="833a7-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="833a7-124">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="833a7-124">From date</span></span></p></th>
<th><p><span data-ttu-id="833a7-125">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="833a7-125">To date</span></span></p></th>
<th><p><span data-ttu-id="833a7-126">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="833a7-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="833a7-127">Előfizetés típusa</span><span class="sxs-lookup"><span data-stu-id="833a7-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="833a7-128">Project</span><span class="sxs-lookup"><span data-stu-id="833a7-128">Project</span></span></p></th>
<th><p><span data-ttu-id="833a7-129">Kategória</span><span class="sxs-lookup"><span data-stu-id="833a7-129">Category</span></span></p></th>
<th><p><span data-ttu-id="833a7-130">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="833a7-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="833a7-131">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="833a7-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="833a7-132">2011. március 10.</span><span class="sxs-lookup"><span data-stu-id="833a7-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="833a7-133">2011. március 11.</span><span class="sxs-lookup"><span data-stu-id="833a7-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="833a7-134">SZÁM - 2</span><span class="sxs-lookup"><span data-stu-id="833a7-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="833a7-135"><strong>Csökkentési napok</strong></span><span class="sxs-lookup"><span data-stu-id="833a7-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="833a7-136">9013</span><span class="sxs-lookup"><span data-stu-id="833a7-136">9013</span></span></p></td>
<td><p><span data-ttu-id="833a7-137">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="833a7-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="833a7-138">HUF</span><span class="sxs-lookup"><span data-stu-id="833a7-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="833a7-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="833a7-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="833a7-140">A 2011. márciusi tranzakciók számlázása esetén a 200 eurós eladási ár 12,90 euróval csökken.</span><span class="sxs-lookup"><span data-stu-id="833a7-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="833a7-141">Az előfizetési tranzakcióhoz felszámítható összeg ezért 187,10 euró, és a két tranzakció összesített számlaértéke 187,10 euró lesz.</span><span class="sxs-lookup"><span data-stu-id="833a7-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="833a7-142">Lásd még</span><span class="sxs-lookup"><span data-stu-id="833a7-142">See also</span></span>

[<span data-ttu-id="833a7-143">Előfizetési díjak napjainak csökkentése</span><span class="sxs-lookup"><span data-stu-id="833a7-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]