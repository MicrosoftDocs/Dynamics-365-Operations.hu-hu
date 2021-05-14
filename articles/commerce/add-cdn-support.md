---
title: Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása
description: Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 59277323e0995f59d3a451395a038fa3708274eb
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936830"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="eb885-103">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="eb885-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="eb885-104">Ez a témakör azt mutatja be, hogyan lehet hozzáadni tartalomkézbesítési hálózatot (CDN) a Microsoft Dynamics 365 Commerce-környezetéhez.</span><span class="sxs-lookup"><span data-stu-id="eb885-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="eb885-105">Ha egy e-kereskedelmi környezetet hoz létre a Dynamics 365 Commerce alkalmazásban, akkor konfigurálhatja úgy, hogy együttműködjön az Ön CDN-szolgáltatásával.</span><span class="sxs-lookup"><span data-stu-id="eb885-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="eb885-106">Az Ön egyéni tartománya az e-kereskedelmi környezet létesítési folyamata során engedélyezhető.</span><span class="sxs-lookup"><span data-stu-id="eb885-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="eb885-107">Azt is megteheti, hogy egy szolgáltatáskérelmet használ a beállításához a létesítési folyamat befejeződését követően.</span><span class="sxs-lookup"><span data-stu-id="eb885-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="eb885-108">Az e-kereskedelmi környezet létesítési folyamata egy olyan állomásnevet generál, amely a környezethez van társítva.</span><span class="sxs-lookup"><span data-stu-id="eb885-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="eb885-109">Ez az állomásnév a következő formátummal rendelkezik, ahol az \<*e-commerce-tenant-name*\> az Ön környezetének neve:</span><span class="sxs-lookup"><span data-stu-id="eb885-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="eb885-110">&lt;e-kereskedelmi-bérlő-neve&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="eb885-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="eb885-111">A létesítési folyamat során létrejövő állomásnév vagy végpont csak a következőhöz támogat Secure Sockets Layer (SSL) tanúsítvány: \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="eb885-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="eb885-112">Nem támogatja az SSL-t egyéni tartományok esetében.</span><span class="sxs-lookup"><span data-stu-id="eb885-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="eb885-113">Ezért a CDN egyéni tartományainak esetében meg kell szüntetnie az SSL-t, majd továbbítania kell a CDN-ből a forgalmat a Commerce által generált állomásnévre vagy végpontra.</span><span class="sxs-lookup"><span data-stu-id="eb885-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="eb885-114">Ezenkívül a Commerce programból származó *statikák* (JavaScript vagy egymásba ágyazott stíluslap \[CSS\] fájlok) a Commerce által generált végpontból kerülnek kiszolgálásra (\*. commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="eb885-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="eb885-115">A statikák csak akkor gyorsítótárazhatók, ha az a Commerce által generált állomásnév vagy végpont a CDN mögé kerül.</span><span class="sxs-lookup"><span data-stu-id="eb885-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="eb885-116">SSL beállítása</span><span class="sxs-lookup"><span data-stu-id="eb885-116">Set up SSL</span></span>

<span data-ttu-id="eb885-117">Miután létrehozta a Commerce-környezetet a megadott egyéni tartománnyal, vagy miután egy szolgáltatáskéréssel megadta az egyéni tartományt a környezete számára, a Commerce előkészítési csapatával együttműködve meg kell terveznie a DNS változásait.</span><span class="sxs-lookup"><span data-stu-id="eb885-117">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, you need to work with the Commerce onboarding team to plan the DNS changes.</span></span>

<span data-ttu-id="eb885-118">A korábban említettek szerint a létrehozott állomásnév vagy végpont csak a \*.commerce.dynamics.com esetében támogat SSL-tanúsítványt.</span><span class="sxs-lookup"><span data-stu-id="eb885-118">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="eb885-119">Nem támogatja az SSL-t egyéni tartományok esetében.</span><span class="sxs-lookup"><span data-stu-id="eb885-119">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="eb885-120">CDN-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="eb885-120">CDN services</span></span>

<span data-ttu-id="eb885-121">A Commerce-környezettel együtt bármely CDN-szolgáltatás használható.</span><span class="sxs-lookup"><span data-stu-id="eb885-121">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="eb885-122">Íme két példa:</span><span class="sxs-lookup"><span data-stu-id="eb885-122">Here are two examples:</span></span>

- <span data-ttu-id="eb885-123">**Microsoft Azure Front Door Service** – Az Azure CDN-megoldása.</span><span class="sxs-lookup"><span data-stu-id="eb885-123">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="eb885-124">További tájékoztatás az Azure Front Door Service szolgáltatásról: [Azure Front Door Service dokumentációja](/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="eb885-124">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](/azure/frontdoor/).</span></span>
- <span data-ttu-id="eb885-125">**Akamai Dynamic Site Accelerator** – További tudnivalók: [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="eb885-125">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="eb885-126">CDN beállítása</span><span class="sxs-lookup"><span data-stu-id="eb885-126">CDN setup</span></span>

<span data-ttu-id="eb885-127">A CDN beállítási folyamata az alábbi általános lépésekből áll:</span><span class="sxs-lookup"><span data-stu-id="eb885-127">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="eb885-128">Adjon hozzá egy előtéri állomást.</span><span class="sxs-lookup"><span data-stu-id="eb885-128">Add a front-end host.</span></span>
1. <span data-ttu-id="eb885-129">Konfiguráljon egy háttérkészletet.</span><span class="sxs-lookup"><span data-stu-id="eb885-129">Configure a backend pool.</span></span>
1. <span data-ttu-id="eb885-130">Állítsa be az útvonaltervezés szabályait.</span><span class="sxs-lookup"><span data-stu-id="eb885-130">Set up rules for routing.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="eb885-131">Adjon hozzá egy előtéri állomást</span><span class="sxs-lookup"><span data-stu-id="eb885-131">Add a front-end host</span></span>

<span data-ttu-id="eb885-132">Bármely CDN-szolgáltatás használható, de a jelen témakör példájában az Azure Front Door Service kerül felhasználásra.</span><span class="sxs-lookup"><span data-stu-id="eb885-132">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="eb885-133">Az Azure Front Door Service beállításával kapcsolatos információkat itt talál: [Rövid útmutató: Front Door létrehozása egy magas szintű rendelkezésre állású, globális webes alkalmazáshoz](/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="eb885-133">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="eb885-134">Háttérkészlet konfigurálása az Azure Front Door Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="eb885-134">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="eb885-135">Kövesse az alábbi lépéseket háttérkészlet konfigurálásához az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="eb885-135">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="eb885-136">Adja hozzá az **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** elemet egy háttérkészlethez egyéni állomásként, amelynek a háttérállomás fejléce ugyanaz, az **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** esetében.</span><span class="sxs-lookup"><span data-stu-id="eb885-136">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has a backend host header that is the same as **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span></span>
1. <span data-ttu-id="eb885-137">A **Terheléselosztás** alatt hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="eb885-137">Under **Load balancing**, leave the default values.</span></span>
1. <span data-ttu-id="eb885-138">Tiltsa le a háttérkészlet állapotellenőrzését.</span><span class="sxs-lookup"><span data-stu-id="eb885-138">Disable health checks for the backend pool.</span></span>

<span data-ttu-id="eb885-139">A következő ábra a **Háttéralkalmazás hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban a megadott háttéralkalmazás állomásnevét.</span><span class="sxs-lookup"><span data-stu-id="eb885-139">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Háttérkészlet hozzáadása párbeszédpanel](./media/CDN_BackendPool.png)

<span data-ttu-id="eb885-141">A következő ábra a **Háttérkészlet hozzáadása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban az alapértelmezett terheléselosztási értékeket.</span><span class="sxs-lookup"><span data-stu-id="eb885-141">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Háttérkészlet párbeszédpanel hozzáadása folytatva](./media/CDN_BackendPool_2.png)

> [!NOTE]
> <span data-ttu-id="eb885-143">Győződjön meg róla, hogy letiltja az **Állapotellenőrzések** funkciót a saját Azure Front Door Service beállításakor a Commerce számára.</span><span class="sxs-lookup"><span data-stu-id="eb885-143">Be sure to disable **Health Probes** when setting up your own Azure Front Door service for Commerce.</span></span>


### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="eb885-144">Szabályok beállítása az Azure Front Door Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="eb885-144">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="eb885-145">Ha be szeretne állítani egy útvonaltervezési szabályt az Azure Front Door Service szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="eb885-145">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="eb885-146">Útvonaltervezési szabály hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="eb885-146">Add a routing rule.</span></span>
1. <span data-ttu-id="eb885-147">A **Név** mezőbe írja be az **alapértelmezett** szót.</span><span class="sxs-lookup"><span data-stu-id="eb885-147">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="eb885-148">Az **Elfogadott protokoll** mezőben válassza a **HTTP és HTTPS** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="eb885-148">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="eb885-149">Az **Előtéri állomások** mezőbe írja be a **dynamics-ecom-bérlő-neve.azurefd.net** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="eb885-149">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="eb885-150">Az **Egyeztetendő minták** alatt a felső mezőbe írja be a következőt: **/\***.</span><span class="sxs-lookup"><span data-stu-id="eb885-150">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="eb885-151">Az **Útvonal részletei** adja meg az **Útvonal típusa** beállítás számára a **Továbbítás** értéket.</span><span class="sxs-lookup"><span data-stu-id="eb885-151">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="eb885-152">Válassza ki a **Háttérkészlet** mezőben az **ecom-backend** elemet.</span><span class="sxs-lookup"><span data-stu-id="eb885-152">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="eb885-153">A **Továbbítási protokollok** mezőcsoportban válassza ki az **Egyeztetési kérelem** beállítást.</span><span class="sxs-lookup"><span data-stu-id="eb885-153">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="eb885-154">Állítsa az **URL újraírása** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="eb885-154">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="eb885-155">Állítsa a **Gyorsítótárazás** beállítást **Letiltva** értékre.</span><span class="sxs-lookup"><span data-stu-id="eb885-155">Set the **Caching** option to **Disabled**.</span></span>


> [!WARNING]
> <span data-ttu-id="eb885-156">Ha a használni kívánt tartomány már aktív és élő, hozzon létre egy támogatási jegyet az [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) **Támogatás** mozaikján, és kérjen segítséget a következő lépésekhez.</span><span class="sxs-lookup"><span data-stu-id="eb885-156">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="eb885-157">További információért tekintse át a [Támogatás igénylése a Finance and Operations alkalmazásokhoz vagy a Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="eb885-157">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="eb885-158">Ha a tartománya új, és nem egy korábban létező élő tartomány, akkor a saját egyéni tartományát hozzáadhatja az Azure Front Door Service konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="eb885-158">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="eb885-159">Ez lehetővé teszi a webforgalom számára, hogy az Azure Front Door példányon keresztül irányítsa a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="eb885-159">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="eb885-160">Az egyéni tartomány (például `www.fabrikam.com`) hozzáadásához be kell állítania egy kanonikus nevet (CNAME) a tartomány számára.</span><span class="sxs-lookup"><span data-stu-id="eb885-160">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="eb885-161">A következő ábra a **CNAME konfigurálása** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="eb885-161">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![CNAME konfiguráció párbeszédpanel](./media/CNAME_Configuration.png)

<span data-ttu-id="eb885-163">A tanúsítványt kezelheti az Azure Front Door Service szolgáltatásával, vagy használhatja az egyéni tartományhoz tartozó saját tanúsítványát.</span><span class="sxs-lookup"><span data-stu-id="eb885-163">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="eb885-164">A következő ábra az **Egyéni tartomány HTTPS** párbeszédpanelt mutatja az Azure Front Door Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="eb885-164">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Egyéni tartomány HTTPS párbeszédpanel](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="eb885-166">Az Azure Front Doorhoz való egyéni tartományok hozzáadásával kapcsolatos további információkat lásd az [Egyéni tartomány hozzáadása a Front Doorhoz](/azure/frontdoor/front-door-custom-domain) menüpontot.</span><span class="sxs-lookup"><span data-stu-id="eb885-166">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="eb885-167">A CDN-nek most már helyesen konfiguráltnak kell lennie, hogy használható legyen a Commerce webhelyével.</span><span class="sxs-lookup"><span data-stu-id="eb885-167">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eb885-168">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="eb885-168">Additional resources</span></span>

[<span data-ttu-id="eb885-169">Tartalomkézbesítési hálózat végrehajtási beállításai</span><span class="sxs-lookup"><span data-stu-id="eb885-169">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]