---
title: "Személyre szabott termékajánlások"
description: "Ez a témakör a Dynamics 365 for Retail pénztár (POS) eszközön megjeleníthető termékajánlásaival kapcsolatban rendelkezik információval."
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 368468a1c1cd023862f1405dddf3a90574edce22
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="personalized-product-recommendations"></a><span data-ttu-id="05cfa-103">Személyre szabott termékajánlások</span><span class="sxs-lookup"><span data-stu-id="05cfa-103">Personalized product recommendations</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="05cfa-104">A termékajánló szolgáltatás jelenlegi verzióját eltávolítjuk, mivel ezt a funkciót jobb algoritmussal és újabb kiskereskedelmi orientált képességekkel újratervezzük.</span><span class="sxs-lookup"><span data-stu-id="05cfa-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="05cfa-105">További információ: [Eltávolított vagy elavult funkciók](../dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="05cfa-105">For more information see [Removed or deprecated features](../dev-itpro/migration-upgrade/deprecated-features.md).</span></span> <span data-ttu-id="05cfa-106">Navigáljon az oldal aljára, ha problémái vannak az adott környezetben már engedélyezett termékajánlásokkal.</span><span class="sxs-lookup"><span data-stu-id="05cfa-106">Navigate to the bottom of the page if you are facing issues with already-enabled product recommendations for your environment.</span></span> 

<span data-ttu-id="05cfa-107">A Dynamics 365 for Retail rendszerben a termékajánlásokat meg lehet jeleníteni a pénztár (POS) eszközön.</span><span class="sxs-lookup"><span data-stu-id="05cfa-107">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="05cfa-108">Az ajánlások olyan elemek, amelyek érdekelhetik a vevőt a vásárlási előzmények alapján, a kívánságlistájukon levő elemek alapján, illetve olyan elemek alapján, amelyeket más felhasználók vásároltak meg online vagy hagyományos üzletekben.</span><span class="sxs-lookup"><span data-stu-id="05cfa-108">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="05cfa-109">A nagy katalógussal dolgozó kiskereskedők esetében az ajánlások segítenek a vevőknek a termékek felderítésében.</span><span class="sxs-lookup"><span data-stu-id="05cfa-109">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="05cfa-110">A vevő érdeklődésének és vásárlási szokásainak megfelelően célzott termékek bemutatásával a termékajánlások segíthetik a kiskereskedőket az értéknövelő, valamint a keresztértékesítésben, és növelhetik a vevők megtartását.</span><span class="sxs-lookup"><span data-stu-id="05cfa-110">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="05cfa-111">A Dynamics 365 for Retail rendszerben a termékajánlásokat a kognitív szolgáltatás és a Microsoft Azure gépi tanulás szolgálja ki.</span><span class="sxs-lookup"><span data-stu-id="05cfa-111">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="05cfa-112">Esetek</span><span class="sxs-lookup"><span data-stu-id="05cfa-112">Scenarios</span></span>
---------

<span data-ttu-id="05cfa-113">Az alábbi POS-esetekben engedélyezettek a termékajánlások.</span><span class="sxs-lookup"><span data-stu-id="05cfa-113">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="05cfa-114">A felhő POS vagy a modern POS (MPOS) esetében állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="05cfa-114">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="05cfa-115">A **Termékadatok kezelése** oldalon:</span><span class="sxs-lookup"><span data-stu-id="05cfa-115">On the **Product details** page:</span></span>

-   <span data-ttu-id="05cfa-116">Ha az üzlet alkalmazottja megnyitja valamelyik **Termékadatok** oldalt, amikor az előző tranzakciókat nézi meg különböző csatornákat lefedve, az ajánlások motor további elemeket javasol, amelyek várhatóan együtt fognak megvásárolni.</span><span class="sxs-lookup"><span data-stu-id="05cfa-116">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="05cfa-117">Ha az üzlet alkalmazottja hozzáad egy vevőt a tranzakcióhoz, majd látogat egy **Termékadatok** lapot, az ajánlások motor a vevői tranzakciók előzményeinek segítségével személyre szabott ajánlásokat tesz.</span><span class="sxs-lookup"><span data-stu-id="05cfa-117">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="05cfa-118">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="05cfa-118">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="05cfa-119">A **Tranzakció** oldalon:</span><span class="sxs-lookup"><span data-stu-id="05cfa-119">On the **Transaction** page:</span></span>

-   <span data-ttu-id="05cfa-120">Az ajánlások motor a kosárban levő cikkek teljes listája alapján cikkeket javasol.</span><span class="sxs-lookup"><span data-stu-id="05cfa-120">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="05cfa-121">Ha az üzlet alkalmazottja hozzáad egy vevőt a tranzakcióhoz, az ajánlások motor a vevői tranzakciók előzményeinek segítségével, valamint a kosárban levő cikkel alapján személyes ajánlásokat tesz.</span><span class="sxs-lookup"><span data-stu-id="05cfa-121">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="05cfa-122">Javaslatok megjelenítéséhez a **Tranzakció** lapon a kiskereskedőnek frissítenie kell a képernyő-elrendezést Dynamics 365 for Retail rendszerben.</span><span class="sxs-lookup"><span data-stu-id="05cfa-122">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="05cfa-123">Az **Ajánlások** vezérlőt rá kell húzni a **Tranzakció** oldalra.</span><span class="sxs-lookup"><span data-stu-id="05cfa-123">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="05cfa-124">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="05cfa-124">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="05cfa-125">A **Vevő adatai** oldalon:</span><span class="sxs-lookup"><span data-stu-id="05cfa-125">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="05cfa-126">Az ajánlások motor a felhasználói azonosító és a vevő kívánságlistáján levő cikkek alapján cikkeket javasol.</span><span class="sxs-lookup"><span data-stu-id="05cfa-126">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="05cfa-127">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="05cfa-127">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="05cfa-128">A Dynamics 365 for Retail rendszer konfigurálása a POS-ajánlások engedélyezésére</span><span class="sxs-lookup"><span data-stu-id="05cfa-128">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="05cfa-129">A termékajánlások beállításához a következőket kell tenni:</span><span class="sxs-lookup"><span data-stu-id="05cfa-129">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="05cfa-130">Győződjön meg arról, hogy a megfelelő **Jogi személy** választotta ki.</span><span class="sxs-lookup"><span data-stu-id="05cfa-130">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="05cfa-131">Keresse meg az **Entitástár** elemet, jelölje be a **Kiskereskedelmi értékesítés** lehetőséget, és kattintson a **Frissítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="05cfa-131">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.</span></span> <span data-ttu-id="05cfa-132">Ezzel a bemutatóadatokat (vagy a saját adatait) használja az üzemi adatbázisból, és áthelyezi őket az entitástárba.</span><span class="sxs-lookup"><span data-stu-id="05cfa-132">This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="05cfa-133">Választható lehetőség: Javaslatok megjelenítéséhez a tranzakciók képernyőn, menjen a **Képernyőelrendezés** lehetőséghez, válassza ki a képernyőelrendezést, indítsa el a **Képernyő-elrendezés tervezőjét**, majd helyezze az **ajánlások** vezérlőjét oda, ahová szükséges.</span><span class="sxs-lookup"><span data-stu-id="05cfa-133">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**, and then drop the **recommendations** control where needed.</span></span>

4.  <span data-ttu-id="05cfa-134">Keresse fel a **Kiskereskedelmi paraméterek** elemet, válassza **Gépi tanulás** elemet, jelölje be az **Igen** lehetőséget **POS-ajánlások engedélyezése** alatt.</span><span class="sxs-lookup"><span data-stu-id="05cfa-134">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="05cfa-135">A javaslatok megtekintéséhez a POS-on, futtassa az **1110** globális konfigurációs feladatot.</span><span class="sxs-lookup"><span data-stu-id="05cfa-135">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="05cfa-136">A POS képernyő-elrendezés tervezőjén végzett módosítások megjelenítéséhez futtassa az **1070** csatorna konfigurációs feladatot.</span><span class="sxs-lookup"><span data-stu-id="05cfa-136">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="05cfa-137">Hogyan működik?</span><span class="sxs-lookup"><span data-stu-id="05cfa-137">How does it work?</span></span>
<span data-ttu-id="05cfa-138">Az **Entitástár** entitás frissítésekor a következő műveletek végrehajtása történik.</span><span class="sxs-lookup"><span data-stu-id="05cfa-138">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="05cfa-139">A kognitív szolgáltatások által megkövetelt formátumban a rendszer kivonja az adatokat a Dynamics 365 for Retail működési adatbázisából, és elküldi őket az entitástárba.</span><span class="sxs-lookup"><span data-stu-id="05cfa-139">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="05cfa-140">Az adatokat az Azure Data Factory (ADF) használja fel az adatok tisztításához Hive-parancsfájlok használatával, az ADF-tevékenységek részeként.</span><span class="sxs-lookup"><span data-stu-id="05cfa-140">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="05cfa-141">A megtisztított adatokat blobtároló tárolja.</span><span class="sxs-lookup"><span data-stu-id="05cfa-141">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="05cfa-142">A blobtároló adatait a kognitív szolgáltatások API használja egy ajánlási modell betanításához.</span><span class="sxs-lookup"><span data-stu-id="05cfa-142">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="05cfa-143">Ha bekapcsolja az **Ajánlások engedélyezése** elemet, és elvégzi a konfigurációs feladatok futtatását, a következő műveletek végrehajtása történik.</span><span class="sxs-lookup"><span data-stu-id="05cfa-143">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="05cfa-144">A modell hitelesítő adatokat és az azonosítót a rendszer az API segítségével szerzi meg, majd a Dynamics 365 for Retail működési adatbázisában tárolja, az AOS web.config állományában, illetve a kiskereskedelmi kiszolgálón is.</span><span class="sxs-lookup"><span data-stu-id="05cfa-144">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="05cfa-145">A modell hitelesítő adatok és az azonosító hozzáférhetők a CRT számára, hogy ki lehessen szolgálni a felhő POS és az MPOS felől online módban érkező termékajánlás-lehívásokat.</span><span class="sxs-lookup"><span data-stu-id="05cfa-145">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>

> ## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a><span data-ttu-id="05cfa-146">Már engedélyezett termékajánlások esetében problémák elhárítása</span><span class="sxs-lookup"><span data-stu-id="05cfa-146">Troubleshoot issues where you have Product recommendations already enabled</span></span> 
> - <span data-ttu-id="05cfa-147">Keresse meg a **Kiskereskedelmi paraméterek** > **Gépi tanulás** > **Termékajánlások letiltása** elemet, és futtassa a **Globális konfiguráció feladat [1110]** elemet.</span><span class="sxs-lookup"><span data-stu-id="05cfa-147">Navigate to **Retail Parameters** > **Machine learning** > **Disable product recommendations** and run **Global configuration job [1110]**.</span></span> <span data-ttu-id="05cfa-148">Ha nem találja a **Gépi tanulás** lapot, forduljon a Dynamics támogatásához.</span><span class="sxs-lookup"><span data-stu-id="05cfa-148">If you are not able to locate **Machine learning** tab, please contact Dynamics Support.</span></span> 
> 
> - <span data-ttu-id="05cfa-149">Ha az **Ajánlások vezérlőelem** hozzá van adva a tranzakcióképernyőhöz a **Képernyő-elrendezés tervezője** használatával, távolítsa el azt is.</span><span class="sxs-lookup"><span data-stu-id="05cfa-149">If you added the **Recommendations control** to your transaction screen using the **Screen layout designer**, please remove that as well.</span></span> 



<a name="additional-resources"></a><span data-ttu-id="05cfa-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="05cfa-150">Additional resources</span></span>
--------

[<span data-ttu-id="05cfa-151">Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján</span><span class="sxs-lookup"><span data-stu-id="05cfa-151">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




