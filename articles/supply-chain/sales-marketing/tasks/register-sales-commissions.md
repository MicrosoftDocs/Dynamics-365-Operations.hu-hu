---
title: Értékesítési jutalékok regisztrálása
description: Ez a témakör az értékesítési jutalékok számításának és regisztrálásának módját mutatja be.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83cea952f4883d49621a9f7d16440927a8eddb98
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830561"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="72c83-103">Értékesítési jutalékok regisztrálása</span><span class="sxs-lookup"><span data-stu-id="72c83-103">Register sales commissions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72c83-104">Ez a témakör az értékesítési jutalékok számításának és regisztrálásának módját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="72c83-104">This topic explains how sales commissions are calculated and registered.</span></span> <span data-ttu-id="72c83-105">Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.</span><span class="sxs-lookup"><span data-stu-id="72c83-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="72c83-106">Mielőtt elindítaná az útmutatót, az „Értékesítési jutalékok szabályainak beállítása” című segédlet futtatásával győződjön meg, hogy rendelkezik az összes szükséges jutalékszámítási beállítással.</span><span class="sxs-lookup"><span data-stu-id="72c83-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="72c83-107">Jegyezze fel a jutalékfolyamathoz kiválasztott vevő és cikkszámokat, majd használja ezeket ebben az útmutatóban a megfelelő helyen értékesítési rendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="72c83-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="72c83-108">Számlázzon egy értékesítési rendelést, amely lehetővé teszi egy értékesítőnek a jutalékot</span><span class="sxs-lookup"><span data-stu-id="72c83-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="72c83-109">A navigációs ablakban ugorjon a **Modulok > Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="72c83-109">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="72c83-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-110">Select **New**.</span></span>
3. <span data-ttu-id="72c83-111">A **Vevői számla** mező legördülő listájából válassza ki a kívánt rekordot.</span><span class="sxs-lookup"><span data-stu-id="72c83-111">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="72c83-112">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-112">Select **OK**.</span></span>
5. <span data-ttu-id="72c83-113">A műveleti ablaktáblán válassza ki a **Beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="72c83-113">On the Action Pane, select **Options**.</span></span>
6. <span data-ttu-id="72c83-114">Válassza ki a **Nézetváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-114">Select **Change view**.</span></span>
7. <span data-ttu-id="72c83-115">Válassza ki a **Fejlécnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="72c83-115">Select **Header view**.</span></span>
8. <span data-ttu-id="72c83-116">Bontsa ki a **Beállítások** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="72c83-116">Expand the **Setup** section.</span></span>

    - <span data-ttu-id="72c83-117">Az **Értékesítési csoport** mező értéke a csoportot jellemzi egy vagy több hozzárendelt értékesítővel.</span><span class="sxs-lookup"><span data-stu-id="72c83-117">The value in the **Sales group** field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="72c83-118">Az a csoport tagjai kapják jutalékokat a rendelés számlázásakor, előre megadott szorzók és elosztás szerint.</span><span class="sxs-lookup"><span data-stu-id="72c83-118">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   
    - <span data-ttu-id="72c83-119">Az érték a vevőkártyáról másolódik, de megváltoztatható.</span><span class="sxs-lookup"><span data-stu-id="72c83-119">The value is copied from the Customer card, but you can change it if you wish.</span></span>  
    - <span data-ttu-id="72c83-120">Az Értékesítési csoport is az értékesítési rendelés sorba másolódik.</span><span class="sxs-lookup"><span data-stu-id="72c83-120">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="72c83-121">Meg lehet változtatni, így az eltérő lehet a fejlécben és/vagy a sorok között megadottól.</span><span class="sxs-lookup"><span data-stu-id="72c83-121">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    - <span data-ttu-id="72c83-122">A **Jutalékcsoport** mezőjének értéke azt a csoportot jelöli, amelyet egy vagy több vevő jutalékénak követése céljából hozott létre.</span><span class="sxs-lookup"><span data-stu-id="72c83-122">The value in the **Commission group** field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   
    - <span data-ttu-id="72c83-123">Az érték a vevőkártyáról másolódik, de megváltoztatható.</span><span class="sxs-lookup"><span data-stu-id="72c83-123">The value is copied from the Customer card, but you can change it if you wish.</span></span>   

9. <span data-ttu-id="72c83-124">A műveleti ablaktáblán válassza ki a **Beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="72c83-124">On the Action Pane, select **Options**.</span></span>
10. <span data-ttu-id="72c83-125">Válassza ki a **Nézetváltás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-125">Select **Change view**.</span></span>
11. <span data-ttu-id="72c83-126">Válassza ki a **Sorokat megjelenítő nézet** elemre.</span><span class="sxs-lookup"><span data-stu-id="72c83-126">Select **Line view**.</span></span>
12. <span data-ttu-id="72c83-127">A **Cikkszám** mező legördülő listájában válassza ki a jutalékokhoz beállított elemet.</span><span class="sxs-lookup"><span data-stu-id="72c83-127">In the drop down menu of the **Item number** field, select the item you have set up for commissions.</span></span> 
13. <span data-ttu-id="72c83-128">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="72c83-128">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="72c83-129">Jegyezze fel a sor Nettó összegét.</span><span class="sxs-lookup"><span data-stu-id="72c83-129">Take note of the line's Net amount.</span></span> <span data-ttu-id="72c83-130">Az értékesítési bevétel összegét jelöli, amely ebben a példában a jutalékszámítás alapja.</span><span class="sxs-lookup"><span data-stu-id="72c83-130">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
14. <span data-ttu-id="72c83-131">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-131">Select **Save**.</span></span>
15. <span data-ttu-id="72c83-132">A műveleti ablaktáblán válassza ki a **Számla** elemet.</span><span class="sxs-lookup"><span data-stu-id="72c83-132">On the Action Pane, select **Invoice**.</span></span>
16. <span data-ttu-id="72c83-133">Válassza ki a **Számla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-133">Select **Invoice**.</span></span>
17. <span data-ttu-id="72c83-134">Bontsa ki a **Paraméterek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="72c83-134">Expand the **Parameters** section.</span></span>
18. <span data-ttu-id="72c83-135">A **Mennyiség** mezőben válassza a **Mind** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-135">In the **Quantity** field, select **All**.</span></span>
19. <span data-ttu-id="72c83-136">Válassza ki az **Igen** lehetőséget a **Feladás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="72c83-136">Select **Yes** in the **Posting** field.</span></span>
20. <span data-ttu-id="72c83-137">Válassza ki az **OK** lehetőséget, majd ismét az **OK** lehetőséget a következő ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="72c83-137">Select **OK**, then select **OK** in the next pane.</span></span> <span data-ttu-id="72c83-138">A tranzakció feladása körülbelül egy percet vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="72c83-138">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="72c83-139">Engedélyezze a folyamat befejezését és ne zárja be az ablakot.</span><span class="sxs-lookup"><span data-stu-id="72c83-139">Allow the processing to complete and don't close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="72c83-140">A regisztrált értékesítési jutalékok áttekintése</span><span class="sxs-lookup"><span data-stu-id="72c83-140">Review the registered sales commissions</span></span>
1. <span data-ttu-id="72c83-141">A műveleti ablaktáblán válassza ki a **Számla**, majd ismét a **Számla** elemet.</span><span class="sxs-lookup"><span data-stu-id="72c83-141">On the Action Pane, select **Invoice**, then select **Invoice** again.</span></span>
2. <span data-ttu-id="72c83-142">A műveleti ablaktáblán válassza ki a **Számla**, majd a **Jutaléktranzakciók** elemet.</span><span class="sxs-lookup"><span data-stu-id="72c83-142">On the Action Pane, select **Invoice**, then select **Commission transactions**.</span></span>

    - <span data-ttu-id="72c83-143">Az **Áttekintés** lap megjeleníti a számlázott értékesítési megrendeléshez társított értékesítőknek kifizethető jutalék összegeit jelölő sorokat.</span><span class="sxs-lookup"><span data-stu-id="72c83-143">The **Overview** tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="72c83-144">Most ellenőrizze a részleteket.</span><span class="sxs-lookup"><span data-stu-id="72c83-144">Let's review the details.</span></span>  
    - <span data-ttu-id="72c83-145">Ha az „Értékesítési jutalékok szabályainak beállítása” útmutatót használta a **Jutalék értékesítési csoportja** beállításához, két ember kapja az értékesítési jutalékokat, és a jutalék egyenlően oszlik el közöttük.</span><span class="sxs-lookup"><span data-stu-id="72c83-145">If you used the "Set up sales commission rules" guide to set up the **Commission sales** group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    - <span data-ttu-id="72c83-146">Ebben a példában a jutalék teljes összege az értékesítési bevétel (a rendelési sor nettó összege) százalékában számolt.</span><span class="sxs-lookup"><span data-stu-id="72c83-146">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>  
3. <span data-ttu-id="72c83-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="72c83-147">Close the page.</span></span>
4. <span data-ttu-id="72c83-148">Válassza ki a **Bizonylat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="72c83-148">Select **Voucher**.</span></span> <span data-ttu-id="72c83-149">Ellenőrizheti a bizonylat tranzakciókat az előre megadott jutalék költséghez és jutalék fizethető számlához feladott jutalék összegekhez.</span><span class="sxs-lookup"><span data-stu-id="72c83-149">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  

