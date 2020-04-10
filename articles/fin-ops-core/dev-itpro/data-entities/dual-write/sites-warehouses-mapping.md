---
title: Integrált helyek és raktárak
description: Ez a témakör a hely- és raktáradatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
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
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 1b9181211bbb65cdfc46e63f3cee0e9f5bc9f6a4
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173062"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="e1601-103">Integrált telephelyek és raktárak</span><span class="sxs-lookup"><span data-stu-id="e1601-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="e1601-104">Ez a témakör a hely- és raktáradatok integrációját ismerteti a Finance and Operations és a Common Data Service között.</span><span class="sxs-lookup"><span data-stu-id="e1601-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="e1601-105">Az üzemeltetési helyszínek és a raktárak közös fogalmak az Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="e1601-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="e1601-106">Ezek a vállalat ellátási láncának modellezésére használatosak.</span><span class="sxs-lookup"><span data-stu-id="e1601-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="e1601-107">Sablonok</span><span class="sxs-lookup"><span data-stu-id="e1601-107">Templates</span></span>

<span data-ttu-id="e1601-108">A Common Data Serviceintegrációjával ezekkel elvekkel és a hozzájuk kapcsolódó adatokkal a következő táblázatban található Common Data Service helyek és raktárak adatentitásai használhatók.</span><span class="sxs-lookup"><span data-stu-id="e1601-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="e1601-109">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="e1601-109">Finance and Operations apps</span></span> | <span data-ttu-id="e1601-110">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="e1601-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="e1601-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="e1601-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="e1601-112">Webhelyek</span><span class="sxs-lookup"><span data-stu-id="e1601-112">Sites</span></span> | <span data-ttu-id="e1601-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="e1601-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="e1601-114">Raktárak</span><span class="sxs-lookup"><span data-stu-id="e1601-114">Warehouses</span></span> | <span data-ttu-id="e1601-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="e1601-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

