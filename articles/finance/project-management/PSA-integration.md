---
title: A Project Service Automation áttekintése
description: Ez a témakör a Dynamics 365 Project Service Automation – Dynamics 365 Finance integrálási megoldásról nyújt tájékoztatást.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250553"
---
# <a name="project-service-automation-overview"></a><span data-ttu-id="8a311-103">A Project Service Automation áttekintése</span><span class="sxs-lookup"><span data-stu-id="8a311-103">Project Service Automation overview</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8a311-104">A Project Service Automation és Finance közötti integrációs megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Dynamics 365 Finance és a Dynamics 365 Project Service Automation példányai között a Common Data Service szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="8a311-104">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Dynamics 365 Finance and Dynamics 365 Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="8a311-105">Az integrációs sablonok, mely az adatintegráció funkcióban érhetők el lehetővé teszik, a projektek, projektszerződések, a projektszerződéssorok és projektszerződéssor mérföldkövek, kiadástranzakció-kategóriák, becsült órák és becsült költségek áramoltatását a Project Service Automation és a Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-105">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="8a311-106">A 7.3.0 verzió használata esetén telepítenie kell a KB 4074835 csomagot.</span><span class="sxs-lookup"><span data-stu-id="8a311-106">If you're using version 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="8a311-107">Ezt követően lehetséges a rögzített árú projektek integrálása.</span><span class="sxs-lookup"><span data-stu-id="8a311-107">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="8a311-108">Ha a 7.3.0 verziót használja, tranzakciókat hív be a Project Service Automation alkalmazásból, telepítenie kell KB 4345320 frissítést annak érdekében, hogy a díjakat megjelenítse a projektszámlán.</span><span class="sxs-lookup"><span data-stu-id="8a311-108">If you're using version 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="8a311-109">Amennyiben a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="8a311-109">If you're using version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="8a311-110">Amennyiben a 8.0.1 vagy újabb verzióját használja, szinkronizálhatja azt aktuális adatokat.</span><span class="sxs-lookup"><span data-stu-id="8a311-110">If you're using version 8.0.1 or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="8a311-111">Mielőtt integrálhatná a Project Service Automation és Finance alkalmazásokat, konfigurálnia kell a Project Service Automation integráció paramétereit.</span><span class="sxs-lookup"><span data-stu-id="8a311-111">Before you can integrate Project Service Automation Finance, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="8a311-112">További tudnivalókért lásd [Project Service Automation integrálási paraméterek](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="8a311-112">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="8a311-113">Az integráció közvetlen szinkronizálást nyújt az alábbi helyzetekben:</span><span class="sxs-lookup"><span data-stu-id="8a311-113">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="8a311-114">Projektszerződések karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-114">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="8a311-115">Projektek létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-115">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="8a311-116">Projektszerződés-sorok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-116">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="8a311-117">Projektszerződés-sorok mérföldköveinek karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-117">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="8a311-118">Projektfeladatok karbantartása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-118">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="8a311-119">Kiadási tranzakció kategóriák karbantartása a Finance alkalmazásban, és azok közvetlen szinkronizálása a Finance és a Project Service Automation között.</span><span class="sxs-lookup"><span data-stu-id="8a311-119">Maintain expense transaction categories in Finance, and synchronize them directly from Finance to Project Service Automation.</span></span>
- <span data-ttu-id="8a311-120">Projektóra becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-120">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="8a311-121">Projektköltség-becslések létrehozása a Project Service Automation alkalmazásban, és azok közvetlen szinkronizálása a Project Service Automation és Finance között.</span><span class="sxs-lookup"><span data-stu-id="8a311-121">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="8a311-122">Projektidő, költség és tényleges díjak létrehozása a Project Service Automation alkalmazásban, és projekttranzakciók létrehozása a Project Service Automation integrációs naplójában, hogy azok beküldhetők legyenek a Finance alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="8a311-122">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="8a311-123">Adatszinkronizálás</span><span class="sxs-lookup"><span data-stu-id="8a311-123">Data synchronization</span></span>

<span data-ttu-id="8a311-124">A következő ábra bemutatja az adatszinkronizálást a Project Service Automation és a Finance közötti integráció részeként.</span><span class="sxs-lookup"><span data-stu-id="8a311-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance.</span></span>

> [!NOTE]
> <span data-ttu-id="8a311-125">Jelenleg nem áll rendelkezésre minden sablon.</span><span class="sxs-lookup"><span data-stu-id="8a311-125">Not all templates are currently available.</span></span> <span data-ttu-id="8a311-126">A sablonok az elkészülés időpontjában lesznek kiadva.</span><span class="sxs-lookup"><span data-stu-id="8a311-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="8a311-127">[![Project Service Automation és Finance integráció paraméterei](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="8a311-127">[![Project Service Automation integration with Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance"></a><span data-ttu-id="8a311-128">A Finance rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="8a311-128">System requirements for Finance</span></span>

<span data-ttu-id="8a311-129">A Project Service Automation és Finance megoldás használatához telepítenie kell az Enterprise edition 7.3 verzióját, 12-es vagy újabb platformfrissítéssel.</span><span class="sxs-lookup"><span data-stu-id="8a311-129">To use the Project Service Automation to Finance integration solution, you must install Enterprise edition 7.3 with Platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="8a311-130">A Project Service Automation rendszerkövetelményei</span><span class="sxs-lookup"><span data-stu-id="8a311-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="8a311-131">A Project Service Automation és Finance integráció használatához telepítenie kell a következő összetevőket:</span><span class="sxs-lookup"><span data-stu-id="8a311-131">To use the Project Service Automation to Finance integration solution, you must install the following components:</span></span>

- <span data-ttu-id="8a311-132">Dynamics 365 Project Service Automation 9.0.0.0 vagy újabb verziója</span><span class="sxs-lookup"><span data-stu-id="8a311-132">Dynamics 365 Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="8a311-133">A potenciális ügyfelek készpénzre váltása megoldás Dynamics 365 Sales szolgáltatáshoz, 1.14.0.0 (v14) vagy későbbi verzió</span><span class="sxs-lookup"><span data-stu-id="8a311-133">Prospect to cash solution for Dynamics 365 Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="8a311-134">Project Service Automation és a Finance integrációs megoldás a Dynamics 365 Project Service Automation 1.0.0.0 vagy újabb verziójához</span><span class="sxs-lookup"><span data-stu-id="8a311-134">Project Service Automation to Finance solution for Dynamics 365 Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="8a311-135">A Project Service Automation to Finance integrációs megoldást Project Service Automation példányába telepítse</span><span class="sxs-lookup"><span data-stu-id="8a311-135">Install the Project Service Automation to Finance integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="8a311-136">Töltse le a Project Service Automation to Finance integrációs megoldást a [Microsoft letöltőközpontból](https://www.microsoft.com/download/details.aspx?id=57016), és kövesse a megoldáshoz tartozó utasításokat.</span><span class="sxs-lookup"><span data-stu-id="8a311-136">Download the Project Service Automation to Finance integration solution from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>
