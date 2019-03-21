---
title: Munkafolyamat GYIK
description: Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/01/2019
ms.locfileid: "773213"
---
# <a name="workflow-system"></a><span data-ttu-id="b7667-103">Munkafolyamat-rendszer</span><span class="sxs-lookup"><span data-stu-id="b7667-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7667-104">Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b7667-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="b7667-105">Értesítések</span><span class="sxs-lookup"><span data-stu-id="b7667-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="b7667-106">Miért érkeznik a több értesítés egy munkaelem elutasítása esetén?</span><span class="sxs-lookup"><span data-stu-id="b7667-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="b7667-107">Egy munkaelem elutasításakor, a munkatétel elutasítottként lesz befejezve.</span><span class="sxs-lookup"><span data-stu-id="b7667-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="b7667-108">Egy másik munkatétel lesz létrehozva és kiosztva a létrehozónak.</span><span class="sxs-lookup"><span data-stu-id="b7667-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="b7667-109">Ez azt jelenti, hogy van egy értesítés az elutasított munka létrehozójának, és egy külön értesítés az új „módosítás kérése” munkaelemhez hozzárendelt felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="b7667-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="b7667-110">Minden értesítés egy másik meunelemhez tartozik, de a hasonlóság megtévesztő lehet.</span><span class="sxs-lookup"><span data-stu-id="b7667-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="b7667-111">Tervezzük ennek fejlesztését egy későbbi kiadásban.</span><span class="sxs-lookup"><span data-stu-id="b7667-111">We are looking at ways to improve this in a future release.</span></span>
