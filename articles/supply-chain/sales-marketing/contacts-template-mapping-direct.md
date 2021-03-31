---
title: A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales Névjegy (Névjegyek) és Névjegy (Vevők) entitások közvetlenül a Dynamics 365 Supply Chain Management alkalmazásba történő szinkronizálására használatosak.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
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
ms.openlocfilehash: d0e3b8b2087547ea93a16cd3eb43b2126e0e787b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215793"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a><span data-ttu-id="f6539-103">A Sales-kapcsolatok közvetlen szinkronizálása a Supply Chain Management-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="f6539-103">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="f6539-104">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Microsoft Dataverse for Apps szolgáltatásban](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="f6539-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="f6539-105">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Sales Névjegy (Névjegyek) és Névjegy (Vevők) táblát közvetlenül a Dynamics 365 Supply Chain Management alkalmazásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="f6539-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) tables directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="f6539-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="f6539-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="f6539-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Supply Chain Management és a Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="f6539-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="f6539-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákkal kapcsolatos adatok áramlását a Supply Chain Management és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="f6539-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="f6539-109">A következő ábra bemutatja a Supply Chain Management és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="f6539-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="f6539-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="f6539-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f6539-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="f6539-111">Templates and tasks</span></span>

<span data-ttu-id="f6539-112">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="f6539-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="f6539-113">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="f6539-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="f6539-114">A következő sablonokat és alapul szolgáló feladatokat használják a névjegy táblák szinkronizálásához a Sales és a Supply Chain Management között:</span><span class="sxs-lookup"><span data-stu-id="f6539-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) tables in Sales to Contact (Customers) tables in Supply Chain Management.</span></span>

- <span data-ttu-id="f6539-115">**A sablonok nevei az adatintegrációban**</span><span class="sxs-lookup"><span data-stu-id="f6539-115">**Names of the templates in Data integration**</span></span>

    - <span data-ttu-id="f6539-116">Névjegyek (Sales – Supply Chain Management ) – közvetlen</span><span class="sxs-lookup"><span data-stu-id="f6539-116">Contacts (Sales to Supply Chain Management) - Direct</span></span>
    - <span data-ttu-id="f6539-117">Kapcsolatok az ügyfelekre (Sales – Supply Chain Management) – közvetlen</span><span class="sxs-lookup"><span data-stu-id="f6539-117">Contacts to Customer (Sales to Supply Chain Management) - Direct</span></span>

- <span data-ttu-id="f6539-118">**A feladatok nevei az adatintegrációs projektben**</span><span class="sxs-lookup"><span data-stu-id="f6539-118">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="f6539-119">Névjegyek</span><span class="sxs-lookup"><span data-stu-id="f6539-119">Contacts</span></span>
    - <span data-ttu-id="f6539-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="f6539-120">ContactToCustomer</span></span>

<span data-ttu-id="f6539-121">A kapcsolattartó-szinkronizálás előtt szükséges a következő szinkronizálási feladat: számlák (Sales – Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="f6539-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Supply Chain Management)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="f6539-122">Entitáskészletek</span><span class="sxs-lookup"><span data-stu-id="f6539-122">Entity sets</span></span>

| <span data-ttu-id="f6539-123">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="f6539-123">Sales</span></span>    | <span data-ttu-id="f6539-124">Ellátásilánc-kezelés</span><span class="sxs-lookup"><span data-stu-id="f6539-124">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="f6539-125">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="f6539-125">Contacts</span></span> | <span data-ttu-id="f6539-126">Dataverse kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="f6539-126">Dataverse Contacts</span></span>           |
| <span data-ttu-id="f6539-127">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="f6539-127">Contacts</span></span> | <span data-ttu-id="f6539-128">Vevők V2</span><span class="sxs-lookup"><span data-stu-id="f6539-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="f6539-129">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="f6539-129">Entity flow</span></span>

<span data-ttu-id="f6539-130">A névjegyek kezelése a Salesben történik, majd szinkronizálódnak a Supply Chain Management programban.</span><span class="sxs-lookup"><span data-stu-id="f6539-130">Contacts are managed in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="f6539-131">A Sales kapcsolattartójából kapcsolattartó vagy vevő lehet a Supply Chain Managementben.</span><span class="sxs-lookup"><span data-stu-id="f6539-131">A contact in Sales can become either a contact or a customer in Supply Chain Management.</span></span> <span data-ttu-id="f6539-132">Annak a megállapításához, hogy egy Sales-kapcsolattartót a Supply Chain Management alkalmazásban kapcsolattartóként vagy vevőként kell szinkronizálni, a rendszer megvizsgálja a következő tulajdonságokat a kapcsolattartó esetében a Salesben:</span><span class="sxs-lookup"><span data-stu-id="f6539-132">To determine whether a contact in Sales should be synchronized to Supply Chain Management as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="f6539-133">**Szinkronizálás vevőbe a Supply Chain Management alkalmazásban:** kapcsolattartók, ahol a **van aktív vevő** értéke **Igen**</span><span class="sxs-lookup"><span data-stu-id="f6539-133">**Synchronization to a customer in Supply Chain Management:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="f6539-134">**Szinkronizálás kapcsolattartóba a Supply Chain Management alkalmazásban:** kapcsolattartók, ahol a **van aktív vevő** értéke **nem**, és a **vállalat** (szülő számla/névjegy) fiókra mutat (nem kapcsolattartó)</span><span class="sxs-lookup"><span data-stu-id="f6539-134">**Synchronization to a contact in Supply Chain Management:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="f6539-135">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="f6539-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="f6539-136">Új **van aktív vevő** oszlopot adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="f6539-136">A new **Is Active Customer** column has been added to the contact.</span></span> <span data-ttu-id="f6539-137">Ebben az oszlopban értékesítési tevékenység kapcsolattartóit és értékesítési tevékenység nincs szegmensből megkülönböztetésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="f6539-137">This column is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="f6539-138">A **van aktív vevő** értéke **Igen** csak a kapcsolattartók esetében, akikhez ajánlatok, rendelések vagy számlák köthetők.</span><span class="sxs-lookup"><span data-stu-id="f6539-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="f6539-139">Csak ezek a kapcsolattartók szinkronizálódnak a Supply Chain Management alkalmazásba vevőként.</span><span class="sxs-lookup"><span data-stu-id="f6539-139">Only those contacts are synchronized to Supply Chain Management as customers.</span></span>

<span data-ttu-id="f6539-140">Új **IsCompanyAnAccount** oszlopot adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="f6539-140">A new **IsCompanyAnAccount** column has been added to the contact.</span></span> <span data-ttu-id="f6539-141">Az oszlop segítségével adhatja meg, hogy a kapcsolattartó **Számla** típusú vállalathoz (szülő partner vagy kapcsolattartó) kapcsolódik-e.</span><span class="sxs-lookup"><span data-stu-id="f6539-141">This column indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="f6539-142">Ez az információ a Supply Chain Management alkalmazásban kapcsolattartóként szinkronizálandó kapcsolattartók azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="f6539-142">This information is used to identify contacts that should be synchronized to Supply Chain Management as contacts.</span></span>

<span data-ttu-id="f6539-143">Új **kapcsolattartó száma** oszlop hozzá lett adva a kapcsolattartó a természetes és egyedi kulcs az integráció biztosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="f6539-143">A new **Contact Number** column has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="f6539-144">Új kapcsolattartó létrehozásakor egy **kapcsolattartó száma** értéke automatikusan létrejön egy számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="f6539-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="f6539-145">Az érték áll **CON**, amelyet egy növekvő számsorozat és utótag hat karakterből követ.</span><span class="sxs-lookup"><span data-stu-id="f6539-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="f6539-146">Íme, egy példa: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="f6539-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="f6539-147">A Sales integrációs megoldásának alkalmazásakor egy frissítési parancsprogram beállítja a **kapcsolattartó száma** oszlopot a meglévő kapcsolattartónál a korábban ismertetett számsorozat használatával.</span><span class="sxs-lookup"><span data-stu-id="f6539-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** column for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="f6539-148">A frissítési parancsfájl beállítja a **van aktív vevő** oszlopot **Igen** értékre minden értékesítési tevékenységgel rendelkező kapcsolattartónál.</span><span class="sxs-lookup"><span data-stu-id="f6539-148">The upgrade script also sets the **Is Active Customer** column to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-supply-chain-management"></a><span data-ttu-id="f6539-149">A Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="f6539-149">In Supply Chain Management</span></span>

<span data-ttu-id="f6539-150">Kapcsolattartók vannak megjelölt használatával a **IsContactPersonExternallyMaintained** tulajdonság.</span><span class="sxs-lookup"><span data-stu-id="f6539-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="f6539-151">Ez a tulajdonság jelzi, hogy kapcsolattartó külsőleg tarthatók karban.</span><span class="sxs-lookup"><span data-stu-id="f6539-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="f6539-152">Ebben az esetben a külsőleg karbantartott kapcsolattartók karbantartása a Salesben történik.</span><span class="sxs-lookup"><span data-stu-id="f6539-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="f6539-153">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="f6539-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="f6539-154">Kapcsolattartóból vevő</span><span class="sxs-lookup"><span data-stu-id="f6539-154">Contact to customer</span></span>

- <span data-ttu-id="f6539-155">A **CustomerGroup** kötelező a Supply Chain Managementben.</span><span class="sxs-lookup"><span data-stu-id="f6539-155">**CustomerGroup** is required in Supply Chain Management.</span></span> <span data-ttu-id="f6539-156">Szinkronizációs hibák elkerülésének elősegítése érdekében az alapértelmezett értéket adhat meg a hozzárendelésben.</span><span class="sxs-lookup"><span data-stu-id="f6539-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="f6539-157">Az alapértelmezett érték akkor használatos, ha az oszlop üres, az értékesítési.</span><span class="sxs-lookup"><span data-stu-id="f6539-157">That default value is then used if the column is left blank in Sales.</span></span>

    <span data-ttu-id="f6539-158">Az alapértelmezett sablonérték **10**.</span><span class="sxs-lookup"><span data-stu-id="f6539-158">The default template value is **10**.</span></span>

- <span data-ttu-id="f6539-159">A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Supply Chain Management számának csökkentésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="f6539-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="f6539-160">Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.</span><span class="sxs-lookup"><span data-stu-id="f6539-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="f6539-161">**SiteId** – alapértelmezett helyét is meg lehet adni a Supply Chain Managementben.</span><span class="sxs-lookup"><span data-stu-id="f6539-161">**SiteId** – A default site can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="f6539-162">Egy hely a Supply Chain Management árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="f6539-162">A site is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="f6539-163">Sablon értéket **SiteId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="f6539-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="f6539-164">**WarehouseId** – alapértelmezett raktárat is meg lehet adni a Supply Chain Managementben.</span><span class="sxs-lookup"><span data-stu-id="f6539-164">**WarehouseId** – A default warehouse can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="f6539-165">Egy raktár a Supply Chain Management árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="f6539-165">A warehouse is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="f6539-166">Sablon értéket **WarehouseId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="f6539-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="f6539-167">**LanguageId** – Egy nyelv a Supply Chain Management árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="f6539-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>
    
        <span data-ttu-id="f6539-168">Az alapértelmezett sablonérték **en-us**.</span><span class="sxs-lookup"><span data-stu-id="f6539-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f6539-169">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="f6539-169">Template mapping in Data integration</span></span>

<span data-ttu-id="f6539-170">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="f6539-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="f6539-171">A leképezést mutatja, hogy melyik oszlopadatok szinkronizálódnak a Sales – Supply Chain Management irányban.</span><span class="sxs-lookup"><span data-stu-id="f6539-171">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="f6539-172">Kapcsolattartóból kapcsolattartó</span><span class="sxs-lookup"><span data-stu-id="f6539-172">Contact to contact</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="f6539-174">Kapcsolattartóból vevő</span><span class="sxs-lookup"><span data-stu-id="f6539-174">Contact to customer</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="f6539-176">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="f6539-176">Related topics</span></span>

[<span data-ttu-id="f6539-177">A potenciális vevők készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="f6539-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="f6539-178">A Supply Chain Management-ügyfelek közvetlen szinkronizálása a Sales-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="f6539-178">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="f6539-179">A Supply Chain Management-termékek közvetlen szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="f6539-179">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="f6539-180">Értékesítési rendelés szinkronizálása közvetlenül a Sales szolgáltatás és a Supply Chain Management szolgáltatás között</span><span class="sxs-lookup"><span data-stu-id="f6539-180">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="f6539-181">Értékesítésiszámla-fejlécek és -sorok szinkronizálása közvetlenül a Supply Chain Management szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="f6539-181">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]