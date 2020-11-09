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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f502519ba419cb8fa322eb1d22f06d2b805f5f05
ms.sourcegitcommit: afc43699c0edc4ff2be310cb37add2ab586b64c0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000734"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="6081b-103">Szervezeti hierarchia a Common Data Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="6081b-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6081b-104">Mivel a Dynamics 365 Finance egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik.</span><span class="sxs-lookup"><span data-stu-id="6081b-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="6081b-105">A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.</span><span class="sxs-lookup"><span data-stu-id="6081b-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="6081b-106">Bár a Common Data Service nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel.</span><span class="sxs-lookup"><span data-stu-id="6081b-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="6081b-107">A Common Data Service integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Common Data Service szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="6081b-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="6081b-108">Adatáramlás</span><span class="sxs-lookup"><span data-stu-id="6081b-108">Data flow</span></span>

<span data-ttu-id="6081b-109">Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Common Data Service alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával.</span><span class="sxs-lookup"><span data-stu-id="6081b-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="6081b-110">Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Common Data Service szolgáltatásban is tájékoztatási és bővítési célból.</span><span class="sxs-lookup"><span data-stu-id="6081b-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="6081b-111">A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Common Data Service szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="6081b-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Architektúra képe](media/dual-write-data-flow.png)

<span data-ttu-id="6081b-113">A szervezeti hierarchiához tartozó entitásleképezések a Finance and Operations alkalmazások és a Common Data Service szolgáltatás közötti egyirányú adatáramlást szolgálják.</span><span class="sxs-lookup"><span data-stu-id="6081b-113">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="6081b-114">Sablonok</span><span class="sxs-lookup"><span data-stu-id="6081b-114">Templates</span></span>

<span data-ttu-id="6081b-115">A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="6081b-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="6081b-116">A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott entitás-leképezések gyűjteményét.</span><span class="sxs-lookup"><span data-stu-id="6081b-116">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="6081b-117">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="6081b-117">Finance and Operations apps</span></span> | <span data-ttu-id="6081b-118">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="6081b-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="6081b-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="6081b-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="6081b-120">Szervezeti hierarchiához kapcsolódó célok</span><span class="sxs-lookup"><span data-stu-id="6081b-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="6081b-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="6081b-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="6081b-122">Ez a sablon a Szervezeti hierarchia célja entitás egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="6081b-122">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="6081b-123">Szervezeti hierarchia típusa</span><span class="sxs-lookup"><span data-stu-id="6081b-123">Organization hierarchy type</span></span> | <span data-ttu-id="6081b-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="6081b-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="6081b-125">Ez a sablon a Szervezeti hierarchia típusa entitás egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="6081b-125">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="6081b-126">Szervezeti hierarchia – közzétett</span><span class="sxs-lookup"><span data-stu-id="6081b-126">Organization hierarchy - published</span></span> | <span data-ttu-id="6081b-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="6081b-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="6081b-128">Ez a sablon a Szervezeti hierarchia közzétéve entitás egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="6081b-128">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="6081b-129">Üzemi egység</span><span class="sxs-lookup"><span data-stu-id="6081b-129">Operating unit</span></span> | <span data-ttu-id="6081b-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="6081b-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="6081b-131">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="6081b-131">Legal entities</span></span> | <span data-ttu-id="6081b-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="6081b-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="6081b-133">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="6081b-133">Legal entities</span></span> | <span data-ttu-id="6081b-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="6081b-134">cdm_companies</span></span> | <span data-ttu-id="6081b-135">A jogi személy (vállalat) adatainak kétirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="6081b-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="6081b-136">Belső szervezet</span><span class="sxs-lookup"><span data-stu-id="6081b-136">Internal Organization</span></span>

<span data-ttu-id="6081b-137">A Common Data Service belső szervezeti adati két entitásból származnak: **üzemi egység** és **jogi személyek**.</span><span class="sxs-lookup"><span data-stu-id="6081b-137">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
