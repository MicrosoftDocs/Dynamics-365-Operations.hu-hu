--- 
title: "Beszerzésikategória-hierarchiák irányelveinek beállítása"
description: "A következő lépésekkel egy kategóriába tartozó termékek megrendelésére vonatkozóan állíthat be szabályokat."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f98f5b578c1d01463d196b6018e9f47a9d924be7
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="4aa4d-103">Beszerzésikategória-hierarchiák irányelveinek beállítása</span><span class="sxs-lookup"><span data-stu-id="4aa4d-103">Set up policies for procurement category hierarchies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4aa4d-104">A következő lépésekkel egy kategóriába tartozó termékek megrendelésére vonatkozóan állíthat be szabályokat.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="4aa4d-105">Egy adott beszerzési irányelvhez határozunk meg szabályokat.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="4aa4d-106">A kategória-hozzáférési szabály meghatározza, hogy az alkalmazottaknak igénylések létrehozásakor mely beszerzési kategóriákhoz van hozzáférésük.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="4aa4d-107">Igénylés létrehozásakor a rendszer az alkalmazotthoz tartozó jogi személy és üzemi egység alapján határozza meg, hogy melyik beszerzési irányelvet és kategória-hozzáférési szabályt kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="4aa4d-108">Az USMF bemutatócég adataiban használhatja ezt az eljárást.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="4aa4d-109">Ezt a feladatot általában egy beszerzési vezető végezné el.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="4aa4d-110">Beszerzési irányelv keresése</span><span class="sxs-lookup"><span data-stu-id="4aa4d-110">Find the procurement policy</span></span>
1. <span data-ttu-id="4aa4d-111">Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Irányelvek > Beszerzési irányelvek.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="4aa4d-112">Kattintson az itt lévő hivatkozásra: Beszerzési irányelv USMF irányelv.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="4aa4d-113">Ez az az irányelv, amelyet hozzárendel a szabályhoz.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="4aa4d-114">Aktív irányelvnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="4aa4d-115">Kategória-hozzáférési szabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="4aa4d-115">Create a category access rule</span></span>
1. <span data-ttu-id="4aa4d-116">Válassza ki a Kategóriához való hozzáférés irányelvszabályát.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="4aa4d-117">Ha az Irányelvszabály létrehozása gomb nem működik (halványítva jelenik meg), akkor a Kategóriához való hozzáféréshez már tartozik egy aktív irányelvszabály.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="4aa4d-118">Az Érvényesség dátuma, illetve a Lejárat dátuma mezők segítségével állapítsa meg, hogy melyik az, majd jelölje ki és kattintson az Irányelvszabály kivezetése gombra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="4aa4d-119">Ha rá tud kattintani az Irányelvszabály létrehozása gombra, nincsen teendője.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="4aa4d-120">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="4aa4d-121">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="4aa4d-122">Az idő nem eshet egybe egy már aktív szabállyal.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="4aa4d-123">Válassza ki azt a kategóriát, amelyre a szabályt alkalmazni kívánja.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="4aa4d-124">Jegyezze fel, hogy melyik kategóriáról van szó – később szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="4aa4d-125">Amikor kiválaszt egy kategóriát, annak szülőkategóriája vagy szülőkategóriái is hozzá fog(nak) adódni a Kiválasztott kategóriák listához.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="4aa4d-126">Amennyiben alkalmazni kívánja a szabályt a kijelölt kategória összes alkategóriájára, jelölje be az Alkategóriákkal lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="4aa4d-127">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-127">Click Add.</span></span>
    * <span data-ttu-id="4aa4d-128">Ha az Igen lehetőségre állítja a Fölérendelt szabállyal együtt opciót, a szülőkategóriához meghatározott irányelvszabály az alárendelt kategóriákra is érvényes lesz, amennyiben azokhoz nincs megadva külön irányelvszabály.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="4aa4d-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="4aa4d-130">Kategória-irányelvszabály létrehozása</span><span class="sxs-lookup"><span data-stu-id="4aa4d-130">Create a category policy rule</span></span>
1. <span data-ttu-id="4aa4d-131">Válassza ki a Kategória irányelvszabályát.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="4aa4d-132">Ha az Irányelvszabály létrehozása gomb nem működik (halványítva jelenik meg), válassza ki az aktív irányelvszabályt, majd kattintson az Irányelvszabály kivezetése gombra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="4aa4d-133">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="4aa4d-134">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="4aa4d-135">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-135">Click Add.</span></span>
5. <span data-ttu-id="4aa4d-136">Válassza ki ugyanazt a kategóriát, mint a Kategóriához való hozzáférési szabály esetén.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="4aa4d-137">Válasszon ki egy lehetőséget a Szállító kiválasztása mezőben.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="4aa4d-138">Válasszon ki egy szabályt a kiválasztható szállítók típusának ellenőrzéséhez az igénylések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="4aa4d-139">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-139">Click Close.</span></span>
    * <span data-ttu-id="4aa4d-140">Az így definiált irányelvszabályok Felhasználás típusú igénylésekre érvényesek.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="4aa4d-141">Ha a Feltöltés típusú igénylések irányelveit kívánja meghatározni, „Feltöltési kategória hozzáférési irányelvszabálya” típusú irányelvszabályt kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="4aa4d-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  


