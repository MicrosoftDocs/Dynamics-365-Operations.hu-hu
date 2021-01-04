---
title: A Lifecycle Services (LCS) szolgáltatás eltávolított vagy elavult funkciói
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból, vagy az eltávolításuk be van tervezve.
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: abf7a1a0a75ac3098efeeab3df65481999b69acc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687878"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a><span data-ttu-id="e2d83-103">A Lifecycle Services (LCS) szolgáltatás eltávolított vagy elavult funkciói</span><span class="sxs-lookup"><span data-stu-id="e2d83-103">Removed or deprecated features in Lifecycle Services (LCS)</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e2d83-104">Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva vagy elavultak a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="e2d83-104">This topic describes features that have been removed or deprecated for Microsoft Dynamics Lifecycle Services (LCS).</span></span>

- <span data-ttu-id="e2d83-105">Az *eltávolított* szolgáltatások már nem érhetők el a szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="e2d83-105">A *removed* feature is no longer available in the service.</span></span>
- <span data-ttu-id="e2d83-106">Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.</span><span class="sxs-lookup"><span data-stu-id="e2d83-106">A *deprecated* feature isn't in active development and might be removed in a future update.</span></span>

<span data-ttu-id="e2d83-107">Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.</span><span class="sxs-lookup"><span data-stu-id="e2d83-107">This list is provided so that you can consider these removals and deprecations as you do your own planning.</span></span>

## <a name="october-2019-announcements"></a><span data-ttu-id="e2d83-108">2019. októberi bejelentések</span><span class="sxs-lookup"><span data-stu-id="e2d83-108">October 2019 announcements</span></span>

### <a name="flowchart-diagrams-in-business-process-modeler"></a><span data-ttu-id="e2d83-109">Az üzletifolyamat-modellező folyamatábrái</span><span class="sxs-lookup"><span data-stu-id="e2d83-109">Flowchart diagrams in Business process modeler</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="e2d83-110"><strong>Elavulás/eltávolítás oka</strong></span><span class="sxs-lookup"><span data-stu-id="e2d83-110"><strong>Reason for deprecation/removal</strong></span></span></td>
<td><span data-ttu-id="e2d83-111">Elavulttá fog válni a folyamatábra-diagramok összetevője az Üzletifolyamat-modellezőben (BPM), mert az örökölt kialakítás alacsony kihasználtságot eredményezett.</span><span class="sxs-lookup"><span data-stu-id="e2d83-111">We are deprecating the flowchart diagrams component in Business process modeler (BPM), because the legacy design caused low usage.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e2d83-112"><strong>Felváltotta másik szolgáltatás?</strong></span><span class="sxs-lookup"><span data-stu-id="e2d83-112"><strong>Replaced by another feature?</strong></span></span></td>
<td><span data-ttu-id="e2d83-113">Nem</span><span class="sxs-lookup"><span data-stu-id="e2d83-113">No</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e2d83-114"><strong>Érintett területek</strong></span><span class="sxs-lookup"><span data-stu-id="e2d83-114"><strong>Areas affected</strong></span></span></td>
<td><span data-ttu-id="e2d83-115">Üzletifolyamat-modellező</span><span class="sxs-lookup"><span data-stu-id="e2d83-115">Business process modeler</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e2d83-116"><strong>Állapot</strong></span><span class="sxs-lookup"><span data-stu-id="e2d83-116"><strong>Status</strong></span></span></td>
<td><span data-ttu-id="e2d83-117">Elavult: A BPM folyamatábra összetevője várhatóan 2020-ban eltávolításra kerül.</span><span class="sxs-lookup"><span data-stu-id="e2d83-117">Deprecated: The flowchart diagrams component in BPM is expected to be removed in 2020.</span></span> <span data-ttu-id="e2d83-118">A következők funkciók nem lesznek elérhetők:</span><span class="sxs-lookup"><span data-stu-id="e2d83-118">The following functionality will be unavailable:</span></span>
<ul>
<li><span data-ttu-id="e2d83-119">Minden folyamatábra csak olvasható, és nem érhető el szerkesztésre.</span><span class="sxs-lookup"><span data-stu-id="e2d83-119">All flowcharts will be read-only and unavailable for editing.</span></span> <span data-ttu-id="e2d83-120">A folyamatábra-tevékenységekhez társított alakzattulajdonságok sem lesznek elérhetők.</span><span class="sxs-lookup"><span data-stu-id="e2d83-120">The shape properties that are associated with flowchart activities will also be unavailable.</span></span> <span data-ttu-id="e2d83-121">Ezek a folyamatábrák tartalmazzák továbbá az alapértelmezett folyamatábrákat, amelyek automatikusan létrejönnek és a testreszabott folyamatábrákat, amelyeket az alapértelmezett folyamatábrák alapján módosítottak.</span><span class="sxs-lookup"><span data-stu-id="e2d83-121">These flowcharts include both the default flowcharts that are automatically generated and customized flowcharts that are modified based on those default flowcharts.</span></span></li>
<li><span data-ttu-id="e2d83-122">A folyamat lépései csak olvashatók, és nem érhető el szerkesztésre.</span><span class="sxs-lookup"><span data-stu-id="e2d83-122">The process steps will be read-only and unavailable for editing.</span></span></li>     
<li><span data-ttu-id="e2d83-123">Az örökölt illeszkedés-/hiányelemzés nem lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="e2d83-123">The legacy fit/gap analysis feature will be unavailable.</span></span> <span data-ttu-id="e2d83-124">Ezért a program automatikusan nem hozhat létre vagy bocsájthat rendelkezésre exportáláshoz hiánylistát.</span><span class="sxs-lookup"><span data-stu-id="e2d83-124">Therefore, no gap list will be automatically created or available for export.</span></span>
<p><span data-ttu-id="e2d83-125"><strong>Megjegyzés:</strong> Ez a funkció korábban már elavult és helyébe a Microsoft Azure DevOps integrációk léptek.</span><span class="sxs-lookup"><span data-stu-id="e2d83-125"><strong>Note:</strong> This feature had previously been deprecated and replaced by Microsoft Azure DevOps integrations.</span></span></p>
</li>
<li><span data-ttu-id="e2d83-126">A folyamatábra verzióelőzményei nem lesznek elérhetők.</span><span class="sxs-lookup"><span data-stu-id="e2d83-126">The version history of the flowchart will be unavailable.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>
