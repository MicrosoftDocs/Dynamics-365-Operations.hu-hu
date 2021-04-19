---
title: Áfa-hozzárendelés és felülbírálások
description: Ez az eljárás bemutatja, hogyan lehet áfacsoportokat társítani kereskedelmi csatornákhoz.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 28d393dcf727eec7211f6092ea67de2b85359f1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811942"
---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="3ae08-103">Áfa-hozzárendelés és felülbírálások</span><span class="sxs-lookup"><span data-stu-id="3ae08-103">Sales tax assignment and overrides</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ae08-104">Ez az eljárás bemutatja, hogyan lehet áfacsoportokat társítani kereskedelmi csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="3ae08-104">This procedure demonstrates how to assign sales tax groups to commerce channels.</span></span> <span data-ttu-id="3ae08-105">Emellett az új áfafelülírás létrehozásának és annak meglévő áfafelülírás csoporthoz rendelésének folyamatán is végig vezet.</span><span class="sxs-lookup"><span data-stu-id="3ae08-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="3ae08-106">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="3ae08-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="3ae08-107">Ugorjon a következő oldalra: Retail és Commerce > Csatornák > Üzletek > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="3ae08-107">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="3ae08-108">A listában kattintson a „Houston”-hoz tartozó csatornaazonosítóra.</span><span class="sxs-lookup"><span data-stu-id="3ae08-108">In the list, click the Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="3ae08-109">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3ae08-109">Click Edit.</span></span>
    * <span data-ttu-id="3ae08-110">Az „Áfa csoport” mező tartalmazza az aktuális céghez kapcsolódó áfa csoportok listáját.</span><span class="sxs-lookup"><span data-stu-id="3ae08-110">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="3ae08-111">Az aktuálisan hozzárendelt csoport egy általános „Texas” áfacsoport.</span><span class="sxs-lookup"><span data-stu-id="3ae08-111">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="3ae08-112">Vannak áfacsoportok „Washington”-hoz és „Washington, King County”-hoz is.</span><span class="sxs-lookup"><span data-stu-id="3ae08-112">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="3ae08-113">Az áfacsoportok több közigazgatási terület adóit is tartalmazhatják.</span><span class="sxs-lookup"><span data-stu-id="3ae08-113">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="3ae08-114">Az „Áfa felülírás” mező az, ahol az áfa-felülírási csoport csatornához rendelhető.</span><span class="sxs-lookup"><span data-stu-id="3ae08-114">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="3ae08-115">Az áfa-felülírási csoportok használhatók olyan áfafelülírások csoportosítására, amik több üzletre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="3ae08-115">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="3ae08-116">Ahelyett hogy egyesével, manuálisan rendelné össze az áfafelülírásokat, létrehozhat egy csoportot, amit közvetlenül a csatornákhoz rendelhet, így időt takaríthat meg.</span><span class="sxs-lookup"><span data-stu-id="3ae08-116">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="3ae08-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3ae08-117">Click Save.</span></span>
5. <span data-ttu-id="3ae08-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3ae08-118">Close the page.</span></span>
6. <span data-ttu-id="3ae08-119">Menjen a Retail and Commerce > Csatorna beállítása > Áfák > Áfafelülírások lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3ae08-119">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="3ae08-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3ae08-120">Click New.</span></span>
8. <span data-ttu-id="3ae08-121">Az Áfafelülírás mezőbe írja be az ön felülírásának nevét.</span><span class="sxs-lookup"><span data-stu-id="3ae08-121">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="3ae08-122">a Leírása mezőbe adja meg a felülírás leírását.</span><span class="sxs-lookup"><span data-stu-id="3ae08-122">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="3ae08-123">Állítsa az állapotot „Engedélyezett”-re.</span><span class="sxs-lookup"><span data-stu-id="3ae08-123">Set the status to "Enable."</span></span>
11. <span data-ttu-id="3ae08-124">Bontsa ki vagy zárja be Felülírás részt.</span><span class="sxs-lookup"><span data-stu-id="3ae08-124">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="3ae08-125">A Típus mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3ae08-125">In the Type field, select an option.</span></span>
    * <span data-ttu-id="3ae08-126">A cikkek áfa csoportjai használhatóak konkrét cikkek áfáinak felülírásához, amennyiben azok a csoportba tartoznak.</span><span class="sxs-lookup"><span data-stu-id="3ae08-126">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="3ae08-127">Például, az élelmiszerek tipikusan eltérő áfával rendelkeznek a fizikai árukhoz képest, így valószínűleg érdemes saját áfacsoportba sorolni őket.</span><span class="sxs-lookup"><span data-stu-id="3ae08-127">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span> <span data-ttu-id="3ae08-128">Az áfacsoportok adók csoportjai, amely az adott csatornára használhatóak.</span><span class="sxs-lookup"><span data-stu-id="3ae08-128">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="3ae08-129">Ha például a csatorna értékesít kiskereskedelemben és vállalkozástól-vállalkozásnak is, akkor különböző cikkáfacsoportok használhatóak.</span><span class="sxs-lookup"><span data-stu-id="3ae08-129">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="3ae08-130">Minden alkalmazható adót az áfacsoporthoz kell rendelni.</span><span class="sxs-lookup"><span data-stu-id="3ae08-130">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="3ae08-131">Most kiválaszthatja a „Kezdő” és „Végző” adókat vagy kiválaszthatja a „Adócsoportból” és „Adócsoportig”, hogy létrehozza az ön adófelülírását.</span><span class="sxs-lookup"><span data-stu-id="3ae08-131">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span> <span data-ttu-id="3ae08-132">A "Kezdő" mező mutatja a felülírandó adót vagy adócsoportot.</span><span class="sxs-lookup"><span data-stu-id="3ae08-132">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="3ae08-133">A Cikk áfacsoport szerinti felülírás eltérő lehetőségeket biztosít, az áfacsoporttal történő felülíráshoz képest.</span><span class="sxs-lookup"><span data-stu-id="3ae08-133">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span> <span data-ttu-id="3ae08-134">A Áfafelülírások beállíthatók egész tranzakciók áfa felülírására, vagy a tranzakció megadott soraira.</span><span class="sxs-lookup"><span data-stu-id="3ae08-134">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="3ae08-135">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3ae08-135">Click Save.</span></span>
14. <span data-ttu-id="3ae08-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3ae08-136">Close the page.</span></span>
15. <span data-ttu-id="3ae08-137">Menjen a Retail és Commerce > Csatorna beállítása > Áfák > Áfafelülírás csoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3ae08-137">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="3ae08-138">Ebben a lépésben az újonnan létrehozott áfafelülírást fogja hozzárendelni a Houston csatornához rendelt áfa-felülírási csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="3ae08-138">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="3ae08-139">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3ae08-139">Click Edit.</span></span>
17. <span data-ttu-id="3ae08-140">Bontsa ki vagy csukja össze a Beállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3ae08-140">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="3ae08-141">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="3ae08-141">Click Add.</span></span>
19. <span data-ttu-id="3ae08-142">Az Áfacsoport felülírás mezőben kattintson a legördítő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3ae08-142">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="3ae08-143">Válassza ki a korábban létrehozott áfafelülírást a listából.</span><span class="sxs-lookup"><span data-stu-id="3ae08-143">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="3ae08-144">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3ae08-144">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="3ae08-145">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3ae08-145">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]