---
title: Majdnem valós idejű adatok integrálása a Finance and Operations és a Common Data Service között
description: Ez a témakör a termékadatok integrációjával kapcsolatosan nyújt áttekintést a Finance and Operations és a Common Data Service között.
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
ms.openlocfilehash: b7d9e6be6fb2fef85bcf1182f89b8e370abea3d6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184485"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="48cd3-103">Közel valós idejű adatintegráció a Common Data Service szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="48cd3-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="48cd3-104">Az aktuális digitális környezetben a vállalkozási ökoszisztémákban a Microsoft Dynamics 365 alkalmazásokat csomagban szokták használni.</span><span class="sxs-lookup"><span data-stu-id="48cd3-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="48cd3-105">Mivel a személyektől, az ügyfelektől, a műveletekből és az eszközök internetes hálózatából (IoT-eszközök) származó adatok egy forrásba kerülnek bele, lehetőség van digitális visszacsatolási körök kialakítására.</span><span class="sxs-lookup"><span data-stu-id="48cd3-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="48cd3-106">Ehhez alapvetően fontos a Finance and Operations alkalmazások és más Dynamics 365 alkalmazásainak az integrációja.</span><span class="sxs-lookup"><span data-stu-id="48cd3-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="48cd3-107">Bizonyos alkalmazások a Common Data Service mellett érhetők el.</span><span class="sxs-lookup"><span data-stu-id="48cd3-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="48cd3-108">A Finance and Operations alkalmazások adatainak és a Common Data Service szolgáltatásnak az integrációja révén más alkalmazások koherensen és zökkenőmentesen kommunikálhatnak a Finance and Operations rendszerrel.</span><span class="sxs-lookup"><span data-stu-id="48cd3-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="48cd3-109">A Finance and Operations alkalmazások és a Common Data Service – kettős írású keretrendszerrel – majdnem valós idejű adatszinkronizálást tesz lehetővé a Finance and Operations alkalmazások és más Dynamics 365 alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="48cd3-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="48cd3-110">A lefedettség nagy, az alkalmazás 28 felületére terjed ki.</span><span class="sxs-lookup"><span data-stu-id="48cd3-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="48cd3-111">A célunk, hogy az üzleti folyamatokat az alkalmazásokon keresztül összekötő, zökkenőmentes adatfolyamokkal „egy Dynamics 365” felhasználói élményt kínáljunk.</span><span class="sxs-lookup"><span data-stu-id="48cd3-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Az architektúra áttekintő ábrája](media/dual-write-overview.jpg)

<span data-ttu-id="48cd3-113">A következő értékajánlatok érhetők el az ügyfelek számára:</span><span class="sxs-lookup"><span data-stu-id="48cd3-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="48cd3-114">Szervezeti hierarchia a Common Data Service rendszerben</span><span class="sxs-lookup"><span data-stu-id="48cd3-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="48cd3-115">Vállalati koncepció a Common Data Service rendszerben</span><span class="sxs-lookup"><span data-stu-id="48cd3-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="48cd3-116">Vevő integrált alapadatai</span><span class="sxs-lookup"><span data-stu-id="48cd3-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="48cd3-117">Szállító integrált alapadatai</span><span class="sxs-lookup"><span data-stu-id="48cd3-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="48cd3-118">Egyesített alaptermék</span><span class="sxs-lookup"><span data-stu-id="48cd3-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="48cd3-119">Rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="48cd3-119">System requirements</span></span>

<span data-ttu-id="48cd3-120">A szinkron, kétirányú, majdnem valós idejű adatmozgáshoz a következő verziókra van szükség:</span><span class="sxs-lookup"><span data-stu-id="48cd3-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="48cd3-121">Microsoft Dynamics 365 for Finance and Operations 10.0.4-es verzió (2019. július), 28-as vagy újabb platformfrissítéssel</span><span class="sxs-lookup"><span data-stu-id="48cd3-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="48cd3-122">Microsoft Dynamics 365 for Customer Engagement, 9.1-es (4.2-es) vagy újabb platformverzió</span><span class="sxs-lookup"><span data-stu-id="48cd3-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="48cd3-123">Telepítési útmutató</span><span class="sxs-lookup"><span data-stu-id="48cd3-123">Setup instructions</span></span>

<span data-ttu-id="48cd3-124">A Finance and Operations alkalmazások és a Common Data Service közötti integráció az alábbi lépésekkel állítható be.</span><span class="sxs-lookup"><span data-stu-id="48cd3-124">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="48cd3-125">A kettős írású rendszer beállítása a kettős írás előnézetét bejelentő oldalon lévő [lépésenkénti útmutatóban](https://aka.ms/dualwrite-docs) található.</span><span class="sxs-lookup"><span data-stu-id="48cd3-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="48cd3-126">A megoldás [a Finance and Operations, a Common Data Service és a Customer Engagement integrációja](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer-csoportból tölthető le és telepíthető.</span><span class="sxs-lookup"><span data-stu-id="48cd3-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="48cd3-127">A csomag öt megoldást tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="48cd3-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="48cd3-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="48cd3-128">Dynamics365Company</span></span>
    + <span data-ttu-id="48cd3-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="48cd3-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="48cd3-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="48cd3-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="48cd3-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="48cd3-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="48cd3-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="48cd3-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="48cd3-133">Kövesse a [kezdeti hivatkozási adatok szinkronizálásának](dual-write-initial.md) végrehajtási sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="48cd3-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="48cd3-134">A dupla írású szinkronizálás problémáinak megoldásáról a [Hibaelhárítási útmutató – adatintegráció](dual-write-troubleshooting.md) részen talál további információt.</span><span class="sxs-lookup"><span data-stu-id="48cd3-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48cd3-135">Egyszerre nem használható kettős írás és a [Potenciális ügyfelek készpénzre váltása](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="48cd3-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="48cd3-136">Ha Potenciális ügyfelek készpénzre váltása megoldást használ, el kell távolítania.</span><span class="sxs-lookup"><span data-stu-id="48cd3-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="48cd3-137">Ezenkívül a Potenciális ügyfelek készpénzre váltása megoldásban lévő kettős írású vevői és a szállítói sablonokat is le kell tiltani.</span><span class="sxs-lookup"><span data-stu-id="48cd3-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
