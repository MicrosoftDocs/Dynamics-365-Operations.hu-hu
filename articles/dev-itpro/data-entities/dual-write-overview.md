---
title: Majdnem valós idejű adatok integrálása a Finance and Operations és a Common Data Service között
description: Ez a cikk a Microsoft Dynamics 365 for Finance and Operations és a Common Data Service közötti integrációt tekinti át.
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
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797228"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a><span data-ttu-id="aaef9-103">Majdnem valós idejű adatok integrálása a Finance and Operations és a Common Data Service között</span><span class="sxs-lookup"><span data-stu-id="aaef9-103">Near-real-time data integration between Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="aaef9-104">Az aktuális digitális környezetben a vállalkozási ökoszisztémákban a Microsoft Dynamics 365 csomag egészét szokták használni.</span><span class="sxs-lookup"><span data-stu-id="aaef9-104">In the current digital world, business ecosystems use the Microsoft Dynamics 365 suite as a whole.</span></span> <span data-ttu-id="aaef9-105">Mivel a személyektől, az ügyfelektől, a műveletekből és az eszközök internetes hálózatából (IoT-eszközök) származó adatok egy forrásba kerülnek bele, lehetőség van digitális visszacsatolási körök kialakítására.</span><span class="sxs-lookup"><span data-stu-id="aaef9-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="aaef9-106">Ehhez alapvetően fontos a Dynamics 365 for Finance and Operations és a Dynamics 365 for Customer Engagement alkalmazásainak az integrációja.</span><span class="sxs-lookup"><span data-stu-id="aaef9-106">To achieve this experience, integration between Dynamics 365 for Finance and Operations and Dynamics 365 for Customer Engagement applications is essential.</span></span> <span data-ttu-id="aaef9-107">A Customer Engagement-alkalmazások a Common Data Service mellett érhetők el.</span><span class="sxs-lookup"><span data-stu-id="aaef9-107">Customer Engagement applications are built on top of Common Data Service.</span></span> <span data-ttu-id="aaef9-108">A Finance and Operations adatainak és a Common Data Service szolgáltatásnak az integrációja révén a Customer Engagement-alkalmazások koherensen és zökkenőmentesen kommunikálhatnak a Finance and Operations rendszerrel.</span><span class="sxs-lookup"><span data-stu-id="aaef9-108">Integration between Finance and Operations data with Common Data Service lets Customer Engagement applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="aaef9-109">A Finance and Operations és a Common Data Service – kettős írású keretrendszerrel – majdnem valós idejű adatszinkronizálást tesz lehetővé a Customer Engagement-alkalmazások és a Finance and Operations rendszer között.</span><span class="sxs-lookup"><span data-stu-id="aaef9-109">Finance and Operations and Common Data Service provide near-real-time data synchronization between Finance and Operations and Customer Engagement applications via a dual-write framework.</span></span> <span data-ttu-id="aaef9-110">A lefedettség nagy, a Finance and Operations 28 támadási felületére terjed ki.</span><span class="sxs-lookup"><span data-stu-id="aaef9-110">The coverage is broad and spans 28 surface areas of Finance and Operations.</span></span> <span data-ttu-id="aaef9-111">A célunk, hogy az üzleti folyamatokat az alkalmazásokon keresztül összekötő, zökkenőmentes adatfolyamokkal „egy Dynamics 365” felhasználói élményt kínáljunk.</span><span class="sxs-lookup"><span data-stu-id="aaef9-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Az architektúra áttekintő ábrája](media/dual-write-overview.jpg)

<span data-ttu-id="aaef9-113">A következő értékajánlatok érhetők el az ügyfelek számára:</span><span class="sxs-lookup"><span data-stu-id="aaef9-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="aaef9-114">Szervezeti hierarchia a Common Data Service rendszerben</span><span class="sxs-lookup"><span data-stu-id="aaef9-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="aaef9-115">Vállalati koncepció a Common Data Service rendszerben</span><span class="sxs-lookup"><span data-stu-id="aaef9-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="aaef9-116">Vevő integrált alapadatai</span><span class="sxs-lookup"><span data-stu-id="aaef9-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="aaef9-117">Szállító integrált alapadatai</span><span class="sxs-lookup"><span data-stu-id="aaef9-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="aaef9-118">Egyesített alaptermék</span><span class="sxs-lookup"><span data-stu-id="aaef9-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="aaef9-119">Rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="aaef9-119">System requirements</span></span>

<span data-ttu-id="aaef9-120">A szinkron, kétirányú, majdnem valós idejű adatmozgáshoz a következő verziókra van szükség:</span><span class="sxs-lookup"><span data-stu-id="aaef9-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="aaef9-121">Microsoft Dynamics 365 for Finance and Operations 10.0.4-es verzió (2019. július), 28-as vagy újabb platformfrissítéssel</span><span class="sxs-lookup"><span data-stu-id="aaef9-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="aaef9-122">Microsoft Dynamics 365 for Customer Engagement, 9.1-es (4.2-es) vagy újabb platformverzió</span><span class="sxs-lookup"><span data-stu-id="aaef9-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="aaef9-123">Telepítési útmutató</span><span class="sxs-lookup"><span data-stu-id="aaef9-123">Setup instructions</span></span>

<span data-ttu-id="aaef9-124">A Finance and Operations és a Common Data Service közötti integráció az alábbi lépésekkel állítható be.</span><span class="sxs-lookup"><span data-stu-id="aaef9-124">Follow these steps to set up integration between Finance and Operations and Common Data Service.</span></span>
    
1. <span data-ttu-id="aaef9-125">A kettős írású rendszer beállítása a kettős írás előnézetét bejelentő oldalon lévő [lépésenkénti útmutatóban](https://aka.ms/dualwrite-docs) található.</span><span class="sxs-lookup"><span data-stu-id="aaef9-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="aaef9-126">A megoldás [a Finance and Operations, a Common Data Service és a Customer Engagement integrációja](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer-csoportból tölthető le és telepíthető.</span><span class="sxs-lookup"><span data-stu-id="aaef9-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="aaef9-127">A csomag öt megoldást tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="aaef9-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="aaef9-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="aaef9-128">Dynamics365Company</span></span>
    + <span data-ttu-id="aaef9-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="aaef9-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="aaef9-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="aaef9-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="aaef9-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="aaef9-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="aaef9-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="aaef9-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="aaef9-133">Kövesse a [kezdeti hivatkozási adatok szinkronizálásának](dual-write-initial.md) végrehajtási sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="aaef9-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="aaef9-134">A dupla írású szinkronizálás problémáinak megoldásáról a [Hibaelhárítási útmutató – adatintegráció](dual-write-troubleshooting.md) részen talál további információt.</span><span class="sxs-lookup"><span data-stu-id="aaef9-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aaef9-135">Egyszerre nem használható kettős írás és a [Potenciális ügyfelek készpénzre váltása](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="aaef9-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="aaef9-136">Ha Potenciális ügyfelek készpénzre váltása megoldást használ, el kell távolítania.</span><span class="sxs-lookup"><span data-stu-id="aaef9-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="aaef9-137">Ezenkívül a Potenciális ügyfelek készpénzre váltása megoldásban lévő kettős írású vevői és a szállítói sablonokat is le kell tiltani.</span><span class="sxs-lookup"><span data-stu-id="aaef9-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
