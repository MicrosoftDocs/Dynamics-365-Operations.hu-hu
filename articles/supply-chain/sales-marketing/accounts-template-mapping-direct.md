---
title: A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales ügyfelek a Supply Chain Management alkalmazásba szinkronizálására használatosak.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 1bf0da5ba5274b61758bc0efdc2f2167327966ad
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831650"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a><span data-ttu-id="29b06-103">A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="29b06-103">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="29b06-104">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Microsoft Dataverse for Apps szolgáltatásban](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="29b06-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="29b06-105">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales ügyfeleinek köztvetlenül a Dynamics 365 Supply Chain Management alkalmazásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="29b06-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="29b06-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="29b06-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="29b06-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="29b06-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span>  <span data-ttu-id="29b06-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákkal kapcsolatos adatok áramlását a Supply Chain Management és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="29b06-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="29b06-109">A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="29b06-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="29b06-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="29b06-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="29b06-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="29b06-111">Templates and tasks</span></span>

<span data-ttu-id="29b06-112">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [Power Apps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="29b06-112">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="29b06-113">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="29b06-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="29b06-114">A következő sablonokat és alapul szolgáló feladatot használják a termékek szinkronizálásához a Sales és a Supply Chain Management között:</span><span class="sxs-lookup"><span data-stu-id="29b06-114">The following template and underlying task are used to synchronize accounts from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="29b06-115">**Sablon neve az adatintegrációban:** Fiókok (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="29b06-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="29b06-116">**A feladat neve a projektben:** Fiókok – Vevők</span><span class="sxs-lookup"><span data-stu-id="29b06-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="29b06-117">Szinkronizálási feladat nem szükséges a Számla/ügyfél szinkronizálás előtt.</span><span class="sxs-lookup"><span data-stu-id="29b06-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="29b06-118">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="29b06-118">Entity set</span></span>

| <span data-ttu-id="29b06-119">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="29b06-119">Sales</span></span>    | <span data-ttu-id="29b06-120">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="29b06-120">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="29b06-121">Számlák</span><span class="sxs-lookup"><span data-stu-id="29b06-121">Accounts</span></span> | <span data-ttu-id="29b06-122">Vevők V2</span><span class="sxs-lookup"><span data-stu-id="29b06-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="29b06-123">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="29b06-123">Entity flow</span></span>

<span data-ttu-id="29b06-124">Az ügyfelek kezelése a Salesben történik, majd szinkronizálódnak a Supply Chain Management alkalmazásban ügyfélként.</span><span class="sxs-lookup"><span data-stu-id="29b06-124">Accounts are managed in Sales and synchronized to Supply Chain Management as customers.</span></span> <span data-ttu-id="29b06-125">A **Külsőleg karbantartott** tulajdonságának beállítása ezeknél az ügyfeleknél **Igen** a Sales szolgáltatásból érkező vevők nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="29b06-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="29b06-126">A számlázás során a adatok szinkronizálva vannak-e az értékesítési számlák szűréséhez.</span><span class="sxs-lookup"><span data-stu-id="29b06-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="29b06-127">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="29b06-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="29b06-128">A **számlaszám** oszlop akkor érhető el a **számla** oldalon.</span><span class="sxs-lookup"><span data-stu-id="29b06-128">The **Account Number** column is available on the **Account** page.</span></span> <span data-ttu-id="29b06-129">Tették integráláshoz a természetes és egyedi kulcs.</span><span class="sxs-lookup"><span data-stu-id="29b06-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="29b06-130">A vevői kapcsolatkezelés (CRM) megoldás természetes kulcs funkciója hatással lehet a vevőkre, akik már használják a **számlaszám** oszlopot, de nem használják az egyedi **számlaszám** értéket számlánként.</span><span class="sxs-lookup"><span data-stu-id="29b06-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** column, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="29b06-131">Az integrációs megoldás jelenleg ebben az esetben nem támogatja.</span><span class="sxs-lookup"><span data-stu-id="29b06-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="29b06-132">Új számla létrehozása esetén, ha egy **számlaszám** értéke nem létezik, szerint egy számsorozat alapján automatikusan történik.</span><span class="sxs-lookup"><span data-stu-id="29b06-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="29b06-133">Az érték áll **számlás**, amelyet egy növekvő számsorozat és utótag hat karakterből követ.</span><span class="sxs-lookup"><span data-stu-id="29b06-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="29b06-134">Íme, egy példa: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="29b06-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="29b06-135">A Sales integrációs megoldásának használatakor egy frissítési parancsfájl beállítja a **Számlaszám** oszlopot a létező számlákhoz a Salesben.</span><span class="sxs-lookup"><span data-stu-id="29b06-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** column for existing accounts in Sales.</span></span> <span data-ttu-id="29b06-136">Ha nem **Számlaszám** értékeit, a számsorozatot, amely a fentebb leírt használatos.</span><span class="sxs-lookup"><span data-stu-id="29b06-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="29b06-137">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="29b06-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="29b06-138">A **CustomerGroupId** leképezést frissíteni kell a Supply Chain Management egy érvényes értékére.</span><span class="sxs-lookup"><span data-stu-id="29b06-138">The **CustomerGroupId** mapping must be updated to a valid value in Supply Chain Management.</span></span> <span data-ttu-id="29b06-139">Meghatározhat egy alapértelmezett értéket, vagy az érték beállítható egy Értékmegfeleltetés használatával.</span><span class="sxs-lookup"><span data-stu-id="29b06-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="29b06-140">Az alapértelmezett sablonérték **10**.</span><span class="sxs-lookup"><span data-stu-id="29b06-140">The default template value is **10**.</span></span>

- <span data-ttu-id="29b06-141">A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Supply Chain Management számának csökkentésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="29b06-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="29b06-142">Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.</span><span class="sxs-lookup"><span data-stu-id="29b06-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="29b06-143">**SiteId** – hely a Supply Chain Management árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="29b06-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="29b06-144">Alapértelmezett webhely készíthetők a terméket, vagy a vevő a rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="29b06-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="29b06-145">Az alapértelmezett sablonérték **1**.</span><span class="sxs-lookup"><span data-stu-id="29b06-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="29b06-146">**WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükségesek Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="29b06-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="29b06-147">Alapértelmezett raktár készíthető a termék vagy a vevő a rendelés fejlécében a Supply Chain Management programban.</span><span class="sxs-lookup"><span data-stu-id="29b06-147">A default warehouse can be taken either from the product, or from the customer from the order header in Supply Chain Management.</span></span>

        <span data-ttu-id="29b06-148">Az alapértelmezett sablonérték **13**.</span><span class="sxs-lookup"><span data-stu-id="29b06-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="29b06-149">**LanguageId** – Egy nyelv a Supply Chain Management árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="29b06-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span> <span data-ttu-id="29b06-150">Alapértelmezés szerint a vevő a rendelés fejlécéből a nyelvet használja.</span><span class="sxs-lookup"><span data-stu-id="29b06-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="29b06-151">Az alapértelmezett sablonérték **en-us**.</span><span class="sxs-lookup"><span data-stu-id="29b06-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="29b06-152">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="29b06-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="29b06-153">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** oszlopok nem szerepelnek a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="29b06-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** columns aren't included in the default mappings.</span></span> <span data-ttu-id="29b06-154">Ezen oszlopok megfeleltetéséhez be kell állítania egy értékmegfeleltetést, amely az adott szervezetek adataira specifikus, amelyek között a tábla szinkronizálódik.</span><span class="sxs-lookup"><span data-stu-id="29b06-154">To map these columns, you must set up a value mapping that is specific to the data in the organizations that the table is synchronized between.</span></span>

<span data-ttu-id="29b06-155">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="29b06-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="29b06-156">A leképezést mutatja, hogy melyik oszlopadatok szinkronizálódnak a Sales – Supply Chain Management irányban.</span><span class="sxs-lookup"><span data-stu-id="29b06-156">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

![Sablonleképezés az adatintegrátorban](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="29b06-158">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="29b06-158">Related topics</span></span>


[<span data-ttu-id="29b06-159">A potenciális vevők készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="29b06-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="29b06-160">A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="29b06-160">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="29b06-161">A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="29b06-161">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="29b06-162">Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között</span><span class="sxs-lookup"><span data-stu-id="29b06-162">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="29b06-163">Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="29b06-163">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]