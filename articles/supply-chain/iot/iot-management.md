---
title: IoT Intelligencia figyelése és kezelése
description: Ez a témakör azt mutatja be, hogyan lehet felügyelni és kezelni az IoT Intelligencia alkalmazást.
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
ms.openlocfilehash: 97a87b78a0178424f00e464262bb7f69e8a5b4a0
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386520"
---
# <a name="monitor-and-manage-iot-intelligence"></a><span data-ttu-id="db7c7-103">IoT Intelligencia figyelése és kezelése</span><span class="sxs-lookup"><span data-stu-id="db7c7-103">Monitor and manage IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="db7c7-104">Ez a témakör azt mutatja be, hogyan lehet felügyelni és kezelni az IoT Intelligencia alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="db7c7-104">This topic explains how to monitor and manage IoT Intelligence.</span></span>

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a><span data-ttu-id="db7c7-105">A Microsoftnál Dynamics 365 Supply Chain Management forgatókönyveinek figyelése</span><span class="sxs-lookup"><span data-stu-id="db7c7-105">Monitor scenarios in Microsoft Dynamics 365 Supply Chain Management</span></span>

<span data-ttu-id="db7c7-106">A IoT Intelligencia feldolgozását több helyen is nyomon követheti:</span><span class="sxs-lookup"><span data-stu-id="db7c7-106">You can monitor IoT Intelligence processing from several places:</span></span>

+ <span data-ttu-id="db7c7-107">**Modulok \> Gyártásvezérlés \> Lekérdezések és jelentések \> IoT Intelligencia \> Értesítések** – A feloldatlan értesítések listájának megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="db7c7-107">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Notifications** – View the list of unresolved notifications.</span></span>
+ <span data-ttu-id="db7c7-108">**Modulok \> Gyártásvezérlés \> Lekérdezések és jelentések \> IoT Intelligencia \> Lezárt értesítések** – A megoldott vagy elvetett értesítések listájának megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="db7c7-108">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Closed notifications** – View the list of notifications that have been resolved or dismissed.</span></span>
+ <span data-ttu-id="db7c7-109">**Modulok \> Gyártásvezérlés \> Lekérdezések és jelentések \> IoT Intelligencia \> Mérőszám-kulcsok** – Az **Erőforrás állapota** idősorozat-diagramok mérőszám-kulcsainak megtekintése.</span><span class="sxs-lookup"><span data-stu-id="db7c7-109">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Metric keys** – View the metric keys for the **Resource Status** times series charts.</span></span>
+ <span data-ttu-id="db7c7-110">**Modulok \> Gyártásvezérlés \> Gyártásvégrehajtás \> Erőforrás állapota** – Adott mérőszámok nyomon követése a **Konfigurálás** párbeszédpanel segítségével.</span><span class="sxs-lookup"><span data-stu-id="db7c7-110">**Modules \> Production control \> Manufacturing execution \> Resource status** – Track specific metrics by using the **Configure** dialog box.</span></span> <span data-ttu-id="db7c7-111">Ha egy forgatókönyv kivételt észlel, akkor az értesítés a kivétel részleteit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="db7c7-111">If a scenario detects an exception, a notification shows the details of the exception.</span></span>
+ <span data-ttu-id="db7c7-112">**Munkaterületek \> Termelési szint kezelése \> Értesítések** – A feloldatlan értesítések listájának megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="db7c7-112">**Workspaces \> Production floor management \> Notifications** – View the list of unresolved notifications.</span></span>

## <a name="modify-a-running-iot-intelligence-scenario"></a><span data-ttu-id="db7c7-113">Futó IoT Intelligencia forgatókönyv módosítása</span><span class="sxs-lookup"><span data-stu-id="db7c7-113">Modify a running IoT Intelligence scenario</span></span>

<span data-ttu-id="db7c7-114">Ha egy forgatókönyv fut, akkor ezeket a változtatásokat hajthatja végre:</span><span class="sxs-lookup"><span data-stu-id="db7c7-114">When a scenario is running, you can make these changes:</span></span>

+ <span data-ttu-id="db7c7-115">Új érzékelőséma-definíciók hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="db7c7-115">Add new sensor schema definitions.</span></span>
+ <span data-ttu-id="db7c7-116">Új jeladatértékek kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="db7c7-116">Select new signal data values.</span></span>
+ <span data-ttu-id="db7c7-117">A meglévő jeladatértékek kiválasztásának törlése.</span><span class="sxs-lookup"><span data-stu-id="db7c7-117">Cancel the selection of existing signal data values.</span></span>
+ <span data-ttu-id="db7c7-118">Új jeladatértékek hozzáadása és leképezése.</span><span class="sxs-lookup"><span data-stu-id="db7c7-118">Add and map new signal data values.</span></span>
+ <span data-ttu-id="db7c7-119">Küszöbértékek frissítése.</span><span class="sxs-lookup"><span data-stu-id="db7c7-119">Update threshold values.</span></span>

<span data-ttu-id="db7c7-120">Ha egy forgatókönyv fut, akkor ezek a változtatások tiltottak:</span><span class="sxs-lookup"><span data-stu-id="db7c7-120">When a scenario is running, these changes are prohibited:</span></span>

+ <span data-ttu-id="db7c7-121">Az engedélyezett forgatókönyv által jelenleg fogyasztott sémadefiníciók törlése vagy módosítása.</span><span class="sxs-lookup"><span data-stu-id="db7c7-121">Delete or modify any schema definitions that are currently consumed by an enabled scenario.</span></span>
+ <span data-ttu-id="db7c7-122">Az engedélyezett forgatókönyv kiválasztott sémaelérési útjainak módosítása.</span><span class="sxs-lookup"><span data-stu-id="db7c7-122">Change the enabled scenario's selected schema paths.</span></span>

## <a name="simulation-options"></a><span data-ttu-id="db7c7-123">Szimulációs lehetőségek</span><span class="sxs-lookup"><span data-stu-id="db7c7-123">Simulation options</span></span>

<span data-ttu-id="db7c7-124">Szimulálhatja a gyári gépek jeleit.</span><span class="sxs-lookup"><span data-stu-id="db7c7-124">You can simulate factory machine signals.</span></span> <span data-ttu-id="db7c7-125">További részletekért lásd ezeket a témaköröket:</span><span class="sxs-lookup"><span data-stu-id="db7c7-125">For more information, see these topics:</span></span>

+ [<span data-ttu-id="db7c7-126">IoT DevKit AZ3166 csatlakoztatása az Azure IoT-központhoz</span><span class="sxs-lookup"><span data-stu-id="db7c7-126">Connect IoT DevKit AZ3166 to Azure IoT Hub</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [<span data-ttu-id="db7c7-127">Raspberry Pi online szimulátor csatlakoztatása az Azure IoT-központhoz (Node.js)</span><span class="sxs-lookup"><span data-stu-id="db7c7-127">Connect Raspberry Pi online simulator to Azure IoT Hub (Node.js)</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [<span data-ttu-id="db7c7-128">Eszközszimulációs megoldás gyorsító – áttekintés</span><span class="sxs-lookup"><span data-stu-id="db7c7-128">Device Simulation solution accelerator overview</span></span>](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)