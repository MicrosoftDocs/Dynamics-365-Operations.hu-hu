---
title: "Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján"
description: "Ez a témakör ismerteti, hogyan adható hozzá ajánlások vezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Retail képernyő-elrendezés tervezőjének használatával."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 86dce19011b98dace5c5df72280180e0b1c8bbaa
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="62e4c-103">Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján</span><span class="sxs-lookup"><span data-stu-id="62e4c-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="62e4c-104">Ez a témakör ismerteti, hogyan adható hozzá ajánlások vezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Retail képernyő-elrendezés tervezőjének használatával.</span><span class="sxs-lookup"><span data-stu-id="62e4c-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="62e4c-105">A Microsoft Dynamics 365 for Retail használata esetén megjeleníthet termékajánlásokat a POS-eszközön.</span><span class="sxs-lookup"><span data-stu-id="62e4c-105">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="62e4c-106">Az *Ajánlások* olyan elemek, amelyek érdekelhetik a vevőt a vásárlási előzmények alapján, a kívánságlistájukon levő elemek alapján, illetve olyan elemek alapján, amelyeket más felhasználók vásároltak meg online vagy hagyományos üzletekben.</span><span class="sxs-lookup"><span data-stu-id="62e4c-106">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="62e4c-107">Termékajánlások megjelenítéséhez vezérlőt kell hozzáadni a tranzakciós képernyőhöz a képernyő-elrendezés tervezőjének segítségével.</span><span class="sxs-lookup"><span data-stu-id="62e4c-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="62e4c-108">Az Elrendezéstervező megnyitása</span><span class="sxs-lookup"><span data-stu-id="62e4c-108">Open Layout designer</span></span>
1.  <span data-ttu-id="62e4c-109">Lépjen a **Kiskereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztár** &gt; **Képernyő-elrendezések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="62e4c-110">A vezérlővel bővíteni kívánt képernyő megkereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="62e4c-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="62e4c-111">Például szűrjön a **Képernyő-elrendezés azonosítója** mezőre „F2CP16:9M” érték használatával.</span><span class="sxs-lookup"><span data-stu-id="62e4c-111">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="62e4c-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="62e4c-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="62e4c-113">Például válassza a „Név: F2CP16:9M Képernyő-elrendezés azonosítója: F2CP16:9M” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="62e4c-113">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="62e4c-114">Kattintson az **Elrendezéstervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-114">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="62e4c-115">Kövesse az utasításokat az elrendezéstervező elindításához.</span><span class="sxs-lookup"><span data-stu-id="62e4c-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="62e4c-116">Amikor a rendszer kéri a hitelesítő adatokat, adja meg ugyanazokat a hitelesítő adatokat, amelyekkel az Elrendezéstervezőt a **Képernyő-elrendezések** oldalról elindította.</span><span class="sxs-lookup"><span data-stu-id="62e4c-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="62e4c-117">A bejelentkezéstkor az alábbihoz hasonló oldal jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="62e4c-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="62e4c-118">Az elrendezés a bolthoz végzett testreszabásoktól függően eltérő lesz.</span><span class="sxs-lookup"><span data-stu-id="62e4c-118">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="62e4c-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Válasszon megjelenítési beállítást</span><span class="sxs-lookup"><span data-stu-id="62e4c-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="62e4c-120">Két konfigurációs lehetőség áll rendelkezlésre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-120">There are two configurations options available.</span></span> <span data-ttu-id="62e4c-121">Válassza azt a lehetőséget, amely a legjobban illik a bolthoz, és kövesse a további utasításokat a vezérlő beállításának befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="62e4c-121">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="62e4c-122">A két lehetőség:</span><span class="sxs-lookup"><span data-stu-id="62e4c-122">The two options are:</span></span>
-   <span data-ttu-id="62e4c-123">Ajánlások mindig láthatók.</span><span class="sxs-lookup"><span data-stu-id="62e4c-123">Recommendations are always visible.</span></span>
-   <span data-ttu-id="62e4c-124">Az **Ajánlások** lap megjelenik a rácsban a képernyő jobb oldalán.</span><span class="sxs-lookup"><span data-stu-id="62e4c-124">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="62e4c-125">Ajánlások mindig láthatóvá tétele</span><span class="sxs-lookup"><span data-stu-id="62e4c-125">To make recommendations always visible</span></span>

1.  <span data-ttu-id="62e4c-126">Csökkentse a tranzakciós sorok részletei terület magasságát úgy, hogy a tőle balra eső ügyfélpanellel egyforma magas legyen.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="62e4c-126">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="62e4c-127">A bal oldali menüből húzza az ajánlások vezérlőt a tranzakciós sor részletei terület és a tranzakciós képernyőn lent középen látható gombrács közé.</span><span class="sxs-lookup"><span data-stu-id="62e4c-127">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="62e4c-128">Méretezze át a vezérlőt, hogy elférjen.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="62e4c-128">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="62e4c-129">Az **X** gombra kattintva zárja be az Elrendezéstervezőt.</span><span class="sxs-lookup"><span data-stu-id="62e4c-129">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="62e4c-130">A Dynamics 365 for Retailben lépjen a **Kiskereskedelem** &gt; **Kiskereskedelmi IT** &gt; **Elosztási ütemezések** elemre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-130">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="62e4c-131">Válassza az **1090, Pénztárgépek** elemet.</span><span class="sxs-lookup"><span data-stu-id="62e4c-131">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="62e4c-132">Kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-132">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="62e4c-133">Az Ajánlások lap hozzáadása a képernyő jobb oldalán látható gombrácshoz</span><span class="sxs-lookup"><span data-stu-id="62e4c-133">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="62e4c-134">Kattintson a jobb gombbal az oldal jobb oldalán található gombrács utolsó lapja alatti üres területre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-134">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="62e4c-135">Kattintson a **Testreszabás** elemre.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="62e4c-135">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="62e4c-136">Kattintson az **Új lap** elemre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-136">Click **New tab**.</span></span>
4.  <span data-ttu-id="62e4c-137">Keresse meg a most felvett új lapot.</span><span class="sxs-lookup"><span data-stu-id="62e4c-137">Find the new tab that you just added.</span></span> <span data-ttu-id="62e4c-138">Ehhez lehet, hogy le kell görgetnie.</span><span class="sxs-lookup"><span data-stu-id="62e4c-138">You may need to scroll down.</span></span>
5.  <span data-ttu-id="62e4c-139">A **Tartalom** legördülő menüben válassza az **Ajánlott termékek** elemet.</span><span class="sxs-lookup"><span data-stu-id="62e4c-139">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="62e4c-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="62e4c-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="62e4c-141">A **Címke** mezőbe írjon be egy nevet az ajánlások lapnak. Írja be például ezt: Ajánlott termékek.</span><span class="sxs-lookup"><span data-stu-id="62e4c-141">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="62e4c-142">A **Kép** mezőben válassza ki a lapon megjelenítendő képet.</span><span class="sxs-lookup"><span data-stu-id="62e4c-142">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="62e4c-143">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="62e4c-143">Click **OK**.</span></span> <span data-ttu-id="62e4c-144">Az új lap megjelenik a gombrácsban.</span><span class="sxs-lookup"><span data-stu-id="62e4c-144">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="62e4c-145">Az **X** gombra kattintva zárja be az Elrendezéstervezőt.</span><span class="sxs-lookup"><span data-stu-id="62e4c-145">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="62e4c-146">A Dynamics 365 for Retailben lépjen a **Kiskereskedelem** &gt; **Kiskereskedelmi IT** &gt; **Elosztási ütemezések** elemre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-146">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="62e4c-147">Válassza az **1090, Pénztárgépek** elemet.</span><span class="sxs-lookup"><span data-stu-id="62e4c-147">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="62e4c-148">Kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="62e4c-148">Click **Run now**.</span></span>


<a name="see-also"></a><span data-ttu-id="62e4c-149">Lásd még</span><span class="sxs-lookup"><span data-stu-id="62e4c-149">See also</span></span>
--------

[<span data-ttu-id="62e4c-150">Személyre szabott termékajánlások áttekintése</span><span class="sxs-lookup"><span data-stu-id="62e4c-150">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




