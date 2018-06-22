---
title: "Projekt szolgáltatásautomatizálása"
description: "Ez a megoldás az Adatintegráció funkció segítségével szinkronizálja az adatokat a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Project Service Automation példányai között a Common Data Service (CDS) környezetben."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="c74e5-103">Projekt szolgáltatásautomatizálása</span><span class="sxs-lookup"><span data-stu-id="c74e5-103">Project Service Automation</span></span>

<span data-ttu-id="c74e5-104">The Project Service Automation to Finance és Operations integrációs funkció Adatintegráció funkció segítségével szinkronizálja az adatokat a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Dynamics 365 for Project Service Automation példányai között a Common Data Service (CDS) környezetben.</span><span class="sxs-lookup"><span data-stu-id="c74e5-104">The Project Service Automation to Finance and Operations integration solution uses the Data Integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via the Common Data Service (CDS).</span></span> <span data-ttu-id="c74e5-105">Az integrációs sablonok, mely az adatintegráció funkcióban érhetők el lehetővé teszik, a projektek, projektszerződések, a projektszerződéssorok és projektszerződéssor mérföldkövek, kiadástranzakció-kategóriák, becsült órák és becsült költségek áramoltatását a Project Service Automation és a Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-105">The integration templates that are available with the Data Integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="c74e5-106">Amennyiben a Dynamics 365 for Finance and Operations Enterprise edition 7.3.0-ás verzióját használja,, telepítenie kell a KB 4074835 frissítést.</span><span class="sxs-lookup"><span data-stu-id="c74e5-106">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="c74e5-107">Ez lehetővé teszi a rögzített árú projektek integrálását.</span><span class="sxs-lookup"><span data-stu-id="c74e5-107">This will allow you to integrate fixed price projects.</span></span>
>
> <span data-ttu-id="c74e5-108">Amennyiben a Dynamics 365 for Finance and Operations 8.0-ás verzióját használja a projektfeladatok integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="c74e5-108">If you are using Dynamics 365 for Finance and Operations version 8.0, you will be able to use project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
>
> <span data-ttu-id="c74e5-109">Amennyiben a Dynamics 365 for Finance and Operations 8.0.1-es verzióját használja, lépes lesz szinkronizálni a tényleges értékeket.</span><span class="sxs-lookup"><span data-stu-id="c74e5-109">If you are using Dynamics 365 for Finance and Operations version 8.0.1, you will be able to synchronize actuals.</span></span>
>
> <span data-ttu-id="c74e5-110">Amennyiben a Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához.</span><span class="sxs-lookup"><span data-stu-id="c74e5-110">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="c74e5-111">Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.</span><span class="sxs-lookup"><span data-stu-id="c74e5-111">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

<span data-ttu-id="c74e5-112">Mielőtt integrálhatná a Project Service Automation és Finance and Operations alkalmazásokat, konfigurálnia kell a Project Service Automation integráció paramétereit.</span><span class="sxs-lookup"><span data-stu-id="c74e5-112">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="c74e5-113">További tudnivalókért lásd Project Service Automation integrálási paraméterek.</span><span class="sxs-lookup"><span data-stu-id="c74e5-113">For more information, see Project Service Automation integration parameters.</span></span>

<span data-ttu-id="c74e5-114">Az integráció közvetlen szinkronizálást nyújt az alábbi helyzetekben:</span><span class="sxs-lookup"><span data-stu-id="c74e5-114">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="c74e5-115">Projektszerződések karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-115">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c74e5-116">Projektek létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-116">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c74e5-117">Projektszerződéssorok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-117">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c74e5-118">Projektszerződéssor mérföldkövek karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-118">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c74e5-119">Projektfeladatok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-119">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c74e5-120">Kiadási tranzakció kategóriák karbantartása a Finance and Operations alkalmazásban, és azok közvetlen szinkronizálása a Finance and Operations és a Project Service Automation között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-120">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="c74e5-121">Projektóra becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-121">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="c74e5-122">Projektköltség becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="c74e5-122">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="c74e5-123">Adatszinkronizálás</span><span class="sxs-lookup"><span data-stu-id="c74e5-123">Data synchronization</span></span>
<span data-ttu-id="c74e5-124">A következő ábra bemutatja az adatszinkronizálást a Project Service Automation és a Finance and Operations közötti integráció részeként.</span><span class="sxs-lookup"><span data-stu-id="c74e5-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="c74e5-125">Jelenleg nem áll rendelkezésre minden sablon.</span><span class="sxs-lookup"><span data-stu-id="c74e5-125">Not all templates are currently available.</span></span> <span data-ttu-id="c74e5-126">A sablonok az elkészülés időpontjában lesznek kiadva.</span><span class="sxs-lookup"><span data-stu-id="c74e5-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="c74e5-127">[![Project Service Automation és Finance and Operations integráció](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="c74e5-127">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="c74e5-128">Rendszerigény a Finance and Operations rendszerhez</span><span class="sxs-lookup"><span data-stu-id="c74e5-128">System requirements for Finance and Operations</span></span>

<span data-ttu-id="c74e5-129">A Project Service Automation és Finance and Operations megoldás használatához telepítenie kell a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 verzióját, 12-es vagy újabb platformfrissítéssel.</span><span class="sxs-lookup"><span data-stu-id="c74e5-129">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="c74e5-130">A Project Service Automation rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="c74e5-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="c74e5-131">A Project Service Automation és Finance and Operations integráció használatához telepítenie kell a következő összetevőket:</span><span class="sxs-lookup"><span data-stu-id="c74e5-131">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="c74e5-132">Microsoft Dynamics 365 for Project Service Automation 9.0.0.0 vagy újabb verzió.</span><span class="sxs-lookup"><span data-stu-id="c74e5-132">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later.</span></span>
- <span data-ttu-id="c74e5-133">A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 for Sales szolgáltatáshoz, 1.14.0.0 (v14) vagy későbbi verzió.</span><span class="sxs-lookup"><span data-stu-id="c74e5-133">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>
- <span data-ttu-id="c74e5-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation 1.0.0.0 vagy újabb verzió.</span><span class="sxs-lookup"><span data-stu-id="c74e5-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation version 1.0.0.0 or later.</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="c74e5-135">A Project Service Automation to Finance and Operations integrációs megoldást Project Service Automation példányába telepítse</span><span class="sxs-lookup"><span data-stu-id="c74e5-135">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>



