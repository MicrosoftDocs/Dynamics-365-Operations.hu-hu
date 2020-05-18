---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Supply Chain Management alkalmazásból.
author: kamaybac
manager: AnnBe
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7502cd16129431d41d152508fb3b49ff85a5a9f8
ms.sourcegitcommit: f1db998ecfccca660eb15cc2739b12c8463fa54d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2020
ms.locfileid: "3331248"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a><span data-ttu-id="38475-103">Eltávolított vagy elavult funkciók a Dynamics 365 Supply Chain Management szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="38475-103">Removed or deprecated features in Dynamics 365 Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38475-104">Ez a témakör frissítve lesz a Dynamics 365 Supply Chain Management újonnan eltávolított vagy avultatott szolgáltatásaival.</span><span class="sxs-lookup"><span data-stu-id="38475-104">This topic will be updated as new removed or deprecated features are documented for Dynamics 365 Supply Chain Management.</span></span>

- <span data-ttu-id="38475-105">Az *eltávolított* szolgáltatások már nem érhetők el a termékben.</span><span class="sxs-lookup"><span data-stu-id="38475-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="38475-106">Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.</span><span class="sxs-lookup"><span data-stu-id="38475-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="38475-107">Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.</span><span class="sxs-lookup"><span data-stu-id="38475-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span>

> [!NOTE]
> <span data-ttu-id="38475-108">A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat.</span><span class="sxs-lookup"><span data-stu-id="38475-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="38475-109">Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.</span><span class="sxs-lookup"><span data-stu-id="38475-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a><span data-ttu-id="38475-110">Eltávolított vagy elavult szolgáltatások a Supply Chain Management 10.0.11 kiadásában</span><span class="sxs-lookup"><span data-stu-id="38475-110">Features removed or deprecated in the Supply Chain Management 10.0.11 release</span></span>

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a><span data-ttu-id="38475-111">A Supply Chain Management beépített tervezési motorjának használata elosztási forgatókönyvekhez</span><span class="sxs-lookup"><span data-stu-id="38475-111">Use of built-in Supply Chain Management master planning engine for distribution scenarios</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="38475-112">**Elavulás/eltávolítás oka**</span><span class="sxs-lookup"><span data-stu-id="38475-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="38475-113">A teljesítmény fokozása és az SQL-adatbázis terhelésének minimalizálása érdekében alaptervezés futtatásakor a Supply Chain Management alaptervezési motorját leváltja a Tervezési optimalizálás.</span><span class="sxs-lookup"><span data-stu-id="38475-113">To enhance performance and minimize the SQL database load during master planning runs, the built-in Supply Chain Management master planning engine is being replaced by Planning Optimization.</span></span> <span data-ttu-id="38475-114">A Tervezési optimalizálás lehetővé teszi a gyors tervezésfuttatásokat, amelyek munkaidőben is elvégezhetők.</span><span class="sxs-lookup"><span data-stu-id="38475-114">Planning Optimization allows for fast planning runs that can be performed even during office hours.</span></span> <span data-ttu-id="38475-115">Ez lehetővé teszi a tervezők számára, hogy azonnal reagáljanak az igény- vagy a tervezési paraméterek változásaira.</span><span class="sxs-lookup"><span data-stu-id="38475-115">This enables planners to react immediately to changes in demand or planning parameters.</span></span> |
| <span data-ttu-id="38475-116">**Felváltotta másik szolgáltatás?**</span><span class="sxs-lookup"><span data-stu-id="38475-116">**Replaced by another feature?**</span></span>   | <span data-ttu-id="38475-117">Igen, a Tervezés optimalizálása átveszi a meglévő beépített Supply Chain Management alaptervezési motorjának szerepét.</span><span class="sxs-lookup"><span data-stu-id="38475-117">Yes, Planning Optimization will replace the existing built-in Supply Chain Management master planning engine.</span></span> |
| <span data-ttu-id="38475-118">**Érintett területek**</span><span class="sxs-lookup"><span data-stu-id="38475-118">**Product areas affected**</span></span>         | <span data-ttu-id="38475-119">Supply Chain Management – Alaptervezés</span><span class="sxs-lookup"><span data-stu-id="38475-119">Supply Chain Management - Master planning</span></span> |
| <span data-ttu-id="38475-120">**Telepítési beállítás**</span><span class="sxs-lookup"><span data-stu-id="38475-120">**Deployment option**</span></span>              | <span data-ttu-id="38475-121">Csak felhő.</span><span class="sxs-lookup"><span data-stu-id="38475-121">Cloud only.</span></span> <span data-ttu-id="38475-122">A Tervezés optimalizálása nem támogatott helyszíni telepítések esetében.</span><span class="sxs-lookup"><span data-stu-id="38475-122">Planning Optimization is not supported with on-premises deployments.</span></span> |
| <span data-ttu-id="38475-123">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="38475-123">**Status**</span></span>                         | <span data-ttu-id="38475-124">Elavult.</span><span class="sxs-lookup"><span data-stu-id="38475-124">Deprecated.</span></span> <span data-ttu-id="38475-125">2021 áprilisában az elosztási forgatókönyvek már nem lesznek támogatottak a beépített Dynamics 365 Supply Chain Management alaptervezési motorral.</span><span class="sxs-lookup"><span data-stu-id="38475-125">On April 2021, distribution scenarios will no longer be supported with the built-in Dynamics 365 Supply Chain Management master planning engine.</span></span> <span data-ttu-id="38475-126">Terjesztési esetekhez a vevőknek a Tervezési optimalizációt kell használniuk az alaptervezés számításaihoz.</span><span class="sxs-lookup"><span data-stu-id="38475-126">For distribution scenarios, customers must use Planning Optimization for master planning calculations.</span></span> <span data-ttu-id="38475-127">További tájékoztatás: [Tervezésoptimalizálás dokumentációja](https://go.microsoft.com/fwlink/?linkid=2105830).</span><span class="sxs-lookup"><span data-stu-id="38475-127">For more information, see [Planning Optimization documentation](https://go.microsoft.com/fwlink/?linkid=2105830).</span></span> <span data-ttu-id="38475-128">A Dynamics 365 Supply Chain Management helyszíni telepítését használó ügyfelek továbbra is használhatják a Supply Chain Management alaptervezés motorját a terjesztési forgatókönyvekhez 2021. áprilisa után.</span><span class="sxs-lookup"><span data-stu-id="38475-128">Customers with on-premises deployments of Dynamics 365 Supply Chain Management may continue to use the Supply Chain Management master planning engine for distribution scenarios after April 2021.</span></span> <span data-ttu-id="38475-129">Azonban nem lesz több funkciófejlesztés.</span><span class="sxs-lookup"><span data-stu-id="38475-129">However, no more feature enhancements will be provided.</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="38475-130">Korábbi bejelentések az eltávolított vagy elavult funkciókról</span><span class="sxs-lookup"><span data-stu-id="38475-130">Previous announcements about removed or deprecated features</span></span>

<span data-ttu-id="38475-131">További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="38475-131">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
