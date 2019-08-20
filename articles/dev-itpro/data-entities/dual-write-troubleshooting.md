---
title: Hibaelhárítási útmutató – adatintegráció
description: Ez a cikk a Microsoft Dynamics 365 for Finance and Operations és a Common Data Service közötti adatintegráció során felmerülő hibák elhárítását tekinti át.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797275"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="290fa-103">Hibaelhárítási útmutató – adatintegráció</span><span class="sxs-lookup"><span data-stu-id="290fa-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a><span data-ttu-id="290fa-104">Engedélyezze a Beépülő modul nyomkövetését a Common Data Service szolgáltatásban, és tekintse át a kettős írású beépülő modul hibáinak részleteit</span><span class="sxs-lookup"><span data-stu-id="290fa-104">Enable Plugin Trace in Common Data Service and check the dual-write Plugin error details</span></span>

<span data-ttu-id="290fa-105">Ha hiba történik a kettős írású szinkronizálás során, akkor a nyomon követési naplóban tekintheti át a hibákat:</span><span class="sxs-lookup"><span data-stu-id="290fa-105">If you are facing an issue or error with dual-write synchronization, you can inspect the errors in the trace log:</span></span>

1. <span data-ttu-id="290fa-106">A hibák áttekintése előtt engedélyeznie kell a Beépülő modul nyomkövetését. Az útmutató a következő helyen található: [Beépülő modul regisztrálása](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="290fa-106">Before you can inspect the errors, you must enable Plugin trace using the instructions in [Register plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) to enable Plugin trace.</span></span> <span data-ttu-id="290fa-107">Ezután megtekintheti a hibákat.</span><span class="sxs-lookup"><span data-stu-id="290fa-107">Now you can inspect the errors.</span></span>
2. <span data-ttu-id="290fa-108">Jelentkezzen be a Dynamics 365 for Sales rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="290fa-108">Login to Dynamics 365 for Sales.</span></span>
3. <span data-ttu-id="290fa-109">Kattintson a Beállítások ikonra (fogaskerék), és válassza a **Speciális beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="290fa-109">Click on the Settings icon (a gear), and select **Advanced Settings**.</span></span>
4. <span data-ttu-id="290fa-110">A **Beállítások** menüben válassza a **Testreszabás > Beépülő modul nyomkövetési naplója** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="290fa-110">In the **Settings** menu, choose **Customization > Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="290fa-111">A hiba részleteinek megtekintéséhez kattintson a típusnévre: **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin**.</span><span class="sxs-lookup"><span data-stu-id="290fa-111">Click the type name **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** to display the error details.</span></span>

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a><span data-ttu-id="290fa-112">A Finance and Operations kettős írású szinkronizálási hibáinak ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="290fa-112">Check dual-write synchronization errors in Finance and Operations</span></span>

<span data-ttu-id="290fa-113">A hibák a következő lépésekkel tekinthetők meg a tesztelés során:</span><span class="sxs-lookup"><span data-stu-id="290fa-113">You can check the errors during testing by following these steps:</span></span>

+ <span data-ttu-id="290fa-114">Jelentkezzen be a LifeCycle Services (LCS) szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="290fa-114">Login to LifeCycle Services (LCS).</span></span>
+ <span data-ttu-id="290fa-115">Nyissa meg azt az LCS-projektet, amelyen kettős írású tesztelést szeretne végezni.</span><span class="sxs-lookup"><span data-stu-id="290fa-115">Open the LCS project that you chose to perform dual-write testing.</span></span>
+ <span data-ttu-id="290fa-116">Lépjen a Felhőbeli környezetek részre.</span><span class="sxs-lookup"><span data-stu-id="290fa-116">Go to Cloud Hosted Environments.</span></span>
+ <span data-ttu-id="290fa-117">Távoli asztal szolgáltatással nyissa meg a Finance and Operations VM-et. Használja az LCS-ben látható helyi fiókot.</span><span class="sxs-lookup"><span data-stu-id="290fa-117">Remote desktop to Finance and Operations VM using local account that is displayed in LCS.</span></span>
+ <span data-ttu-id="290fa-118">Nyissa meg az eseménynaplót.</span><span class="sxs-lookup"><span data-stu-id="290fa-118">Open the event viewer.</span></span> 
+ <span data-ttu-id="290fa-119">Lépjen az **Alkalmazás- és szolgáltatásnaplók > Microsoft > Dynamics > AX-DualWriteSync > Működő** részre.</span><span class="sxs-lookup"><span data-stu-id="290fa-119">Navigate to **Applications and Services logs > Microsoft > Dynamics > AX-DualWriteSync > Operational**.</span></span> <span data-ttu-id="290fa-120">Megjelennek a hibák és a részletek.</span><span class="sxs-lookup"><span data-stu-id="290fa-120">The errors and details are displayed.</span></span>

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a><span data-ttu-id="290fa-121">Másik Common Data Service-környezet összekapcsolása és az összekapcsolás megszüntetése a Finance and Operationsben</span><span class="sxs-lookup"><span data-stu-id="290fa-121">How to unlink and link another Common Data Service environment from Finance and Operations</span></span>

<span data-ttu-id="290fa-122">Az összekapcsolások a következő lépésekkel frissíthetők:</span><span class="sxs-lookup"><span data-stu-id="290fa-122">You can update links by following these steps:</span></span>

+ <span data-ttu-id="290fa-123">Lépjen a Finance and Operations-környezethez.</span><span class="sxs-lookup"><span data-stu-id="290fa-123">Navigate to the Finance and Operations environment.</span></span>
+ <span data-ttu-id="290fa-124">Nyissa meg az Adatkezelést.</span><span class="sxs-lookup"><span data-stu-id="290fa-124">Open Data Management.</span></span>
+ <span data-ttu-id="290fa-125">Kattintson **A CDS for Apps hivatkozása** elemre.</span><span class="sxs-lookup"><span data-stu-id="290fa-125">Click on **Link to CDS for apps**.</span></span>
+ <span data-ttu-id="290fa-126">Válassza ki az összes futó leképezést, és kattintson a **Leállítás** elemre.</span><span class="sxs-lookup"><span data-stu-id="290fa-126">Select all the running mappings and click **Stop**.</span></span> 
+ <span data-ttu-id="290fa-127">Válassza ki az összes futó leképezést, és kattintson a **Törlés** elemre.</span><span class="sxs-lookup"><span data-stu-id="290fa-127">Select all the mappings and click **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="290fa-128">A **Törlés** beállítás nem látható, ha a **CustomerV3-Account** sablont választja ki.</span><span class="sxs-lookup"><span data-stu-id="290fa-128">The **Delete** option will not appear if **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="290fa-129">Ha szükséges, törölje a sablon kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="290fa-129">Unselect it if needed.</span></span> <span data-ttu-id="290fa-130">A **CustomerV3-Account** egy régebben létesített sablon, amely együttműködik a Potenciális ügyfelek készpénzre váltása sablonnal.</span><span class="sxs-lookup"><span data-stu-id="290fa-130">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="290fa-131">Mivel globálisan kiadott sablon, minden sablon alatt megjelenik.</span><span class="sxs-lookup"><span data-stu-id="290fa-131">Because it is globally released, it shows up under all templates.</span></span>

+ <span data-ttu-id="290fa-132">Kattintson a **Környezet leválasztása** elemre.</span><span class="sxs-lookup"><span data-stu-id="290fa-132">Click **Unlink environment**.</span></span>
+ <span data-ttu-id="290fa-133">A megerősítéshez kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="290fa-133">Click **Yes** for confirmation.</span></span>
+ <span data-ttu-id="290fa-134">Az új környezet összekapcsolásához kövesse a [telepítési útmutató](https://aka.ms/dualwrite-docs) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="290fa-134">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>

