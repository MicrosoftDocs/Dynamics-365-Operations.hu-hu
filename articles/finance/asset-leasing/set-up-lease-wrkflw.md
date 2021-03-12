---
title: Lízingjóváhagyási munkafolyamatok beállítása
description: A témakör bemutatja, hogyan állíthat be egy jóváhagyási munkafolyamatot, amely új lízing létrehozásakor fog futni.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d2135458873963dc7c930b4bcef0c508c7d9635f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992839"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="66918-103">Lízingjóváhagyási munkafolyamatok beállítása</span><span class="sxs-lookup"><span data-stu-id="66918-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66918-104">A témakör bemutatja, hogyan állíthat be egy jóváhagyási munkafolyamatot, amely új lízing létrehozásakor fog futni.</span><span class="sxs-lookup"><span data-stu-id="66918-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="66918-105">A munkafolyamat használatáról a [Lízingjóváhagyási munkafolyamatok használata](use-create-lease-wrkflw.md) című témakörben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="66918-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="66918-106">Nyissa meg az **Eszközlízing \> Beállítás \> Lízingmunkafolyamat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66918-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="66918-107">A **Lízingmunkafolyamat** oldalon válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66918-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="66918-108">A megjelenő párbeszédpanelben a **Munkafolyamat-típus** csoportjában válassza a **Lízingmunkafolyamat** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="66918-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="66918-109">Az alkalmazás megnyílik.</span><span class="sxs-lookup"><span data-stu-id="66918-109">The application is opened.</span></span> <span data-ttu-id="66918-110">Futtatása után jelentkezzen be az Azure Active Directory (Azure AD) alkalmazásba, hogy átirányítsa a munkafolyamat-alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="66918-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="66918-111">Húzza a **Lízingmunkafolyamat-jóváhagyási** elemét a munkafolyamatra.</span><span class="sxs-lookup"><span data-stu-id="66918-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="66918-112">Csatlakoztasson egy csomópontot a **Start** – **Lízingmunkafolyamat-jóváhagyáshoz**.</span><span class="sxs-lookup"><span data-stu-id="66918-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="66918-113">Ezután csatlakoztassa a **Lízingmunkafolyamat-jóváhagyás** – **Befejezéshez**.</span><span class="sxs-lookup"><span data-stu-id="66918-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="66918-114">Kattintson duplán a **Lízingmunkafolyamat-jóváhagyásra**.</span><span class="sxs-lookup"><span data-stu-id="66918-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="66918-115">Válassza a **Tulajdonságok** lehetőséget, majd az **Alapbeállítások** elemben adja meg a munkafolyamat nevét.</span><span class="sxs-lookup"><span data-stu-id="66918-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="66918-116">Ezen a lapon további paramétereket is beállíthat a munkafolyamathoz.</span><span class="sxs-lookup"><span data-stu-id="66918-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="66918-117">Ha bekapcsolta az **Automatikus műveletek** lehetőséget, a rendszer automatikusan végrehajt egy adott műveletet.</span><span class="sxs-lookup"><span data-stu-id="66918-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="66918-118">Az értesítések akkor küldhetők el, ha meg vannak adva az **Értesítések** lapon. A **Speciális beállítások** fülön megadhatja a végső jóváhagyót, beállíthat egy időkorlátot, és kijelölhet konkrét műveleteket, amelyeket végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="66918-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="66918-119">Ha befejezte a munkafolyamat-paraméterek beállítását, válassza a **Bezárás** gombot.</span><span class="sxs-lookup"><span data-stu-id="66918-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="66918-120">Válassza ki az **1. lépés** lehetőséget, majd a **Tulajdonságok** elemet.</span><span class="sxs-lookup"><span data-stu-id="66918-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="66918-121">Az **Alapszintű beállítások** lehetőségben adja meg a lépés nevét, hozzon létre egy jóváhagyási tárgysort, és adja meg a jóváhagyásra vonatkozó utasításokat.</span><span class="sxs-lookup"><span data-stu-id="66918-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="66918-122">A **Hozzárendelés** lapon válassza ki a hozzárendelés típusát.</span><span class="sxs-lookup"><span data-stu-id="66918-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="66918-123">Ha adott felhasználókat szeretne hozzárendelni a jóváhagyáshoz, válassza a **Felhasználó** lehetőséget, jelölje ki a lízingeket jóváhagyó felhasználókat, majd válassza a **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66918-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="66918-124">A munkafolyamat létrehozásához válassza a **Mentés és a bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66918-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="66918-125">Ezután a rendszer kérésére válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="66918-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="66918-126">A **Munkafolyamat létrehozása** oldalon válassza a **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66918-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="66918-127">Jelölje ki az új munkafolyamatot, majd válassza a **Verziók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66918-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="66918-128">Ezután válassza az **Aktívvá tétel** lehetőséget, hogy a munkafolyamat aktív legyen.</span><span class="sxs-lookup"><span data-stu-id="66918-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="66918-129">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="66918-129">Select **Close**.</span></span> <span data-ttu-id="66918-130">Megjelenik az új aktív verzió.</span><span class="sxs-lookup"><span data-stu-id="66918-130">The new active version appears.</span></span>
