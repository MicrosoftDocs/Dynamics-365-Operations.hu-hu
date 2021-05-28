---
title: Kifizetési díj beállítása TDS-hatósági fizetésekhez
description: Ez a témakör elmagyarázza, hogyan lehet beállítani a forrásnál levont adóért felszámított (TDS) hatósági kifizetéseknél kifizetési díjait.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023313"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a><span data-ttu-id="62015-103">Kifizetési díj beállítása TDS-hatósági fizetésekhez</span><span class="sxs-lookup"><span data-stu-id="62015-103">Set up payment fees for TDS authority payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62015-104">Ez a témakör elmagyarázza, hogyan lehet beállítani a forrásnál levont adóért felszámított (TDS) hatósági kifizetéseknél kifizetési díjait.</span><span class="sxs-lookup"><span data-stu-id="62015-104">This topic explains how to set up payment fees that are charged for Tax Deducted at Source (TDS) authority payments.</span></span>

1. <span data-ttu-id="62015-105">Ugrás a **Kötelezettségek \> Kifizetés beállítása \> Fizetési díj** elemre.</span><span class="sxs-lookup"><span data-stu-id="62015-105">Go to **Accounts payable \> Payment setup \> Payment fee**.</span></span>

    <span data-ttu-id="62015-106">[![Kifizetési díj oldal](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span><span class="sxs-lookup"><span data-stu-id="62015-106">[![Payment fee page](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span></span>

2. <span data-ttu-id="62015-107">Válassza az **Új** lehetőséget, hozzon létre egy kifizetési díjat, majd adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="62015-107">Select **New** to create a payment fee, and enter the required details.</span></span>
3. <span data-ttu-id="62015-108">A **Díj típusa** mezőben válassza ki a kifizetési díj típusát.</span><span class="sxs-lookup"><span data-stu-id="62015-108">In the **Fee type** field, select the type of payment fee:</span></span>

    - <span data-ttu-id="62015-109">**None**</span><span class="sxs-lookup"><span data-stu-id="62015-109">**None**</span></span>
    - <span data-ttu-id="62015-110">**Kamat** – A TDS-hatóság szállítójának teljesített késedelmes fizetések után kamatot számítunk fel.</span><span class="sxs-lookup"><span data-stu-id="62015-110">**Interest** – Interest is charged on late payments that are made to the TDS authority vendor.</span></span>
    - <span data-ttu-id="62015-111">**Egyebek** – A TDS-hatóság szállítójának teljesített késedelmes fizetések után egyéb díjakat számítunk fel.</span><span class="sxs-lookup"><span data-stu-id="62015-111">**Others** – Other charges are charged on late payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="62015-112">Ha a **Kamat** vagy az **Egyéb** lehetőséget választja, a **Költség** mező automatikusan **Főkönyvre** lesz beállítva.</span><span class="sxs-lookup"><span data-stu-id="62015-112">If you select **Interest** or **Others**, the **Charge** field is automatically set to **Ledger**.</span></span>

4. <span data-ttu-id="62015-113">Ha a **Mezőtípus** mezőben a **Kamat** vagy az **Egyebek** lehetőséget választotta, a **Főszámla** mezőben válassza ki a főkönyvszámlát, amire könyvelheti a kamatot vagy az egyéb díjakat.</span><span class="sxs-lookup"><span data-stu-id="62015-113">If you selected **Interest** or **Others** in the **Field type** field, in the **Main account** field, select the ledger account to post the interest or other charges to.</span></span>
5. <span data-ttu-id="62015-114">Adja meg az egyéb szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="62015-114">Enter the other required details.</span></span>
6. <span data-ttu-id="62015-115">A Műveletablakban válassza a **Fizetési díj beállítása** beállítást a **Fizetési díj beállítása** oldal megnyitásához, ahol beállíthatja a fizetési díjakat a bankok különböző kombinációihoz, a fizetési módokhoz, a fizetési előírásokhoz, a pénznemekhez és a dátumintervallumokhoz.</span><span class="sxs-lookup"><span data-stu-id="62015-115">On the Action Pane, select **Payment fee setup** to open the **Payment fee setup** page, where you can set up payment fees for various combinations of banks, methods of payment, payment specifications, currencies, and date intervals.</span></span>

    <span data-ttu-id="62015-116">[![Kifizetési díj beállítása oldal](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span><span class="sxs-lookup"><span data-stu-id="62015-116">[![Payment fee setup page](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span></span>

7. <span data-ttu-id="62015-117">Adja meg a **Csoportosítások** mező **Áttekintés** lapján, hogy mely bankokhoz állítja be a kifizetési díjat:</span><span class="sxs-lookup"><span data-stu-id="62015-117">On the **Overview** tab, in the **Groupings** field, specify which banks you're setting up the payment fee for:</span></span>

    - <span data-ttu-id="62015-118">**Tábla** – Az díj egy adott bankszámlára érvényes.</span><span class="sxs-lookup"><span data-stu-id="62015-118">**Table** – The fee is valid for a specific bank account.</span></span>
    - <span data-ttu-id="62015-119">**Csoport** – A díj egy adott bankcsoportra érvényes.</span><span class="sxs-lookup"><span data-stu-id="62015-119">**Group** – The fee is valid for a specific bank group.</span></span>
    - <span data-ttu-id="62015-120">**Mind** – A díj minden bankszámlára érvényes.</span><span class="sxs-lookup"><span data-stu-id="62015-120">**All** – The fee is valid for all the bank accounts.</span></span>

8. <span data-ttu-id="62015-121">Ha a **Csoportosítások** mezőben a **Tábla** vagy a **Csoport** lehetőséget választotta, akkor a **Bankkapcsolat** mezőben válassza ki azt a bankszámlát vagy bankcsoportot, amely számára beállítja a kifizetési díjat.</span><span class="sxs-lookup"><span data-stu-id="62015-121">If you selected **Table** or **Group** in the **Groupings** field, in the **Bank relation** field, select the specific bank account or bank group that you're setting up the payment fee for.</span></span>
9. <span data-ttu-id="62015-122">A **Kifizetési módszer** mezőben válassza ki kifizetési díjak megfizetésének fizetési módját.</span><span class="sxs-lookup"><span data-stu-id="62015-122">In the **Method of payment** field, select the method of payment for the payment of fees.</span></span>
10. <span data-ttu-id="62015-123">A **Kifizetés meghatározása** mezőben válassza ki vagy írja be a **Kifizetés meghatározása** lapon létrehozott kifizetési előírás kódját.</span><span class="sxs-lookup"><span data-stu-id="62015-123">In the **Payment specification** field, select or enter the payment specification code that was generated on the **Payment specification** page.</span></span>
    - <span data-ttu-id="62015-124">A Fizetési meghatározás a kifizetések elektronikus alapok átutalási módjainak használatos.</span><span class="sxs-lookup"><span data-stu-id="62015-124">The Payment specification is used with electronic fund transfer methods of payment.</span></span>
12. <span data-ttu-id="62015-125">A **Kifizetés pénzneme** mezőben válassza ki a pénznemet, ami aktiválja a díjat.</span><span class="sxs-lookup"><span data-stu-id="62015-125">In the **Payment currency** field, select the currency that activates the fee.</span></span> <span data-ttu-id="62015-126">Csak a kiválasztott pénznemet használó tranzakciók aktiválják a díjat.</span><span class="sxs-lookup"><span data-stu-id="62015-126">Only transactions that use the selected currency can activate the fee.</span></span> <span data-ttu-id="62015-127">Ha üresen hagyja ezt a mezőt, minden pénznem aktiválja a díjat.</span><span class="sxs-lookup"><span data-stu-id="62015-127">If you leave this field blank, all currencies activate the fee.</span></span>
13. <span data-ttu-id="62015-128">A **Százalék/összeg** mezőben válassza ki a számítási módot.</span><span class="sxs-lookup"><span data-stu-id="62015-128">In the **Percentage/Amount** field, select the calculation method.</span></span> <span data-ttu-id="62015-129">A lehetőségek az **Összeg**, a **Százalék** és az **Intervallum**.</span><span class="sxs-lookup"><span data-stu-id="62015-129">The options are **Amount**, **Percent**, and **Interval**.</span></span>
14. <span data-ttu-id="62015-130">A **Díj összege** mezőben adja meg a díj összegét a kifizetés százalékaként vagy egy kifizetés összegeként.</span><span class="sxs-lookup"><span data-stu-id="62015-130">In the **Fee amount** field, specify the fee amount as either a percentage of the payment or the amount for one payment.</span></span>
15. <span data-ttu-id="62015-131">A **Díj pénzneme** mezőben pontosítsa a díj pénznemének kódját.</span><span class="sxs-lookup"><span data-stu-id="62015-131">In the **Fee currency** field, specify the currency code for the fee.</span></span>
16. <span data-ttu-id="62015-132">Válassza az **Általános** lapot a kiválasztott bankszámla részleteinek megtekintéséhez vagy módosításához.</span><span class="sxs-lookup"><span data-stu-id="62015-132">Select the **General** tab to view or modify the details for the selected bank account.</span></span>

    <span data-ttu-id="62015-133">[![Általános fül](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span><span class="sxs-lookup"><span data-stu-id="62015-133">[![General tab](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span></span>

16. <span data-ttu-id="62015-134">A **Minimális** mezőben adja meg azt a minimális tranzakcióösszeget, amely aktiválja a díjat.</span><span class="sxs-lookup"><span data-stu-id="62015-134">In the **Minimum** field, enter the minimum transaction amount that activates the fee.</span></span>
17. <span data-ttu-id="62015-135">A **Maximális** mezőben adja meg azt a maximális tranzakcióösszeget, amely aktiválja a díjat.</span><span class="sxs-lookup"><span data-stu-id="62015-135">In the **Maximum** field, enter the maximum transaction amount that activates the fee.</span></span>
18. <span data-ttu-id="62015-136">A Költségek kiszámításához a **Kezdő dátum** és a **Befejező dátum** mezőkben határozzon meg egy dátumtartományt.</span><span class="sxs-lookup"><span data-stu-id="62015-136">In the **From date** and **To date** fields, define a date range for calculating fees.</span></span>
19. <span data-ttu-id="62015-137">A **Minimális díj** mezőben adja meg a díj összegét a kifizetés százalékaként vagy egy kifizetés összegeként.</span><span class="sxs-lookup"><span data-stu-id="62015-137">In the **Minimum fee** field, specify the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
20. <span data-ttu-id="62015-138">Az **Áfacsoport** mezőben válassza ki az áfa összegének kiszámításához használt áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="62015-138">In the **Sales tax group** field, select the sales tax group to use to calculate the sales tax for the fee amount.</span></span>
21. <span data-ttu-id="62015-139">A **Cikkáfacsoport** mezőben válassza ki a cikkáfa összegének kiszámításához használt áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="62015-139">In the **Item sales tax group** field, select the item sales tax group to use to calculate the item sales tax for the fee amount.</span></span>
22. <span data-ttu-id="62015-140">Válassza ki az **Intervallum** lapot.</span><span class="sxs-lookup"><span data-stu-id="62015-140">Select the **Interval** tab.</span></span> 

    <span data-ttu-id="62015-141">[![Intervallum lap](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span><span class="sxs-lookup"><span data-stu-id="62015-141">[![Interval tab](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span></span>

23. <span data-ttu-id="62015-142">A **Napok** mezőben adja meg a kifizetés feladási dátuma (engedményezés dátuma) és a kötelezvény határideje között eltelt napok számát.</span><span class="sxs-lookup"><span data-stu-id="62015-142">In the **Days** field, enter the number of days between the posting date (discounting date) of the payment and the due date of the promissory note.</span></span>
24. <span data-ttu-id="62015-143">A **Százalék/Összeg** mezőben adja meg, hogy százalék vagy meghatározott összeg-e a meghatározás.</span><span class="sxs-lookup"><span data-stu-id="62015-143">In the **Percentage/Amount** field, select whether the specification is a percentage or a set amount.</span></span>
25. <span data-ttu-id="62015-144">A **Díj összege** mezőben adja meg a díj összegét a kifizetés százalékaként vagy egy kifizetés összegeként.</span><span class="sxs-lookup"><span data-stu-id="62015-144">In the **Fee amount** field, enter the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
26. <span data-ttu-id="62015-145">Zárja be a **Kifizetési díj beállítása** lapot.</span><span class="sxs-lookup"><span data-stu-id="62015-145">Close the **Payment fee setup** page.</span></span>
27. <span data-ttu-id="62015-146">Zárja be a **Kifizetési díj** lapot.</span><span class="sxs-lookup"><span data-stu-id="62015-146">Close the **Payment fee** page.</span></span>
