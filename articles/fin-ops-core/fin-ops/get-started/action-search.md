---
title: Műveletkeresés
description: Ez a cikk a művelet keresési funkciót ismerteti. A műveletkeresés segít megkeresni és adott lapon lefuttatni műveleteket.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb268c2643b45f6797793dbc5b7cc2e33d5218d9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564214"
---
# <a name="action-search"></a><span data-ttu-id="de291-104">Műveletkeresés</span><span class="sxs-lookup"><span data-stu-id="de291-104">Action search</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de291-105">Ez a cikk a művelet keresési funkciót ismerteti.</span><span class="sxs-lookup"><span data-stu-id="de291-105">This article describes the action search functionality.</span></span> <span data-ttu-id="de291-106">A műveletkeresés segít megkeresni és adott lapon lefuttatni műveleteket.</span><span class="sxs-lookup"><span data-stu-id="de291-106">Action search will help you find and run actions on a page.</span></span>

## <a name="introduction"></a><span data-ttu-id="de291-107">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="de291-107">Introduction</span></span>

<span data-ttu-id="de291-108">Az oldalakon az utasítások elsősorban a műveletpaneleken láthatók, egyrészt az oldal tetején megjelenő normál műveletpanelen, és az oldal különböző szakaszaiban megjelenő eszköztárakon.</span><span class="sxs-lookup"><span data-stu-id="de291-108">Pages primarily expose commands on Action Panes, both the standard Action Pane that appears at the top of a page and the toolbars that appear in various sections of the page.</span></span> <span data-ttu-id="de291-109">A korábbi verziókban a billentyűtippek szolgáltatás lehetővé tette a műveletpanel bármely gombjának gyors elérését az Alt billentyű, majd egy betűsorozat lenyomásával.</span><span class="sxs-lookup"><span data-stu-id="de291-109">In previous versions, a Key Tips feature let you quickly access any button on an Action Pane by pressing the Alt key and then a series of letters.</span></span>

<span data-ttu-id="de291-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span><span class="sxs-lookup"><span data-stu-id="de291-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span></span>

<span data-ttu-id="de291-111">A műveletkeresés funkció a billentyűparancs-tippeket helyettesíti, amelyek már nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="de291-111">The action search feature replaces Key Tips, which are no longer available.</span></span> <span data-ttu-id="de291-112">Ez az új funkció lehetővé teszi, hogy gyorsan megkeressen és működtessen egy gombot bármelyik látható műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="de291-112">This new feature lets you quickly search for and run a button from any visible Action Pane.</span></span>

## <a name="using-action-search"></a><span data-ttu-id="de291-113">A műveletkeresés használatával</span><span class="sxs-lookup"><span data-stu-id="de291-113">Using action search</span></span>

<span data-ttu-id="de291-114">A műveletkeresési funkció használatához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="de291-114">To use the action search feature, follow these steps.</span></span>

1. <span data-ttu-id="de291-115">A műveleti ablaktáblán kattintson a **műveletkeresés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="de291-115">On the Action Pane, click in the **action search** field.</span></span> <span data-ttu-id="de291-116">(A **műveletkeresés** mező egy nagyítóüveget ábrázoló ikont tartalmaz.)</span><span class="sxs-lookup"><span data-stu-id="de291-116">(The **action search** field contains a magnifying glass icon.)</span></span>
2. <span data-ttu-id="de291-117">Írja be a futtatni kívánt gomb nevének egy részét vagy egészét.</span><span class="sxs-lookup"><span data-stu-id="de291-117">Type all or part of the name of the button that you want to run.</span></span> <span data-ttu-id="de291-118">Emellett kereshet a gomb „elérési útját” alkotó szavak használatával is.</span><span class="sxs-lookup"><span data-stu-id="de291-118">You can also search by using words from the button's "path."</span></span> <span data-ttu-id="de291-119">(További információért lásd a cikk következő részét.) Általában kettő vagy négy karakter beírása után megjelenik egy gomb az eredménylista felső részén.</span><span class="sxs-lookup"><span data-stu-id="de291-119">(For more information, see the next section of this article.) Typically, a button will appear near the top of the results list after you've typed two to four characters.</span></span>
3. <span data-ttu-id="de291-120">Keresse meg és futtassa a gombot a találati listában (egér vagy billentyűzet segítségével).</span><span class="sxs-lookup"><span data-stu-id="de291-120">Find and run the button in the results list (by using your mouse or keyboard).</span></span>

<span data-ttu-id="de291-121">A gomb futtatása után a fókusz visszakerül az utolsó pozícióra az oldalon, így tovább dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="de291-121">After the button is run, the focus is returned to your last position on the page, so that you can continue to work.</span></span>

<span data-ttu-id="de291-122">[![műveletkeresési mező](./media/action-search-field.png)](./media/action-search-field.png)</span><span class="sxs-lookup"><span data-stu-id="de291-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span></span>

<span data-ttu-id="de291-123">A Ctrl+/ vagy az Alt+Q billentyűkombinációkkal is elindíthatja a műveletkeresést.</span><span class="sxs-lookup"><span data-stu-id="de291-123">You can also start action search by pressing Ctrl+/ or Alt+Q.</span></span> <span data-ttu-id="de291-124">Nyomja le a billentyűparancsot ismét, hogy visszatérjen a fókusz az utolsó pozícióra az oldalon.</span><span class="sxs-lookup"><span data-stu-id="de291-124">Press the keyboard shortcut again to return the focus to your last position on the page.</span></span>

## <a name="understanding-the-results-list"></a><span data-ttu-id="de291-125">Az eredménylista ismertetése</span><span class="sxs-lookup"><span data-stu-id="de291-125">Understanding the results list</span></span>

<span data-ttu-id="de291-126">Gyakran a gomb helyét és környezetét is ismernünk kell ahhoz, hogy teljesen átlássuk a gomb funkcióját.</span><span class="sxs-lookup"><span data-stu-id="de291-126">Often, you must know both the location and the context of a button to fully understand the purpose of that button.</span></span> <span data-ttu-id="de291-127">Ezért az eredménylistában további információk is láthatók, amelyek segítenek megérteni, pontosan mely gombok láthatók a listában.</span><span class="sxs-lookup"><span data-stu-id="de291-127">Therefore, the results list shows additional information to help you understand exactly which buttons appear in the list.</span></span> <span data-ttu-id="de291-128">Főként a gomb „elérési útja” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="de291-128">In particular, the "path" of the button is shown.</span></span> <span data-ttu-id="de291-129">Az elérési út a felhasználói felület következő elemeihez tartozó címkéket tartalmazhatja lényegesként:</span><span class="sxs-lookup"><span data-stu-id="de291-129">This path might include the labels of the following UI elements, as relevant:</span></span>

- <span data-ttu-id="de291-130">Műveleti ablaktábla lap</span><span class="sxs-lookup"><span data-stu-id="de291-130">Action Pane tab</span></span>
- <span data-ttu-id="de291-131">Gombcsoport</span><span class="sxs-lookup"><span data-stu-id="de291-131">Button group</span></span>
- <span data-ttu-id="de291-132">Menügomb (ha a gomb menügombon belül található)</span><span class="sxs-lookup"><span data-stu-id="de291-132">Menu button (if the button is inside a menu button)</span></span>
- <span data-ttu-id="de291-133">Menüelválasztó (ha a gomb egy névvel ellátott csoporton belül található egy menügombban)</span><span class="sxs-lookup"><span data-stu-id="de291-133">Menu separator (if the button is inside a named group inside a menu button)</span></span>
- <span data-ttu-id="de291-134">Csoport vagy a lap az oldalon (például egy gyorslap neve)</span><span class="sxs-lookup"><span data-stu-id="de291-134">Group or tab on the page (for example, the name of a FastTab)</span></span>

<span data-ttu-id="de291-135">Például beírta, hogy **össz** a **műveletkeresés** mezőbe, és most az eredménylistát nézi.</span><span class="sxs-lookup"><span data-stu-id="de291-135">For example, you typed **tot** in the **action search** field and are now examining the results list.</span></span> <span data-ttu-id="de291-136">Az első tétel az **Összesen** nevű gombnál ki van emelve.</span><span class="sxs-lookup"><span data-stu-id="de291-136">The first entry, for a button that is named **Totals**, is highlighted.</span></span> <span data-ttu-id="de291-137">A gomb **Értékesítési rendelés** &gt; **Nézet** elérési útja is látható.</span><span class="sxs-lookup"><span data-stu-id="de291-137">A button path of **Sales order** &gt; **View** is also shown.</span></span> <span data-ttu-id="de291-138">Az elérési út **Értékesítési rendelés** része felel meg az **Értékesítési rendelés** lapnak a Művelet ablakban, és az elérési út **Megtekintés** része felel meg a **Megtekintés** csoportnak a lapon. Hasonlóan az elérési útja az **Összengedmény** gombnak (**Értékesítés**&gt;**Számítás**) ad tájékoztatást arról, hogy ez a gomb a **Számítás** csoportban az **Értékesítés** lapon található a Művelet ablakban.</span><span class="sxs-lookup"><span data-stu-id="de291-138">The **Sales order** part of the path corresponds to the **Sales order** tab on the Action Pane, and the **View** part of the path corresponds to the **View** group on that tab. Similarly, the path of the **Total discount** button (**Sell** &gt; **Calculate**) informs you that this button is located in the **Calculate** group on the **Sell** tab of the Action Pane.</span></span> <span data-ttu-id="de291-139">Tehát ez az információ segít megérteni, pontosan melyik gomb aktiválódik a műveletkeresés hatására (ha az eredménylistában az adott gombot választja).</span><span class="sxs-lookup"><span data-stu-id="de291-139">Therefore, this information helps you understand exactly which button will be triggered by action search (if you select that button in the results list).</span></span>

<span data-ttu-id="de291-140">[![műveletkeresési mező adatokkal](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span><span class="sxs-lookup"><span data-stu-id="de291-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span></span>

<span data-ttu-id="de291-141">Az előző példában a műveletkeresési funkció az oldal tetején található normál Műveleti ablaktáblából mutatott eredményeket.</span><span class="sxs-lookup"><span data-stu-id="de291-141">In the previous example, action search showed results from the standard Action Pane at the top of a page.</span></span> <span data-ttu-id="de291-142">A műveletkeresés azonban az oldal más területein található, látható eszköztárakból is jelenít meg eredményeket.</span><span class="sxs-lookup"><span data-stu-id="de291-142">However, action search also shows results from visible toolbars that are in other places on the page.</span></span> <span data-ttu-id="de291-143">Például az **Aktuális készlet** gombot keresi, amely az **Értékesítési rendelés sorai** gyorslapon található.</span><span class="sxs-lookup"><span data-stu-id="de291-143">For example, you're searching for the **On-hand inventory** button that is on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="de291-144">Ebben az esetben az eredménylistában látható gombelérési út (**Értékesítési rendelés sorai** &gt; **Készlet** &gt; **Nézet**) arról tájékoztat, hogy ez a gomb a **Készlet** menügomb **Nézet** fejlécében található az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="de291-144">In this case, the button path in the results list (**Sales order lines** &gt; **Inventory** &gt; **View**) informs you that this button is under the **View** heading on the **Inventory** menu button on the **Sales order lines** FastTab.</span></span>

<span data-ttu-id="de291-145">[![aktuális készlet](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="de291-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span></span>

> [!NOTE]
> <span data-ttu-id="de291-146">Vannak olyan gombok, amelyek nem jelennek meg a művelet keresésében.</span><span class="sxs-lookup"><span data-stu-id="de291-146">There are some buttons that do not show up in Action search.</span></span> <span data-ttu-id="de291-147">Ilyenek többek között legördülő párbeszédpanelek gombjai és a segédűrlapok gombjai.</span><span class="sxs-lookup"><span data-stu-id="de291-147">These include drop dialog buttons and buttons from subforms.</span></span> 

## <a name="action-search-vs-navigation-search"></a><span data-ttu-id="de291-148">Műveletkeresés és navigációs keresés</span><span class="sxs-lookup"><span data-stu-id="de291-148">Action search vs. Navigation search</span></span>

<span data-ttu-id="de291-149">A műveletkereséssel műveletek kereshetők meg és futtathatók egy oldalon. Emellett van egy másik keresési funkció is, amellyel oldalak kereshetők és nyithatók meg.</span><span class="sxs-lookup"><span data-stu-id="de291-149">Whereas action search is intended to find and run actions on a page, there is a separate search mechanism for finding and navigating to pages.</span></span> <span data-ttu-id="de291-150">Ezen funkcióval kapcsolatos további információk a [Navigációs keresés](navigation-search.md) cikkben találhatók.</span><span class="sxs-lookup"><span data-stu-id="de291-150">For more information about that feature, see the [Navigation search](navigation-search.md) article.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]