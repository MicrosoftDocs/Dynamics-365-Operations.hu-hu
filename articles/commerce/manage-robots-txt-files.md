---
title: Robots.txt fájlok kezelése
description: Ez a témakör a robots. txt fájl kezelésének módját ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban.
author: BrianShook
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: d0ce49f2968030ca4656a01c7646819c01635e12
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003487"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="6fea1-103">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="6fea1-103">Manage robots.txt files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6fea1-104">Ez a témakör a robots. txt fájl kezelésének módját ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="6fea1-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6fea1-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="6fea1-105">Overview</span></span>

<span data-ttu-id="6fea1-106">A robotkizárási szabvány, vagy a robots.txt egy olyan szabvány, amelyet a webhelyek a webrobotokkal való kommunikációra használnak.</span><span class="sxs-lookup"><span data-stu-id="6fea1-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="6fea1-107">A webrobotokat utasítja a webhely minden olyan területével kapcsolatban, amit nem kell felkeresniük.</span><span class="sxs-lookup"><span data-stu-id="6fea1-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="6fea1-108">A robotokat gyakran használják a keresőmotorok webhelyek indexeléséhez.</span><span class="sxs-lookup"><span data-stu-id="6fea1-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="6fea1-109">A robotok kiszolgálóról való kizárásához egy fájlt kell létrehoznia a kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="6fea1-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="6fea1-110">Ebben a fájlban megad egy hozzáférési irányelvet a robotok számára.</span><span class="sxs-lookup"><span data-stu-id="6fea1-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="6fea1-111">A fájlnak HTTP-n keresztüli elérhetőnek kell lennie a **/robots.txt** helyi URL-címen.</span><span class="sxs-lookup"><span data-stu-id="6fea1-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="6fea1-112">A robots.txt fájl segítségével a keresőmotorok indexelik a webhely tartalmát.</span><span class="sxs-lookup"><span data-stu-id="6fea1-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="6fea1-113">A Dynamics 365 Commerce lehetővé teszi, hogy feltöltsön egy robots.txt fájlt a tartományához.</span><span class="sxs-lookup"><span data-stu-id="6fea1-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="6fea1-114">A Commerce környezetben található minden tartományhoz feltölthet egy robots.txt fájlt, és azt hozzárendelheti az adott tartományhoz.</span><span class="sxs-lookup"><span data-stu-id="6fea1-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="6fea1-115">Ha többet szeretne tudni a robots.txt fájlról, keresse fel a [Webrobotok oldalait](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="6fea1-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="6fea1-116">Robots.txt fájl feltöltése</span><span class="sxs-lookup"><span data-stu-id="6fea1-116">Upload a robots.txt file</span></span>

<span data-ttu-id="6fea1-117">Miután létrehozta és módosította a robots.txt fájlt a [robotkizárási szabvány](https://www.robotstxt.org/orig.html) szerint, ellenőrizze, hogy a fájl elérhető-e azon a számítógépen, amelyen a Commerce szerkesztőeszközöket fogja használni.</span><span class="sxs-lookup"><span data-stu-id="6fea1-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="6fea1-118">A fájlnak a **robots.txt** nevet kell adni.</span><span class="sxs-lookup"><span data-stu-id="6fea1-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="6fea1-119">A legjobb eredmény érdekében a szabványban megadott formátummal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="6fea1-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="6fea1-120">Minden egyes Commerce-ügyfél felelős a robots.txt fájl tartalmának érvényesítéséért és fenntartásáért.</span><span class="sxs-lookup"><span data-stu-id="6fea1-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="6fea1-121">A robots.txt fájl feltöltéséhez be kell jelentkeznie a Commerce rendszerbe rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="6fea1-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="6fea1-122">A robots.txt fájl feltöltéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6fea1-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6fea1-123">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="6fea1-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="6fea1-124">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="6fea1-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="6fea1-125">A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt.</span><span class="sxs-lookup"><span data-stu-id="6fea1-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="6fea1-126">A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.</span><span class="sxs-lookup"><span data-stu-id="6fea1-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="6fea1-127">Válassza a **Kezelés** lehetőséget a robots.txt fájl feltöltéséhez a környezete egyik tartományához.</span><span class="sxs-lookup"><span data-stu-id="6fea1-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="6fea1-128">A jobb oldali menüben kattintson a **Feltöltés** gombra (felfelé mutató nyíl) a robots.txt fájlhoz társított tartomány mellett.</span><span class="sxs-lookup"><span data-stu-id="6fea1-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="6fea1-129">Megjelenik egy fájlböngésző párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="6fea1-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="6fea1-130">A párbeszédpanelen tallózással keresse meg és jelölje ki azt a robots.txt fájlt, amelyet fel szeretne tölteni a társított tartományra, majd válassza a **Megnyitás** lehetőséget a feltöltés befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="6fea1-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="6fea1-131">A feltöltés során a Commerce ellenőrzi, hogy a fájl szövegfájl-e, de nem érvényesíti a fájl tartalmát.</span><span class="sxs-lookup"><span data-stu-id="6fea1-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="6fea1-132">Robots.txt fájl letöltése</span><span class="sxs-lookup"><span data-stu-id="6fea1-132">Download a robots.txt file</span></span>

<span data-ttu-id="6fea1-133">A robots.txt fájl letöltéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6fea1-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6fea1-134">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="6fea1-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="6fea1-135">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="6fea1-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="6fea1-136">A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt.</span><span class="sxs-lookup"><span data-stu-id="6fea1-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="6fea1-137">A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.</span><span class="sxs-lookup"><span data-stu-id="6fea1-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="6fea1-138">Válassza a **Kezelés** lehetőséget a robots.txt fájl letöltéséhez a környezete egyik tartományához.</span><span class="sxs-lookup"><span data-stu-id="6fea1-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="6fea1-139">A jobb oldali menüben kattintson a **Letöltés** gombra (lefelé mutató nyíl) a robots.txt fájlhoz társított tartomány mellett.</span><span class="sxs-lookup"><span data-stu-id="6fea1-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="6fea1-140">Megjelenik egy fájlböngésző párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="6fea1-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="6fea1-141">A párbeszédpanelen keresse meg a helyi meghajtón a kívánt helyet, erősítse meg vagy adja meg a fájlnevet, majd válassza a **Mentés** lehetőséget a letöltés befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="6fea1-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="6fea1-142">Ezzel az eljárással csak a korábban a Commerce szerkesztőeszközökkel feltöltött robots.txt fájlok tölthetők le.</span><span class="sxs-lookup"><span data-stu-id="6fea1-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="6fea1-143">Robots.txt fájl törlése</span><span class="sxs-lookup"><span data-stu-id="6fea1-143">Delete a robots.txt file</span></span>

<span data-ttu-id="6fea1-144">A robots.txt fájl törléséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6fea1-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6fea1-145">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="6fea1-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="6fea1-146">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="6fea1-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="6fea1-147">A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt.</span><span class="sxs-lookup"><span data-stu-id="6fea1-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="6fea1-148">A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.</span><span class="sxs-lookup"><span data-stu-id="6fea1-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="6fea1-149">Válassza a **Kezelés** lehetőséget a robots.txt fájl törléséhez a környezete egyik tartománya esetében.</span><span class="sxs-lookup"><span data-stu-id="6fea1-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="6fea1-150">A jobb oldali menüben kattintson a **Törlés** gombra (szemeteskuka szimbólum) a robots.txt fájlhoz társított tartomány mellett.</span><span class="sxs-lookup"><span data-stu-id="6fea1-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="6fea1-151">Megjelenik egy fájlböngésző ablak.</span><span class="sxs-lookup"><span data-stu-id="6fea1-151">A file browser window appears.</span></span>
6. <span data-ttu-id="6fea1-152">A fájlböngésző ablakban tallózással keresse meg és jelölje ki azt a robots.txt fájlt, amelyet törlni szeretne a tartomány esetében, majd válassza a **Megnyitás** lehetőséget a feltöltés befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="6fea1-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="6fea1-153">Megjelenik egy figyelmeztető üzenetpanel.</span><span class="sxs-lookup"><span data-stu-id="6fea1-153">A warning message box appears.</span></span>
7. <span data-ttu-id="6fea1-154">Az üzenetpanelen válassza a **Törlés** lehetőséget a robots.txt fájl törlésének jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="6fea1-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="6fea1-155">Ezzel az eljárással csak a korábban a Commerce szerkesztőeszközökkel feltöltött robots.txt fájlok törölhetők.</span><span class="sxs-lookup"><span data-stu-id="6fea1-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6fea1-156">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6fea1-156">Additional resources</span></span>

[<span data-ttu-id="6fea1-157">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6fea1-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="6fea1-158">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="6fea1-158">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="6fea1-159">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="6fea1-159">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="6fea1-160">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="6fea1-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="6fea1-161">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="6fea1-161">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="6fea1-162">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6fea1-162">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="6fea1-163">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="6fea1-163">Enable location-based store detection</span></span>](enable-store-detection.md)
