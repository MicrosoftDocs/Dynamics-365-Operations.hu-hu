---
title: Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Finance projektköltség kategóriáinak közvetlenül a Microsoft Dynamics 365 Project Service Automation szolgáltatásba történő szinkronizálására használatosak.
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
ms.openlocfilehash: 482febc91a04766216f9887ab59d30cc9aed5096
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250507"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="76cf0-103">Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között</span><span class="sxs-lookup"><span data-stu-id="76cf0-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="76cf0-104">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Finance projektköltség kategóriáinak közvetlenül a Dynamics 365 Project Service Automation szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="76cf0-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Dynamics 365 Finance and Dynamics 365 Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="76cf0-105">Ha a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat használhatja.</span><span class="sxs-lookup"><span data-stu-id="76cf0-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="76cf0-106">Tényleges integráció a 8.0.1 vagy újabb verzióiban érhető el.</span><span class="sxs-lookup"><span data-stu-id="76cf0-106">Actuals integration is available in version 8.0.1 or later.</span></span>
> - <span data-ttu-id="76cf0-107">Amennyiben az Enterprise edition 7.3.0-ás verziót használja, a KB 4132657 és KB 4132660 telepítését követően, használhat sablonokat projektfeladatok, kiadási tranzakciókategóriák, becsült órák, becsült kiadások és a tényleges értékek integrálásához, és a funkciók zárolásának beállításához.</span><span class="sxs-lookup"><span data-stu-id="76cf0-107">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="76cf0-108">Ha a könyvelési felosztásokat kell visszaállítania, ajánlott a KB 4131710 telepítése is.</span><span class="sxs-lookup"><span data-stu-id="76cf0-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance"></a><span data-ttu-id="76cf0-109">Adatáramlás a Project Service Automation és a Finance között</span><span class="sxs-lookup"><span data-stu-id="76cf0-109">Data flow for Project Service Automation and Finance</span></span>

<span data-ttu-id="76cf0-110">A Project Service Automation és a Finance közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance példányok közötti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="76cf0-110">The Project Service Automation and Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="76cf0-111">Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projektköltségtranzakció-kategóriákkal kapcsolatos adatáramlást a Project Service Automation és Finance alkalmazások között.</span><span class="sxs-lookup"><span data-stu-id="76cf0-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Project Service Automation.</span></span>

<span data-ttu-id="76cf0-112">Ha a projektköltség-kategóriák a Finance alkalmazásban vannak kezelve, az integrációs folyamat először a Finance és a Project Service Automation között történik.</span><span class="sxs-lookup"><span data-stu-id="76cf0-112">If the project expense categories are mastered in Finance, the integration flow is first from Finance to Project Service Automation.</span></span> <span data-ttu-id="76cf0-113">A projektköltség integrációs azonosítói ezt követően frissítve lesznek a Project Service Automation és a Finance közötti szinkronizálással.</span><span class="sxs-lookup"><span data-stu-id="76cf0-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance.</span></span>

<span data-ttu-id="76cf0-114">Ha a projektköltség-kategóriák a Project Service Automation alkalmazásban vannak kezelve, az integrációs folyamat először a Project Service Automation és a Finance között történik.</span><span class="sxs-lookup"><span data-stu-id="76cf0-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance.</span></span> <span data-ttu-id="76cf0-115">A projektkategóriákat már azelőtt konfigurálni kell a Finance alkalmazásban, mielőtt szinkronizálná a Project Service Automation alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="76cf0-115">The project categories must already be configured in Finance before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="76cf0-116">Majd szinkronizálja vissza a Finance alkalmazásból a Project Service Automation alkalmazásba, majd ismét a Project Service Automation alkalmazásból a Finance alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="76cf0-116">Then synchronize from Finance back to Project Service Automation, and then from Project Service Automation to Finance again.</span></span> <span data-ttu-id="76cf0-117">Ezzel a módszerrel segíthet garantálni, hogy a kategóriák kapcsolva legyenek és ne legyenek ismétlődő elemek létrehozva.</span><span class="sxs-lookup"><span data-stu-id="76cf0-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="76cf0-118">Általában a projektköltség-kategóriák a Finance alkalmazásban vannak kezelve.</span><span class="sxs-lookup"><span data-stu-id="76cf0-118">Typically, the project expense categories are mastered in Finance.</span></span> <span data-ttu-id="76cf0-119">Azonban ha nincsenek, vagy ha a költségkategóriák már létre lettek hozva a Project Service Automation alkalmazásban, először szinkronizálni kell a Projektkiadás-tranzakció kategóriák sablon használatával (Fin és Ops PSA).</span><span class="sxs-lookup"><span data-stu-id="76cf0-119">However, if they aren't, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="76cf0-120">Majd szinkronizálja a Projektköltség-tranzakció kategóriák (Fin and Ops to PSA) sablonnal</span><span class="sxs-lookup"><span data-stu-id="76cf0-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="76cf0-121">Még egyszer futtatnia kell a szinkronizálást a Project Service Automation és a Finance között.</span><span class="sxs-lookup"><span data-stu-id="76cf0-121">You should then run the synchronization from Project Service Automation to Finance one more time.</span></span>
>
> <span data-ttu-id="76cf0-122">Ha először a Project Service Automation alkalmazásból szinkronizál, az alábbi követelményeknek teljesülnie kell a Finance alkalmazásban a szinkronizálás futtatása előtt:</span><span class="sxs-lookup"><span data-stu-id="76cf0-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance before the synchronization is run:</span></span>
>
> - <span data-ttu-id="76cf0-123">A megosztott kategória, amely megfelel a projektkategóriának, amely be van állítva a Project Service Automation alkalmazásban léteznie kell, és is engedélyezni kell a **Projekthez** és **Költséghez** is.</span><span class="sxs-lookup"><span data-stu-id="76cf0-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="76cf0-124">Az egyes Finance jogi személyekhez, amelyeket integrálni kell, a következő projektkategóriáknak léteznie kell:</span><span class="sxs-lookup"><span data-stu-id="76cf0-124">For each Finance legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="76cf0-125">**Projektkategória** létezik.</span><span class="sxs-lookup"><span data-stu-id="76cf0-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="76cf0-126">**Használat a költségmodulban** engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="76cf0-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="76cf0-127">**Aktív a naplóban** engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="76cf0-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="76cf0-128">A **Tranzakciótípus** beállítása **Kiadás**.</span><span class="sxs-lookup"><span data-stu-id="76cf0-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="76cf0-129">A következő ábra bemutatja a Project Service Automation és a Finance közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="76cf0-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="76cf0-130">[![Adatáramlás a Project Service Automation és a Finance integrációjához](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="76cf0-130">[![Data flow for Project Service Automation integration with Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a><span data-ttu-id="76cf0-131">Projekt költségkategóriák szinkronizálása a Finance alkalmazásból a Project Service Automation alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="76cf0-131">Project expense category synchronization from Finance to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="76cf0-132">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="76cf0-132">Template and task</span></span>

<span data-ttu-id="76cf0-133">A rendelkezésre álló sablon eléréséhez a Microsoft PowerApps adminisztrációs központban válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="76cf0-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="76cf0-134">A következő sablon és az alapul szolgáló feladat használható a projektköltség-kategóriák szinkronizálásához a Project Service Automation és a Finance között:</span><span class="sxs-lookup"><span data-stu-id="76cf0-134">The following template and underlying task are used to synchronize project expense categories from Finance to Project Service Automation:</span></span>

- <span data-ttu-id="76cf0-135">**Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (Fin and Ops to PSA)</span><span class="sxs-lookup"><span data-stu-id="76cf0-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="76cf0-136">**A feladat neve a projektben** Sync categories to PSA (Kategóriák szinkronizálása PSA-ba)</span><span class="sxs-lookup"><span data-stu-id="76cf0-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="76cf0-137">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="76cf0-137">Entity set</span></span>

| <span data-ttu-id="76cf0-138">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="76cf0-138">Finance</span></span>                           | <span data-ttu-id="76cf0-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="76cf0-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="76cf0-140">Integrációs entitás a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="76cf0-140">Integration entity for categories</span></span> | <span data-ttu-id="76cf0-141">Tranzakciókategóriák.</span><span class="sxs-lookup"><span data-stu-id="76cf0-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="76cf0-142">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="76cf0-142">Entity flow</span></span>

<span data-ttu-id="76cf0-143">Projektköltség-kategóriák kezelése a Finance alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.</span><span class="sxs-lookup"><span data-stu-id="76cf0-143">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="76cf0-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="76cf0-144">Power Query</span></span>

<span data-ttu-id="76cf0-145">Microsoft Power Queryt for Excelt kell használnia a számlázási típus beállításához a tranzakciókategórián, amikor a Project Service Automation alkalmazásba szinkronizál.</span><span class="sxs-lookup"><span data-stu-id="76cf0-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="76cf0-146">A Projektkiadás-tranzakció kategóriák (Fin and Ops to PSA) sablonban található egy alapértelmezett oszlop, és a hozzárendelés már rendelkezésre áll.</span><span class="sxs-lookup"><span data-stu-id="76cf0-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="76cf0-147">Ha saját sablont hoz létre, hozzá kell adnia egy feltételes oszlopot a Power Query-ben.</span><span class="sxs-lookup"><span data-stu-id="76cf0-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="76cf0-148">Kövesse ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="76cf0-148">Follow these steps.</span></span>

1. <span data-ttu-id="76cf0-149">Kattintson a nyílra a projekt költség-kategóriák hozzárendelésének megnyitásához a Projektköltség-tranzakció kategóriák t (Fin és a PSA Ops) sablonban.</span><span class="sxs-lookup"><span data-stu-id="76cf0-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="76cf0-150">Kattintson a **Speciális lekérdezés és szűrés** hivatkozásra a Power Query megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="76cf0-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="76cf0-151">Válassza a **Feltételes oszlop hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="76cf0-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="76cf0-152">Adjon meg egy nevet az új oszlopnak, például **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="76cf0-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="76cf0-153">Adja meg a következő feltételt: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="76cf0-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="76cf0-154">Kattintson a **OK** elemre az oszlopon.</span><span class="sxs-lookup"><span data-stu-id="76cf0-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="76cf0-155">Ügyeljen arra, hogy ez az új oszlop hozzá legyen rendelve a hozzárendelés oldalon.</span><span class="sxs-lookup"><span data-stu-id="76cf0-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="76cf0-156">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="76cf0-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="76cf0-157">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Finance – Project Service Automation irányban.</span><span class="sxs-lookup"><span data-stu-id="76cf0-157">The mapping shows the field information that will be synchronized from Finance to Project Service Automation.</span></span>

<span data-ttu-id="76cf0-158">[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="76cf0-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a><span data-ttu-id="76cf0-159">Projekt költségkategóriák szinkronizálása a Project Service Automation alkalmazásból a Finance alkalmazásba</span><span class="sxs-lookup"><span data-stu-id="76cf0-159">Project expense category synchronization from Project Service Automation to Finance</span></span>

### <a name="template-and-task"></a><span data-ttu-id="76cf0-160">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="76cf0-160">Template and task</span></span>

<span data-ttu-id="76cf0-161">A következő sablon és az alapul szolgáló feladat használható a projektköltség-kategóriák szinkronizálásához a Project Service Automation és a Finance között:</span><span class="sxs-lookup"><span data-stu-id="76cf0-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="76cf0-162">**Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (PSA to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="76cf0-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="76cf0-163">**A feladat neve a projektben** Sync categories to Fin Ops (Kategóriák szinkronizálása Fin Ops-ba)</span><span class="sxs-lookup"><span data-stu-id="76cf0-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="76cf0-164">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="76cf0-164">Entity set</span></span>

| <span data-ttu-id="76cf0-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="76cf0-165">Project Service Automation</span></span> | <span data-ttu-id="76cf0-166">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="76cf0-166">Finance</span></span>                           |
|----------------------------|-----------------------------------|
| <span data-ttu-id="76cf0-167">Tranzakciókategóriák.</span><span class="sxs-lookup"><span data-stu-id="76cf0-167">Transaction categories</span></span>     | <span data-ttu-id="76cf0-168">Integrációs entitás a kategóriákhoz</span><span class="sxs-lookup"><span data-stu-id="76cf0-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="76cf0-169">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="76cf0-169">Entity flow</span></span>

<span data-ttu-id="76cf0-170">Projektköltség-kategóriák kezelése a Finance alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.</span><span class="sxs-lookup"><span data-stu-id="76cf0-170">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="76cf0-171">A visszaszinkronizálás Finance alkalmazásba frissíti a projektkategóriát a Finance alkalmazásban a Project Service Automation alkalmazás integrációs azonosítójával.</span><span class="sxs-lookup"><span data-stu-id="76cf0-171">The synchronization back to Finance updates the project category in Finance with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="76cf0-172">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="76cf0-172">Template mapping in Data integration</span></span>

<span data-ttu-id="76cf0-173">Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban</span><span class="sxs-lookup"><span data-stu-id="76cf0-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="76cf0-174">A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.</span><span class="sxs-lookup"><span data-stu-id="76cf0-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="76cf0-175">[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="76cf0-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
