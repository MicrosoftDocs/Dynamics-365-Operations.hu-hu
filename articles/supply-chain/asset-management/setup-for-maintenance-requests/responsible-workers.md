---
title: Felelős karbantartási dolgozók
description: Ez a témakör azt mutatja be, hogyan lehet felelős karbantartási dolgozókat beállítani az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 113ee2b45c569c7dae3609f1027e31c4e5e5c54a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429628"
---
# <a name="responsible-maintenance-workers"></a><span data-ttu-id="5fd1b-103">Felelős karbantartási dolgozók</span><span class="sxs-lookup"><span data-stu-id="5fd1b-103">Responsible maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="5fd1b-104">A felelős karbantartási dolgozók eszköztípusokhoz, eszközökhöz, munkavégzési helyszínekhez, karbantartási feladat típusának kategóriáihoz, karbantartási feladatok típusaihoz, karbantartási feladat típusának változataihoz és ügyletekhez egyaránt kapcsolódhatnak.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-104">Responsible maintenance workers can be related to asset types, assets, functional locations, maintenance job type categories, maintenance job types, maintenance job type variants, and trades.</span></span> <span data-ttu-id="5fd1b-105">Feltüntethetők a munkarendeléseken és a karbantartási kérelmeken annak jelzésére, hogy kik azok az előnyben részesített karbantartási dolgozók, akiket a munkarendeléshez célszerű rendelni.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-105">They can be used on work orders and maintenance requests to indicate a preference about the maintenance workers who should be responsible for a work order.</span></span> <span data-ttu-id="5fd1b-106">(Ezek a karbantartási dolgozók azonban nem feltétlenül egyeznek meg azokkal, akiket a munkarendelés elvégzésére ütemeztek.) Ennek a funkciónak a használata nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-106">(However, those maintenance workers aren't necessarily the same workers who are scheduled to carry out the work order.) Use of this functionality is optional.</span></span> <span data-ttu-id="5fd1b-107">Használható például felelős dolgozók vagy dolgozói csoportok konkrét munkatípusokhoz vagy munkaterületekhez történő kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-107">For example, it can be used to select responsible workers or worker groups for specific work types or work areas.</span></span>

<span data-ttu-id="5fd1b-108">A munkarendelés-életciklus vagy a karbantartás iránti kérelem életciklusa során van lehetőség a felelős karbantartási dolgozók módosítására vagy aktualizálására.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-108">During a work order lifecycle or a maintenance request lifecycle, responsible maintenance workers can be changed or updated.</span></span> <span data-ttu-id="5fd1b-109">Ez a módosítás vagy frissítés kapcsolódhat például a karbantartási kérelem vagy a munkarendelés életciklus-állapotának változásához.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-109">This change or update might be related to, for example, a change in the maintenance request lifecycle state or the work order lifecycle state.</span></span>

<span data-ttu-id="5fd1b-110">A **Felelős karbantartási dolgozók** oldalon való beállítás munkarendelés-ütemezés során *nem* használatos.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-110">The setup on the **Responsible maintenance workers** page is *not* used during work order scheduling.</span></span>

> [!NOTE]
> <span data-ttu-id="5fd1b-111">Az Eszközkezelés modulban azokat az *előnyben részesített* karbantartási dolgozókat is beállíthatja, akiket a munkarendelés-ütemezés során a munkarendelésekhez lehet rendelni.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-111">In Asset Management, you can also set up *preferred* maintenance workers who might be allocated to work orders during work order scheduling.</span></span>

<span data-ttu-id="5fd1b-112">A felelős karbantartási dolgozók beállítása előtt be kell állítania a kiválasztáshoz rendelkezésre álló dolgozók és karbantartási dolgozók csoportjait.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-112">Before you can set up responsible maintenance workers, you must set up the workers and maintenance worker groups that should be available for selection.</span></span> <span data-ttu-id="5fd1b-113">A dolgozói és karbantartási dolgozói csoportok beállítására vonatkozó további tudnivalókért tanulmányozza a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) című témakört.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-113">For information about how to set up workers and maintenance worker groups, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-responsible-maintenance-workers"></a><span data-ttu-id="5fd1b-114">Felelős karbantartási dolgozók beállítása</span><span class="sxs-lookup"><span data-stu-id="5fd1b-114">Set up responsible maintenance workers</span></span>

1. <span data-ttu-id="5fd1b-115">Válassza ki az **Eszközkezelés**\>**Beállítás**\>**Dolgozók**\>**Felelős karbantartási dolgozók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-115">Select **Asset management** \> **Setup** \> **Workers** \> **Responsible maintenance workers**.</span></span>
2. <span data-ttu-id="5fd1b-116">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-116">Select **New** to create a record.</span></span>
3. <span data-ttu-id="5fd1b-117">Először hozzon létre egy alapértelmezett felelős karbantartási dolgozót vagy felelős karbantartási dolgozói csoportra vonatkozó beállítást, ahol csak a **Felelős karbantartási dolgozói csoport** mezőt és/vagy **Felelős dolgozó** mezőt állítja be.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-117">First create a default responsible maintenance worker or responsible maintenance worker group setup, where you set only the **Responsible maintenance worker group** field and/or the **Responsible worker** field.</span></span> <span data-ttu-id="5fd1b-118">Hagyja üresen a fennmaradó mezőket.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-118">Leave the remaining fields blank.</span></span> <span data-ttu-id="5fd1b-119">A program ezt az alapértelmezett beállítást használja a munkarendelés-ütemezés során, ha nincs más konkrétabb kombináció, amely jobban megfelel a munkarendelés tartalmának.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-119">This default setup will be used during work order scheduling if no other, more specific combination matches the contents of the work order.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5fd1b-120">A karbantartási kérés létrehozása során, amikor egy felelős karbantartási dolgozó vagy egy felelős karbantartási dolgozói csoport rendelkezésre áll az **Összes karbantartási kérés** lapon történő kiválasztáshoz, az Eszközkezelő lehetséges egyezést keresve végigellenőrzi az összes felelős karbantartási dolgozó rekordját.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-120">During creation of a maintenance request, when a responsible maintenance worker or responsible maintenance worker group is made available for selection on the **All maintenance requests** page, Asset Management goes through all responsible maintenance worker records to check for a possible match.</span></span> <span data-ttu-id="5fd1b-121">Mindig a leginkább meghatározott kombinációt ellenőrzi először.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-121">It always checks the most specific combination first.</span></span> <span data-ttu-id="5fd1b-122">Más szóval az Eszközkezelés modul először a **Kereskedelem** mezővel való egyezést ellenőrzi.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-122">In other words, Asset Management first checks for a match for the **Trade** field.</span></span> <span data-ttu-id="5fd1b-123">Ha nem talál egyezést, akkor a **Karbantartási feladat típusának változata** mezővel való egyezést ellenőrzi.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-123">If no match is found, it checks for a match for the **Maintenance job type variant** field.</span></span> <span data-ttu-id="5fd1b-124">Ha nem talál egyezést, akkor a **Karbantartási feladat típusa** mezővel való egyezést ellenőrzi, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-124">If no match is found, it checks for a match for the **Maintenance job type** field, and so on.</span></span> <span data-ttu-id="5fd1b-125">Mint látható az oldal elrendezésén, ez azt jelenti, hogy a legspecifikusabb kombináció megtalálása érdekében az Eszközkezelés modul jobbról balra haladva minden egyes rekordot ellenőriz (elsőként a **Kereskedelem**, majd a **Karbantartási feladat típusának változata**, majd a **Karbantartási feladat típusa**, majd a **Karbantartási feladat típuskategóriája**, majd a **Munkavégzési helyszín**, majd az **Eszköz** és végül az **Eszköztípus** elemet).</span><span class="sxs-lookup"><span data-stu-id="5fd1b-125">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match (first **Trade**, then **Maintenance job type variant**, then **Maintenance job type**, then **Maintenance job type category**, then **Functional location**, then **Asset**, and finally **Asset type**).</span></span> <span data-ttu-id="5fd1b-126">Ha nem talál egyezést, akkor a rendszer azt az alapértelmezett rekordot használja, amely a hét mező egyikében sem tartalmaz választási lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-126">If no match is found, the default record that has no selections in those seven fields is used.</span></span>

<span data-ttu-id="5fd1b-127">A következő ábra a **Felelős karbantartási dolgozók** oldalt szemlélteti.</span><span class="sxs-lookup"><span data-stu-id="5fd1b-127">The following illustration shows an example of the **Responsible maintenance workers** page.</span></span>

![Felelős karbantartási dolgozók oldal](media/08-setup-for-requests.png)
