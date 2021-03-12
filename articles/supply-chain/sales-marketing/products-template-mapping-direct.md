---
title: A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management termékeinek közvetlenül a Dynamics 365 Sales szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: ecee843b6c09c86b4e40ab34cc113e5a7e7c76f8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977688"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a><span data-ttu-id="784b7-103">A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="784b7-103">Synchronize products directly from Supply Chain Management to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="784b7-104">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Microsoft Dataverse for Apps szolgáltatásban](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="784b7-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="784b7-105">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Supply Chain Management termékeinek közvetlenül a Dynamics 365 Sales szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="784b7-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="784b7-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="784b7-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="784b7-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="784b7-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="784b7-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákkal kapcsolatos adatok áramlását a Supply Chain Management és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="784b7-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="784b7-109">A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="784b7-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="784b7-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="784b7-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="784b7-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="784b7-111">Templates and tasks</span></span>

<span data-ttu-id="784b7-112">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [Power Apps Admin Centert](https://admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="784b7-112">To access the available templates, open [Power Apps Admin Center](https://admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="784b7-113">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="784b7-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="784b7-114">A következő sablonokat és alapul szolgáló feladatokat használják a termékek szinkronizálásához a Supply Chain Management és a Sales között:</span><span class="sxs-lookup"><span data-stu-id="784b7-114">The following template and underlying tasks are used to synchronize products from Supply Chain Management to Sales.</span></span>

- <span data-ttu-id="784b7-115">**Sablon neve az adatintegrációban:** Termékek (Supply Chain Management – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="784b7-115">**Name of the template in Data integration:** Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="784b7-116">**A feladat neve az adatintegrációs projektben:** Termékek</span><span class="sxs-lookup"><span data-stu-id="784b7-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="784b7-117">Szinkronizálási feladat nem szükséges a fiókszinkronizálás előtt.</span><span class="sxs-lookup"><span data-stu-id="784b7-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="784b7-118">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="784b7-118">Entity set</span></span>

| <span data-ttu-id="784b7-119">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="784b7-119">Supply Chain Management</span></span>    | <span data-ttu-id="784b7-120">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="784b7-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="784b7-121">Értékesíthető kiadott termékek</span><span class="sxs-lookup"><span data-stu-id="784b7-121">Sellable released products</span></span> | <span data-ttu-id="784b7-122">Termékek</span><span class="sxs-lookup"><span data-stu-id="784b7-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="784b7-123">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="784b7-123">Entity flow</span></span>

<span data-ttu-id="784b7-124">A termékek kezelése a Supply Chain Management történik, majd szinkronizálódnak a Sales programban.</span><span class="sxs-lookup"><span data-stu-id="784b7-124">Products are managed in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="784b7-125">A Supply Chain Management **Értékesíthető kiadott termékek** adatentitása csak *értékesíthető* termékeket exportál.</span><span class="sxs-lookup"><span data-stu-id="784b7-125">The **Sellable released products** data entity in Supply Chain Management exports only products that are *sellable*.</span></span> <span data-ttu-id="784b7-126">Az értékesíthető termékek olyan termékek, amelyek rendelkeznek az általuk megkövetelt információkkal annak érdekében, hogy azokat értékesítési rendelésekben használják.</span><span class="sxs-lookup"><span data-stu-id="784b7-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="784b7-127">Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve van az **Érvényesítés** funkcióval a **Kiadott termék** oldalon.</span><span class="sxs-lookup"><span data-stu-id="784b7-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="784b7-128">A termékszám kulcsként használható.</span><span class="sxs-lookup"><span data-stu-id="784b7-128">The product number is used as a key.</span></span> <span data-ttu-id="784b7-129">Ezért ha a termékváltozatok szinkronizálásra kerülnek a Sales-szel, minden termékváltozat egyedi termékazonosítóval rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="784b7-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="784b7-130">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="784b7-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="784b7-131">A Sales szolgáltatásba az új **Külsőleg karbantartott** mező került a termékekhez, amely azt jelzi, hogy a terméket külsőleg tartják karban.</span><span class="sxs-lookup"><span data-stu-id="784b7-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="784b7-132">Az érték alapértelmezésben **Igen** a Sales-be való importálás során.</span><span class="sxs-lookup"><span data-stu-id="784b7-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="784b7-133">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="784b7-133">The following values are available:</span></span>

- <span data-ttu-id="784b7-134">**Igen** – A termék a Supply Chain Management szolgáltatásból származik, és nem lesz szerkeszthető a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="784b7-134">**Yes** – The product originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="784b7-135">**Nem** – A terméket közvetlenül a Sales szolgáltatásban adták meg.</span><span class="sxs-lookup"><span data-stu-id="784b7-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="784b7-136">**(Üres)** – A termék már létezett a Sales szolgáltatásban a Potenciális ügyfelek készpénzre váltása engedélyezése előtt.</span><span class="sxs-lookup"><span data-stu-id="784b7-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="784b7-137">A **Külsőleg karbantartott** mező segít annak garantálásában, hogy csak azok az árajánlatok és értékesítési megbízások, amelyek külsőleg karbantartott termékeket tartalmaznak, szinkronizálnak a Supply Chain Management szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="784b7-137">The **Is Externally Maintained** field helps ensure that only quotations and sales orders that have externally maintained products will be synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="784b7-138">Külsőleg karbantartása termékek a program automatikusan hozzáadja az első érvényes árlista, ugyanabban a pénznemben.</span><span class="sxs-lookup"><span data-stu-id="784b7-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="784b7-139">Az árlisták betűrendben, név szerint vannak rendezve.</span><span class="sxs-lookup"><span data-stu-id="784b7-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="784b7-140">A Supply Chain Management termékeladási ára egyben az árlistán szereplő ár.</span><span class="sxs-lookup"><span data-stu-id="784b7-140">The product sales price from Supply Chain Management is used as the price on the price list.</span></span> <span data-ttu-id="784b7-141">Ezért győződjön meg arról, hogy tartozik árlista minden egyes Sales termékeladási pénznemhez a Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="784b7-141">Therefore, there must be a price list in Sales for every product sales currency in Supply Chain Management.</span></span> <span data-ttu-id="784b7-142">A felszabadított, eladható termékek pénznemét a jogi személy számviteli pénznemére kell beállítani, ahonnan a terméket exportálják.</span><span class="sxs-lookup"><span data-stu-id="784b7-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="784b7-143">A termékszinkronizálás nem fog sikerülni, hacsak nem létezik olyan árlista, amelynek megfelelő pénzneme van.</span><span class="sxs-lookup"><span data-stu-id="784b7-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="784b7-144">A használt árlista az integrációval szabályozható a pricelevelid.name [alapértelmezett árlista (név)] leképezésével az adatintegrációs projektben.</span><span class="sxs-lookup"><span data-stu-id="784b7-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="784b7-145">A beírásnál csak kisbetűk használhatók.</span><span class="sxs-lookup"><span data-stu-id="784b7-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="784b7-146">Például a „Szabványos” nevű értékesítési árlista alapértelmezetten ez lenne: Célmező: pricelevelid.name [alapértelmezett árlista (név)] és Leképezés típusa: [ { "transformType": "Default", "defaultValue": "standard" } ].</span><span class="sxs-lookup"><span data-stu-id="784b7-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="784b7-147">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="784b7-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="784b7-148">Mielőtt először futtatná a szinkronizálást, töltse ki az Egyedi terméktáblázatot a Supply Chain Management meglévő termékeihez.</span><span class="sxs-lookup"><span data-stu-id="784b7-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Supply Chain Management.</span></span> <span data-ttu-id="784b7-149">A feladat befejezéséig nem lesznek szinkronizálva a meglévő termékek.</span><span class="sxs-lookup"><span data-stu-id="784b7-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="784b7-150">A Supply Chain Management esetén akkor a keresés kereséséhez **feltöltése egyedi termék tábla**.</span><span class="sxs-lookup"><span data-stu-id="784b7-150">In Supply Chain Management, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="784b7-151">Válassza az **Egyedi termék tábla feltöltése** lehetőséget a feladat futtatásához.</span><span class="sxs-lookup"><span data-stu-id="784b7-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="784b7-152">Ez a feladat csak egyszer futtatható.</span><span class="sxs-lookup"><span data-stu-id="784b7-152">This job must be run only one time.</span></span>

- <span data-ttu-id="784b7-153">Győződjön meg róla, hogy megvan a szükséges értékhozzárendelés az értékesítési mértékegységre vonatkozóan a Supply Chain Management és a Sales között a **SalesUnitSymbol** **DefaultUnit (Name)** leképezésénél.</span><span class="sxs-lookup"><span data-stu-id="784b7-153">Make sure that the required value map for the selling unit of measure (UOM) between Supply Chain Management and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="784b7-154">Frissítse az **Egységcsoport** (**defaultuomscheduleid.name**) értékleképezését, hogy megegyezzen az **Egységcsoportok** értékével a Sales-ben.</span><span class="sxs-lookup"><span data-stu-id="784b7-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="784b7-155">A sablon alapértéke az **Alapértelmezett egység**.</span><span class="sxs-lookup"><span data-stu-id="784b7-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="784b7-156">Győződjön meg arról, hogy az összes termék értékesítési mértékegysége a Supply Chain Management szolgáltatásból létezik a Sales szolgáltatásban is.</span><span class="sxs-lookup"><span data-stu-id="784b7-156">Make sure that the selling UOMs for all products from Supply Chain Management exist in Sales.</span></span>
- <span data-ttu-id="784b7-157">Győződjön meg arról, hogy árlisták a Supply Chain Management minden termékeladási pénzneméhez léteznek a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="784b7-157">Make sure that price lists exist in Sales for every product sales currency in Supply Chain Management.</span></span>
- <span data-ttu-id="784b7-158">Amikor létrejönnek a termékek a Sales szolgáltatásban, akkor állapotuk **Sablon** vagy **Aktív** lehet.</span><span class="sxs-lookup"><span data-stu-id="784b7-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="784b7-159">A viselkedés ellenőrzése a **Beállítások** > **Felügyelet** > **Tendszerbeállítások** > **Értékesítés** pontban történik a Sales szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="784b7-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="784b7-160">A létrehozásukkor **Vázlat** állapotú termékeket aktiválni kell, mielőtt azok hozzáadhatók lennének az árajánlatokhoz vagy az értékesítési rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="784b7-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="784b7-161">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="784b7-161">Template mapping in Data integration</span></span>

<span data-ttu-id="784b7-162">Az alábbi ábrán sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="784b7-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="784b7-163">A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Supply Chain Management irányban.</span><span class="sxs-lookup"><span data-stu-id="784b7-163">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Sablonleképezés az adatintegrátorban](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="784b7-165">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="784b7-165">Related topics</span></span>

[<span data-ttu-id="784b7-166">A potenciális vevők készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="784b7-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="784b7-167">A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="784b7-167">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="784b7-168">A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="784b7-168">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="784b7-169">Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között</span><span class="sxs-lookup"><span data-stu-id="784b7-169">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="784b7-170">Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="784b7-170">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



