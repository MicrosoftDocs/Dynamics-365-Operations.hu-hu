---
title: A felhasználói felület elemei
description: Ez a témakör az alkalmazásban használt felhasználói felület (UI) elemeit mutatja be.
author: tlefor
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: ''
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 0c58ac63a4eae61c9a1cc6134bd0857394895e30
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693593"
---
# <a name="user-interface-elements"></a><span data-ttu-id="31571-103">A felhasználói felület elemei</span><span class="sxs-lookup"><span data-stu-id="31571-103">User interface elements</span></span>

<span data-ttu-id="31571-104">Ez a témakör az alkalmazásban használt felhasználói felület (UI) elemeit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="31571-104">This topic describes the user interface (UI) elements used in the app.</span></span> <span data-ttu-id="31571-105">Mielőtt a felhasználók navigálni tudnak a kezelőfelületen, fontos tudni a felületet alkotó elemek neveit és funkcióit.</span><span class="sxs-lookup"><span data-stu-id="31571-105">Before users can navigate the interface, it's important to know the names and functions of the elements that make up the interface.</span></span>

## <a name="overview"></a><span data-ttu-id="31571-106">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="31571-106">Overview</span></span>

- <span data-ttu-id="31571-107">**Műveleti ablaktábla** – a navigációs sáv alatti sáv.</span><span class="sxs-lookup"><span data-stu-id="31571-107">**Action Pane** - The bar beneath the navigation bar.</span></span> <span data-ttu-id="31571-108">Itt választhatja ki az oldalon látható rekordok módosítására szolgáló lapokat.</span><span class="sxs-lookup"><span data-stu-id="31571-108">Here, you can select tabs to change records shown in the page.</span></span> <span data-ttu-id="31571-109">A rekordok itt szerkeszthetők és menthetők.</span><span class="sxs-lookup"><span data-stu-id="31571-109">You can edit and save the records here.</span></span>  
- <span data-ttu-id="31571-110">**Adatterület** – a panelen megjelenítheti az adatokat, és nyomon követheti az egyes rekordok műveleteit.</span><span class="sxs-lookup"><span data-stu-id="31571-110">**FactBox** - You can see information and follow the activities of certain records in this pane.</span></span>  
- <span data-ttu-id="31571-111">**Adatterületek ablaktábla** itt lapozhatja át a rekord különböző szempontjait, amely az adatterületen látható.</span><span class="sxs-lookup"><span data-stu-id="31571-111">**FactBox pane** Here, you can scroll through different aspects of a record to view in the FactBox.</span></span>  
- <span data-ttu-id="31571-112">**Szűrési ablaktábla** – Egyes oldalakon a **Szűrők megjelenítése** lehetőséggel megnyithatja ezt az ablaktáblát.</span><span class="sxs-lookup"><span data-stu-id="31571-112">**Filter pane** - On some pages, you can select **Show filters** to open this pane.</span></span> <span data-ttu-id="31571-113">Ez lehetővé teszi a lapon látható eredmények szűkítését.</span><span class="sxs-lookup"><span data-stu-id="31571-113">It allows you to narrow the results visible to you on the page.</span></span>  
- <span data-ttu-id="31571-114">**Navigációs sáv** – a felület felső részén található sáv.</span><span class="sxs-lookup"><span data-stu-id="31571-114">**Navigation bar** - The bar at the top of the interface.</span></span> <span data-ttu-id="31571-115">Itt található a **Dynamics 365 portál**, a **Keresés**, a **Vállalatválasztó**, a **Műveleti központ**, a **Beállítások**, a **Súgó és támogatás**, valamint a felhasználói profil.</span><span class="sxs-lookup"><span data-stu-id="31571-115">It contains the **Dynamics 365 portal**, **Search**, **company picker**, **Action center**, **Settings**, **Help & Support**, and the user profile.</span></span>  
- <span data-ttu-id="31571-116">**Navigációs lista** – egyes oldalakon az ablaktáblán görgetve megkeresheti a megadott rekordot.</span><span class="sxs-lookup"><span data-stu-id="31571-116">**Navigation list** - On some pages, you can scroll through this pane to find a specific record.</span></span> <span data-ttu-id="31571-117">Ha be van jelölve, akkor a rekord adatai megjelennek a lapon.</span><span class="sxs-lookup"><span data-stu-id="31571-117">When selected, the details of the record will appear in the page.</span></span>  
- <span data-ttu-id="31571-118">**Navigációs ablaktábla** - A leginkább bal oldali ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="31571-118">**Navigation pane** - The left-most pane.</span></span> <span data-ttu-id="31571-119">Innen a termék bármelyik lapját megtalálhatja.</span><span class="sxs-lookup"><span data-stu-id="31571-119">From here, you can find any page in the product.</span></span>  
- <span data-ttu-id="31571-120">**Oldal** – a felület központi fókusza.</span><span class="sxs-lookup"><span data-stu-id="31571-120">**Page** - The central focus of the interface.</span></span> <span data-ttu-id="31571-121">A többi felhasználóifelület-összetevőn végzett kiválasztások befolyásolják, hogy itt milyen rekordok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="31571-121">Selections made on the other UI components will affect what records are shown here.</span></span>  
- <span data-ttu-id="31571-122">**Ablaktábla** - A leginkább jobb oldali ablaktábla.</span><span class="sxs-lookup"><span data-stu-id="31571-122">**Pane** - The right-most pane.</span></span> <span data-ttu-id="31571-123">Ez bizonyos esetekben megnyílik, amikor a rekordok jellemzőit módosítani és menteni kell.</span><span class="sxs-lookup"><span data-stu-id="31571-123">This will open in some cases when aspects of a record need to be changed and saved.</span></span>  
- <span data-ttu-id="31571-124">**Lap** – a műveleti ablakra történő hivatkozáskor ez egy olyan beállítási menü, amely akkor jelenik meg, ha a műveleti ablaktáblában kiválasztja a megadott beállítást.</span><span class="sxs-lookup"><span data-stu-id="31571-124">**Tab** - When referring to the Action Pane, it's a menu of options that appears when you select a given option in the Action Pane.</span></span>  

![A következő kép bemutatja ezeknek az elemeknek az elhelyezkedését a kezelőfelületen.](media/user-interface-01.png)

## <a name="tabs-fields-and-sections"></a><span data-ttu-id="31571-126">Lapok, mezők és szakaszok</span><span class="sxs-lookup"><span data-stu-id="31571-126">Tabs, fields, and sections</span></span>

<span data-ttu-id="31571-127">A *lap* egy kiválasztás az oldalon, amely egy rekord másik aspektusát nyitja meg ugyanazon az oldalon.</span><span class="sxs-lookup"><span data-stu-id="31571-127">A *tab* is a selection made on the page that opens a different aspect of a record on the same page.</span></span> <span data-ttu-id="31571-128">Gyakran engedélyezi bizonyos *mezők* módosítását, vagy olyan felhasználóifelület-elemekét, amelyek gépelt bevitelt engedélyeznek.</span><span class="sxs-lookup"><span data-stu-id="31571-128">Often, it will allow you to change certain *fields*, or UI elements that allow typed input.</span></span> 

<span data-ttu-id="31571-129">A *Gyorslap* egy olyan lap, amelynek további előnye, hogy egyszerre több lapot is láthatóvá tesz.</span><span class="sxs-lookup"><span data-stu-id="31571-129">A *FastTab* is a tab with the added benefit of allowing multiple tabs to be visible at the same.</span></span> <span data-ttu-id="31571-130">A gyorslap kibontásához kattintson a jobb szélén látható lefelé mutató nyílra.</span><span class="sxs-lookup"><span data-stu-id="31571-130">You can expand a FastTab by selecting the downward-pointing arrow on the right end of it.</span></span>

![A következő kép egy példát mutat a lapokra és Gyorslapokra.](media/user-interface-02.png)

<span data-ttu-id="31571-132">A *szakasz* hasonló egy laphoz. A „szakasz” szót gyakran használják egy oldal olyan területeinek leírására, amelyek információk egy megadott kategóriáját tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="31571-132">A *section* is similar to a tab. The word "section" is often used to describe any area of a page that organizes a specific category of information.</span></span> <span data-ttu-id="31571-133">A következő képen a szakaszok példái láthatók: Összegzés, Rendelések és kedvencek, valamint Hivatkozások.</span><span class="sxs-lookup"><span data-stu-id="31571-133">In the following image, Summary, Orders and favorites, and Links are all examples of sections.</span></span>

![A következő kép egy példát mutat a lapokra és szakaszokra.](media/user-interface-03.png)

## <a name="dialog-boxes-and-drop-down-menus"></a><span data-ttu-id="31571-135">Párbeszédpanelek és legördülő menük</span><span class="sxs-lookup"><span data-stu-id="31571-135">Dialog boxes and drop-down menus</span></span>

<span data-ttu-id="31571-136">A *párbeszédpanel* egy olyan ablak, amely akkor jelenik meg, amikor bizonyos kiválasztásokkal egy rekordot kívánnak módosítani vagy létrehozni.</span><span class="sxs-lookup"><span data-stu-id="31571-136">A *dialog box* is a pane that opens when certain selections are made to change or create a record.</span></span> <span data-ttu-id="31571-137">A párbeszédpanelek olyan mezőket tartalmaznak, amelyek lehetővé teszik gépelt bemenetek megadását.</span><span class="sxs-lookup"><span data-stu-id="31571-137">Dialog boxes contain fields that allow you to enter typed input.</span></span> <span data-ttu-id="31571-138">Előfordulhat, hogy egy megadott mezőből ki lehet választani egy lefelé mutató nyilat, amely megnyitja a választható lehetőségek listáját.</span><span class="sxs-lookup"><span data-stu-id="31571-138">Sometimes, a given field will allow you to select a downward facing arrow that opens a list of options to choose from.</span></span> <span data-ttu-id="31571-139">Ezt nevezzük *legördülő menünek*.</span><span class="sxs-lookup"><span data-stu-id="31571-139">This is called a *drop-down menu*.</span></span> <span data-ttu-id="31571-140">Az alábbi képen a **Típus** és **Vevőcsoport** mezőkben szerepel a legördülő menü megnyitási lehetősége.</span><span class="sxs-lookup"><span data-stu-id="31571-140">In the following image, the **Type** and **Customer group** fields contain the option to open a drop-down menu.</span></span>

![A következő kép egy példát mutat a párbeszédpanelekre.](media/user-interface-04.png)

<span data-ttu-id="31571-142">Bizonyos esetekben egy párbeszédpanel nyílik meg egy adott gomb mellett, amikor rákattint.</span><span class="sxs-lookup"><span data-stu-id="31571-142">In some cases, a dialog box will open near a given button when you select it.</span></span> <span data-ttu-id="31571-143">Ezt nevezzük *legördülő párbeszédablaknak*.</span><span class="sxs-lookup"><span data-stu-id="31571-143">This is called a *drop-down dialog box*.</span></span> <span data-ttu-id="31571-144">Az alábbi képen kiválasztottuk az **Adott naptól** gombot, amely megnyitott egy legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="31571-144">In the following image, the **As of date** button was selected, which opened a drop-down dialog box.</span></span>

![A következő kép egy példát mutat a legördülő párbeszédpanelekre.](media/user-interface-05.png)

## <a name="notifications"></a><span data-ttu-id="31571-146">Értesítések</span><span class="sxs-lookup"><span data-stu-id="31571-146">Notifications</span></span>

<span data-ttu-id="31571-147">A felügyelt objektumok bizonyos módosításai *értesítésekként* jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="31571-147">Certain changes to the objects you oversee will appear as *notifications*.</span></span> <span data-ttu-id="31571-148">A rendszer értesítésekkel tájékoztathatja, amikor egy bizonyos ügyfél adatai módosultak, vagy figyelmezteti, amikor a rendszer nem fogadja el a bizonyos mezőkbe bevitt értékeket.</span><span class="sxs-lookup"><span data-stu-id="31571-148">Notifications may notify you when a specific customer's information has been changed, or it may alert you when the system can't accept inputs you've added in certain fields.</span></span> <span data-ttu-id="31571-149">Megtanulhatja, hogy hogyan szabályozhatja, hogy miről kapjon értesítéseket a [Figyelmeztetések áttekintése](../get-started/alerts-overview.md) részben.</span><span class="sxs-lookup"><span data-stu-id="31571-149">You can learn how to customize what you receive notifications about in the [Alerts overview](../get-started/alerts-overview.md).</span></span>

<span data-ttu-id="31571-150">Az értesítések számos módon megjelennek.</span><span class="sxs-lookup"><span data-stu-id="31571-150">Notifications appear in a variety of ways.</span></span>
- <span data-ttu-id="31571-151">**Funkcióbuborék** – Ez egy mező, lap vagy más gomb mellett jelenik meg, és magyarázatot nyújt a funkció használati módjára.</span><span class="sxs-lookup"><span data-stu-id="31571-151">**Feature callout** - This will appear next to a field, tab, or other button to offer an explanation of what the feature is used for.</span></span> 
- <span data-ttu-id="31571-152">**Műveleti központ** - Az értesítést tartalmazó mező a navigációs sávon, a Műveleti központ gomb mellett jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="31571-152">**Action center** - A box that contains the notification will appear next to the Action center button on the navigation bar.</span></span> <span data-ttu-id="31571-153">Az értesítéssel kapcsolatos részleteket a **Műveleti központ** kiválasztásával jelenítheti meg .</span><span class="sxs-lookup"><span data-stu-id="31571-153">You can see details about the notification by selecting **Action center**.</span></span>  
- <span data-ttu-id="31571-154">**Üzenetsáv** – ez a műveleti ablaktábla alatt fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="31571-154">**Message bar** - This will appear beneath the Action Pane.</span></span>  

<span data-ttu-id="31571-155">A következő kép példákat mutat be az ilyen típusú értesítésekre.</span><span class="sxs-lookup"><span data-stu-id="31571-155">The following image shows examples of these types of notifications.</span></span>

![A következő kép példákat mutat be az értesítésekre.](media/user-interface-06.png)

- <span data-ttu-id="31571-157">**Üzenetpanel** – Ez a felületen keresztben jelenik meg, és reagálni kell rá, mielőtt folytathatná a termék használatát.</span><span class="sxs-lookup"><span data-stu-id="31571-157">**Message box** - This will appear over the interface and must be interacted with before you can continue to use the product.</span></span>  

![A következő kép egy példát mutat az üzenetpanelekre.](media/user-interface-07.png)

## <a name="toolbars-grids-and-lists"></a><span data-ttu-id="31571-159">Eszköztárak, rácsok és listák</span><span class="sxs-lookup"><span data-stu-id="31571-159">Toolbars, grids, and lists</span></span>

<span data-ttu-id="31571-160">Az *eszköztár* olyan eszközöket tartalmaz, mint például a mezők hozzáadásának vagy a rekordok eltávolításának a képessége.</span><span class="sxs-lookup"><span data-stu-id="31571-160">A *toolbar* contains tools, such as the ability to add fields or remove records.</span></span> <span data-ttu-id="31571-161">Előfordulhat, hogy egy oldalon egy eszköztár egy *rács* fölött jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="31571-161">Sometimes, a toolbar will appear on the page above a *grid*.</span></span> <span data-ttu-id="31571-162">Ez a terület, a rács, a rekordok sorainak és a hozzájuk kapcsolódó különböző adatoszlopoknak adott név.</span><span class="sxs-lookup"><span data-stu-id="31571-162">This area, grid, is a name given to rows of records with various columns of data.</span></span> <span data-ttu-id="31571-163">Nem minden rács felett van eszköztár.</span><span class="sxs-lookup"><span data-stu-id="31571-163">Not all grids have toolbars above them.</span></span>

<span data-ttu-id="31571-164">A *lista* rekordok gyűjteményének a neve, amelyeket át lehet görgetni.</span><span class="sxs-lookup"><span data-stu-id="31571-164">A *list* is the name given to a collection of records that you can scroll through.</span></span> <span data-ttu-id="31571-165">Ezeket a rekordokat átviheti az oldalra, ha kijelöli őket.</span><span class="sxs-lookup"><span data-stu-id="31571-165">You can bring these records into the page by selecting them.</span></span> <span data-ttu-id="31571-166">Ez a művelet gyakran egy rácsot nyit meg.</span><span class="sxs-lookup"><span data-stu-id="31571-166">Often, this will open a grid.</span></span>

![A következő kép példákat mutat be az eszköztárakra, rácsokra és listákra.](media/user-interface-08.png)
