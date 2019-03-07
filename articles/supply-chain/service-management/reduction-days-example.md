---
title: Csökkentési napok – Példa
description: Csökkentési napok – Példa.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46b38579e8a6246476d0893e1a047ad434f6d399
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "334105"
---
# <a name="reduction-days-example"></a><span data-ttu-id="03bd8-103">Csökkentési napok – Példa</span><span class="sxs-lookup"><span data-stu-id="03bd8-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="03bd8-104">Előfizetési tranzakciót hozott létre egy vevő karbantartási előfizetéséhez a következő táblázatban foglaltak szerint.</span><span class="sxs-lookup"><span data-stu-id="03bd8-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="03bd8-105">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="03bd8-105">From date</span></span></p></th>
<th><p><span data-ttu-id="03bd8-106">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="03bd8-106">To date</span></span></p></th>
<th><p><span data-ttu-id="03bd8-107">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="03bd8-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="03bd8-108">Előfizetés típusa</span><span class="sxs-lookup"><span data-stu-id="03bd8-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="03bd8-109">Project</span><span class="sxs-lookup"><span data-stu-id="03bd8-109">Project</span></span></p></th>
<th><p><span data-ttu-id="03bd8-110">Kategória</span><span class="sxs-lookup"><span data-stu-id="03bd8-110">Category</span></span></p></th>
<th><p><span data-ttu-id="03bd8-111">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="03bd8-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="03bd8-112">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="03bd8-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03bd8-113">2011. március 01.</span><span class="sxs-lookup"><span data-stu-id="03bd8-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="03bd8-114">2011. március 31.</span><span class="sxs-lookup"><span data-stu-id="03bd8-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="03bd8-115">SZÁM - 2</span><span class="sxs-lookup"><span data-stu-id="03bd8-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="03bd8-116"><strong>Szabályos</strong></span><span class="sxs-lookup"><span data-stu-id="03bd8-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="03bd8-117">9013</span><span class="sxs-lookup"><span data-stu-id="03bd8-117">9013</span></span></p></td>
<td><p><span data-ttu-id="03bd8-118">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="03bd8-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="03bd8-119">HUF</span><span class="sxs-lookup"><span data-stu-id="03bd8-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="03bd8-120">200,00</span><span class="sxs-lookup"><span data-stu-id="03bd8-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03bd8-121">Az ügyfél bejelenti, hogy két napig (március 10-e és március 11-e) nem igényli a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="03bd8-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="03bd8-122">Ön elfogadja, hogy az előfizetést e két nappal csökkenti.</span><span class="sxs-lookup"><span data-stu-id="03bd8-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="03bd8-123">Az alábbi táblázatban foglaltaknak megfelelően létrehoz egy új, **Csökkentési napok** típusú tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="03bd8-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="03bd8-124">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="03bd8-124">From date</span></span></p></th>
<th><p><span data-ttu-id="03bd8-125">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="03bd8-125">To date</span></span></p></th>
<th><p><span data-ttu-id="03bd8-126">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="03bd8-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="03bd8-127">Előfizetés típusa</span><span class="sxs-lookup"><span data-stu-id="03bd8-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="03bd8-128">Project</span><span class="sxs-lookup"><span data-stu-id="03bd8-128">Project</span></span></p></th>
<th><p><span data-ttu-id="03bd8-129">Kategória</span><span class="sxs-lookup"><span data-stu-id="03bd8-129">Category</span></span></p></th>
<th><p><span data-ttu-id="03bd8-130">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="03bd8-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="03bd8-131">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="03bd8-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03bd8-132">2011. március 10.</span><span class="sxs-lookup"><span data-stu-id="03bd8-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="03bd8-133">2011. március 11.</span><span class="sxs-lookup"><span data-stu-id="03bd8-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="03bd8-134">SZÁM - 2</span><span class="sxs-lookup"><span data-stu-id="03bd8-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="03bd8-135"><strong>Csökkentési napok</strong></span><span class="sxs-lookup"><span data-stu-id="03bd8-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="03bd8-136">9013</span><span class="sxs-lookup"><span data-stu-id="03bd8-136">9013</span></span></p></td>
<td><p><span data-ttu-id="03bd8-137">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="03bd8-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="03bd8-138">HUF</span><span class="sxs-lookup"><span data-stu-id="03bd8-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="03bd8-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="03bd8-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03bd8-140">A 2011. márciusi tranzakciók számlázása esetén a 200 eurós eladási ár 12,90 euróval csökken.</span><span class="sxs-lookup"><span data-stu-id="03bd8-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="03bd8-141">Az előfizetési tranzakcióhoz felszámítható összeg ezért 187,10 euró, és a két tranzakció összesített számlaértéke 187,10 euró lesz.</span><span class="sxs-lookup"><span data-stu-id="03bd8-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="03bd8-142">Lásd még</span><span class="sxs-lookup"><span data-stu-id="03bd8-142">See also</span></span>

[<span data-ttu-id="03bd8-143">Előfizetési díjak napjainak csökkentése</span><span class="sxs-lookup"><span data-stu-id="03bd8-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  


