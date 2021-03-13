---
title: Kettős írás beállítása a Lifecycle Services szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet kettős írású kapcsolatot beállítani a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: df67e498b963af3ded7464f46f37bb4b2ca7d852
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127593"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="f9c94-103">Kettős írás beállítása a Lifecycle Services szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="f9c94-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f9c94-104">Ez a témakör azt mutatja be, hogyan lehet beállítani egy kettős írási kapcsolatot egy új Finance and Operations környezet és egy új Dataverse környezet között a Microsoft Dynamics Lifecycle Services (LCS) megoldásból.</span><span class="sxs-lookup"><span data-stu-id="f9c94-104">This topic explains how to set up a dual-write connection between a new Finance and Operations environment and a new Dataverse environment from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f9c94-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="f9c94-105">Prerequisites</span></span>

<span data-ttu-id="f9c94-106">A kettős írási kapcsolatot csak akkor lehet létrehozni, ha Ön adminisztrátor.</span><span class="sxs-lookup"><span data-stu-id="f9c94-106">You must be an admin to set up a dual-write connection.</span></span>

+ <span data-ttu-id="f9c94-107">Hozzáféréssel kell rendelkeznie a bérlőhöz.</span><span class="sxs-lookup"><span data-stu-id="f9c94-107">You must have access to the tenant.</span></span>
+ <span data-ttu-id="f9c94-108">Mind a Finance and Operations, mind a Dataverse környezetek esetében adminisztrátornak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="f9c94-108">You must be an admin in both Finance and Operations environments and Dataverse environments.</span></span>

## <a name="set-up-a-dual-write-connection"></a><span data-ttu-id="f9c94-109">Kettős írási kapcsolat beállítása</span><span class="sxs-lookup"><span data-stu-id="f9c94-109">Set up a dual-write connection</span></span>

<span data-ttu-id="f9c94-110">A kettős írási kapcsolat beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f9c94-110">Follow these steps to set up the dual-write connection.</span></span>

1. <span data-ttu-id="f9c94-111">Az LCS_ben lépjen a projektjére.</span><span class="sxs-lookup"><span data-stu-id="f9c94-111">In LCS, go to your project.</span></span>
2. <span data-ttu-id="f9c94-112">A **Konfigurálás** kiválasztásával új környezetet telepíthet.</span><span class="sxs-lookup"><span data-stu-id="f9c94-112">Select **Configure** to deploy a new environment.</span></span>
3. <span data-ttu-id="f9c94-113">Válassza ki a verziót.</span><span class="sxs-lookup"><span data-stu-id="f9c94-113">Select the version.</span></span> 
4. <span data-ttu-id="f9c94-114">Válassza ki a topológiát.</span><span class="sxs-lookup"><span data-stu-id="f9c94-114">Select the topology.</span></span> <span data-ttu-id="f9c94-115">Ha csak egy topológia érhető el, akkor automatikusan ki van jelölve.</span><span class="sxs-lookup"><span data-stu-id="f9c94-115">If only one topology is available, it's automatically selected.</span></span>
5. <span data-ttu-id="f9c94-116">Hajtsa végre a **Telepítési beállítások** varázsló első lépéseit.</span><span class="sxs-lookup"><span data-stu-id="f9c94-116">Complete the first steps in the **Deployment settings** wizard.</span></span>
6. <span data-ttu-id="f9c94-117">A **Dataverse** lapon tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="f9c94-117">On the **Dataverse** tab, follow one of these steps:</span></span>

    - <span data-ttu-id="f9c94-118">Ha már egy Dataverse környezet létesítve van a bérlő számára, akkor kiválaszthatja azt.</span><span class="sxs-lookup"><span data-stu-id="f9c94-118">If a Dataverse environment is already provisioned for your tenant, you can select it.</span></span>

        1. <span data-ttu-id="f9c94-119">Állítsa a **Dataverse** konfigurálása beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="f9c94-119">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="f9c94-120">Az **Elérhető környezetek** oszlopban válassza ki azt a környezetet, amellyel integrálni szeretné a Finance and Operations-adatokat.</span><span class="sxs-lookup"><span data-stu-id="f9c94-120">In the **Available environments** column, select the environment to integrate with your Finance and Operations data.</span></span> <span data-ttu-id="f9c94-121">A lista minden olyan környezetet tartalmaz, amelyen adminisztrátori jogosultságai vannak.</span><span class="sxs-lookup"><span data-stu-id="f9c94-121">The list includes all environments where you have admin privileges.</span></span>
        3. <span data-ttu-id="f9c94-122">Jelölje be az **Elfogadom** jelölőnégyzetet, annak jelzéséhez, hogy elfogadja-e a feltételeket.</span><span class="sxs-lookup"><span data-stu-id="f9c94-122">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![A Dataverse lap, ha már egy Dataverse környezet létesítve van a bérlő számára](../dual-write/media/lcs_setup_1.png)

    - <span data-ttu-id="f9c94-124">Ha a bérlő még nem rendelkezik Dataverse-környezettel, akkor az új környezet lesz létesítve.</span><span class="sxs-lookup"><span data-stu-id="f9c94-124">If your tenant doesn't already have a Dataverse environment, a new environment will be provisioned.</span></span>

        1. <span data-ttu-id="f9c94-125">Állítsa a **Dataverse** konfigurálása beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="f9c94-125">Set the **Configure Dataverse** option to **Yes**.</span></span>
        2. <span data-ttu-id="f9c94-126">Adja meg egy nevet a Dataverse környezetnek.</span><span class="sxs-lookup"><span data-stu-id="f9c94-126">Enter a name for the Dataverse environment.</span></span>
        3. <span data-ttu-id="f9c94-127">Válassza ki azt a régiót, amelybe a környezetet szeretné létesíteni.</span><span class="sxs-lookup"><span data-stu-id="f9c94-127">Select the region to deploy the environment in.</span></span>
        4. <span data-ttu-id="f9c94-128">Válassza ki a környezetre vonatkozó alapértelmezett nyelvet és pénznemet.</span><span class="sxs-lookup"><span data-stu-id="f9c94-128">Select the default language and currency for the environment.</span></span>

            > [!NOTE]
            > <span data-ttu-id="f9c94-129">Később nem módosíthatja a nyelvet és a pénznemet.</span><span class="sxs-lookup"><span data-stu-id="f9c94-129">You can't change the language and currency later.</span></span>

        5. <span data-ttu-id="f9c94-130">Jelölje be az **Elfogadom** jelölőnégyzetet, annak jelzéséhez, hogy elfogadja-e a feltételeket.</span><span class="sxs-lookup"><span data-stu-id="f9c94-130">Select the **Agree** check box to indicate that you agree to the terms and conditions.</span></span>

        ![A Dataverse lap, amikor a bérlő még nem rendelkezik Dataverse-környezettel](../dual-write/media/lcs_setup_2.png)

7. <span data-ttu-id="f9c94-132">Hajtsa végre a **Telepítési beállítások** varázsló fennmaradó lépéseit.</span><span class="sxs-lookup"><span data-stu-id="f9c94-132">Complete the remaining steps in the **Deployment settings** wizard.</span></span>
8. <span data-ttu-id="f9c94-133">Miután a környezet állapota már **Telepített**, nyissa meg a környezeti részletek lapot.</span><span class="sxs-lookup"><span data-stu-id="f9c94-133">After the environment has a status of **Deployed**, open the environment details page.</span></span> <span data-ttu-id="f9c94-134">Az **Power Platform Integráció** szakasz az összekapcsolt Finance and Operations környezet és Dataverse környezet nevét jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="f9c94-134">The **Power Platform Integration** section shows the names of the Finance and Operations environment and the Dataverse environment that are linked.</span></span>

    ![Power Platform Integráció szakasz](../dual-write/media/lcs_setup_3.png)

9. <span data-ttu-id="f9c94-136">A Finance and Operations környezethez tartozó adminisztrátornak be kell jelentkeznie a LCS-be, és ki kell választania a **CDS csatolása alkalmazásokhoz** hivatkozást az összekapcsolása befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="f9c94-136">An admin of the Finance and Operations environment must sign in to LCS and select **Link to CDS for Apps** to complete the link.</span></span> <span data-ttu-id="f9c94-137">A környezeti részletek lap az adminisztrátor kapcsolattartási adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="f9c94-137">The environment details page shows the admin's contact information.</span></span>

    <span data-ttu-id="f9c94-138">Az összekapcsolás befejezését követően a program frissíti a állapotot **Környezet-összekapcsolás sikeresen befejezve** értékre.</span><span class="sxs-lookup"><span data-stu-id="f9c94-138">After the link is completed, the status is updated to **Environment linking successfully completed**.</span></span>

10. <span data-ttu-id="f9c94-139">Az **Adatintegrációs** munkaterület megnyitásához a Finance and Operations környezetben és a rendelkezésre álló sablonok ellenőrzéséhez válassza a **CDS csatolása alkalmazásokhoz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f9c94-139">To open the **Data integration** workspace in the Finance and Operations environment and control the templates that are available, select **Link to CDS for Apps**.</span></span>

    ![A CDS csatolása alkalmazásokhoz gomb az Power Platform Integráció területen](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> <span data-ttu-id="f9c94-141">A környezetek nem csatolhatók le az LCS használatával.</span><span class="sxs-lookup"><span data-stu-id="f9c94-141">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="f9c94-142">Egy környezet kapcsolatának megszüntetése érdekében nyissa meg az **Adatintegráció** munkaterületet a Finance and Operations környezetben , majd válassza a **Csatolás megszüntetése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="f9c94-142">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

