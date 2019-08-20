---
title: Előfizetések könyvelése
description: A szolgáltatási előfizetésekkel manuálisan könyvelhető a bevétel a díjtranzakció kiszámlázását követő időszakokban.
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27908e2852f3f28264f83e0118eb4be79c9e03bc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742286"
---
# <a name="accruing-subscriptions"></a><span data-ttu-id="f13a5-103">Előfizetések könyvelése</span><span class="sxs-lookup"><span data-stu-id="f13a5-103">Accruing subscriptions</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f13a5-104">A szolgáltatási előfizetésekkel manuálisan könyvelhető a bevétel a díjtranzakció kiszámlázását követő időszakokban.</span><span class="sxs-lookup"><span data-stu-id="f13a5-104">With service subscriptions, you manually accrue revenue in the periods following the date when you invoiced a fee transaction.</span></span>

<span data-ttu-id="f13a5-105">Az előfizetési díjra vonatkozóan létrehozott számlázási időszakokra könyvelési időszakok jönnek létre, és a könyvelési időszakok az előfizetés időszakkódjára épülnek.</span><span class="sxs-lookup"><span data-stu-id="f13a5-105">Accrual periods are created for the invoice period that you set up for the subscription fee, and the accrual periods are based on the period code of the subscription.</span></span>

<span data-ttu-id="f13a5-106">A bevételeket elhatárolhatja, illetve sztornírozhatja.</span><span class="sxs-lookup"><span data-stu-id="f13a5-106">You can accrue and reverse accrued revenue.</span></span>

## <a name="reverse-accruals-of-credit-amounts"></a><span data-ttu-id="f13a5-107">Követel összegek könyvelésének sztornírozása</span><span class="sxs-lookup"><span data-stu-id="f13a5-107">Reverse accruals of credit amounts</span></span>

<span data-ttu-id="f13a5-108">Ha meghitelezi a kiszámlázott előfizetési összeget, a könyvelt összegek sztornírozására két különböző módszert használhat:</span><span class="sxs-lookup"><span data-stu-id="f13a5-108">If you credit invoiced subscription amounts, you can use two methods to reverse the accrual amounts:</span></span>

  - <span data-ttu-id="f13a5-109">Sztornírozhat minden egyes könyvelt bevételt külön-külön, mielőtt létrehozza a jóváírási javaslatot a tranzakcióhoz.</span><span class="sxs-lookup"><span data-stu-id="f13a5-109">You can reverse each accrued revenue transaction individually before you create the credit note proposal for the transaction.</span></span> <span data-ttu-id="f13a5-110">Ez a manuális módszer.</span><span class="sxs-lookup"><span data-stu-id="f13a5-110">This is the manual method.</span></span> <span data-ttu-id="f13a5-111">(manuális)</span><span class="sxs-lookup"><span data-stu-id="f13a5-111">(manual)</span></span>

  - <span data-ttu-id="f13a5-112">Vagy sztornírozhatja a könyvelt összegeket a jóváírási javaslat feladási dátumán vagy a könyvelés eredeti feladási dátumán.</span><span class="sxs-lookup"><span data-stu-id="f13a5-112">You can have the accrued amounts reversed on the date where the credit note is posted or on the original posting date of the accrual.</span></span>

<span data-ttu-id="f13a5-113">További tudnivalókkal kapcsolatban lásd: [Subscription parameters (form)](https://technet.microsoft.com/library/aa619615.aspx).</span><span class="sxs-lookup"><span data-stu-id="f13a5-113">For more information, see [Subscription parameters (form)](https://technet.microsoft.com/library/aa619615.aspx).</span></span>

## <a name="setup-requirements"></a><span data-ttu-id="f13a5-114">A beállítás előfeltételei</span><span class="sxs-lookup"><span data-stu-id="f13a5-114">Setup requirements</span></span>

<span data-ttu-id="f13a5-115">A bevételek elhatárolása előtt ellenőrizze, hogy teljesülnek-e a az adatokra vonatkozó követelmények:</span><span class="sxs-lookup"><span data-stu-id="f13a5-115">To accrue revenue, make sure that the following data requirements are met:</span></span>

## <a name="account-setup"></a><span data-ttu-id="f13a5-116">Számlabeállítás</span><span class="sxs-lookup"><span data-stu-id="f13a5-116">Account setup</span></span>

<span data-ttu-id="f13a5-117">A **Folyamatban lévő munka - előfizetés** és az **Elhatárolt bevétel - előfizetés** számlákat kell be kell állítani a **Projekt** modulban.</span><span class="sxs-lookup"><span data-stu-id="f13a5-117">The **WIP - subscription** and the **Accrued revenue - subscription** accounts must be set up in the **Project** module.</span></span>

<span data-ttu-id="f13a5-118">Amikor elhatárolt bevételeket ad fel, a **Folyamatban lévő munka - előfizetés** számlán az elhatárolt összeg tartozik tételként jelenik meg, az **Elhatárolt bevétel - előfizetés** számlán pedig követel tételként.</span><span class="sxs-lookup"><span data-stu-id="f13a5-118">When you post accrued revenue, the **WIP - subscription** account is debited with the accrual amount, and the **Accrued revenue - subscription** account is credited with the accrual amount.</span></span>

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a><span data-ttu-id="f13a5-119">Az előfizetési bevétel elhatárolására használt számlák beállítása</span><span class="sxs-lookup"><span data-stu-id="f13a5-119">Set up accounts for accrual of subscription revenue</span></span>

1.  <span data-ttu-id="f13a5-120">Kattintson a **Projektvezetés és könyvelés** \> **Beállítás** \> **Feladás** \> **Főkönyvi feladás beállítása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f13a5-120">Click **Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**.</span></span>

2.  <span data-ttu-id="f13a5-121">Kattintson a **Bevételi számlák** lapra, és válassza **Folyamatban lévő munka - előfizetés** vagy **Elhatárolt bevétel - előfizetés** lehetőségre a számlák beállításához.</span><span class="sxs-lookup"><span data-stu-id="f13a5-121">Click the **Revenue accounts** tab, and select **WIP - subscription** or **Accrued revenue - subscription** to set up the accounts.</span></span>

## <a name="subscription-group-setup"></a><span data-ttu-id="f13a5-122">Előfizetési csoport beállítása</span><span class="sxs-lookup"><span data-stu-id="f13a5-122">Subscription group setup</span></span>

<span data-ttu-id="f13a5-123">Ahhoz, hogy az előfizetések bevétele elhatárolható legyen, a **Bevétel elhatárolása** jelölőnégyzetet be kell jelölni.</span><span class="sxs-lookup"><span data-stu-id="f13a5-123">To be able to accrue revenue for subscriptions, the **Accrue revenue** check box must be selected.</span></span> <span data-ttu-id="f13a5-124">Ez annak a csoportnak az **Előfizetési csoportok** lapján található, amely az előfizetéshez kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="f13a5-124">This is found on the **Subscription groups** form for the group that is attached to the subscription.</span></span> <span data-ttu-id="f13a5-125">Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok**.</span><span class="sxs-lookup"><span data-stu-id="f13a5-125">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="enable-revenue-accrual-on-a-subscription-group"></a><span data-ttu-id="f13a5-126">Bevételelhatárolás engedélyezése az előfizetéscsoportokban</span><span class="sxs-lookup"><span data-stu-id="f13a5-126">Enable revenue accrual on a subscription group</span></span>

1.  <span data-ttu-id="f13a5-127">Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok**.</span><span class="sxs-lookup"><span data-stu-id="f13a5-127">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="periods"></a><span data-ttu-id="f13a5-128">Időszakok</span><span class="sxs-lookup"><span data-stu-id="f13a5-128">Periods</span></span>

<span data-ttu-id="f13a5-129">Be kell állítania egy számlázási időszakkódot.</span><span class="sxs-lookup"><span data-stu-id="f13a5-129">You must set up an invoicing period code.</span></span> <span data-ttu-id="f13a5-130">Hacsak nem szeretné a számlázási időszakkal megegyező időintervallumokban elhatárolni a bevételt, be kell állítania egy könyvelési időszakot is.</span><span class="sxs-lookup"><span data-stu-id="f13a5-130">Unless you want to accrue revenue in the same time intervals as you use for invoicing, you must also set up an accrual period.</span></span>

<span data-ttu-id="f13a5-131">A következő táblázat áttekintést ad arról, hogy mely könyvelési időszakokat állíthatja be az egyes számlázási időszakokhoz.</span><span class="sxs-lookup"><span data-stu-id="f13a5-131">The following table provides an overview of which accrual periods can be set up for each invoicing period:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f13a5-132">Számlázási időszak</span><span class="sxs-lookup"><span data-stu-id="f13a5-132">Invoicing period</span></span></p></th>
<th><p><span data-ttu-id="f13a5-133">Könyvelési időszak</span><span class="sxs-lookup"><span data-stu-id="f13a5-133">Accrual period</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f13a5-134"><strong>év</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-134"><strong>Years</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f13a5-135"><strong>év</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-135"><strong>Years</strong></span></span></p></li>
<li><p><span data-ttu-id="f13a5-136"><strong>Negyedév</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-136"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="f13a5-137"><strong>Hónap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-137"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="f13a5-138"><strong>Nap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-138"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13a5-139"><strong>Negyedév</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-139"><strong>Quarter</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f13a5-140"><strong>Negyedév</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-140"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="f13a5-141"><strong>Hónap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-141"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="f13a5-142"><strong>Nap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-142"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13a5-143"><strong>Hónap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-143"><strong>Month</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f13a5-144"><strong>Hónap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-144"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="f13a5-145"><strong>Nap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-145"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13a5-146"><strong>Hét</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-146"><strong>Week</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f13a5-147"><strong>Nap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-147"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13a5-148"><strong>Nap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-148"><strong>Day</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f13a5-149"><strong>Nap</strong></span><span class="sxs-lookup"><span data-stu-id="f13a5-149"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f13a5-150">A számlázási időszak beállítása a teljes előfizetési csoport beállításának kötelező részét képezi.</span><span class="sxs-lookup"><span data-stu-id="f13a5-150">Setting up the invoicing period is a mandatory part of the overall subscription group setup.</span></span> <span data-ttu-id="f13a5-151">Eldöntheti, hogy az előfizetési csoporthoz egy könyvelési időszakot is beállít-e.</span><span class="sxs-lookup"><span data-stu-id="f13a5-151">You can decide whether to also set up an accrual period for the subscription group.</span></span> <span data-ttu-id="f13a5-152">Ha beállít az előfizetési csoporthoz egy könyvelési időszakot, a rendszer ezt az időszakot javasolja az **Időszakkód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f13a5-152">If you set up an accrual period for the subscription group, this period is suggested in the **Period code** field.</span></span> <span data-ttu-id="f13a5-153">Ez a mező az **Előfizetési bevétel könyvelése** oldalon található, amikor könyveli az előfizetési bevételt.</span><span class="sxs-lookup"><span data-stu-id="f13a5-153">This field is found in the **Accrue subscription revenue** form, when you accrue subscription revenue.</span></span> <span data-ttu-id="f13a5-154">A könyvelési időszak viszont csak opcionális információ az előfizetési csoportnál.</span><span class="sxs-lookup"><span data-stu-id="f13a5-154">However, the accrual period is optional information about the subscription group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="f13a5-155">A következő elérési utat használja az <STRONG>Előfizetési bevétel könyvelése</STRONG> oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f13a5-155">Use the following path to open the <STRONG>Accrue subscription revenue</STRONG> form.</span></span> <span data-ttu-id="f13a5-156">Kattintson a következőkre: <STRONG>Szolgáltatáskezelés</STRONG>&gt;<STRONG>Időszakos</STRONG>&gt;<STRONG>Szolgáltatási előfizetések</STRONG>&gt;<STRONG>Előfizetési bevétel könyvelése</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f13a5-156">Click <STRONG>Service management</STRONG> &gt; <STRONG>Periodic</STRONG> &gt; <STRONG>Service subscriptions</STRONG> &gt; <STRONG>Accrue subscription revenue</STRONG>.</span></span></P>


## <a name="transactions"></a><span data-ttu-id="f13a5-157">Tranzakciók</span><span class="sxs-lookup"><span data-stu-id="f13a5-157">Transactions</span></span>

<span data-ttu-id="f13a5-158">Megadhatja az elhatárolt bevétel feladása során létrehozott főkönyvi tranzakciók számát.</span><span class="sxs-lookup"><span data-stu-id="f13a5-158">You can control the number of ledger transactions that are created when you post accrued revenue.</span></span> <span data-ttu-id="f13a5-159">Az előfizetésekkel kapcsolatban határozza meg, hogy a főkönyvi tranzakciók teljes összegként vagy soronként jöjjenek létre.</span><span class="sxs-lookup"><span data-stu-id="f13a5-159">On subscriptions, define if the ledger transactions should be created as a total or per line.</span></span>

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a><span data-ttu-id="f13a5-160">A megjelenítendő feladási részletek szintjének meghatározása elhatárolt tranzakciók esetére</span><span class="sxs-lookup"><span data-stu-id="f13a5-160">Specify the level of posting details to display for accrued transactions</span></span>

1.  <span data-ttu-id="f13a5-161">Kattintson a **Projektvezetés és könyvelés** \> **Beállítás** \> **Projektvezetési és könyvelési paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f13a5-161">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="f13a5-162">A **Pénzügyi** lapon, a **Számla** mezőben válassza ki az **Összesítés** vagy **Sor** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f13a5-162">On the **Financial** tab, in the **Invoice** field, select **Total** or **Line**.</span></span>


## <a name="see-also"></a><span data-ttu-id="f13a5-163">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f13a5-163">See also</span></span>

[<span data-ttu-id="f13a5-164">Előfizetési bevétel könyvelése</span><span class="sxs-lookup"><span data-stu-id="f13a5-164">Accrue subscription revenue</span></span>](accrue-subscription-revenue.md)

  


