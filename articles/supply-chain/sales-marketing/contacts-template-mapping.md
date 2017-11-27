---
title: "A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók a névjegyek esetében."
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c838fef502f643c764fade9cd79ae770ffc36974
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="0ce6b-103">A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="0ce6b-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="0ce6b-104">A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="0ce6b-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="0ce6b-105">Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók a névjegyek esetében.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="0ce6b-106">Sablonok és feladatok</span><span class="sxs-lookup"><span data-stu-id="0ce6b-106">Templates and tasks</span></span>

<span data-ttu-id="0ce6b-107">A következő sablonokat és alapul szolgáló feladatokat használják a névjegyek szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="0ce6b-108">**Sablonok nevei.**</span><span class="sxs-lookup"><span data-stu-id="0ce6b-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="0ce6b-109">Kapcsolattartók (Fin és Ops értékesítés)</span><span class="sxs-lookup"><span data-stu-id="0ce6b-109">Contacts (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="0ce6b-110">Kapcsolattartók ügyfélhez (Fin és Ops értékesítés)</span><span class="sxs-lookup"><span data-stu-id="0ce6b-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="0ce6b-111">**A projekt tevékenységeinek neve:**</span><span class="sxs-lookup"><span data-stu-id="0ce6b-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="0ce6b-112">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="0ce6b-112">Contacts</span></span>
    - <span data-ttu-id="0ce6b-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="0ce6b-113">ContactToCustomer</span></span>

<span data-ttu-id="0ce6b-114">A kapcsolattartó-szinkronizálás előtt szükséges a következő szinkronizálási feladat: számlák (Fin és Ops értékesítés)</span><span class="sxs-lookup"><span data-stu-id="0ce6b-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="0ce6b-115">Entitáskészletek</span><span class="sxs-lookup"><span data-stu-id="0ce6b-115">Entity sets</span></span>

| <span data-ttu-id="0ce6b-116">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="0ce6b-116">Sales</span></span>    | <span data-ttu-id="0ce6b-117">CDS</span><span class="sxs-lookup"><span data-stu-id="0ce6b-117">CDS</span></span>     | <span data-ttu-id="0ce6b-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0ce6b-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="0ce6b-119">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="0ce6b-119">Contacts</span></span> | <span data-ttu-id="0ce6b-120">Kapcsolat</span><span class="sxs-lookup"><span data-stu-id="0ce6b-120">Contact</span></span> | <span data-ttu-id="0ce6b-121">CDS-kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="0ce6b-121">CDS Contacts</span></span>           |
| <span data-ttu-id="0ce6b-122">Kapcsolattartók</span><span class="sxs-lookup"><span data-stu-id="0ce6b-122">Contacts</span></span> | <span data-ttu-id="0ce6b-123">Könyvelési számla</span><span class="sxs-lookup"><span data-stu-id="0ce6b-123">Account</span></span> | <span data-ttu-id="0ce6b-124">Vevők V2</span><span class="sxs-lookup"><span data-stu-id="0ce6b-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="0ce6b-125">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="0ce6b-125">Entity flow</span></span>

<span data-ttu-id="0ce6b-126">Kapcsolattartók kezeli az értékesítési és a közös adatok szolgáltatás CD- és késedelmi a műveletekhez pedig szinkronizálva vannak-e.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="0ce6b-127">Az értékesítési kapcsolattartó válhat a kapcsolattartót a CD- és a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="0ce6b-128">Azt is megteheti hogy lehessen egy számlát a CD-k és a vevő késedelmi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-129">Annak meghatározásához, hogy kapcsolattartó kell vehetők át az értékesítési szinkronizálás CD- és a pénzügyi és a műveletek (például az értékesítési kapcsolattartók &gt;lépjen kapcsolatba a CD &gt;kapcsolattartók Finance and Operations), a rendszer megvizsgálja a következő tulajdonságokat az értékesítésben a kapcsolattartó:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="0ce6b-130">**CD számláján és a vevő késedelmi és műveletek szinkronizálása:** kapcsolatba lép a where **van az aktív vevő** értéke **Igen**</span><span class="sxs-lookup"><span data-stu-id="0ce6b-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="0ce6b-131">**CD kapcsolattartó és a pénzügyi és a műveletek a kapcsolattartó szinkronizálása:** kapcsolatba lép a where **van az aktív vevő** értéke **nem** és **vállalat** (szülő partner vagy kapcsolattartó) mutat fiókja (nem kapcsolattartó)</span><span class="sxs-lookup"><span data-stu-id="0ce6b-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="0ce6b-132">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="0ce6b-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="0ce6b-133">Új **van az aktív vevő** mezőt adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="0ce6b-134">Ebben a mezőben értékesítési tevékenység kapcsolattartóit és értékesítési tevékenység nincs szegmensből megkülönböztetésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="0ce6b-135">**Aktív vevő** értéke **Igen** csak a kapcsolattartók, ajánlatok, rendelések vagy számlák köthető.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="0ce6b-136">A Sales-kapcsolatok szinkronizálása a Finance and Operations--ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="0ce6b-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="0ce6b-137">Új **IsCompanyAnAccount** mezőt adtak a kapcsolattartóval.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="0ce6b-138">Ez a mező segítségével adja meg, hogy a kapcsolattartó a vállalat (szülő partner vagy kapcsolattartó) kapcsolódik a **számla** típusa.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="0ce6b-139">Ez az információ Finance and Operations kapcsolattartóként kell szinkronizálandó kapcsolattartók azonosítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="0ce6b-140">Új **kapcsolattartó száma** mező hozzá lett adva a kapcsolattartó a természetes és egyedi kulcs az integráció biztosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="0ce6b-141">Új kapcsolattartó létrehozásakor egy **kapcsolattartó száma** értéke automatikusan létrejön egy számsorozat alapján.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="0ce6b-142">Az érték áll **CON**, amelyet egy növekvő számsorozat és utótag hat karakterből követ.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="0ce6b-143">Íme, egy példa: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="0ce6b-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="0ce6b-144">Az integrációs megoldás értékesítési hozzáadná az értékesítésekhez, amikor beállítja a frissítési parancsprogram a **kapcsolattartó száma** meglévő korábban ismertetett számsorozatot használó ügyfelek mezőt.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="0ce6b-145">Is beállítja a frissítési parancsfájl a **van az aktív vevő** mezőt **Igen** minden értékesítési tevékenység rendelkező kapcsolattartók.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="0ce6b-146">A Finance and Operations alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="0ce6b-146">In Finance and Operations</span></span> 

<span data-ttu-id="0ce6b-147">Kapcsolattartók vannak megjelölt használatával a **IsContactPersonExternallyMaintained** tulajdonság.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="0ce6b-148">Ez a tulajdonság jelzi, hogy kapcsolattartó külsőleg tarthatók karban.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="0ce6b-149">Ebben az esetben külsőleg karbantartani kapcsolattartók karbantartása az értékesítés.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="0ce6b-150">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="0ce6b-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="0ce6b-151">Névjegy - névjegy</span><span class="sxs-lookup"><span data-stu-id="0ce6b-151">Contact to Contact</span></span>

- <span data-ttu-id="0ce6b-152">Frissítés **CD Szervezetazonosító** a a **forrás &gt;CD** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="0ce6b-153">A sablon alapértelmezésre **Organization_OrganizationId [Szervezetazonosító]** van **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="0ce6b-154">A sablon alapértelmezésre **PrimaryAccount_Organization_OrganizationId [Organization ID]** - **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="0ce6b-155">**A cím, ország, terület kódja** kell lennie a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-156">Szinkronizációs hibák elkerülése érdekében az alapértelmezett értéket adhat a **CD &gt;műveletek** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="0ce6b-157">Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="0ce6b-158">A sablon alapértelmezett **PrimaryAddressCountryRegionISOCode** értéke **USA**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="0ce6b-159">Győződjön meg arról, hogy egy értéket a következő mező szerepel a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-160">Az adatok a Finance and Operations nincs szükség esetén távolíthatja el a hozzárendelést a a **CD &gt;cél** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="0ce6b-161">**Finance and Operations mezőnév:** határozat</span><span class="sxs-lookup"><span data-stu-id="0ce6b-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="0ce6b-162">**Leképezés:** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="0ce6b-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="0ce6b-163">Konvertálás vevővé</span><span class="sxs-lookup"><span data-stu-id="0ce6b-163">Contact to Customer</span></span>

- <span data-ttu-id="0ce6b-164">Frissítés **CD Szervezetazonosító** a a **forrás &gt;CD** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="0ce6b-165">A sablon alapértelmezésre **Organization_OrganizationId [Szervezetazonosító]** van **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="0ce6b-166">**A cím, ország, terület kódja** kell lennie a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-167">Szinkronizációs hibák elkerülése érdekében az alapértelmezett értéket adhat a **CD &gt;Cél** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="0ce6b-168">Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="0ce6b-169">A sablon alapértelmezett **PrimaryAddressCountryRegionISOCode** értéke **USA**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="0ce6b-170">**CustomerGroup** kell lennie a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-171">Szinkronizációs hibák elkerülése érdekében az alapértelmezett értéket adhat a **CD &gt;Cél** hozzárendelés.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="0ce6b-172">Az alapértelmezett érték akkor használatos, ha a mező üres, az értékesítési.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="0ce6b-173">A sablon alapértelmezett **CustomerGroupId** értéke **USA**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="0ce6b-174">A következő hozzárendelésének eltávolítása hozzáadásával **CD &gt;cél**, segítséget nyújthat manuális, amelyek szerepelnek a Finance and Operations számának csökkentésével lehetséges.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-175">Használhatja az alapértelmezett értékek vagy hozzárendelése, például **ország/régió** vagy **Város**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="0ce6b-176">**SiteId** -alapértelmezett helyét is meg lehet adni a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-177">Hely a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-178">Sablon értéket **SiteId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="0ce6b-179">**WarehouseId** -alapértelmezett helyét is meg lehet adni a Finance and Operationsben.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-180">Raktár a Finance and Operations árajánlatok és értékesítési rendelések létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-181">Sablon értéket **WarehouseId** nincs definiálva.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="0ce6b-182">**LanguageId** - nyelv a Finance and Operations árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="0ce6b-183">A sablon alapértelmezett **LanguageId** értéke **en-us**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="0ce6b-184">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="0ce6b-184">Template mapping in data integrator</span></span>

<span data-ttu-id="0ce6b-185">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="0ce6b-186">Névjegy - névjegy</span><span class="sxs-lookup"><span data-stu-id="0ce6b-186">Contact to Contact</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-template-mapping-data-integrator-1.png)

![Sablonleképezés a névjegyekhez az adatintegrátorban](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="0ce6b-189">Konvertálás vevővé</span><span class="sxs-lookup"><span data-stu-id="0ce6b-189">Contact to Customer</span></span>

![Sablonleképezés az adatintegrátorban](./media/contacts-template-mapping-data-integrator-3.png)

![Sablonleképezés a névjegyekhez az adatintegrátorban](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="0ce6b-192">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="0ce6b-192">Related topics</span></span>

[<span data-ttu-id="0ce6b-193">A Finance and Operations-termékek szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="0ce6b-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="0ce6b-194">A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="0ce6b-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="0ce6b-195">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="0ce6b-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="0ce6b-196">Értékesítésirendelés-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="0ce6b-196">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="0ce6b-197">Értékesítésiszámla-fejlécek és -sorok szinkronizálása a Finance and Operations szolgáltatásból a Sales szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="0ce6b-197">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)

