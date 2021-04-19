---
title: robots.txt fájlok kezelése
description: Ez a témakör a robots. txt fájl kezelésének módját ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban.
author: BrianShook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: b9b832d6714447f8957095c8c87d48527087f12d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794235"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="69887-103">robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="69887-103">Manage robots.txt files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="69887-104">Ez a témakör a robots. txt fájl kezelésének módját ismerteti a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="69887-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="69887-105">A robotkizárási szabvány, vagy a robots.txt egy olyan szabvány, amelyet a webhelyek a webrobotokkal való kommunikációra használnak.</span><span class="sxs-lookup"><span data-stu-id="69887-105">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="69887-106">A webrobotokat utasítja a webhely minden olyan területével kapcsolatban, amit nem kell felkeresniük.</span><span class="sxs-lookup"><span data-stu-id="69887-106">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="69887-107">A robotokat gyakran használják a keresőmotorok webhelyek indexeléséhez.</span><span class="sxs-lookup"><span data-stu-id="69887-107">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="69887-108">A robotok kiszolgálóról való kizárásához egy fájlt kell létrehoznia a kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="69887-108">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="69887-109">Ebben a fájlban megad egy hozzáférési irányelvet a robotok számára.</span><span class="sxs-lookup"><span data-stu-id="69887-109">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="69887-110">A fájlnak HTTP-n keresztüli elérhetőnek kell lennie a **/robots.txt** helyi URL-címen.</span><span class="sxs-lookup"><span data-stu-id="69887-110">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="69887-111">A robots.txt fájl segítségével a keresőmotorok indexelik a webhely tartalmát.</span><span class="sxs-lookup"><span data-stu-id="69887-111">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="69887-112">A Dynamics 365 Commerce lehetővé teszi, hogy feltöltsön egy robots.txt fájlt a tartományához.</span><span class="sxs-lookup"><span data-stu-id="69887-112">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="69887-113">A Commerce környezetben található minden tartományhoz feltölthet egy robots.txt fájlt, és azt hozzárendelheti az adott tartományhoz.</span><span class="sxs-lookup"><span data-stu-id="69887-113">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="69887-114">Ha többet szeretne tudni a robots.txt fájlról, keresse fel a [Webrobotok oldalait](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="69887-114">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="69887-115">Robots.txt fájl feltöltése</span><span class="sxs-lookup"><span data-stu-id="69887-115">Upload a robots.txt file</span></span>

<span data-ttu-id="69887-116">Miután létrehozta és módosította a robots.txt fájlt a [robotkizárási szabvány](https://www.robotstxt.org/orig.html) szerint, ellenőrizze, hogy a fájl elérhető-e azon a számítógépen, amelyen a Commerce szerkesztőeszközöket fogja használni.</span><span class="sxs-lookup"><span data-stu-id="69887-116">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="69887-117">A fájlnak a **robots.txt** nevet kell adni.</span><span class="sxs-lookup"><span data-stu-id="69887-117">The file must be named **robots.txt**.</span></span> <span data-ttu-id="69887-118">A legjobb eredmény érdekében a szabványban megadott formátummal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="69887-118">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="69887-119">Minden egyes Commerce-ügyfél felelős a robots.txt fájl tartalmának érvényesítéséért és fenntartásáért.</span><span class="sxs-lookup"><span data-stu-id="69887-119">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="69887-120">A robots.txt fájl feltöltéséhez be kell jelentkeznie a Commerce rendszerbe rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="69887-120">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="69887-121">A robots.txt fájl feltöltéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="69887-121">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="69887-122">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="69887-122">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="69887-123">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="69887-123">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="69887-124">A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt.</span><span class="sxs-lookup"><span data-stu-id="69887-124">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="69887-125">A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.</span><span class="sxs-lookup"><span data-stu-id="69887-125">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="69887-126">Válassza a **Kezelés** lehetőséget a robots.txt fájl feltöltéséhez a környezete egyik tartományához.</span><span class="sxs-lookup"><span data-stu-id="69887-126">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="69887-127">A jobb oldali menüben kattintson a **Feltöltés** gombra (felfelé mutató nyíl) a robots.txt fájlhoz társított tartomány mellett.</span><span class="sxs-lookup"><span data-stu-id="69887-127">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="69887-128">Megjelenik egy fájlböngésző párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="69887-128">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="69887-129">A párbeszédpanelen tallózással keresse meg és jelölje ki azt a robots.txt fájlt, amelyet fel szeretne tölteni a társított tartományra, majd válassza a **Megnyitás** lehetőséget a feltöltés befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="69887-129">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="69887-130">A feltöltés során a Commerce ellenőrzi, hogy a fájl szövegfájl-e, de nem érvényesíti a fájl tartalmát.</span><span class="sxs-lookup"><span data-stu-id="69887-130">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="69887-131">Robots.txt fájl letöltése</span><span class="sxs-lookup"><span data-stu-id="69887-131">Download a robots.txt file</span></span>

<span data-ttu-id="69887-132">A robots.txt fájl letöltéséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="69887-132">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="69887-133">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="69887-133">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="69887-134">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="69887-134">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="69887-135">A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt.</span><span class="sxs-lookup"><span data-stu-id="69887-135">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="69887-136">A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.</span><span class="sxs-lookup"><span data-stu-id="69887-136">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="69887-137">Válassza a **Kezelés** lehetőséget a robots.txt fájl letöltéséhez a környezete egyik tartományához.</span><span class="sxs-lookup"><span data-stu-id="69887-137">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="69887-138">A jobb oldali menüben kattintson a **Letöltés** gombra (lefelé mutató nyíl) a robots.txt fájlhoz társított tartomány mellett.</span><span class="sxs-lookup"><span data-stu-id="69887-138">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="69887-139">Megjelenik egy fájlböngésző párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="69887-139">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="69887-140">A párbeszédpanelen keresse meg a helyi meghajtón a kívánt helyet, erősítse meg vagy adja meg a fájlnevet, majd válassza a **Mentés** lehetőséget a letöltés befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="69887-140">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="69887-141">Ezzel az eljárással csak a korábban a Commerce szerkesztőeszközökkel feltöltött robots.txt fájlok tölthetők le.</span><span class="sxs-lookup"><span data-stu-id="69887-141">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="69887-142">Robots.txt fájl törlése</span><span class="sxs-lookup"><span data-stu-id="69887-142">Delete a robots.txt file</span></span>

<span data-ttu-id="69887-143">A robots.txt fájl törléséhez a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="69887-143">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="69887-144">Rendszergazdaként jelentkezzen be a Commerce rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="69887-144">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="69887-145">A bal oldali navigációs ablaktáblán válassza ki a **Bérlői beállítások** (a fogaskerék szimbólum mellett) lehetőséget a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="69887-145">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="69887-146">A **Bérlő beállításai** területen válassza a **Robots.txt** fájlt.</span><span class="sxs-lookup"><span data-stu-id="69887-146">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="69887-147">A környezetéhez társított összes tartomány listája megjelenik az ablak fő részében.</span><span class="sxs-lookup"><span data-stu-id="69887-147">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="69887-148">Válassza a **Kezelés** lehetőséget a robots.txt fájl törléséhez a környezete egyik tartománya esetében.</span><span class="sxs-lookup"><span data-stu-id="69887-148">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="69887-149">A jobb oldali menüben kattintson a **Törlés** gombra (szemeteskuka szimbólum) a robots.txt fájlhoz társított tartomány mellett.</span><span class="sxs-lookup"><span data-stu-id="69887-149">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="69887-150">Megjelenik egy fájlböngésző ablak.</span><span class="sxs-lookup"><span data-stu-id="69887-150">A file browser window appears.</span></span>
6. <span data-ttu-id="69887-151">A fájlböngésző ablakban tallózással keresse meg és jelölje ki azt a robots.txt fájlt, amelyet törlni szeretne a tartomány esetében, majd válassza a **Megnyitás** lehetőséget a feltöltés befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="69887-151">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="69887-152">Megjelenik egy figyelmeztető üzenetpanel.</span><span class="sxs-lookup"><span data-stu-id="69887-152">A warning message box appears.</span></span>
7. <span data-ttu-id="69887-153">Az üzenetpanelen válassza a **Törlés** lehetőséget a robots.txt fájl törlésének jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="69887-153">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="69887-154">Ezzel az eljárással csak a korábban a Commerce szerkesztőeszközökkel feltöltött robots.txt fájlok törölhetők.</span><span class="sxs-lookup"><span data-stu-id="69887-154">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69887-155">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="69887-155">Additional resources</span></span>

[<span data-ttu-id="69887-156">Tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="69887-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="69887-157">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="69887-157">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="69887-158">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="69887-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="69887-159">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="69887-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="69887-160">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="69887-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="69887-161">B2C-bérlő beállítása a Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="69887-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="69887-162">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="69887-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="69887-163">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="69887-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="69887-164">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="69887-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="69887-165">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="69887-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
