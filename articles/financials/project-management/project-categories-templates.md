---
title: Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektköltség kategóriáinak közvetlenül a Microsoft Dynamics 365 for Project Service Automation szolgáltatásba történő szinkronizálására használatosak.
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
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 90d640bb3eea909238b4ff032fcdb3854014e65e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838367"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="18c09-103">Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között</span><span class="sxs-lookup"><span data-stu-id="18c09-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="18c09-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Finance and Operations projektköltség kategóriáinak közvetlenül a Microsoft Dynamics 365 for Project Service Automation szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="18c09-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="18c09-105">Ha a Microsoft Dynamics 365 for Finance and Operations 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="18c09-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in Microsoft Dynamics 365 for Finance and Operations version 8.0.</span></span>
> - <span data-ttu-id="18c09-106">Tényleges integráció a Microsoft Dynamics 365 for Finance and Operations 8.0.1 vagy újabb verzióiban érhető el.</span><span class="sxs-lookup"><span data-stu-id="18c09-106">Actuals integration is available in Microsoft Dynamics 365 for Finance and Operations version 8.0.1 or later.</span></span>
> - <span data-ttu-id="18c09-107">Amennyiben a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához.</span><span class="sxs-lookup"><span data-stu-id="18c09-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="18c09-108">Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.</span><span class="sxs-lookup"><span data-stu-id="18c09-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="18c09-109">Adatáramlás a Project Service Automation és a Finance and Operations esetében</span><span class="sxs-lookup"><span data-stu-id="18c09-109">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="18c09-110">A Project Service Automation és a Finance and Operations közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance and Operations példányok közötti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="18c09-110">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="18c09-111">Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projektköltségtranzakció-kategóriákkal kapcsolatos adatáramlást a Project Service Automation és Finance and Operations alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="18c09-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="18c09-112">Ha a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve, az integrációs folyamat először a Finance and Operations és a Project Service Automation között történik.</span><span class="sxs-lookup"><span data-stu-id="18c09-112">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation.</span></span> <span data-ttu-id="18c09-113">A projektköltség integrációs azonosítói ezt követően frissítve lesznek a Project Service Automation és a Finance and Operations közötti szinkronizálással.</span><span class="sxs-lookup"><span data-stu-id="18c09-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="18c09-114">Ha a projektköltség-kategóriák a Project Service Automation alkalmazásban vannak kezelve, az integrációs folyamat először a Project Service Automation és a Finance and Operations között történik.</span><span class="sxs-lookup"><span data-stu-id="18c09-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="18c09-115">A projektkategóriákat már azelőtt konfigurálni kell a Finance and Operations alkalmazásban, mielőtt szinkronizálná a Project Service Automation alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="18c09-115">The project categories must already be configured in Finance and Operations before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="18c09-116">Majd szinkronizálja vissza a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba, majd ismét a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="18c09-116">Then synchronize from Finance and Operations back to Project Service Automation, and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="18c09-117">Ezzel a módszerrel segíthet garantálni, hogy a kategóriák kapcsolva legyenek és ne legyenek ismétlődő elemek létrehozva.</span><span class="sxs-lookup"><span data-stu-id="18c09-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="18c09-118">Általában a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve.</span><span class="sxs-lookup"><span data-stu-id="18c09-118">Typically, the project expense categories are mastered in Finance and Operations.</span></span> <span data-ttu-id="18c09-119">Azonban, ha azok nem a Finance and Operations alkalmazásban vannak kezelve, vagy a költségkategóriák már létre lettek hozva a Project Service Automation alkalmazásban, először szinkronizálni kell a Projektkiadás-tranzakció kategóriák sablon használatával (Fin és Ops PSA).</span><span class="sxs-lookup"><span data-stu-id="18c09-119">However, if they aren't mastered in Finance and Operations, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="18c09-120">Majd szinkronizálja a Projektköltség-tranzakció kategóriák (Fin and Ops to PSA) sablonnal</span><span class="sxs-lookup"><span data-stu-id="18c09-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="18c09-121">Még egyszer futtatnia kell a szinkronizálást a Project Service Automation és a Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="18c09-121">You should then run the synchronization from Project Service Automation to Finance and Operations one more time.</span></span>
>
> <span data-ttu-id="18c09-122">Ha először a Project Service Automation alkalmazásból szinkronizál, az alábbi követelményeknek teljesülnie kell a Finance and Operations alkalmazásban a szinkronizálás futtatása előtt:</span><span class="sxs-lookup"><span data-stu-id="18c09-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance and Operations before the synchronization is run:</span></span>
>
> - <span data-ttu-id="18c09-123">A megosztott kategória, amely megfelel a projektkategóriának, amely be van állítva a Project Service Automation alkalmazásban léteznie kell, és is engedélyezni kell a **Projekthez** és **Költséghez** is.</span><span class="sxs-lookup"><span data-stu-id="18c09-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="18c09-124">Az egyes Finance and Operations jogi személyekhez, amelyeket integrálni kell, a következő projektkategóriáknak léteznie kell:</span><span class="sxs-lookup"><span data-stu-id="18c09-124">For each Finance and Operations legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="18c09-125">**Projektkategória** létezik.</span><span class="sxs-lookup"><span data-stu-id="18c09-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="18c09-126">**Használat a költségmodulban** engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="18c09-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="18c09-127">**Aktív a naplóban** engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="18c09-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="18c09-128">A **Tranzakciótípus** beállítása **Kiadás**.</span><span class="sxs-lookup"><span data-stu-id="18c09-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="18c09-129">A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="18c09-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="18c09-130">[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="18c09-130">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a><span data-ttu-id="18c09-131">Projekt költségkategóriák szinkronizálása a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="18c09-131">Project expense category synchronization from Finance and Operations to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="18c09-132">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="18c09-132">Template and task</span></span>

<span data-ttu-id="18c09-133">A rendelkezésre álló sablon eléréséhez a Microsoft PowerApps adminisztrációs központban válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="18c09-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="18c09-134">A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Finance and Operations között és a Project Service Automation között:</span><span class="sxs-lookup"><span data-stu-id="18c09-134">The following template and underlying task are used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

- <span data-ttu-id="18c09-135">**Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (Fin and Ops to PSA)</span><span class="sxs-lookup"><span data-stu-id="18c09-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="18c09-136">**A feladat neve a projektben** Sync categories to PSA (Kategóriák szinkronizálása PSA-ba)</span><span class="sxs-lookup"><span data-stu-id="18c09-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="18c09-137">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="18c09-137">Entity set</span></span>

| <span data-ttu-id="18c09-138">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="18c09-138">Finance and Operations</span></span>            | <span data-ttu-id="18c09-139">Projekt szolgáltatásautomatizálása</span><span class="sxs-lookup"><span data-stu-id="18c09-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="18c09-140">Integrációs entitás a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="18c09-140">Integration entity for categories</span></span> | <span data-ttu-id="18c09-141">Tranzakciókategóriák.</span><span class="sxs-lookup"><span data-stu-id="18c09-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="18c09-142">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="18c09-142">Entity flow</span></span>

<span data-ttu-id="18c09-143">Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.</span><span class="sxs-lookup"><span data-stu-id="18c09-143">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="18c09-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="18c09-144">Power Query</span></span>

<span data-ttu-id="18c09-145">Microsoft Power Queryt for Excelt kell használnia a számlázási típus beállításához a tranzakciókategórián, amikor a Project Service Automation alkalmazásba szinkronizál.</span><span class="sxs-lookup"><span data-stu-id="18c09-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="18c09-146">A Projektkiadás-tranzakció kategóriák (Fin and Ops to PSA) sablonban található egy alapértelmezett oszlop, és a hozzárendelés már rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="18c09-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="18c09-147">Ha saját sablont hoz létre, hozzá kell adnia egy feltételes oszlopot a Power Query-ben.</span><span class="sxs-lookup"><span data-stu-id="18c09-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="18c09-148">Kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="18c09-148">Follow these steps.</span></span>

1. <span data-ttu-id="18c09-149">Kattintson a nyílra a projekt költség-kategóriák hozzárendelésének megnyitásához a Projektköltség-tranzakció kategóriák t (Fin és a PSA Ops) sablonban.</span><span class="sxs-lookup"><span data-stu-id="18c09-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="18c09-150">Kattintson a **Speciális lekérdezés és szűrés** hivatkozásra a Power Query megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="18c09-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="18c09-151">Válassza a **Feltételes oszlop hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="18c09-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="18c09-152">Adjon meg egy nevet az új oszlopnak, például **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="18c09-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="18c09-153">Adja meg a következő feltételt: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="18c09-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="18c09-154">Kattintson a **OK** elemre az oszlopon.</span><span class="sxs-lookup"><span data-stu-id="18c09-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="18c09-155">Ügyeljen arra, hogy ez az új oszlop hozzá legyen rendelve a hozzárendelés oldalon.</span><span class="sxs-lookup"><span data-stu-id="18c09-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="18c09-156">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="18c09-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="18c09-157">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Finance and Operations – Project Service Automation irányban.</span><span class="sxs-lookup"><span data-stu-id="18c09-157">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="18c09-158">[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="18c09-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="18c09-159">Projekt költségkategóriák szinkronizálása a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="18c09-159">Project expense category synchronization from Project Service Automation to Finance and Operations</span></span>

### <a name="template-and-task"></a><span data-ttu-id="18c09-160">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="18c09-160">Template and task</span></span>

<span data-ttu-id="18c09-161">A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Project Service Automation és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="18c09-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

- <span data-ttu-id="18c09-162">**Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="18c09-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="18c09-163">**A feladat neve a projektben** Sync categories to Fin Ops (Kategóriák szinkronizálása Fin Ops-ba)</span><span class="sxs-lookup"><span data-stu-id="18c09-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="18c09-164">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="18c09-164">Entity set</span></span>

| <span data-ttu-id="18c09-165">Projekt szolgáltatásautomatizálása</span><span class="sxs-lookup"><span data-stu-id="18c09-165">Project Service Automation</span></span> | <span data-ttu-id="18c09-166">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="18c09-166">Finance and Operations</span></span>            |
|----------------------------|-----------------------------------|
| <span data-ttu-id="18c09-167">Tranzakciókategóriák.</span><span class="sxs-lookup"><span data-stu-id="18c09-167">Transaction categories</span></span>     | <span data-ttu-id="18c09-168">Integrációs entitás a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="18c09-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="18c09-169">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="18c09-169">Entity flow</span></span>

<span data-ttu-id="18c09-170">Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.</span><span class="sxs-lookup"><span data-stu-id="18c09-170">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="18c09-171">A visszaszinkronizálás Finance and Operations alkalmazásba frissíti a projektkategóriát a Finance and Operations alkalmazásban a Project Service Automation alkalmazás integrációs azonosítójával.</span><span class="sxs-lookup"><span data-stu-id="18c09-171">The synchronization back to Finance and Operations updates the project category in Finance and Operations with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="18c09-172">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="18c09-172">Template mapping in Data integration</span></span>

<span data-ttu-id="18c09-173">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="18c09-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="18c09-174">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="18c09-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="18c09-175">[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="18c09-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
