---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 1.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 92eb1508905309294e17b770829b1c5a22be1316
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304725"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-8-2018"></a><span data-ttu-id="ac36b-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 8.)</span><span class="sxs-lookup"><span data-stu-id="ac36b-103">What's new or changed in Dynamics 365 for Talent Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ac36b-104">**Build 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="ac36b-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="ac36b-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="ac36b-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="ac36b-106">Más használandó dátumok engedélyezése szabadság szintalap szerint (Szabadság kezelése)</span><span class="sxs-lookup"><span data-stu-id="ac36b-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="ac36b-107">Szabadság odaítélése során az alkalmazottakhoz, az odaítélési szintalap határozza meg, mennyi eltávozás lesz elhatárolva egy alkalmazotthoz</span><span class="sxs-lookup"><span data-stu-id="ac36b-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="ac36b-108">Jelenleg ezek a szintek az alkalmazott belépési dátumán és a szolgálati idő dátumán alapulnak.</span><span class="sxs-lookup"><span data-stu-id="ac36b-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="ac36b-109">Bizonyos esetekben a szervezeteknek szükséges, hogy ezek a szintek más dátumokon alapuljanak, mint az évforduló vagy eredeti felvételi dátuma.</span><span class="sxs-lookup"><span data-stu-id="ac36b-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="ac36b-110">Ezek a dátumok már szabadság terven használva vannak annak meghatározására, hogy mikor történnek az elhatárolások, az elhatárolt összeg meghatározásához immár használhatók ugyanezek a dátumok, amikor egy munkavállalót hozzáadnak egy tervhez.</span><span class="sxs-lookup"><span data-stu-id="ac36b-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="ac36b-111">Egyéb változtatások</span><span class="sxs-lookup"><span data-stu-id="ac36b-111">Other changes</span></span>
<span data-ttu-id="ac36b-112">Ez a verzió egyéb javításokat is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="ac36b-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="ac36b-113">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="ac36b-113">Known issue</span></span>

<span data-ttu-id="ac36b-114">**Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői.</span><span class="sxs-lookup"><span data-stu-id="ac36b-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="ac36b-115">Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek.</span><span class="sxs-lookup"><span data-stu-id="ac36b-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="ac36b-116">(Ezt a problémát kijavítjuk a következő platformfrissítéssel.)</span><span class="sxs-lookup"><span data-stu-id="ac36b-116">(This issue will be fixed in the next platform update.)</span></span>
