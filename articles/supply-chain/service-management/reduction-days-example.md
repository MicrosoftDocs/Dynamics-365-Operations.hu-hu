---
title: "Csökkentési napok – Példa"
description: "Csökkentési napok – Példa."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 46b38579e8a6246476d0893e1a047ad434f6d399
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---


# <a name="reduction-days-example"></a><span data-ttu-id="30368-103">Csökkentési napok – Példa</span><span class="sxs-lookup"><span data-stu-id="30368-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="30368-104">Előfizetési tranzakciót hozott létre egy vevő karbantartási előfizetéséhez a következő táblázatban foglaltak szerint.</span><span class="sxs-lookup"><span data-stu-id="30368-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="30368-105">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="30368-105">From date</span></span></p></th>
<th><p><span data-ttu-id="30368-106">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="30368-106">To date</span></span></p></th>
<th><p><span data-ttu-id="30368-107">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="30368-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="30368-108">Előfizetés típusa</span><span class="sxs-lookup"><span data-stu-id="30368-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="30368-109">Project</span><span class="sxs-lookup"><span data-stu-id="30368-109">Project</span></span></p></th>
<th><p><span data-ttu-id="30368-110">Kategória</span><span class="sxs-lookup"><span data-stu-id="30368-110">Category</span></span></p></th>
<th><p><span data-ttu-id="30368-111">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="30368-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="30368-112">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="30368-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30368-113">2011. március 01.</span><span class="sxs-lookup"><span data-stu-id="30368-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="30368-114">2011. március 31.</span><span class="sxs-lookup"><span data-stu-id="30368-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="30368-115">SZÁM - 2</span><span class="sxs-lookup"><span data-stu-id="30368-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="30368-116"><strong>Szabályos</strong></span><span class="sxs-lookup"><span data-stu-id="30368-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="30368-117">9013</span><span class="sxs-lookup"><span data-stu-id="30368-117">9013</span></span></p></td>
<td><p><span data-ttu-id="30368-118">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="30368-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="30368-119">HUF</span><span class="sxs-lookup"><span data-stu-id="30368-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="30368-120">200,00</span><span class="sxs-lookup"><span data-stu-id="30368-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="30368-121">Az ügyfél bejelenti, hogy két napig (március 10-e és március 11-e) nem igényli a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="30368-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="30368-122">Ön elfogadja, hogy az előfizetést e két nappal csökkenti.</span><span class="sxs-lookup"><span data-stu-id="30368-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="30368-123">Az alábbi táblázatban foglaltaknak megfelelően létrehoz egy új, **Csökkentési napok** típusú tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="30368-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="30368-124">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="30368-124">From date</span></span></p></th>
<th><p><span data-ttu-id="30368-125">Záró dátum</span><span class="sxs-lookup"><span data-stu-id="30368-125">To date</span></span></p></th>
<th><p><span data-ttu-id="30368-126">Előfizetés</span><span class="sxs-lookup"><span data-stu-id="30368-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="30368-127">Előfizetés típusa</span><span class="sxs-lookup"><span data-stu-id="30368-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="30368-128">Project</span><span class="sxs-lookup"><span data-stu-id="30368-128">Project</span></span></p></th>
<th><p><span data-ttu-id="30368-129">Kategória</span><span class="sxs-lookup"><span data-stu-id="30368-129">Category</span></span></p></th>
<th><p><span data-ttu-id="30368-130">Értékesítés pénzneme</span><span class="sxs-lookup"><span data-stu-id="30368-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="30368-131">Eladási ár</span><span class="sxs-lookup"><span data-stu-id="30368-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30368-132">2011. március 10.</span><span class="sxs-lookup"><span data-stu-id="30368-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="30368-133">2011. március 11.</span><span class="sxs-lookup"><span data-stu-id="30368-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="30368-134">SZÁM - 2</span><span class="sxs-lookup"><span data-stu-id="30368-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="30368-135"><strong>Csökkentési napok</strong></span><span class="sxs-lookup"><span data-stu-id="30368-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="30368-136">9013</span><span class="sxs-lookup"><span data-stu-id="30368-136">9013</span></span></p></td>
<td><p><span data-ttu-id="30368-137">Alkateg2</span><span class="sxs-lookup"><span data-stu-id="30368-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="30368-138">HUF</span><span class="sxs-lookup"><span data-stu-id="30368-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="30368-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="30368-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="30368-140">A 2011. márciusi tranzakciók számlázása esetén a 200 eurós eladási ár 12,90 euróval csökken.</span><span class="sxs-lookup"><span data-stu-id="30368-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="30368-141">Az előfizetési tranzakcióhoz felszámítható összeg ezért 187,10 euró, és a két tranzakció összesített számlaértéke 187,10 euró lesz.</span><span class="sxs-lookup"><span data-stu-id="30368-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="30368-142">Lásd még</span><span class="sxs-lookup"><span data-stu-id="30368-142">See also</span></span>

[<span data-ttu-id="30368-143">Előfizetési díjak napjainak csökkentése</span><span class="sxs-lookup"><span data-stu-id="30368-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  



