---
title: Munkafolyamat GYIK
description: Ez a témakör a munkafolyamat-rendszerrel kapcsolatos gyakori kérdéseket tartalmazza.
author: ChrisGarty
manager: AnnBe
ms.date: 06/19/2019
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
ms.openlocfilehash: 0188e8ed3cbbfd7dbccd7d13cf6129e146a919ac
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772697"
---
# <a name="workflow-faq"></a><span data-ttu-id="88a13-103">Munkafolyamat GYIK</span><span class="sxs-lookup"><span data-stu-id="88a13-103">Workflow FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88a13-104">Ez a témakör a munkafolyamat-rendszerrel kapcsolatos gyakori kérdéseket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="88a13-104">This topic answers frequently asked questions about the workflow system.</span></span>

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="88a13-105">Miért érkeznik a több értesítés egy munkaelem elutasítása esetén?</span><span class="sxs-lookup"><span data-stu-id="88a13-105">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="88a13-106">Egy munkaelem elutasításakor, a munkatétel elutasítottként lesz befejezve.</span><span class="sxs-lookup"><span data-stu-id="88a13-106">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="88a13-107">Egy másik munkatétel lesz létrehozva és kiosztva a létrehozónak.</span><span class="sxs-lookup"><span data-stu-id="88a13-107">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="88a13-108">Ez azt jelenti, hogy van egy értesítés az elutasított munka létrehozójának, és egy külön értesítés az új „módosítás kérése” munkaelemhez hozzárendelt felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="88a13-108">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="88a13-109">Minden értesítés egy másik meunelemhez tartozik, de a hasonlóság megtévesztő lehet.</span><span class="sxs-lookup"><span data-stu-id="88a13-109">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="88a13-110">Tervezzük ennek fejlesztését egy későbbi kiadásban.</span><span class="sxs-lookup"><span data-stu-id="88a13-110">We are looking at ways to improve this in a future release.</span></span>

## <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="88a13-111">Miért nem sikerülnek a munkafolyamat-exportálásaim?</span><span class="sxs-lookup"><span data-stu-id="88a13-111">Why are my workflow exports failing?</span></span>
<span data-ttu-id="88a13-112">A munkafolyamat-exportálási funkcióra jelenleg korlátozás vonatkozik, amely megakadályozza, hogy a munkafolyamatok nevei túllépjék a 48 karaktert.</span><span class="sxs-lookup"><span data-stu-id="88a13-112">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="88a13-113">Ha egy 48 karakternél hosszabb nevet használ, a „Kiszolgáló nem tudta hitelesíteni a kérelmet” hibát kap és/vagy nem lehetséges a fájlok fájltípus nélküli exportálása.</span><span class="sxs-lookup"><span data-stu-id="88a13-113">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="88a13-114">A következő blogbejegyzés további részleteket nyújt: [Munkafolyamat exportálása](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="88a13-114">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a><span data-ttu-id="88a13-115">A munkafolyamat elküldője is jóváhagyhatja a munkafolyamatot?</span><span class="sxs-lookup"><span data-stu-id="88a13-115">Can the submitter of a workflow also approve the workflow?</span></span>
<span data-ttu-id="88a13-116">Igen, ha így van beállítva, akkor a munkafolyamat elküldője is jóváhagyhatja a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="88a13-116">Yes, a submitter of a workflow can also approve the workflow if it is configured that way.</span></span> <span data-ttu-id="88a13-117">Ennek a viselkedésnek a megelőzése érdekében adja meg a **Munkafolyamat-paraméterek > Általános > Jóváhagyó > Beküldő általi jóváhagyás tiltása** beállításhoz az **Igen** értéket.</span><span class="sxs-lookup"><span data-stu-id="88a13-117">To prevent this behavior, set **Workflow parameters > General > Approver > Disallow approval by submitter** to **Yes**.</span></span>

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a><span data-ttu-id="88a13-118">Hozzáadhatok olyan figyelmeztetéseket a munkafolyamatokhoz, amelyek értesítik a felhasználókat?</span><span class="sxs-lookup"><span data-stu-id="88a13-118">Can I add alerts to workflows to provide notifications to users?</span></span>
<span data-ttu-id="88a13-119">Az alábbiakban az értesítésre szolgáló figyelmeztetések munkafolyamatokhoz való hozzáadásáról olvashat néhány alapvető részletet:</span><span class="sxs-lookup"><span data-stu-id="88a13-119">Here are a few key areas to note about adding alerts to workflows to provide notifications:</span></span>
- <span data-ttu-id="88a13-120">A figyelmeztetések és a munkafolyamat-értesítési mechanizmusok összehasonlítása</span><span class="sxs-lookup"><span data-stu-id="88a13-120">Alerts versus workflow notification mechanisms</span></span>
    - <span data-ttu-id="88a13-121">A figyelmeztetések beállíthatók a rekordok változásaihoz.</span><span class="sxs-lookup"><span data-stu-id="88a13-121">Alerts can be set up for record changes.</span></span> <span data-ttu-id="88a13-122">A munkafolyamatok során módosulnak a rekordok, így beállítható a rekord munkafolyamat által okozott módosításával kapcsolatos figyelmeztetés.</span><span class="sxs-lookup"><span data-stu-id="88a13-122">Workflows change records, so it's possible to set up an alert related to a record change caused by a workflow.</span></span> <span data-ttu-id="88a13-123">Mivel azonban a munkafolyamatok eltérő értesítési beállításokat használnak, a figyelmeztetések használata nem a legjobb megoldás.</span><span class="sxs-lookup"><span data-stu-id="88a13-123">However, because workflows have different built-in notification options, using alerts isn’t ideal.</span></span>
- <span data-ttu-id="88a13-124">A munkafolyamatok normál értesítései</span><span class="sxs-lookup"><span data-stu-id="88a13-124">Standard notifications from workflows</span></span> 
    - <span data-ttu-id="88a13-125">A munkafolyamatok rendelkeznek beépített e-mail-értesítésekkel.</span><span class="sxs-lookup"><span data-stu-id="88a13-125">Workflows have built in email notifications.</span></span> <span data-ttu-id="88a13-126">A vevő beállíthatja, hogy a felhasználók e-mailben kapjanak értesítéseket.</span><span class="sxs-lookup"><span data-stu-id="88a13-126">A customer can configure the notifications so that the users are sent emails.</span></span> <span data-ttu-id="88a13-127">Az ilyen értesítések esetében a felhasználók nem kapnak üzenetet a Műveleti központból.</span><span class="sxs-lookup"><span data-stu-id="88a13-127">Those notifications don’t result in Action Center messages for users.</span></span>
    - <span data-ttu-id="88a13-128">Egy jövőbeli frissítésben bevezetjük a Műveleti központ üzenetét, így a felhasználóhoz egy munkafolyamat munkatételét lehet hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="88a13-128">In a future update we will be adding an Action Center message so a user is assigned a workflow work item.</span></span> 
- <span data-ttu-id="88a13-129">Értesítések hozzáadása a munkafolyamatokhoz</span><span class="sxs-lookup"><span data-stu-id="88a13-129">Adding notifications to workflows</span></span>
    - <span data-ttu-id="88a13-130">A Műveleti központ üzeneteivel adott felhasználók is megcélozhatók, például az X++ munkafolyamatból létrehozott üzenetekkel.</span><span class="sxs-lookup"><span data-stu-id="88a13-130">Action Center messages can be created for specific users, such as a message created from a workflow in X++.</span></span>
    - <span data-ttu-id="88a13-131">[Üzleti események munkafolyamatai](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow), amelyekkel a vevő a kívánt értesítést használható folyamatokat aktiválhatja.</span><span class="sxs-lookup"><span data-stu-id="88a13-131">[Workflows have Business Events](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) that the customer could use to trigger Flows have the notifications that they are looking for.</span></span>   

<span data-ttu-id="88a13-132">Összefoglalva, ha a felhasználó nem a megfelelő értesítést kapja a Műveleti központból, amikor hozzárendelik a munkafolyamat egyik munkatételét, a [Munkafolyamat üzleti eseményeinek](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) Microsoft Power Automate szolgáltatással való használatával további vagy más értesítések válhatnak elérhetővé.</span><span class="sxs-lookup"><span data-stu-id="88a13-132">In summary, if a user does not get the proper notification from the Action Center when they are assigned a workflow work item, then leverage [Workflow Business Events](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) with Microsoft Power Automate to provide additional or different notifications.</span></span>
