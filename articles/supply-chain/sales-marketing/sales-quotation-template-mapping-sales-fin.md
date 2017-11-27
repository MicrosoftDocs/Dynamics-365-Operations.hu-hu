---
title: "Értékesítésiajánlat-fejlécek és -sorok közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba"
description: "A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési árajánlatok fejlécei és sorai esetében."
author: ChristianRytt
manager: AnnBe
ms.date: 11/14/2017
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
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 8a75c6dd91020ab3e676e2bb40d5c822731e244f
ms.contentlocale: hu-hu
ms.lasthandoff: 11/14/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="f94fe-103">Értékesítésiajánlat-fejlécek és -sorok közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="f94fe-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f94fe-104">A témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition és a Microsoft Dynamics 365 for Sales közötti közvetlen szinkronizálásra használhatók az értékesítési árajánlatok fejlécei és sorai esetében.</span><span class="sxs-lookup"><span data-stu-id="f94fe-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

> [!NOTE]
> <span data-ttu-id="f94fe-105">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie: [Dynamics 365 integráció](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="f94fe-105">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="f94fe-106">Sablon és feladatok</span><span class="sxs-lookup"><span data-stu-id="f94fe-106">Template and tasks</span></span>

<span data-ttu-id="f94fe-107">A következő sablont és alapul szolgáló feladatokat használják az értékesítési ajánlati fejlécek és sorok közvetlen szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="f94fe-107">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="f94fe-108">**Sablon neve az adatintegrációban:** Értékesítési ajánlatok (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="f94fe-108">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="f94fe-109">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="f94fe-109">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="f94fe-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="f94fe-110">QuoteHeader</span></span>
    - <span data-ttu-id="f94fe-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="f94fe-111">QuoteLine</span></span>

<span data-ttu-id="f94fe-112">A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési ajánlat fejlécének és sorainak szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="f94fe-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="f94fe-113">Termékek (Fin and Ops – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="f94fe-113">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="f94fe-114">Számlák (Sales a Fin and Opshoz) – Közvetlen (ha van)</span><span class="sxs-lookup"><span data-stu-id="f94fe-114">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="f94fe-115">Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) – közvetlen (ha van)</span><span class="sxs-lookup"><span data-stu-id="f94fe-115">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="f94fe-116">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="f94fe-116">Entity set</span></span>

| <span data-ttu-id="f94fe-117">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="f94fe-117">Sales</span></span>        | <span data-ttu-id="f94fe-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f94fe-118">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="f94fe-119">Idézetek</span><span class="sxs-lookup"><span data-stu-id="f94fe-119">Quotes</span></span>       | <span data-ttu-id="f94fe-120">CDS értékesítésiajánlat-fejléc</span><span class="sxs-lookup"><span data-stu-id="f94fe-120">CDS sales quotation header</span></span> |
| <span data-ttu-id="f94fe-121">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="f94fe-121">QuoteDetails</span></span> | <span data-ttu-id="f94fe-122">CDS értékesítési ajánlat sorai</span><span class="sxs-lookup"><span data-stu-id="f94fe-122">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="f94fe-123">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="f94fe-123">Entity flow</span></span>

<span data-ttu-id="f94fe-124">Az értékesítési ajánlatok létrehozása a Sales-ben történik, majd szinkronizálódnak a Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="f94fe-124">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="f94fe-125">A Sales értékesítési ajánlatai csak akkor szinkronizálódnak, ha teljesülnek az alábbi feltételek:</span><span class="sxs-lookup"><span data-stu-id="f94fe-125">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="f94fe-126">Az értékesítési ajánlatban szereplő összes termék külsőleg van karbantartva.</span><span class="sxs-lookup"><span data-stu-id="f94fe-126">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="f94fe-127">Miután rákattint az **Ajánlat aktiválása** lehetőségre, az értékesítési árajánlat aktívvá válik.</span><span class="sxs-lookup"><span data-stu-id="f94fe-127">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="f94fe-128">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="f94fe-128">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="f94fe-129">A **Csak külsőleg karbantartott termékei vannak** mező hozzáadódott az **Ajánlat** entitáshoz annak érdekében, hogy konzisztensen követni lehessen, hogy az értékesítési ajánlat teljes mértékben külsőleg karbantartott termékekből áll-e.</span><span class="sxs-lookup"><span data-stu-id="f94fe-129">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="f94fe-130">Ha az értékesítési árfolyamok csak külsőleg fenntartott termékeket tartalmaznak, a termékeket a Finance and Operations kezeli.</span><span class="sxs-lookup"><span data-stu-id="f94fe-130">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="f94fe-131">Ez a viselkedés garantálja, hogy nem próbálja szinkronizálni az értékesítési ajánlati sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.</span><span class="sxs-lookup"><span data-stu-id="f94fe-131">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="f94fe-132">Az értékesítési ajánlat minden terméke frissül a **Csak külsőleg karbantartott termékei vannak** információval az árajánlat fejlécéből.</span><span class="sxs-lookup"><span data-stu-id="f94fe-132">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="f94fe-133">Ezek az információk megtalálhatók az **Ajánlat csak külsőleg fenntartott termékekre vonatkozik** mezőben, a **QuoteDetails** entitásnál.</span><span class="sxs-lookup"><span data-stu-id="f94fe-133">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="f94fe-134">Kedvezményt lehet hozzáadni az idevonatkozó termékhez, és szinkronizálva lesz a Finance and Operations szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="f94fe-134">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="f94fe-135">A fejlécen az **Engedmény**, **Költségek** és **Adó** mezők a Finance and Operations szolgáltatásból szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="f94fe-135">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="f94fe-136">Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés.</span><span class="sxs-lookup"><span data-stu-id="f94fe-136">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="f94fe-137">Az aktuális modellben az **Ár**, **Engedmény**, **Költség** és az **Adó** mezők lezárt fájlrendszer és kezeli a Finance and Operations felületén.</span><span class="sxs-lookup"><span data-stu-id="f94fe-137">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="f94fe-138">Az értékesítési a megoldás teszi a következő mezők írásvédett, mivel az értékek nem szinkronizálja a késedelmi a műveletekhez pedig:</span><span class="sxs-lookup"><span data-stu-id="f94fe-138">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="f94fe-139">Csak olvasható mezőket az értékesítésiajánlat-fejlécen:**Árengedmény%** Árengedmény%, **Árengedmény** és**Fuvardíj**</span><span class="sxs-lookup"><span data-stu-id="f94fe-139">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="f94fe-140">Csak olvasható mezők az ajánlat termékein: **Adó**</span><span class="sxs-lookup"><span data-stu-id="f94fe-140">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="f94fe-141">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="f94fe-141">Preconditions and mapping setup</span></span>

<span data-ttu-id="f94fe-142">Értékesítési ajánlatok szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="f94fe-142">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="f94fe-143">Beállítás a Salesben</span><span class="sxs-lookup"><span data-stu-id="f94fe-143">Setup in Sales</span></span>

- <span data-ttu-id="f94fe-144">Győződjön meg róla, hogy beállították az engedélyeket ahhoz a csapathoz, amelytől a Sales kapcsolatkészletének felhasználója hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="f94fe-144">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="f94fe-145">Bemutatóadatok használatakor rendszerint a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport.</span><span class="sxs-lookup"><span data-stu-id="f94fe-145">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="f94fe-146">Ha a csapatnak nincs adminisztrátori hozzáférése, akkor ha a projektet az adatintegrálásból futtatja, hibaüzenet jelenik meg, amely azt jelzi, hogy a fő csapat hiányzik.</span><span class="sxs-lookup"><span data-stu-id="f94fe-146">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="f94fe-147">A csoport engedélyeinek beállításához kattintson a **beállítások**&gt;**biztonsági**&gt;**csapatok**, és válassza ki a csapatot.</span><span class="sxs-lookup"><span data-stu-id="f94fe-147">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="f94fe-148">Válasszon **szerepkörök kezelése**, és válassza ki a kívánt engedélyeket, például rendelkező szerepkör **rendszergazda**.</span><span class="sxs-lookup"><span data-stu-id="f94fe-148">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="f94fe-149">Lépjen a **Beállítások** &gt; **Adminisztráció** &gt; **Rendszerbeállítások** &gt; **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:</span><span class="sxs-lookup"><span data-stu-id="f94fe-149">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="f94fe-150">A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.</span><span class="sxs-lookup"><span data-stu-id="f94fe-150">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="f94fe-151">Az **Engedményszámítási módszer** mező értéke a **Sortétel**.</span><span class="sxs-lookup"><span data-stu-id="f94fe-151">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="f94fe-152">Beállítás az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="f94fe-152">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="f94fe-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="f94fe-153">QuoteHeader</span></span>

- <span data-ttu-id="f94fe-154">Győződjön meg róla, hogy a szükséges leképezés létezik: **Shipto\_country** – **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="f94fe-154">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="f94fe-155">Az Értékmegfeleltetés is megadható egy alapértelmezett érték, amely akkor használható, ha az érték üresen marad.</span><span class="sxs-lookup"><span data-stu-id="f94fe-155">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="f94fe-156">egyszerűen állítsa a bal oldalt az "Üres" értékre, és állítsa a jobb oldalt a kívánt országra vagy régióra.</span><span class="sxs-lookup"><span data-stu-id="f94fe-156">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="f94fe-157">Ezzel a módszerrel nem kell beírni az országot vagy régiót a belföldi rendeléseknél.</span><span class="sxs-lookup"><span data-stu-id="f94fe-157">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="f94fe-158">A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve, és ahol az üres érték = **Amerikai Egyesült Államok**.</span><span class="sxs-lookup"><span data-stu-id="f94fe-158">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="f94fe-159">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="f94fe-159">QuoteLine</span></span>

- <span data-ttu-id="f94fe-160">Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése meg van adva a Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="f94fe-160">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="f94fe-161">Győződjön meg róla, hogy a szükséges mértékegységek meghatározása a Sales szolgáltatásban történik.</span><span class="sxs-lookup"><span data-stu-id="f94fe-161">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="f94fe-162">Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel az **oumid.name** esetében a **SalesUnitSymbol** értékkel.</span><span class="sxs-lookup"><span data-stu-id="f94fe-162">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="f94fe-163">Nem kötelező: a következő leképezések hozzáadásával biztosíthatja, hogy az értékesítési árlisták beillesztése a Finance and Operations szolgáltatásba, ha az ügyfél vagy a termék nem tartalmaz alapértelmezett információkat:</span><span class="sxs-lookup"><span data-stu-id="f94fe-163">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="f94fe-164">**SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="f94fe-164">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="f94fe-165">Nincs alapértelmezett sablonérték a **SiteId** elemnél.</span><span class="sxs-lookup"><span data-stu-id="f94fe-165">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="f94fe-166">**WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="f94fe-166">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="f94fe-167">Nincs alapértelmezett sablonérték a **WarehouseId** elemnél.</span><span class="sxs-lookup"><span data-stu-id="f94fe-167">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="f94fe-168">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="f94fe-168">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="f94fe-169">A **engedmény**, **költségek**, és **adó** mezők egy összetett-beállítást a pénzügyi és műveletek szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="f94fe-169">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="f94fe-170">Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés.</span><span class="sxs-lookup"><span data-stu-id="f94fe-170">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="f94fe-171">Az aktuális modellben a **ár**, **engedmény**, **költség**, és **adó** mezők lezárt fájlrendszer a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f94fe-171">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="f94fe-172">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="f94fe-172">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="f94fe-173">Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="f94fe-173">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="f94fe-174">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="f94fe-174">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="f94fe-175">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="f94fe-175">QuoteHeader</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="f94fe-177">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="f94fe-177">QuoteLine</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="f94fe-179">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="f94fe-179">Related topics</span></span>

[<span data-ttu-id="f94fe-180">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="f94fe-180">Prospect to cash</span></span>](prospect-to-cash.md)


