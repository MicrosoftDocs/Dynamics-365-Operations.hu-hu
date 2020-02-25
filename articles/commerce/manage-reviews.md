---
title: Minősítések és értékelések kezelése
description: Ez a témakör azt mutatja be, hogyan lehet kezelni a minősítéseket és értékeléseket a Microsoft Dynamics 365 Commerce minősítések és értékelések moderálása eszközével.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027242"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="a0484-103">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="a0484-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a0484-104">Ez a témakör azt mutatja be, hogyan lehet kezelni a minősítéseket és értékeléseket a Microsoft Dynamics 365 Commerce minősítések és értékelések moderálása eszközével.</span><span class="sxs-lookup"><span data-stu-id="a0484-104">This topic explains how to manage ratings and reviews by using the Microsoft Dynamics 365 Commerce ratings and reviews moderation tool.</span></span>

## <a name="overview"></a><span data-ttu-id="a0484-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="a0484-105">Overview</span></span>

<span data-ttu-id="a0484-106">A Dynamics 365 Commerce a Microsoft Azure kognitív szolgáltatását használja a szöveg automatikus moderálására a profán szavak kivonásával.</span><span class="sxs-lookup"><span data-stu-id="a0484-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="a0484-107">Ezenkívül a moderátorok a minősítések és a értékelések moderálása eszközt a következő manuális feladatokhoz használhatják:</span><span class="sxs-lookup"><span data-stu-id="a0484-107">In addition, moderators can use the ratings and reviews moderation tool for the following manual tasks:</span></span>

- <span data-ttu-id="a0484-108">Értékelések moderálása válaszadással vagy eltávolításukkal.</span><span class="sxs-lookup"><span data-stu-id="a0484-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="a0484-109">Vevői értékelések törlése a vevő kérésére.</span><span class="sxs-lookup"><span data-stu-id="a0484-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="a0484-110">Minősítések és értékelése tömeges importálása egy Microsoft Power BI sablonba hogy elemezhetők legyenek a minősítések és a vélemények trendjei.</span><span class="sxs-lookup"><span data-stu-id="a0484-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="access-ratings-and-reviews-moderation-features"></a><span data-ttu-id="a0484-111">A minősítések és értékelések moderációs funkcióinak elérése</span><span class="sxs-lookup"><span data-stu-id="a0484-111">Access ratings and reviews moderation features</span></span>

<span data-ttu-id="a0484-112">Az e-Commerce webhelykezelő eszköz minősítések és ellenőrzések moderálási szolgáltatásainak eléréséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-112">To access ratings and reviews moderation features in the e-Commerce site management tool, follow these steps.</span></span>

1. <span data-ttu-id="a0484-113">Jelentkezzen be a [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="a0484-113">Sign in to [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="a0484-114">Nyissa meg azt a projektet, amely tartalmazza a projektet, ahol az e-kereskedelmet inicializálni kívánja.</span><span class="sxs-lookup"><span data-stu-id="a0484-114">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="a0484-115">A **Környezetek** szakaszban válassza ki a környezetet.</span><span class="sxs-lookup"><span data-stu-id="a0484-115">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="a0484-116">A **Környezeti funkciók** területen kattintson a**Kiskereskedelem kezelése** elemre.</span><span class="sxs-lookup"><span data-stu-id="a0484-116">Under **Environment features**, select **Retail manage**.</span></span>
1. <span data-ttu-id="a0484-117">Az **e-Commerce** lap **Hivatkozások** területén válassza az **e-Commerce webhelykezelő eszköz** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-117">On the **e-Commerce** tab under **Links**, select **e-Commerce Site management tool**.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="a0484-118">Értékelés elolvasása</span><span class="sxs-lookup"><span data-stu-id="a0484-118">Read a review</span></span> 

1. <span data-ttu-id="a0484-119">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-119">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="a0484-120">A lap jobb felső részén található keresési mező használatával szűrheti a megjelenített értékeléseket a termék azonosítója, a terméknév vagy az értékelés szövege szerint.</span><span class="sxs-lookup"><span data-stu-id="a0484-120">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="a0484-121">A további szűrők használatával időszak, minősítés, csatorna vagy probléma állapota szerint korlátozhatja (levett, megválaszolt vagy jelentett) az értékeléseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-121">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Moderálás kezdőoldala](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="a0484-123">Értékelés megválaszolása</span><span class="sxs-lookup"><span data-stu-id="a0484-123">Respond to a review</span></span> 

<span data-ttu-id="a0484-124">Előfordulhat, hogy azok a vevőkk, akik egy terméket megvásároltak, kifejezik elégedettségüket vagy elégedetlenségüket, vagy jelzik, hogy nem értik, hogyan kell használni a terméket.</span><span class="sxs-lookup"><span data-stu-id="a0484-124">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="a0484-125">Moderátorként válaszolhat értékelésekre..</span><span class="sxs-lookup"><span data-stu-id="a0484-125">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="a0484-126">Ez a válasz a az értékeléssel együtt jelenik meg a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a0484-126">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="a0484-127">Az értékelés megválaszolásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-127">To respond to a review, follow these steps.</span></span>

1. <span data-ttu-id="a0484-128">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-128">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="a0484-129">Keresse meg és válassza ki a megválaszolandó értékelést.</span><span class="sxs-lookup"><span data-stu-id="a0484-129">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="a0484-130">A jobb oldali tulajdonságok ablaktáblán válassza a **Válasz hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0484-130">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="a0484-131">Adja meg a válasz szövegét, valamint azt a nevet, amelyet meg kell jeleníteni a válaszadó számára.</span><span class="sxs-lookup"><span data-stu-id="a0484-131">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="a0484-132">Az alapértelmezett válaszadó neve **Moderátor.**</span><span class="sxs-lookup"><span data-stu-id="a0484-132">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="a0484-133">Amikor elkészült, válassza a **Válasz feladása** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-133">When you've finished, select **Post response**.</span></span>

![Válaszolás értékelésre](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="a0484-135">Egy értékelés levétele</span><span class="sxs-lookup"><span data-stu-id="a0484-135">Take down a review</span></span> 

<span data-ttu-id="a0484-136">Előfordulhat, hogy üzleti érdek fűződik ahhoz, hogy a moderátorok eltávolítsanak bizonyos vevői értékeléseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-136">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="a0484-137">Az értékelés levételéhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-137">To take down a review, follow these steps.</span></span>

1. <span data-ttu-id="a0484-138">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-138">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="a0484-139">Keresse meg és válassza ki azt az értékelést, amelyet le kell venni.</span><span class="sxs-lookup"><span data-stu-id="a0484-139">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="a0484-140">A jobb oldali tulajdonságok ablaktáblán válasszon ki egy eltávolítási okot, majd válassza a **Levétel** parancsot.</span><span class="sxs-lookup"><span data-stu-id="a0484-140">In the properties pane on the right, select a takedown reason, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="a0484-141">Vevői értékelések törlése a vevő kérésére</span><span class="sxs-lookup"><span data-stu-id="a0484-141">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="a0484-142">Előfordulhat, hogy a vevők az értékelést és az értékelés adatait véglegesen törölni szeretnék egy e-kereskedelmi webhelyről.</span><span class="sxs-lookup"><span data-stu-id="a0484-142">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="a0484-143">A vevőtől érkező eltávolítási kérelmet fogadó moderátor eltávolíthatja a vevő adatait az értékelés törlése funkcióval.</span><span class="sxs-lookup"><span data-stu-id="a0484-143">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="a0484-144">A vevő adatainak megkereséséhez és törléséhez a moderátornak be kell írnia azt az e-mail-címet, amelyet a vevő a bejelentkezéshez és az értékelés elkészítéséhez használt.</span><span class="sxs-lookup"><span data-stu-id="a0484-144">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="a0484-145">A vevői adatok megkereséséhez és törléséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-145">To find and delete customer data, follow these steps.</span></span>

1. <span data-ttu-id="a0484-146">Nyissa meg a **Kezdőlap \> Értékelések \> Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-146">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="a0484-147">A **Vevő keresése e-mail-cím alapján** mezőben adja meg a felhasználó e-mail-címét, majd válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0484-147">In the **Search for users by email address** field, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="a0484-148">Ha a vevőnek van valamilyen értékelési tevékenysége (például a beküldött értékelések, szavazás más vásárlói értékelések hasznosságával kapcsolatosan vagy megjegyzések egy másik vásárló értékelésére), az eredmények megjelennek.</span><span class="sxs-lookup"><span data-stu-id="a0484-148">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="a0484-149">Mindegyik tételhez tartozik egy **Törlés** gomb.</span><span class="sxs-lookup"><span data-stu-id="a0484-149">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="a0484-150">Minden egyes törlendő elemhez válassza ki a **Törlés** gombot.</span><span class="sxs-lookup"><span data-stu-id="a0484-150">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="a0484-151">Amikor a program megerősítést kér, válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0484-151">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Ügyféladatok törlése](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="a0484-153">Az adatok teljes eltávolítására rendszerből akár 7 napot is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="a0484-153">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="a0484-154">A moderátoroknak tájékoztatniuk kell a vevőket erről a késésről.</span><span class="sxs-lookup"><span data-stu-id="a0484-154">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="a0484-155">Ha a vevő a saját fiókbeállításaiban megváltoztatta a nevét, akkor a keresési eredmények között több elem is megjelenhet.</span><span class="sxs-lookup"><span data-stu-id="a0484-155">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="a0484-156">Ebben az esetben a vevő adatainak teljes törléséhez a moderátornak ki kell választania a **Törlés** lehetőséget minden egyes elemhez.</span><span class="sxs-lookup"><span data-stu-id="a0484-156">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="a0484-157">A minősítések és a értékelések adatainak letöltése</span><span class="sxs-lookup"><span data-stu-id="a0484-157">Download ratings and reviews data</span></span>

<span data-ttu-id="a0484-158">A minősítések és értékelések moderálása eszközzel a moderátorok importálhatják a minősítések és értékelések adatait, hogy elemezhessék a trendeket.</span><span class="sxs-lookup"><span data-stu-id="a0484-158">The ratings and reviews moderation tool lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="a0484-159">Elérhető egy alapvető Power BI-metrikákat tartalmazó sablon.</span><span class="sxs-lookup"><span data-stu-id="a0484-159">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="a0484-160">A moderátorok ezt a sablont használhatják a kötegben importált adatok összekapcsolására és egy irányítópult megjelenítésére is.</span><span class="sxs-lookup"><span data-stu-id="a0484-160">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="a0484-161">Nem kell egyéni irányítópultot létrehozniuk.</span><span class="sxs-lookup"><span data-stu-id="a0484-161">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="a0484-162">A moderátorok a Power BI-sablont is testreszabhatják, hogy az megfeleljen igényeiknek.</span><span class="sxs-lookup"><span data-stu-id="a0484-162">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="a0484-163">A minősítések és a értékelések adatainak letöltéséhez hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-163">To download ratings and reviews data, follow these steps.</span></span>

1. <span data-ttu-id="a0484-164">Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-164">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="a0484-165">Válassza az **Étrékelések adatainak letöltése** lehetőséget a minősítések és értékelések adatainak tömeges letöltéséhez vesszővel tagolt (CSV) formátumban.</span><span class="sxs-lookup"><span data-stu-id="a0484-165">Select **Download reviews data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="a0484-166">Minősítések és értékelések trendjeinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="a0484-166">View ratings and reviews trends</span></span>

<span data-ttu-id="a0484-167">A moderátorok letölthetik a Power BI-sablont, így megtekinthetik az trendeket az irányítópultokon.</span><span class="sxs-lookup"><span data-stu-id="a0484-167">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="a0484-168">A minősítések és a értékelések trendjeinek megtekintéséhez hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a0484-168">To view ratings and reviews trends, follow these steps.</span></span>

1. <span data-ttu-id="a0484-169">Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-169">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="a0484-170">A sablon letöltéséhez válassza ki a **PowerBI-sablont**.</span><span class="sxs-lookup"><span data-stu-id="a0484-170">Select **PowerBI template** to download the template.</span></span>

    ![A Power BI-sablon letöltése](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="a0484-172">Nyissa meg a letöltött sablont a Power BI alkalmazás segítségével.</span><span class="sxs-lookup"><span data-stu-id="a0484-172">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="a0484-173">Zárja be a megjelenő **Webtartalomhoz való hozzáférés** párbeszédpanelt, majd zárja be a megjelenő „Frissítési” hibaüzenetet.</span><span class="sxs-lookup"><span data-stu-id="a0484-173">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="a0484-174">Menjen a **Kezdőlapra**, válassza a **Lekérdezések szerkesztése** lehetőséget, majd válassza az **Adatforrás-beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="a0484-174">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="a0484-175">Az **Adatforrás beállításai** párbeszédpanelen jelölje be a **Forrás módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0484-175">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="a0484-176">Az **URL-cím** mezőbe írja be az előző eljárásban letöltött értékelés adatainak elérési útját (például **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="a0484-176">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![A Vesszővel tagolt értékek párbeszédpanel URL-mezője](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="a0484-178">Válassza a **OK** lehetőséget, majd kattintson az **Módosítások** alkalmazása gombra.</span><span class="sxs-lookup"><span data-stu-id="a0484-178">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="a0484-179">Az adatforrásra módosításainak alkalmazása eltart egy-két percig.</span><span class="sxs-lookup"><span data-stu-id="a0484-179">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="a0484-180">Válassza ki a **Trendek lapot** a minősítések és a vélemények trendjeinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="a0484-180">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Minősítések és értékelések trendjei](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="a0484-182">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a0484-182">Additional resources</span></span>

[<span data-ttu-id="a0484-183">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="a0484-183">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="a0484-184">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a0484-184">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="a0484-185">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a0484-185">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="a0484-186">A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="a0484-186">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
