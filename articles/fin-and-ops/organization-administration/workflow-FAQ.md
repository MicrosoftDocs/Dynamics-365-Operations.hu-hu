---
title: Munkafolyamat GYIK
description: Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509291"
---
# <a name="workflow-system"></a><span data-ttu-id="4d756-103">Munkafolyamat-rendszer</span><span class="sxs-lookup"><span data-stu-id="4d756-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d756-104">Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4d756-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="4d756-105">Értesítések</span><span class="sxs-lookup"><span data-stu-id="4d756-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="4d756-106">Miért érkeznik a több értesítés egy munkaelem elutasítása esetén?</span><span class="sxs-lookup"><span data-stu-id="4d756-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="4d756-107">Egy munkaelem elutasításakor, a munkatétel elutasítottként lesz befejezve.</span><span class="sxs-lookup"><span data-stu-id="4d756-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="4d756-108">Egy másik munkatétel lesz létrehozva és kiosztva a létrehozónak.</span><span class="sxs-lookup"><span data-stu-id="4d756-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="4d756-109">Ez azt jelenti, hogy van egy értesítés az elutasított munka létrehozójának, és egy külön értesítés az új „módosítás kérése” munkaelemhez hozzárendelt felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="4d756-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="4d756-110">Minden értesítés egy másik meunelemhez tartozik, de a hasonlóság megtévesztő lehet.</span><span class="sxs-lookup"><span data-stu-id="4d756-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="4d756-111">Tervezzük ennek fejlesztését egy későbbi kiadásban.</span><span class="sxs-lookup"><span data-stu-id="4d756-111">We are looking at ways to improve this in a future release.</span></span>

### <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="4d756-112">Miért nem sikerülnek a munkafolyamat-exportálásaim?</span><span class="sxs-lookup"><span data-stu-id="4d756-112">Why are my workflow exports failing?</span></span>
<span data-ttu-id="4d756-113">A munkafolyamat-exportálási funkcióra jelenleg korlátozás vonatkozik, amely megakadályozza, hogy a munkafolyamatok nevei túllépjék a 48 karaktert.</span><span class="sxs-lookup"><span data-stu-id="4d756-113">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="4d756-114">Ha egy 48 karakternél hosszabb nevet használ, a „Kiszolgáló nem tudta hitelesíteni a kérelmet” hibát kap és/vagy nem lehetséges a fájlok fájltípus nélküli exportálása.</span><span class="sxs-lookup"><span data-stu-id="4d756-114">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="4d756-115">A következő blogbejegyzés további részleteket nyújt: [Munkafolyamat exportálása](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="4d756-115">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>
