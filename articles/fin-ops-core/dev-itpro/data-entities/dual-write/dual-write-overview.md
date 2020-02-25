---
title: Közel valós idejű adatintegráció a Common Data Service szolgáltatással
description: Ez a cikk a Finance and Operations és a Common Data Service közötti integrációt tekinti át.
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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019822"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="c5d6b-103">Közel valós idejű adatintegráció a Common Data Service szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="c5d6b-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="c5d6b-104">Az aktuális digitális környezetben a vállalkozási ökoszisztémákban a Microsoft Dynamics 365 alkalmazásokat csomagban szokták használni.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="c5d6b-105">Mivel a személyektől, az ügyfelektől, a műveletekből és az eszközök internetes hálózatából (IoT-eszközök) származó adatok egy forrásba kerülnek bele, lehetőség van digitális visszacsatolási körök kialakítására.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="c5d6b-106">Ehhez alapvetően fontos a Finance and Operations alkalmazások és más Dynamics 365 alkalmazásainak az integrációja.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="c5d6b-107">Bizonyos alkalmazások a Common Data Service mellett érhetők el.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="c5d6b-108">A Finance and Operations alkalmazásadatok integrációja a Common Data Service megoldással lehetővé teszi más alkalmazások számára a koherens és folyékony kommunikációt a Finance and Operations programmal.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="c5d6b-109">A Finance and Operations alkalmazások és a Common Data Service – kettős írású keretrendszerrel – majdnem valós idejű adatszinkronizálást tesz lehetővé a Finance and Operations alkalmazások és más Dynamics 365 alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="c5d6b-110">A lefedettség nagy, az alkalmazás 28 felületére terjed ki.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="c5d6b-111">A célunk, hogy az üzleti folyamatokat az alkalmazásokon keresztül összekötő, zökkenőmentes adatfolyamokkal „egy Dynamics 365” felhasználói élményt kínáljunk.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Az architektúra áttekintő ábrája](media/dual-write-overview.jpg)

<span data-ttu-id="c5d6b-113">A következő értékajánlatok érhetők el:</span><span class="sxs-lookup"><span data-stu-id="c5d6b-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="c5d6b-114">Szervezeti hierarchia a Common Data Service rendszerben</span><span class="sxs-lookup"><span data-stu-id="c5d6b-114">Organization hierarchy in Common Data Service</span></span>](organization-mapping.md)
+ [<span data-ttu-id="c5d6b-115">Vállalati koncepció a Common Data Service rendszerben</span><span class="sxs-lookup"><span data-stu-id="c5d6b-115">Company concept in Common Data Service</span></span>](company-data.md)
+ [<span data-ttu-id="c5d6b-116">Vevő integrált alapadatai</span><span class="sxs-lookup"><span data-stu-id="c5d6b-116">Integrated customer master</span></span>](customer-mapping.md)
+ [<span data-ttu-id="c5d6b-117">Integrált főkönyv</span><span class="sxs-lookup"><span data-stu-id="c5d6b-117">Integrated ledger</span></span>](ledger-mapping.md)
+ [<span data-ttu-id="c5d6b-118">Egységes terméktapasztalat</span><span class="sxs-lookup"><span data-stu-id="c5d6b-118">Unified product experience</span></span>](product-mapping.md)
+ [<span data-ttu-id="c5d6b-119">Szállító integrált alapadatai</span><span class="sxs-lookup"><span data-stu-id="c5d6b-119">Integrated vendor master</span></span>](vendor-mapping.md)
+ [<span data-ttu-id="c5d6b-120">Integrált helyek és raktárak</span><span class="sxs-lookup"><span data-stu-id="c5d6b-120">Integrated sites and warehouses</span></span>](sites-warehouses-mapping.md)
+ [<span data-ttu-id="c5d6b-121">Integrált adózási alapadatok</span><span class="sxs-lookup"><span data-stu-id="c5d6b-121">Integrated tax master</span></span>](tax-mapping.md)

## <a name="system-requirements"></a><span data-ttu-id="c5d6b-122">Rendszerkövetelmények</span><span class="sxs-lookup"><span data-stu-id="c5d6b-122">System requirements</span></span>

<span data-ttu-id="c5d6b-123">A szinkron, kétirányú, majdnem valós idejű adatmozgáshoz a következő verziókra van szükség:</span><span class="sxs-lookup"><span data-stu-id="c5d6b-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="c5d6b-124">Microsoft Dynamics 365 for Finance and Operations 10.0.4-es verzió (2019. július), 28-as vagy újabb platformfrissítéssel</span><span class="sxs-lookup"><span data-stu-id="c5d6b-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="c5d6b-125">Microsoft Dynamics 365 for Customer Engagement, 9.1-es (4.2-es) vagy újabb platformverzió</span><span class="sxs-lookup"><span data-stu-id="c5d6b-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="c5d6b-126">Telepítési útmutató</span><span class="sxs-lookup"><span data-stu-id="c5d6b-126">Setup instructions</span></span>

<span data-ttu-id="c5d6b-127">A Finance and Operations alkalmazások és a Common Data Service közötti integráció beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="c5d6b-128">A kettős írású rendszer beállítása a kettős írás előnézetét bejelentő oldalon lévő [lépésenkénti útmutatóban](https://aka.ms/dualwrite-docs) található.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="c5d6b-129">Töltse le és telepítse a megoldást a [Fin Ops és CDS/CE integráció a kettős írás segítségével](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer-csoportból.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-129">Download and install the solution from the [Fin Ops and CDS/CE Integration via Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="c5d6b-130">A csomag öt megoldást tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="c5d6b-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="c5d6b-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="c5d6b-131">Dynamics365Company</span></span>
    + <span data-ttu-id="c5d6b-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="c5d6b-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="c5d6b-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="c5d6b-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="c5d6b-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="c5d6b-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="c5d6b-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="c5d6b-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="c5d6b-136">Kövesse a [kezdeti hivatkozási adatok szinkronizálásának](initial-sync.md) végrehajtási sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-136">Follow the execution order for [synchronizing initial reference data](initial-sync.md).</span></span>
4. <span data-ttu-id="c5d6b-137">A dupla írású szinkronizálás problémáinak megoldásáról a [Hibaelhárítási útmutató – adatintegráció](dual-write-troubleshooting.md) részen talál további információt.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5d6b-138">Egyszerre nem használható kettős írás és a [Potenciális ügyfelek készpénzre váltása](../../../../supply-chain/sales-marketing/prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="c5d6b-138">You can’t run dual-write and [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) side-by-side.</span></span> <span data-ttu-id="c5d6b-139">Ha Potenciális ügyfelek készpénzre váltása megoldást használ, el kell távolítania.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="c5d6b-140">Ezenkívül a Potenciális ügyfelek készpénzre váltása megoldásban lévő kettős írású vevői és a szállítói sablonokat is le kell tiltani.</span><span class="sxs-lookup"><span data-stu-id="c5d6b-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
