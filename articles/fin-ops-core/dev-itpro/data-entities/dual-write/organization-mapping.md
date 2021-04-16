---
title: Szervezeti hierarchia a Dataverse szolgáltatásban
description: Ez a témakör a szervezeti adatok integrációját ismerteti a Finance and Operations alkalmazás és a Dataverse között.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8b147c27b9309b1b3597f1194c415fbb2e2b7ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750812"
---
# <a name="organization-hierarchy-in-dataverse"></a><span data-ttu-id="f6275-103">Szervezeti hierarchia a Dataverse szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="f6275-103">Organization hierarchy in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f6275-104">Mivel a Dynamics 365 Finance egy pénzügyi rendszer a *szervezet* egy alapvető koncepciója, és a rendszerbeállítás a szervezeti hierarchia konfigurációjával kezdődik.</span><span class="sxs-lookup"><span data-stu-id="f6275-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="f6275-105">A vállalati pénzügyei nyomon követhetők a szervezet szintjén, illetve a szervezeti hierarchia bármely szintjén.</span><span class="sxs-lookup"><span data-stu-id="f6275-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="f6275-106">Bár a Dataverse nem rendelkezik a szervezeti hierarchia koncepciójával, mégis van néhány laza koncepciója, mint például a teljes árbevétel.</span><span class="sxs-lookup"><span data-stu-id="f6275-106">Although Dataverse doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="f6275-107">A Dataverse integráció részeként a szervezeti hierarchia adatszerkezete hozzá lesz adva a Dataverse szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="f6275-107">As part of Dataverse integration, the organization hierarchy data structure is added to Dataverse.</span></span>

## <a name="data-flow"></a><span data-ttu-id="f6275-108">Adatáramlás</span><span class="sxs-lookup"><span data-stu-id="f6275-108">Data flow</span></span>

<span data-ttu-id="f6275-109">Egy olyan üzleti ökoszisztéma, amely a Finance and Operations alkalmazásokból és Dataverse alkalmazásokból áll továbbra is rendelkezik szervezeti hierarchiával.</span><span class="sxs-lookup"><span data-stu-id="f6275-109">A business ecosystem that consists of Finance and Operations apps and Dataverse will continue to have an organization hierarchy.</span></span> <span data-ttu-id="f6275-110">Ez a szervezeti hierarchia a Finance and Operations alkalmazásokra épül, de látható a Dataverse szolgáltatásban is tájékoztatási és bővítési célból.</span><span class="sxs-lookup"><span data-stu-id="f6275-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Dataverse for informational and extensibility purposes.</span></span> <span data-ttu-id="f6275-111">A következő ábrán a szervezeti hierarchiát tartalmazó adatok láthatók, amelyek megjelennek a Dataverse szolgáltatásban egyirányú adatáramlásként a Finance and Operations alkalmazások és a Dataverse között.</span><span class="sxs-lookup"><span data-stu-id="f6275-111">The following illustration shows the organization hierarchy information that is exposed in Dataverse as a one-way data flow from Finance and Operations apps to Dataverse.</span></span>

![Architektúra képe](media/dual-write-data-flow.png)

<span data-ttu-id="f6275-113">A szervezeti hierarchiához tartozó táblaleképezések a Finance and Operations alkalmazások és a Dataverse szolgáltatás közötti egyirányú adatáramlást szolgálják.</span><span class="sxs-lookup"><span data-stu-id="f6275-113">Organization hierarchy table maps are available for one-way synchronization of data from Finance and Operations apps to Dataverse.</span></span>

## <a name="templates"></a><span data-ttu-id="f6275-114">Sablonok</span><span class="sxs-lookup"><span data-stu-id="f6275-114">Templates</span></span>

<span data-ttu-id="f6275-115">A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat.</span><span class="sxs-lookup"><span data-stu-id="f6275-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="f6275-116">A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott táblaleképezések gyűjteményét.</span><span class="sxs-lookup"><span data-stu-id="f6275-116">As the following table shows, a collection of table maps is created to sync products and related information.</span></span>

<span data-ttu-id="f6275-117">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="f6275-117">Finance and Operations apps</span></span> | <span data-ttu-id="f6275-118">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="f6275-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="f6275-119">Leírás</span><span class="sxs-lookup"><span data-stu-id="f6275-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="f6275-120">Szervezeti hierarchiához kapcsolódó célok</span><span class="sxs-lookup"><span data-stu-id="f6275-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="f6275-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="f6275-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="f6275-122">Ez a sablon a Szervezeti hierarchia célja tábla egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="f6275-122">This template provides one-way synchronization of the Organization Hierarchy Purpose table.</span></span>
<span data-ttu-id="f6275-123">Szervezeti hierarchia típusa</span><span class="sxs-lookup"><span data-stu-id="f6275-123">Organization hierarchy type</span></span> | <span data-ttu-id="f6275-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="f6275-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="f6275-125">Ez a sablon a Szervezeti hierarchia típusa tábla egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="f6275-125">This template provides one-way synchronization of the Organization Hierarchy Type table.</span></span>
<span data-ttu-id="f6275-126">Szervezeti hierarchia – közzétéve</span><span class="sxs-lookup"><span data-stu-id="f6275-126">Organization hierarchy - published</span></span> | <span data-ttu-id="f6275-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="f6275-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="f6275-128">Ez a sablon a Szervezeti hierarchia közzétéve tábla egyirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="f6275-128">This template provides one-way synchronization of the Organization Hierarchy Published table.</span></span>
<span data-ttu-id="f6275-129">Üzemi egység</span><span class="sxs-lookup"><span data-stu-id="f6275-129">Operating unit</span></span> | <span data-ttu-id="f6275-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="f6275-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="f6275-131">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="f6275-131">Legal entities</span></span> | <span data-ttu-id="f6275-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="f6275-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="f6275-133">Jogi személyek</span><span class="sxs-lookup"><span data-stu-id="f6275-133">Legal entities</span></span> | <span data-ttu-id="f6275-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="f6275-134">cdm_companies</span></span> | <span data-ttu-id="f6275-135">A jogi személy (vállalat) adatainak kétirányú szinkronizálását teszi lehetővé.</span><span class="sxs-lookup"><span data-stu-id="f6275-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="f6275-136">Belső szervezet</span><span class="sxs-lookup"><span data-stu-id="f6275-136">Internal Organization</span></span>

<span data-ttu-id="f6275-137">A Dataverse belső szervezeti adati két táblából származnak: **üzemi egység** és **jogi személyek**.</span><span class="sxs-lookup"><span data-stu-id="f6275-137">Internal organization information in Dataverse comes from two tables, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]