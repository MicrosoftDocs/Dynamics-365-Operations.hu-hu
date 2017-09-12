---
title: "Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti szinkronizálásra használhatók az értékesítési árajánlatok fejlécei és sorai esetében."
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
ms.openlocfilehash: 172a3da1b6d90a25ea9ebd14265e70e4a6f9bd70
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="ccf91-103">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="ccf91-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ccf91-104">A potenciális vevő készpénzfizetési Solution használata előtt meg kell ismernie: [Dynamics 365 adatintegráció](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="ccf91-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="ccf91-105">A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) és a Microsoft Dynamics 365 for Sales (Sales) közötti szinkronizálásra használhatók az értékesítési árajánlatok fejlécei és sorai esetében.</span><span class="sxs-lookup"><span data-stu-id="ccf91-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="ccf91-106">Sablon és feladatok</span><span class="sxs-lookup"><span data-stu-id="ccf91-106">Template and tasks</span></span>

<span data-ttu-id="ccf91-107">A következő sablonokat és alapul szolgáló feladatokat használják az értékesítési ajánlati fejlécek és sorok szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="ccf91-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="ccf91-108">**Sablon neve:** Értékesítési árajánlatok (Sales – Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ccf91-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="ccf91-109">**A projekt tevékenységeinek neve:**</span><span class="sxs-lookup"><span data-stu-id="ccf91-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="ccf91-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="ccf91-110">QuoteHeader</span></span>
    - <span data-ttu-id="ccf91-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="ccf91-111">QuoteLine</span></span>

<span data-ttu-id="ccf91-112">A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési ajánlat fejlécének és sorainak szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="ccf91-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="ccf91-113">Termékek</span><span class="sxs-lookup"><span data-stu-id="ccf91-113">Products</span></span>
- <span data-ttu-id="ccf91-114">Fiókok (ha vannak)</span><span class="sxs-lookup"><span data-stu-id="ccf91-114">Accounts (if used)</span></span>
- <span data-ttu-id="ccf91-115">Kapcsolattartók (ha vannak)</span><span class="sxs-lookup"><span data-stu-id="ccf91-115">Contacts (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="ccf91-116">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="ccf91-116">Entity set</span></span>

| <span data-ttu-id="ccf91-117">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="ccf91-117">Sales</span></span>        | <span data-ttu-id="ccf91-118">CDS</span><span class="sxs-lookup"><span data-stu-id="ccf91-118">CDS</span></span>           | <span data-ttu-id="ccf91-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ccf91-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="ccf91-120">Idézetek</span><span class="sxs-lookup"><span data-stu-id="ccf91-120">Quotes</span></span>       | <span data-ttu-id="ccf91-121">Árajánlat</span><span class="sxs-lookup"><span data-stu-id="ccf91-121">Quotation</span></span>     | <span data-ttu-id="ccf91-122">Értékesítésiajánlat-fejlécek</span><span class="sxs-lookup"><span data-stu-id="ccf91-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="ccf91-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="ccf91-123">QuoteDetails</span></span> | <span data-ttu-id="ccf91-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="ccf91-124">QuotationLine</span></span> | <span data-ttu-id="ccf91-125">CDS értékesítési ajánlat sorai</span><span class="sxs-lookup"><span data-stu-id="ccf91-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="ccf91-126">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="ccf91-126">Entity flow</span></span>

<span data-ttu-id="ccf91-127">Az értékesítési ajánlatok létrehozása a Sales-ben történik, majd szinkronizálódnak a Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="ccf91-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="ccf91-128">A Sales értékesítési ajánlatai csak akkor szinkronizálódnak, ha teljesülnek az alábbi feltételek:</span><span class="sxs-lookup"><span data-stu-id="ccf91-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="ccf91-129">Az értékesítésiajánlat-sorokban szereplő összes termék külsőleg van karbantartva.</span><span class="sxs-lookup"><span data-stu-id="ccf91-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="ccf91-130">Az értékesítési ajánlat aktív vagy aktiválva van.</span><span class="sxs-lookup"><span data-stu-id="ccf91-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ccf91-131">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="ccf91-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="ccf91-132">A **Csak külsőleg karbantartott termékei vannak** mező hozzáadódott az Ajánlat entitáshoz annak érdekében, hogy konzisztensen követni lehessen, hogy az értékesítési ajánlat teljes mértékben külsőleg karbantartott termékekből áll-e.</span><span class="sxs-lookup"><span data-stu-id="ccf91-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="ccf91-133">Ha az értékesítési árfolyamok csak külsőleg fenntartott termékeket tartalmaznak, a termékeket a Finance and Operations kezeli.</span><span class="sxs-lookup"><span data-stu-id="ccf91-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="ccf91-134">Ez a viselkedés garantálja, hogy nem próbálja szinkronizálni az értékesítési ajánlati sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.</span><span class="sxs-lookup"><span data-stu-id="ccf91-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="ccf91-135">Az ajánlat minden terméke és sora frissül a **Csak külsőleg karbantartott termékei vannak** információval az árajánlat fejlécéből.</span><span class="sxs-lookup"><span data-stu-id="ccf91-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="ccf91-136">Ezek az információk megtalálhatók az **ajánlat már külsőleg karbantartása termékek csak** az ajánlatkérési sorhoz entitáson mezőt.</span><span class="sxs-lookup"><span data-stu-id="ccf91-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="ccf91-137">A **engedmény**, **költségek**, és **adó** mezők egy összetett-beállítást a pénzügyi és műveletek szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="ccf91-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="ccf91-138">Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés.</span><span class="sxs-lookup"><span data-stu-id="ccf91-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="ccf91-139">Az aktuális modellben a **ár**, **engedmény**, **költség**, és **adó** mezők lezárt fájlrendszer és kezeli a pénzügyi és a műveletek.</span><span class="sxs-lookup"><span data-stu-id="ccf91-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="ccf91-140">Az értékesítési a megoldás teszi a következő mezők írásvédett, mivel az értékek nem szinkronizálja a késedelmi a műveletekhez pedig:</span><span class="sxs-lookup"><span data-stu-id="ccf91-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="ccf91-141">**Csak olvasható mezőket az értékesítésiajánlat-fejléc:** kedvezmény %, engedmény, szállítási mennyiség</span><span class="sxs-lookup"><span data-stu-id="ccf91-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="ccf91-142">**Csak olvasható mezők értékesítésiajánlat-sorokban:** Adó</span><span class="sxs-lookup"><span data-stu-id="ccf91-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ccf91-143">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="ccf91-143">Preconditions and mapping setup</span></span>

- <span data-ttu-id="ccf91-144">Értékesítési árajánlatok, értékesítés, a szinkronizálás előtt lépjen **beállítások**&gt;**felügyeleti**&gt;**rendszerbeállítások**&gt;**értékesítési**, és győződjön meg róla, hogy a **számítási módszer az engedmény** mező értéke **egységenkénti**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-144">Before you synchronize sales quotations, in Sales, go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="ccf91-145">Ez a beállítás segít garantálni, hogy az értékesítésből származó sor engedménye megegyezik a Finance and Operations beállításával.</span><span class="sxs-lookup"><span data-stu-id="ccf91-145">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="ccf91-146">Ellenkező esetben az engedmény nem fog Pénzügy és a műveletek, a megfelelő, mert a pénzügyi és műveletek felirat jelenik meg az engedmény egységenkénti kedvezményt, még akkor is, ha az értékesítési sor engedmény volt.</span><span class="sxs-lookup"><span data-stu-id="ccf91-146">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>
- <span data-ttu-id="ccf91-147">A Finance and Operationsben lépjen a **Kinnlevőségek** &gt; **Beállítás** &gt; **Kinnlévőségek paraméterei** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="ccf91-147">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="ccf91-148">Az a **számsorozat** lapon válassza ki az értékesítési ajánlatok számsorozata, és kattintson a **részleteinek megtekintése**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-148">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="ccf91-149">Ezután a **főkönyvi beállítása**, állítsa be a **kézi** mezőt **Igen**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-149">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="ccf91-150">A Finance and Operationsben lépjen a **Kinnlevőségek** &gt; **Beállítás** &gt; **Kinnlévőségek paraméterei** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="ccf91-150">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="ccf91-151">Ezt a **Szállítmányok** lapon a **szállításidátum-ellenőrzés** mezőt **nincs**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-151">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="ccf91-152">Ez a beállítás megakadályozza, hogy az értékesítési ajánlatok sikertelen szinkronizálás.</span><span class="sxs-lookup"><span data-stu-id="ccf91-152">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="ccf91-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="ccf91-153">QuoteHeader</span></span>

- <span data-ttu-id="ccf91-154">A **kért szállítási dátum** mező szükséges-e a pénzügyi és a műveletek, és a szinkronizálás nem hajtható végre, ha a mező üresen marad.</span><span class="sxs-lookup"><span data-stu-id="ccf91-154">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="ccf91-155">Erről a problémáról megakadályozza, ha a mező üres, az alapértelmezett dátum származik **forrás &gt;CD**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-155">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="ccf91-156">A dátum a preferált értékre módosuljon.</span><span class="sxs-lookup"><span data-stu-id="ccf91-156">The date should be updated to a preferred value.</span></span> <span data-ttu-id="ccf91-157">Jelenleg nem adhat meg értéket például **Ma**, amely meghatározza a mai dátumig.</span><span class="sxs-lookup"><span data-stu-id="ccf91-157">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="ccf91-158">A dátum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="ccf91-158">You must enter a specific date.</span></span> <span data-ttu-id="ccf91-159">A sablon alapértelmezett **Kért kézbesítési dátum** értéke **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-159">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="ccf91-160">**A cím, ország, terület kódja** mező kötelező a Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="ccf91-160">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="ccf91-161">Szinkronizációs hibák elkerülése érdekében, megadhatja az alapértelmezett érték, amely akkor használható, ha a mezőt üresen hagyja az értékesítésben.</span><span class="sxs-lookup"><span data-stu-id="ccf91-161">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="ccf91-162">A alapértelmezés szerinti értéke is hasznos, mivel nem kell manuálisan adja meg egy értéket a a **ország, régió** helyi címeknél mezőt.</span><span class="sxs-lookup"><span data-stu-id="ccf91-162">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="ccf91-163">A **DeliveryAddressCountryRegionISOCode** beállításnak nincs alapértelmezett értéke.</span><span class="sxs-lookup"><span data-stu-id="ccf91-163">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="ccf91-164">Frissíti a hozzárendelést az **CD Szervezetazonosító** a **forrás &gt;CD**, hogy megfeleljen **CD szervezet** a szervezeti egységben:</span><span class="sxs-lookup"><span data-stu-id="ccf91-164">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="ccf91-165">A sablon alapértelmezett **Organization_OrganizationId** értéke **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-165">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ccf91-166">A sablon alapértelmezett **Account_Organization_OrganizationId** értéke **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-166">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ccf91-167">A sablon alapértelmezett **InvoiceAccount_OrganizationId** értéke **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-167">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

### <a name="quoteline"></a><span data-ttu-id="ccf91-168">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="ccf91-168">QuoteLine</span></span>

- <span data-ttu-id="ccf91-169">Frissíti a hozzárendelést az **CD Szervezetazonosító** a **forrás &gt;CD**, hogy megfeleljen **CD szervezet** a szervezeti egységben:</span><span class="sxs-lookup"><span data-stu-id="ccf91-169">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="ccf91-170">A sablon alapértelmezett **Organization_OrganizationId** értéke **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-170">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ccf91-171">A sablon alapértelmezésre **Product_Organization_Organization_OrganizationId** van **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-171">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ccf91-172">A sablon alapértelmezésre **Quotation_Organization_Organization_OrganizationId** van **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-172">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="ccf91-173">A **kért szállítási dátum** mező szükséges-e a pénzügyi és a műveletek, és a szinkronizálás nem hajtható végre, ha a mező üresen marad.</span><span class="sxs-lookup"><span data-stu-id="ccf91-173">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="ccf91-174">Erről a problémáról megakadályozza, ha a mező üres, az alapértelmezett dátum származik **forrás &gt;CD**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-174">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="ccf91-175">A dátum a preferált értékre módosuljon.</span><span class="sxs-lookup"><span data-stu-id="ccf91-175">The date should be updated to a preferred value.</span></span> <span data-ttu-id="ccf91-176">Jelenleg nem adhat meg értéket például **Ma**, amely meghatározza a mai dátumig.</span><span class="sxs-lookup"><span data-stu-id="ccf91-176">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="ccf91-177">A dátum megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="ccf91-177">You must enter a specific date.</span></span> <span data-ttu-id="ccf91-178">A sablon alapértelmezett **Kért kézbesítési dátum** értéke **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-178">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="ccf91-179">Lehetőség van a következő hozzárendelésének eltávolítása **CD &gt;cél** biztosítása, hogy az ajánlati sorok importálják Pénzügy és a műveletek, ha nincs megadva alapértelmezett a vevő vagy a termék:</span><span class="sxs-lookup"><span data-stu-id="ccf91-179">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="ccf91-180">**SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="ccf91-180">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="ccf91-181">Nincs alapértelmezett sablonérték a **SiteId** elemnél.</span><span class="sxs-lookup"><span data-stu-id="ccf91-181">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="ccf91-182">**WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="ccf91-182">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="ccf91-183">Nincs alapértelmezett sablonérték a **WarehouseId** elemnél.</span><span class="sxs-lookup"><span data-stu-id="ccf91-183">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="ccf91-184">Győződjön meg róla, hogy a szükséges érték hozzárendelése az Eladási mértékegység (Mértékegységet) a pénzügyi és a műveletek a **CD &gt;cél** hozzárendelése **Quantity_UOM**, **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="ccf91-184">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="ccf91-185">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="ccf91-185">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="ccf91-186">A **engedmény**, **költségek**, és **adó** mezők egy összetett-beállítást a pénzügyi és műveletek szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="ccf91-186">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="ccf91-187">Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés.</span><span class="sxs-lookup"><span data-stu-id="ccf91-187">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="ccf91-188">Az aktuális modellben a **ár**, **engedmény**, **költség**, és **adó** mezők lezárt fájlrendszer a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ccf91-188">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="ccf91-189">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="ccf91-189">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="ccf91-190">Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="ccf91-190">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="ccf91-191">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="ccf91-191">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="ccf91-192">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="ccf91-192">QuoteHeader</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="ccf91-195">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="ccf91-195">QuoteLine</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="ccf91-198">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="ccf91-198">Related topics</span></span>

[<span data-ttu-id="ccf91-199">A Finance and Operations-termékek szinkronizálása a Sales-termékekre</span><span class="sxs-lookup"><span data-stu-id="ccf91-199">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="ccf91-200">A Sales-számlák szinkronizálása a Finance and Operations-ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="ccf91-200">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="ccf91-201">A Sales-kapcsolatok szinkronizálása a Finance and Operations-kapcsolatokra vagy -ügyfelekre</span><span class="sxs-lookup"><span data-stu-id="ccf91-201">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



