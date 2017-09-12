---
title: "A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók."
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
ms.openlocfilehash: b497f078d9786a5c7630e924da6bb04cad37f5e9
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="9a2de-103">A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="9a2de-103">Synchronize accounts from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="9a2de-104">A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="9a2de-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="9a2de-105">A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók a fiókok esetében.</span><span class="sxs-lookup"><span data-stu-id="9a2de-105">The topic discusses the templates and underlying tasks that are used to synchronize accounts from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="template-and-task"></a><span data-ttu-id="9a2de-106">Sablon és feladat</span><span class="sxs-lookup"><span data-stu-id="9a2de-106">Template and task</span></span>

<span data-ttu-id="9a2de-107">A következő sablonokat és alapul szolgáló feladatokat használják a fiókok szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="9a2de-107">The following templates and underlying tasks are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="9a2de-108">**Sablon neve:** Fiókok (Sales – Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="9a2de-108">**Name of the template:** Accounts (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="9a2de-109">**A feladat neve a projektben:** Fiókok – számla - vevők</span><span class="sxs-lookup"><span data-stu-id="9a2de-109">**Name of the task in the project:** Accounts - Account - Customers</span></span>

<span data-ttu-id="9a2de-110">Szinkronizálási feladatok szükségessége a szinkronizálás előtt: Nincs</span><span class="sxs-lookup"><span data-stu-id="9a2de-110">Sync tasks required prior to Account / Customer sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="9a2de-111">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="9a2de-111">Entity set</span></span>

| <span data-ttu-id="9a2de-112">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="9a2de-112">Sales</span></span>    | <span data-ttu-id="9a2de-113">CDS</span><span class="sxs-lookup"><span data-stu-id="9a2de-113">CDS</span></span>     | <span data-ttu-id="9a2de-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9a2de-114">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="9a2de-115">Számlák</span><span class="sxs-lookup"><span data-stu-id="9a2de-115">Accounts</span></span> | <span data-ttu-id="9a2de-116">Könyvelési számla</span><span class="sxs-lookup"><span data-stu-id="9a2de-116">Account</span></span> | <span data-ttu-id="9a2de-117">Vevők</span><span class="sxs-lookup"><span data-stu-id="9a2de-117">Customers</span></span>              |

## <a name="entity-flow"></a><span data-ttu-id="9a2de-118">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="9a2de-118">Entity flow</span></span>

<span data-ttu-id="9a2de-119">A számlákat a Sales modulban kezeli a rendszer, és a Finance and Operationsben szinkronizálódnak.</span><span class="sxs-lookup"><span data-stu-id="9a2de-119">Accounts are managed in Sales and synchronized to Finance and Operations as Customers.</span></span> <span data-ttu-id="9a2de-120">A **külsőleg megmarad** ilyen vevő tulajdonságának értéke **Igen**, amely az értékesítési ajánlatból vevők nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="9a2de-120">The **Is Externally Maintained** property on these Customers is set to **Yes** to track Customers that originate from Sales.</span></span> <span data-ttu-id="9a2de-121">A számlázás során a adatok szinkronizálva vannak-e az értékesítési számlák szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="9a2de-121">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="9a2de-122">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="9a2de-122">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="9a2de-123">A **számlaszám** a mező akkor érhető el a **számla** oldalon.</span><span class="sxs-lookup"><span data-stu-id="9a2de-123">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="9a2de-124">Tették integráláshoz a természetes és egyedi kulcs.</span><span class="sxs-lookup"><span data-stu-id="9a2de-124">It has been made a natural and unique key to support the integration.</span></span> <span data-ttu-id="9a2de-125">A vevő kapcsolat kezelés (CRM) megoldás természetes kulcselemét hatással lehet a vevőknek, akik már használja a **számlaszám** használó egyedi nem, de a mező **számlaszám** számlánként értékeket.</span><span class="sxs-lookup"><span data-stu-id="9a2de-125">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="9a2de-126">Az integrációs megoldás jelenleg ebben az esetben nem támogatja.</span><span class="sxs-lookup"><span data-stu-id="9a2de-126">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="9a2de-127">Új számla létrehozása esetén, ha egy **számlaszám** értéke nem létezik, szerint egy számsorozat alapján automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="9a2de-127">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="9a2de-128">Az érték áll **számlás**, amelyet egy növekvő számsorozat és utótag hat karakterből követ.</span><span class="sxs-lookup"><span data-stu-id="9a2de-128">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="9a2de-129">Íme, egy példa: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="9a2de-129">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="9a2de-130">Az integrációs megoldás értékesítési kiegyenlítésekor beállítja a frissítési parancsprogram a **számlaszám** létező számlák, értékesítési mezőt.</span><span class="sxs-lookup"><span data-stu-id="9a2de-130">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="9a2de-131">Ha nem **számlaszám** értékeit, a számsorozatot, amely a fentebb leírt használatos.</span><span class="sxs-lookup"><span data-stu-id="9a2de-131">If there are no **Account Number** values, the number sequence that was described earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="9a2de-132">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="9a2de-132">Preconditions and mapping setup</span></span>

- <span data-ttu-id="9a2de-133">**CustomerGroupId** frissíteni kell, hogy a pénzügyi és műveletek egy érvényes értéket.</span><span class="sxs-lookup"><span data-stu-id="9a2de-133">**CustomerGroupId** must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="9a2de-134">Meghatározhat egy alapértelmezett értéket, vagy az érték beállítható egy Értékmegfeleltetés használatával.</span><span class="sxs-lookup"><span data-stu-id="9a2de-134">You can specify a default value, or you can set the value by using a value map.</span></span> <span data-ttu-id="9a2de-135">Az alapértelmezett sablonérték **10**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-135">The default template value is **10**.</span></span>
- <span data-ttu-id="9a2de-136">**A cím, ország, terület kódja** kell lennie a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="9a2de-136">**Address country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="9a2de-137">Szinkronizációs hibák elkerülése érdekében megadhatja az alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="9a2de-137">To avoid synchronization errors, you can specify a default value.</span></span> <span data-ttu-id="9a2de-138">Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.</span><span class="sxs-lookup"><span data-stu-id="9a2de-138">That default value is then used if the field is left blank in Sales.</span></span>

    - <span data-ttu-id="9a2de-139">A sablon alapértelmezett **AddressCountryRegionISOCode** értéke **USA**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-139">The default template value for **AddressCountryRegionISOCode** is **USA**.</span></span>
    - <span data-ttu-id="9a2de-140">A sablon alapértelmezett **DeliveryAddressCountryRegionISOCode** értéke **USA**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-140">The default template value for **DeliveryAddressCountryRegionISOCode** is **USA**.</span></span>

- <span data-ttu-id="9a2de-141">A következő hozzárendelésének eltávolítása hozzáadásával **CD &gt;cél**, segítséget nyújthat manuális, amelyek szükségesek a Pénzügy és műveletek számának csökkentésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="9a2de-141">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="9a2de-142">Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="9a2de-143">**SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="9a2de-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="9a2de-144">Alapértelmezett webhely készíthetők a terméket, vagy a vevő a rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="9a2de-144">A default site can be taken either from the product, or from the customer from the order header.</span></span> <span data-ttu-id="9a2de-145">A sablon alapértelmezett **SiteId** értéke **USA**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-145">The default template value for **SiteId** is **1**.</span></span>
    - <span data-ttu-id="9a2de-146">**WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="9a2de-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="9a2de-147">Alapértelmezett raktár készíthető a termék vagy a vevő a rendelés fejlécében a Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="9a2de-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span> <span data-ttu-id="9a2de-148">A sablon alapértelmezett **WarehouseId** értéke **13**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-148">The default template value for **WarehouseId** is **13**.</span></span>
    - <span data-ttu-id="9a2de-149">**LanguageId** – nyelv a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="9a2de-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="9a2de-150">Alapértelmezés szerint a vevő a rendelés fejlécéből a nyelvet használja.</span><span class="sxs-lookup"><span data-stu-id="9a2de-150">By default, the language from the order header from the customer is used.</span></span> <span data-ttu-id="9a2de-151">A sablon alapértelmezett **LanguageId** értéke **en-us**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-151">The default template value for **LanguageId** is **en-us**.</span></span>

- <span data-ttu-id="9a2de-152">CD szervezeti azonosító frissítése (**Organization_OrganizationId**) található a **forrás &gt;CD** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="9a2de-152">Update the CDS organization ID (**Organization_OrganizationId**) in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="9a2de-153">Az alapértelmezett sablonérték **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="9a2de-153">The default template value is **ORG001**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="9a2de-154">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="9a2de-154">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="9a2de-155">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem szerepelnek a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="9a2de-155">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="9a2de-156">Ezek a mezők megfeleltetéséhez be kell állítania egy értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="9a2de-156">To map these fields, you must set up a value mapping.</span></span> <span data-ttu-id="9a2de-157">Érték-hozzárendelésre vonatkoznak a szervezetek között szinkronizált entitás adatait.</span><span class="sxs-lookup"><span data-stu-id="9a2de-157">Value mappings are specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="9a2de-158">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="9a2de-158">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Sablonleképezés az adatintegrátorban](./media/accounts-template-mapping-data-integrator-1.png)

![Sablonleképezés a számlákhoz az adatintegrátorban](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="9a2de-161">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="9a2de-161">Related topics</span></span>

[<span data-ttu-id="9a2de-162">A Finance and Operations-termékek szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="9a2de-162">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="9a2de-163">A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="9a2de-163">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="9a2de-164">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="9a2de-164">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)




