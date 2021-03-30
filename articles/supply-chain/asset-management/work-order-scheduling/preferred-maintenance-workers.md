---
title: Preferált karbantartási dolgozók beállítása
description: Ez a témakör azt mutatja be, hogyan lehet előnyben részesített karbantartási dolgozókat beállítani az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 102f48d1273ac91d5cb42eca11d2dec337c30528
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214962"
---
# <a name="set-up-preferred-maintenance-workers"></a><span data-ttu-id="178e3-103">Preferált karbantartási dolgozók beállítása</span><span class="sxs-lookup"><span data-stu-id="178e3-103">Set up preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="178e3-104">Amikor a program a munkarendelés ütemezésekor kiosztja a dolgozókat a munkarendeléshez lehetőség van arra, hogy megadja, melyik karbantartási dolgozót vagy dolgozócsoportot szeretné előnyben részesíteni.</span><span class="sxs-lookup"><span data-stu-id="178e3-104">During work order scheduling, you can make a preference regarding which maintenance worker or worker group is allocated to complete the work order.</span></span> <span data-ttu-id="178e3-105">A funkció használata nem kötelező, de a dolgozó tudásának és szakértelme alapján a legalkalmasabb karbantartási dolgozót tudja kiválasztani egy feladatra.</span><span class="sxs-lookup"><span data-stu-id="178e3-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="178e3-106">A program csak az ütemezés időpontban rendelkezésre álló karbantartási dolgozókat ütemezi.</span><span class="sxs-lookup"><span data-stu-id="178e3-106">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="178e3-107">Ha egy előnyben részesített karbantartási dolgozó beállítása egyezik egy munkarendeléssel az ütemezés során, de a karbantartási dolgozó más feladatokra van beosztva, akkor a munkarendelést egy másik, rendelkezésre álló karbantartási dolgozó fogja megkapni.</span><span class="sxs-lookup"><span data-stu-id="178e3-107">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another available maintenance worker.</span></span>

<span data-ttu-id="178e3-108">Mielőtt beállítja a karbantartási dolgozókat, először be kell állítania a karbantartási dolgozókat és a dolgozói csoportokat.</span><span class="sxs-lookup"><span data-stu-id="178e3-108">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups.</span></span> <span data-ttu-id="178e3-109">A karbantartási dolgozók és dolgozói csoportok beállításával kapcsolatosan a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című cikkben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="178e3-109">For a description about how to set up maintenance workers and worker groups, see to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="178e3-110">Előnyben részesített dolgozók beállítása</span><span class="sxs-lookup"><span data-stu-id="178e3-110">Set up preferred workers</span></span>

<span data-ttu-id="178e3-111">A preferált karbantartási dolgozók vagy dolgozói csoportok kapcsolódhatnak következők közül egyhez vagy többhöz:</span><span class="sxs-lookup"><span data-stu-id="178e3-111">A preferred maintenance worker or worker group can be related to one or more of the following:</span></span>

- <span data-ttu-id="178e3-112">kereskedelem</span><span class="sxs-lookup"><span data-stu-id="178e3-112">trade</span></span>  
- <span data-ttu-id="178e3-113">karbantartási feladattípus változata</span><span class="sxs-lookup"><span data-stu-id="178e3-113">maintenance job type variant</span></span>  
- <span data-ttu-id="178e3-114">karbantartási feladat típusa</span><span class="sxs-lookup"><span data-stu-id="178e3-114">maintenance job type</span></span>  
- <span data-ttu-id="178e3-115">karbantartási feladattípus kategóriája</span><span class="sxs-lookup"><span data-stu-id="178e3-115">maintenance job type category</span></span>  
- <span data-ttu-id="178e3-116">eszköz</span><span class="sxs-lookup"><span data-stu-id="178e3-116">asset</span></span>  
- <span data-ttu-id="178e3-117">eszköztípus</span><span class="sxs-lookup"><span data-stu-id="178e3-117">asset type</span></span>  

<span data-ttu-id="178e3-118">Minél több lehetőséget választ ki egy rekordhoz, annál konkrétabb lesz a beállítás.</span><span class="sxs-lookup"><span data-stu-id="178e3-118">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="178e3-119">Kattintson az **Eszközkezelés** > **Beállítások** > **Dolgozók** > **Preferált karbantartási dolgozók** elemre.</span><span class="sxs-lookup"><span data-stu-id="178e3-119">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="178e3-120">Hozzon létre egy új rekordot az **Új** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="178e3-120">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="178e3-121">Kezdjen egy „alapértelmezett” karbantartási dolgozói vagy dolgozói csoport létrehozásával.</span><span class="sxs-lookup"><span data-stu-id="178e3-121">Start by creating a "default" maintenance worker or worker group.</span></span> <span data-ttu-id="178e3-122">Ez azt jelenti, hogy csak a **Preferált karbantartási dolgozói csoport** vagy a **Preferált karbantartási dolgozó** mezőben lett kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="178e3-122">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="178e3-123">Az alábbi képernyőfotón egy példa látható az első rekordra, amelyben a „Kérések” lett kijelölve **Preferált karbantartási dolgozói csoportként**.</span><span class="sxs-lookup"><span data-stu-id="178e3-123">In the screenshot below, you see an example in the first record in which "Requests" is selected as **Preferred maintenance worker group**.</span></span>

    [!NOTE] <span data-ttu-id="178e3-124">A program az alapértelmezett beállítást használja a munkarendelés-ütemezés során, ha nincs más konkrétabb kombináció, amely jobban megfelel a munkarendelés tartalmának.</span><span class="sxs-lookup"><span data-stu-id="178e3-124">The default setup will be used during work order scheduling if no other, more specific, combination matches the contents of the work order.</span></span>

4. <span data-ttu-id="178e3-125">Új rekord létrehozásához ismételje meg a 2. lépést.</span><span class="sxs-lookup"><span data-stu-id="178e3-125">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="178e3-126">A preferált dolgozótól vagy dolgozó csoporttól függően válassza ki a kívánt beállításokat.</span><span class="sxs-lookup"><span data-stu-id="178e3-126">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> 

    <span data-ttu-id="178e3-127">*Példa:* Az alábbi képernyőfotón, a hatodik rekordban, Shawn Richardson karbantartási dolgozó van kiválasztva preferált dolgozóként.</span><span class="sxs-lookup"><span data-stu-id="178e3-127">*Example:* In the screenshot below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="178e3-128">Ha az ütemezés időpontjában szabad, a CH-BP1-03-02 eszközt és a „Létesítményértékelés” típusú karbantartás feladattípust tartalmazó munkarendelés ütemezése során automatikusan ki lesz választva.</span><span class="sxs-lookup"><span data-stu-id="178e3-128">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintenance job type "Facility assessment", if he is available at the scheduled time.</span></span>

    [!NOTE] <span data-ttu-id="178e3-129">Általában amikor a munkarendelés ütemezésekor egy preferált karbantartási dolgozó lesz kiválasztva, az Eszközkezelés ellenőrzi a **Preferált karbantartási dolgozók** rekordokban az esetleges egyezéseket. A rendszer a legkonkrétabb kombinációt ellenőrzi elsőként.</span><span class="sxs-lookup"><span data-stu-id="178e3-129">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="178e3-130">Ha nem talál egyezést, akkor az olyan „alapértelmezett” rekordot használja, amelyik meg lett adva a **Preferált karbantartási dolgozói csoport** vagy a **Preferált karbantartási dolgozó** mezőben.</span><span class="sxs-lookup"><span data-stu-id="178e3-130">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>

![1. ábra](media/02-work-order-scheduling.png)

<span data-ttu-id="178e3-132">Beállíthat *felelős* karbantartási dolgozókat is, akiket ki lehet választani egy karbantartási kérés vagy munkarendelés létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="178e3-132">You can also set up *responsible* maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="178e3-133">Az **Összes munkarendelés** és az **Összes karbantartási kérés** részen szükség szerint szerkesztheti a kijelölést.</span><span class="sxs-lookup"><span data-stu-id="178e3-133">You can edit the selection in **All work orders** and **All maintenance requests**, if required.</span></span> <span data-ttu-id="178e3-134">További információért lásd: [Felelős karbantartási dolgozók](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="178e3-134">For more information, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

<span data-ttu-id="178e3-135">A munkarendelés ütemezése során a program különböző pontszámokat számít ki annak meghatározására, hogy melyik dolgozók kapják a munkarendeléshez kapcsolódó feladatokat (ezeket a pontszámokat az **Eszközkezelés paraméterei** > **Munkarendelés ütemezése** hivatkozásra kattintva tekintheti meg).</span><span class="sxs-lookup"><span data-stu-id="178e3-135">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="178e3-136">Ha a munkarendelés ütemezése során több preferált karbantartási dolgozó vagy felelős karbantartási dolgozó kap ugyanakkora pontszámot, akkor a rendszer véletlenszerűen választ.</span><span class="sxs-lookup"><span data-stu-id="178e3-136">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="178e3-137">Ellenkező mindig a legmagasabb pontszámú dolgozó lesz hozzárendelve a munkarendeléshez.</span><span class="sxs-lookup"><span data-stu-id="178e3-137">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]