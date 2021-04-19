---
title: Statikus fájlok feltöltése és kiszolgálása
description: Ez a témakör azt ismerteti, hogy miként tölthet fel statikus fájlt a Microsoft Dynamics 365 Commerce webhelyszerkesztőjébe, és hogyan hozhat létre egyéni URL-címet és fájlnevet, amely az adott fájl igényléséhez használható.
author: StuHarg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d5f092042b3dda65b041ab2f25f7319dd8e158d1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801385"
---
# <a name="upload-and-serve-static-files"></a><span data-ttu-id="8af0b-103">Statikus fájlok feltöltése és kiszolgálása</span><span class="sxs-lookup"><span data-stu-id="8af0b-103">Upload and serve static files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8af0b-104">Ez a témakör azt ismerteti, hogy miként tölthet fel statikus fájlt a Microsoft Dynamics 365 Commerce webhelyszerkesztőjébe, és hogyan hozhat létre egyéni URL-címet és fájlnevet, amely az adott fájl igényléséhez használható.</span><span class="sxs-lookup"><span data-stu-id="8af0b-104">This topic describes how to upload a static file into Microsoft Dynamics 365 Commerce site builder, and how to create a custom URL and file name that can be used to request that file.</span></span>

<span data-ttu-id="8af0b-105">Egyes külső összekötők megkövetelik, hogy egy fájlt az e-kereskedelmi webhelyről tárolják és szolgálják ki.</span><span class="sxs-lookup"><span data-stu-id="8af0b-105">Some third-party connectors require that a file be hosted and served from the e-commerce site.</span></span> <span data-ttu-id="8af0b-106">Ezek az összekötők arra számítanak, hogy a fájlt egy adott visszahívási URL elérési útvonalra és fájlnévre irányuló kérelmek adják vissza.</span><span class="sxs-lookup"><span data-stu-id="8af0b-106">These connectors expect that the file will be returned by requests to a specific callback URL path and file name.</span></span> <span data-ttu-id="8af0b-107">Ezért ez a témakör azt ismerteti, hogyan tölthet fel és szolgálhat ki olyan statikus fájlt, amely felhasználó által definiálható URL-címmel és fájlnévvel rendelkezik egy Dynamics 365 Commerce e-kereskedelmi webhelyen.</span><span class="sxs-lookup"><span data-stu-id="8af0b-107">Therefore, this topic explains how to upload and serve a static file that has a user-definable URL and file name on a Dynamics 365 Commerce e-commerce site.</span></span>

## <a name="create-a-site-url-that-returns-a-static-file"></a><span data-ttu-id="8af0b-108">Statikus fájlt visszaadó webhely URL-címének létrehozása</span><span class="sxs-lookup"><span data-stu-id="8af0b-108">Create a site URL that returns a static file</span></span>

<span data-ttu-id="8af0b-109">Ha olyan webhely URL-címet szeretne létrehozni, amely statikus fájlt ad vissza a Commerce webhelyszerkesztőben, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8af0b-109">To create a site URL that returns a static file in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="8af0b-110">Nyissa meg a webhely médiatárát, és töltse fel azt a fájlt, amelyet a megadott URL-címre érkező kéréseknek kell kézbesíteni.</span><span class="sxs-lookup"><span data-stu-id="8af0b-110">Go to your site's Media library, and upload the file that should be served by requests to the URL that you will define.</span></span> <span data-ttu-id="8af0b-111">Ha már feltöltötte a fájlt, kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="8af0b-111">If you've already uploaded the file, you can skip this step.</span></span>
1. <span data-ttu-id="8af0b-112">Nyissa meg a webhely **URL-címeit**.</span><span class="sxs-lookup"><span data-stu-id="8af0b-112">Go to **URLs** for your site.</span></span>
1. <span data-ttu-id="8af0b-113">Válassza az **Új \> Új URL-cím** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-113">Select **New \> New URL**.</span></span>
1. <span data-ttu-id="8af0b-114">Az **Új URL-cím** párbeszédpanelen válassza a **Médiatár-eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-114">In the **New URL** dialog box, select **Media library asset**.</span></span>
1. <span data-ttu-id="8af0b-115">Az **URL elérési út** mezőbe írja be az URL elérési utat.</span><span class="sxs-lookup"><span data-stu-id="8af0b-115">In the **URL path** field, enter the URL path.</span></span> <span data-ttu-id="8af0b-116">Adja meg a fájlnevet az elérési útban.</span><span class="sxs-lookup"><span data-stu-id="8af0b-116">Include the file name in the path.</span></span>
1. <span data-ttu-id="8af0b-117">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-117">Select **Next**.</span></span> <span data-ttu-id="8af0b-118">Megnyílik a Médiatár, és megjeleníti a feltöltött **dokumentum** típusú összes médiaelemet.</span><span class="sxs-lookup"><span data-stu-id="8af0b-118">The Media library is opened and shows all media assets of the **document** type that have been uploaded.</span></span>
1. <span data-ttu-id="8af0b-119">Válassza ki azt a fájlt, amelyet az 5. lépésben meghatározott URL-címre vonatkozó kérések esetén kell megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="8af0b-119">Select the file that should be served for requests to the URL that you defined in step 5.</span></span>
1. <span data-ttu-id="8af0b-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-120">Select **Save**.</span></span>

<span data-ttu-id="8af0b-121">Ezen a ponton a létrehozott URL piszkozat állapotban van.</span><span class="sxs-lookup"><span data-stu-id="8af0b-121">At this point, the URL that you created is in a draft state.</span></span> <span data-ttu-id="8af0b-122">Az URL-cím által mutatott fájl csak akkor lesz visszaadva, ha közzéteszi az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="8af0b-122">The file that the URL points to won't be returned until you publish the URL.</span></span> <span data-ttu-id="8af0b-123">Az URL közzététele előtt ellenőrizheti, hogy a megfelelő adatokat adja-e vissza.</span><span class="sxs-lookup"><span data-stu-id="8af0b-123">Before you publish the URL, you can validate that it returns the correct data.</span></span>

## <a name="validate-and-publish-a-url"></a><span data-ttu-id="8af0b-124">URL ellenőrzése és közzététele</span><span class="sxs-lookup"><span data-stu-id="8af0b-124">Validate and publish a URL</span></span>

<span data-ttu-id="8af0b-125">Az URL közzététel előtti ellenőrzéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8af0b-125">To validate an URL before you publish it, follow these steps.</span></span>

1. <span data-ttu-id="8af0b-126">Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet az előnézethez.</span><span class="sxs-lookup"><span data-stu-id="8af0b-126">Go to **URLs** for your site, and select the URL to preview.</span></span>
2. <span data-ttu-id="8af0b-127">A jobb oldali Tulajdonságok ablaktáblán, a **Szerkesztés** gomb alatt válassza ki a megfelelő URL-hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="8af0b-127">In the properties pane on the right, below the **Edit** button, select the correct URL link.</span></span> <span data-ttu-id="8af0b-128">Egy új böngészőablak nyílik meg, és 404-es hibaüzenetet kell kapnia.</span><span class="sxs-lookup"><span data-stu-id="8af0b-128">A new browser window is opened, and you should receive a 404 error.</span></span>
3. <span data-ttu-id="8af0b-129">Fűzze a **?preview=inprogress** lekérdezési sztringet az URL-címhez (például `https://yoursite.com/callback.html?preview=inprogress`), és töltse be újra az oldalt.</span><span class="sxs-lookup"><span data-stu-id="8af0b-129">Append the **?preview=inprogress** query string to the URL (for example, `https://yoursite.com/callback.html?preview=inprogress`), and reload the page.</span></span> <span data-ttu-id="8af0b-130">A válaszban a rendszernek a médiatárba feltöltött fájlt kell visszaadnia.</span><span class="sxs-lookup"><span data-stu-id="8af0b-130">The file that you uploaded to the Media library should be returned in the response.</span></span>

<span data-ttu-id="8af0b-131">Miután ellenőrizte az URL-címet, közzéteheti azt.</span><span class="sxs-lookup"><span data-stu-id="8af0b-131">After you've validated the URL, you can publish it.</span></span>

1. <span data-ttu-id="8af0b-132">Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet.</span><span class="sxs-lookup"><span data-stu-id="8af0b-132">Go to **URLs** for your site, and select the URL.</span></span>
2. <span data-ttu-id="8af0b-133">Válassza a parancssáv **Közzététel** elemét.</span><span class="sxs-lookup"><span data-stu-id="8af0b-133">Select **Publish** on the command bar.</span></span>

## <a name="update-the-file-that-a-url-points-to"></a><span data-ttu-id="8af0b-134">A fájl frissítése, amelyre egy URL-cím mutat</span><span class="sxs-lookup"><span data-stu-id="8af0b-134">Update the file that a URL points to</span></span>

<span data-ttu-id="8af0b-135">Az URL-cím közzététele után frissítheti azt, hogy az egy másik fájlra mutatjon.</span><span class="sxs-lookup"><span data-stu-id="8af0b-135">After a URL is published, you can update it so that it points to a different file.</span></span> <span data-ttu-id="8af0b-136">Azt is megteheti, hogy frissíti az URL-címet, hogy egy másik erőforrástípusra mutasson a következő szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="8af0b-136">Alternatively, you can update the URL so that it points to a different the type of resource, as described in the next section.</span></span> <span data-ttu-id="8af0b-137">Az URL-címet például egy belső oldalra vagy egy átirányításra irányíthatja.</span><span class="sxs-lookup"><span data-stu-id="8af0b-137">For example, you can point the URL to an internal page or a redirect.</span></span>

<span data-ttu-id="8af0b-138">Az URL-címmel megcélzott fájl frissítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8af0b-138">To update the file that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="8af0b-139">Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet a frissítéshez.</span><span class="sxs-lookup"><span data-stu-id="8af0b-139">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="8af0b-140">A jobb oldali tulajdonságok panelen válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-140">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="8af0b-141">Az **URL-hozzárendelés** szakaszban válassza a **2. lépés** mezőt, majd válasszon egy új dokumentumot a médiatárból.</span><span class="sxs-lookup"><span data-stu-id="8af0b-141">Under **URL assignment**, select the **Step 2** box, and then select a new document from the Media library.</span></span>
1. <span data-ttu-id="8af0b-142">Válassza az **Alkalmazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-142">Select **Apply**.</span></span>

## <a name="update-the-asset-type-that-a-url-points-to"></a><span data-ttu-id="8af0b-143">Az eszköztípus frissítése, amelyre egy URL-cím mutat</span><span class="sxs-lookup"><span data-stu-id="8af0b-143">Update the asset type that a URL points to</span></span>

<span data-ttu-id="8af0b-144">Az URL-címeket is frissítheti úgy, hogy az más típusú eszközre (erőforrásra), például belső oldalra vagy átirányításra mutasson.</span><span class="sxs-lookup"><span data-stu-id="8af0b-144">You can also update a URL so that it points to a different type of asset (resource), such as an internal page or a redirect.</span></span>

<span data-ttu-id="8af0b-145">Az URL-címmel megcélzott eszköztípus frissítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8af0b-145">To update the asset type that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="8af0b-146">Lépjen az **URL-címek** részhez a webhelynél, és válassza ki az URL címet a frissítéshez.</span><span class="sxs-lookup"><span data-stu-id="8af0b-146">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="8af0b-147">A jobb oldali tulajdonságok panelen válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-147">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="8af0b-148">Az **URL-hozzárendelés** szakaszban az **1. lépés** részben válasszon egy másik eszköztípust.</span><span class="sxs-lookup"><span data-stu-id="8af0b-148">Under **URL assignment**, under **Step 1**, select a different asset type.</span></span>
1. <span data-ttu-id="8af0b-149">Válassza a **2. lépés** mezőt, és válasszon új eszközt.</span><span class="sxs-lookup"><span data-stu-id="8af0b-149">Select the **Step 2** box, and then select the new asset.</span></span>
1. <span data-ttu-id="8af0b-150">Válassza az **Alkalmazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8af0b-150">Select **Apply**.</span></span>

## <a name="change-the-url-path"></a><span data-ttu-id="8af0b-151">Az URL elérési útjának módosítása</span><span class="sxs-lookup"><span data-stu-id="8af0b-151">Change the URL path</span></span>

<span data-ttu-id="8af0b-152">Az URL-cím létrehozása után az elérési út nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="8af0b-152">After a URL is created, its path can't be changed.</span></span> <span data-ttu-id="8af0b-153">Ha módosítania kell a fájlra vagy más típusú erőforrásra mutató URL-címet, új URL-címet kell létrehoznia, hozzá kell rendelnie a meglévő fájlhoz vagy más erőforráshoz, majd vissza kell vonnia a közzétételt, és törölnie kell a régi URL-címet.</span><span class="sxs-lookup"><span data-stu-id="8af0b-153">If you must change the URL path that serves a file or any other type of resource, you have to create a new URL, map it to the existing file or other resource, and then unpublish and delete the old URL.</span></span>

<span data-ttu-id="8af0b-154">Az URL-cím elérési útjának módosításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8af0b-154">To change the URL path, follow these steps.</span></span>

1. <span data-ttu-id="8af0b-155">Új URL-cím létrehozásához és a meglévő fájlhoz vagy más erőforráshoz való hozzárendeléséhez kövesse a jelen téma korábbi szakaszában, a [Statikus fájlt visszaadó webhely URL-címének létrehozása](#create-a-site-url-that-returns-a-static-file) részben leírt utasításokat.</span><span class="sxs-lookup"><span data-stu-id="8af0b-155">To create a new URL and map it to the existing file or another resource, follow the instructions in the [Create a site URL that returns a static file](#create-a-site-url-that-returns-a-static-file) section earlier in this topic.</span></span>
1. <span data-ttu-id="8af0b-156">Jelölje ki az új URL-címet, és válassza a **Közzététel** lehetőséget a parancssávon.</span><span class="sxs-lookup"><span data-stu-id="8af0b-156">Select the new URL, and select **Publish** on the command bar.</span></span> <span data-ttu-id="8af0b-157">Az új URL-cím közzé lesz téve.</span><span class="sxs-lookup"><span data-stu-id="8af0b-157">The new URL is published.</span></span>
1. <span data-ttu-id="8af0b-158">A régi URL közzétételének visszavonásához jelölje ki, majd válassza a **Közzététel visszavonás** elemet a parancssávon.</span><span class="sxs-lookup"><span data-stu-id="8af0b-158">To unpublish the old URL, select it, and then select **Unpublish** on the command bar.</span></span> <span data-ttu-id="8af0b-159">Most már törölheti a régi URL-t, ha akarja.</span><span class="sxs-lookup"><span data-stu-id="8af0b-159">You can now delete the old URL if you want.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8af0b-160">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8af0b-160">Additional resources</span></span>

[<span data-ttu-id="8af0b-161">Digitális eszközkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="8af0b-161">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="8af0b-162">Képek feltöltése</span><span class="sxs-lookup"><span data-stu-id="8af0b-162">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="8af0b-163">Videók feltöltése</span><span class="sxs-lookup"><span data-stu-id="8af0b-163">Upload videos</span></span>](dam-upload-video.md)

[<span data-ttu-id="8af0b-164">Fájlok feltöltése képek és videók kivételével</span><span class="sxs-lookup"><span data-stu-id="8af0b-164">Upload files other than images and videos</span></span>](dam-upload-files.md)

[<span data-ttu-id="8af0b-165">Képek körülvágása</span><span class="sxs-lookup"><span data-stu-id="8af0b-165">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="8af0b-166">Képfókuszpontok testreszabása</span><span class="sxs-lookup"><span data-stu-id="8af0b-166">Customize image focal points</span></span>](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]