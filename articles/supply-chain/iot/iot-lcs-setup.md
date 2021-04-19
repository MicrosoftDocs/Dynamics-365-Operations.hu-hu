---
title: A IoT Intelligencia beépülő modul telepítése az LCS-ben
description: Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.
author: robinarh
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2d1cc9a7535be05a3e466c27e53047d694cf0160
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826443"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="e15bd-103">A IoT Intelligencia beépülő modul telepítése az LCS-ben</span><span class="sxs-lookup"><span data-stu-id="e15bd-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e15bd-104">Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="e15bd-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="e15bd-105">Ne felejtse el, hogy a bővítmények nem telepíthetők bemutató/próbaverziós környezetbe.</span><span class="sxs-lookup"><span data-stu-id="e15bd-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="e15bd-106">A bővítmény telepítése előtt [létre kell hoznia az Azure-erőforrásokat](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="e15bd-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="e15bd-107">Az LCS-környezet beállítása</span><span class="sxs-lookup"><span data-stu-id="e15bd-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="e15bd-108">Nyissa meg az LCS-t, majd nyissa meg a Microsoft Dynamics 365 Supply Chain Management-környezetét.</span><span class="sxs-lookup"><span data-stu-id="e15bd-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="e15bd-109">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="e15bd-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="e15bd-110">Válassza az **Új bővítmény telepítése** lehetőséget a környezetben engedélyezett bővítmények listájának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e15bd-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="e15bd-111">A **Telepítendő bővítmény kiválasztása** párbeszédpanelen válassza ki az **IoT Intelligencia** elemet.</span><span class="sxs-lookup"><span data-stu-id="e15bd-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="e15bd-112">Adja meg az IoT-központ és a Redis-gyorsítótár adatait a **Bővítmények beállítása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="e15bd-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="e15bd-113">A szükséges értékek megtalálhatók a kulcstárban, amelyet az [Azure-erőforrások létrehozása](iot-azure-setup.md) részben hozott létre.</span><span class="sxs-lookup"><span data-stu-id="e15bd-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="e15bd-114">**Bérlő azonosítója** – Az Azure portálon nyissa meg a kulcstárolót, majd kattintson a bal oldali navigációs ablak **Áttekintés** elemére, és másolja át a **Címtár-azonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="e15bd-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="e15bd-115">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="e15bd-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="e15bd-116">**IoT-eseményközponttal kompatibilis végpont kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét.</span><span class="sxs-lookup"><span data-stu-id="e15bd-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="e15bd-117">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="e15bd-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="e15bd-118">**IoT-eseményközponttal kompatibilis végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol az IoT-központ eseményközpont-kapcsolati karaktersorozata tárolva van.</span><span class="sxs-lookup"><span data-stu-id="e15bd-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="e15bd-119">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="e15bd-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="e15bd-120">**Redis-gyorsítótár kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét.</span><span class="sxs-lookup"><span data-stu-id="e15bd-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="e15bd-121">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="e15bd-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="e15bd-122">**Redis-gyorsítótár végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol a Redis-gyorsítótár kapcsolati karaktersorozata tárolva van.</span><span class="sxs-lookup"><span data-stu-id="e15bd-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="e15bd-123">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="e15bd-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="e15bd-124">Jelölje be a jelölőnégyzetet az Általános Szerződési Feltételek elfogadásához.</span><span class="sxs-lookup"><span data-stu-id="e15bd-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="e15bd-125">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e15bd-125">Select **Install**.</span></span>
8. <span data-ttu-id="e15bd-126">Megjelenik egy üzenet, amely azt jelzi, hogy a "Bővítmény sikeresen aktiválva telepítésre."</span><span class="sxs-lookup"><span data-stu-id="e15bd-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="e15bd-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e15bd-127">Select **OK**.</span></span>

<span data-ttu-id="e15bd-128">Az LCS-beállítás befejeződött.</span><span class="sxs-lookup"><span data-stu-id="e15bd-128">LCS setup is now completed.</span></span> <span data-ttu-id="e15bd-129">A következő lépés a [forgatókönyvek beállítása](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="e15bd-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="e15bd-130">A bővítmény eltávolítása</span><span class="sxs-lookup"><span data-stu-id="e15bd-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="e15bd-131">A Supply Chain Management alkalmazásban [tiltsa le a forgatókönyveket](iot-scenario-setup.md#disable-a-scenario).</span><span class="sxs-lookup"><span data-stu-id="e15bd-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#disable-a-scenario).</span></span>
2. <span data-ttu-id="e15bd-132">Az LCS-ben lépjen a Supply Chain Management környezet részleteihez.</span><span class="sxs-lookup"><span data-stu-id="e15bd-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="e15bd-133">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="e15bd-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="e15bd-134">Válassza az **Eltávolítás** lehetőséget az IoT Intelligencia beépülő modul esetén.</span><span class="sxs-lookup"><span data-stu-id="e15bd-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]