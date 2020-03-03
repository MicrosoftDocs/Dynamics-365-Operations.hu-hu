---
title: Hibaelhárítási útmutató – adatintegráció
description: Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti adatintegrációk során felmerülő hibák elhárítását tekinti át.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 87bdb72024c1c3844ff61e832a92f7edcc77c5d6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019821"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="d0e9a-103">Hibaelhárítási útmutató – adatintegráció</span><span class="sxs-lookup"><span data-stu-id="d0e9a-103">Troubleshooting guide for data integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a><span data-ttu-id="d0e9a-104">Engedélyezze a Beépülő modul nyomkövetési naplóját a Common Data Service szolgáltatásban, és vizsgálja meg át a kettős írású beépülő modul hibáinak részleteit</span><span class="sxs-lookup"><span data-stu-id="d0e9a-104">Enable plug-in trace logs in Common Data Service and inspect the dual-write plug-in error details</span></span>

<span data-ttu-id="d0e9a-105">Ha a kettős írású szinkronizálás során problémát vagy hibát észlel, hajtsa végre a következő lépéseket a nyomkövetési napló hibáinak ellenőrzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-105">If you experience an issue or error during dual-write synchronization, follow these steps to inspect the errors in the trace log.</span></span>

1. <span data-ttu-id="d0e9a-106">A hibák ellenőrzése előtt engedélyeznie kell a beépülő modul nyomonkövetési naplókat.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-106">Before you can inspect the errors, you must enable plug-in trace logs.</span></span> <span data-ttu-id="d0e9a-107">További információért tekints meg az [Oktatás: beépülő modul írása vagy regisztrálás](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) „Nyomonkövetési naplók megtekintése” szakaszát.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-107">For instructions, see the "View trace logs" section of [Tutorial: Write and register a plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span></span>

    <span data-ttu-id="d0e9a-108">Most megtekintheti a hibákat.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-108">You can now inspect the errors.</span></span>

2. <span data-ttu-id="d0e9a-109">Jelentkezzen be a Microsoft Dynamics 365 Sales alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-109">Sign in to Microsoft Dynamics 365 Sales.</span></span>
3. <span data-ttu-id="d0e9a-110">Válassza ki a **Beállítások** gombot (a fogaskerék szimbólumát), majd válassza ki a **Speciális beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-110">Select the **Settings** button (the gear symbol), and then select **Advanced Settings**.</span></span>
4. <span data-ttu-id="d0e9a-111">A **Beállítások** menüben válassza a **Testreszabás \> Beépülő modul nyomkövetési naplója** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-111">On the **Settings** menu, select **Customization \> Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="d0e9a-112">A hiba részleteinek megjelenítéséhez kattintson a típusnévre: **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-112">Select **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** as the type name to show the error details.</span></span>

## <a name="inspect-dual-write-synchronization-errors"></a><span data-ttu-id="d0e9a-113">Kettős írás szinkronizálási hibák ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="d0e9a-113">Inspect dual-write synchronization errors</span></span>

<span data-ttu-id="d0e9a-114">Kövesse az alábbi lépéseket a hibák tesztelés során történő ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-114">Follow these steps to inspect errors during testing.</span></span>

1. <span data-ttu-id="d0e9a-115">Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-115">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="d0e9a-116">Nyissa meg az LCS-projektet a kettős írási teszt elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-116">Open the LCS project to do dual-write testing for.</span></span>
3. <span data-ttu-id="d0e9a-117">Válassza a **Felhőbeli környezetek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-117">Select **Cloud-hosted environments**.</span></span>
4. <span data-ttu-id="d0e9a-118">Hozzon létre távoli asztali kapcsolatot az alkalmazás virtuális gépével (VM) az LCS modulban megjelenített helyi fiók használatával.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-118">Make a Remote desktop connection to the application virtual machine (VM) by using local account that is shown in LCS.</span></span>
5. <span data-ttu-id="d0e9a-119">Nyissa meg az eseménynaplót.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-119">Open Event Viewer.</span></span> 
6. <span data-ttu-id="d0e9a-120">Lépjen az **Alkalmazás- és szolgáltatásnaplók \> Microsoft \> Dynamics \> AX-DualWriteSync \> Működő** részre.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-120">Go to **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span> <span data-ttu-id="d0e9a-121">Megjelennek a hibák és a részletek.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-121">The errors and details are shown.</span></span>

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a><span data-ttu-id="d0e9a-122">Kapcsoljon le egy Common Data Service környezetet az alkalmazásból és kapcsoljon egy másik környezetet</span><span class="sxs-lookup"><span data-stu-id="d0e9a-122">Unlink one Common Data Service environment from the application and link another environment</span></span>

<span data-ttu-id="d0e9a-123">A linkek frissítéséhez hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-123">Follow these steps to update links.</span></span>

1. <span data-ttu-id="d0e9a-124">Nyissa meg az alkalmazáskörnyezet.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-124">Go to the application environment.</span></span>
2. <span data-ttu-id="d0e9a-125">Nyissa meg az Adatkezelést.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-125">Open Data Management.</span></span>
3. <span data-ttu-id="d0e9a-126">Válassza a **CDS for Apps hivatkozása** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="d0e9a-126">Select **Link to CDS for apps**.</span></span>
4. <span data-ttu-id="d0e9a-127">Válassza ki az összes futó leképezést, majd válassza a **Leállítás**parancsot.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-127">Select all the mappings that are running, and then select **Stop**.</span></span>
5. <span data-ttu-id="d0e9a-128">Válassza ki az összes leképezést, majd válassza a **Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-128">Select all the mappings, and then select **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0e9a-129">A **Törlés** beállítás nem elérhető, ha a **CustomerV3-Account** sablont választja ki.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-129">The **Delete** option isn't available if the **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="d0e9a-130">Szükség esetén törölje a sablon kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-130">Clear the selection of this template as required.</span></span> <span data-ttu-id="d0e9a-131">A **CustomerV3-Account** egy régebben létesített sablon, amely együttműködik a Potenciális ügyfelek készpénzre váltása sablonnal.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-131">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="d0e9a-132">Mivel globálisan kiadott sablon, minden sablon alatt megjelenik.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-132">Because it's globally released, it appears under all templates.</span></span>

6. <span data-ttu-id="d0e9a-133">Válassza a **Környezet leválasztása** elemet.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-133">Select **Unlink environment**.</span></span>
7. <span data-ttu-id="d0e9a-134">A művelet jóváhagyásához válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-134">Select **Yes** to confirm the operation.</span></span>
8. <span data-ttu-id="d0e9a-135">Az új környezet összekapcsolásához kövesse a [telepítési útmutató](https://aka.ms/dualwrite-docs) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="d0e9a-135">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>