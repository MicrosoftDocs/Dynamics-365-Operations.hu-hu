---
title: Jövőben esedékes csekkek
description: Ez a cikk a Microsoft Dynamics 365 Finance támogatását írja le a jövőben esedékes csekkeket illetően. A jövőben esedékes csekkek olyan csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítják ki. Emiatt a csekk nem váltható be a megadott dátumig.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38ee6c5b3d258c313a2066b388a83330bf696d39
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178121"
---
# <a name="postdated-checks"></a><span data-ttu-id="bd6c6-105">Jövőben esedékes csekkek</span><span class="sxs-lookup"><span data-stu-id="bd6c6-105">Postdated checks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd6c6-106">Ez a cikk a támogatást írja le a jövőben esedékes csekkeket illetően.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-106">This article provides information about support for postdated checks.</span></span> <span data-ttu-id="bd6c6-107">A jövőben esedékes csekkek olyan csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítják ki.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="bd6c6-108">Emiatt a csekk nem váltható be a megadott dátumig.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="bd6c6-109">A Dynamics 365 Finance támogatja a teljes menedzselési ciklust a jövőben esedékes csekkekhez, a Kinnlevőségekben és a Kötelezettségekben is, ahogy a következő táblázat mutatja.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-109">Dynamics 365 Finance supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd6c6-110">Eset</span><span class="sxs-lookup"><span data-stu-id="bd6c6-110">Scenario</span></span></th>
<th><span data-ttu-id="bd6c6-111">Részletek</span><span class="sxs-lookup"><span data-stu-id="bd6c6-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bd6c6-112">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="bd6c6-113">Állítson be egy új fizetési módot, és adja meg a kifizetési módot a kiállított csekkekhez, a beérkezett csekkekhez és az adóelőleghez.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bd6c6-114">Szállítónak kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="bd6c6-115">Jegyezze be a szállítónak feladni kívánt jövőben esedékes csekk adatait.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="bd6c6-116">A kifizetés feladásakor a szállítói felelősség elismerésre kerül, de a bankszámla jóváírása még nem történik meg.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="bd6c6-117">Ehelyett erre a célra elszámoló-számlát alkalmaznak.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bd6c6-118">Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="bd6c6-119">Jegyezze fel a vevőtől érkezett, jövőben esedékes csekk adataid.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="bd6c6-120">A kifizetés feladásakor a vevő megkapja az értesítést arról, hogy a kifizetés megtörtént, azonban a bankszámla terhelése még nem történik meg.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="bd6c6-121">Ehelyett erre a célra elszámoló-számlát alkalmaznak.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bd6c6-122">Szállítónak vagy vevőnek kiállított helyettesítő, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="bd6c6-123">Ha a szállítónak vagy a vevőnek készült eredeti csekk elveszik vagy megsérül, helyettesítő, jövőben esedékes csekket bocsáthat ki.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="bd6c6-124">Amikor nyilvántartásba veszi a csekk részletes adatait, hivatkozzon az eredeti csekkre és jelezze, hogy az új csekk az eredetit helyettesíti.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="bd6c6-125">Fel is adhatja a helyettesítő csekket.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bd6c6-126">Vevő által kiállított, jövőben esedékes csekk átvitele szállítónak</span><span class="sxs-lookup"><span data-stu-id="bd6c6-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="bd6c6-127">Amikor egy jövőben esedékes csekket kap egy vevőtől, a csekket átadhatja egy szállítónak fizetésként.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bd6c6-128">Vevő vagy szállítónak kiállított, jövőben esedékes csekk kiegyenlítése</span><span class="sxs-lookup"><span data-stu-id="bd6c6-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="bd6c6-129">Fizesse ki az áthidaló számlára (a vevőnek vagy a szállítónak kiállított) feladott csekket akkor, amikor az érvényessé válik.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="bd6c6-130">A csekk kifizetésekor a bank jóváírja vagy tartozást hagy a korábban használt elszámoló-számlával szemben.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bd6c6-131">Szállítónak kiállított, jövőben esedékes csekk érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="bd6c6-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="bd6c6-132">Érvénytelenítheti a könyvelt, jövőben esedékes csekket ezekben az esetekben: - A csekket visszaküldik a banknak.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="bd6c6-133">- A csekket nem megfelelő számlához alkalmazták.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="bd6c6-134">- Készpénzes fizetés történik a csekkel szemben.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-134">- A cash payment is made against the check.</span></span>
  </td>
  </tr>
  <tr class="even">
  <td><span data-ttu-id="bd6c6-135">Jövőben esedékes csekk kifizetésének leállítása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-135">Stop payment for a postdated check</span></span></td>
  <td><span data-ttu-id="bd6c6-136">Leállíthatja egy szállítónak kiállított, jövőben esedékes csekk kifizetését különböző okokból, például elégtelen fedezet esetén, a szállítóval kötött szerződés feltételeinek megváltozásakor, a szállító által szállított hibás áruk, vagy a termékek szállítóhoz történő visszaküldése miatt.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="bd6c6-137">Csak olyan csekkek kifizetése állítható le, amelyek még nincsenek kiegyenlítve.</span><span class="sxs-lookup"><span data-stu-id="bd6c6-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
  </tr>
  </tbody>
  </table>



<span data-ttu-id="bd6c6-138">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="bd6c6-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="bd6c6-139">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="bd6c6-140">Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="bd6c6-141">Vevő által kiállított, jövőben esedékes csekk kiegyenlítése</span><span class="sxs-lookup"><span data-stu-id="bd6c6-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="bd6c6-142">Szállító részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="bd6c6-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="bd6c6-143">Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése</span><span class="sxs-lookup"><span data-stu-id="bd6c6-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)



