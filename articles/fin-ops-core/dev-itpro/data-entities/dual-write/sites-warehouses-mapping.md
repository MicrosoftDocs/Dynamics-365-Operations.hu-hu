---
title: Integrált helyek és raktárak
description: Ez a témakör a hely- és raktáradatok integrációját ismerteti a Finance and Operations és a Dataverse között.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
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
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: b93e5f15e281c20f8688d496fc78f8b46b8aa996
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560361"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="70dfe-103">Integrált telephelyek és raktárak</span><span class="sxs-lookup"><span data-stu-id="70dfe-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="70dfe-104">Ez a témakör a hely- és raktáradatok integrációját ismerteti a Finance and Operations és a Dataverse között.</span><span class="sxs-lookup"><span data-stu-id="70dfe-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="70dfe-105">Az üzemeltetési helyszínek és a raktárak közös fogalmak az Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="70dfe-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="70dfe-106">Ezek a vállalat ellátási láncának modellezésére használatosak.</span><span class="sxs-lookup"><span data-stu-id="70dfe-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="70dfe-107">Sablonok</span><span class="sxs-lookup"><span data-stu-id="70dfe-107">Templates</span></span>

<span data-ttu-id="70dfe-108">A Dataverse integrációjával ezekkel elvekkel és a hozzájuk kapcsolódó adatokkal a következő táblázatban található Dataverse helyek és raktárak adattáblái használhatók.</span><span class="sxs-lookup"><span data-stu-id="70dfe-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="70dfe-109">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="70dfe-109">Finance and Operations apps</span></span> | <span data-ttu-id="70dfe-110">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="70dfe-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="70dfe-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="70dfe-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="70dfe-112">Webhelyek</span><span class="sxs-lookup"><span data-stu-id="70dfe-112">Sites</span></span> | <span data-ttu-id="70dfe-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="70dfe-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="70dfe-114">Raktárak</span><span class="sxs-lookup"><span data-stu-id="70dfe-114">Warehouses</span></span> | <span data-ttu-id="70dfe-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="70dfe-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]