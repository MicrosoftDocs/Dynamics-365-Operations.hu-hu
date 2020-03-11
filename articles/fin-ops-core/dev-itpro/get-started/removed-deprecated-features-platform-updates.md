---
title: Eltávolított vagy elavult Platform-funkciók
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087883"
---
# <a name="removed-or-deprecated-platform-features"></a><span data-ttu-id="62c74-103">Eltávolított vagy elavult Platform-funkciók</span><span class="sxs-lookup"><span data-stu-id="62c74-103">Removed or deprecated platform features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62c74-104">Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.</span><span class="sxs-lookup"><span data-stu-id="62c74-104">This topic describes features that have been removed, or that are planned for removal in platform updates of Finance and Operations apps.</span></span>

- <span data-ttu-id="62c74-105">Az *eltávolított* szolgáltatások már nem érhetők el a termékben.</span><span class="sxs-lookup"><span data-stu-id="62c74-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="62c74-106">Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.</span><span class="sxs-lookup"><span data-stu-id="62c74-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="62c74-107">Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.</span><span class="sxs-lookup"><span data-stu-id="62c74-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="62c74-108">A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat.</span><span class="sxs-lookup"><span data-stu-id="62c74-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="62c74-109">Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.</span><span class="sxs-lookup"><span data-stu-id="62c74-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="62c74-110">32-as platformfrissítés</span><span class="sxs-lookup"><span data-stu-id="62c74-110">Platform update 32</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="62c74-111">A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát</span><span class="sxs-lookup"><span data-stu-id="62c74-111">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="62c74-112">**Elavulás/eltávolítás oka**</span><span class="sxs-lookup"><span data-stu-id="62c74-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="62c74-113">Ez biztonsági hiba volt, mert a módosítási kérelmet nem szándékolt felhasználó számára is lehetett elküldeni.</span><span class="sxs-lookup"><span data-stu-id="62c74-113">This was a security issue because the request for change could be sent to an unintended user.</span></span> <span data-ttu-id="62c74-114">Ez egy használhatósági probléma is volt, mivel a felhasználó rá volt kényszerítve, hogy meghatározza, hogy ki volt a kezdeményező, és manuálisan ki kellet jelölnie.</span><span class="sxs-lookup"><span data-stu-id="62c74-114">This was also a usability issue because it forced the user to determine who the workflow originator was and manually select them.</span></span>  |
| <span data-ttu-id="62c74-115">**Felváltotta másik szolgáltatás?**</span><span class="sxs-lookup"><span data-stu-id="62c74-115">**Replaced by another feature?**</span></span>   | <span data-ttu-id="62c74-116">Nem</span><span class="sxs-lookup"><span data-stu-id="62c74-116">No</span></span> |
| <span data-ttu-id="62c74-117">**Érintett területek**</span><span class="sxs-lookup"><span data-stu-id="62c74-117">**Product areas affected**</span></span>         | <span data-ttu-id="62c74-118">Munkafolyamat</span><span class="sxs-lookup"><span data-stu-id="62c74-118">Workflow</span></span> |
| <span data-ttu-id="62c74-119">**Telepítési beállítás**</span><span class="sxs-lookup"><span data-stu-id="62c74-119">**Deployment option**</span></span>              | <span data-ttu-id="62c74-120">Összes</span><span class="sxs-lookup"><span data-stu-id="62c74-120">All</span></span> |
| <span data-ttu-id="62c74-121">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="62c74-121">**Status**</span></span>                         | <span data-ttu-id="62c74-122">A felhasználó kiválasztása legördülő lista el lett távolítva a 32-es platformfrissítésben.</span><span class="sxs-lookup"><span data-stu-id="62c74-122">The user selection drop-down list was removed from the request change dialog box in Platform update 32.</span></span> <span data-ttu-id="62c74-123">A módosítási kérelmeket a program automatikusan elküldi a létrehozónak, a szándéknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="62c74-123">Request change requests will be automatically sent to the originator as intended.</span></span> <span data-ttu-id="62c74-124">A funkciókkal kapcsolatos további tudnivalókat lásd: [Munkafolyamat-jóváhagyási folyamatok műveletei](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span><span class="sxs-lookup"><span data-stu-id="62c74-124">For more information about this functionality, see [Actions in workflow approval processes](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="62c74-125">Korábbi bejelentések az eltávolított vagy elavult funkciókról</span><span class="sxs-lookup"><span data-stu-id="62c74-125">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="62c74-126">További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="62c74-126">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../migration-upgrade/deprecated-features.md).</span></span>

