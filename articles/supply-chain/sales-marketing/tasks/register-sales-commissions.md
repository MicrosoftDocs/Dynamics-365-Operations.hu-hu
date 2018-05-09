--- 
title: "Értékesítési jutalékok regisztrálása"
description: "Ez az eljárás bemutatja az értékesítési jutalék számítását és regisztrálását."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0fad3c62f926e508e09a265a600194b7ea595bf0
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="register-sales-commissions"></a><span data-ttu-id="8af8c-103">Értékesítési jutalékok regisztrálása</span><span class="sxs-lookup"><span data-stu-id="8af8c-103">Register sales commissions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8af8c-104">Ez az eljárás bemutatja az értékesítési jutalék számítását és regisztrálását.</span><span class="sxs-lookup"><span data-stu-id="8af8c-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="8af8c-105">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="8af8c-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="8af8c-106">Mielőtt elindítaná az útmutatót, az „Értékesítési jutalékok szabályainak beállítása” című segédlet futtatásával győződjön meg, hogy rendelkezik az összes szükséges jutalékszámítási beállítással.</span><span class="sxs-lookup"><span data-stu-id="8af8c-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="8af8c-107">Jegyezze fel a jutalékfolyamathoz kiválasztott vevő és cikkszámokat, majd használja ezeket ebben az útmutatóban a megfelelő helyen értékesítési rendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="8af8c-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="8af8c-108">Számlázzon egy értékesítési rendelést, amely lehetővé teszi egy értékesítőnek a jutalékot</span><span class="sxs-lookup"><span data-stu-id="8af8c-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="8af8c-109">Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.</span><span class="sxs-lookup"><span data-stu-id="8af8c-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="8af8c-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-110">Click New.</span></span>
3. <span data-ttu-id="8af8c-111">A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8af8c-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8af8c-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8af8c-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="8af8c-113">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8af8c-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8af8c-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8af8c-114">Click OK.</span></span>
7. <span data-ttu-id="8af8c-115">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="8af8c-116">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-116">Click Change view.</span></span>
9. <span data-ttu-id="8af8c-117">Kattintson a Fejlécnézet gombra.</span><span class="sxs-lookup"><span data-stu-id="8af8c-117">Click Header view.</span></span>
10. <span data-ttu-id="8af8c-118">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8af8c-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="8af8c-119">Az értékesítési csoport mező értéke a csoportot jellemzi, egy, vagy több hozzárendelt üzletkötővel.</span><span class="sxs-lookup"><span data-stu-id="8af8c-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="8af8c-120">Az a csoport tagjai kapják jutalékokat a rendelés számlázásakor, előre megadott szorzók és elosztás szerint.</span><span class="sxs-lookup"><span data-stu-id="8af8c-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="8af8c-121">Az érték a vevőkártyáról másolódik, de megváltoztatható.</span><span class="sxs-lookup"><span data-stu-id="8af8c-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="8af8c-122">Az Értékesítési csoport is az értékesítési rendelés sorba másolódik.</span><span class="sxs-lookup"><span data-stu-id="8af8c-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="8af8c-123">Meg lehet változtatni, így az eltérő lehet a fejlécben és/vagy a sorok között megadottól.</span><span class="sxs-lookup"><span data-stu-id="8af8c-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="8af8c-124">A Jutalék csoport mezőjének értéke jelöli a csoportot, amelynek a célja egy vagy több vevő jutalékénak követése.</span><span class="sxs-lookup"><span data-stu-id="8af8c-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="8af8c-125">Az érték a vevőkártyáról másolódik, de megváltoztatható.</span><span class="sxs-lookup"><span data-stu-id="8af8c-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="8af8c-126">A Művelet ablaktáblában kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="8af8c-127">Kattintson a Nézetváltás elemre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-127">Click Change view.</span></span>
13. <span data-ttu-id="8af8c-128">Kattintson a Sor nézetre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-128">Click Line view.</span></span>
14. <span data-ttu-id="8af8c-129">A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8af8c-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="8af8c-130">A listában válassza ki a cikket, amelyet a jutalékokhoz állított be.</span><span class="sxs-lookup"><span data-stu-id="8af8c-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="8af8c-131">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="8af8c-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8af8c-132">Jegyezze fel a sor Nettó összegét.</span><span class="sxs-lookup"><span data-stu-id="8af8c-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="8af8c-133">Az értékesítési bevétel összegét jelöli, amely ebben a példában a jutalékszámítás alapja.</span><span class="sxs-lookup"><span data-stu-id="8af8c-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="8af8c-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8af8c-134">Click Save.</span></span>
18. <span data-ttu-id="8af8c-135">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="8af8c-136">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-136">Click Invoice.</span></span>
20. <span data-ttu-id="8af8c-137">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8af8c-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="8af8c-138">A Mennyiség mezőben válassza a „Mind” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af8c-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="8af8c-139">Válassza ki az Igen lehetőséget a Feladás mezőben.</span><span class="sxs-lookup"><span data-stu-id="8af8c-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="8af8c-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8af8c-140">Click OK.</span></span>
24. <span data-ttu-id="8af8c-141">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8af8c-141">Click OK.</span></span>
    * <span data-ttu-id="8af8c-142">A tranzakció feladása körülbelül egy percet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="8af8c-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="8af8c-143">Engedélyezze a folyamat befejezését és ne zárja be az ablakot.</span><span class="sxs-lookup"><span data-stu-id="8af8c-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="8af8c-144">A regisztrált értékesítési jutalékok áttekintése</span><span class="sxs-lookup"><span data-stu-id="8af8c-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="8af8c-145">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="8af8c-146">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-146">Click Invoice.</span></span>
3. <span data-ttu-id="8af8c-147">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="8af8c-148">Kattintson a Jutaléktranzakciókra.</span><span class="sxs-lookup"><span data-stu-id="8af8c-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="8af8c-149">Az Áttekintés lap a számlázott értékesítési megrendeléshez társított üzletkötőknek kifizethető jutalék összegeket jelölő sorokat mutat.</span><span class="sxs-lookup"><span data-stu-id="8af8c-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="8af8c-150">Most ellenőrizze a részleteket.</span><span class="sxs-lookup"><span data-stu-id="8af8c-150">Let's review the details.</span></span>     
    * <span data-ttu-id="8af8c-151">Ha az „Értékesítési jutalékok szabályainak beállítása” útmutatót használta a Jutalék értékesítési csoport beállításához, két ember kapja az értékesítési jutalékokat, és a jutalék egyenlően oszlik el közöttük.</span><span class="sxs-lookup"><span data-stu-id="8af8c-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="8af8c-152">Ebben a példában a jutalék teljes összege az értékesítési bevétel (a rendelési sor nettó összege) százalékában számolt.</span><span class="sxs-lookup"><span data-stu-id="8af8c-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="8af8c-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8af8c-153">Close the page.</span></span>
6. <span data-ttu-id="8af8c-154">Kattintson a Bizonylat elemre.</span><span class="sxs-lookup"><span data-stu-id="8af8c-154">Click Voucher.</span></span>
    * <span data-ttu-id="8af8c-155">Ellenőrizheti a bizonylat tranzakciókat az előre megadott jutalék költséghez és jutalék fizethető számlához feladott jutalék összegekhez.</span><span class="sxs-lookup"><span data-stu-id="8af8c-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  


