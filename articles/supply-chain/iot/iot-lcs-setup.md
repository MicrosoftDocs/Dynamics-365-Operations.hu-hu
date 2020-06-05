---
title: A IoT Intelligencia beépülő modul telepítése az LCS-ben
description: Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: 04333b3659f090b15cc0d0ee216f14dabc588883
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386521"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a><span data-ttu-id="843d8-103">A IoT Intelligencia beépülő modul telepítése az LCS-ben</span><span class="sxs-lookup"><span data-stu-id="843d8-103">Install the IoT Intelligence add-in in LCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="843d8-104">Ez a témakör bemutatja, hogyan telepítheti az IoT Intelligencia beépülő modult a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="843d8-104">This topic explains how to install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="843d8-105">A bővítmény telepítése előtt [létre kell hoznia az Azure-erőforrásokat](iot-azure-setup.md).</span><span class="sxs-lookup"><span data-stu-id="843d8-105">Before you can install the add-in, you must [create the Azure resources](iot-azure-setup.md).</span></span>

## <a name="set-up-the-lcs-environment"></a><span data-ttu-id="843d8-106">Az LCS-környezet beállítása</span><span class="sxs-lookup"><span data-stu-id="843d8-106">Set up the LCS environment</span></span>

1. <span data-ttu-id="843d8-107">Nyissa meg az LCS-t, majd nyissa meg a Microsoft Dynamics 365 Supply Chain Management-környezetét.</span><span class="sxs-lookup"><span data-stu-id="843d8-107">Open LCS, and go to your Microsoft Dynamics 365 Supply Chain Management environment.</span></span>
2. <span data-ttu-id="843d8-108">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="843d8-108">Scroll to the **Environment add-ins** section.</span></span>
3. <span data-ttu-id="843d8-109">Válassza az **Új bővítmény telepítése** lehetőséget a környezetben engedélyezett bővítmények listájának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="843d8-109">Select **Install a new add-in** to show the list of add-ins that have been enabled for the environment.</span></span>
4. <span data-ttu-id="843d8-110">A **Telepítendő bővítmény kiválasztása** párbeszédpanelen válassza ki az **IoT Intelligencia** elemet.</span><span class="sxs-lookup"><span data-stu-id="843d8-110">In the **Select an add-in to install** dialog box, select **IoT Intelligence**.</span></span>
5. <span data-ttu-id="843d8-111">Adja meg az IoT-központ és a Redis-gyorsítótár adatait a **Bővítmények beállítása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="843d8-111">In the **Setup add-in** dialog box, provide the details of your IoT hub and Redis cache.</span></span> <span data-ttu-id="843d8-112">A szükséges értékek megtalálhatók a kulcstárban, amelyet az [Azure-erőforrások létrehozása](iot-azure-setup.md) részben hozott létre.</span><span class="sxs-lookup"><span data-stu-id="843d8-112">You can find the required values in the key vault that you created in [Create Azure resources](iot-azure-setup.md).</span></span>

    + <span data-ttu-id="843d8-113">**Bérlő azonosítója** – Az Azure portálon nyissa meg a kulcstárolót, majd kattintson a bal oldali navigációs ablak **Áttekintés** elemére, és másolja át a **Címtár-azonosító** értékét.</span><span class="sxs-lookup"><span data-stu-id="843d8-113">**Tenant ID** – In the Azure portal, go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **Directory ID** value.</span></span> <span data-ttu-id="843d8-114">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="843d8-114">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="843d8-115">**IoT-eseményközponttal kompatibilis végpont kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét.</span><span class="sxs-lookup"><span data-stu-id="843d8-115">**IoT Event Hub-compatible endpoint Key Vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="843d8-116">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="843d8-116">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="843d8-117">**IoT-eseményközponttal kompatibilis végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol az IoT-központ eseményközpont-kapcsolati karaktersorozata tárolva van.</span><span class="sxs-lookup"><span data-stu-id="843d8-117">**IoT Event Hub-compatible endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the event hub connection string for the IoT hub is stored.</span></span> <span data-ttu-id="843d8-118">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="843d8-118">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="843d8-119">**Redis-gyorsítótár kulcstároló URI-azonosítója** – Lépjen a kulcstárolóra, majd a bal oldali navigációs ablakban válassza az **Áttekintés** parancsot, majd másolja át a **DNS-név** értékét.</span><span class="sxs-lookup"><span data-stu-id="843d8-119">**Redis cache key vault URI** – Go to the key vault, and then, in the left navigation pane, select **Overview**, and copy the **DNS name** value.</span></span> <span data-ttu-id="843d8-120">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="843d8-120">Paste that value in the **Setup add-in** dialog box.</span></span>
    + <span data-ttu-id="843d8-121">**Redis-gyorsítótár végpont titkos kódjának neve** – Lépjen a kulcstárolóhoz, majd a bal oldali navigációs ablakban válassza ki a **Titkos kód** lehetőséget, majd másolja a titkos kód nevét oda, ahol a Redis-gyorsítótár kapcsolati karaktersorozata tárolva van.</span><span class="sxs-lookup"><span data-stu-id="843d8-121">**Redis cache endpoint secret name** – Go to the key vault, and then, in the left navigation pane, select **Secrets**, and copy the name of the secret where the connection string for the Redis cache is stored.</span></span> <span data-ttu-id="843d8-122">Illessze be ezt az értéket a **Bővítmény beállítása** párbeszédpanelbe.</span><span class="sxs-lookup"><span data-stu-id="843d8-122">Paste that value in the **Setup add-in** dialog box.</span></span>

6. <span data-ttu-id="843d8-123">Jelölje be a jelölőnégyzetet az Általános Szerződési Feltételek elfogadásához.</span><span class="sxs-lookup"><span data-stu-id="843d8-123">Select the check box to accept the terms and conditions.</span></span>
7. <span data-ttu-id="843d8-124">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="843d8-124">Select **Install**.</span></span>
8. <span data-ttu-id="843d8-125">Megjelenik egy üzenet, amely azt jelzi, hogy a "Bővítmény sikeresen aktiválva telepítésre."</span><span class="sxs-lookup"><span data-stu-id="843d8-125">A message box appears that states, "Add-in has been successfully triggered for installation."</span></span> <span data-ttu-id="843d8-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="843d8-126">Select **OK**.</span></span>

<span data-ttu-id="843d8-127">Az LCS-beállítás befejeződött.</span><span class="sxs-lookup"><span data-stu-id="843d8-127">LCS setup is now completed.</span></span> <span data-ttu-id="843d8-128">A következő lépés a [forgatókönyvek beállítása](iot-scenario-setup.md).</span><span class="sxs-lookup"><span data-stu-id="843d8-128">The next step is to [set up the scenarios](iot-scenario-setup.md).</span></span>

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a><span data-ttu-id="843d8-129">A bővítmény eltávolítása</span><span class="sxs-lookup"><span data-stu-id="843d8-129">Uninstall the add-in</span></span>

1. <span data-ttu-id="843d8-130">A Supply Chain Management alkalmazásban [tiltsa le a forgatókönyveket](iot-scenario-setup.md#how-to-disable-a-scenario).</span><span class="sxs-lookup"><span data-stu-id="843d8-130">In Supply Chain Management, [disable the scenarios](iot-scenario-setup.md#how-to-disable-a-scenario).</span></span>
2. <span data-ttu-id="843d8-131">Az LCS-ben lépjen a Supply Chain Management környezet részleteihez.</span><span class="sxs-lookup"><span data-stu-id="843d8-131">In LCS, go to your Supply Chain Management environment details.</span></span>
3. <span data-ttu-id="843d8-132">Görgessen le a **Környezeti bővítmények** szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="843d8-132">Scroll to the **Environment add-ins** section.</span></span>
4. <span data-ttu-id="843d8-133">Válassza az **Eltávolítás** lehetőséget az IoT Intelligencia beépülő modul esetén.</span><span class="sxs-lookup"><span data-stu-id="843d8-133">Select **Uninstall** for the IoT Intelligence add-in.</span></span>