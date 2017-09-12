---
title: "A Finance and Operations-termékek szinkronizálása a Sales-termékekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="3e270-103">A Finance and Operations-termékek szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="3e270-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="3e270-104">A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="3e270-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="3e270-105">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="3e270-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="3e270-106">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="3e270-106">Template and task</span></span>

<span data-ttu-id="3e270-107">A következő sablonok és kapcsolódó feladatok a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók.</span><span class="sxs-lookup"><span data-stu-id="3e270-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="3e270-108">Sablon neve: Termékek (Fin and Ops – Sales)</span><span class="sxs-lookup"><span data-stu-id="3e270-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="3e270-109">A projektben lévő feladat neve: Termékek</span><span class="sxs-lookup"><span data-stu-id="3e270-109">Name of task in project: Products</span></span>

<span data-ttu-id="3e270-110">Szinkronizálási feladatok szükségessége a termékszinkronizálás előtt: Nincs</span><span class="sxs-lookup"><span data-stu-id="3e270-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="3e270-111">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="3e270-111">Entity set</span></span>

| <span data-ttu-id="3e270-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="3e270-112">**Finance and Operations**</span></span> | <span data-ttu-id="3e270-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="3e270-113">**CDS**</span></span> | <span data-ttu-id="3e270-114">**Értékesítések**</span><span class="sxs-lookup"><span data-stu-id="3e270-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="3e270-115">Értékesíthető kiadott termékek</span><span class="sxs-lookup"><span data-stu-id="3e270-115">Sellable released products</span></span> | <span data-ttu-id="3e270-116">Termék</span><span class="sxs-lookup"><span data-stu-id="3e270-116">Product</span></span> | <span data-ttu-id="3e270-117">Termékek</span><span class="sxs-lookup"><span data-stu-id="3e270-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="3e270-118">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="3e270-118">Entity flow</span></span>

<span data-ttu-id="3e270-119">A termékek kezelése a Finance and Operationsben történik, majd szinkronizálás történik a Sales programmal.</span><span class="sxs-lookup"><span data-stu-id="3e270-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="3e270-120">A Finance and Operations **Értékesíthető kiadott termékek** adatentitása csak olyan termékeket exportál, amelyek eladhatók, ami azt jelenti, hogy a termékek rendelkeznek az értékesítési rendeléshez szükséges információkkal.</span><span class="sxs-lookup"><span data-stu-id="3e270-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="3e270-121">Ugyanazok a szabályok vonatkoznak, ha egy termék ellenőrizve a **érvényesítése** működni a **megjelent termék** oldalon.</span><span class="sxs-lookup"><span data-stu-id="3e270-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="3e270-122">A **termékszám** szolgál a kulcs, ami azt jelenti, változatok CD-és értékesítési szinkronizálta egyedi termék **termék azonosítók** / **termékváltozat**.</span><span class="sxs-lookup"><span data-stu-id="3e270-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="3e270-123">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="3e270-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="3e270-124">Az értékesítési, a termékek új mezőt **külsőleg megmarad** hozzáadódik jelezheti, hogy egy adott termék külsőleg tarthatók karban.</span><span class="sxs-lookup"><span data-stu-id="3e270-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="3e270-125">Az érték **Igen** értékesítési importálás során alapértelmezés szerint.</span><span class="sxs-lookup"><span data-stu-id="3e270-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="3e270-126">**Külsőleg karbantartani van = Yes**: termék származik, pénzügyi és a műveletek, és nem lesz szerkeszthető az értékesítésben.</span><span class="sxs-lookup"><span data-stu-id="3e270-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="3e270-127">**Külsőleg karbantartani van = nem**: termék közvetlenül az értékesítési kerül.</span><span class="sxs-lookup"><span data-stu-id="3e270-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="3e270-128">**Külsőleg karbantartani van = üres**: termék létezik az értékesítésben a potenciális vevő készpénzfizetési Solution engedélyezése előtt.</span><span class="sxs-lookup"><span data-stu-id="3e270-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="3e270-129">A **külsőleg megmarad** adatok annak biztosítására, hogy csak a **ajánlatok** és **értékesítési rendelések** tartalmazó **külsőleg karbantartása termékek** késedelmi a műveletekhez pedig szinkronizálja.</span><span class="sxs-lookup"><span data-stu-id="3e270-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="3e270-130">**Külsőleg karbantartása termékek** a program automatikusan hozzáadja az első érvényes **árlista**, ugyanabban a pénznemben.</span><span class="sxs-lookup"><span data-stu-id="3e270-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="3e270-131">Megjegyzés: a lista betűrend szerint vannak rendezve **neve**.</span><span class="sxs-lookup"><span data-stu-id="3e270-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="3e270-132">Pénzügy és a műveletek a termék eladási ára ár egyben az a **árlista**.</span><span class="sxs-lookup"><span data-stu-id="3e270-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="3e270-133">Ez azt jelenti, hogy szükséges a **árlista** minden egyes értékesítési **termék értékesítési pénznem** Finance and Operationset.</span><span class="sxs-lookup"><span data-stu-id="3e270-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="3e270-134">A kiadott termékhez árusítási pénznem a jogi személynél, amelyből a termék exportálja a könyvelési pénznemben van beállítva.</span><span class="sxs-lookup"><span data-stu-id="3e270-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="3e270-135">Termék szinkronizálás nélkül nem fog sikerülni egy **árlista** a megfelelő pénznemben.</span><span class="sxs-lookup"><span data-stu-id="3e270-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="3e270-136">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="3e270-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="3e270-137">Mielőtt futtatná a legelső szinkronizálás, ki kell tölteni a **egyedi termék tábla** pénzügyi és a műveletek a meglévő termékek.</span><span class="sxs-lookup"><span data-stu-id="3e270-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="3e270-138">Ez a feladat befejezéséig nem lesz szinkronizálva meglévő terméken.</span><span class="sxs-lookup"><span data-stu-id="3e270-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="3e270-139">A Finance and Operations esetén akkor a keresés kereséséhez **feltöltése egyedi termék tábla**.</span><span class="sxs-lookup"><span data-stu-id="3e270-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="3e270-140">Kattintson az **Egyedi termék tábla feltöltése** lehetőségre a feladat futtatásához.</span><span class="sxs-lookup"><span data-stu-id="3e270-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="3e270-141">Ezt a feladatot csak egyszer kell futtatni.</span><span class="sxs-lookup"><span data-stu-id="3e270-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="3e270-142">Győződjön meg arról, hogy a szükséges **ValueMap** értékesítési **mértékegység** (Mértékegységet) Finance and Operations szerepel a **forrás -\> SalesUnitSymbol leképezése CD / DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="3e270-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="3e270-143">Győződjön meg arról, hogy **tizedesjegyek** mértékegység a saját igényeinek a **CD -\> cél**.</span><span class="sxs-lookup"><span data-stu-id="3e270-143">Ensure that **Decimals supported** for UOM match your requirements in **CDS -\> Destination**.</span></span> <span data-ttu-id="3e270-144">Ha különböző értékeket a mértékegység van szüksége, ez nem végezhető **ValueMap** egységtől, például [minden: 0] & [font: 2].</span><span class="sxs-lookup"><span data-stu-id="3e270-144">If you require different values per UOM, this can be done with **ValueMap** from Unit, for example, [Each : 0] & [Pound : 2].</span></span>

    -   <span data-ttu-id="3e270-145">A sablon alapértéke 0.</span><span class="sxs-lookup"><span data-stu-id="3e270-145">Template value is defaulted to 0.</span></span>

-   <span data-ttu-id="3e270-146">CD szervezeti azonosító frissítése: **Organization_OrganizationId** található a **forrás \>CD** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="3e270-146">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="3e270-147">A sablon alapértéke ORG001.</span><span class="sxs-lookup"><span data-stu-id="3e270-147">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="3e270-148">Frissítés **ValueMap** a **egység csoport** (**defaultuomscheduleid.name**) a **CD -\> cél** megfelelően a **csoportjai** értékesítési.</span><span class="sxs-lookup"><span data-stu-id="3e270-148">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="3e270-149">A sablon alapértéke az **Alapértelmezett egység**.</span><span class="sxs-lookup"><span data-stu-id="3e270-149">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="3e270-150">Ellenőrizze, hogy az összes termék UOMs eladási késedelmi és műveletek értékesítés szerepel-e a **CD választási listák** értéke.</span><span class="sxs-lookup"><span data-stu-id="3e270-150">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="3e270-151">Győződjön meg arról, hogy **árlisták** minden egyes pénznemhez termék eladási késedelmi és műveletek értékesítési szerepel.</span><span class="sxs-lookup"><span data-stu-id="3e270-151">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="3e270-152">Termékek hozhatja létre az értékesítési állapot **"vázlat"** vagy **aktív**.</span><span class="sxs-lookup"><span data-stu-id="3e270-152">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="3e270-153">Ez **rendszerbeállítások** alapján **értékesítési** értékesítés.</span><span class="sxs-lookup"><span data-stu-id="3e270-153">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="3e270-154">Vázlat állapotú létrehozott termékeket kell aktiválni kell, mielőtt azok adhatók hozzá **ajánlat** vagy **eladási rendelés**.</span><span class="sxs-lookup"><span data-stu-id="3e270-154">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="3e270-155">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="3e270-155">Template mapping in data integrator</span></span>

<span data-ttu-id="3e270-156">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="3e270-156">The following illustrations show an example of a template mapping in data integrator.</span></span>

![sablonleképezés az adatintegrátorban](./media/products-template-mapping-data-integrator-1.png)

![sablonleképezés a termékekhez az adatintegrátorban](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="3e270-159">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="3e270-159">Related topics</span></span>

[<span data-ttu-id="3e270-160">A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="3e270-160">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="3e270-161">A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="3e270-161">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="3e270-162">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="3e270-162">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)


