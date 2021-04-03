---
title: Házon belüli eszközök szervizeléshez
description: Ez a témakör azt mutatja be, hogyan használható a Microsoft Dynamics 365 Field Service szolgáltatás a vevői eszközök és a belső eszközök szervizelésére.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
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
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: d4d681b2362c90b69007ea44c01c886f96cc1db1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568078"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="d8616-103">Házon belüli eszközök szervizelése</span><span class="sxs-lookup"><span data-stu-id="d8616-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d8616-104">A Microsoft Dynamics 365 Field Service a vevői eszközök szervizelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="d8616-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="d8616-105">A Dynamics 365 Supply Chain Management tárgyieszköz kezelője belső eszközök karbantartása céljából van kialakítva.</span><span class="sxs-lookup"><span data-stu-id="d8616-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="d8616-106">Ennek a két alkalmazásnak az integrációja lehetővé teszi a Field Service szolgáltatás használatát a vevői tárgyi eszközök és a belső tárgyi eszközök szervizelésére.</span><span class="sxs-lookup"><span data-stu-id="d8616-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="d8616-107">A tárgyi eszközöket a funkcionális hely vagy hierarchia alapján is osztályozhatja, és részletes szinten nyomon követheti a szervizelést.</span><span class="sxs-lookup"><span data-stu-id="d8616-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="d8616-108">További információ:[A Dynamics 365 Field Service és a Supply Chain Management integrációja](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="d8616-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="d8616-109">Sablonok</span><span class="sxs-lookup"><span data-stu-id="d8616-109">Templates</span></span>

<span data-ttu-id="d8616-110">A saját tárgyi eszközök tartalmazza azokat a központi táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="d8616-110">In-house-assets include a collection of core table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="d8616-111">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="d8616-111">Finance and Operations apps</span></span> | <span data-ttu-id="d8616-112">Modellvezérelt alkalmazások a Dynamics 365-ben</span><span class="sxs-lookup"><span data-stu-id="d8616-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="d8616-113">Leírás</span><span class="sxs-lookup"><span data-stu-id="d8616-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="d8616-114">Tárgyieszközkezelés eszközéletciklus modelljei</span><span class="sxs-lookup"><span data-stu-id="d8616-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="d8616-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="d8616-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="d8616-116">Tárgyieszközkezelés eszközéletciklus állapotai</span><span class="sxs-lookup"><span data-stu-id="d8616-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="d8616-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="d8616-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="d8616-118">Tárgyieszköz-kezelő eszközök</span><span class="sxs-lookup"><span data-stu-id="d8616-118">Asset management assets</span></span> | <span data-ttu-id="d8616-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="d8616-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="d8616-120">Tárgyieszköz-kezelő eszköztípusok</span><span class="sxs-lookup"><span data-stu-id="d8616-120">Asset management asset types</span></span> | <span data-ttu-id="d8616-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="d8616-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="d8616-122">Eszközkezelés munkavégési helyszín életciklusmodellek</span><span class="sxs-lookup"><span data-stu-id="d8616-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="d8616-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="d8616-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="d8616-124">Eszközkezelés munkavégési helyszín életciklusállapotok</span><span class="sxs-lookup"><span data-stu-id="d8616-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="d8616-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="d8616-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="d8616-126">Tárgyieszköz-kezelés munkavégzési helyszínek</span><span class="sxs-lookup"><span data-stu-id="d8616-126">Asset management functional locations</span></span> | <span data-ttu-id="d8616-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="d8616-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="d8616-128">Tárgyieszköz-kezelés munkavégzési helyszíntípusok</span><span class="sxs-lookup"><span data-stu-id="d8616-128">Asset management functional location types</span></span> | <span data-ttu-id="d8616-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="d8616-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="d8616-130">Tárgyieszközök gyártói</span><span class="sxs-lookup"><span data-stu-id="d8616-130">Asset management manufacturers</span></span> | <span data-ttu-id="d8616-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="d8616-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="d8616-132">Tárgyieszköz-kezelési modellek</span><span class="sxs-lookup"><span data-stu-id="d8616-132">Asset management models</span></span> | <span data-ttu-id="d8616-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="d8616-133">msdyn\_models</span></span> | |
| <span data-ttu-id="d8616-134">Tárgyeszköz-kezelés garancia</span><span class="sxs-lookup"><span data-stu-id="d8616-134">Asset management warranty</span></span> | <span data-ttu-id="d8616-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="d8616-135">msdyn\_warranties</span></span> | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]