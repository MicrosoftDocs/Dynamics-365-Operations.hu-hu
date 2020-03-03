---
title: Szervezeti hierarchia a Common Data Service szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations alkalmazás és a Common Data Service között.
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
ms.openlocfilehash: fbf7cc33d12fb54d2ff02acc46ba2e284b2a2b3f
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019818"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="27946-103">Szervezeti hierarchia a Common Data Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="27946-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="27946-104">Mivel a Dynamics 365 Finance egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik.</span><span class="sxs-lookup"><span data-stu-id="27946-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="27946-105">A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.</span><span class="sxs-lookup"><span data-stu-id="27946-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="27946-106">Bár a Common Data Service nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel.</span><span class="sxs-lookup"><span data-stu-id="27946-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="27946-107">A Common Data Service integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Common Data Service szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="27946-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="27946-108">Adatáramlás</span><span class="sxs-lookup"><span data-stu-id="27946-108">Data flow</span></span>

<span data-ttu-id="27946-109">Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Common Data Service alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával.</span><span class="sxs-lookup"><span data-stu-id="27946-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="27946-110">Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Common Data Service szolgáltatásban is tájékoztatási és bővítési célból.</span><span class="sxs-lookup"><span data-stu-id="27946-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="27946-111">A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Common Data Service szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="27946-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Architektúra képe](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="27946-113">Sablonok</span><span class="sxs-lookup"><span data-stu-id="27946-113">Templates</span></span>

<span data-ttu-id="27946-114">A szervezeti hierarchiához tartozó entitásleképezések a Finance and Operations alkalmazások és a Common Data Service szolgáltatás közötti egyirányú adatáramlást szolgálják.</span><span class="sxs-lookup"><span data-stu-id="27946-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="27946-115">Sablonok</span><span class="sxs-lookup"><span data-stu-id="27946-115">Templates</span></span>

<span data-ttu-id="27946-116">A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="27946-116">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="27946-117">A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott entitás-leképezések gyűjteményét.</span><span class="sxs-lookup"><span data-stu-id="27946-117">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="27946-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="27946-118">Finance and Operations</span></span> | <span data-ttu-id="27946-119">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="27946-119">Other Dynamics 365 apps</span></span> | <span data-ttu-id="27946-120">Leírás</span><span class="sxs-lookup"><span data-stu-id="27946-120">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="27946-121">Szervezeti hierarchiához kapcsolódó célok</span><span class="sxs-lookup"><span data-stu-id="27946-121">Organization hierarchy purposes</span></span> | <span data-ttu-id="27946-122">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="27946-122">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="27946-123">Ez a sablon a Szervezeti hierarchia célja entitás egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="27946-123">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="27946-124">Szervezeti hierarchia típusa</span><span class="sxs-lookup"><span data-stu-id="27946-124">Organization hierarchy type</span></span> | <span data-ttu-id="27946-125">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="27946-125">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="27946-126">Ez a sablon a Szervezeti hierarchia típusa entitás egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="27946-126">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="27946-127">Szervezeti hierarchia – közzétett</span><span class="sxs-lookup"><span data-stu-id="27946-127">Organization hierarchy - published</span></span> | <span data-ttu-id="27946-128">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="27946-128">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="27946-129">Ez a sablon a Szervezeti hierarchia közzétéve entitás egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="27946-129">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="27946-130">Üzemi egység</span><span class="sxs-lookup"><span data-stu-id="27946-130">Operating unit</span></span> | <span data-ttu-id="27946-131">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="27946-131">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="27946-132">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="27946-132">Legal entities</span></span> | <span data-ttu-id="27946-133">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="27946-133">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="27946-134">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="27946-134">Legal entities</span></span> | <span data-ttu-id="27946-135">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="27946-135">cdm_companies</span></span> | <span data-ttu-id="27946-136">A jogi személy (vállalat) adatainak kétirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="27946-136">Provides bidirectional synchronization of legal entity (company) information.</span></span>


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="27946-137">Belső szervezet</span><span class="sxs-lookup"><span data-stu-id="27946-137">Internal Organization</span></span>

<span data-ttu-id="27946-138">A Common Data Service belső szervezeti adati két entitásból származnak: **üzemi egység** és **jogi személyek**.</span><span class="sxs-lookup"><span data-stu-id="27946-138">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
