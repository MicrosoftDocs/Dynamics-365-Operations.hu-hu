---
title: Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez
description: Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Retail képernyő-elrendezés tervezőjének használatával.
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f17da3db6fbc19548544a0c6c090a0b6db093673
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606849"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="52f92-103">Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez</span><span class="sxs-lookup"><span data-stu-id="52f92-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="52f92-104">A termékajánló szolgáltatás jelenlegi verzióját eltávolítjuk, mivel ezt a funkciót jobb algoritmussal és újabb kiskereskedelmi orientált képességekkel újratervezzük.</span><span class="sxs-lookup"><span data-stu-id="52f92-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="52f92-105">További információ: [Eltávolított vagy elavult funkciók](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="52f92-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span>

<span data-ttu-id="52f92-106">Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Retail képernyő-elrendezés tervezőjének használatával.</span><span class="sxs-lookup"><span data-stu-id="52f92-106">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="52f92-107">A Microsoft Dynamics 365 for Retail használata esetén megjeleníthet termékajánlásokat a pénztáreszközön.</span><span class="sxs-lookup"><span data-stu-id="52f92-107">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="52f92-108">Az *Ajánlások* olyan elemek, amelyek érdekelhetik a vevőt a vásárlási előzmények alapján, a kívánságlistájukon levő elemek alapján, illetve olyan elemek alapján, amelyeket más felhasználók vásároltak meg online vagy hagyományos üzletekben.</span><span class="sxs-lookup"><span data-stu-id="52f92-108">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="52f92-109">Termékajánlások megjelenítéséhez vezérlőt kell hozzáadni a tranzakciós képernyőhöz a képernyő-elrendezés tervezőjének segítségével.</span><span class="sxs-lookup"><span data-stu-id="52f92-109">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="52f92-110">Az Elrendezéstervező megnyitása</span><span class="sxs-lookup"><span data-stu-id="52f92-110">Open Layout designer</span></span>

1. <span data-ttu-id="52f92-111">Lépjen a **Kiskereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztár** &gt; **Képernyő-elrendezések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52f92-111">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="52f92-112">A vezérlővel bővíteni kívánt képernyő megkereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="52f92-112">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="52f92-113">Például szűrjön a **Képernyő-elrendezés azonosítója** mezőre az **F2CP16:9M** érték használatával.</span><span class="sxs-lookup"><span data-stu-id="52f92-113">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="52f92-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="52f92-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="52f92-115">Például válassza a **Név: F2CP16:9M Képernyő-elrendezés azonosítója: F2CP16:9M** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52f92-115">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="52f92-116">Kattintson az **Elrendezéstervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="52f92-116">Click **Layout designer**.</span></span>
5. <span data-ttu-id="52f92-117">Kövesse az utasításokat az elrendezéstervező elindításához.</span><span class="sxs-lookup"><span data-stu-id="52f92-117">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="52f92-118">Amikor a rendszer kéri a hitelesítő adatokat, adja meg ugyanazokat a hitelesítő adatokat, amelyekkel az Elrendezéstervezőt a **Képernyő-elrendezések** oldalról elindította.</span><span class="sxs-lookup"><span data-stu-id="52f92-118">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="52f92-119">A bejelentkezéstkor az alábbihoz hasonló oldal jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="52f92-119">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="52f92-120">Az elrendezés a bolthoz végzett testreszabásoktól függően eltérő lesz.</span><span class="sxs-lookup"><span data-stu-id="52f92-120">The layout will be different depending on the customizations that were made for your store.</span></span>

    <span data-ttu-id="52f92-121">[![Elrendezéstervező](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="52f92-121">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="52f92-122">Válasszon ki egy megjelenítési beállítást</span><span class="sxs-lookup"><span data-stu-id="52f92-122">Choose a display option</span></span>

<span data-ttu-id="52f92-123">Két konfigurációs lehetőség áll rendelkezlésre.</span><span class="sxs-lookup"><span data-stu-id="52f92-123">There are two configurations options available.</span></span> <span data-ttu-id="52f92-124">Válassza azt a lehetőséget, amely a legjobban illik a bolthoz, és kövesse a további utasításokat a vezérlő beállításának befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="52f92-124">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="52f92-125">A két lehetőség:</span><span class="sxs-lookup"><span data-stu-id="52f92-125">The two options are:</span></span>

- <span data-ttu-id="52f92-126">Ajánlások mindig láthatók.</span><span class="sxs-lookup"><span data-stu-id="52f92-126">Recommendations are always visible.</span></span>
- <span data-ttu-id="52f92-127">Az **Ajánlások** lap megjelenik a rácsban a képernyő jobb oldalán.</span><span class="sxs-lookup"><span data-stu-id="52f92-127">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="52f92-128">Az ajánlások mindig láthatóvá tétele</span><span class="sxs-lookup"><span data-stu-id="52f92-128">Make recommendations always visible</span></span>

1. <span data-ttu-id="52f92-129">Csökkentse a tranzakciós sorok részletei terület magasságát úgy, hogy a tőle balra eső ügyfélpanellel egyforma magas legyen.</span><span class="sxs-lookup"><span data-stu-id="52f92-129">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>

    <span data-ttu-id="52f92-130">[![A tranzakciós sorok részletezési területének magassága csökkentve](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="52f92-130">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="52f92-131">A bal oldali menüből húzza az ajánlások vezérlőt a tranzakciós sor részletei terület és a tranzakciós képernyőn lent középen látható gombrács közé.</span><span class="sxs-lookup"><span data-stu-id="52f92-131">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="52f92-132">Méretezze át a vezérlőt, hogy elférjen.</span><span class="sxs-lookup"><span data-stu-id="52f92-132">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="52f92-133">[![Javaslatok vezérlő az elrendezéshez adva](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="52f92-133">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>

3. <span data-ttu-id="52f92-134">Az **X** gombra kattintva zárja be az Elrendezéstervezőt.</span><span class="sxs-lookup"><span data-stu-id="52f92-134">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="52f92-135">A Dynamics 365 for Retail alkalmazásban lépjen a **Kiskereskedelem** &gt; **Kiskereskedelem IT** &gt; **Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="52f92-135">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="52f92-136">Válassza az  **1090, Pénztárgépek** elemet.</span><span class="sxs-lookup"><span data-stu-id="52f92-136">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="52f92-137">Kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="52f92-137">Click **Run now**.</span></span>

### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="52f92-138">Egy Ajánlások lap hozzáadása a képernyő jobb oldalán látható gombrácshoz</span><span class="sxs-lookup"><span data-stu-id="52f92-138">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="52f92-139">Kattintson a jobb gombbal az oldal jobb oldalán található gombrács utolsó lapja alatti üres területre.</span><span class="sxs-lookup"><span data-stu-id="52f92-139">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2. <span data-ttu-id="52f92-140">Kattintson a **Testreszabás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="52f92-140">Click **Customize**.</span></span>

    <span data-ttu-id="52f92-141">[![Testreszabás – Lapvezérlő párbeszédpanel](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="52f92-141">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="52f92-142">Kattintson az **Új lap** elemre.</span><span class="sxs-lookup"><span data-stu-id="52f92-142">Click **New tab**.</span></span>
4. <span data-ttu-id="52f92-143">Keresse meg a most felvett új lapot.</span><span class="sxs-lookup"><span data-stu-id="52f92-143">Find the new tab that you just added.</span></span> <span data-ttu-id="52f92-144">Ehhez lehet, hogy le kell görgetnie.</span><span class="sxs-lookup"><span data-stu-id="52f92-144">You may need to scroll down.</span></span>
5. <span data-ttu-id="52f92-145">A **Tartalom** legördülő menüben válassza az **Ajánlott termékek** elemet.</span><span class="sxs-lookup"><span data-stu-id="52f92-145">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="52f92-146">[![Javasolt termékek kiválasztása a Tartalmak mezőben](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="52f92-146">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="52f92-147">A **Címke** mezőben adjon meg egy nevet a javaslatok lapnak Például „Javasolt termékek”.</span><span class="sxs-lookup"><span data-stu-id="52f92-147">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="52f92-148">A **Kép** mezőben válassza ki a lapon megjelenítendő képet.</span><span class="sxs-lookup"><span data-stu-id="52f92-148">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="52f92-149">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="52f92-149">Click **OK**.</span></span> <span data-ttu-id="52f92-150">Az új lap megjelenik a gombrácsban.</span><span class="sxs-lookup"><span data-stu-id="52f92-150">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="52f92-151">Az **X** gombra kattintva zárja be az Elrendezéstervezőt.</span><span class="sxs-lookup"><span data-stu-id="52f92-151">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="52f92-152">A Dynamics 365 for Retail alkalmazásban lépjen a **Kiskereskedelem** &gt; **Kiskereskedelem IT** &gt; **Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="52f92-152">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="52f92-153">A listában válassza a **1090, Pénztárgépek** elemet.</span><span class="sxs-lookup"><span data-stu-id="52f92-153">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="52f92-154">Kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="52f92-154">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52f92-155">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="52f92-155">Additional resources</span></span>

[<span data-ttu-id="52f92-156">Személyre szabott termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="52f92-156">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)
