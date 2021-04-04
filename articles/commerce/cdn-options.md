---
title: Tartalomkézbesítési hálózat végrehajtási beállításai
description: Ez a témakör a tartalomkézbesítési hálózat (CDN) végrehajtásának különböző, Microsoft Dynamics 365 Commerce-környezetekben használható beállításait vizsgálja meg. Ilyen lehetőségek például az Azure Front Door és a vevő által birtokolt Azure Front Door natív, Commerce rendszerbeli példányai.
author: BrianShook
manager: AnnBe
ms.date: 03/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ae0769b7e19f80244186c51454444c499c5e497f
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582803"
---
# <a name="content-delivery-network-implementation-options"></a><span data-ttu-id="1168d-104">Tartalomkézbesítési hálózat végrehajtási beállításai</span><span class="sxs-lookup"><span data-stu-id="1168d-104">Content delivery network implementation options</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1168d-105">Ez a témakör a tartalomkézbesítési hálózat (CDN) végrehajtásának különböző, Microsoft Dynamics 365 Commerce-környezetekben használható beállításait vizsgálja meg.</span><span class="sxs-lookup"><span data-stu-id="1168d-105">This topic reviews the different options for content delivery network (CDN) implementation that can be used with Microsoft Dynamics 365 Commerce environments.</span></span> <span data-ttu-id="1168d-106">Ilyen lehetőségek például az Azure Front Door és a vevő által birtokolt Azure Front Door natív, Commerce rendszerbeli példányai.</span><span class="sxs-lookup"><span data-stu-id="1168d-106">These options include native, Commerce-provided instances of Azure Front Door and customer-owned instances of Azure Front Door.</span></span>

<span data-ttu-id="1168d-107">A Commerce-vevőknek számos lehetőségük van, amikor a CDN-szolgáltatás Commerce-környezetben történő használatát fontolgatják.</span><span class="sxs-lookup"><span data-stu-id="1168d-107">Commerce customers have several options when they are considering which CDN service to use with their Commerce environment.</span></span> <span data-ttu-id="1168d-108">A Commerce rendszer alapvető Azure Front Door támogatással jelenik meg, amely alapvető tárhely- és egyéni tartománykövetelményeket fed le.</span><span class="sxs-lookup"><span data-stu-id="1168d-108">Commerce is released with basic Azure Front Door support that covers basic hosting and custom domain requirements.</span></span> <span data-ttu-id="1168d-109">Olyan vállalatok esetén, amelyek nagyobb ellenőrzést és konkrétabb biztonsági képességeket, például webalkalmazási tűzfalat (WAF) szeretnének, a legjobb lehetőség az Azure Front Door vevő által birtokolt példánya vagy külső CDN-szolgáltatás használata.</span><span class="sxs-lookup"><span data-stu-id="1168d-109">For companies that want more control and more specific security abilities, such as a web application firewall (WAF), the best option might be to use either a customer-owned instance of Azure Front Door or an external CDN service.</span></span>

<span data-ttu-id="1168d-110">A Commerce-környezetekben a következő három CDN-végrehajtási beállítás használható:</span><span class="sxs-lookup"><span data-stu-id="1168d-110">The following three CDN implementation options can be used with Commerce environments:</span></span>

- <span data-ttu-id="1168d-111">A Commerce által biztosított Azure Front Door-példány</span><span class="sxs-lookup"><span data-stu-id="1168d-111">The Commerce-provided instance of Azure Front Door</span></span>
- <span data-ttu-id="1168d-112">Az Azure Front Door vevő által birtokolt példánya (a jobb ellenőrzési és további biztonsági funkciók érdekében)</span><span class="sxs-lookup"><span data-stu-id="1168d-112">A customer-owned instance of Azure Front Door (for increased control and additional security features)</span></span>
- <span data-ttu-id="1168d-113">Külső CDN-szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="1168d-113">An external CDN service</span></span>

<span data-ttu-id="1168d-114">Mind a három CDN-bégrehajtási beállítás csak dinamikus HTML-tartalmat nyújt egyéni tartományokból.</span><span class="sxs-lookup"><span data-stu-id="1168d-114">All three CDN implementation options deliver only dynamic HTML content from custom domains.</span></span> <span data-ttu-id="1168d-115">A Commerce-rendszer automatikusan kezeli az összes JavaScript-, egymásra épülő stílusalap- (CSS), kép-, video- és egyéb statikus tartalmat a Microsoft által kezelt CDN-ek segítségével.</span><span class="sxs-lookup"><span data-stu-id="1168d-115">Commerce automatically handles all JavaScript, Cascading Style Sheets (CSS), images, video, and other static content through Microsoft-managed CDNs.</span></span> <span data-ttu-id="1168d-116">A kiválasztott lehetőség határozza meg az elérhető üzemeltetési lehetőségeket, az ellenőrzési lehetőségeket és további biztonsági lehetőségeket.</span><span class="sxs-lookup"><span data-stu-id="1168d-116">The option that you choose determines the operational capabilities, control capabilities, and additional security capabilities that are available.</span></span>

<span data-ttu-id="1168d-117">A következő ábrán látható a Commerce architektúrája.</span><span class="sxs-lookup"><span data-stu-id="1168d-117">The following illustration shows an overview of the Commerce architecture.</span></span>

![A Commerce architektúrájának áttekintése](media/Commerce_CDN-Option_ComparisonModels.png)

<span data-ttu-id="1168d-119">Az Azure Front Door-példányának Commerce rendszerbeli beállításával kapcsolatban lásd: [CDN-támogatás hozzáadása](add-cdn-support.md).</span><span class="sxs-lookup"><span data-stu-id="1168d-119">For more information about how to set up an instance of Azure Front Door for your Commerce site, see [Add CDN Support](add-cdn-support.md).</span></span>

## <a name="use-the-commerce-provided-azure-front-door-instance"></a><span data-ttu-id="1168d-120">A Commerce által biztosított Azure Front Door-példány használata</span><span class="sxs-lookup"><span data-stu-id="1168d-120">Use the Commerce-provided Azure Front Door instance</span></span>

<span data-ttu-id="1168d-121">Az alábbi táblázat felsorolja a Commerce által a tartalomvégpontok kezelésére biztosított Azure Front Door-példány előnyeit és hátrányait.</span><span class="sxs-lookup"><span data-stu-id="1168d-121">The following table lists the pros and cons of using the Commerce-provided instance of Azure Front Door to manage content endpoints.</span></span>

| <span data-ttu-id="1168d-122">Előnyök</span><span class="sxs-lookup"><span data-stu-id="1168d-122">Pros</span></span> | <span data-ttu-id="1168d-123">Hátrányok</span><span class="sxs-lookup"><span data-stu-id="1168d-123">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="1168d-124">A példány szerepel a Commerce költségeiben.</span><span class="sxs-lookup"><span data-stu-id="1168d-124">The instance is included in the Commerce cost.</span></span></li><li><span data-ttu-id="1168d-125">Mivel a példányt a Commerce csapata kezeli, kevesebb karbantartás szükséges, és megosztott beállítási lépések vannak.</span><span class="sxs-lookup"><span data-stu-id="1168d-125">Because the instance is managed by the Commerce team, less maintenance is required, and there are shared setup steps.</span></span></li><li><span data-ttu-id="1168d-126">Az Azure-környezetben tárolt infrastruktúra méretezhető, biztonságos és megbízható.</span><span class="sxs-lookup"><span data-stu-id="1168d-126">The Azure-hosted infrastructure is scalable, secure, and reliable.</span></span></li><li><span data-ttu-id="1168d-127">Az SSL-tanúsítványt egyszer kell beállítani, utána automatikusan megújul.</span><span class="sxs-lookup"><span data-stu-id="1168d-127">The Secure Sockets Layer (SSL) certificate requires a one-time setup and is automatically renewed.</span></span></li><li><span data-ttu-id="1168d-128">A Commerce csapata figyeli a példányt, hogy vannak-e hibák és anomáliák.</span><span class="sxs-lookup"><span data-stu-id="1168d-128">The instance is monitored for errors and anomalies by the Commerce team.</span></span></li></ul> | <ul><li><span data-ttu-id="1168d-129">A WAF nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="1168d-129">A WAF isn't supported.</span></span></li><li><span data-ttu-id="1168d-130">Nincsenek egyedi testreszabások és beállítási módosítások.</span><span class="sxs-lookup"><span data-stu-id="1168d-130">There are no specific customizations or setting adjustments.</span></span></li><li><span data-ttu-id="1168d-131">A példány frissítései vagy módosításai Commerce csapatától függnek.</span><span class="sxs-lookup"><span data-stu-id="1168d-131">The instance depends on the Commerce team for updates or changes.</span></span></li><li><span data-ttu-id="1168d-132">Az apex-tartományokhoz külön Azure Front Door-példány szükséges, és további munka szükséges az apex-tartományok és az Azure DNS integrálásához.</span><span class="sxs-lookup"><span data-stu-id="1168d-132">A separate Azure Front Door instance is required for apex domains, and extra work is required to integrate apex domains with Azure DNS.</span></span></li><li><span data-ttu-id="1168d-133">A másodpercenkénti válaszokról (RPS) vagy a hibaarányról nem biztosítanak telemetriai adatokat a vevőnek.</span><span class="sxs-lookup"><span data-stu-id="1168d-133">No telemetry about responses per second (RPS) or the error rate is provided to the customer.</span></span></li></ul> |

<span data-ttu-id="1168d-134">Az alábbi ábra a Commerce-rendszer által biztosított Azure Front Door-példány architektúráját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="1168d-134">The following illustration shows the architecture of the Commerce-provided Azure Front Door instance.</span></span>

![A Commerce által biztosított Azure Front Door-példány](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a><span data-ttu-id="1168d-136">Vevő által birtokolt Azure Front Door példány használata</span><span class="sxs-lookup"><span data-stu-id="1168d-136">Use a customer-owned Azure Front Door instance</span></span>

<span data-ttu-id="1168d-137">Az alábbi táblázat felsorolja a vevő által birtokolt, a tartalomvégpontok kezelésére biztosított Azure Front Door-példány előnyeit és hátrányait.</span><span class="sxs-lookup"><span data-stu-id="1168d-137">The following table lists the pros and cons of using a customer-owned instance of Azure Front Door to manage content endpoints.</span></span>

| <span data-ttu-id="1168d-138">Előnyök</span><span class="sxs-lookup"><span data-stu-id="1168d-138">Pros</span></span> | <span data-ttu-id="1168d-139">Hátrányok</span><span class="sxs-lookup"><span data-stu-id="1168d-139">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="1168d-140">A telepítés biztonságos és könnyen kezelhető.</span><span class="sxs-lookup"><span data-stu-id="1168d-140">Setup is secure and easy to manage.</span></span></li><li><span data-ttu-id="1168d-141">Az Azure-környezetben tárolt infrastruktúra méretezhető, biztonságos és megbízható.</span><span class="sxs-lookup"><span data-stu-id="1168d-141">The Azure-hosted infrastructure is scalable, secure, and reliable.</span></span></li><li><span data-ttu-id="1168d-142">A példány lehetővé teszi a WAF-integrációt és a részletességi szabályvezérlőket a kifejezetten az ön webhelyére finomhangolt biztonsághoz.</span><span class="sxs-lookup"><span data-stu-id="1168d-142">The instance allows for WAF integration and granular rule controls for finer-grade security that is tuned specifically for your site.</span></span></li><li><span data-ttu-id="1168d-143">A példány lehetővé teszi az SSL-tanúsítványok finomhangolását (a vevő által birtokolt és az Azure Front Door által kezelt esetében egyaránt) és a tartomány-összekapcsolásokat.</span><span class="sxs-lookup"><span data-stu-id="1168d-143">The instance allows for finer control of SSL certificates (both customer-owned and Azure Front Door–managed) and domain linking.</span></span></li><li><span data-ttu-id="1168d-144">A példány apex-tartományokkal kapcsolatos megoldást kínál, ha közvetlenül párosítva van az Azure DNS-sel.</span><span class="sxs-lookup"><span data-stu-id="1168d-144">The instance offers an apex domain solution if it's paired directly with Azure DNS.</span></span></li><li><span data-ttu-id="1168d-145">A rendszer telemetriai adatokat és riasztást biztosít.</span><span class="sxs-lookup"><span data-stu-id="1168d-145">Telemetry and alerting are provided.</span></span></li><li><span data-ttu-id="1168d-146">Az SSL-tanúsítványt egyszer kell beállítani, utána automatikusan megújul.</span><span class="sxs-lookup"><span data-stu-id="1168d-146">The SSL certificate requires a one-time setup and is automatically renewed.</span></span></li></ul> | <ul><li><span data-ttu-id="1168d-147">A példányt Ön kezeli.</span><span class="sxs-lookup"><span data-stu-id="1168d-147">The instance is self-managed.</span></span></li><li><span data-ttu-id="1168d-148">Ehhez kezdeti tudásra is szükség van.</span><span class="sxs-lookup"><span data-stu-id="1168d-148">Initial knowledge ramp-up is required.</span></span></li></ul> |

<span data-ttu-id="1168d-149">A következő ábra egy Commerce-infrastruktúrát mutat be, amely egy vevő által birtokolt Azure Front Door-példányt tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1168d-149">The following illustration shows a Commerce infrastructure that includes a customer-owned Azure Front Door instance.</span></span>

![Vevő által birtokolt Azure Front Door-példányt tartalmazó Commerce-infrastruktúra](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a><span data-ttu-id="1168d-151">Külső CDN-szolgáltatás használata</span><span class="sxs-lookup"><span data-stu-id="1168d-151">Use an external CDN service</span></span>

<span data-ttu-id="1168d-152">Az alábbi táblázat felsorolja a tartalomvégpontok kezelésére használt külső CDN-szolgáltatás előnyeit és hátrányait.</span><span class="sxs-lookup"><span data-stu-id="1168d-152">The following table lists the pros and cons of using an external CDN service to manage content endpoints.</span></span>

| <span data-ttu-id="1168d-153">Előnyök</span><span class="sxs-lookup"><span data-stu-id="1168d-153">Pros</span></span> | <span data-ttu-id="1168d-154">Hátrányok</span><span class="sxs-lookup"><span data-stu-id="1168d-154">Cons</span></span> |
|------|------|
| <ul><li><span data-ttu-id="1168d-155">Ez a lehetőség akkor hasznos, ha a meglévő tartomány már egy külső CDN-en található.</span><span class="sxs-lookup"><span data-stu-id="1168d-155">This option is useful when the existing domain is already hosted on an external CDN.</span></span></li><li><span data-ttu-id="1168d-156">Lehet, hogy a versenytársak CDN-jei (például az Akamai) több WAF-lehetőséggel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="1168d-156">Competitor CDNs (for example, Akamai) might have more WAF capabilities.</span></span></li></ul> | <ul><li><span data-ttu-id="1168d-157">Külön szerződés és további költségszámítás szükséges.</span><span class="sxs-lookup"><span data-stu-id="1168d-157">A separate contract and additional costing are required.</span></span></li><li><span data-ttu-id="1168d-158">Az SSL-lel kapcsolatban további költségek merülhetnek fel.</span><span class="sxs-lookup"><span data-stu-id="1168d-158">SSL might incur additional costs.</span></span></li><li><span data-ttu-id="1168d-159">Mivel a szolgáltatás nem az Azure felhőstruktúra része, egy további infrastruktúra kezelésére van szükség.</span><span class="sxs-lookup"><span data-stu-id="1168d-159">Because the service is separate from the Azure cloud structure, additional infrastructure must be managed.</span></span></li><li><span data-ttu-id="1168d-160">Előfordulhat, hogy a szolgáltatás hosszabb időbeli befektetést igényel a végponti és a biztonsági beállítások során.</span><span class="sxs-lookup"><span data-stu-id="1168d-160">The service might require longer time investments in endpoint and security setup.</span></span></li><li><span data-ttu-id="1168d-161">A szolgáltatást Ön kezeli.</span><span class="sxs-lookup"><span data-stu-id="1168d-161">The service is self-managed.</span></span></li><li><span data-ttu-id="1168d-162">A szolgáltatást Ön felügyeli.</span><span class="sxs-lookup"><span data-stu-id="1168d-162">The service is self-monitored.</span></span></li></ul> |

<span data-ttu-id="1168d-163">Az alábbi ábra egy külső CDN-szolgáltatást tartalmazó Commerce-infrastruktúrát mutat be.</span><span class="sxs-lookup"><span data-stu-id="1168d-163">The following illustration shows a Commerce infrastructure that includes an external CDN service.</span></span>

![Külső CDN-szolgáltatást tartalmazó Commerce-infrastruktúra](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a><span data-ttu-id="1168d-165">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1168d-165">Additional resources</span></span>

[<span data-ttu-id="1168d-166">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1168d-166">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)