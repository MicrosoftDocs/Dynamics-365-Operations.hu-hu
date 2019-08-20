---
title: Szervezeti hierarchia a Common Data Service szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789198"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="49981-103">Szervezeti hierarchia a Common Data Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="49981-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="49981-104">Mivel a Microsoft Dynamics 365 for Finance and Operations egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik.</span><span class="sxs-lookup"><span data-stu-id="49981-104">Because Microsoft Dynamics 365 for Finance and Operations is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="49981-105">A vállalati pénzügyei és műveletei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.</span><span class="sxs-lookup"><span data-stu-id="49981-105">Business financials and operations can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="49981-106">Bár a Common Data Service nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel.</span><span class="sxs-lookup"><span data-stu-id="49981-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="49981-107">A Common Data Service integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Common Data Service szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="49981-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="49981-108">Adatáramlás</span><span class="sxs-lookup"><span data-stu-id="49981-108">Data flow</span></span>

<span data-ttu-id="49981-109">Egy olyan üzleti ökoszisztéma, amely a Finance and Operations és Common Data Service alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával.</span><span class="sxs-lookup"><span data-stu-id="49981-109">A business ecosystem that consists of Finance and Operations and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="49981-110">Ez a szervezeti hierarchia a Finance and Operations alkalmazásra épül, de látható a Common Data Service szolgáltatásban is tájékoztatási és bővítési célból.</span><span class="sxs-lookup"><span data-stu-id="49981-110">This organization hierarchy is built on Finance and Operations, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="49981-111">A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Common Data Service szolgáltatásban egyirányú adatáramlásként a Finance and Operations és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="49981-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations to Common Data Service.</span></span>

![Architektúra képe](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="49981-113">Sablonok</span><span class="sxs-lookup"><span data-stu-id="49981-113">Templates</span></span>

<span data-ttu-id="49981-114">A szervezeti hierarchiához tartozó entitásleképezések a Finance and Operations és a Common Data Service szolgáltatás közötti egyirányú adatáramlást szolgálják.</span><span class="sxs-lookup"><span data-stu-id="49981-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="49981-115">Szervezeti hierarchia céljának karbantartása</span><span class="sxs-lookup"><span data-stu-id="49981-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="49981-116">Ez a sablon a Szervezeti hierarchia célja entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a Dynamics 365 for Customer Engagement között.</span><span class="sxs-lookup"><span data-stu-id="49981-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to Dynamics 365 for Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="49981-117">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="49981-117">Source field</span></span> | <span data-ttu-id="49981-118">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="49981-118">Map type</span></span> | <span data-ttu-id="49981-119">Célmező</span><span class="sxs-lookup"><span data-stu-id="49981-119">Destination field</span></span>
---|---|---
<span data-ttu-id="49981-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="49981-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="49981-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="49981-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="49981-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="49981-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="49981-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="49981-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="49981-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="49981-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="49981-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="49981-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="49981-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="49981-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="49981-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="49981-127">msdyn\_immutable</span></span>
<span data-ttu-id="49981-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="49981-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="49981-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="49981-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="49981-130">Belső Szervezeti hierarchia típusa</span><span class="sxs-lookup"><span data-stu-id="49981-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="49981-131">Ez a sablon a Szervezeti hierarchia típusa entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a Customer Engagement között.</span><span class="sxs-lookup"><span data-stu-id="49981-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="49981-132">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="49981-132">Source field</span></span> | <span data-ttu-id="49981-133">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="49981-133">Map type</span></span> | <span data-ttu-id="49981-134">Célmező</span><span class="sxs-lookup"><span data-stu-id="49981-134">Destination field</span></span>
---|---|---
<span data-ttu-id="49981-135">NÉV</span><span class="sxs-lookup"><span data-stu-id="49981-135">NAME</span></span> | \> | <span data-ttu-id="49981-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="49981-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="49981-137">Belső Szervezeti hierarchia</span><span class="sxs-lookup"><span data-stu-id="49981-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="49981-138">Ez a sablon a Szervezeti hierarchia közzétéve entitás egyirányú szinkronizálását teszi lehetővé a Finance and Operations és a Customer Engagement között.</span><span class="sxs-lookup"><span data-stu-id="49981-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="49981-139">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="49981-139">Source field</span></span> | <span data-ttu-id="49981-140">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="49981-140">Map type</span></span> | <span data-ttu-id="49981-141">Célmező</span><span class="sxs-lookup"><span data-stu-id="49981-141">Destination field</span></span>
---|---|---
<span data-ttu-id="49981-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="49981-142">VALIDTO</span></span> | \> | <span data-ttu-id="49981-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="49981-143">msdyn\_validto</span></span>
<span data-ttu-id="49981-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="49981-144">VALIDFROM</span></span> | \> | <span data-ttu-id="49981-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="49981-145">msdyn\_validfrom</span></span>
<span data-ttu-id="49981-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="49981-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="49981-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="49981-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="49981-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="49981-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="49981-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="49981-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="49981-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="49981-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="49981-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="49981-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="49981-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="49981-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="49981-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="49981-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="49981-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="49981-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="49981-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="49981-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="49981-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="49981-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="49981-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="49981-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="49981-158">Belső szervezet</span><span class="sxs-lookup"><span data-stu-id="49981-158">Internal Organization</span></span>

<span data-ttu-id="49981-159">A Common Data Service belső szervezeti adati két Finance and Operations entitásból származnak: **üzemi egység** és **jogi személyek**.</span><span class="sxs-lookup"><span data-stu-id="49981-159">Internal organization information in Common Data Service comes from two Finance and Operations entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="49981-160">Üzemi egység</span><span class="sxs-lookup"><span data-stu-id="49981-160">Operating unit</span></span>

<span data-ttu-id="49981-161">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="49981-161">Source field</span></span> | <span data-ttu-id="49981-162">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="49981-162">Map type</span></span> | <span data-ttu-id="49981-163">Célmező</span><span class="sxs-lookup"><span data-stu-id="49981-163">Destination field</span></span>
---|---|---
<span data-ttu-id="49981-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="49981-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="49981-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="49981-165">msdyn\_languageid</span></span>
<span data-ttu-id="49981-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="49981-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="49981-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="49981-167">msdyn\_namealias</span></span>
<span data-ttu-id="49981-168">NÉV</span><span class="sxs-lookup"><span data-stu-id="49981-168">NAME</span></span> | \> | <span data-ttu-id="49981-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="49981-169">msdyn\_name</span></span>
<span data-ttu-id="49981-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="49981-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="49981-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="49981-171">msdyn\_partynumber</span></span>
<span data-ttu-id="49981-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="49981-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="49981-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="49981-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="49981-174">Jogi személy</span><span class="sxs-lookup"><span data-stu-id="49981-174">Legal entity</span></span>

<span data-ttu-id="49981-175">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="49981-175">Source field</span></span> | <span data-ttu-id="49981-176">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="49981-176">Map type</span></span> | <span data-ttu-id="49981-177">Célmező</span><span class="sxs-lookup"><span data-stu-id="49981-177">Destination field</span></span>
---|---|---
<span data-ttu-id="49981-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="49981-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="49981-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="49981-179">msdyn\_namealias</span></span>
<span data-ttu-id="49981-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="49981-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="49981-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="49981-181">msdyn\_languageid</span></span>
<span data-ttu-id="49981-182">NÉV</span><span class="sxs-lookup"><span data-stu-id="49981-182">NAME</span></span> | \> | <span data-ttu-id="49981-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="49981-183">msdyn\_name</span></span>
<span data-ttu-id="49981-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="49981-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="49981-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="49981-185">msdyn\_partynumber</span></span>
<span data-ttu-id="49981-186">nincs</span><span class="sxs-lookup"><span data-stu-id="49981-186">none</span></span> | \>\> | <span data-ttu-id="49981-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="49981-187">msdyn\_type</span></span>
<span data-ttu-id="49981-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="49981-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="49981-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="49981-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="49981-190">Cég</span><span class="sxs-lookup"><span data-stu-id="49981-190">Company</span></span>

<span data-ttu-id="49981-191">Kétirányú szinkronizálás biztosít a jogi személyre (vállalat) vonatkozó adatokhoz a Finance and Operations és a Customer Engagement között.</span><span class="sxs-lookup"><span data-stu-id="49981-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="49981-192">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="49981-192">Source field</span></span> | <span data-ttu-id="49981-193">Térkép típusa</span><span class="sxs-lookup"><span data-stu-id="49981-193">Map type</span></span> | <span data-ttu-id="49981-194">Célmező</span><span class="sxs-lookup"><span data-stu-id="49981-194">Destination field</span></span>
---|---|---
<span data-ttu-id="49981-195">NÉV</span><span class="sxs-lookup"><span data-stu-id="49981-195">NAME</span></span> | = | <span data-ttu-id="49981-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="49981-196">cdm\_name</span></span>
<span data-ttu-id="49981-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="49981-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="49981-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="49981-198">cdm\_companycode</span></span>
