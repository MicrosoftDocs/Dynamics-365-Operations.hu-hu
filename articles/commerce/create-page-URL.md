---
title: Weblap URL-jének létrehozása
description: Ez a témakör egy lap URL-címének a webhelyén történő létrehozásával kapcsolatos alapfogalmakat és eljárásokat ismerteti.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ab7325dd4060392ed43e59c1ad48069d294d81c0
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697548"
---
# <a name="create-a-page-url"></a><span data-ttu-id="cab89-103">Weblap URL-jének létrehozása</span><span class="sxs-lookup"><span data-stu-id="cab89-103">Create a page URL</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="cab89-104">Ez a témakör egy lap URL-címének a webhelyén történő létrehozásával kapcsolatos alapfogalmakat és eljárásokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="cab89-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

## <a name="overview"></a><span data-ttu-id="cab89-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cab89-105">Overview</span></span>

<span data-ttu-id="cab89-106">A webhely egy lapjára mutató teljes vagy abszolút URL-cím különböző részekből áll.</span><span class="sxs-lookup"><span data-stu-id="cab89-106">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="cab89-107">Például a `https://www.contoso.com/en-us/contactus` URL-cím a következő részekből áll:</span><span class="sxs-lookup"><span data-stu-id="cab89-107">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="cab89-108">`https://www.contoso.com`– A HTTP protokoll és a webhely tartománya.</span><span class="sxs-lookup"><span data-stu-id="cab89-108">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="cab89-109">`/en-us`– A webhely nyelvi elérési útja.</span><span class="sxs-lookup"><span data-stu-id="cab89-109">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="cab89-110">`/contactus`– A **Kapcsolat** lap relatív URL-címe.</span><span class="sxs-lookup"><span data-stu-id="cab89-110">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="cab89-111">A relatív URL ismert URL *alkategória* néven is.</span><span class="sxs-lookup"><span data-stu-id="cab89-111">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="cab89-112">A webhelye tartományát és az opcionális nyelvi útvonalat a webhely beállításakor hozhatja létre.</span><span class="sxs-lookup"><span data-stu-id="cab89-112">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="cab89-113">A webhely beállításai között található online áruházi lapok segítségével további tartományokat és nyelvi útvonalakat adhat hozzá a webhelyhez.</span><span class="sxs-lookup"><span data-stu-id="cab89-113">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="cab89-114">A lap URL alkategóriája önálló entitásként létezik a webhelylétrehozási környezetben.</span><span class="sxs-lookup"><span data-stu-id="cab89-114">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="cab89-115">A lap URL-címe két részből áll: az URL alkategóriát képviselő névből, valamint a webhelye vagy egy külső webhely egyik lapjára irányuló mutatóból.</span><span class="sxs-lookup"><span data-stu-id="cab89-115">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="cab89-116">A lap URL-címe beállítható úgy is, hogy a webhelye vagy egy külső webhely másik lapjára irányítson át.</span><span class="sxs-lookup"><span data-stu-id="cab89-116">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="cab89-117">Weblap URL-jének létrehozása</span><span class="sxs-lookup"><span data-stu-id="cab89-117">Create a page URL</span></span>

<span data-ttu-id="cab89-118">Kétféle módon hozhatók létre lap URL-ek:</span><span class="sxs-lookup"><span data-stu-id="cab89-118">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="cab89-119">Automatikusan a lap létrehozásakor</span><span class="sxs-lookup"><span data-stu-id="cab89-119">Automatically, when you create a page</span></span>
- <span data-ttu-id="cab89-120">Manuálisan, az **URL-ek** lapról</span><span class="sxs-lookup"><span data-stu-id="cab89-120">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="cab89-121">Lap URL létrehozása a lap létrehozásakor</span><span class="sxs-lookup"><span data-stu-id="cab89-121">Create a page URL when you create a page</span></span>

<span data-ttu-id="cab89-122">Ha egy új lap létrehozásakor megad egy nevet az **URL** mezőben, akkor az **URL-ek** lapon automatikusan létrejön egy lap URL, amely erre a lapra mutat.</span><span class="sxs-lookup"><span data-stu-id="cab89-122">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="cab89-123">Miután közzétette az URL-címet és a lapot, amelyre mutat, a webhely felhasználói (az Ön ügyfelei) hozzáférhetnek az URL-címhez társított laphoz.</span><span class="sxs-lookup"><span data-stu-id="cab89-123">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="cab89-124">Ha egy URL-címet anélkül a lap nélkül tesz közzé, amelyre mutat, akkor a webhely felhasználói 404 hibaüzenetet kapnak, amikor megpróbálnak hozzáférni a laphoz.</span><span class="sxs-lookup"><span data-stu-id="cab89-124">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="cab89-125">Ha a weblapot a rámutató URL közzététele nélkül teszi közzé, akkor a lap nem érhető el URL használatával.</span><span class="sxs-lookup"><span data-stu-id="cab89-125">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="cab89-126">Lap URL manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="cab89-126">Manually create a page URL</span></span>

<span data-ttu-id="cab89-127">Amikor új lapokat hoz létre, nem kell megadnia a lap URL-jét.</span><span class="sxs-lookup"><span data-stu-id="cab89-127">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="cab89-128">Ha üresen hagyja az URL mezőt, akkor a lap egy hivatkozás nélküli állapotban jön létre.</span><span class="sxs-lookup"><span data-stu-id="cab89-128">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="cab89-129">Ebben az esetben a vevők nem férhetnek hozzá a laphoz még akkor sem, ha az közzé van téve.</span><span class="sxs-lookup"><span data-stu-id="cab89-129">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="cab89-130">A lap elérhetővé tételéhez manuálisan kell létrehoznia az URL-címet, és társítania kell azt a laphoz.</span><span class="sxs-lookup"><span data-stu-id="cab89-130">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="cab89-131">A lap URL-címének manuális létrehozásához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cab89-131">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="cab89-132">Az **URL-ek** lapon válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cab89-132">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="cab89-133">Válassza ki a webhelynek az URL-hez társítani kívánt lapját.</span><span class="sxs-lookup"><span data-stu-id="cab89-133">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="cab89-134">Adja meg az URL alkategóriát, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cab89-134">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="cab89-135">Ezen a ponton az URL piszkozat állapotban van.</span><span class="sxs-lookup"><span data-stu-id="cab89-135">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="cab89-136">Közzé kell tenni ahhoz, hogy a webhely felhasználói elérjék a társított oldalt.</span><span class="sxs-lookup"><span data-stu-id="cab89-136">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="cab89-137">Lap URL-címének frissítése</span><span class="sxs-lookup"><span data-stu-id="cab89-137">Update a page URL</span></span>

<span data-ttu-id="cab89-138">A lap URL céllapjának frissítéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cab89-138">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="cab89-139">Az **URL-ek** lapon válassza ki a frissítendő URL-címet.</span><span class="sxs-lookup"><span data-stu-id="cab89-139">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="cab89-140">A jobb oldali tulajdonságlapon nyomja meg a céllap mező melletti három pont gombot (**...**).</span><span class="sxs-lookup"><span data-stu-id="cab89-140">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="cab89-141">A párbeszédpanelen válasszon ki egy másik lapot, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="cab89-141">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="cab89-142">Mentse és tegye közzé az URL-t.</span><span class="sxs-lookup"><span data-stu-id="cab89-142">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="cab89-143">Lap URL-címének átirányítása</span><span class="sxs-lookup"><span data-stu-id="cab89-143">Redirect a page URL</span></span>

<span data-ttu-id="cab89-144">Bizonyos esetekben előfordulhat, hogy a vevőknek egy másik lapot kíván megjeleníteni, amikor egy adott URL-címet kérnek.</span><span class="sxs-lookup"><span data-stu-id="cab89-144">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="cab89-145">Ezekben az esetekben a legjobb és legegyszerűbb módszer, ha módosítja a lapot, amelyre a lap URL-címe mutat.</span><span class="sxs-lookup"><span data-stu-id="cab89-145">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="cab89-146">Előfordulhat azonban, hogy jogos oka van arra, hogy a HTTP 301-es vagy 3023-as átirányítások használatával az adott URL-címre vonatkozó kéréseket egy eltérő URL-címre irányítsa át.</span><span class="sxs-lookup"><span data-stu-id="cab89-146">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="cab89-147">Az URL-címnek egy eltérő URL-címre való átirányításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="cab89-147">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="cab89-148">Az **URL-ek** lapon válassza ki a frissítendő URL-címet.</span><span class="sxs-lookup"><span data-stu-id="cab89-148">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="cab89-149">A jobb oldali tulajdonságlapon válassza az **Átirányítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="cab89-149">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="cab89-150">Válassza ki az átirányítás célját:</span><span class="sxs-lookup"><span data-stu-id="cab89-150">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="cab89-151">Ha a webhely egy másik lapjára szeretne mutatni, válassza a **Belső URL** lehetőséget, nyomja meg a három pont gombot (**...**), majd válassza ki azt az URL-címet, amelyre át szeretné irányítani.</span><span class="sxs-lookup"><span data-stu-id="cab89-151">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="cab89-152">Ha egy külső webhelyen található lapra szeretne átirányítani, válassza ki a **Külső URL** lehetőséget, majd írja be a lap teljes URL-címét.</span><span class="sxs-lookup"><span data-stu-id="cab89-152">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="cab89-153">Ne feledje el belefoglalni a protokollt.</span><span class="sxs-lookup"><span data-stu-id="cab89-153">Be sure to include the protocol.</span></span> <span data-ttu-id="cab89-154">Például írja be, hogy `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="cab89-154">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="cab89-155">Ha egy URL-cím már át van irányítva egy belső URL-címre, akkor válassza a **Kijelölés törlése** lehetőséget, mielőtt megadna egy külső URL-címet.</span><span class="sxs-lookup"><span data-stu-id="cab89-155">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="cab89-156">Válasszon egy átirányítástípust:</span><span class="sxs-lookup"><span data-stu-id="cab89-156">Select a redirect type:</span></span>

    - <span data-ttu-id="cab89-157">**Állandó átirányítás (301)** – Akkor válassza ezt a lehetőséget, ha tudja, hogy a tartalom véglegesen áthelyezésre került, és nem lesz visszaállítva a korábbi URL-címre.</span><span class="sxs-lookup"><span data-stu-id="cab89-157">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="cab89-158">A keresőmotorok hozzárendelik az átirányító URL keresőmotor-optimalizálási (SEO) értékét az átirányított URL-címhez, és frissítik a rekordjaikat, hogy azok az új URL-címet jelenítsék meg.</span><span class="sxs-lookup"><span data-stu-id="cab89-158">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="cab89-159">**Ideiglenes átirányítás (302)** – Válassza ezt a lehetőséget, ha a forgalmat a keresőmotorok frissítése nélkül szeretné átirányítani.</span><span class="sxs-lookup"><span data-stu-id="cab89-159">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="cab89-160">Ez a módszer általában akkor használatos, ha a tartalom hamarosan visszatért a korábbi URL-címre.</span><span class="sxs-lookup"><span data-stu-id="cab89-160">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="cab89-161">Amikor készen áll az átirányítás végrehajtására, mentse és tegye közzé az URL-címet.</span><span class="sxs-lookup"><span data-stu-id="cab89-161">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cab89-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cab89-162">Additional resources</span></span>

[<span data-ttu-id="cab89-163">Webhely-navigáció testreszabása</span><span class="sxs-lookup"><span data-stu-id="cab89-163">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="cab89-164">Új webhelyoldal hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cab89-164">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="cab89-165">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="cab89-165">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="cab89-166">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="cab89-166">Add languages to your site</span></span>](add-languages-to-site.md)
