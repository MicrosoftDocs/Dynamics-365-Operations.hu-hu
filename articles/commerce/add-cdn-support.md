---
title: Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.
author: brianshook
manager: annbe
ms.date: 07/31/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 662d26c0157377977bd1031cd7bb13a8e692f37e
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646039"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="3c221-103">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="3c221-103">Add support for a content delivery network (CDN)</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3c221-104">Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.</span><span class="sxs-lookup"><span data-stu-id="3c221-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="3c221-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="3c221-105">Overview</span></span>

<span data-ttu-id="3c221-106">Ha egy e-kereskedelmi környezetet hoz létre a Dynamics 365 Commerce alkalmazásban, akkor konfigurálhatja úgy, hogy együttműködjön az Ön CDN-szolgáltatásával.</span><span class="sxs-lookup"><span data-stu-id="3c221-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="3c221-107">Az Ön egyéni tartománya az e-kereskedelmi környezet létesítési folyamata során engedélyezhető.</span><span class="sxs-lookup"><span data-stu-id="3c221-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="3c221-108">Azt is megteheti, hogy egy szolgáltatáskérelmet használ a beállításához a létesítési folyamat befejeződését követően.</span><span class="sxs-lookup"><span data-stu-id="3c221-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="3c221-109">Az e-kereskedelmi környezet létesítési folyamata egy olyan állomásnevet generál, amely a környezethez van társítva.</span><span class="sxs-lookup"><span data-stu-id="3c221-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="3c221-110">Ez az állomásnév a következő formátummal rendelkezik, ahol az \<*e-commerce-tenant-name*\> az Ön környezetének neve:</span><span class="sxs-lookup"><span data-stu-id="3c221-110">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="3c221-111">&lt;e-kereskedelmi-bérlő-neve&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="3c221-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="3c221-112">A létesítési folyamat során létrejövő állomásnév vagy végpont csak a következőhöz támogat Secure Sockets Layer (SSL) tanúsítvány: \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="3c221-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="3c221-113">Nem támogatja az SSL-t egyéni tartományok esetében.</span><span class="sxs-lookup"><span data-stu-id="3c221-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="3c221-114">Ezért a CDN egyéni tartományainak esetében meg kell szüntetnie az SSL-t, majd továbbítania kell a CDN-ből a forgalmat a Commerce által generált állomásnévre vagy végpontra.</span><span class="sxs-lookup"><span data-stu-id="3c221-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="3c221-115">Ezenkívül a Commerce programból származó *statikák* (JavaScript vagy egymásba ágyazott stíluslap \[CSS\] fájlok) a Commerce által generált végpontból kerülnek kiszolgálásra (\*. commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="3c221-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="3c221-116">A statikák csak akkor gyorsítótárazhatók, ha az a Commerce által generált állomásnév vagy végpont a CDN mögé kerül.</span><span class="sxs-lookup"><span data-stu-id="3c221-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="3c221-117">SSL beállítása</span><span class="sxs-lookup"><span data-stu-id="3c221-117">Set up SSL</span></span>

<span data-ttu-id="3c221-118">Az SSL beállításának és a statikák gyorsítótárazásának biztosításához konfigurálnia kell a CDN-t, hogy az a Commerce által az Ön környezetéhez generált állomásnévhez legyen társítva.</span><span class="sxs-lookup"><span data-stu-id="3c221-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="3c221-119">Csak a statikák esetében a következő mintákat is gyorsítótárazni kell:</span><span class="sxs-lookup"><span data-stu-id="3c221-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="3c221-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="3c221-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="3c221-121">Miután létrehozta a Commerce-környezetet a megadott egyéni tartománnyal, vagy miután egy szolgáltatáskéréssel megadta az egyéni tartományt a környezete számára, irányítsa az egyéni tartományt a Commerce által generált állomásnévre vagy végpontra.</span><span class="sxs-lookup"><span data-stu-id="3c221-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="3c221-122">A korábban említettek szerint a létrehozott állomásnév vagy végpont csak a \*.commerce.dynamics.com esetében támogat SSL-tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="3c221-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="3c221-123">Nem támogatja az SSL-t egyéni tartományok esetében.</span><span class="sxs-lookup"><span data-stu-id="3c221-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="3c221-124">CDN-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="3c221-124">CDN services</span></span>

<span data-ttu-id="3c221-125">A Commerce-környezettel együtt bármely CDN-szolgáltatás használható.</span><span class="sxs-lookup"><span data-stu-id="3c221-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="3c221-126">Íme két példa:</span><span class="sxs-lookup"><span data-stu-id="3c221-126">Here are two examples:</span></span>

- <span data-ttu-id="3c221-127">**Microsoft Azure Front Door Service** – Az Azure CDN-megoldása.</span><span class="sxs-lookup"><span data-stu-id="3c221-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="3c221-128">További tájékoztatás az Azure Front Door Service szolgáltatásról: [Azure Front Door Service dokumentációja](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="3c221-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="3c221-129">**Akamai Dynamic Site Accelerator** – További tudnivalók: [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="3c221-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="3c221-130">CDN beállítása</span><span class="sxs-lookup"><span data-stu-id="3c221-130">CDN setup</span></span>

<span data-ttu-id="3c221-131">A CDN beállítási folyamata az alábbi általános lépésekből áll:</span><span class="sxs-lookup"><span data-stu-id="3c221-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="3c221-132">Adjon hozzá egy előtéri állomást.</span><span class="sxs-lookup"><span data-stu-id="3c221-132">Add a front-end host.</span></span>
1. <span data-ttu-id="3c221-133">Konfiguráljon egy háttérkészletet.</span><span class="sxs-lookup"><span data-stu-id="3c221-133">Configure a backend pool.</span></span>
1. <span data-ttu-id="3c221-134">Állítson be szabályokat az útvonaltervezéshez és gyorsítótárazáshoz.</span><span class="sxs-lookup"><span data-stu-id="3c221-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="3c221-135">Adjon hozzá egy előtéri állomást</span><span class="sxs-lookup"><span data-stu-id="3c221-135">Add a front-end host</span></span>

<span data-ttu-id="3c221-136">Bármely CDN-szolgáltatás használható, de a jelen témakör példájában az Azure Front Door Service kerül felhasználásra.</span><span class="sxs-lookup"><span data-stu-id="3c221-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="3c221-137">Az Azure Front Door Service beállításával kapcsolatos információkat itt talál: [Rövid útmutató: Front Door létrehozása egy magas szintű rendelkezésre állású, globális webes alkalmazáshoz](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="3c221-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="3c221-138">Háttérkészlet konfigurálása az Azure Front Door Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="3c221-138">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="3c221-139">Kövesse az alábbi lépéseket háttérkészlet konfigurálásához az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="3c221-139">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="3c221-140">Adja hozzá az **&lt;ecom-bérlő-neve&gt;.commerce.dynamics.com** elemet egy háttérkészlethez egy egyéni állomásként, amelynek üres a háttérállomás fejléce.</span><span class="sxs-lookup"><span data-stu-id="3c221-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="3c221-141">A **Terheléselosztás** alatt hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="3c221-141">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="3c221-142">A következő ábra a **Háttéralkalmazás hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban a megadott háttéralkalmazás állomásnevét.</span><span class="sxs-lookup"><span data-stu-id="3c221-142">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Háttérkészlet hozzáadása párbeszédpanel](./media/CDN_BackendPool.png)

<span data-ttu-id="3c221-144">A következő ábra a **Háttérkészlet hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban az alapértelmezett terheléselosztási értékeket.</span><span class="sxs-lookup"><span data-stu-id="3c221-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Háttérkészlet párbeszédpanel hozzáadása folytatva](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="3c221-146">Szabályok beállítása az Azure Front Door Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="3c221-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="3c221-147">Ha be szeretne állítani egy útvonaltervezési szabályt az Azure Front Door Service szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3c221-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="3c221-148">Útvonaltervezési szabály hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="3c221-148">Add a routing rule.</span></span>
1. <span data-ttu-id="3c221-149">A **Név** mezőbe írja be az **alapértelmezett** szót.</span><span class="sxs-lookup"><span data-stu-id="3c221-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="3c221-150">Az **Elfogadott protokoll** mezőben válassza a **HTTP és HTTPS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c221-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="3c221-151">Az **Előtéri állomások** mezőbe írja be a **dynamics-ecom-bérlő-neve.azurefd.net** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="3c221-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="3c221-152">Az **Egyeztetendő minták** alatt a felső mezőbe írja be a következőt: **/\***.</span><span class="sxs-lookup"><span data-stu-id="3c221-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="3c221-153">Az **Útvonal részletei** adja meg az **Útvonal típusa** beállítás számára a **Továbbítás** értéket.</span><span class="sxs-lookup"><span data-stu-id="3c221-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="3c221-154">Válassza ki a **Háttérkészlet** mezőben az **ecom-backend** elemet.</span><span class="sxs-lookup"><span data-stu-id="3c221-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="3c221-155">A **Továbbítási protokollok** mezőcsoportban válassza ki az **Egyeztetési kérelem** beállítást.</span><span class="sxs-lookup"><span data-stu-id="3c221-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="3c221-156">Állítsa az **URL újraírása** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="3c221-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="3c221-157">Állítsa a **Gyorsítótárazás** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="3c221-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="3c221-158">Ha be szeretne állítani egy gyorsítótárazási szabályt az Azure Front Door Service szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3c221-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="3c221-159">Gyorsítótárazási szabály hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="3c221-159">Add a caching rule.</span></span>
1. <span data-ttu-id="3c221-160">A **Név** mezőbe írja be a **statikák** szót.</span><span class="sxs-lookup"><span data-stu-id="3c221-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="3c221-161">Az **Elfogadott protokoll** mezőben válassza a **HTTP és HTTPS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c221-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="3c221-162">Az **Előtéri állomások** mezőbe írja be a **dynamics-ecom-bérlő-neve.azurefd.net** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="3c221-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="3c221-163">Az **Egyeztetendő minták** alatt a felső mezőbe írja be a következőt: **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="3c221-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="3c221-164">Az **Útvonal részletei** adja meg az **Útvonal típusa** beállítás számára a **Továbbítás** értéket.</span><span class="sxs-lookup"><span data-stu-id="3c221-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="3c221-165">Válassza ki a **Háttérkészlet** mezőben az **ecom-backend** elemet.</span><span class="sxs-lookup"><span data-stu-id="3c221-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="3c221-166">A **Továbbítási protokollok** mezőcsoportban válassza ki az **Egyeztetési kérelem** beállítást.</span><span class="sxs-lookup"><span data-stu-id="3c221-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="3c221-167">Állítsa az **URL újraírása** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="3c221-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="3c221-168">Állítsa a **Gyorsítótárazás** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="3c221-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="3c221-169">A **Lekérdezési karakterlánc gyorsítótárazási viselkedése** mezőben válassza a **Minden egyedi URL gyorsítótárazása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3c221-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="3c221-170">A **Dinamikus tömörítés** mezőcsoportban válassza az **Engedélyezve** beállítást.</span><span class="sxs-lookup"><span data-stu-id="3c221-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="3c221-171">A következő ábra a **Szabály hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="3c221-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Szabály hozzáadása párbeszédpanel](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="3c221-173">Ha a használni kívánt tartomány már aktív és élő, hozzon létre egy támogatási jegyet az [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) **Támogatás** mozaikján, és kérjen segítséget a következő lépésekhez.</span><span class="sxs-lookup"><span data-stu-id="3c221-173">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="3c221-174">További információért tekintse át a [Támogatás igénylése a Finance and Operations alkalmazásokhoz vagy a Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="3c221-174">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="3c221-175">Ha a tartománya új, és nem egy korábban létező élő tartomány, akkor a saját egyéni tartományát hozzáadhatja az Azure Front Door Service konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="3c221-175">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="3c221-176">Ez lehetővé teszi a webforgalom számára, hogy az Azure Front Door példányon keresztül irányítsa a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="3c221-176">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="3c221-177">Az egyéni tartomány (például `www.fabrikam.com`) hozzáadásához be kell állítania egy kanonikus nevet (CNAME) a tartomány számára.</span><span class="sxs-lookup"><span data-stu-id="3c221-177">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="3c221-178">A következő ábra a **CNAME konfigurálása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="3c221-178">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![CNAME konfiguráció párbeszédpanel](./media/CNAME_Configuration.png)

<span data-ttu-id="3c221-180">A tanúsítványt kezelheti az Azure Front Door Service szolgáltatásával, vagy használhatja az egyéni tartományhoz tartozó saját tanúsítványát.</span><span class="sxs-lookup"><span data-stu-id="3c221-180">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="3c221-181">A következő ábra az **Egyéni tartomány HTTPS** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="3c221-181">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Egyéni tartomány HTTPS párbeszédpanel](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="3c221-183">Az Azure Front Doorhoz való egyéni tartományok hozzáadásával kapcsolatos további információkat lásd az [Egyéni tartomány hozzáadása a Front Doorhoz](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain) menüpontot.</span><span class="sxs-lookup"><span data-stu-id="3c221-183">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="3c221-184">A CDN-nek most már helyesen konfiguráltnak kell lennie, hogy használható legyen a Commerce webhelyével.</span><span class="sxs-lookup"><span data-stu-id="3c221-184">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3c221-185">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3c221-185">Additional resources</span></span>

[<span data-ttu-id="3c221-186">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="3c221-186">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="3c221-187">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="3c221-187">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="3c221-188">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="3c221-188">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="3c221-189">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="3c221-189">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="3c221-190">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="3c221-190">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="3c221-191">URL-átirányítások feltöltése ömlesztett formában</span><span class="sxs-lookup"><span data-stu-id="3c221-191">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="3c221-192">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="3c221-192">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="3c221-193">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="3c221-193">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="3c221-194">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="3c221-194">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="3c221-195">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="3c221-195">Enable location-based store detection</span></span>](enable-store-detection.md)
