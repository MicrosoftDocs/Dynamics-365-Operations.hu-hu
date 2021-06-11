---
title: Kettős írás beállítása a Lifecycle Services szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet kettős írású kapcsolatot beállítani a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103569"
---
# <a name="dual-write-setup-from-lifecycle-services"></a><span data-ttu-id="a3cfe-103">Kettős írás beállítása a Lifecycle Services szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="a3cfe-103">Dual-write setup from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a3cfe-104">Ez a témakör bemutatja, hogyan lehet engedélyezni a kettős írást a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-104">This topic explains how to enable dual-write from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3cfe-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a3cfe-105">Prerequisites</span></span>

<span data-ttu-id="a3cfe-106">A következő témakörökben leírtak szerint végre kell hajtani a Power Platform-integrációt:</span><span class="sxs-lookup"><span data-stu-id="a3cfe-106">You must complete the Power Platform integration as described in the following topics:</span></span>

+ [<span data-ttu-id="a3cfe-107">Power Platform-integráció – engedélyezés a környezet telepítése során</span><span class="sxs-lookup"><span data-stu-id="a3cfe-107">Power Platform Integration - Enable during environment deployment</span></span>](../../power-platform/overview.md#enable-during-environment-deployment)
+ [<span data-ttu-id="a3cfe-108">Power Platform-integráció – beállítás a környezet telepítése után</span><span class="sxs-lookup"><span data-stu-id="a3cfe-108">Power Platform integration - Set up after environment deployment</span></span>](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a><span data-ttu-id="a3cfe-109">Kettős írás beállítása az új Dataverse-környezetekhez</span><span class="sxs-lookup"><span data-stu-id="a3cfe-109">Set up dual-write for new Dataverse environments</span></span>

<span data-ttu-id="a3cfe-110">A kettős írás **Környezet részletes adatai** LCS-oldalról történő beállításához hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a3cfe-110">Follow these steps to set up dual-write from LCS **Environment Details** page:</span></span>

1. <span data-ttu-id="a3cfe-111">A **Környezet részletes adatai** oldalon bontsa ki a **Power Platform-integráció** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-111">On the **Environment Details** page, expand the **Power Platform Integration** section.</span></span>

2. <span data-ttu-id="a3cfe-112">Kattintson a **Kettős írású alkalmazás** gombra.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-112">Select the **Dual-write application** button.</span></span>

    ![Power Platform-integráció](media/powerplat_integration_step2.png)

3. <span data-ttu-id="a3cfe-114">Olvassa el az Általános Szerződési Feltételeket, majd válassza a **Konfigurálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-114">Review the terms and conditions, and then select **Configure**.</span></span>

4. <span data-ttu-id="a3cfe-115">A folytatáshoz válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-115">Select **OK** to continue.</span></span>

5. <span data-ttu-id="a3cfe-116">A haladás nyomon követéséhez időnként frissítse a Környezet részletes adatai odalt.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-116">You can monitor the progress by periodically refreshing the environment details page.</span></span> <span data-ttu-id="a3cfe-117">A telepítéshez általában nem kell 30 percnél hosszabb idő.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-117">Setup typically takes 30 minutes or less.</span></span>  

6. <span data-ttu-id="a3cfe-118">Ha a telepítés befejeződött, egy üzenet tájékoztatja arról, hogy a folyamat sikeres volt-e, vagy történt-e hiba.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-118">When the setup is complete, a message will inform you if the process was successful or if there was a failure.</span></span> <span data-ttu-id="a3cfe-119">Ha a beállítás sikertelen, erre vonatkozó hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-119">If the setup failed, then a related error message is displayed.</span></span> <span data-ttu-id="a3cfe-120">Csak akkor léphet tovább a következő lépésre, ha kijavítja az esetleges hibákat.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-120">You must fix any errors before moving to the next step.</span></span>

7. <span data-ttu-id="a3cfe-121">Válassza az **Összekapcsolás Power Platform-környezettel** a Dataverse és az aktuális környezet adatbázisainak összekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-121">Select **Link to Power Platform environment** to create a link between Dataverse and the current environment's databases.</span></span> <span data-ttu-id="a3cfe-122">Ehhez általában nem kell 5 percnél hosszabb idő.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-122">This typically takes less than 5 minutes.</span></span>

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Összekapcsolás Power Platform-környezettel":::

8. <span data-ttu-id="a3cfe-124">Ha befejeződött az összekapcsolás, megjelenik egy hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-124">When the linking is complete, a hyperlink is displayed.</span></span> <span data-ttu-id="a3cfe-125">A hivatkozásra kattintva jelentkezzen be a Finance and Operations-környezet kettős íráshoz használatos felügyeleti területére.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-125">Use the link to sign in to the dual-write administration area in the Finance and Operations environment.</span></span> <span data-ttu-id="a3cfe-126">Itt beállíthatja az entitások leképezését.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-126">From there, you can set up entity mappings.</span></span>

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a><span data-ttu-id="a3cfe-127">Kettős írás beállítása meglévő Dataverse-környezetekhez</span><span class="sxs-lookup"><span data-stu-id="a3cfe-127">Set up dual-write for an existing Dataverse environment</span></span>

<span data-ttu-id="a3cfe-128">Ha meglévő Dataverse-környezetben szeretne kettős írást beállítani, [támogatási jegyet](../../lifecycle-services/lcs-support.md) kell küldenie a Microsoftnak.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-128">To set up dual-write for an existing Dataverse environment, you must create a Microsoft [support ticket](../../lifecycle-services/lcs-support.md).</span></span> <span data-ttu-id="a3cfe-129">A jegynek a következőket kell tartalmaznia:</span><span class="sxs-lookup"><span data-stu-id="a3cfe-129">The ticket must include:</span></span>

+ <span data-ttu-id="a3cfe-130">A Finance and Operations-környezet azonosítója.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-130">Your Finance and Operations environment ID.</span></span>
+ <span data-ttu-id="a3cfe-131">A környezet neve a Lifecycle Services szolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-131">Your environment name from Lifecycle Services.</span></span>
+ <span data-ttu-id="a3cfe-132">A Dataverse-szervezetazonosító, vagy a Power Platform-környezetazonosító a Power Platform Adminisztrációs központjából.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-132">The Dataverse organization ID or Power Platform Environment ID from Power Platform Admin Center.</span></span> <span data-ttu-id="a3cfe-133">A jegyben kérje, hogy az azonosító legyen a Power Platform-integrációhoz használt példány.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-133">In your ticket, request that the ID be the instance used for Power Platform integration.</span></span>

> [!NOTE]
> <span data-ttu-id="a3cfe-134">A környezetek nem csatolhatók le az LCS használatával.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-134">You can't unlink environments by using LCS.</span></span> <span data-ttu-id="a3cfe-135">Egy környezet kapcsolatának megszüntetése érdekében nyissa meg az **Adatintegráció** munkaterületet a Finance and Operations környezetben , majd válassza a **Csatolás megszüntetése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-135">To unlink an environment, open the **Data integration** workspace in the Finance and Operations environment, and then select **Unlink**.</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
