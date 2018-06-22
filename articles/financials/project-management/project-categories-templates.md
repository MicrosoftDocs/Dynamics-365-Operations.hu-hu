---
title: "Projekt költségkategóriák szinkronizálása a Project Service Automation alkalmazásból"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt költségkategóriáinak Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
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
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: hu-hu
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="a77e7-103">Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között</span><span class="sxs-lookup"><span data-stu-id="a77e7-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

<span data-ttu-id="a77e7-104">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt költségkategóriáinak Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="a77e7-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> <span data-ttu-id="a77e7-105">Projektfeladatok integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Dynamics 365 for Finance and Operations 8.0-ás verziójában érhető el.</span><span class="sxs-lookup"><span data-stu-id="a77e7-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="a77e7-106">Adatáramlás a Project Service Automation és a Finance and Operations esetében</span><span class="sxs-lookup"><span data-stu-id="a77e7-106">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="a77e7-107">A Project Service Automation és a Finance and Operations közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance and Operations példányok közötti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="a77e7-107">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="a77e7-108">Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projektköltségtranzakció-kategóriákkal kapcsolatos adatáramlást a Project Service Automation és Finance and Operations alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="a77e7-108">The integration templates that are available with the Data integration feature enables the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="a77e7-109">Ha a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve az integrációs folyamat először a Finance and Operations és a Project Service Automation között történik majd ezt követően történik a projektköltség-kategóriák integrációs azonosítóinak szinkronizálása a Project Service Automation és Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="a77e7-109">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation, and then updating the project expense categories integration IDs by synchronizing from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="a77e7-110">Ha a projektköltség-kategóriák a Project Service Automation alkalmazásban vannak kezelve, az integrációs folyamat először a Project Service Automation és a Finance and Operations között történik.</span><span class="sxs-lookup"><span data-stu-id="a77e7-110">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="a77e7-111">A projektkategóriákat már előtt konfigurálni kell a Finance and Operations alkalmazásban, mielőtt szinkronizálná a Project Service Automation alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a77e7-111">The project categories must already be configured in Finance and Operations prior to the synchronization from Project Service Automation.</span></span> <span data-ttu-id="a77e7-112">Majd szinkronizálja vissza a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba, majd ismét a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a77e7-112">Then synchronize from Finance and Operations back to Project Service Automation and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="a77e7-113">Ez biztosítja a kategóriák kapcsolását, az ismétlődések elkerülését.</span><span class="sxs-lookup"><span data-stu-id="a77e7-113">This ensures the categories are linked and duplicates are not created.</span></span>

> [!NOTE]
> <span data-ttu-id="a77e7-114">Általában a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve.</span><span class="sxs-lookup"><span data-stu-id="a77e7-114">Typically, the project expense categories will be mastered in Finance and Operations.</span></span> <span data-ttu-id="a77e7-115">Ha nem ez a helyzet, vagy már létrehozott költségkategóriákat a Project Service Automation alkalmazásban , először szinkronizálnia kell a Projektköltség-tranzakció kategóriák használatával (PSA to Fin and Ops) használatával és majd szinkronizálnia kell a Projektköltség-tranzakció kategóriák (Fin and Ops to PSA) használatával.</span><span class="sxs-lookup"><span data-stu-id="a77e7-115">If that is not your situation, or you already have expense categories created in Project Service Automation, you must first sync using the Project expense transaction categories (PSA to Fin and Ops) and then sync using Project expense transaction categories (Fin and Ops to PSA).</span></span> <span data-ttu-id="a77e7-116">Ezután ismét futtatnia kell a PSA to Fin and Ops szinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="a77e7-116">You should then run the sync from PSA to Fin and Ops one more time.</span></span>

> <span data-ttu-id="a77e7-117">Ha a szinkronizálás a Project Service Automation alkalmazásból történik, a projektkategóriákat már be kell állítani a Finance and Operations alkalmazásban és minden olyan projektkategóriát, melyet szinkronizálni kell a Projektszolgáltatás-automatizálás kategóriában be kell állítani az **Aktív a naplókban**.</span><span class="sxs-lookup"><span data-stu-id="a77e7-117">If synchronizing first from Project Service Automation, the project categories must already be set up in Finance and Operations and any project categories that need to be synched with the Project Service Automation transaction categories must be set up to be **Active in journals**.</span></span>

<span data-ttu-id="a77e7-118">A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="a77e7-118">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="a77e7-119">[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="a77e7-119">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="a77e7-120">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="a77e7-120">Templates and tasks</span></span>

<span data-ttu-id="a77e7-121">A rendelkezésre álló sablonok eléréséhez a Microsoft PowerApps Admin Centerben válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="a77e7-121">To access available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="a77e7-122">A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Finance and Operations között és a Project Service Automation között:</span><span class="sxs-lookup"><span data-stu-id="a77e7-122">The following template and underlying task is used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="a77e7-123">**Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (Fin and Ops to PSA)</span><span class="sxs-lookup"><span data-stu-id="a77e7-123">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
-  <span data-ttu-id="a77e7-124">**A feladat neve a projektben** Sync categories to PSA (Kategóriák szinkronizálása PSA-ba)</span><span class="sxs-lookup"><span data-stu-id="a77e7-124">**Name of the task in the project:** Sync categories to PSA</span></span>

## <a name="entity-set"></a><span data-ttu-id="a77e7-125">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="a77e7-125">Entity set</span></span>

| <span data-ttu-id="a77e7-126">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a77e7-126">Finance and Operations</span></span>               | <span data-ttu-id="a77e7-127">Projekt szolgáltatásautomatizálása</span><span class="sxs-lookup"><span data-stu-id="a77e7-127">Project Service Automation</span></span>    |
|--------------------------------------|-------------------------------|
| <span data-ttu-id="a77e7-128">Integrációs entitás a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="a77e7-128">Integration entity for categories</span></span>    | <span data-ttu-id="a77e7-129">Tranzakciókategóriák.</span><span class="sxs-lookup"><span data-stu-id="a77e7-129">Transaction categories</span></span>        |

## <a name="entity-flow"></a><span data-ttu-id="a77e7-130">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="a77e7-130">Entity flow</span></span>

<span data-ttu-id="a77e7-131">Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.</span><span class="sxs-lookup"><span data-stu-id="a77e7-131">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="a77e7-132">Power Query</span><span class="sxs-lookup"><span data-stu-id="a77e7-132">Power Query</span></span>

<span data-ttu-id="a77e7-133">Microsoft Power Queryt kell használnia a számlázási típus beállításához a tranzakciókategórián, amikor a Project Service Automation alkalmazásba szinkronizál.</span><span class="sxs-lookup"><span data-stu-id="a77e7-133">You must use Microsoft Power Query to set the billing type on the transaction category when synchronizing to Project Service Automation.</span></span> <span data-ttu-id="a77e7-134">A Projektkiadás-tranzakció kategóriák (Fin and Ops to PSA) sablonban van egy alapértelmezett oszlop, és a hozzárendelés már rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="a77e7-134">The Project expense transaction categories (Fin and Ops to PSA) template has a default column and mapping already provided.</span></span> <span data-ttu-id="a77e7-135">Ha saját sablont hoz létre, hozzá kell adnia egy feltételes oszlopot a Power Query-ben.</span><span class="sxs-lookup"><span data-stu-id="a77e7-135">If you create your own template, you must add a conditional column in Power Query.</span></span>
- <span data-ttu-id="a77e7-136">Nyissa meg a Speciális lekérdezés és szűrés űrlapot a projektköltség-kategóriák feladat hozzárendelésében.</span><span class="sxs-lookup"><span data-stu-id="a77e7-136">Open the Advance Query and Filtering form from within the mapping of project expense categories task.</span></span>
- <span data-ttu-id="a77e7-137">Válassza a **Feltételes oszlop hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a77e7-137">Select **Add Conditional Column**.</span></span>
- <span data-ttu-id="a77e7-138">Adjon meg egy nevet az új oszlopnak, például BillingType.</span><span class="sxs-lookup"><span data-stu-id="a77e7-138">Give the new column a name, such as BillingType.</span></span>
- <span data-ttu-id="a77e7-139">Adja meg a következő feltételt: Ha **CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="a77e7-139">Enter the following condition: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
- <span data-ttu-id="a77e7-140">Kattintson a **OK** elemre az oszlopon.</span><span class="sxs-lookup"><span data-stu-id="a77e7-140">Click **OK** on the column.</span></span>
- <span data-ttu-id="a77e7-141">Ügyeljen arra, hogy ez az új oszlop hozzá legyen rendelve a hozzárendelés oldalon.</span><span class="sxs-lookup"><span data-stu-id="a77e7-141">Be sure to map this new column in the mapping page.</span></span>

<span data-ttu-id="a77e7-142">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="a77e7-142">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="a77e7-143">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Finance and Operations – Project Service Automation irányban.</span><span class="sxs-lookup"><span data-stu-id="a77e7-143">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="a77e7-144">[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="a77e7-144">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

<span data-ttu-id="a77e7-145">A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Project Service Automation és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="a77e7-145">The following template and underlying task is used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="a77e7-146">-**A sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (PSA to Fin and Ops) -**A feladat neve a projektben:** Kategóriák szinkronizálása a Fin Ops-ba</span><span class="sxs-lookup"><span data-stu-id="a77e7-146">-**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops) -**Name of the task in the project:** Sync categories to Fin Ops</span></span>

## <a name="entity-set"></a><span data-ttu-id="a77e7-147">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="a77e7-147">Entity set</span></span>

| <span data-ttu-id="a77e7-148">Projekt szolgáltatásautomatizálása</span><span class="sxs-lookup"><span data-stu-id="a77e7-148">Project Service Automation</span></span>      | <span data-ttu-id="a77e7-149">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a77e7-149">Finance and Operations</span></span>             |
|---------------------------------|------------------------------------|
| <span data-ttu-id="a77e7-150">Tranzakciókategóriák.</span><span class="sxs-lookup"><span data-stu-id="a77e7-150">Transaction categories</span></span>          | <span data-ttu-id="a77e7-151">Integrációs entitás a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="a77e7-151">Integration entity for categories</span></span>  | 

## <a name="entity-flow"></a><span data-ttu-id="a77e7-152">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="a77e7-152">Entity flow</span></span>

<span data-ttu-id="a77e7-153">Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.</span><span class="sxs-lookup"><span data-stu-id="a77e7-153">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="a77e7-154">Majd szinkronizálja vissza a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba, majd a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a77e7-154">The synchronization back to Finance and Operations updates the integration ID from Project Service Automation on the Finance and Operations project category.</span></span>

<span data-ttu-id="a77e7-155">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="a77e7-155">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="a77e7-156">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="a77e7-156">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="a77e7-157">[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="a77e7-157">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

