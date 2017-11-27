---
title: "A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók a névjegyek entitásainak esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8de9a920f384b69c9b3764a0431208bbdcb395bf
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="4b172-103">A Sales-kapcsolatok közvetlen szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="4b172-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="4b172-104">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie: [Dynamics 365 integráció](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="4b172-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="4b172-105">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók a névjegyek entitásainak esetében.</span><span class="sxs-lookup"><span data-stu-id="4b172-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="4b172-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="4b172-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="4b172-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="4b172-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="4b172-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="4b172-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="4b172-109">A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="4b172-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="4b172-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="4b172-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="4b172-111">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="4b172-111">Templates and tasks</span></span>

<span data-ttu-id="4b172-112">A rendelkezésre álló sablonok megtekintéséhez nyissa meg a [PowerApps Admin Centert](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="4b172-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="4b172-113">Válassza a **Projektek** lehetőséget, és ezután kattintson a jobb felső sarkában az **Új projekt** elemre a nyilvános sablonok kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="4b172-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="4b172-114">A következő sablonokat és alapul szolgáló feladatokat használják a névjegyentitások szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="4b172-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="4b172-115">**A sablonok nevei az adatintegrációban:**</span><span class="sxs-lookup"><span data-stu-id="4b172-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="4b172-116">Kapcsolattartók (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="4b172-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="4b172-117">Kapcsolattartók ügyfélhez (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="4b172-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="4b172-118">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="4b172-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="4b172-119">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="4b172-119">Contacts</span></span>
    - <span data-ttu-id="4b172-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="4b172-120">ContactToCustomer</span></span>

<span data-ttu-id="4b172-121">A kapcsolattartó-szinkronizálás előtt szükséges a következő szinkronizálási feladat: számlák (Sales – Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="4b172-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="4b172-122">Entitáskészletek</span><span class="sxs-lookup"><span data-stu-id="4b172-122">Entity sets</span></span>

| <span data-ttu-id="4b172-123">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="4b172-123">Sales</span></span>    | <span data-ttu-id="4b172-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4b172-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="4b172-125">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="4b172-125">Contacts</span></span> | <span data-ttu-id="4b172-126">CDS-kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="4b172-126">CDS Contacts</span></span>           |
| <span data-ttu-id="4b172-127">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="4b172-127">Contacts</span></span> | <span data-ttu-id="4b172-128">Vevők V2</span><span class="sxs-lookup"><span data-stu-id="4b172-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="4b172-129">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="4b172-129">Entity flow</span></span>

<span data-ttu-id="4b172-130">A kapcsolattartók kezelése a Sales programban történik, majd szinkronizálás történik a Finance and Operations programmal.</span><span class="sxs-lookup"><span data-stu-id="4b172-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="4b172-131">A Sales kapcsolattartójából kapcsolattartó vagy vevő lehet a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="4b172-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="4b172-132">Annak a megállapításához, hogy egy Sales-kapcsolattartót az Finance and Operationsben kapcsolattartóként vagy vevőként kell szinkronizálni, a rendszer megvizsgálja a következő tulajdonságokat a kapcsolattartó esetében a Salesben:</span><span class="sxs-lookup"><span data-stu-id="4b172-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="4b172-133">**Szinkronizálás vevőbe a Finance and Operationsben:** kapcsolattartók, ahol a **van aktív vevő** értéke **Igen**</span><span class="sxs-lookup"><span data-stu-id="4b172-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="4b172-134">**Szinkronizálás kapcsolattartóba a Finance and Operationsben:** kapcsolattartók, ahol a **van aktív vevő** értéke **nem**, és a **vállalat** (szülő számla/névjegy) fiókra mutat (nem kapcsolattartó)</span><span class="sxs-lookup"><span data-stu-id="4b172-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="4b172-135">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="4b172-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="4b172-136">Új **van aktív vevő** mezőt adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="4b172-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="4b172-137">Ebben a mezőben értékesítési tevékenység kapcsolattartóit és értékesítési tevékenység nincs szegmensből megkülönböztetésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="4b172-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="4b172-138">A **van aktív vevő** értéke **Igen** csak a kapcsolattartók esetében, akikhez ajánlatok, rendelések vagy számlák köthetők.</span><span class="sxs-lookup"><span data-stu-id="4b172-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="4b172-139">Csak ezek a kapcsolattartók szinkronizálódnak a Finance and Operationsbe vevőként.</span><span class="sxs-lookup"><span data-stu-id="4b172-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="4b172-140">Új **IsCompanyAnAccount** mezőt adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="4b172-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="4b172-141">A mező segítségével adhatja meg, hogy a kapcsolattartó **Számla** típusú vállalathoz (szülő partner vagy kapcsolattartó) kapcsolódik-e.</span><span class="sxs-lookup"><span data-stu-id="4b172-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="4b172-142">Ez az információ a Finance and Operationsben kapcsolattartóként szinkronizálandó kapcsolattartók azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="4b172-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="4b172-143">Új **kapcsolattartó száma** mező hozzá lett adva a kapcsolattartó a természetes és egyedi kulcs az integráció biztosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="4b172-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="4b172-144">Új kapcsolattartó létrehozásakor egy **kapcsolattartó száma** értéke automatikusan létrejön egy számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="4b172-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="4b172-145">Az érték áll **CON**, amelyet egy növekvő számsorozat és utótag hat karakterből követ.</span><span class="sxs-lookup"><span data-stu-id="4b172-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="4b172-146">Íme, egy példa: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="4b172-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="4b172-147">A Sales integrációs megoldásának alkalmazásakor egy frissítési parancsprogram beállítja a **kapcsolattartó száma** mezőt a meglévő kapcsolattartónál a korábban ismertetett számsorozat használatával.</span><span class="sxs-lookup"><span data-stu-id="4b172-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="4b172-148">A frissítési parancsfájl beállítja a **van aktív vevő** mezőt **Igen** értékre minden értékesítési tevékenységgel rendelkező kapcsolattartónál.</span><span class="sxs-lookup"><span data-stu-id="4b172-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="4b172-149">A Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="4b172-149">In Finance and Operations</span></span>

<span data-ttu-id="4b172-150">Kapcsolattartók vannak megjelölt használatával a **IsContactPersonExternallyMaintained** tulajdonság.</span><span class="sxs-lookup"><span data-stu-id="4b172-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="4b172-151">Ez a tulajdonság jelzi, hogy kapcsolattartó külsőleg tarthatók karban.</span><span class="sxs-lookup"><span data-stu-id="4b172-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="4b172-152">Ebben az esetben a külsőleg karbantartott kapcsolattartók karbantartása a Salesben történik.</span><span class="sxs-lookup"><span data-stu-id="4b172-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="4b172-153">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="4b172-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="4b172-154">Kapcsolattartóból vevő</span><span class="sxs-lookup"><span data-stu-id="4b172-154">Contact to customer</span></span>

- <span data-ttu-id="4b172-155">**CustomerGroup** kell lennie a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="4b172-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="4b172-156">Szinkronizációs hibák elkerülésének elősegítése érdekében az alapértelmezett értéket adhat meg a hozzárendelésben.</span><span class="sxs-lookup"><span data-stu-id="4b172-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="4b172-157">Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.</span><span class="sxs-lookup"><span data-stu-id="4b172-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="4b172-158">Az alapértelmezett sablonérték **10**.</span><span class="sxs-lookup"><span data-stu-id="4b172-158">The default template value is **10**.</span></span>

- <span data-ttu-id="4b172-159">A következő hozzárendelésének eltávolítása hozzáadásával CD cél, segítséget nyújthat manuális, amelyek szükségesek a Finance and Operations számának csökkentésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="4b172-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="4b172-160">Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.</span><span class="sxs-lookup"><span data-stu-id="4b172-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="4b172-161">**SiteId** – alapértelmezett helyét is meg lehet adni a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="4b172-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="4b172-162">Hely a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="4b172-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="4b172-163">Sablon értéket **SiteId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="4b172-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="4b172-164">**WarehouseId** – alapértelmezett helyét is meg lehet adni a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="4b172-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="4b172-165">Raktár a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="4b172-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="4b172-166">Sablon értéket **WarehouseId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="4b172-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="4b172-167">**LanguageId** – nyelv a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="4b172-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="4b172-168">Az alapértelmezett sablonérték **en-us**.</span><span class="sxs-lookup"><span data-stu-id="4b172-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4b172-169">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="4b172-169">Template mapping in Data integration</span></span>

<span data-ttu-id="4b172-170">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="4b172-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b172-171">A leképezést mutatja, hogy melyik mezőadatok szinkronizálódnak a Sales – Finance and Operations irányban.</span><span class="sxs-lookup"><span data-stu-id="4b172-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="4b172-172">Kapcsolattartóból kapcsolattartó</span><span class="sxs-lookup"><span data-stu-id="4b172-172">Contact to contact</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="4b172-174">Kapcsolattartóból vevő</span><span class="sxs-lookup"><span data-stu-id="4b172-174">Contact to customer</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="4b172-176">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="4b172-176">Related topics</span></span>

[<span data-ttu-id="4b172-177">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="4b172-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="4b172-178">A Sales-számlák közvetlen szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="4b172-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="4b172-179">A Finance and Operations-termékek közvetlen szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="4b172-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="4b172-180">Értékesítésirendelés-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="4b172-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)

[<span data-ttu-id="4b172-181">Értékesítésiszámla-fejlécek és -sorok közvetlen szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="4b172-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



