---
title: A IoT Intelligencia beépülő modul telepítése az LCS-ben
description: Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2bcbf69362e4ca3a156d1d404e15489ddb3f0d0
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597216"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="94c7d-103">A IoT Intelligencia beépülő modul telepítése az LCS-ben</span><span class="sxs-lookup"><span data-stu-id="94c7d-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="94c7d-104">Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="94c7d-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="94c7d-105">Ne felejtse el, hogy a bővítmények nem telepíthetők bemutató/próbaverziós környezetbe.</span><span class="sxs-lookup"><span data-stu-id="94c7d-105">Note that add-ins cannot be installed on a demo/trial environment.</span></span> <span data-ttu-id="94c7d-106">A bővítmény telepítése előtt [létre kell hoznia az Azure-erőforrásokat](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="94c7d-106">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="94c7d-107">Az LCS-környezet beállítása</span><span class="sxs-lookup"><span data-stu-id="94c7d-107">Set up the LCS environment</span></span>

1. <span data-ttu-id="94c7d-108">Nyissa meg az LCS-t, majd nyissa meg a Microsoft Dynamics 365 Supply Chain Management-környezetét.</span><span class="sxs-lookup"><span data-stu-id="94c7d-108">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="94c7d-109">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="94c7d-109">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="94c7d-110">Válassza az **Új bővítmény telepítése** lehetőséget a környezetben engedélyezett bővítmények listájának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="94c7d-110">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="94c7d-111">A **Telepítendő bővítmény kiválasztása** párbeszédpanelen válassza ki az **IoT Intelligencia** elemet.</span><span class="sxs-lookup"><span data-stu-id="94c7d-111">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="94c7d-112">Adja meg az IoT-központ és a Redis-gyorsítótár adatait a **Bővítmények beállítása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="94c7d-112">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="94c7d-113">A szükséges értékek megtalálhatók a kulcstárban, amelyet az [Azure-erőforrások létrehozása](iot-azure-setup.md) részben hozott létre.</span><span class="sxs-lookup"><span data-stu-id="94c7d-113">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="94c7d-114">**Bérlő azonosítója** – Az Azure portálon nyissa meg a kulcstárolót, majd kattintson a bal oldali navigációs ablak **Áttekintés** elemére, és másolja át a **Címtár-azonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="94c7d-114">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="94c7d-115">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="94c7d-115">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="94c7d-116">**IoT-eseményközponttal kompatibilis végpont kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét.</span><span class="sxs-lookup"><span data-stu-id="94c7d-116">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="94c7d-117">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="94c7d-117">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="94c7d-118">**IoT-eseményközponttal kompatibilis végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol az IoT-központ eseményközpont-kapcsolati karaktersorozata tárolva van.</span><span class="sxs-lookup"><span data-stu-id="94c7d-118">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="94c7d-119">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="94c7d-119">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="94c7d-120">**Redis-gyorsítótár kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét.</span><span class="sxs-lookup"><span data-stu-id="94c7d-120">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="94c7d-121">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="94c7d-121">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="94c7d-122">**Redis-gyorsítótár végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol a Redis-gyorsítótár kapcsolati karaktersorozata tárolva van.</span><span class="sxs-lookup"><span data-stu-id="94c7d-122">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="94c7d-123">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="94c7d-123">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="94c7d-124">Jelölje be a jelölőnégyzetet az Általános Szerződési Feltételek elfogadásához.</span><span class="sxs-lookup"><span data-stu-id="94c7d-124">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="94c7d-125">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="94c7d-125">Select **Install**.</span></span>
8. <span data-ttu-id="94c7d-126">Megjelenik egy üzenet, amely azt jelzi, hogy a "Bővítmény sikeresen aktiválva telepítésre."</span><span class="sxs-lookup"><span data-stu-id="94c7d-126">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="94c7d-127">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="94c7d-127">Select **OK**.</span></span>

<span data-ttu-id="94c7d-128">Az LCS-beállítás befejeződött.</span><span class="sxs-lookup"><span data-stu-id="94c7d-128">LCS setup is now completed.</span></span> <span data-ttu-id="94c7d-129">A következő lépés a [forgatókönyvek beállítása](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="94c7d-129">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="94c7d-130">A bővítmény eltávolítása</span><span class="sxs-lookup"><span data-stu-id="94c7d-130">Uninstall the add-in</span></span>

1. <span data-ttu-id="94c7d-131">A Supply Chain Management alkalmazásban [tiltsa le a forgatókönyveket](iot-scenario-setup.md#how-to-disable-a-scenario).</span><span class="sxs-lookup"><span data-stu-id="94c7d-131">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#how-to-disable-a-scenario).</span></span>
2. <span data-ttu-id="94c7d-132">Az LCS-ben lépjen a Supply Chain Management környezet részleteihez.</span><span class="sxs-lookup"><span data-stu-id="94c7d-132">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="94c7d-133">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="94c7d-133">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="94c7d-134">Válassza az **Eltávolítás** lehetőséget az IoT Intelligencia beépülő modul esetén.</span><span class="sxs-lookup"><span data-stu-id="94c7d-134">Select **Uninstall** for the IoT Intelligence add-in.</span></span>
