---
title: Minősítések és értékelések kezelése
description: Ez a témakör azt mutatja be, hogyan kezelheti az értékeléseket és véleményeket a Microsoft Dynamics 365 Commerce webhelykészítőjében.
author: gvrmohanreddy
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 60ad0dd821dc91576a59cf73ec46da4aefd34a2f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794259"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="5e397-103">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="5e397-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5e397-104">Ez a témakör azt mutatja be, hogyan kezelheti az értékeléseket és véleményeket a Microsoft Dynamics 365 Commerce webhelykészítőjében.</span><span class="sxs-lookup"><span data-stu-id="5e397-104">This topic explains how to manage ratings and reviews in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="5e397-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="5e397-105">Overview</span></span>

<span data-ttu-id="5e397-106">A Dynamics 365 Commerce a Microsoft Azure kognitív szolgáltatását használja a szöveg automatikus moderálására a profán szavak kivonásával.</span><span class="sxs-lookup"><span data-stu-id="5e397-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="5e397-107">Ezenkívül a moderátorok a Dynamics 365 Commerce webhelykészítő segítségével a következő manuális feladatokat hajthatják végre:</span><span class="sxs-lookup"><span data-stu-id="5e397-107">In addition, moderators can use Dynamics 365 Commerce site builder to implement the following manual tasks:</span></span>

- <span data-ttu-id="5e397-108">Értékelések moderálása válaszadással vagy eltávolításukkal.</span><span class="sxs-lookup"><span data-stu-id="5e397-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="5e397-109">Vevői értékelések törlése a vevő kérésére.</span><span class="sxs-lookup"><span data-stu-id="5e397-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="5e397-110">Minősítések és értékelése tömeges importálása egy Microsoft Power BI sablonba, hogy elemezhetők legyenek a minősítések és a vélemények trendjei.</span><span class="sxs-lookup"><span data-stu-id="5e397-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="5e397-111">Értékelés elolvasása</span><span class="sxs-lookup"><span data-stu-id="5e397-111">Read a review</span></span> 

<span data-ttu-id="5e397-112">Ha a Commerce webhelykészítőben egy értékelést szeretne elolvasni, akkor a következő lépéseket kövesse.</span><span class="sxs-lookup"><span data-stu-id="5e397-112">To read to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e397-113">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-113">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="5e397-114">A lap jobb felső részén található keresési mező használatával szűrheti a megjelenített értékeléseket a termék azonosítója, a terméknév vagy az értékelés szövege szerint.</span><span class="sxs-lookup"><span data-stu-id="5e397-114">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="5e397-115">A további szűrők használatával időszak, minősítés, csatorna vagy probléma állapota szerint korlátozhatja (levett, megválaszolt vagy jelentett) az értékeléseket.</span><span class="sxs-lookup"><span data-stu-id="5e397-115">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Moderálás kezdőoldala](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="5e397-117">Értékelés megválaszolása</span><span class="sxs-lookup"><span data-stu-id="5e397-117">Respond to a review</span></span> 

<span data-ttu-id="5e397-118">Előfordulhat, hogy azok a vevőkk, akik egy terméket megvásároltak, kifejezik elégedettségüket vagy elégedetlenségüket, vagy jelzik, hogy nem értik, hogyan kell használni a terméket.</span><span class="sxs-lookup"><span data-stu-id="5e397-118">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="5e397-119">Moderátorként válaszolhat értékelésekre..</span><span class="sxs-lookup"><span data-stu-id="5e397-119">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="5e397-120">Ez a válasz a az értékeléssel együtt jelenik meg a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="5e397-120">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="5e397-121">Ha a Commerce webhelykészítőben egy értékelésre szeretne válaszolni, akkor a következő lépéseket kövesse.</span><span class="sxs-lookup"><span data-stu-id="5e397-121">To respond to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e397-122">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-122">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="5e397-123">Keresse meg és válassza ki a megválaszolandó értékelést.</span><span class="sxs-lookup"><span data-stu-id="5e397-123">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="5e397-124">A jobb oldali tulajdonságok ablaktáblán válassza a **Válasz hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e397-124">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="5e397-125">Adja meg a válasz szövegét, valamint azt a nevet, amelyet meg kell jeleníteni a válaszadó számára.</span><span class="sxs-lookup"><span data-stu-id="5e397-125">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="5e397-126">Az alapértelmezett válaszadó neve **Moderátor.**</span><span class="sxs-lookup"><span data-stu-id="5e397-126">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="5e397-127">Amikor elkészült, válassza a **Válasz feladása** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-127">When you've finished, select **Post response**.</span></span>

![Válaszolás értékelésre](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="5e397-129">Egy értékelés levétele</span><span class="sxs-lookup"><span data-stu-id="5e397-129">Take down a review</span></span> 

<span data-ttu-id="5e397-130">Előfordulhat, hogy üzleti érdek fűződik ahhoz, hogy a moderátorok eltávolítsanak bizonyos vevői értékeléseket.</span><span class="sxs-lookup"><span data-stu-id="5e397-130">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="5e397-131">Ha a Commerce webhelykészítőben egy értékelést szeretne félretenni, akkor a következő lépéseket kövesse.</span><span class="sxs-lookup"><span data-stu-id="5e397-131">To take down a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e397-132">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-132">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="5e397-133">Keresse meg és válassza ki azt az értékelést, amelyet le kell venni.</span><span class="sxs-lookup"><span data-stu-id="5e397-133">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="5e397-134">A jobb oldali tulajdonságok ablaktáblán, a **Értékelés félretétele** elemnél válassza ki a félretétel okot, majd válassza **Félretétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e397-134">In the properties pane on the right, select a takedown reason under **Takedown Review**, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="5e397-135">Vevői értékelések törlése a vevő kérésére</span><span class="sxs-lookup"><span data-stu-id="5e397-135">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="5e397-136">Előfordulhat, hogy a vevők az értékelést és az értékelés adatait véglegesen törölni szeretnék egy e-kereskedelmi webhelyről.</span><span class="sxs-lookup"><span data-stu-id="5e397-136">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="5e397-137">A vevőtől érkező eltávolítási kérelmet fogadó moderátor eltávolíthatja a vevő adatait az értékelés törlése funkcióval.</span><span class="sxs-lookup"><span data-stu-id="5e397-137">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="5e397-138">A vevő adatainak megkereséséhez és törléséhez a moderátornak be kell írnia azt az e-mail-címet, amelyet a vevő a bejelentkezéshez és az értékelés elkészítéséhez használt.</span><span class="sxs-lookup"><span data-stu-id="5e397-138">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="5e397-139">A Commerce webhelykészítő vevői adatainak megkereséséhez és törléséhez az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="5e397-139">To find and delete customer data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e397-140">Nyissa meg a **Kezdőlap \> Értékelések \> Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-140">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="5e397-141">A **Vevő keresése e-mail-cím alapján** négyzetben adja meg a felhasználó e-mail-címét, majd válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e397-141">In the **Search for users by email address** box, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="5e397-142">Ha a vevőnek van valamilyen értékelési tevékenysége (például a beküldött értékelések, szavazás más vásárlói értékelések hasznosságával kapcsolatosan vagy megjegyzések egy másik vásárló értékelésére), az eredmények megjelennek.</span><span class="sxs-lookup"><span data-stu-id="5e397-142">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="5e397-143">Mindegyik tételhez tartozik egy **Törlés** gomb.</span><span class="sxs-lookup"><span data-stu-id="5e397-143">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="5e397-144">Minden egyes törlendő elemhez válassza ki a **Törlés** gombot.</span><span class="sxs-lookup"><span data-stu-id="5e397-144">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="5e397-145">Amikor a program megerősítést kér, válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e397-145">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Ügyféladatok törlése](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="5e397-147">Az adatok teljes eltávolítására rendszerből akár 7 napot is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="5e397-147">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="5e397-148">A moderátoroknak tájékoztatniuk kell a vevőket erről a késésről.</span><span class="sxs-lookup"><span data-stu-id="5e397-148">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="5e397-149">Ha a vevő a saját fiókbeállításaiban megváltoztatta a nevét, akkor a keresési eredmények között több elem is megjelenhet.</span><span class="sxs-lookup"><span data-stu-id="5e397-149">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="5e397-150">Ebben az esetben a vevő adatainak teljes törléséhez a moderátornak ki kell választania a **Törlés** lehetőséget minden egyes elemhez.</span><span class="sxs-lookup"><span data-stu-id="5e397-150">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="5e397-151">A minősítések és a értékelések adatainak letöltése</span><span class="sxs-lookup"><span data-stu-id="5e397-151">Download ratings and reviews data</span></span>

<span data-ttu-id="5e397-152">A Commerce webhelykészítővel a moderátorok importálhatják a minősítések és értékelések adatait, hogy elemezhessék a trendeket.</span><span class="sxs-lookup"><span data-stu-id="5e397-152">Commerce site builder lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="5e397-153">Elérhető egy alapvető Power BI-metrikákat tartalmazó sablon.</span><span class="sxs-lookup"><span data-stu-id="5e397-153">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="5e397-154">A moderátorok ezt a sablont használhatják a kötegben importált adatok összekapcsolására és egy irányítópult megjelenítésére is.</span><span class="sxs-lookup"><span data-stu-id="5e397-154">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="5e397-155">Nem kell egyéni irányítópultot létrehozniuk.</span><span class="sxs-lookup"><span data-stu-id="5e397-155">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="5e397-156">A moderátorok a Power BI-sablont is testreszabhatják, hogy az megfeleljen igényeiknek.</span><span class="sxs-lookup"><span data-stu-id="5e397-156">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="5e397-157">A Commerce webhelykészítőben az értékelések és vélemények letöltéséhez az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="5e397-157">To download ratings and reviews data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e397-158">Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-158">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="5e397-159">Válassza az **Étrékelés adatainak letöltése** lehetőséget a minősítések és értékelések adatainak tömeges letöltéséhez vesszővel tagolt (CSV) formátumban.</span><span class="sxs-lookup"><span data-stu-id="5e397-159">Select **Download review data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="5e397-160">Minősítések és értékelések trendjeinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="5e397-160">View ratings and reviews trends</span></span>

<span data-ttu-id="5e397-161">A moderátorok letölthetik a Power BI-sablont, így megtekinthetik az trendeket az irányítópultokon.</span><span class="sxs-lookup"><span data-stu-id="5e397-161">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="5e397-162">A Commerce webhelykészítőben az értékelések és vélemények trendjeinek megtekintéséhez az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="5e397-162">To view ratings and reviews trends in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="5e397-163">Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-163">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="5e397-164">A sablon letöltéséhez válassza ki a **PowerBI-sablont**.</span><span class="sxs-lookup"><span data-stu-id="5e397-164">Select **PowerBI template** to download the template.</span></span>

    ![Töltse le a Power BI sablont](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="5e397-166">Nyissa meg a letöltött sablont a Power BI alkalmazás segítségével.</span><span class="sxs-lookup"><span data-stu-id="5e397-166">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="5e397-167">Zárja be a megjelenő **Webtartalomhoz való hozzáférés** párbeszédpanelt, majd zárja be a megjelenő „Frissítési” hibaüzenetet.</span><span class="sxs-lookup"><span data-stu-id="5e397-167">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="5e397-168">Menjen a **Kezdőlapra**, válassza a **Lekérdezések szerkesztése** lehetőséget, majd válassza az **Adatforrás-beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="5e397-168">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="5e397-169">Az **Adatforrás beállításai** párbeszédpanelen jelölje be a **Forrás módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5e397-169">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="5e397-170">Az **URL-cím** mezőbe írja be az előző eljárásban letöltött értékelés adatainak elérési útját (például **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="5e397-170">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![A Vesszővel tagolt értékek párbeszédpanel URL-mezője](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="5e397-172">Válassza a **OK** lehetőséget, majd kattintson az **Módosítások** alkalmazása gombra.</span><span class="sxs-lookup"><span data-stu-id="5e397-172">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="5e397-173">Az adatforrásra módosításainak alkalmazása eltart egy-két percig.</span><span class="sxs-lookup"><span data-stu-id="5e397-173">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="5e397-174">Válassza ki a **Trendek lapot** a minősítések és a vélemények trendjeinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="5e397-174">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Minősítések és értékelések trendjei](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="5e397-176">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5e397-176">Additional resources</span></span>

[<span data-ttu-id="5e397-177">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="5e397-177">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="5e397-178">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="5e397-178">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="5e397-179">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="5e397-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="5e397-180">A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="5e397-180">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]