---
title: Minősítések és értékelések kezelése
description: Ez a témakör azt mutatja be, hogyan kezelheti az értékeléseket és véleményeket a Microsoft Dynamics 365 Commerce webhelykészítőjében.
author: gvrmohanreddy
manager: annbe
ms.date: 10/09/2020
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
ms.openlocfilehash: 3fc88bc5a5868dce7c0539bf3f0ddc5b751e7b75
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412884"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="a3383-103">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="a3383-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a3383-104">Ez a témakör azt mutatja be, hogyan kezelheti az értékeléseket és véleményeket a Microsoft Dynamics 365 Commerce webhelykészítőjében.</span><span class="sxs-lookup"><span data-stu-id="a3383-104">This topic explains how to manage ratings and reviews in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="a3383-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="a3383-105">Overview</span></span>

<span data-ttu-id="a3383-106">A Dynamics 365 Commerce a Microsoft Azure kognitív szolgáltatását használja a szöveg automatikus moderálására a profán szavak kivonásával.</span><span class="sxs-lookup"><span data-stu-id="a3383-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="a3383-107">Ezenkívül a moderátorok a Dynamics 365 Commerce webhelykészítő segítségével a következő manuális feladatokat hajthatják végre:</span><span class="sxs-lookup"><span data-stu-id="a3383-107">In addition, moderators can use Dynamics 365 Commerce site builder to implement the following manual tasks:</span></span>

- <span data-ttu-id="a3383-108">Értékelések moderálása válaszadással vagy eltávolításukkal.</span><span class="sxs-lookup"><span data-stu-id="a3383-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="a3383-109">Vevői értékelések törlése a vevő kérésére.</span><span class="sxs-lookup"><span data-stu-id="a3383-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="a3383-110">Minősítések és értékelése tömeges importálása egy Microsoft Power BI sablonba hogy elemezhetők legyenek a minősítések és a vélemények trendjei.</span><span class="sxs-lookup"><span data-stu-id="a3383-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="a3383-111">Értékelés elolvasása</span><span class="sxs-lookup"><span data-stu-id="a3383-111">Read a review</span></span> 

<span data-ttu-id="a3383-112">Ha a Commerce webhelykészítőben egy értékelést szeretne elolvasni, akkor a következő lépéseket kövesse.</span><span class="sxs-lookup"><span data-stu-id="a3383-112">To read to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a3383-113">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-113">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="a3383-114">A lap jobb felső részén található keresési mező használatával szűrheti a megjelenített értékeléseket a termék azonosítója, a terméknév vagy az értékelés szövege szerint.</span><span class="sxs-lookup"><span data-stu-id="a3383-114">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="a3383-115">A további szűrők használatával időszak, minősítés, csatorna vagy probléma állapota szerint korlátozhatja (levett, megválaszolt vagy jelentett) az értékeléseket.</span><span class="sxs-lookup"><span data-stu-id="a3383-115">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Moderálás kezdőoldala](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="a3383-117">Értékelés megválaszolása</span><span class="sxs-lookup"><span data-stu-id="a3383-117">Respond to a review</span></span> 

<span data-ttu-id="a3383-118">Előfordulhat, hogy azok a vevőkk, akik egy terméket megvásároltak, kifejezik elégedettségüket vagy elégedetlenségüket, vagy jelzik, hogy nem értik, hogyan kell használni a terméket.</span><span class="sxs-lookup"><span data-stu-id="a3383-118">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="a3383-119">Moderátorként válaszolhat értékelésekre..</span><span class="sxs-lookup"><span data-stu-id="a3383-119">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="a3383-120">Ez a válasz a az értékeléssel együtt jelenik meg a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a3383-120">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="a3383-121">Ha a Commerce webhelykészítőben egy értékelésre szeretne válaszolni, akkor a következő lépéseket kövesse.</span><span class="sxs-lookup"><span data-stu-id="a3383-121">To respond to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a3383-122">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-122">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="a3383-123">Keresse meg és válassza ki a megválaszolandó értékelést.</span><span class="sxs-lookup"><span data-stu-id="a3383-123">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="a3383-124">A jobb oldali tulajdonságok ablaktáblán válassza a **Válasz hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a3383-124">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="a3383-125">Adja meg a válasz szövegét, valamint azt a nevet, amelyet meg kell jeleníteni a válaszadó számára.</span><span class="sxs-lookup"><span data-stu-id="a3383-125">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="a3383-126">Az alapértelmezett válaszadó neve **Moderátor.**</span><span class="sxs-lookup"><span data-stu-id="a3383-126">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="a3383-127">Amikor elkészült, válassza a **Válasz feladása** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-127">When you've finished, select **Post response**.</span></span>

![Válaszolás értékelésre](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="a3383-129">Egy értékelés levétele</span><span class="sxs-lookup"><span data-stu-id="a3383-129">Take down a review</span></span> 

<span data-ttu-id="a3383-130">Előfordulhat, hogy üzleti érdek fűződik ahhoz, hogy a moderátorok eltávolítsanak bizonyos vevői értékeléseket.</span><span class="sxs-lookup"><span data-stu-id="a3383-130">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="a3383-131">Ha a Commerce webhelykészítőben egy értékelést szeretne félretenni, akkor a következő lépéseket kövesse.</span><span class="sxs-lookup"><span data-stu-id="a3383-131">To take down a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a3383-132">Nyissa meg a **Kezdőlap \> Értékelések \> Moderálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-132">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="a3383-133">Keresse meg és válassza ki azt az értékelést, amelyet le kell venni.</span><span class="sxs-lookup"><span data-stu-id="a3383-133">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="a3383-134">A jobb oldali tulajdonságok ablaktáblán, a **Értékelés félretétele** elemnél válassza ki a félretétel okot, majd válassza **Félretétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a3383-134">In the properties pane on the right, select a takedown reason under **Takedown Review**, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="a3383-135">Vevői értékelések törlése a vevő kérésére</span><span class="sxs-lookup"><span data-stu-id="a3383-135">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="a3383-136">Előfordulhat, hogy a vevők az értékelést és az értékelés adatait véglegesen törölni szeretnék egy e-kereskedelmi webhelyről.</span><span class="sxs-lookup"><span data-stu-id="a3383-136">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="a3383-137">A vevőtől érkező eltávolítási kérelmet fogadó moderátor eltávolíthatja a vevő adatait az értékelés törlése funkcióval.</span><span class="sxs-lookup"><span data-stu-id="a3383-137">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="a3383-138">A vevő adatainak megkereséséhez és törléséhez a moderátornak be kell írnia azt az e-mail-címet, amelyet a vevő a bejelentkezéshez és az értékelés elkészítéséhez használt.</span><span class="sxs-lookup"><span data-stu-id="a3383-138">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="a3383-139">A Commerce webhelykészítő vevői adatainak megkereséséhez és törléséhez az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="a3383-139">To find and delete customer data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a3383-140">Nyissa meg a **Kezdőlap \> Értékelések \> Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-140">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="a3383-141">A **Vevő keresése e-mail-cím alapján** négyzetben adja meg a felhasználó e-mail-címét, majd válassza a **Keresés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a3383-141">In the **Search for users by email address** box, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="a3383-142">Ha a vevőnek van valamilyen értékelési tevékenysége (például a beküldött értékelések, szavazás más vásárlói értékelések hasznosságával kapcsolatosan vagy megjegyzések egy másik vásárló értékelésére), az eredmények megjelennek.</span><span class="sxs-lookup"><span data-stu-id="a3383-142">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="a3383-143">Mindegyik tételhez tartozik egy **Törlés** gomb.</span><span class="sxs-lookup"><span data-stu-id="a3383-143">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="a3383-144">Minden egyes törlendő elemhez válassza ki a **Törlés** gombot.</span><span class="sxs-lookup"><span data-stu-id="a3383-144">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="a3383-145">Amikor a program megerősítést kér, válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a3383-145">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Ügyféladatok törlése](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="a3383-147">Az adatok teljes eltávolítására rendszerből akár 7 napot is igénybe vehet.</span><span class="sxs-lookup"><span data-stu-id="a3383-147">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="a3383-148">A moderátoroknak tájékoztatniuk kell a vevőket erről a késésről.</span><span class="sxs-lookup"><span data-stu-id="a3383-148">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="a3383-149">Ha a vevő a saját fiókbeállításaiban megváltoztatta a nevét, akkor a keresési eredmények között több elem is megjelenhet.</span><span class="sxs-lookup"><span data-stu-id="a3383-149">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="a3383-150">Ebben az esetben a vevő adatainak teljes törléséhez a moderátornak ki kell választania a **Törlés** lehetőséget minden egyes elemhez.</span><span class="sxs-lookup"><span data-stu-id="a3383-150">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="a3383-151">A minősítések és a értékelések adatainak letöltése</span><span class="sxs-lookup"><span data-stu-id="a3383-151">Download ratings and reviews data</span></span>

<span data-ttu-id="a3383-152">A Commerce webhelykészítővel a moderátorok importálhatják a minősítések és értékelések adatait, hogy elemezhessék a trendeket.</span><span class="sxs-lookup"><span data-stu-id="a3383-152">Commerce site builder lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="a3383-153">Elérhető egy alapvető Power BI-metrikákat tartalmazó sablon.</span><span class="sxs-lookup"><span data-stu-id="a3383-153">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="a3383-154">A moderátorok ezt a sablont használhatják a kötegben importált adatok összekapcsolására és egy irányítópult megjelenítésére is.</span><span class="sxs-lookup"><span data-stu-id="a3383-154">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="a3383-155">Nem kell egyéni irányítópultot létrehozniuk.</span><span class="sxs-lookup"><span data-stu-id="a3383-155">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="a3383-156">A moderátorok a Power BI-sablont is testreszabhatják, hogy az megfeleljen igényeiknek.</span><span class="sxs-lookup"><span data-stu-id="a3383-156">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="a3383-157">A Commerce webhelykészítőben az értékelések és vélemények letöltéséhez az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="a3383-157">To download ratings and reviews data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a3383-158">Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-158">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="a3383-159">Válassza az **Étrékelés adatainak letöltése** lehetőséget a minősítések és értékelések adatainak tömeges letöltéséhez vesszővel tagolt (CSV) formátumban.</span><span class="sxs-lookup"><span data-stu-id="a3383-159">Select **Download review data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="a3383-160">Minősítések és értékelések trendjeinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="a3383-160">View ratings and reviews trends</span></span>

<span data-ttu-id="a3383-161">A moderátorok letölthetik a Power BI-sablont, így megtekinthetik az trendeket az irányítópultokon.</span><span class="sxs-lookup"><span data-stu-id="a3383-161">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="a3383-162">A Commerce webhelykészítőben az értékelések és vélemények trendjeinek megtekintéséhez az alábbi lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="a3383-162">To view ratings and reviews trends in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="a3383-163">Nyissa meg a **Kezdőlap \> Értékelések \> Jelentéskészítés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-163">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="a3383-164">A sablon letöltéséhez válassza ki a **PowerBI-sablont**.</span><span class="sxs-lookup"><span data-stu-id="a3383-164">Select **PowerBI template** to download the template.</span></span>

    ![Töltse le a Power BI sablont](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="a3383-166">Nyissa meg a letöltött sablont a Power BI alkalmazás segítségével.</span><span class="sxs-lookup"><span data-stu-id="a3383-166">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="a3383-167">Zárja be a megjelenő **Webtartalomhoz való hozzáférés** párbeszédpanelt, majd zárja be a megjelenő „Frissítési” hibaüzenetet.</span><span class="sxs-lookup"><span data-stu-id="a3383-167">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="a3383-168">Menjen a **Kezdőlapra**, válassza a **Lekérdezések szerkesztése** lehetőséget, majd válassza az **Adatforrás-beállítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="a3383-168">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="a3383-169">Az **Adatforrás beállításai** párbeszédpanelen jelölje be a **Forrás módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a3383-169">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="a3383-170">Az **URL-cím** mezőbe írja be az előző eljárásban letöltött értékelés adatainak elérési útját (például **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="a3383-170">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![A Vesszővel tagolt értékek párbeszédpanel URL-mezője](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="a3383-172">Válassza a **OK** lehetőséget, majd kattintson az **Módosítások** alkalmazása gombra.</span><span class="sxs-lookup"><span data-stu-id="a3383-172">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="a3383-173">Az adatforrásra módosításainak alkalmazása eltart egy-két percig.</span><span class="sxs-lookup"><span data-stu-id="a3383-173">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="a3383-174">Válassza ki a **Trendek lapot** a minősítések és a vélemények trendjeinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="a3383-174">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Minősítések és értékelések trendjei](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="a3383-176">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a3383-176">Additional resources</span></span>

[<span data-ttu-id="a3383-177">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="a3383-177">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="a3383-178">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a3383-178">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="a3383-179">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a3383-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="a3383-180">A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="a3383-180">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
