---
title: Értékesítésiajánlat-fejlécek és -sorok közvetlen szinkronizálása a Sales szolgáltatásból a Finance and Operations szolgáltatásba
description: Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak az ajánlatfejlécek és sorok közvetlen szinkronizálásához a Microsoft Dynamics 365 for Sales és a Microsoft Dynamics 365 for Finance and Operations között.
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
ms.openlocfilehash: efe943f5c874ed041ce7984272ebc19f57cca6ef
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572581"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="bed12-103">Értékesítésiajánlat-fejlécek és -sorok szinkronizálása közvetlenül a Sales szolgáltatásból a Finance and Operations szolgáltatásba</span><span class="sxs-lookup"><span data-stu-id="bed12-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bed12-104">Ez a témakör a sablonokat és alapul szolgáló feladatokat mutatja be, amelyeket használnak az ajánlatfejlécek és sorok közvetlen szinkronizálásához a Microsoft Dynamics 365 for Sales és a Microsoft Dynamics 365 for Finance and Operations között.</span><span class="sxs-lookup"><span data-stu-id="bed12-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="bed12-105">A potenciális ügyfelek készpénzre váltása megoldás használata előtt meg kell ismernie az [Adatintegrálással a Common Data Service for Apps szolgáltatásban](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="bed12-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="bed12-106">A potenciális ügyfelek készpénzre váltása adatfolyama</span><span class="sxs-lookup"><span data-stu-id="bed12-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="bed12-107">A potenciális ügyfelek készpénzre váltása megoldás az adatszinkronizálás funkción keresztül szinkronizálja az adatokat Finance and Operations and Sales példányai között.</span><span class="sxs-lookup"><span data-stu-id="bed12-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="bed12-108">Az Adatintegrációs szolgáltatásban rendelkezésre álló A potenciális ügyfelek készpénzre váltása sablonok lehetővé teszik a termék-, ügyfél-, kapcsolatfelvételi és eladási számlákra vonatkozó adatok áramlását a Finance and Operations és a Sales között.</span><span class="sxs-lookup"><span data-stu-id="bed12-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="bed12-109">A következő ábra bemutatja a Finance and Operations és a Sales közötti adatszinkronizálást.</span><span class="sxs-lookup"><span data-stu-id="bed12-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="bed12-110">[![A potenciális ügyfelek készpénzre váltása adatfolyama](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="bed12-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="bed12-111">Sablon és feladatok</span><span class="sxs-lookup"><span data-stu-id="bed12-111">Template and tasks</span></span>

<span data-ttu-id="bed12-112">A következő sablont és alapul szolgáló feladatokat használják az értékesítési ajánlati fejlécek és sorok közvetlen szinkronizálásához a Sales és a Finance and Operations között:</span><span class="sxs-lookup"><span data-stu-id="bed12-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="bed12-113">**Sablon neve az adatintegrációban:** Értékesítési ajánlatok (Sales – Fin and Ops) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="bed12-113">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="bed12-114">**A feladatok nevei az adatintegrációs projektben:**</span><span class="sxs-lookup"><span data-stu-id="bed12-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="bed12-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="bed12-115">QuoteHeader</span></span>
    - <span data-ttu-id="bed12-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="bed12-116">QuoteLine</span></span>

<span data-ttu-id="bed12-117">A következő szinkronizálási feladatok kötelezőek, mielőtt az értékesítési ajánlat fejlécének és sorainak szinkronizálása megtörténhetne:</span><span class="sxs-lookup"><span data-stu-id="bed12-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="bed12-118">Termékek (Fin and Ops – Sales) – Közvetlen</span><span class="sxs-lookup"><span data-stu-id="bed12-118">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="bed12-119">Számlák (Sales a Fin and Opshoz) – Közvetlen (ha van)</span><span class="sxs-lookup"><span data-stu-id="bed12-119">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="bed12-120">Kapcsolattartók vevőkkel (Sales a Fin and Opshoz) – közvetlen (ha van)</span><span class="sxs-lookup"><span data-stu-id="bed12-120">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="bed12-121">Entitás beállítása</span><span class="sxs-lookup"><span data-stu-id="bed12-121">Entity set</span></span>

| <span data-ttu-id="bed12-122">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="bed12-122">Sales</span></span>        | <span data-ttu-id="bed12-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bed12-123">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="bed12-124">Idézetek</span><span class="sxs-lookup"><span data-stu-id="bed12-124">Quotes</span></span>       | <span data-ttu-id="bed12-125">CDS értékesítésiajánlat-fejléc</span><span class="sxs-lookup"><span data-stu-id="bed12-125">CDS sales quotation header</span></span> |
| <span data-ttu-id="bed12-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="bed12-126">QuoteDetails</span></span> | <span data-ttu-id="bed12-127">CDS értékesítési ajánlat sorai</span><span class="sxs-lookup"><span data-stu-id="bed12-127">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="bed12-128">Entitás folyamata</span><span class="sxs-lookup"><span data-stu-id="bed12-128">Entity flow</span></span>

<span data-ttu-id="bed12-129">Az értékesítési ajánlatok létrehozása a Sales-ben történik, majd szinkronizálódnak a Finance and Operations programban.</span><span class="sxs-lookup"><span data-stu-id="bed12-129">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="bed12-130">A Sales értékesítési ajánlatai csak akkor szinkronizálódnak, ha teljesülnek az alábbi feltételek:</span><span class="sxs-lookup"><span data-stu-id="bed12-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="bed12-131">Az értékesítési ajánlatban szereplő összes termék külsőleg van karbantartva.</span><span class="sxs-lookup"><span data-stu-id="bed12-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="bed12-132">Miután rákattint az **Ajánlat aktiválása** lehetőségre, az értékesítési árajánlat aktívvá válik.</span><span class="sxs-lookup"><span data-stu-id="bed12-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="bed12-133">Potenciális vevő értékesítési készpénzfizetési megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="bed12-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="bed12-134">A **Csak külsőleg karbantartott termékei vannak** mező hozzáadódott az **Ajánlat** entitáshoz annak érdekében, hogy konzisztensen követni lehessen, hogy az értékesítési ajánlat teljes mértékben külsőleg karbantartott termékekből áll-e.</span><span class="sxs-lookup"><span data-stu-id="bed12-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="bed12-135">Ha az értékesítési árfolyamok csak külsőleg fenntartott termékeket tartalmaznak, a termékeket a Finance and Operations kezeli.</span><span class="sxs-lookup"><span data-stu-id="bed12-135">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="bed12-136">Ez a viselkedés garantálja, hogy nem próbálja szinkronizálni az értékesítési ajánlati sorokat olyan termékekkel, amelyek ismeretlenek a Finance and Operations számára.</span><span class="sxs-lookup"><span data-stu-id="bed12-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="bed12-137">Az értékesítési ajánlat minden terméke frissül a **Csak külsőleg karbantartott termékei vannak** információval az árajánlat fejlécéből.</span><span class="sxs-lookup"><span data-stu-id="bed12-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="bed12-138">Ezek az információk megtalálhatók az **Ajánlat csak külsőleg fenntartott termékekre vonatkozik** mezőben, a **QuoteDetails** entitásnál.</span><span class="sxs-lookup"><span data-stu-id="bed12-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="bed12-139">Kedvezményt lehet hozzáadni az idevonatkozó termékhez, és szinkronizálva lesz a Finance and Operations szolgáltatással.</span><span class="sxs-lookup"><span data-stu-id="bed12-139">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="bed12-140">A fejlécen az **Engedmény**, **Költségek** és **Adó** mezők a Finance and Operations szolgáltatásból szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="bed12-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="bed12-141">Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés.</span><span class="sxs-lookup"><span data-stu-id="bed12-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="bed12-142">Az aktuális modellben az **Ár**, **Engedmény**, **Költség** és az **Adó** mezők lezárt fájlrendszer és kezeli a Finance and Operations felületén.</span><span class="sxs-lookup"><span data-stu-id="bed12-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="bed12-143">Az értékesítési a megoldás teszi a következő mezők írásvédett, mivel az értékek nem szinkronizálja a késedelmi a műveletekhez pedig:</span><span class="sxs-lookup"><span data-stu-id="bed12-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="bed12-144">Csak olvasható mezőket az értékesítésiajánlat-fejlécen:**Árengedmény%** Árengedmény%, **Árengedmény** és**Fuvardíj**</span><span class="sxs-lookup"><span data-stu-id="bed12-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="bed12-145">Csak olvasható mezők az ajánlat termékein: **Adó**</span><span class="sxs-lookup"><span data-stu-id="bed12-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="bed12-146">Előfeltételek és hozzárendelési beállítás</span><span class="sxs-lookup"><span data-stu-id="bed12-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="bed12-147">Értékesítési ajánlatok szinkronizálása előtt fontos frissíteni a rendszert a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="bed12-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="bed12-148">Beállítás a Salesben</span><span class="sxs-lookup"><span data-stu-id="bed12-148">Setup in Sales</span></span>

- <span data-ttu-id="bed12-149">Győződjön meg róla, hogy beállították az engedélyeket ahhoz a csapathoz, amelytől a Sales kapcsolatkészletének felhasználója hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="bed12-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="bed12-150">Bemutatóadatok használatakor rendszerint a felhasználó rendelkezik rendszergazdai hozzáféréssel, de nem a csoport.</span><span class="sxs-lookup"><span data-stu-id="bed12-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="bed12-151">Ha a csapatnak nincs adminisztrátori hozzáférése, akkor ha a projektet az adatintegrálásból futtatja, hibaüzenet jelenik meg, amely azt jelzi, hogy a fő csapat hiányzik.</span><span class="sxs-lookup"><span data-stu-id="bed12-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="bed12-152">A csoport engedélyeinek beállításához kattintson a **beállítások**&gt;**biztonsági**&gt;**csapatok**, és válassza ki a csapatot.</span><span class="sxs-lookup"><span data-stu-id="bed12-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="bed12-153">Válasszon **szerepkörök kezelése**, és válassza ki a kívánt engedélyeket, például rendelkező szerepkör **rendszergazda**.</span><span class="sxs-lookup"><span data-stu-id="bed12-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="bed12-154">Lépjen a **Beállítások** &gt; **Adminisztráció** &gt; **Rendszerbeállítások** &gt; **Értékesítés** pontra, és győződjön meg róla, hogy a következő beállításokat használja:</span><span class="sxs-lookup"><span data-stu-id="bed12-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="bed12-155">A **Rendszer díjazási számítási rendszerének használata** beállítás értéke **Igen**.</span><span class="sxs-lookup"><span data-stu-id="bed12-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="bed12-156">Az **Engedményszámítási módszer** mező értéke a **Sortétel**.</span><span class="sxs-lookup"><span data-stu-id="bed12-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="bed12-157">Beállítás az adatintegrációs projektben</span><span class="sxs-lookup"><span data-stu-id="bed12-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="bed12-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="bed12-158">QuoteHeader</span></span>

- <span data-ttu-id="bed12-159">Győződjön meg róla, hogy a szükséges leképezés létezik: **Shipto\_country** – **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="bed12-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="bed12-160">Az Értékmegfeleltetés is megadható egy alapértelmezett érték, amely akkor használható, ha az érték üresen marad.</span><span class="sxs-lookup"><span data-stu-id="bed12-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="bed12-161">egyszerűen állítsa a bal oldalt az "Üres" értékre, és állítsa a jobb oldalt a kívánt országra vagy régióra.</span><span class="sxs-lookup"><span data-stu-id="bed12-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="bed12-162">Ezzel a módszerrel nem kell beírni az országot vagy régiót a belföldi rendeléseknél.</span><span class="sxs-lookup"><span data-stu-id="bed12-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="bed12-163">A sablon értéke olyan értékkérkép, amelyben több ország vagy régió van leképezve, és ahol az üres érték = **Amerikai Egyesült Államok**.</span><span class="sxs-lookup"><span data-stu-id="bed12-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="bed12-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="bed12-164">QuoteLine</span></span>

- <span data-ttu-id="bed12-165">Győződjön meg arról, hogy a **SalesUnitSymbol** szükséges értékmegfeleltetése meg van adva a Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="bed12-165">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="bed12-166">Győződjön meg róla, hogy a szükséges mértékegységek meghatározása a Sales szolgáltatásban történik.</span><span class="sxs-lookup"><span data-stu-id="bed12-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="bed12-167">Olyan sablonérték, amely rendelkezik értékmegfeleltetéssel az **oumid.name** esetében a **SalesUnitSymbol** értékkel.</span><span class="sxs-lookup"><span data-stu-id="bed12-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="bed12-168">Nem kötelező: a következő leképezések hozzáadásával biztosíthatja, hogy az értékesítési árlisták beillesztése a Finance and Operations szolgáltatásba, ha az ügyfél vagy a termék nem tartalmaz alapértelmezett információkat:</span><span class="sxs-lookup"><span data-stu-id="bed12-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="bed12-169">**SiteId** – hely a Pénzügy és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="bed12-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="bed12-170">Nincs alapértelmezett sablonérték a **SiteId** elemnél.</span><span class="sxs-lookup"><span data-stu-id="bed12-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="bed12-171">**WarehouseId** – hely a raktár és műveletek árajánlatok és értékesítési rendelések sorainak létrehozásához szükséges.</span><span class="sxs-lookup"><span data-stu-id="bed12-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="bed12-172">Nincs alapértelmezett sablonérték a **WarehouseId** elemnél.</span><span class="sxs-lookup"><span data-stu-id="bed12-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="bed12-173">Sablonleképezés az adatintegrátorban</span><span class="sxs-lookup"><span data-stu-id="bed12-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="bed12-174">A **engedmény**, **költségek**, és **adó** mezők egy összetett-beállítást a pénzügyi és műveletek szabályozhatók.</span><span class="sxs-lookup"><span data-stu-id="bed12-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="bed12-175">Ezzel a beállítással jelenleg nem támogatott integrációs megfeleltetés.</span><span class="sxs-lookup"><span data-stu-id="bed12-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="bed12-176">Az aktuális modellben a **ár**, **engedmény**, **költség**, és **adó** mezők lezárt fájlrendszer a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bed12-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="bed12-177">A **fizetési feltételek**, **feltételek áruszállítási**, **szállítási feltételek**, **szállítási mód**, és **szállítási mód** mezők nem találhatók meg a alapértelmezett-leképezései.</span><span class="sxs-lookup"><span data-stu-id="bed12-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="bed12-178">Ezek a mezők megfeleltetéséhez be kell állítania egy adott szervezetek között szinkronizált entitás adatainak értékmegfeleltetések.</span><span class="sxs-lookup"><span data-stu-id="bed12-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="bed12-179">Az alábbi ábrákon sablon hozzárendelést például adatok integrátor megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="bed12-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="bed12-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="bed12-180">QuoteHeader</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="bed12-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="bed12-182">QuoteLine</span></span>

![Sablonleképezés az adatintegrátorban](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="bed12-184">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="bed12-184">Related topics</span></span>

[<span data-ttu-id="bed12-185">A potenciális ügyfelek készpénzre váltása</span><span class="sxs-lookup"><span data-stu-id="bed12-185">Prospect to cash</span></span>](prospect-to-cash.md)

