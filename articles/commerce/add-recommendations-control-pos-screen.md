---
title: Ajánlatok hozzáadása a tranzakciós képernyőhöz
description: Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 Commerce képernyő-elrendezés tervezőjének használatával.
author: bebeale
manager: AnnBe
ms.date: 03/12/20
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
ms.openlocfilehash: 9117f398ee1d9edbd3aee9bed366eea225964184
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127675"
---
# <a name="add-recommendations-to-the-transaction-screen"></a><span data-ttu-id="56566-103">Ajánlatok hozzáadása a tranzakciós képernyőhöz</span><span class="sxs-lookup"><span data-stu-id="56566-103">Add recommendations to the transaction screen</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="56566-104">Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 Commerce képernyő-elrendezés tervezőjének használatával.</span><span class="sxs-lookup"><span data-stu-id="56566-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="56566-105">A termék ajánlásaival kapcsolatos további tudnivalók: [Termékajánlások a POS-dokumentációban](product.md).</span><span class="sxs-lookup"><span data-stu-id="56566-105">For more information about product recommendations, read the  [product recommendations on POS documentation](product.md).</span></span>


<span data-ttu-id="56566-106">A Commerce használata esetén megjeleníthet termékajánlásokat a pénztáreszközön.</span><span class="sxs-lookup"><span data-stu-id="56566-106">You can display product recommendations on your POS device when you use Commerce.</span></span> <span data-ttu-id="56566-107">Termékajánlások megjelenítéséhez vezérlőt kell hozzáadni a tranzakciós képernyőhöz a képernyő-elrendezés tervezőjének segítségével.</span><span class="sxs-lookup"><span data-stu-id="56566-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="56566-108">Az Elrendezéstervező megnyitása</span><span class="sxs-lookup"><span data-stu-id="56566-108">Open Layout designer</span></span>

1. <span data-ttu-id="56566-109">Lépjen a **Kiskereskedelem és kereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztár** &gt; **Képernyő-elrendezések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="56566-109">Go to **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="56566-110">A vezérlővel bővíteni kívánt képernyő megkereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="56566-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="56566-111">Például szűrjön a **Képernyő-elrendezés azonosítója** mezőre az **F2CP16:9M** érték használatával.</span><span class="sxs-lookup"><span data-stu-id="56566-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="56566-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="56566-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="56566-113">Például válassza a **Név: F2CP16:9M Képernyő-elrendezés azonosítója: F2CP16:9M** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="56566-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="56566-114">Kattintson az **Elrendezéstervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="56566-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="56566-115">Kövesse az utasításokat az elrendezéstervező elindításához.</span><span class="sxs-lookup"><span data-stu-id="56566-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="56566-116">Amikor a rendszer kéri a hitelesítő adatokat, adja meg ugyanazokat a hitelesítő adatokat, amelyekkel az Elrendezéstervezőt a **Képernyő-elrendezések** oldalról elindította.</span><span class="sxs-lookup"><span data-stu-id="56566-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="56566-117">A bejelentkezéstkor az alábbihoz hasonló oldal jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="56566-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="56566-118">Az elrendezés a bolthoz végzett testreszabásoktól függően eltérő lesz.</span><span class="sxs-lookup"><span data-stu-id="56566-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="56566-119">[![Elrendezéstervező](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="56566-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="56566-120">Válasszon ki egy megjelenítési beállítást</span><span class="sxs-lookup"><span data-stu-id="56566-120">Choose a display option</span></span>

<span data-ttu-id="56566-121">Két konfigurációs lehetőség áll rendelkezlésre.</span><span class="sxs-lookup"><span data-stu-id="56566-121">There are two configurations options available.</span></span> <span data-ttu-id="56566-122">Válassza azt a lehetőséget, amely a legjobban illik a bolthoz, és kövesse a további utasításokat a vezérlő beállításának befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="56566-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="56566-123">A két lehetőség:</span><span class="sxs-lookup"><span data-stu-id="56566-123">The two options are:</span></span>

- <span data-ttu-id="56566-124">Ajánlások mindig láthatók.</span><span class="sxs-lookup"><span data-stu-id="56566-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="56566-125">Az **Ajánlások** lap megjelenik a rácsban a képernyő jobb oldalán.</span><span class="sxs-lookup"><span data-stu-id="56566-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="56566-126">Az ajánlások mindig láthatóvá tétele</span><span class="sxs-lookup"><span data-stu-id="56566-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="56566-127">Csökkentse a tranzakciós sorok részletei terület magasságát úgy, hogy a tőle balra eső ügyfélpanellel egyforma magas legyen.</span><span class="sxs-lookup"><span data-stu-id="56566-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="56566-128">[![A tranzakciós sorok részletezési területének magassága csökkentve](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="56566-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="56566-129">A bal oldali menüből húzza az ajánlások vezérlőt a tranzakciós sor részletei terület és a tranzakciós képernyőn lent középen látható gombrács közé.</span><span class="sxs-lookup"><span data-stu-id="56566-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="56566-130">Méretezze át a vezérlőt, hogy elférjen.</span><span class="sxs-lookup"><span data-stu-id="56566-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="56566-131">[![Javaslatok vezérlő az elrendezéshez adva](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="56566-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="56566-132">Az **X** gombra kattintva zárja be az Elrendezéstervezőt.</span><span class="sxs-lookup"><span data-stu-id="56566-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="56566-133">A Commerce-ben ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem és kereskedelem informatika** &gt; **Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="56566-133">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="56566-134">Válassza az **1090, Pénztárgépek** elemet.</span><span class="sxs-lookup"><span data-stu-id="56566-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="56566-135">Kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="56566-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="56566-136">Egy Ajánlások lap hozzáadása a képernyő jobb oldalán látható gombrácshoz</span><span class="sxs-lookup"><span data-stu-id="56566-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="56566-137">Kattintson a jobb gombbal az oldal jobb oldalán található gombrács utolsó lapja alatti üres területre.</span><span class="sxs-lookup"><span data-stu-id="56566-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="56566-138">Kattintson a **Testreszabás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="56566-138">Click **Customize**.</span></span>

    <span data-ttu-id="56566-139">[![Testreszabás – Lapvezérlő párbeszédpanel](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="56566-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="56566-140">Kattintson az **Új lap** elemre.</span><span class="sxs-lookup"><span data-stu-id="56566-140">Click **New tab**.</span></span>
4. <span data-ttu-id="56566-141">Keresse meg a most felvett új lapot.</span><span class="sxs-lookup"><span data-stu-id="56566-141">Find the new tab that you just added.</span></span> <span data-ttu-id="56566-142">Ehhez lehet, hogy le kell görgetnie.</span><span class="sxs-lookup"><span data-stu-id="56566-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="56566-143">A **Tartalom** legördülő menüben válassza az **Ajánlott termékek** elemet.</span><span class="sxs-lookup"><span data-stu-id="56566-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="56566-144">[![Javasolt termékek kiválasztása a Tartalmak mezőben](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="56566-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="56566-145">A **Címke** mezőben adjon meg egy nevet a javaslatok lapnak Például „Javasolt termékek”.</span><span class="sxs-lookup"><span data-stu-id="56566-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="56566-146">A **Kép** mezőben válassza ki a lapon megjelenítendő képet.</span><span class="sxs-lookup"><span data-stu-id="56566-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="56566-147">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="56566-147">Click **OK**.</span></span> <span data-ttu-id="56566-148">Az új lap megjelenik a gombrácsban.</span><span class="sxs-lookup"><span data-stu-id="56566-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="56566-149">Az **X** gombra kattintva zárja be az Elrendezéstervezőt.</span><span class="sxs-lookup"><span data-stu-id="56566-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="56566-150">A Commerce-ben ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem és kereskedelem informatika** &gt; **Elosztási ütemezés** pontra.</span><span class="sxs-lookup"><span data-stu-id="56566-150">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="56566-151">Válassza az **1090, Pénztárgépek** elemet.</span><span class="sxs-lookup"><span data-stu-id="56566-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="56566-152">Kattintson a **Futtatás most** elemre.</span><span class="sxs-lookup"><span data-stu-id="56566-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56566-153">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="56566-153">Additional resources</span></span>

[<span data-ttu-id="56566-154">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="56566-154">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="56566-155">ADLS engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="56566-155">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="56566-156">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="56566-156">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="56566-157">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="56566-157">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="56566-158">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="56566-158">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="56566-159">Ajánlat listáinak hozzáadása egy e-Commerce webhelyhez</span><span class="sxs-lookup"><span data-stu-id="56566-159">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="56566-160">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="56566-160">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="56566-161">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="56566-161">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="56566-162">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="56566-162">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="56566-163">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="56566-163">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="56566-164">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="56566-164">Product recommendations FAQ</span></span>](faq-recommendations.md)
