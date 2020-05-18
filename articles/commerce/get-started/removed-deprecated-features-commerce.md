---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Commerce alkalmazásban.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335276"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="d2dd7-103">Eltávolított vagy elavult funkciók a Dynamics 365 Commerce szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="d2dd7-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2dd7-104">Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="d2dd7-105">Az *eltávolított* szolgáltatások már nem érhetők el a termékben.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="d2dd7-106">Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="d2dd7-107">Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="d2dd7-108">A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="d2dd7-109">Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="d2dd7-110">Eltávolított vagy elavult szolgáltatások a Commerce 10.0.10 kiadásában</span><span class="sxs-lookup"><span data-stu-id="d2dd7-110">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="d2dd7-111">803-as pénztári művelet – Kitárolás és bevételezés</span><span class="sxs-lookup"><span data-stu-id="d2dd7-111">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="d2dd7-112">**Elavulás/eltávolítás oka**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="d2dd7-113">A kitárolási és bevételezési műveletek új művelet-újratervezés miatt elavulnak.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-113">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="d2dd7-114">**Felváltotta másik szolgáltatás?**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="d2dd7-115">Igen.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-115">Yes.</span></span> <span data-ttu-id="d2dd7-116">A két új pénztári-művelet helyettesíti: bejövő művelet (804) és kimenő művelet (805).</span><span class="sxs-lookup"><span data-stu-id="d2dd7-116">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="d2dd7-117">**Érintett területek**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-117">**Product areas affected**</span></span>         | <span data-ttu-id="d2dd7-118">Pénztár (POS) alkalmazás</span><span class="sxs-lookup"><span data-stu-id="d2dd7-118">Point of sale (POS) application</span></span> |
| <span data-ttu-id="d2dd7-119">**Telepítési beállítás**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-119">**Deployment option**</span></span>              | <span data-ttu-id="d2dd7-120">Összes</span><span class="sxs-lookup"><span data-stu-id="d2dd7-120">All</span></span> |
| <span data-ttu-id="d2dd7-121">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-121">**Status**</span></span>                         | <span data-ttu-id="d2dd7-122">Elavult: A 10.0.10 kiadástól kezdve a kitárolási és bevételezési művelet már nem fog új szolgáltatási frissítéseket kapni.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-122">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="d2dd7-123">Csak a kritikus hibajavítások lesznek végrehajtva ehhez a művelethez a későbbi kiadásokban.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-123">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="d2dd7-124">Minden ügyfelünket arra bíztatjuk, hogy álljanak át új [Bejövő műveletek](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) és [Kimenő műveletekre](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) lehetőségekre, amelyek továbbra is a hosszú távú termékfejlesztési program részei.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-124">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="d2dd7-125">Eltávolított vagy elavult szolgáltatások a Commerce 10.0.7 kiadásában</span><span class="sxs-lookup"><span data-stu-id="d2dd7-125">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="d2dd7-126">Commerce GetProductAvailabilities és GetAvailableInventoryNearby API-k</span><span class="sxs-lookup"><span data-stu-id="d2dd7-126">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="d2dd7-127">**Elavulás/eltávolítás oka**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-127">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="d2dd7-128">Új, optimalizált API-k lettek létrehozva, ezek váltják le a GetProductAvailabilities és GetAvailableInventoryNearby API-kat.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-128">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="d2dd7-129">**Felváltotta másik szolgáltatás?**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-129">**Replaced by another feature?**</span></span>   | <span data-ttu-id="d2dd7-130">Igen: Leváltották a GetEstimatedAvailability és a GetEstimatedProductWarehouseAvailability API-k.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-130">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="d2dd7-131">**Érintett területek**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-131">**Product areas affected**</span></span>         | <span data-ttu-id="d2dd7-132">e-Commerce alkalmazás SDK</span><span class="sxs-lookup"><span data-stu-id="d2dd7-132">e-Commerce application SDK</span></span> |
| <span data-ttu-id="d2dd7-133">**Telepítési beállítás**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-133">**Deployment option**</span></span>              | <span data-ttu-id="d2dd7-134">Összes</span><span class="sxs-lookup"><span data-stu-id="d2dd7-134">All</span></span> |
| <span data-ttu-id="d2dd7-135">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="d2dd7-135">**Status**</span></span>                         | <span data-ttu-id="d2dd7-136">Elavult: A 10.0.7-es kiadástól a továbbiakban nem fordítunk figyelmet a GetProductAvailabilities és GetAvailableInventoryNearby fejlesztésére.</span><span class="sxs-lookup"><span data-stu-id="d2dd7-136">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="d2dd7-137">Azok a szervezetek, amelyek ezeket az API-kat használják az e-Commerce telepítések során, át kell álljanak az új GetEstimatedAvailability és GetEstimatedProductWarehouseAvailability API-k használatára, és engedélyezniük kell az [Optimalizált termékelérhetőség-számítás funkciót](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="d2dd7-137">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="d2dd7-138">Korábbi bejelentések az eltávolított vagy elavult funkciókról</span><span class="sxs-lookup"><span data-stu-id="d2dd7-138">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="d2dd7-139">További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="d2dd7-139">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
