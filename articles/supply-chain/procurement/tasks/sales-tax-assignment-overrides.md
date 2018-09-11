--- 
title: "Áfa-hozzárendelés és felülbírálások"
description: "Ez az eljárás bemutatja, hogyan lehet áfacsoportokat társítani kiskereskedelmi csatornákhoz."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 2420dceeb321ed11dbf6d7d9c09e3a579d65134c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/11/2018

---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="5fe24-103">Áfa-hozzárendelés és felülbírálások</span><span class="sxs-lookup"><span data-stu-id="5fe24-103">Sales tax assignment and overrides</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5fe24-104">Ez az eljárás bemutatja, hogyan lehet áfacsoportokat társítani kiskereskedelmi csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="5fe24-104">This procedure demonstrates how to assign sales tax groups to retail channels.</span></span> <span data-ttu-id="5fe24-105">Emellett az új áfafelülírás létrehozásának és annak meglévő áfafelülírás csoporthoz rendelésének folyamatán is végig vezet.</span><span class="sxs-lookup"><span data-stu-id="5fe24-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="5fe24-106">Az eljárás</span><span class="sxs-lookup"><span data-stu-id="5fe24-106">This procedure</span></span>

<span data-ttu-id="5fe24-107">az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="5fe24-107">uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5fe24-108">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="5fe24-108">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="5fe24-109">A listában kattintson a „Houston”-hoz tartozó Kiskereskedelmi csatorna azonosítóra.</span><span class="sxs-lookup"><span data-stu-id="5fe24-109">In the list, click the Retail Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="5fe24-110">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe24-110">Click Edit.</span></span>
    * <span data-ttu-id="5fe24-111">Az „Áfa csoport” mező tartalmazza az aktuális céghez kapcsolódó áfa csoportok listáját.</span><span class="sxs-lookup"><span data-stu-id="5fe24-111">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="5fe24-112">Az aktuálisan hozzárendelt csoport egy általános „Texas” áfacsoport.</span><span class="sxs-lookup"><span data-stu-id="5fe24-112">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="5fe24-113">Vannak áfacsoportok „Washington”-hoz és „Washington, King County”-hoz is.</span><span class="sxs-lookup"><span data-stu-id="5fe24-113">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="5fe24-114">Az áfacsoportok több közigazgatási terület adóit is tartalmazhatják.</span><span class="sxs-lookup"><span data-stu-id="5fe24-114">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="5fe24-115">Az „Áfa felülírás” mező az, ahol az áfa-felülírási csoport csatornához rendelhető.</span><span class="sxs-lookup"><span data-stu-id="5fe24-115">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="5fe24-116">Az áfa-felülírási csoportok használhatók olyan áfafelülírások csoportosítására, amik több üzletre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="5fe24-116">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="5fe24-117">Ahelyett hogy egyesével, manuálisan rendelné össze az áfafelülírásokat, létrehozhat egy csoportot, amit közvetlenül a csatornákhoz rendelhet, így időt takaríthat meg.</span><span class="sxs-lookup"><span data-stu-id="5fe24-117">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="5fe24-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe24-118">Click Save.</span></span>
5. <span data-ttu-id="5fe24-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5fe24-119">Close the page.</span></span>
6. <span data-ttu-id="5fe24-120">Menjen a Kiskereskedelmi és kereskedelem > Csatorna-beállítás > Forgalmi adók > Áfafelülírások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe24-120">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="5fe24-121">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe24-121">Click New.</span></span>
8. <span data-ttu-id="5fe24-122">Az Áfafelülírás mezőbe írja be az ön felülírásának nevét.</span><span class="sxs-lookup"><span data-stu-id="5fe24-122">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="5fe24-123">a Leírása mezőbe adja meg a felülírás leírását.</span><span class="sxs-lookup"><span data-stu-id="5fe24-123">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="5fe24-124">Állítsa az állapotot „Engedélyezett”-re.</span><span class="sxs-lookup"><span data-stu-id="5fe24-124">Set the status to "Enable."</span></span>
11. <span data-ttu-id="5fe24-125">Bontsa ki vagy zárja be Felülírás részt.</span><span class="sxs-lookup"><span data-stu-id="5fe24-125">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="5fe24-126">A Típus mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5fe24-126">In the Type field, select an option.</span></span>
    * <span data-ttu-id="5fe24-127">A cikkek áfa csoportjai használhatóak konkrét cikkek áfáinak felülírásához, amennyiben azok a csoportba tartoznak.</span><span class="sxs-lookup"><span data-stu-id="5fe24-127">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="5fe24-128">Például, az élelmiszerek tipikusan eltérő áfával rendelkeznek a fizikai árukhoz képest, így valószínűleg érdemes saját áfacsoportba sorolni őket.</span><span class="sxs-lookup"><span data-stu-id="5fe24-128">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span>     <span data-ttu-id="5fe24-129">Az áfacsoportok adók csoportjai, amely az adott csatornára használhatóak.</span><span class="sxs-lookup"><span data-stu-id="5fe24-129">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="5fe24-130">Ha például a csatorna értékesít kiskereskedelemben és vállalkozástól-vállalkozásnak is, akkor különböző cikkáfacsoportok használhatóak.</span><span class="sxs-lookup"><span data-stu-id="5fe24-130">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="5fe24-131">Minden alkalmazható adót az áfacsoporthoz kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="5fe24-131">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="5fe24-132">Most kiválaszthatja a „Kezdő” és „Végző” adókat vagy kiválaszthatja a „Adócsoportból” és „Adócsoportig”, hogy létrehozza az ön adófelülírását.</span><span class="sxs-lookup"><span data-stu-id="5fe24-132">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span>    <span data-ttu-id="5fe24-133">A "Kezdő" mező mutatja a felülírandó adót vagy adócsoportot.</span><span class="sxs-lookup"><span data-stu-id="5fe24-133">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="5fe24-134">A Cikk áfacsoport szerinti felülírás eltérő lehetőségeket biztosít, az áfacsoporttal történő felülíráshoz képest.</span><span class="sxs-lookup"><span data-stu-id="5fe24-134">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span>    <span data-ttu-id="5fe24-135">A Áfafelülírások beállíthatók egész tranzakciók áfa felülírására, vagy a tranzakció megadott soraira.</span><span class="sxs-lookup"><span data-stu-id="5fe24-135">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="5fe24-136">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe24-136">Click Save.</span></span>
14. <span data-ttu-id="5fe24-137">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5fe24-137">Close the page.</span></span>
15. <span data-ttu-id="5fe24-138">Menjen a Kiskereskedelmi és kereskedelem > Csatorna-beállítás > Forgalmi adók > Áfafelülírás csoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe24-138">Go to Retail and commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="5fe24-139">Ebben a lépésben az újonnan létrehozott áfafelülírást fogja hozzárendelni a Houston csatornához rendelt áfa-felülírási csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="5fe24-139">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="5fe24-140">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5fe24-140">Click Edit.</span></span>
17. <span data-ttu-id="5fe24-141">Bontsa ki vagy csukja össze a Beállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5fe24-141">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="5fe24-142">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe24-142">Click Add.</span></span>
19. <span data-ttu-id="5fe24-143">Az Áfacsoport felülírás mezőben kattintson a legördítő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5fe24-143">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="5fe24-144">Válassza ki a korábban létrehozott áfafelülírást a listából.</span><span class="sxs-lookup"><span data-stu-id="5fe24-144">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="5fe24-145">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5fe24-145">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="5fe24-146">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5fe24-146">Click Save.</span></span>


