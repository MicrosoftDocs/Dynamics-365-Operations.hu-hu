---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. szeptember 17.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 213324f9074f88d9fdc8efdfa46bc3ed7817d1e8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "856807"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-17-2018"></a><span data-ttu-id="8baad-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. szeptember 17.)</span><span class="sxs-lookup"><span data-stu-id="8baad-103">What's new or changed in Dynamics 365 for Talent Core HR (September 17, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8baad-104">**Build 8.1.154.0**</span><span class="sxs-lookup"><span data-stu-id="8baad-104">**Build 8.1.154.0**</span></span>

<span data-ttu-id="8baad-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="8baad-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="leave-and-absence--accrue-time-based-on-hours-worked"></a><span data-ttu-id="8baad-106">Szabadság és távollét – Szabadság elhatárolása a ledolgozott órák alapján</span><span class="sxs-lookup"><span data-stu-id="8baad-106">Leave and Absence – Accrue time based on hours worked</span></span>

<span data-ttu-id="8baad-107">Új elhatárolási típus lett hozzáadva a Távollétcsomagokhoz.</span><span class="sxs-lookup"><span data-stu-id="8baad-107">A new accrual type has been added to Leave plans.</span></span> <span data-ttu-id="8baad-108">Az elhatárolási ütemezés mostantól alapulhat a szolgáltatás hónapjain vagy a ledolgozott órákon.</span><span class="sxs-lookup"><span data-stu-id="8baad-108">The accrual schedule can now be based on months of service or hours worked.</span></span> <span data-ttu-id="8baad-109">További tájékoztatásért lásd a [Szabadság elhatárolása a ledolgozott órák alapján](leave-accrue-hours-worked.md) című cikket.</span><span class="sxs-lookup"><span data-stu-id="8baad-109">For more information, see [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

## <a name="platform-update-18"></a><span data-ttu-id="8baad-110">18-es platformfrissítés</span><span class="sxs-lookup"><span data-stu-id="8baad-110">Platform update 18</span></span>

<span data-ttu-id="8baad-111">A 18-as platformfrissítés a Talent kiadásának részévé vált.</span><span class="sxs-lookup"><span data-stu-id="8baad-111">Platform update 18 is now part of the Talent release.</span></span> 

-   <span data-ttu-id="8baad-112">A kötelező és egyéb mezők személyre szabással elrejthetők.</span><span class="sxs-lookup"><span data-stu-id="8baad-112">Mandatory and other fields can be hidden via personalization.</span></span> <span data-ttu-id="8baad-113">Lehetővé teszi a felhasználó számára, hogy egyszerűsített élményt hozzon létre, ahol az üzleti logika által alapértelmezett kötelező mezők nem jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="8baad-113">This allows a user to create a simplified experience where mandatory fields that are defaulted by business logic are not shown.</span></span> <span data-ttu-id="8baad-114">A rejtett kötelező mezők ideiglenesen szintén láthatók, amennyiben üresek egy mentés megkísérlése során.</span><span class="sxs-lookup"><span data-stu-id="8baad-114">Hidden mandatory fields are also temporarily made visible if they are empty when a save is attempted.</span></span>

-   <span data-ttu-id="8baad-115">A 18-as platformfrissítéstől kezdődően a Talent webes ügyfele a Microsoft Fluent Design elemeihez igazítja a vizuális elemeket.</span><span class="sxs-lookup"><span data-stu-id="8baad-115">In Platform update 18, the Talent web client now aligns its visuals with Microsoft Fluent Design.</span></span>

    -   <span data-ttu-id="8baad-116">Amikor a mezők „olvasási módban” vannak, egyszerűen kiválaszthatja a szerkesztés beállítást a mezőkben az űrlap szerkesztésre való váltásához.</span><span class="sxs-lookup"><span data-stu-id="8baad-116">When fields are in “read mode”, you can simply select the edit option in the fields to switch the form to edit.</span></span>

    -   <span data-ttu-id="8baad-117">Módosítások a mezők olvasási módban való megjelenítésében.</span><span class="sxs-lookup"><span data-stu-id="8baad-117">Changes in how fields display when in read mode.</span></span>

    -   <span data-ttu-id="8baad-118">A munkaterületek és oldalak fejlécei félkövérek.</span><span class="sxs-lookup"><span data-stu-id="8baad-118">Headings in workspaces and pages are bold.</span></span>

-   <span data-ttu-id="8baad-119">A csere nélküli keresések viselkedését továbbfejlesztettük.</span><span class="sxs-lookup"><span data-stu-id="8baad-119">The behavior of non-replacing lookups has been improved.</span></span> <span data-ttu-id="8baad-120">Ha további információt szeretne, lásd a [Csere nélküli keresések továbbfejlesztett viselkedése](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fbusiness-applications-release-notes%2FOctober18%2Fdynamics365-finance-operations%2Fnon-replacing-lookups&data=02%7C01%7C%7Ce0b3b3bee47b4424aaa208d619ce86f2%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636724772137980342&sdata=RN1qjtZSLtS010zgs0KlcwFrrB8Z7uWWGtFjdxdaamg%3D&reserved=0) című cikket.</span><span class="sxs-lookup"><span data-stu-id="8baad-120">For more information, see [Improved behavior for non-replacing lookups](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fbusiness-applications-release-notes%2FOctober18%2Fdynamics365-finance-operations%2Fnon-replacing-lookups&data=02%7C01%7C%7Ce0b3b3bee47b4424aaa208d619ce86f2%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636724772137980342&sdata=RN1qjtZSLtS010zgs0KlcwFrrB8Z7uWWGtFjdxdaamg%3D&reserved=0).</span></span>

## <a name="bug-fixes"></a><span data-ttu-id="8baad-121">Hibajavítások</span><span class="sxs-lookup"><span data-stu-id="8baad-121">Bug fixes</span></span>

<span data-ttu-id="8baad-122">Ez a kiadás számos további hibajavítást tartalmaz, beleértve azt, hogy az ACA, ADA és I9 hivatkozásai mostantól csak az USA-beli vállalatok számára engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="8baad-122">This release includes several additional bug fixes, including references to ACA, ADA, and I9 now will only be enabled in US companies.</span></span>
