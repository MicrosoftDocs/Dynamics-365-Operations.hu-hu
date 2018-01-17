---
title: "A Finance and Operations-termékek szinkronizálása a Sales-termékekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: b949701604d0cbca2728a0055d52f7385106082b
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="3229c-103">A Finance and Operations-termékek szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="3229c-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="3229c-104">A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="3229c-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="3229c-105">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="3229c-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="3229c-106">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="3229c-106">Template and task</span></span>

<span data-ttu-id="3229c-107">A következő sablonok és kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="3229c-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="3229c-108">Sablon neve: Termékek (Fin and Ops – Sales)</span><span class="sxs-lookup"><span data-stu-id="3229c-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="3229c-109">A projektben lévő feladat neve: Termékek</span><span class="sxs-lookup"><span data-stu-id="3229c-109">Name of task in project: Products</span></span>

<span data-ttu-id="3229c-110">Szinkronizálási feladatok szükségessége a termékszinkronizálás előtt: Nincs</span><span class="sxs-lookup"><span data-stu-id="3229c-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="3229c-111">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="3229c-111">Entity set</span></span>

| <span data-ttu-id="3229c-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="3229c-112">**Finance and Operations**</span></span> | <span data-ttu-id="3229c-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="3229c-113">**CDS**</span></span> | <span data-ttu-id="3229c-114">**Értékesítések**</span><span class="sxs-lookup"><span data-stu-id="3229c-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="3229c-115">Értékesíthető kiadott termékek</span><span class="sxs-lookup"><span data-stu-id="3229c-115">Sellable released products</span></span> | <span data-ttu-id="3229c-116">Termék</span><span class="sxs-lookup"><span data-stu-id="3229c-116">Product</span></span> | <span data-ttu-id="3229c-117">Termékek</span><span class="sxs-lookup"><span data-stu-id="3229c-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="3229c-118">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="3229c-118">Entity flow</span></span>

<span data-ttu-id="3229c-119">A termékek kezelése a Finance and Operationsben történik, majd szinkronizálás történik a Sales programmal.</span><span class="sxs-lookup"><span data-stu-id="3229c-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="3229c-120">A Finance and Operations **Értékesíthető kiadott termékek** adatentitása csak olyan termékeket exportál, amelyek eladhatók, ami azt jelenti, hogy a termékek rendelkeznek az értékesítési rendeléshez szükséges információkkal.</span><span class="sxs-lookup"><span data-stu-id="3229c-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="3229c-121">Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve a **érvényesítése** működni a **megjelent termék** oldalon.</span><span class="sxs-lookup"><span data-stu-id="3229c-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="3229c-122">A **termékszám** szolgál a kulcs, ami azt jelenti, változatok CD-és értékesítési szinkronizálta egyedi termék **termék azonosítók** / **termékváltozat**.</span><span class="sxs-lookup"><span data-stu-id="3229c-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="3229c-123">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="3229c-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="3229c-124">Az értékesítési, a termékek új mezőt **külsőleg megmarad** hozzáadódik jelezheti, hogy egy adott termék külsőleg tarthatók karban.</span><span class="sxs-lookup"><span data-stu-id="3229c-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="3229c-125">Az érték **Igen** értékesítési importálás során alapértelmezés szerint.</span><span class="sxs-lookup"><span data-stu-id="3229c-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="3229c-126">**Külsőleg karbantartani van = Yes**: termék származik, pénzügyi és a műveletek, és nem lesz szerkeszthető az értékesítésben.</span><span class="sxs-lookup"><span data-stu-id="3229c-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="3229c-127">**Külsőleg karbantartani van = nem**: termék közvetlenül az értékesítési kerül.</span><span class="sxs-lookup"><span data-stu-id="3229c-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="3229c-128">**Külsőleg karbantartani van = üres**: termék létezik az értékesítésben a potenciális vevő készpénzfizetési Solution engedélyezése előtt.</span><span class="sxs-lookup"><span data-stu-id="3229c-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="3229c-129">A **külsőleg megmarad** adatok annak biztosítására, hogy csak a **ajánlatok** és **értékesítési rendelések** tartalmazó **külsőleg karbantartása termékek** késedelmi a műveletekhez pedig szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="3229c-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="3229c-130">**Külsőleg karbantartása termékek** a program automatikusan hozzáadja az első érvényes **árlista**, ugyanabban a pénznemben.</span><span class="sxs-lookup"><span data-stu-id="3229c-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="3229c-131">Megjegyzés: a lista betűrend szerint vannak rendezve **neve**.</span><span class="sxs-lookup"><span data-stu-id="3229c-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="3229c-132">Pénzügy és a műveletek a termék eladási ára ár egyben az a **árlista**.</span><span class="sxs-lookup"><span data-stu-id="3229c-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="3229c-133">Ez azt jelenti, hogy szükséges a **árlista** minden egyes értékesítési **termék értékesítési pénznem** Finance and Operationset.</span><span class="sxs-lookup"><span data-stu-id="3229c-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="3229c-134">A kiadott termékhez árusítási pénznem a jogi személynél, amelyből a termék exportálja a könyvelési pénznemben van beállítva.</span><span class="sxs-lookup"><span data-stu-id="3229c-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="3229c-135">Termék szinkronizálás nélkül nem fog sikerülni egy **árlista** a megfelelő pénznemben.</span><span class="sxs-lookup"><span data-stu-id="3229c-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="3229c-136">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="3229c-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="3229c-137">Mielőtt futtatná a legelső szinkronizálás, ki kell tölteni a **egyedi termék tábla** pénzügyi és a műveletek a meglévő termékek.</span><span class="sxs-lookup"><span data-stu-id="3229c-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="3229c-138">Ez a feladat befejezéséig nem lesz szinkronizálva meglévő terméken.</span><span class="sxs-lookup"><span data-stu-id="3229c-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="3229c-139">A Finance and Operations esetén akkor a keresés kereséséhez **feltöltése egyedi termék tábla**.</span><span class="sxs-lookup"><span data-stu-id="3229c-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="3229c-140">Kattintson az **Egyedi termék tábla feltöltése** lehetőségre a feladat futtatásához.</span><span class="sxs-lookup"><span data-stu-id="3229c-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="3229c-141">Ezt a feladatot csak egyszer kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="3229c-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="3229c-142">Győződjön meg arról, hogy a szükséges **ValueMap** értékesítési **mértékegység** (Mértékegységet) Finance and Operations szerepel a **forrás -\> SalesUnitSymbol leképezése CD / DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="3229c-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="3229c-143">CD szervezeti azonosító frissítése: **Organization_OrganizationId** található a **forrás \>CD** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="3229c-143">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="3229c-144">A sablon alapértéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="3229c-144">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="3229c-145">Frissítés **ValueMap** a **egység csoport** (**defaultuomscheduleid.name**) a **CD -\> cél** megfelelően a **csoportjai** értékesítési.</span><span class="sxs-lookup"><span data-stu-id="3229c-145">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="3229c-146">A sablon alapértéke az **Alapértelmezett egység**.</span><span class="sxs-lookup"><span data-stu-id="3229c-146">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="3229c-147">Ellenőrizze, hogy az összes termék UOMs eladási késedelmi és műveletek értékesítés szerepel-e a **CD választási listák** értéke.</span><span class="sxs-lookup"><span data-stu-id="3229c-147">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="3229c-148">Győződjön meg arról, hogy **árlisták** minden egyes pénznemhez termék eladási késedelmi és műveletek értékesítési szerepel.</span><span class="sxs-lookup"><span data-stu-id="3229c-148">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="3229c-149">Termékek hozhatja létre az értékesítési állapot **"vázlat"** vagy **aktív**.</span><span class="sxs-lookup"><span data-stu-id="3229c-149">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="3229c-150">Ez **rendszerbeállítások** alapján **értékesítési** értékesítés.</span><span class="sxs-lookup"><span data-stu-id="3229c-150">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="3229c-151">Vázlat állapotú létrehozott termékeket kell aktiválni kell, mielőtt azok adhatók hozzá **ajánlat** vagy **eladási rendelés**.</span><span class="sxs-lookup"><span data-stu-id="3229c-151">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="3229c-152">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="3229c-152">Template mapping in data integrator</span></span>

<span data-ttu-id="3229c-153">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="3229c-153">The following illustrations show an example of a template mapping in data integrator.</span></span>

![sablonleképezés az adatintegrátorban](./media/products-template-mapping-data-integrator-1.png)

![sablonleképezés a termékekhez az adatintegrátorban](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="3229c-156">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="3229c-156">Related topics</span></span>

[<span data-ttu-id="3229c-157">A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="3229c-157">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="3229c-158">A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="3229c-158">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="3229c-159">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="3229c-159">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="3229c-160">Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="3229c-160">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="3229c-161">Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="3229c-161">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


