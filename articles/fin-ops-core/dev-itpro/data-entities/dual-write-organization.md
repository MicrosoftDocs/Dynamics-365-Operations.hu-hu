---
title: Szervezeti hierarchia a Common Data Service szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations alkalmazások és a Common Data Service között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182025"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="b81c5-103">Szervezeti hierarchia a Common Data Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="b81c5-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="b81c5-104">Mivel a Dynamics 365 Finance egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik.</span><span class="sxs-lookup"><span data-stu-id="b81c5-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="b81c5-105">A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.</span><span class="sxs-lookup"><span data-stu-id="b81c5-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="b81c5-106">Bár a Common Data Service nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel.</span><span class="sxs-lookup"><span data-stu-id="b81c5-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="b81c5-107">A Common Data Service integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Common Data Service szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="b81c5-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="b81c5-108">Adatáramlás</span><span class="sxs-lookup"><span data-stu-id="b81c5-108">Data flow</span></span>

<span data-ttu-id="b81c5-109">Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Common Data Service alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával.</span><span class="sxs-lookup"><span data-stu-id="b81c5-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="b81c5-110">Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Common Data Service szolgáltatásban is tájékoztatási és bővítési célból.</span><span class="sxs-lookup"><span data-stu-id="b81c5-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="b81c5-111">A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Common Data Service szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="b81c5-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Architektúra képe](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="b81c5-113">Sablonok</span><span class="sxs-lookup"><span data-stu-id="b81c5-113">Templates</span></span>

<span data-ttu-id="b81c5-114">A szervezeti hierarchiához tartozó entitásleképezések a Finance and Operations alkalmazások és a Common Data Service szolgáltatás közötti egyirányú adatáramlást szolgálják.</span><span class="sxs-lookup"><span data-stu-id="b81c5-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="b81c5-115">Szervezeti hierarchia céljának karbantartása</span><span class="sxs-lookup"><span data-stu-id="b81c5-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="b81c5-116">Ez a sablon a Szervezeti hierarchia célja entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a más Dynamics 365 alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="b81c5-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="b81c5-117">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-117">Source field</span></span> | <span data-ttu-id="b81c5-118">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="b81c5-118">Map type</span></span> | <span data-ttu-id="b81c5-119">Célmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-119">Destination field</span></span>
---|---|---
<span data-ttu-id="b81c5-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="b81c5-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="b81c5-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="b81c5-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="b81c5-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="b81c5-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="b81c5-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="b81c5-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="b81c5-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="b81c5-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="b81c5-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="b81c5-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="b81c5-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="b81c5-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="b81c5-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="b81c5-127">msdyn\_immutable</span></span>
<span data-ttu-id="b81c5-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="b81c5-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="b81c5-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="b81c5-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="b81c5-130">Belső Szervezeti hierarchia típusa</span><span class="sxs-lookup"><span data-stu-id="b81c5-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="b81c5-131">Ez a sablon a Szervezeti hierarchia típusa entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a más Dynamics 365 alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="b81c5-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="b81c5-132">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-132">Source field</span></span> | <span data-ttu-id="b81c5-133">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="b81c5-133">Map type</span></span> | <span data-ttu-id="b81c5-134">Célmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-134">Destination field</span></span>
---|---|---
<span data-ttu-id="b81c5-135">NÉV</span><span class="sxs-lookup"><span data-stu-id="b81c5-135">NAME</span></span> | \> | <span data-ttu-id="b81c5-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="b81c5-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="b81c5-137">Belső Szervezeti hierarchia</span><span class="sxs-lookup"><span data-stu-id="b81c5-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="b81c5-138">Ez a sablon a Szervezeti hierarchia közzétéve entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a más Dynamics 365 alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="b81c5-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="b81c5-139">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-139">Source field</span></span> | <span data-ttu-id="b81c5-140">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="b81c5-140">Map type</span></span> | <span data-ttu-id="b81c5-141">Célmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-141">Destination field</span></span>
---|---|---
<span data-ttu-id="b81c5-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="b81c5-142">VALIDTO</span></span> | \> | <span data-ttu-id="b81c5-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="b81c5-143">msdyn\_validto</span></span>
<span data-ttu-id="b81c5-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="b81c5-144">VALIDFROM</span></span> | \> | <span data-ttu-id="b81c5-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="b81c5-145">msdyn\_validfrom</span></span>
<span data-ttu-id="b81c5-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="b81c5-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="b81c5-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="b81c5-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="b81c5-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="b81c5-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="b81c5-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="b81c5-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="b81c5-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="b81c5-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="b81c5-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="b81c5-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="b81c5-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="b81c5-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="b81c5-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="b81c5-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="b81c5-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="b81c5-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="b81c5-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="b81c5-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="b81c5-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="b81c5-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="b81c5-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="b81c5-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="b81c5-158">Belső szervezet</span><span class="sxs-lookup"><span data-stu-id="b81c5-158">Internal Organization</span></span>

<span data-ttu-id="b81c5-159">A Common Data Service belső szervezeti adati két entitásból származnak: **üzemi egység** és **jogi személyek**.</span><span class="sxs-lookup"><span data-stu-id="b81c5-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="b81c5-160">Üzemi egység</span><span class="sxs-lookup"><span data-stu-id="b81c5-160">Operating unit</span></span>

<span data-ttu-id="b81c5-161">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-161">Source field</span></span> | <span data-ttu-id="b81c5-162">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="b81c5-162">Map type</span></span> | <span data-ttu-id="b81c5-163">Célmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-163">Destination field</span></span>
---|---|---
<span data-ttu-id="b81c5-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="b81c5-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="b81c5-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="b81c5-165">msdyn\_languageid</span></span>
<span data-ttu-id="b81c5-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="b81c5-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="b81c5-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="b81c5-167">msdyn\_namealias</span></span>
<span data-ttu-id="b81c5-168">NÉV</span><span class="sxs-lookup"><span data-stu-id="b81c5-168">NAME</span></span> | \> | <span data-ttu-id="b81c5-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="b81c5-169">msdyn\_name</span></span>
<span data-ttu-id="b81c5-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="b81c5-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="b81c5-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="b81c5-171">msdyn\_partynumber</span></span>
<span data-ttu-id="b81c5-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="b81c5-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="b81c5-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="b81c5-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="b81c5-174">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="b81c5-174">Legal entity</span></span>

<span data-ttu-id="b81c5-175">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-175">Source field</span></span> | <span data-ttu-id="b81c5-176">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="b81c5-176">Map type</span></span> | <span data-ttu-id="b81c5-177">Célmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-177">Destination field</span></span>
---|---|---
<span data-ttu-id="b81c5-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="b81c5-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="b81c5-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="b81c5-179">msdyn\_namealias</span></span>
<span data-ttu-id="b81c5-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="b81c5-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="b81c5-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="b81c5-181">msdyn\_languageid</span></span>
<span data-ttu-id="b81c5-182">NÉV</span><span class="sxs-lookup"><span data-stu-id="b81c5-182">NAME</span></span> | \> | <span data-ttu-id="b81c5-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="b81c5-183">msdyn\_name</span></span>
<span data-ttu-id="b81c5-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="b81c5-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="b81c5-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="b81c5-185">msdyn\_partynumber</span></span>
<span data-ttu-id="b81c5-186">nincs</span><span class="sxs-lookup"><span data-stu-id="b81c5-186">none</span></span> | \>\> | <span data-ttu-id="b81c5-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="b81c5-187">msdyn\_type</span></span>
<span data-ttu-id="b81c5-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="b81c5-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="b81c5-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="b81c5-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="b81c5-190">Cég</span><span class="sxs-lookup"><span data-stu-id="b81c5-190">Company</span></span>

<span data-ttu-id="b81c5-191">Kétirányú szinkronizálás biztosít a jogi személyre (vállalat) vonatkozó adatokhoz a Finance and Operations és a más Dynamics 365 alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="b81c5-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="b81c5-192">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-192">Source field</span></span> | <span data-ttu-id="b81c5-193">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="b81c5-193">Map type</span></span> | <span data-ttu-id="b81c5-194">Célmező</span><span class="sxs-lookup"><span data-stu-id="b81c5-194">Destination field</span></span>
---|---|---
<span data-ttu-id="b81c5-195">NÉV</span><span class="sxs-lookup"><span data-stu-id="b81c5-195">NAME</span></span> | = | <span data-ttu-id="b81c5-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="b81c5-196">cdm\_name</span></span>
<span data-ttu-id="b81c5-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="b81c5-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="b81c5-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="b81c5-198">cdm\_companycode</span></span>
