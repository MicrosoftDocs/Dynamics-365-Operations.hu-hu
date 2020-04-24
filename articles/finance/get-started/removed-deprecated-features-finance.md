---
title: Eltávolított vagy elavult funkciók a Dynamics 365 Finance szolgáltatásban
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Finance alkalmazásban.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: aebce032d7d780b296ba74fea4467425a3cbe1a7
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175108"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a><span data-ttu-id="4caff-103">Eltávolított vagy elavult funkciók a Dynamics 365 Finance szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="4caff-103">Removed or deprecated features in Dynamics 365 Finance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4caff-104">Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva, vagy eltávolításuk be van tervezve a Dynamics 365 Finance alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="4caff-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Finance.</span></span>

- <span data-ttu-id="4caff-105">Az *eltávolított* szolgáltatások már nem érhetők el a termékben.</span><span class="sxs-lookup"><span data-stu-id="4caff-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="4caff-106">Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.</span><span class="sxs-lookup"><span data-stu-id="4caff-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="4caff-107">Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.</span><span class="sxs-lookup"><span data-stu-id="4caff-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="4caff-108">A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat.</span><span class="sxs-lookup"><span data-stu-id="4caff-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="4caff-109">Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.</span><span class="sxs-lookup"><span data-stu-id="4caff-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a><span data-ttu-id="4caff-110">Eltávolított vagy elavult szolgáltatások a Finance 10.0.12 kiadásában</span><span class="sxs-lookup"><span data-stu-id="4caff-110">Features removed or deprecated in the Finance 10.0.12 release</span></span>

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a><span data-ttu-id="4caff-111">Lengyel SSRS-jelentések: Kimeneti áfajegyzék, Beszerzési áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014</span><span class="sxs-lookup"><span data-stu-id="4caff-111">Polish SSRS reports: Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="4caff-112">**Elavulás/eltávolítás oka**</span><span class="sxs-lookup"><span data-stu-id="4caff-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="4caff-113">Jogi okból nem szükséges.</span><span class="sxs-lookup"><span data-stu-id="4caff-113">Not legally required.</span></span>  |
| <span data-ttu-id="4caff-114">**Felváltotta másik szolgáltatás?**</span><span class="sxs-lookup"><span data-stu-id="4caff-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="4caff-115">Igen (Az alapértelmezett ellenőrzési fájlok Excel-formátumban, áfabevallással-JPK_VDEK)</span><span class="sxs-lookup"><span data-stu-id="4caff-115">Yes (Excel format for Standard Audit File with VAT declaration - JPK_VDEK)</span></span> |
| <span data-ttu-id="4caff-116">**Érintett területek**</span><span class="sxs-lookup"><span data-stu-id="4caff-116">**Product areas affected**</span></span>         | <span data-ttu-id="4caff-117">Pályázat</span><span class="sxs-lookup"><span data-stu-id="4caff-117">Application</span></span> |
| <span data-ttu-id="4caff-118">**Telepítési beállítás**</span><span class="sxs-lookup"><span data-stu-id="4caff-118">**Deployment option**</span></span>              | <span data-ttu-id="4caff-119">Összes</span><span class="sxs-lookup"><span data-stu-id="4caff-119">All</span></span> |
| <span data-ttu-id="4caff-120">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="4caff-120">**Status**</span></span>                         | <span data-ttu-id="4caff-121">Elavult: 2021. július 1-től már nem tervezzük az SSRS-jelentések támogatását **Kimeneti áfajegyék, Bemeneti áfajegyzék, EU összesítő áfajegyzék – Funkcióhivatkozás PL-00014**.</span><span class="sxs-lookup"><span data-stu-id="4caff-121">Deprecated: By July 1, 2021, we plan to no longer support the SSRS reports: **Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014**.</span></span> <span data-ttu-id="4caff-122">A (JPK_VDEK) alapértelmezett ellenőrzési fájljához tartozó Excel formátumú példa lesz bevezetve.</span><span class="sxs-lookup"><span data-stu-id="4caff-122">Excel format example for Standard Audit File with VAT declaration (JPK_VDEK) will be introduced instead.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a><span data-ttu-id="4caff-123">Eltávolított vagy elavult szolgáltatások a Finance 10.0.11 kiadásában</span><span class="sxs-lookup"><span data-stu-id="4caff-123">Features removed or deprecated in the Finance 10.0.11 release</span></span>

### <a name="norwegian-standard-main-accounts"></a><span data-ttu-id="4caff-124">Norvég standard főszámlák</span><span class="sxs-lookup"><span data-stu-id="4caff-124">Norwegian Standard main accounts</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="4caff-125">**Elavulás/eltávolítás oka**</span><span class="sxs-lookup"><span data-stu-id="4caff-125">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="4caff-126">Újratervezés</span><span class="sxs-lookup"><span data-stu-id="4caff-126">Redesign</span></span>  |
| <span data-ttu-id="4caff-127">**Felváltotta másik szolgáltatás?**</span><span class="sxs-lookup"><span data-stu-id="4caff-127">**Replaced by another feature?**</span></span>   | <span data-ttu-id="4caff-128">Igen (ER-formátumú alkalmazás-specifikus paraméterekkel felülírva)</span><span class="sxs-lookup"><span data-stu-id="4caff-128">Yes (Replaced with ER format application-specific parameters)</span></span> |
| <span data-ttu-id="4caff-129">**Érintett területek**</span><span class="sxs-lookup"><span data-stu-id="4caff-129">**Product areas affected**</span></span>         | <span data-ttu-id="4caff-130">Pályázat</span><span class="sxs-lookup"><span data-stu-id="4caff-130">Application</span></span> |
| <span data-ttu-id="4caff-131">**Telepítési beállítás**</span><span class="sxs-lookup"><span data-stu-id="4caff-131">**Deployment option**</span></span>              | <span data-ttu-id="4caff-132">Összes</span><span class="sxs-lookup"><span data-stu-id="4caff-132">All</span></span> |
| <span data-ttu-id="4caff-133">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="4caff-133">**Status**</span></span>                         | <span data-ttu-id="4caff-134">Elavult: 2021. április 1-től már nem tervezzük támogatni a szabványos fő számlákhoz kapcsolódó funkciókat: hivatkozási mező, kapcsolódó tábla, adatentitás.</span><span class="sxs-lookup"><span data-stu-id="4caff-134">Deprecated: By April 1, 2021, we plan to no longer support functionality related to Standard main accounts: Reference field, related table, data entity.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a><span data-ttu-id="4caff-135">Eltávolított vagy elavult szolgáltatások a Finance 10.0.7 kiadásában</span><span class="sxs-lookup"><span data-stu-id="4caff-135">Features removed or deprecated in the Finance 10.0.7 release</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="4caff-136">A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát</span><span class="sxs-lookup"><span data-stu-id="4caff-136">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="4caff-137">**Elavulás/eltávolítás oka**</span><span class="sxs-lookup"><span data-stu-id="4caff-137">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="4caff-138">A csoportfiók kiválasztásához tartozó funkció módosult.</span><span class="sxs-lookup"><span data-stu-id="4caff-138">Changed to the feature with account groups selection.</span></span>  |
| <span data-ttu-id="4caff-139">**Felváltotta másik szolgáltatás?**</span><span class="sxs-lookup"><span data-stu-id="4caff-139">**Replaced by another feature?**</span></span>   | <span data-ttu-id="4caff-140">Igen</span><span class="sxs-lookup"><span data-stu-id="4caff-140">Yes</span></span> |
| <span data-ttu-id="4caff-141">**Érintett területek**</span><span class="sxs-lookup"><span data-stu-id="4caff-141">**Product areas affected**</span></span>         | <span data-ttu-id="4caff-142">Munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="4caff-142">Workflow</span></span> |
| <span data-ttu-id="4caff-143">**Telepítési beállítás**</span><span class="sxs-lookup"><span data-stu-id="4caff-143">**Deployment option**</span></span>              | <span data-ttu-id="4caff-144">Összes</span><span class="sxs-lookup"><span data-stu-id="4caff-144">All</span></span> |
| <span data-ttu-id="4caff-145">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="4caff-145">**Status**</span></span>                         | <span data-ttu-id="4caff-146">Elavult: 2020. december 1-túl a program nem támogatja a kínai bizonylattípus-beállításokat a Számalcsoportok kiválasztása nélkül.</span><span class="sxs-lookup"><span data-stu-id="4caff-146">Deprecated: By December 1, 2020, we plan to no longer support Chinese voucher types setup without Account groups selection.</span></span> <span data-ttu-id="4caff-147">További részleteket az új kialakításról lásd: [A 10.0.7 újdonságai](whats-new-changed-10-0-7.md).</span><span class="sxs-lookup"><span data-stu-id="4caff-147">Find more details about the new design in [What's new in 10.0.7](whats-new-changed-10-0-7.md).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="4caff-148">Korábbi bejelentések az eltávolított vagy elavult funkciókról</span><span class="sxs-lookup"><span data-stu-id="4caff-148">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="4caff-149">További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="4caff-149">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
