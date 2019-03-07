---
title: A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Sales Névjegy (Névjegyek) és Névjegy (Vevők) entitások a Microsoft Dynamics 365 for Finance and Operations szolgáltatásba történő szinkronizálására használatosak.
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
ms.openlocfilehash: 5363c64cd1a475f0047c079d9166718ddc765f02
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "356852"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="8e931-103">A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="8e931-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="8e931-104">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Common Data Service for Apps szolgáltatásban](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="8e931-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="8e931-105">Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Microsoft Dynamics 365 for Sales Névjegy (Névjegyek) és Névjegy (Vevők) entitások közvetlenül a Microsoft Dynamics 365 for Finance and Operations szolgáltatásba történő szinkronizálására használatosak.</span><span class="sxs-lookup"><span data-stu-id="8e931-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="8e931-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="8e931-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="8e931-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="8e931-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="8e931-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="8e931-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="8e931-109">A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="8e931-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="8e931-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="8e931-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="8e931-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="8e931-111">Templates and tasks</span></span>

<span data-ttu-id="8e931-112">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="8e931-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="8e931-113">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="8e931-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="8e931-114">A következő sablonokat és alapul szolgáló feladatokat használják a névjegyentitások szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="8e931-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="8e931-115">**A sablonok nevei az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="8e931-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="8e931-116">Kapcsolattartók (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="8e931-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="8e931-117">Kapcsolattartók ügyfélhez (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="8e931-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="8e931-118">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="8e931-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="8e931-119">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="8e931-119">Contacts</span></span>
    - <span data-ttu-id="8e931-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="8e931-120">ContactToCustomer</span></span>

<span data-ttu-id="8e931-121">A kapcsolattartó-szinkronizálás előtt szükséges a következő szinkronizálási feladat: számlák (Sales – Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="8e931-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="8e931-122">Entitáskészletek</span><span class="sxs-lookup"><span data-stu-id="8e931-122">Entity sets</span></span>

| <span data-ttu-id="8e931-123">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="8e931-123">Sales</span></span>    | <span data-ttu-id="8e931-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8e931-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="8e931-125">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="8e931-125">Contacts</span></span> | <span data-ttu-id="8e931-126">CDS-kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="8e931-126">CDS Contacts</span></span>           |
| <span data-ttu-id="8e931-127">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="8e931-127">Contacts</span></span> | <span data-ttu-id="8e931-128">Vevők V2</span><span class="sxs-lookup"><span data-stu-id="8e931-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="8e931-129">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="8e931-129">Entity flow</span></span>

<span data-ttu-id="8e931-130">A kapcsolattartók kezelése a Sales programban történik, majd szinkronizálás történik a Finance and Operations programmal.</span><span class="sxs-lookup"><span data-stu-id="8e931-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="8e931-131">A Sales kapcsolattartójából kapcsolattartó vagy vevő lehet a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="8e931-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="8e931-132">Annak a megállapításához, hogy egy Sales-kapcsolattartót az Finance and Operationsben kapcsolattartóként vagy vevőként kell szinkronizálni, a rendszer megvizsgálja a következő tulajdonságokat a kapcsolattartó esetében a Salesben:</span><span class="sxs-lookup"><span data-stu-id="8e931-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="8e931-133">**Szinkronizálás vevőbe a Finance and Operationsben:** kapcsolattartók, ahol a **van aktív vevő** értéke **Igen**</span><span class="sxs-lookup"><span data-stu-id="8e931-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="8e931-134">**Szinkronizálás kapcsolattartóba a Finance and Operationsben:** kapcsolattartók, ahol a **van aktív vevő** értéke **nem**, és a **vállalat** (szülő számla/névjegy) fiókra mutat (nem kapcsolattartó)</span><span class="sxs-lookup"><span data-stu-id="8e931-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="8e931-135">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="8e931-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="8e931-136">Új **van aktív vevő** mezőt adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="8e931-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="8e931-137">Ebben a mezőben értékesítési tevékenység kapcsolattartóit és értékesítési tevékenység nincs szegmensből megkülönböztetésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="8e931-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="8e931-138">A **van aktív vevő** értéke **Igen** csak a kapcsolattartók esetében, akikhez ajánlatok, rendelések vagy számlák köthetők.</span><span class="sxs-lookup"><span data-stu-id="8e931-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="8e931-139">Csak ezek a kapcsolattartók szinkronizálódnak a Finance and Operationsbe vevőként.</span><span class="sxs-lookup"><span data-stu-id="8e931-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="8e931-140">Új **IsCompanyAnAccount** mezőt adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="8e931-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="8e931-141">A mező segítségével adhatja meg, hogy a kapcsolattartó **Számla** típusú vállalathoz (szülő partner vagy kapcsolattartó) kapcsolódik-e.</span><span class="sxs-lookup"><span data-stu-id="8e931-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="8e931-142">Ez az információ a Finance and Operationsben kapcsolattartóként szinkronizálandó kapcsolattartók azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="8e931-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="8e931-143">Új **kapcsolattartó száma** mező hozzá lett adva a kapcsolattartó a természetes és egyedi kulcs az integráció biztosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="8e931-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="8e931-144">Új kapcsolattartó létrehozásakor egy **kapcsolattartó száma** értéke automatikusan létrejön egy számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="8e931-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="8e931-145">Az érték áll **CON**, amelyet egy növekvő számsorozat és utótag hat karakterből követ.</span><span class="sxs-lookup"><span data-stu-id="8e931-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="8e931-146">Íme, egy példa: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="8e931-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="8e931-147">A Sales integrációs megoldásának alkalmazásakor egy frissítési parancsprogram beállítja a **kapcsolattartó száma** mezőt a meglévő kapcsolattartónál a korábban ismertetett számsorozat használatával.</span><span class="sxs-lookup"><span data-stu-id="8e931-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="8e931-148">A frissítési parancsfájl beállítja a **van aktív vevő** mezőt **Igen** értékre minden értékesítési tevékenységgel rendelkező kapcsolattartónál.</span><span class="sxs-lookup"><span data-stu-id="8e931-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="8e931-149">A Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="8e931-149">In Finance and Operations</span></span>

<span data-ttu-id="8e931-150">Kapcsolattartók vannak megjelölt használatával a **IsContactPersonExternallyMaintained** tulajdonság.</span><span class="sxs-lookup"><span data-stu-id="8e931-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="8e931-151">Ez a tulajdonság jelzi, hogy kapcsolattartó külsőleg tarthatók karban.</span><span class="sxs-lookup"><span data-stu-id="8e931-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="8e931-152">Ebben az esetben a külsőleg karbantartott kapcsolattartók karbantartása a Salesben történik.</span><span class="sxs-lookup"><span data-stu-id="8e931-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="8e931-153">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="8e931-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="8e931-154">Kapcsolattartóból vevő</span><span class="sxs-lookup"><span data-stu-id="8e931-154">Contact to customer</span></span>

- <span data-ttu-id="8e931-155">**CustomerGroup** kell lennie a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="8e931-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="8e931-156">Szinkronizációs hibák elkerülésének elősegítése érdekében az alapértelmezett értéket adhat meg a hozzárendelésben.</span><span class="sxs-lookup"><span data-stu-id="8e931-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="8e931-157">Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.</span><span class="sxs-lookup"><span data-stu-id="8e931-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="8e931-158">Az alapértelmezett sablonérték **10**.</span><span class="sxs-lookup"><span data-stu-id="8e931-158">The default template value is **10**.</span></span>

- <span data-ttu-id="8e931-159">A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Finance and Operations számának csökkentésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="8e931-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="8e931-160">Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.</span><span class="sxs-lookup"><span data-stu-id="8e931-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="8e931-161">**SiteId** – alapértelmezett helyét is meg lehet adni a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="8e931-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="8e931-162">Hely a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="8e931-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="8e931-163">Sablon értéket **SiteId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="8e931-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="8e931-164">**WarehouseId** – alapértelmezett helyét is meg lehet adni a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="8e931-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="8e931-165">Raktár a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="8e931-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="8e931-166">Sablon értéket **WarehouseId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="8e931-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="8e931-167">**LanguageId** – nyelv a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="8e931-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="8e931-168">Az alapértelmezett sablonérték **en-us**.</span><span class="sxs-lookup"><span data-stu-id="8e931-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="8e931-169">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="8e931-169">Template mapping in Data integration</span></span>

<span data-ttu-id="8e931-170">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="8e931-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="8e931-171">A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="8e931-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="8e931-172">Kapcsolattartóból kapcsolattartó</span><span class="sxs-lookup"><span data-stu-id="8e931-172">Contact to contact</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="8e931-174">Kapcsolattartóból vevő</span><span class="sxs-lookup"><span data-stu-id="8e931-174">Contact to customer</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="8e931-176">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="8e931-176">Related topics</span></span>

[<span data-ttu-id="8e931-177">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="8e931-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="8e931-178">A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="8e931-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="8e931-179">A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="8e931-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="8e931-180">Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="8e931-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="8e931-181">Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="8e931-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)


