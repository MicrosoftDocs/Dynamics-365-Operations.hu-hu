---
title: A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Sales számláinak Microsoft Dynamics 365 for Finance and Operations szolgáltatásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: a0cabdab63d4d44010e52303d6f487db1e910059
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "317890"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="42b8f-103">A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="42b8f-103">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="42b8f-104">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Common Data Service for Apps szolgáltatásban](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="42b8f-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="42b8f-105">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Sales számláinak közvetlenül a Microsoft Dynamics 365 for Finance and Operations szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="42b8f-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="42b8f-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="42b8f-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="42b8f-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="42b8f-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span>  <span data-ttu-id="42b8f-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="42b8f-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="42b8f-109">A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="42b8f-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="42b8f-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="42b8f-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="42b8f-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="42b8f-111">Templates and tasks</span></span>

<span data-ttu-id="42b8f-112">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="42b8f-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="42b8f-113">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="42b8f-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="42b8f-114">A következő sablon és alapul szolgáló feladat használt a fiókok szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="42b8f-114">The following template and underlying task are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="42b8f-115">**Sablon neve az adatintegrációban:** Fiókok (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="42b8f-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="42b8f-116">**A feladat neve a projektben:** Fiókok – Vevők</span><span class="sxs-lookup"><span data-stu-id="42b8f-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="42b8f-117">Szinkronizálási feladat nem szükséges a Számla/ügyfél szinkronizálás előtt.</span><span class="sxs-lookup"><span data-stu-id="42b8f-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="42b8f-118">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="42b8f-118">Entity set</span></span>

| <span data-ttu-id="42b8f-119">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="42b8f-119">Sales</span></span>    | <span data-ttu-id="42b8f-120">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="42b8f-120">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="42b8f-121">Számlák</span><span class="sxs-lookup"><span data-stu-id="42b8f-121">Accounts</span></span> | <span data-ttu-id="42b8f-122">Vevők V2</span><span class="sxs-lookup"><span data-stu-id="42b8f-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="42b8f-123">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="42b8f-123">Entity flow</span></span>

<span data-ttu-id="42b8f-124">A számlákat a Sales modulban kezeli a rendszer, és a Finance and Operationsbe vevőként szinkronizálódnak.</span><span class="sxs-lookup"><span data-stu-id="42b8f-124">Accounts are managed in Sales and synchronized to Finance and Operations as customers.</span></span> <span data-ttu-id="42b8f-125">A **Külsőleg karbantartott** tulajdonságának beállítása ezeknél az ügyfeleknél **Igen** a Sales szolgáltatásból érkező vevők nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="42b8f-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="42b8f-126">A számlázás során a adatok szinkronizálva vannak-e az értékesítési számlák szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="42b8f-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="42b8f-127">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="42b8f-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="42b8f-128">A **számlaszám** a mező akkor érhető el a **számla** oldalon.</span><span class="sxs-lookup"><span data-stu-id="42b8f-128">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="42b8f-129">Tették integráláshoz a természetes és egyedi kulcs.</span><span class="sxs-lookup"><span data-stu-id="42b8f-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="42b8f-130">A vevő kapcsolat kezelés (CRM) megoldás természetes kulcselemét hatással lehet a vevőknek, akik már használja a **számlaszám** használó egyedi nem, de a mező **számlaszám** számlánként értékeket.</span><span class="sxs-lookup"><span data-stu-id="42b8f-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="42b8f-131">Az integrációs megoldás jelenleg ebben az esetben nem támogatja.</span><span class="sxs-lookup"><span data-stu-id="42b8f-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="42b8f-132">Új számla létrehozása esetén, ha egy **számlaszám** értéke nem létezik, szerint egy számsorozat alapján automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="42b8f-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="42b8f-133">Az érték áll **számlás**, amelyet egy növekvő számsorozat és utótag hat karakterből követ.</span><span class="sxs-lookup"><span data-stu-id="42b8f-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="42b8f-134">Íme, egy példa: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="42b8f-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="42b8f-135">Az integrációs megoldás értékesítési kiegyenlítésekor beállítja a frissítési parancsprogram a **számlaszám** létező számlák, értékesítési mezőt.</span><span class="sxs-lookup"><span data-stu-id="42b8f-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="42b8f-136">Ha nem **Számlaszám** értékeit, a számsorozatot, amely a fentebb leírt használatos.</span><span class="sxs-lookup"><span data-stu-id="42b8f-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="42b8f-137">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="42b8f-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="42b8f-138">A **CustomerGroupId** leképezést frissíteni kell a Finance and Operations egy érvényes értékére.</span><span class="sxs-lookup"><span data-stu-id="42b8f-138">The **CustomerGroupId** mapping must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="42b8f-139">Meghatározhat egy alapértelmezett értéket, vagy az érték beállítható egy Értékmegfeleltetés használatával.</span><span class="sxs-lookup"><span data-stu-id="42b8f-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="42b8f-140">Az alapértelmezett sablonérték **10**.</span><span class="sxs-lookup"><span data-stu-id="42b8f-140">The default template value is **10**.</span></span>

- <span data-ttu-id="42b8f-141">A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Finance and Operations számának csökkentésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="42b8f-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="42b8f-142">Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.</span><span class="sxs-lookup"><span data-stu-id="42b8f-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="42b8f-143">**SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="42b8f-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="42b8f-144">Alapértelmezett webhely készíthetők a terméket, vagy a vevő a rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="42b8f-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="42b8f-145">Az alapértelmezett sablonérték **1**.</span><span class="sxs-lookup"><span data-stu-id="42b8f-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="42b8f-146">**WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="42b8f-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="42b8f-147">Alapértelmezett raktár készíthető a termék vagy a vevő a rendelés fejlécében a Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="42b8f-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span>

        <span data-ttu-id="42b8f-148">Az alapértelmezett sablonérték **13**.</span><span class="sxs-lookup"><span data-stu-id="42b8f-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="42b8f-149">**LanguageId** – nyelv a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="42b8f-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="42b8f-150">Alapértelmezés szerint a vevő a rendelés fejlécéből a nyelvet használja.</span><span class="sxs-lookup"><span data-stu-id="42b8f-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="42b8f-151">Az alapértelmezett sablonérték **en-us**.</span><span class="sxs-lookup"><span data-stu-id="42b8f-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="42b8f-152">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="42b8f-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="42b8f-153">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem szerepelnek a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="42b8f-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="42b8f-154">Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="42b8f-154">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="42b8f-155">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="42b8f-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="42b8f-156">A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="42b8f-156">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Sablonleképezés az adatintegrátorban](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="42b8f-158">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="42b8f-158">Related topics</span></span>


[<span data-ttu-id="42b8f-159">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="42b8f-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="42b8f-160">A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="42b8f-160">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="42b8f-161">A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="42b8f-161">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="42b8f-162">Értékesítésirendelés-fejlécek és -sorok szinkronizálása közvetlenül a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="42b8f-162">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="42b8f-163">Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="42b8f-163">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

