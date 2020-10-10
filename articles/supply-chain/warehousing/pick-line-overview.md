---
title: Mobileszköz-menüelem beállítása a kitárolási sor áttekintésének biztosításához
description: Ez a témakör azt mutatja be, hogyan lehet meghatározni, hogy az összes munkasor listája mikor jelenik meg a raktári dolgozók számára, akik mobileszközön dolgoznak fel raktári munkát. Ez a lehetőség olyan raktári dolgozók számára hasznos, akik gyakran igényelnek áttekintést a kivételezési sorokról egy munkarendelésben, hogy optimalizálni tudják a kitárolási sorozatot.
author: MarkusFogelberg
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 3a2c8a69a2c64214a38a654042ea2f62575e7f52
ms.sourcegitcommit: a52a789044ca66c6771224a6cf0be8749bc99e5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2020
ms.locfileid: "3837312"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a><span data-ttu-id="236bd-104">Mobileszköz-menüelem beállítása a kitárolási sor áttekintésének biztosításához</span><span class="sxs-lookup"><span data-stu-id="236bd-104">Set up a mobile device menu item to provide a pick line overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="236bd-105">Ez a témakör azt mutatja be, hogyan lehet beállítani a kitárolási munka feldolgozásához használt mobileszköz-menüelemeket, amelyek a kitárolási munka feldolgozásához használatosak.</span><span class="sxs-lookup"><span data-stu-id="236bd-105">This topic explains how to configure options that are related to the pick line overview for mobile device menu items that are used to process picking work.</span></span> <span data-ttu-id="236bd-106">A kitárolási sor áttekintése a raktári dolgozók számára lehetővé teszi az aktuális feladathoz kapcsolódó összes munkasor listájának megtekintését és a kiválasztást abból.</span><span class="sxs-lookup"><span data-stu-id="236bd-106">The pick line overview lets warehouse workers view and select from a list of all the work lines that are related to their current task.</span></span> <span data-ttu-id="236bd-107">Ez a funkció segítséget nyújt a dolgozóknak a kitárolási folyamat optimalizálásában.</span><span class="sxs-lookup"><span data-stu-id="236bd-107">This capability can help workers optimize their picking sequence.</span></span> <span data-ttu-id="236bd-108">A szolgáltatás olyan beállításokat tartalmaz, amelyek a szokásos **Kihagyás** gombot cserélik le, hogy a dolgozók rögzített sorrendben, egyenként haladjanak végig a sorokon.</span><span class="sxs-lookup"><span data-stu-id="236bd-108">The feature provides options that replace the standard **Skip** button that lets workers cycle through the lines one at a time, in a fixed order.</span></span> <span data-ttu-id="236bd-109">(Ugyanakkor a gomb használatának lehetősége továbbra is elérhető.)</span><span class="sxs-lookup"><span data-stu-id="236bd-109">(However, the option to use that button is still available.)</span></span>

<span data-ttu-id="236bd-110">Az adminisztrátorok egyenként állíthatják be az egyes menüelemeket annak meghatározására, hogy a raktári alkalmazás milyen módon jeleníti meg a kitárolási sor áttekintését.</span><span class="sxs-lookup"><span data-stu-id="236bd-110">Admins can configure each menu item individually to control how, when, and where the warehouse app presents the pick line overview.</span></span>

## <a name="turn-on-the-work-pick-line-overview-feature"></a><span data-ttu-id="236bd-111">A Munkakitárolási-sor áttekintése funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="236bd-111">Turn on the Work pick line overview feature</span></span>

<span data-ttu-id="236bd-112">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="236bd-112">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="236bd-113">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="236bd-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="236bd-114">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="236bd-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="236bd-115">**Modul:** _Raktárkezelés_</span><span class="sxs-lookup"><span data-stu-id="236bd-115">**Module:** _Warehouse management_</span></span>
- <span data-ttu-id="236bd-116">**Funkció neve:** _Munkakitárolási-sor áttekintése_</span><span class="sxs-lookup"><span data-stu-id="236bd-116">**Feature name:** _Work pick line overview_</span></span>

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a><span data-ttu-id="236bd-117">Menüelemek konfigurálása az összes munkasor listájának megjelenítéséhez</span><span class="sxs-lookup"><span data-stu-id="236bd-117">Configure menu items to show a list of all work lines</span></span>

<span data-ttu-id="236bd-118">Mobileszköz-menüelem beállításához a kitárolási sor áttekintésének biztosításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="236bd-118">To set up a mobile device menu item to provide a pick line overview, follow these steps.</span></span>

1. <span data-ttu-id="236bd-119">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="236bd-119">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="236bd-120">Válasszon ki vagy hozzon létre a kitárolási munkához kapcsolódó menüelemet, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="236bd-120">Select or create a menu item that is related to picking work, and set the following values:</span></span>

    - <span data-ttu-id="236bd-121">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="236bd-121">**Mode:** *Work*</span></span>
    - <span data-ttu-id="236bd-122">**Meglévő munka használata:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="236bd-122">**Use existing work:** *Yes*</span></span>
    - <span data-ttu-id="236bd-123">**Irányító:** *Felhasználó által irányított* vagy *Rendszer által irányított*</span><span class="sxs-lookup"><span data-stu-id="236bd-123">**Directed by:** *User directed* or *System directed*</span></span>

    <span data-ttu-id="236bd-124">A menüelemek létrehozásával és a **Mobileszköz menüpontjai** lapján elérhető különböző beállításokkal kapcsolatos további tudnivalókat lásd: [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="236bd-124">For more information about how to create menu items and use the various settings that are available on the **Mobile device menu items** page, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>

1. <span data-ttu-id="236bd-125">Az **Általános** gyorslapon konfigurálja a szolgáltatást úgy, hogy a **Munkasorok listájának megjelenítése** mezőt a következő értékek valamelyikére állítja:</span><span class="sxs-lookup"><span data-stu-id="236bd-125">On the **General** FastTab, configure the feature by setting the **Show work line list** field to one of the following values:</span></span>

    - <span data-ttu-id="236bd-126">**Csak kérés alapján jelenik meg** – A dolgozók választhatják a kitárolási sor listája megjelenítését ha az **Ugrás a következőre** gombot választják a raktári alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="236bd-126">**Show only upon request** – Workers can choose to view the pick line list by selecting the **Skip to** button in the warehouse app.</span></span>
    - <span data-ttu-id="236bd-127">**Megjelenítés minden kitárolás kezdetén** – A dolgozók minden alkalommal látják a listát, amikor egy kitárolási sort kezdenek vagy fejeznek be.</span><span class="sxs-lookup"><span data-stu-id="236bd-127">**Show at the start of every pick** – Workers see the list every time that they start or finish a pick line.</span></span> <span data-ttu-id="236bd-128">A listát újra megtekinthetik, ha kiválasztják az **Ugrás a következőre** gombot a raktári alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="236bd-128">They can also view the list again by selecting the **Skip to** button in the warehouse app.</span></span>
    - <span data-ttu-id="236bd-129">**Megjelenítés csak az első kitárolás kezdetén**: A dolgozók a listát minden új kitárolási munka indításakor látják, de az egyes sorok után nem.</span><span class="sxs-lookup"><span data-stu-id="236bd-129">**Show at the start of the first pick only** – Workers see the list every time that they start new picking work, but not after each line.</span></span> <span data-ttu-id="236bd-130">A listát újra megtekinthetik, ha kiválasztják az **Ugrás a következőre** gombot a raktári alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="236bd-130">They can also view the list again by selecting the **Skip to** button in the warehouse app.</span></span>
    - <span data-ttu-id="236bd-131">**Soha ne jelenítse meg** – A szokásos **Kihagyás** gomb látható a raktári alkalmazásban, és a munkasorok listájának megjelenítése ki van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="236bd-131">**Never show** – The standard **Skip** button appears in the warehouse app, and display of the work line list is turned off.</span></span> <span data-ttu-id="236bd-132">A **Kihagyás** gombbal a dolgozók egy rögzített sorrendben válthatnak a sorok között.</span><span class="sxs-lookup"><span data-stu-id="236bd-132">The **Skip** button lets workers cycle through the lines one at a time, in a fixed order.</span></span> <span data-ttu-id="236bd-133">A listán tetszőleges számú alkalommal is végighaladhatnak, amíg az összes sort fel nem dolgozzák.</span><span class="sxs-lookup"><span data-stu-id="236bd-133">They can also cycle through the list as many times as they require, until all lines have been processed.</span></span>

1. <span data-ttu-id="236bd-134">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="236bd-134">On the Action Pane, select **Save**.</span></span>

    <span data-ttu-id="236bd-135">Ha a **Munkasorok listájának megjelenítése** mezőt bármilyen a *Soha ne jelenítse meg* értéktől eltérő a Műveleti panel **Mezőlista** gombja elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="236bd-135">If you set the **Show work line list** field to any value except *Never show*, the **Field list** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="236bd-136">A Műveleti ablaktáblán válassza ki a **Mezőlista** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="236bd-136">On the Action Pane, select **Field list**.</span></span>
1. <span data-ttu-id="236bd-137">A **Mezőlista** lapon konfigurálja azokat az adatokat, amelyeket a raktári alkalmazás a lista minden sorához megjelenít.</span><span class="sxs-lookup"><span data-stu-id="236bd-137">On the **Field list** page, configure the information that the warehouse app shows for each line in the list.</span></span>

    - <span data-ttu-id="236bd-138">Az **Elsődleges vezérlés** mező értéke mindig *LineNum*.</span><span class="sxs-lookup"><span data-stu-id="236bd-138">The **Primary control** field is always set to *LineNum*.</span></span> <span data-ttu-id="236bd-139">Ennek megfelelően a lista minden sora egy sorszámmal kezdődik.</span><span class="sxs-lookup"><span data-stu-id="236bd-139">Therefore, each row in the list begins with a line number.</span></span>
    - <span data-ttu-id="236bd-140">A többi **Megjelenített mező** mezővel legfeljebb hét további megjeleníthető mezőt adhat hozzá igény szerint.</span><span class="sxs-lookup"><span data-stu-id="236bd-140">Use the remaining **Display field** fields to add up to seven additional display fields, as you require.</span></span> <span data-ttu-id="236bd-141">Mindegyik **Megjelenített mező** mezőben válassza ki a munkasor mező nevét.</span><span class="sxs-lookup"><span data-stu-id="236bd-141">In each **Display field** field, select the name of a work line field.</span></span> <span data-ttu-id="236bd-142">Ekkor minden sor megjelenít egy értéket a mezőben.</span><span class="sxs-lookup"><span data-stu-id="236bd-142">Each line will then show a value for that field.</span></span> <span data-ttu-id="236bd-143">Az értékek az itt kiválasztott sorrendben jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="236bd-143">The values will be shown in the order that you select here.</span></span> <span data-ttu-id="236bd-144">Ha nem szükséges mind a hét érték, akkor üresen hagyhat egyes **Megjelenítendő mező** mezőket.</span><span class="sxs-lookup"><span data-stu-id="236bd-144">You can leave some of the **Display field** fields blank if you don't require all seven values.</span></span>

1. <span data-ttu-id="236bd-145">A művelet ablaktáblán válassza a **Mentés** elemet., majd zárja be a **Mezőlista** oldalt.</span><span class="sxs-lookup"><span data-stu-id="236bd-145">On the Action Pane, select **Save**, and then close the **Field list** page.</span></span>
