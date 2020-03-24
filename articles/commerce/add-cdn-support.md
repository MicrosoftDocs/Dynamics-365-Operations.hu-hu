---
title: Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.
author: brianshook
manager: annbe
ms.date: 03/02/2020
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
ms.openlocfilehash: 23ac9d8844c2a8ae20bd316c40078319601a3a4d
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096725"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="c27e5-103">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c27e5-103">Add support for a content delivery network (CDN)</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c27e5-104">Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.</span><span class="sxs-lookup"><span data-stu-id="c27e5-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="c27e5-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="c27e5-105">Overview</span></span>

<span data-ttu-id="c27e5-106">Ha egy e-kereskedelmi környezetet hoz létre a Dynamics 365 Commerce alkalmazásban, akkor konfigurálhatja úgy, hogy együttműködjön az Ön CDN-szolgáltatásával.</span><span class="sxs-lookup"><span data-stu-id="c27e5-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="c27e5-107">Az Ön egyéni tartománya az e-kereskedelmi környezet létesítési folyamata során engedélyezhető.</span><span class="sxs-lookup"><span data-stu-id="c27e5-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="c27e5-108">Azt is megteheti, hogy egy szolgáltatáskérelmet használ a beállításához a létesítési folyamat befejeződését követően.</span><span class="sxs-lookup"><span data-stu-id="c27e5-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="c27e5-109">Az e-kereskedelmi környezet létesítési folyamata egy olyan állomásnevet generál, amely a környezethez van társítva.</span><span class="sxs-lookup"><span data-stu-id="c27e5-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="c27e5-110">Ez az állomásnév a következő formátummal rendelkezik, ahol az *e-kereskedelmi-bérlő-neve* az Ön környezetének neve:</span><span class="sxs-lookup"><span data-stu-id="c27e5-110">This host name has the following format, where *e-commerce-tenant-name* is the name of your environment:</span></span>

<span data-ttu-id="c27e5-111">&lt;e-kereskedelmi-bérlő-neve&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="c27e5-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="c27e5-112">A létesítési folyamat során létrejövő állomásnév vagy végpont csak a következőhöz támogat Secure Sockets Layer (SSL) tanúsítvány: \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="c27e5-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="c27e5-113">Nem támogatja az SSL-t egyéni tartományok esetében.</span><span class="sxs-lookup"><span data-stu-id="c27e5-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="c27e5-114">Ezért a CDN egyéni tartományainak esetében meg kell szüntetnie az SSL-t, majd továbbítania kell a CDN-ből a forgalmat a Commerce által generált állomásnévre vagy végpontra.</span><span class="sxs-lookup"><span data-stu-id="c27e5-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="c27e5-115">Ezenkívül a Commerce programból származó *statikák* (JavaScript vagy egymásba ágyazott stíluslap \[CSS\] fájlok) a Commerce által generált végpontból kerülnek kiszolgálásra (\*. commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="c27e5-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="c27e5-116">A statikák csak akkor gyorsítótárazhatók, ha az a Commerce által generált állomásnév vagy végpont a CDN mögé kerül.</span><span class="sxs-lookup"><span data-stu-id="c27e5-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="c27e5-117">SSL beállítása</span><span class="sxs-lookup"><span data-stu-id="c27e5-117">Set up SSL</span></span>

<span data-ttu-id="c27e5-118">Az SSL beállításának és a statikák gyorsítótárazásának biztosításához konfigurálnia kell a CDN-t, hogy az a Commerce által az Ön környezetéhez generált állomásnévhez legyen társítva.</span><span class="sxs-lookup"><span data-stu-id="c27e5-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="c27e5-119">Csak a statikák esetében a következő mintákat is gyorsítótárazni kell:</span><span class="sxs-lookup"><span data-stu-id="c27e5-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="c27e5-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="c27e5-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="c27e5-121">Miután létrehozta a Commerce-környezetet a megadott egyéni tartománnyal, vagy miután egy szolgáltatáskéréssel megadta az egyéni tartományt a környezete számára, irányítsa az egyéni tartományt a Commerce által generált állomásnévre vagy végpontra.</span><span class="sxs-lookup"><span data-stu-id="c27e5-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="c27e5-122">A korábban említettek szerint a létrehozott állomásnév vagy végpont csak a \*.commerce.dynamics.com esetében támogat SSL-tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="c27e5-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="c27e5-123">Nem támogatja az SSL-t egyéni tartományok esetében.</span><span class="sxs-lookup"><span data-stu-id="c27e5-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="c27e5-124">CDN-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="c27e5-124">CDN services</span></span>

<span data-ttu-id="c27e5-125">A Commerce-környezettel együtt bármely CDN-szolgáltatás használható.</span><span class="sxs-lookup"><span data-stu-id="c27e5-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="c27e5-126">Íme két példa:</span><span class="sxs-lookup"><span data-stu-id="c27e5-126">Here are two examples:</span></span>

- <span data-ttu-id="c27e5-127">**Microsoft Azure Front Door Service** – Az Azure CDN-megoldása.</span><span class="sxs-lookup"><span data-stu-id="c27e5-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="c27e5-128">További tájékoztatás az Azure Front Door Service szolgáltatásról: [Azure Front Door Service dokumentációja](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="c27e5-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="c27e5-129">**Akamai Dynamic Site Accelerator** – További tudnivalók: [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="c27e5-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="c27e5-130">CDN beállítása</span><span class="sxs-lookup"><span data-stu-id="c27e5-130">CDN setup</span></span>

<span data-ttu-id="c27e5-131">A CDN beállítási folyamata az alábbi általános lépésekből áll:</span><span class="sxs-lookup"><span data-stu-id="c27e5-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="c27e5-132">Adjon hozzá egy előtéri állomást.</span><span class="sxs-lookup"><span data-stu-id="c27e5-132">Add a front-end host.</span></span>
1. <span data-ttu-id="c27e5-133">Konfiguráljon egy háttérkészletet.</span><span class="sxs-lookup"><span data-stu-id="c27e5-133">Configure a back-end pool.</span></span>
1. <span data-ttu-id="c27e5-134">Állítson be szabályokat az útvonaltervezéshez és gyorsítótárazáshoz.</span><span class="sxs-lookup"><span data-stu-id="c27e5-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="c27e5-135">Adjon hozzá egy előtéri állomást</span><span class="sxs-lookup"><span data-stu-id="c27e5-135">Add a front-end host</span></span>

<span data-ttu-id="c27e5-136">Bármely CDN-szolgáltatás használható, de a jelen témakör példájában az Azure Front Door Service kerül felhasználásra.</span><span class="sxs-lookup"><span data-stu-id="c27e5-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="c27e5-137">Az Azure Front Door Service beállításával kapcsolatos információkat itt talál: [Rövid útmutató: Front Door létrehozása egy magas szintű rendelkezésre állású, globális webes alkalmazáshoz](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="c27e5-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a><span data-ttu-id="c27e5-138">Háttérkészlet konfigurálása az Azure Front Door Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="c27e5-138">Configure a back-end pool in Azure Front Door Service</span></span>

<span data-ttu-id="c27e5-139">Kövesse az alábbi lépéseket háttérkészlet konfigurálásához az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="c27e5-139">To configure a back-end pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="c27e5-140">Adja hozzá az **&lt;ecom-bérlő-neve&gt;.commerce.dynamics.com** elemet egy háttérkészlethez egy egyéni állomásként, amelynek üres a háttérállomás fejléce.</span><span class="sxs-lookup"><span data-stu-id="c27e5-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a back-end pool as a custom host that has an empty back-end host header.</span></span>
1. <span data-ttu-id="c27e5-141">Az **Állapotminták** alatt, az **Útvonal** mezőbe írja be a **/keepalive** értéket.</span><span class="sxs-lookup"><span data-stu-id="c27e5-141">Under **Health probes**, in the **Path** field, enter **/keepalive**.</span></span>
1. <span data-ttu-id="c27e5-142">Az **Intervallumok (másodperc)** mezőbe írja be a **255** értéket.</span><span class="sxs-lookup"><span data-stu-id="c27e5-142">In the **Intervals (seconds)** field, enter **255**.</span></span>
1. <span data-ttu-id="c27e5-143">A **Terheléselosztás** alatt hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="c27e5-143">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="c27e5-144">A következő ábra a **Háttérkészlet hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="c27e5-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service.</span></span>

![Háttérkészlet hozzáadása párbeszédpanel](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="c27e5-146">Szabályok beállítása az Azure Front Door Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="c27e5-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="c27e5-147">Ha be szeretne állítani egy útvonaltervezési szabályt az Azure Front Door Service szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c27e5-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="c27e5-148">Útvonaltervezési szabály hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="c27e5-148">Add a routing rule.</span></span>
1. <span data-ttu-id="c27e5-149">A **Név** mezőbe írja be az **alapértelmezett** szót.</span><span class="sxs-lookup"><span data-stu-id="c27e5-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="c27e5-150">Az **Elfogadott protokoll** mezőben válassza a **HTTP és HTTPS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c27e5-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="c27e5-151">Az **Előtéri állomások** mezőbe írja be a **dynamics-ecom-bérlő-neve.azurefd.net** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="c27e5-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="c27e5-152">Az **Egyeztetendő minták** alatt a felső mezőbe írja be a következőt: **/\***.</span><span class="sxs-lookup"><span data-stu-id="c27e5-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="c27e5-153">Az **Útvonal részletei** adja meg az **Útvonal típusa** beállítás számára a **Továbbítás** értéket.</span><span class="sxs-lookup"><span data-stu-id="c27e5-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="c27e5-154">Válassza ki a **Háttérkészlet** mezőben az **ecom-backend** elemet.</span><span class="sxs-lookup"><span data-stu-id="c27e5-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="c27e5-155">A **Továbbítási protokollok** mezőcsoportban válassza ki az **Egyeztetési kérelem** beállítást.</span><span class="sxs-lookup"><span data-stu-id="c27e5-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="c27e5-156">Állítsa az **URL újraírása** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="c27e5-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="c27e5-157">Állítsa a **Gyorsítótárazás** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="c27e5-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="c27e5-158">Ha be szeretne állítani egy gyorsítótárazási szabályt az Azure Front Door Service szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c27e5-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="c27e5-159">Gyorsítótárazási szabály hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="c27e5-159">Add a caching rule.</span></span>
1. <span data-ttu-id="c27e5-160">A **Név** mezőbe írja be a **statikák** szót.</span><span class="sxs-lookup"><span data-stu-id="c27e5-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="c27e5-161">Az **Elfogadott protokoll** mezőben válassza a **HTTP és HTTPS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c27e5-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="c27e5-162">Az **Előtéri állomások** mezőbe írja be a **dynamics-ecom-bérlő-neve.azurefd.net** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="c27e5-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="c27e5-163">Az **Egyeztetendő minták** alatt a felső mezőbe írja be a következőt: **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="c27e5-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="c27e5-164">Az **Útvonal részletei** adja meg az **Útvonal típusa** beállítás számára a **Továbbítás** értéket.</span><span class="sxs-lookup"><span data-stu-id="c27e5-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="c27e5-165">Válassza ki a **Háttérkészlet** mezőben az **ecom-backend** elemet.</span><span class="sxs-lookup"><span data-stu-id="c27e5-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="c27e5-166">A **Továbbítási protokollok** mezőcsoportban válassza ki az **Egyeztetési kérelem** beállítást.</span><span class="sxs-lookup"><span data-stu-id="c27e5-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="c27e5-167">Állítsa az **URL újraírása** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="c27e5-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="c27e5-168">Állítsa a **Gyorsítótárazás** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="c27e5-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="c27e5-169">A **Lekérdezési karakterlánc gyorsítótárazási viselkedése** mezőben válassza a **Minden egyedi URL gyorsítótárazása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c27e5-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="c27e5-170">A **Dinamikus tömörítés** mezőcsoportban válassza az **Engedélyezve** beállítást.</span><span class="sxs-lookup"><span data-stu-id="c27e5-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="c27e5-171">A következő ábra a **Szabály hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="c27e5-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Szabály hozzáadása párbeszédpanel](./media/CDN_CachingRule.png)

<span data-ttu-id="c27e5-173">A kezdeti konfiguráció telepítését követően a saját tartományt fel kell vennie az Azure Front Door Service konfigurációjába.</span><span class="sxs-lookup"><span data-stu-id="c27e5-173">After this initial configuration is deployed, you must add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="c27e5-174">Az egyéni tartomány (például `www.fabrikam.com`) hozzáadásához be kell állítania egy kanonikus nevet (CNAME) a tartomány számára.</span><span class="sxs-lookup"><span data-stu-id="c27e5-174">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="c27e5-175">A következő ábra a **CNAME konfigurálása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="c27e5-175">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![CNAME konfiguráció párbeszédpanel](./media/CNAME_Configuration.png)

> [!NOTE]
> <span data-ttu-id="c27e5-177">Ha a használni kívánt tartomány már aktív és élő, forduljon a támogatáshoz, hogy a tartományt az Azure Front Door Service szolgáltatással engedélyezve tesztet hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="c27e5-177">If the domain that you will use is already active and live, contact support to enable this domain with Azure Front Door Service to set up a test.</span></span>

<span data-ttu-id="c27e5-178">A tanúsítványt kezelheti az Azure Front Door Service szolgáltatásával, vagy használhatja az egyéni tartományhoz tartozó saját tanúsítványát.</span><span class="sxs-lookup"><span data-stu-id="c27e5-178">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="c27e5-179">A következő ábra az **Egyéni tartomány HTTPS** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="c27e5-179">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Egyéni tartomány HTTPS párbeszédpanel](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="c27e5-181">A CDN-nek most már helyesen konfiguráltnak kell lennie, hogy használható legyen a Commerce webhelyével.</span><span class="sxs-lookup"><span data-stu-id="c27e5-181">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c27e5-182">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c27e5-182">Additional resources</span></span>

[<span data-ttu-id="c27e5-183">A tartománynevének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c27e5-183">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="c27e5-184">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="c27e5-184">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="c27e5-185">Online áruház csatornájának beállítása</span><span class="sxs-lookup"><span data-stu-id="c27e5-185">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="c27e5-186">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="c27e5-186">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="c27e5-187">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="c27e5-187">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="c27e5-188">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="c27e5-188">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="c27e5-189">URL-átirányítások feltöltése ömlesztett formában</span><span class="sxs-lookup"><span data-stu-id="c27e5-189">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="c27e5-190">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="c27e5-190">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="c27e5-191">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="c27e5-191">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="c27e5-192">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="c27e5-192">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="c27e5-193">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c27e5-193">Enable location-based store detection</span></span>](enable-store-detection.md)
