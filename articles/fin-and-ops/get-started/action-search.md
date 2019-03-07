---
title: Műveletkeresés
description: Ez a cikk a művelet keresési funkciót ismerteti a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban. A műveletkeresés segít megkeresni és adott lapon lefuttatni műveleteket.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 960c715c487fbda5d93630327f07380e6d8fbd3c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "317499"
---
# <a name="action-search"></a><span data-ttu-id="b054d-104">Műveletkeresés</span><span class="sxs-lookup"><span data-stu-id="b054d-104">Action search</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b054d-105">Ez a cikk a művelet keresési funkciót ismerteti a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="b054d-105">This article describes the action search functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="b054d-106">A műveletkeresés segít megkeresni és adott lapon lefuttatni műveleteket.</span><span class="sxs-lookup"><span data-stu-id="b054d-106">Action search will help you find and run actions on a page.</span></span>

## <a name="introduction"></a><span data-ttu-id="b054d-107">Bevezetés</span><span class="sxs-lookup"><span data-stu-id="b054d-107">Introduction</span></span>

<span data-ttu-id="b054d-108">A Microsoft Dynamics 365 for Finance and Operations oldalain az utasítások elsősorban a műveletpaneleken láthatók, egyrészt az oldal tetején megjelenő normál műveletpanelen, és az oldal különböző szakaszaiban megjelenő eszköztárakon.</span><span class="sxs-lookup"><span data-stu-id="b054d-108">Pages in Microsoft Dynamics 365 for Finance and Operations primarily expose commands on Action Panes, both the standard Action Pane that appears at the top of a page and the toolbars that appear in various sections of the page.</span></span> <span data-ttu-id="b054d-109">A korábbi verziókban a billentyűtippek szolgáltatás lehetővé tette a műveletpanel bármely gombjának gyors elérését az Alt billentyű, majd egy betűsorozat lenyomásával.</span><span class="sxs-lookup"><span data-stu-id="b054d-109">In previous versions, a Key Tips feature let you quickly access any button on an Action Pane by pressing the Alt key and then a series of letters.</span></span>

<span data-ttu-id="b054d-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span><span class="sxs-lookup"><span data-stu-id="b054d-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span></span>

<span data-ttu-id="b054d-111">A Finance and Operations jelenlegi verziójában azonban a billentyűtippek funkció már nem érhető el, és a műveletkeresés funkció lépett a helyébe.</span><span class="sxs-lookup"><span data-stu-id="b054d-111">However, in the current version of Finance and Operations, Key Tips are no longer available but have been replaced by the action search feature.</span></span> <span data-ttu-id="b054d-112">Ez az új funkció lehetővé teszi, hogy gyorsan megkeressen és működtessen egy gombot bármelyik látható műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="b054d-112">This new feature lets you quickly search for and run a button from any visible Action Pane.</span></span>

## <a name="using-action-search"></a><span data-ttu-id="b054d-113">A műveletkeresés használatával</span><span class="sxs-lookup"><span data-stu-id="b054d-113">Using action search</span></span>

<span data-ttu-id="b054d-114">A műveletkeresési funkció használatához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b054d-114">To use the action search feature, follow these steps.</span></span>

1. <span data-ttu-id="b054d-115">A műveleti ablaktáblán kattintson a **műveletkeresés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b054d-115">On the Action Pane, click in the **action search** field.</span></span> <span data-ttu-id="b054d-116">(A **műveletkeresés** mező egy nagyítóüveget ábrázoló ikont tartalmaz.)</span><span class="sxs-lookup"><span data-stu-id="b054d-116">(The **action search** field contains a magnifying glass icon.)</span></span>
2. <span data-ttu-id="b054d-117">Írja be a futtatni kívánt gomb nevének egy részét vagy egészét.</span><span class="sxs-lookup"><span data-stu-id="b054d-117">Type all or part of the name of the button that you want to run.</span></span> <span data-ttu-id="b054d-118">Emellett kereshet a gomb „elérési útját” alkotó szavak használatával is.</span><span class="sxs-lookup"><span data-stu-id="b054d-118">You can also search by using words from the button's "path."</span></span> <span data-ttu-id="b054d-119">(További információért lásd a cikk következő részét.) Általában kettő vagy négy karakter beírása után megjelenik egy gomb az eredménylista felső részén.</span><span class="sxs-lookup"><span data-stu-id="b054d-119">(For more information, see the next section of this article.) Typically, a button will appear near the top of the results list after you've typed two to four characters.</span></span>
3. <span data-ttu-id="b054d-120">Keresse meg és futtassa a gombot a találati listában (egér vagy billentyűzet segítségével).</span><span class="sxs-lookup"><span data-stu-id="b054d-120">Find and run the button in the results list (by using your mouse or keyboard).</span></span>

<span data-ttu-id="b054d-121">A gomb futtatása után a fókusz visszakerül az utolsó pozícióra az oldalon, így tovább dolgozhat.</span><span class="sxs-lookup"><span data-stu-id="b054d-121">After the button is run, the focus is returned to your last position on the page, so that you can continue to work.</span></span>

<span data-ttu-id="b054d-122">[![műveletkeresési mező](./media/action-search-field.png)](./media/action-search-field.png)</span><span class="sxs-lookup"><span data-stu-id="b054d-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span></span>

<span data-ttu-id="b054d-123">A Ctrl+/ vagy az Alt+Q billentyűkombinációkkal is elindíthatja a műveletkeresést.</span><span class="sxs-lookup"><span data-stu-id="b054d-123">You can also start action search by pressing Ctrl+/ or Alt+Q.</span></span> <span data-ttu-id="b054d-124">Nyomja le a billentyűparancsot ismét, hogy visszatérjen a fókusz az utolsó pozícióra az oldalon.</span><span class="sxs-lookup"><span data-stu-id="b054d-124">Press the keyboard shortcut again to return the focus to your last position on the page.</span></span>

## <a name="understanding-the-results-list"></a><span data-ttu-id="b054d-125">Az eredménylista ismertetése</span><span class="sxs-lookup"><span data-stu-id="b054d-125">Understanding the results list</span></span>

<span data-ttu-id="b054d-126">A Finance and Operationsben gyakran a gomb helyét és környezetét is ismernünk kell ahhoz, hogy teljesen átlássuk a gomb funkcióját.</span><span class="sxs-lookup"><span data-stu-id="b054d-126">Often, in Finance and Operations, you must know both the location and the context of a button to fully understand the purpose of that button.</span></span> <span data-ttu-id="b054d-127">Ezért az eredménylistában minden elemnél további információk is láthatók, amelyek segítenek megérteni, pontosan mely gombok láthatók a listában.</span><span class="sxs-lookup"><span data-stu-id="b054d-127">Therefore, additional information is shown for each item in the results list, to help you understand exactly which buttons appear in the list.</span></span> <span data-ttu-id="b054d-128">Főként a gomb „elérési útja” jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b054d-128">In particular, the "path" of the button is shown.</span></span> <span data-ttu-id="b054d-129">Az elérési út a felhasználói felület következő elemeihez tartozó címkéket tartalmazhatja lényegesként:</span><span class="sxs-lookup"><span data-stu-id="b054d-129">This path might include the labels of the following UI elements, as relevant:</span></span>

- <span data-ttu-id="b054d-130">Műveleti ablaktábla lap</span><span class="sxs-lookup"><span data-stu-id="b054d-130">Action Pane tab</span></span>
- <span data-ttu-id="b054d-131">Gombcsoport</span><span class="sxs-lookup"><span data-stu-id="b054d-131">Button group</span></span>
- <span data-ttu-id="b054d-132">Menügomb (ha a gomb menügombon belül található)</span><span class="sxs-lookup"><span data-stu-id="b054d-132">Menu button (if the button is inside a menu button)</span></span>
- <span data-ttu-id="b054d-133">Menüelválasztó (ha a gomb egy névvel ellátott csoporton belül található egy menügombban)</span><span class="sxs-lookup"><span data-stu-id="b054d-133">Menu separator (if the button is inside a named group inside a menu button)</span></span>
- <span data-ttu-id="b054d-134">Csoport vagy a lap az oldalon (például egy gyorslap neve)</span><span class="sxs-lookup"><span data-stu-id="b054d-134">Group or tab on the page (for example, the name of a FastTab)</span></span>

<span data-ttu-id="b054d-135">Például beírta, hogy **össz** a **műveletkeresés** mezőbe, és most az eredménylistát nézi.</span><span class="sxs-lookup"><span data-stu-id="b054d-135">For example, you typed **tot** in the **action search** field and are now examining the results list.</span></span> <span data-ttu-id="b054d-136">Az első tétel az **Összesen** nevű gombnál ki van emelve.</span><span class="sxs-lookup"><span data-stu-id="b054d-136">The first entry, for a button that is named **Totals**, is highlighted.</span></span> <span data-ttu-id="b054d-137">A gomb **Értékesítési rendelés** &gt; **Nézet** elérési útja is látható.</span><span class="sxs-lookup"><span data-stu-id="b054d-137">A button path of **Sales order** &gt; **View** is also shown.</span></span> <span data-ttu-id="b054d-138">Az elérési út **Értékesítési rendelés** része felel meg az **Értékesítési rendelés** lapnak a Művelet ablakban, és az elérési út **Megtekintés** része felel meg a **Megtekintés** csoportnak a lapon. Hasonlóan az elérési útja az **Összengedmény** gombnak (**Értékesítés**&gt;**Számítás**) ad tájékoztatást arról, hogy ez a gomb a **Számítás** csoportban az **Értékesítés** lapon található a Művelet ablakban.</span><span class="sxs-lookup"><span data-stu-id="b054d-138">The **Sales order** part of the path corresponds to the **Sales order** tab on the Action Pane, and the **View** part of the path corresponds to the **View** group on that tab. Similarly, the path of the **Total discount** button (**Sell** &gt; **Calculate**) informs you that this button is located in the **Calculate** group on the **Sell** tab of the Action Pane.</span></span> <span data-ttu-id="b054d-139">Tehát ez az információ segít megérteni, pontosan melyik gomb aktiválódik a műveletkeresés hatására (ha az eredménylistában az adott gombot választja).</span><span class="sxs-lookup"><span data-stu-id="b054d-139">Therefore, this information helps you understand exactly which button will be triggered by action search (if you select that button in the results list).</span></span>

<span data-ttu-id="b054d-140">[![műveletkeresési mező adatokkal](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span><span class="sxs-lookup"><span data-stu-id="b054d-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span></span>

<span data-ttu-id="b054d-141">Az előző példában a műveletkeresési funkció az oldal tetején található normál Műveleti ablaktáblából mutatott eredményeket.</span><span class="sxs-lookup"><span data-stu-id="b054d-141">In the previous example, action search showed results from the standard Action Pane at the top of a page.</span></span> <span data-ttu-id="b054d-142">A műveletkeresés azonban az oldal más területein található, látható eszköztárakból is jelenít meg eredményeket.</span><span class="sxs-lookup"><span data-stu-id="b054d-142">However, action search also shows results from visible toolbars that are located in other places on the page.</span></span> <span data-ttu-id="b054d-143">Például az **Aktuális készlet** gombot keresi, amely az **Értékesítési rendelés sorai** gyorslapon található.</span><span class="sxs-lookup"><span data-stu-id="b054d-143">For example, you're searching for the **On-hand inventory** button that is located on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b054d-144">Ebben az esetben az eredménylistában látható gombelérési út (**Értékesítési rendelés sorai** &gt; **Készlet** &gt; **Nézet**) arról tájékoztat, hogy ez a gomb a **Készlet** menügomb **Nézet** fejlécében található az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="b054d-144">In this case, the button path in the results list (**Sales order lines** &gt; **Inventory** &gt; **View**) informs you that this button is located under the **View** heading on the **Inventory** menu button on the **Sales order lines** FastTab.</span></span>

<span data-ttu-id="b054d-145">[![aktuális készlet](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="b054d-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span></span>

## <a name="action-search-vs-navigation-search"></a><span data-ttu-id="b054d-146">Műveletkeresés és navigációs keresés</span><span class="sxs-lookup"><span data-stu-id="b054d-146">Action search vs. Navigation search</span></span>

<span data-ttu-id="b054d-147">A műveletkereséssel műveletek kereshetők meg és futtathatók egy oldalon. Emellett van egy másik keresési funkció is, amellyel oldalak kereshetők és nyithatók meg a Finance and Operations rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b054d-147">Whereas action search is intended to find and run actions on a page, there is a separate search mechanism for finding and navigating to pages in Finance and Operations.</span></span> <span data-ttu-id="b054d-148">Ezen funkcióval kapcsolatos további információk a [Navigációs keresés](navigation-search.md) cikkben találhatók.</span><span class="sxs-lookup"><span data-stu-id="b054d-148">For more information about that feature, see the [Navigation search](navigation-search.md) article.</span></span>