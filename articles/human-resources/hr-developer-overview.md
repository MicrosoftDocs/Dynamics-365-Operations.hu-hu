---
title: Fejlesztés áttekintése
description: Ez a fejlesztői útmutató API és egyéni mezők hivatkozását tartalmazza. Tájékoztatást ad a többi alkalmazással való integrálásról is.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e67749e6f10b1c9202605b26164e30e5d39aa28
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793585"
---
# <a name="development-overview"></a><span data-ttu-id="b00c0-104">Fejlesztés áttekintése</span><span class="sxs-lookup"><span data-stu-id="b00c0-104">Development overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b00c0-105">Ez a fejlesztői útmutató API és egyéni mezők hivatkozását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b00c0-105">This Developer Guide provides an API and custom fields reference.</span></span> <span data-ttu-id="b00c0-106">Tájékoztatást ad a többi alkalmazással való integrálásról is.</span><span class="sxs-lookup"><span data-stu-id="b00c0-106">It also provides information on integrating with other apps.</span></span>

- [<span data-ttu-id="b00c0-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b00c0-107">Overview</span></span>](hr-developer-overview.md)

- [<span data-ttu-id="b00c0-108">Bővítés a Power Apps és a Power Automate szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="b00c0-108">Extend with Power Apps and Power Automate</span></span>](hr-developer-power-apps.md)

- [<span data-ttu-id="b00c0-109">Human Resources-entitások a Dataverse szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="b00c0-109">Human Resources entities in Dataverse</span></span>](hr-developer-entities.md)

- [<span data-ttu-id="b00c0-110">Egyéni mezők</span><span class="sxs-lookup"><span data-stu-id="b00c0-110">Custom fields</span></span>](hr-developer-custom-fields.md)

- <span data-ttu-id="b00c0-111">Adatintegráció beállítása</span><span class="sxs-lookup"><span data-stu-id="b00c0-111">Set up data integration</span></span>
  - [<span data-ttu-id="b00c0-112">Válasszon ki egy adatintegrációs technológiát</span><span class="sxs-lookup"><span data-stu-id="b00c0-112">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)
  - [<span data-ttu-id="b00c0-113">A Dataverse-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b00c0-113">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)
  - [<span data-ttu-id="b00c0-114">A Finance szolgáltatással való integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b00c0-114">Configure integration with Finance</span></span>](hr-admin-integration-finance.md)
  - [<span data-ttu-id="b00c0-115">A Dayforce szolgáltatással való integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b00c0-115">Configure integration with Dayforce</span></span>](hr-admin-integration-dayforce.md)
  - [<span data-ttu-id="b00c0-116">Ismétlődő adatexportálási alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="b00c0-116">Create a recurring data export app</span></span>](hr-admin-integration-recurring-data-export.md)
  - <span data-ttu-id="b00c0-117">Integráció az Office-szal</span><span class="sxs-lookup"><span data-stu-id="b00c0-117">Integrate with Office</span></span>
    - [<span data-ttu-id="b00c0-118">Office-integrációs oktatóanyag</span><span class="sxs-lookup"><span data-stu-id="b00c0-118">Office integration tutorial</span></span>](../dev-itpro/office-integration/office-integration-tutorial.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="b00c0-119">Entitás adatainak frissítése az Excel alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="b00c0-119">Update entity data in Excel</span></span>](../dev-itpro/office-integration/use-excel-add-in.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="b00c0-120">Az Excel programban történő megnyitási élmények létrehozása</span><span class="sxs-lookup"><span data-stu-id="b00c0-120">Create Open in Excel experiences</span></span>](../dev-itpro/office-integration/office-integration-edit-excel.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="b00c0-121">Office-integráció – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="b00c0-121">Troubleshoot Office integration</span></span>](../dev-itpro/office-integration/office-integration-troubleshooting.md?toc=/dynamics365/unified-operations/talent/toc.json)

- <span data-ttu-id="b00c0-122">Entitás API referenciája</span><span class="sxs-lookup"><span data-stu-id="b00c0-122">Entity API reference</span></span>
  - [<span data-ttu-id="b00c0-123">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="b00c0-123">Authentication</span></span>](hr-developer-api-authentication.md)
  - <span data-ttu-id="b00c0-124">Entitások</span><span class="sxs-lookup"><span data-stu-id="b00c0-124">Entities</span></span>
    - [<span data-ttu-id="b00c0-125">MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="b00c0-125">MyLeaveRequests</span></span>](hr-developer-api-myleaverequests-overview.md)
    - [<span data-ttu-id="b00c0-126">Szabadságkérelem elküldése munkafolyamathoz</span><span class="sxs-lookup"><span data-stu-id="b00c0-126">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)

## <a name="see-also"></a><span data-ttu-id="b00c0-127">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b00c0-127">See also</span></span>

- [<span data-ttu-id="b00c0-128">Új vagy módosult elemek a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="b00c0-128">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)
- [<span data-ttu-id="b00c0-129">Rendszergazdai útmutató</span><span class="sxs-lookup"><span data-stu-id="b00c0-129">Administrator Guide</span></span>](hr-admin-overview.md)
- [<span data-ttu-id="b00c0-130">Felhasználói útmutató</span><span class="sxs-lookup"><span data-stu-id="b00c0-130">User Guide</span></span>](hr-hrpro-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]