---
title: Projektbecslések közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Project Service Automation projektóra becsléseinek és projektköltség becsléseinek közvetlenül a Microsoft Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
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
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: ebf0fce60ad006e798aa4f404fbffcf10a0b31f9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770289"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="7d4bc-103">Projektbecslések közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="7d4bc-103">Synchronize project estimates directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7d4bc-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Project Service Automation projektóra becsléseinek és projektköltség becsléseinek közvetlenül a Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-104">This topic describes the templates and underlying tasks that are used to synchronize project hour estimates and project expense estimates directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="7d4bc-105">Ha a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat is használhatja.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in version 8.0.</span></span>
> - <span data-ttu-id="7d4bc-106">Tényleges integráció a 8.0.1 vagy újabb verzióiban érhető el.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-106">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="7d4bc-107">Adatáramlás a Project Service Automation és a Finance között</span><span class="sxs-lookup"><span data-stu-id="7d4bc-107">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="7d4bc-108">A Project Service Automation és a Finance közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance példányok közötti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-108">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="7d4bc-109">Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projekt becsült óráival és projektek becsült kiadásaival kapcsolatos adatáramlást a Project Service Automation és Finance alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-109">The integration templates that are available with the Data integration feature enable the flow of data about project hour estimates and project expense estimates from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7d4bc-110">A következő ábra bemutatja a Project Service Automation és a Finance közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-110">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="7d4bc-111">[![Adatáramlás a Project Service Automation és a Finance integrációjához](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-111">[![Data flow for Project Service Automation integration with Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span></span>

## <a name="project-hour-estimates"></a><span data-ttu-id="7d4bc-112">Projektórabecslések</span><span class="sxs-lookup"><span data-stu-id="7d4bc-112">Project hour estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="7d4bc-113">Sablon és feladatok</span><span class="sxs-lookup"><span data-stu-id="7d4bc-113">Template and tasks</span></span>

<span data-ttu-id="7d4bc-114">A rendelkezésre álló sablonok eléréséhez a Microsoft Power Apps adminisztrációs központban válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-114">To access the available templates, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="7d4bc-115">A következő sablon és alapul szolgáló feladatok használhatók a projekt becsült óráinak szinkronizálásához a Project Service Automation és Finance között:</span><span class="sxs-lookup"><span data-stu-id="7d4bc-115">The following template and underlying tasks are used to synchronize project hour estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="7d4bc-116">**Sablon neve az adatintegrációban:** Projekt becsült órái (PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-116">**Name of the template in Data integration:** Project hour estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="7d4bc-117">**A projekt tevékenységeinek nevei:**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-117">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="7d4bc-118">Tranzakciókapcsolatok</span><span class="sxs-lookup"><span data-stu-id="7d4bc-118">Transaction relationships</span></span>
    - <span data-ttu-id="7d4bc-119">Költségbecslések</span><span class="sxs-lookup"><span data-stu-id="7d4bc-119">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="7d4bc-120">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="7d4bc-120">Entity set</span></span>

| <span data-ttu-id="7d4bc-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7d4bc-121">Project Service Automation</span></span> | <span data-ttu-id="7d4bc-122">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="7d4bc-122">Finance</span></span>                                       |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="7d4bc-123">Projektfeladatok</span><span class="sxs-lookup"><span data-stu-id="7d4bc-123">Project tasks</span></span>              | <span data-ttu-id="7d4bc-124">Projekt becsült óráihoz tartozó integrációs entitás</span><span class="sxs-lookup"><span data-stu-id="7d4bc-124">Integration entity for project hour estimates</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="7d4bc-125">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="7d4bc-125">Entity flow</span></span>

<span data-ttu-id="7d4bc-126">A projekt becsült óráinak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projekt óra-előrejelzéseinek.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-126">Project hour estimates are managed in Project Service Automation, and they are synchronized to Finance as project hour forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7d4bc-127">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7d4bc-127">Prerequisites</span></span>

<span data-ttu-id="7d4bc-128">A projekt becsült óráinak szinkronizálása előtt, a projekteket, projektfeladatokat és projektköltésgtranzakció-kategóriákat szinkronizálni kell.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-128">Before synchronization of project hour estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="7d4bc-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="7d4bc-129">Power Query</span></span>

<span data-ttu-id="7d4bc-130">A Microsoft Power Query for Excelt a következőkre kell használnia a becsült projektórák sablonban ezen feladatok elvégzéséhez:</span><span class="sxs-lookup"><span data-stu-id="7d4bc-130">In the project hour estimates template, you must use Microsoft Power Query for Excel to complete these tasks:</span></span>

- <span data-ttu-id="7d4bc-131">Állítsa az alapértelmezett lőrejelzési modell azonosítója elemet, ezt használja az integráció új óra-előrejelzések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-131">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="7d4bc-132">Szűrjön ki minden erőforrás-specifikus rekordot a feladatban, melyek miatt az óra-előrejelzésekbe integrálása sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-132">Filter out any resource-specific records in the task that will fail the integration into hour forecasts.</span></span>
- <span data-ttu-id="7d4bc-133">Szűrke ki az összes üres tranzakció kategóriasort.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-133">Filter out any empty transaction category rows.</span></span> <span data-ttu-id="7d4bc-134">A feladat elvégzésének elmulasztása esetben ez hibás óra-előrejelzések eredményezhet.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-134">Failure to complete this task might result in incorrect hour forecasts.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="7d4bc-135">Az alapértelmezett előrejelzési modell beállítása.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-135">Set the default forecast model ID</span></span>

<span data-ttu-id="7d4bc-136">A beszúrt alapértelmezett modellazonosító frissítéséhez a sablonban, kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-136">To update the default forecast model ID in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="7d4bc-137">Majd válassza ki a **Speciális lekérdezés és szűrés** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-137">Then select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="7d4bc-138">Ha az alapértelmezett becsült projektórák (PSA to Fin and Ops) sablont használ, jelölje be a **Beszúrt feltétel** elemet az **Alkalmazott lépések** listában.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-138">If you're using the default Project hour estimates (PSA to Fin and Ops) template, select the **Inserted Condition** in the list of **Applied Steps**.</span></span> <span data-ttu-id="7d4bc-139">Az **Funkció** bejegyzésben, cseréje az **O\_forecast** elemet az lőrejelzési modell azonosítója elemre, melyet használni kell, hogy az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-139">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="7d4bc-140">Az alapértelmezett sablon tartalmaz előrejelzési modellazonosítót a bemutató adatokból.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-140">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="7d4bc-141">Új sablon létrehozásakor, hozzá kell adnia ezt az oszlopot.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-141">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="7d4bc-142">A Power Queyben, jelölje be a **Feltételes oszlop hozzáadása**, elemet és adjon meg egy nevet az új oszlopnak, például **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-142">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="7d4bc-143">Adjon meg egy feltételt az oszlophoz: ha Projektfeladat nem nulla, akkor \<adja meg az előrejelzési modell azonosítóját\>; máskülönben nulla..</span><span class="sxs-lookup"><span data-stu-id="7d4bc-143">Enter the condition for the column, where, if Project task is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="filter-out-resource-specific-records"></a><span data-ttu-id="7d4bc-144">Erőforrásspecifikus rekordok kiszűrése</span><span class="sxs-lookup"><span data-stu-id="7d4bc-144">Filter out resource-specific records</span></span>

<span data-ttu-id="7d4bc-145">A Projekt becsült órái (PSA to Fin and Ops) sablonjának van egy alapértelmezett szűrője erőforrásspecifikus rekordok eltávolítására.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-145">The Project hour estimates (PSA to Fin and Ops) template has a default filter that removes any resource-specific records.</span></span> <span data-ttu-id="7d4bc-146">Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-146">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="7d4bc-147">Jelölje be a **Speciális lekérdezési és szűrés** hivatkozást az **msdyn\_islinetask** oszlop a szűréséhez, hogy csak **Hamis** rekordokat tartalmazzon.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-147">Select the **Advanced Query and Filtering** link to filter on the **msdyn\_islinetask** column so that only **False** records are included.</span></span>

#### <a name="filter-out-empty-transaction-category-rows"></a><span data-ttu-id="7d4bc-148">Az üres tranzakció kategóriasorok kiszűrése</span><span class="sxs-lookup"><span data-stu-id="7d4bc-148">Filter out empty transaction category rows</span></span>

<span data-ttu-id="7d4bc-149">Meg kell adnia egy szűrőt, hogy eltávolítsa az üres tranzakciókategóriákat tartalmazó sorokat.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-149">You must add a filter to remove any rows that have empty transaction categories.</span></span> <span data-ttu-id="7d4bc-150">Ez a feladat szükséges, függetlenül attól, hogy alapértelmezett sablont használ vagy saját sablont hoz létre.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-150">This task is required, regardless of whether you're using the default template or creating your own template.</span></span> <span data-ttu-id="7d4bc-151">Ezzel szűrővel eltávolít minden a Project Service Automation alkalmazásból érkező sort, melyek helytelen óra-előrejelzéseket okozhatnak a Finance alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-151">This filter removes any summary rows from Project Service Automation that might cause the hour forecasts in Finance to be incorrect.</span></span> <span data-ttu-id="7d4bc-152">A **Speciális lekérdezési és szűrési képernyőn** válassza ki, hogy szűrje a **msdyn\_transactioncategory\_value** oszlop nulla rekordjait.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-152">Select **Advanced Query and Filtering** link to filter out null records in the **msdyn\_transactioncategory\_value** column.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7d4bc-153">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="7d4bc-153">Template mapping in Data integration</span></span>

<span data-ttu-id="7d4bc-154">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="7d4bc-154">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="7d4bc-155">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-155">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7d4bc-156">[![Sablon-hozzárendelés](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-156">[![Template mapping](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span></span>

## <a name="project-expense-estimates"></a><span data-ttu-id="7d4bc-157">Projektköltség-becslések</span><span class="sxs-lookup"><span data-stu-id="7d4bc-157">Project expense estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="7d4bc-158">Sablon és feladatok</span><span class="sxs-lookup"><span data-stu-id="7d4bc-158">Template and tasks</span></span>

<span data-ttu-id="7d4bc-159">A következő sablon és alapul szolgáló feladatok használhatók a projekt becsült költségeinek szinkronizálásához a Project Service Automation és Finance között:</span><span class="sxs-lookup"><span data-stu-id="7d4bc-159">The following template and underlying tasks are used to synchronize project expense estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="7d4bc-160">**Sablon neve az adatintegrációban:** Projekt becsült kiadásai (PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-160">**Name of the template in Data integration:** Project expense estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="7d4bc-161">**A projekt tevékenységeinek nevei:**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-161">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="7d4bc-162">Tranzakciókapcsolatok</span><span class="sxs-lookup"><span data-stu-id="7d4bc-162">Transaction relationships</span></span> 
    - <span data-ttu-id="7d4bc-163">Költségbecslések</span><span class="sxs-lookup"><span data-stu-id="7d4bc-163">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="7d4bc-164">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="7d4bc-164">Entity set</span></span>

| <span data-ttu-id="7d4bc-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7d4bc-165">Project Service Automation</span></span> | <span data-ttu-id="7d4bc-166">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="7d4bc-166">Finance</span></span>                                                  |
|----------------------------|----------------------------------------------------------|
| <span data-ttu-id="7d4bc-167">Tranzakciók kapcsolatai</span><span class="sxs-lookup"><span data-stu-id="7d4bc-167">Transaction Connections</span></span>    | <span data-ttu-id="7d4bc-168">Projekttranzakció-kapcsolatok integrációs entitása</span><span class="sxs-lookup"><span data-stu-id="7d4bc-168">Integration entity for project transaction relationships</span></span> |
| <span data-ttu-id="7d4bc-169">Becslési sorok</span><span class="sxs-lookup"><span data-stu-id="7d4bc-169">Estimate Lines</span></span>             | <span data-ttu-id="7d4bc-170">Projekt becsült kiadásához tartozó integrációs entitás</span><span class="sxs-lookup"><span data-stu-id="7d4bc-170">Integration entity for project expense estimates</span></span>         |

### <a name="entity-flow"></a><span data-ttu-id="7d4bc-171">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="7d4bc-171">Entity flow</span></span>

<span data-ttu-id="7d4bc-172">A projekt becsült kiadásainak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projektköltség-előrejelzésekként.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-172">Project expense estimates are managed in Project Service Automation, and they are synchronized to Finance as project expense forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7d4bc-173">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="7d4bc-173">Prerequisites</span></span>

<span data-ttu-id="7d4bc-174">A projekt becsült kiadásai szinkronizálása előtt, a projekteket, projektfeladatokat és projektköltségtranzakció-kategóriákat szinkronizálni kell.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-174">Before synchronization of project expense estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="7d4bc-175">Power Query</span><span class="sxs-lookup"><span data-stu-id="7d4bc-175">Power Query</span></span>

<span data-ttu-id="7d4bc-176">A Microsoft Power Query-t kell használnia a Projekt becsült kiadásainak sablonjában a következő feladatok elvégzéséhez:</span><span class="sxs-lookup"><span data-stu-id="7d4bc-176">In the project expense estimates template, you must use Power Query to complete the following tasks:</span></span>

- <span data-ttu-id="7d4bc-177">Szürés, hogy csak költségbecslési sor rekordok kerüljenek bele.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-177">Filter to include only expense estimate line records.</span></span>
- <span data-ttu-id="7d4bc-178">Állítsa az alapértelmezett lőrejelzési modell azonosítója elemet, ezt használja az integráció új óra-előrejelzések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-178">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="7d4bc-179">A számlázási típusok átalakítása.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-179">Transform the billing types.</span></span>
- <span data-ttu-id="7d4bc-180">A tranzakciótípusok átalakítása.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-180">Transform the transaction types.</span></span>

#### <a name="filter-to-include-only-expense-estimate-lines"></a><span data-ttu-id="7d4bc-181">Szürés, hogy csak költségbecslési sorok kerüljenek bele</span><span class="sxs-lookup"><span data-stu-id="7d4bc-181">Filter to include only expense estimate lines</span></span>

<span data-ttu-id="7d4bc-182">A projekt becsült kiadásai (PSA to Fin and Ops) sablonjának van egy alapértelmezett szűrője, mellyel csak a kiadási sorok szerepelnek az integrációban.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-182">The Project expense estimates (PSA to Fin and Ops) template has a default filter that includes only expense lines in the integration.</span></span> <span data-ttu-id="7d4bc-183">Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-183">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="7d4bc-184">Válassza ki a **Tranzakciókapcsolatok** feladatot, majd kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-184">Select the **Transaction relationships** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="7d4bc-185">Válassza ki a **Speciális lekérdezés és szűrés** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-185">Select the **Advanced Query and Filtering** link.</span></span> <span data-ttu-id="7d4bc-186">Szűrje az **msdyn\_transactiontype1** oszlopot, hogy csak az **msdyn\_estimateline** elemet tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-186">Filter the **msdyn\_transactiontype1** column so that it includes only **msdyn\_estimateline**.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="7d4bc-187">Az alapértelmezett előrejelzési modell beállítása.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-187">Set the default forecast model ID</span></span>

<span data-ttu-id="7d4bc-188">A beszúrt alapértelmezett modellazonosító frissítéséhez a sablonban válassza a **Költségbecslések** feladatot, majd kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-188">To update the default forecast model ID in the template, select the **Expense estimates** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="7d4bc-189">Válassza ki a **Speciális lekérdezés és szűrés** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-189">Select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="7d4bc-190">Ha az alapértelmezett Projekt becsült kiadásai (PSA to Fin and Ops) sablont használja, a Power Query-ben jelölje be az első **Beszúrt feltétel** elemet az **Alkalmazott lépések** szakaszból.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-190">If you're using the default Project expense estimates (PSA to Fin and Ops) template, in Power Query, select the first **Inserted Condition** from the **Applied Steps** section.</span></span> <span data-ttu-id="7d4bc-191">Az **Funkció** bejegyzésben, cseréje az **O\_forecast** elemet az lőrejelzési modell azonosítója elemre, melyet használni kell, hogy az integrációhoz.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-191">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="7d4bc-192">Az alapértelmezett sablon tartalmaz előrejelzési modellazonosítót a bemutató adatokból.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-192">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="7d4bc-193">Új sablon létrehozásakor, hozzá kell adnia ezt az oszlopot.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-193">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="7d4bc-194">A Power Queyben, jelölje be a **Feltételes oszlop hozzáadása**, elemet és adjon meg egy nevet az új oszlopnak, például **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-194">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="7d4bc-195">Adjon meg egy feltételt az oszlophoz, ahol a Becslés sorazonosítója nem nulla, akkor \<adja meg az előrejelzési modell azonosítóját\>; máskülönben nulla..</span><span class="sxs-lookup"><span data-stu-id="7d4bc-195">Enter the condition for the column, where, if Estimate line ID is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="transform-the-billing-types"></a><span data-ttu-id="7d4bc-196">A számlázási típusok átalakítása</span><span class="sxs-lookup"><span data-stu-id="7d4bc-196">Transform the billing types</span></span>

<span data-ttu-id="7d4bc-197">A projekt költség becslése (PSA to Fin and Ops) sablon tartalmaz egy feltételes oszlopot, mely átalakítja a Project Service Automation alkalmazásból kapott számlatípusokat az integráció során.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-197">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the billing types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="7d4bc-198">Ha saját sablont hoz létre, hozzá kell adnia ezt a feltételes oszlopot.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-198">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="7d4bc-199">Válassza a **Speciális lekérdezési és szűrés** hivatkozást, majd válassza a **Feltételes oszlop hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-199">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="7d4bc-200">Adjon meg egy nevet az új oszlopnak, például **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-200">Enter a name for the new column, such as **BillingType**.</span></span> <span data-ttu-id="7d4bc-201">Adja meg a következő feltételt:</span><span class="sxs-lookup"><span data-stu-id="7d4bc-201">Then enter the following condition:</span></span>

<span data-ttu-id="7d4bc-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span></span>  
<span data-ttu-id="7d4bc-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span></span>  
<span data-ttu-id="7d4bc-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span></span>  
<span data-ttu-id="7d4bc-205">else **NotAvailable**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-205">else **NotAvailable**</span></span>

#### <a name="transform-the-transaction-types"></a><span data-ttu-id="7d4bc-206">A tranzakciótípusok átalakítása</span><span class="sxs-lookup"><span data-stu-id="7d4bc-206">Transform the transaction types</span></span>

<span data-ttu-id="7d4bc-207">A projekt költség becslése (PSA to Fin and Ops) sablon tartalmaz egy feltételes oszlopot, mely átalakítja a Project Service Automation alkalmazásból kapott tranzakciótípusokat az integráció során.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-207">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the transaction types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="7d4bc-208">Ha saját sablont hoz létre, hozzá kell adnia ezt a feltételes oszlopot.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-208">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="7d4bc-209">Válassza a **Speciális lekérdezési és szűrés** hivatkozást, majd válassza a **Feltételes oszlop hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-209">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="7d4bc-210">Adjon meg egy nevet az új oszlopnak, például **TransactionType**.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-210">Enter a name for the new column, such as **TransactionType**.</span></span> <span data-ttu-id="7d4bc-211">Adja meg a következő feltételt:</span><span class="sxs-lookup"><span data-stu-id="7d4bc-211">Then enter the following condition:</span></span>

<span data-ttu-id="7d4bc-212">If **msdyn\_transactiontypecode** = 192350000, then **Cost**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-212">If **msdyn\_transactiontypecode** = 192350000, then **Cost**</span></span>  
<span data-ttu-id="7d4bc-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sales**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sales**</span></span>  
<span data-ttu-id="7d4bc-214">else **null**</span><span class="sxs-lookup"><span data-stu-id="7d4bc-214">else **null**</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7d4bc-215">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="7d4bc-215">Template mapping in Data integration</span></span>

<span data-ttu-id="7d4bc-216">Az alábbi ábrán példákat láthat sablonfeladatok hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="7d4bc-216">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="7d4bc-217">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-217">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7d4bc-218">[![Sablon-hozzárendelés](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-218">[![Template mapping](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span></span>

<span data-ttu-id="7d4bc-219">[![Sablon-hozzárendelés](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-219">[![Template mapping](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span></span>
