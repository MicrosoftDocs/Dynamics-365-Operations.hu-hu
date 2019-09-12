---
title: Preferált karbantartási dolgozók beállítása
description: Ez a témakör azt mutatja be, hogyan lehet előnyben részesített karbantartási dolgozókat beállítani az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887411"
---
# <a name="preferred-maintenance-workers"></a><span data-ttu-id="a5bb5-103">Preferált karbantartási dolgozók</span><span class="sxs-lookup"><span data-stu-id="a5bb5-103">Preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="a5bb5-104">Lehetőség van arra, hogy megadja, melyik karbantartási dolgozókat szeretné előnyben részesíteni, amikor a program a munkarendelés ütemezésekor kiosztja a dolgozókat a munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-104">You can make a preference regarding which maintenance workers are allocated to complete work orders during work order scheduling.</span></span> <span data-ttu-id="a5bb5-105">A funkció használata nem kötelező, de a dolgozó tudásának és szakértelme alapján a legalkalmasabb karbantartási dolgozót tudja kiválasztani egy feladatra.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="a5bb5-106">Így a munkarendelés ütemezése során a **Preferált karbantartási dolgozók** beállítás határozza meg, hogy egy adott karbantartási dolgozót vagy dolgozói csoportot ütemezzen-e a rendszer egy munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-106">Therefore, during work order scheduling, the setup in **Preferred maintenance workers** is used to determine if a specific maintenance worker or worker group should be scheduled for a work order.</span></span> <span data-ttu-id="a5bb5-107">A program csak az ütemezés időpontban rendelkezésre álló karbantartási dolgozókat ütemezi.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-107">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="a5bb5-108">Ha egy előnyben részesített karbantartási dolgozó beállítása egyezik egy munkarendeléssel az ütemezés során, de a karbantartási dolgozó más feladatokra van beosztva, akkor a munkarendelést egy másik, rendelkezésre álló karbantartási dolgozó fogja megkapni.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-108">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another, available, maintenance worker.</span></span>

<span data-ttu-id="a5bb5-109">Az előnyben részesített karbantartási dolgozók beállítása előtt be kell állítania a kiválasztható karbantartási dolgozókat és dolgozói csoportokat.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-109">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups that should be available for selection.</span></span> <span data-ttu-id="a5bb5-110">A karbantartási dolgozók és dolgozói csoportok beállításáról a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című cikkben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-110">Refer to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md) for a description on how to set up maintenance workers and worker groups.</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="a5bb5-111">Előnyben részesített dolgozók beállítása</span><span class="sxs-lookup"><span data-stu-id="a5bb5-111">Set up preferred workers</span></span>

<span data-ttu-id="a5bb5-112">A preferált karbantartási dolgozók vagy dolgozói csoportok kapcsolódhatnak a következőhöz:</span><span class="sxs-lookup"><span data-stu-id="a5bb5-112">A preferred maintenance worker or worker group can be related to a specific</span></span>

- <span data-ttu-id="a5bb5-113">kereskedelem</span><span class="sxs-lookup"><span data-stu-id="a5bb5-113">trade</span></span>  
- <span data-ttu-id="a5bb5-114">karbantartási feladattípus változata</span><span class="sxs-lookup"><span data-stu-id="a5bb5-114">maintenance job type variant</span></span>  
- <span data-ttu-id="a5bb5-115">karbantartási feladat típusa</span><span class="sxs-lookup"><span data-stu-id="a5bb5-115">maintenance job type</span></span>  
- <span data-ttu-id="a5bb5-116">karbantartási feladattípus kategóriája</span><span class="sxs-lookup"><span data-stu-id="a5bb5-116">maintenance job type category</span></span>  
- <span data-ttu-id="a5bb5-117">eszköz</span><span class="sxs-lookup"><span data-stu-id="a5bb5-117">asset</span></span>  
- <span data-ttu-id="a5bb5-118">eszköztípus</span><span class="sxs-lookup"><span data-stu-id="a5bb5-118">asset type</span></span>  

<span data-ttu-id="a5bb5-119">vagy a kiválasztottak kombinációja.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-119">or a combination of those selections.</span></span> <span data-ttu-id="a5bb5-120">Minél több lehetőséget választ ki egy rekordhoz, annál konkrétabb lesz a beállítás.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-120">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="a5bb5-121">Kattintson az **Eszközkezelés** > **Beállítások** > **Dolgozók** > **Preferált karbantartási dolgozók** elemre.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-121">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="a5bb5-122">Hozzon létre egy új rekordot az **Új** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-122">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="a5bb5-123">Először hozzon létre egy olyan „alapértelmezett” karbantartási dolgozót vagy dolgozói csoportot, amely nincs kijelölve a fenti listán.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-123">Start by creating a "default" maintenance worker or worker group setup that has no selections in the fields shown in the bullet list above.</span></span> <span data-ttu-id="a5bb5-124">Ez azt jelenti, hogy csak a **Preferált karbantartási dolgozói csoport** vagy a **Preferált karbantartási dolgozó** mezőben lett kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-124">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="a5bb5-125">Az alábbi ábrán egy példa látható az első rekordra, amelyben a „Kérések” lett kijelölve preferált karbantartási dolgozói csoportként.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-125">In the figure below, you see an example in the first record in which "Requests" is selected as preferred maintenance worker group.</span></span>

>[!NOTE]
><span data-ttu-id="a5bb5-126">A program ezt az alapértelmezett beállítást használja a munkarendelés-ütemezés során, ha a munkarendelés ütemezése során nincs más, konkrétabb kombináció, amely jobban megfelel a munkarendelés tartalmának.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-126">The default setup will be used during work order scheduling in case no other, more specific, combination matches the contents of the work order during work order scheduling.</span></span>

4. <span data-ttu-id="a5bb5-127">Új rekord létrehozásához ismételje meg a 2. lépést.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-127">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="a5bb5-128">A preferált dolgozótól vagy dolgozó csoporttól függően válassza ki a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-128">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> <span data-ttu-id="a5bb5-129">*Példa:* Az alábbi ábrán, a hatodik rekordban, Shawn Richardson karbantartási dolgozó van kiválasztva preferált dolgozóként.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-129">*Example:* In the figure below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="a5bb5-130">Ha az ütemezés időpontjában szabad, a CH-BP1-03-02 eszközt és a „Létesítményértékelés” típusú karbantartás feladatot tartalmazó munkarendelés ütemezése során automatikusan ki lesz választva.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-130">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintennace job type "Facility assessment", if he is available at the scheduled time.</span></span>

>[!NOTE]
><span data-ttu-id="a5bb5-131">Általában amikor a munkarendelés ütemezésekor egy preferált karbantartási dolgozó lesz kiválasztva, az Eszközkezelés ellenőrzi a **Preferált karbantartási dolgozók** rekordokban az esetleges egyezéseket. A rendszer a legkonkrétabb kombinációt ellenőrzi elsőként.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-131">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="a5bb5-132">Ha nem talál egyezést, akkor az olyan „alapértelmezett” rekordot használja, amelyik meg lett adva a **Preferált karbantartási dolgozói csoport** vagy a **Preferált karbantartási dolgozó** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-132">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>


![1. ábra](media/02-work-order-scheduling.png)

<span data-ttu-id="a5bb5-134">Beállíthat felelős karbantartási dolgozókat is, akiket ki lehet választani egy karbantartási kérés vagy munkarendelés létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-134">You can also set up responsible maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="a5bb5-135">Az **Összes munkarendelés** és az **Összes karbantartási kérés** részen szükség szerint módosíthatja a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-135">In **All work orders** and **All maintenance requests**, you can edit the selection, if required.</span></span> <span data-ttu-id="a5bb5-136">További információ: [Felelős karbantartási dolgozók](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="a5bb5-136">Refer to [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md) for more information.</span></span>

<span data-ttu-id="a5bb5-137">A munkarendelés ütemezése során a program különböző pontszámokat számít ki annak meghatározására, hogy melyik dolgozók kapják a munkarendeléshez kapcsolódó feladatokat (ezeket a pontszámokat az **Eszközkezelés paraméterei** > **Munkarendelés ütemezése** hivatkozásra kattintva tekintheti meg).</span><span class="sxs-lookup"><span data-stu-id="a5bb5-137">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="a5bb5-138">Ha a munkarendelés ütemezése során több preferált karbantartási dolgozó vagy felelős karbantartási dolgozó kap ugyanakkora pontszámot, akkor a rendszer véletlenszerűen választ.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-138">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="a5bb5-139">Ellenkező mindig a legmagasabb pontszámú dolgozó lesz hozzárendelve a munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="a5bb5-139">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

