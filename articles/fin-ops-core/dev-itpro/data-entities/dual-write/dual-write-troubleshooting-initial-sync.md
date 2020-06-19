---
title: Problémák elhárítása a kezdeti szinkronizációkor
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410081"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="6a1be-103">Problémák elhárítása a kezdeti szinkronizációkor</span><span class="sxs-lookup"><span data-stu-id="6a1be-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6a1be-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="6a1be-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="6a1be-105">Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák.</span><span class="sxs-lookup"><span data-stu-id="6a1be-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a1be-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="6a1be-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="6a1be-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="6a1be-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="6a1be-108">A kezdeti szinkronizálási hibák keresése egy Finance and Operations-alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="6a1be-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="6a1be-109">Miután engedélyezte a leképezési sablonokat, a leképezések állapotának **Fut** állapotnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6a1be-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="6a1be-110">Ha az állapot **Nem fut**, akkor hiba történt a kezdeti szinkronizálás során.</span><span class="sxs-lookup"><span data-stu-id="6a1be-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="6a1be-111">A hibák megtekintéséhez válassza a **Kettős írás** oldal **Kezdeti szinkronizálás adatai** lapját.</span><span class="sxs-lookup"><span data-stu-id="6a1be-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Kezdeti szinkronizálás adatai lapja](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="6a1be-113">A kezdeti szinkronizálás nem hajtható végre: 400 hibás kérelem</span><span class="sxs-lookup"><span data-stu-id="6a1be-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="6a1be-114">**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="6a1be-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="6a1be-115">A következő hibaüzenetek jelenhetnek meg a leképezlés és a kezdeti szinkronizálás futtatása során:</span><span class="sxs-lookup"><span data-stu-id="6a1be-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="6a1be-116">*A távoli kiszolgáló hibát adott vissza: (400) hibás kérelem.), AX exportálás hibát észlelt*</span><span class="sxs-lookup"><span data-stu-id="6a1be-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="6a1be-117">Íme, egy példa a teljes hibaüzenetre.</span><span class="sxs-lookup"><span data-stu-id="6a1be-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="6a1be-118">Ha ez a hiba folyamatosan történik, és a kezdeti szinkronizálás nem hajtható végre, hajtsa végre az alábbi lépéseket a probléma megoldásához.</span><span class="sxs-lookup"><span data-stu-id="6a1be-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="6a1be-119">Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre (VM).</span><span class="sxs-lookup"><span data-stu-id="6a1be-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="6a1be-120">Nyissa meg a Microsoft Management Console programot.</span><span class="sxs-lookup"><span data-stu-id="6a1be-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="6a1be-121">Győződjön meg arról, hogy a **Szolgáltatások** panelen fut a Microsoft Dynamics 365 adatimportálási és -exportálási keretrendszer szolgáltatása.</span><span class="sxs-lookup"><span data-stu-id="6a1be-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="6a1be-122">Indítsa újra, ha leállították, mert erre szükség van a kezdeti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="6a1be-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="6a1be-123">Kezdeti szinkronizálási hiba: 403 Tiltott</span><span class="sxs-lookup"><span data-stu-id="6a1be-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="6a1be-124">A következő hibaüzenetek jelenhetnek meg a kezdeti szinkronizálás során:</span><span class="sxs-lookup"><span data-stu-id="6a1be-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="6a1be-125">*(\[Tiltott\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.), AX exportálás hibát észlelt*</span><span class="sxs-lookup"><span data-stu-id="6a1be-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="6a1be-126">Egy hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6a1be-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="6a1be-127">Bejelentkezés a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="6a1be-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="6a1be-128">Az **Azure Active Directory-alkalmazások** oldalon törölje a **DtAppID** klienst, majd adja hozzá újra.</span><span class="sxs-lookup"><span data-stu-id="6a1be-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Azure AD alkalmazások listájának megnyitása](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="6a1be-130">Önmagára mutató hivatkozással vagy körkörös hivatkozással kapcsolatos hibák a kezdeti szinkronizálás során</span><span class="sxs-lookup"><span data-stu-id="6a1be-130">Self-reference or circular-reference failures during initial synchronization</span></span>

<span data-ttu-id="6a1be-131">Hibaüzenet jelenhet meg, ha bármely leképezésben önmagára mutató hivatkozás szerepel:</span><span class="sxs-lookup"><span data-stu-id="6a1be-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="6a1be-132">A hibák a következő kategóriákba sorolhatók:</span><span class="sxs-lookup"><span data-stu-id="6a1be-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="6a1be-133">Vendors V2 – msdyn_vendors entitás-hozzárendelés</span><span class="sxs-lookup"><span data-stu-id="6a1be-133">Vendors V2 to msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="6a1be-134">Customers V3 – Fiókok entitásleképezés</span><span class="sxs-lookup"><span data-stu-id="6a1be-134">Customers V3 to Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="6a1be-135">Hiba elhárítása a Szállítók V2 – msdyn_vendors entitásleképezésben</span><span class="sxs-lookup"><span data-stu-id="6a1be-135">Resolve an error in Vendors V2 to msdyn_vendors entity mapping</span></span>

<span data-ttu-id="6a1be-136">Előfordulhat, hogy a következő kezdeti szinkronizálási hibákkal találkozik a **Szállítók V2** – **msdyn_vendors** leképezés során, ha az entitások rendelkeznek meglévő rekordokkal amelyek értékeket tartalmaznak a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="6a1be-136">You might run into the following initial sync errors on the **Vendors V2** to **msdyn_vendors** mapping if the entities have existing records with values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="6a1be-137">Ez azért van így, mert az **InvoiceVendorAccountNumber** egy saját magára hivatkozó mező, és a **PrimaryContactPersonId** egy körkörös hivatkozás a szállítói hozzárendelésben.</span><span class="sxs-lookup"><span data-stu-id="6a1be-137">This because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6a1be-138">*Nem sikerült a mező GUID-értékét feloldani: <field> . A keresés nem található: <value> . Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="6a1be-138">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

<span data-ttu-id="6a1be-139">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="6a1be-139">Here are a couple of examples:</span></span>

- <span data-ttu-id="6a1be-140">*Nem sikerült feloldani a GUID-értéket a mezőhöz: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="6a1be-140">*Couldn't resolve the guid for the field: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="6a1be-141">*Nem sikerült feloldani a GUID-értéket a mezőhöz: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. A keresés nem található: V24-1. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span><span class="sxs-lookup"><span data-stu-id="6a1be-141">*Couldn't resolve the guid for the field: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span></span>

<span data-ttu-id="6a1be-142">Ha a szállítói entitásnak ezekben a mezőiben értékekkel rendelkező rekordok találhatók akkor a kezdeti szinkronizálás sikeres befejezéséhez kövesse az alábbi szakasz lépéseit.</span><span class="sxs-lookup"><span data-stu-id="6a1be-142">If you have records with values in these fields in the vendor entity follow the steps in the below section to complete initial sync successfully.</span></span>

1. <span data-ttu-id="6a1be-143">A Finance and Operations alkalmazásban törölje a **PrimaryContactPersonId** és az **InvoiceVendorAccountNumber** mezőket a leképezésből, és mentse a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="6a1be-143">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping and save the changes.</span></span>

    1. <span data-ttu-id="6a1be-144">Nyissa meg a **Vendors V2 (msdyn_vendors)** kettős írás leképezési lapját , és válassza ki az **Entitás-leképezések** fület: A bel oldali szűrőben válassza a **Finance and Operations apps.Vendors V2** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a1be-144">Navigate to the dual-write mapping page for **Vendors V2 (msdyn_vendors)**, and select the **Entity mappings** tab. In the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="6a1be-145">A jobb oldali szűrőben válassz a **Sales.Vendor** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a1be-145">In the right filter, select **Sales.Vendor**.</span></span>

    2. <span data-ttu-id="6a1be-146">Keressen rá a **primarycontactperson** elemre a **PrimaryContactPersonId** forrásmező megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="6a1be-146">Search for **primarycontactperson** to find the source field **PrimaryContactPersonId**.</span></span>
    
    3. <span data-ttu-id="6a1be-147">Kattintson a **Műveletek** gombra, majd válassza a **Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="6a1be-147">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás 3](media/vend_selfref3.png)
    
    4. <span data-ttu-id="6a1be-149">Az **InvoiceVendorAccountNumber** mező törléséhez ismételje meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="6a1be-149">Repeat to delete the **InvoiceVendorAccountNumber** field.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás 4](media/vend-selfref4.png)
    
    5. <span data-ttu-id="6a1be-151">Mentse a leképezés módosításait.</span><span class="sxs-lookup"><span data-stu-id="6a1be-151">Save the mapping changes.</span></span>

2. <span data-ttu-id="6a1be-152">Tiltsa le a **Szállító V2** entitás módosítási nyomon követését.</span><span class="sxs-lookup"><span data-stu-id="6a1be-152">Disable the change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="6a1be-153">Navigáljon az **Adatkezelés \> Adatentitások** részhez.</span><span class="sxs-lookup"><span data-stu-id="6a1be-153">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="6a1be-154">Válassza ki a **Szállítók V2** entitást.</span><span class="sxs-lookup"><span data-stu-id="6a1be-154">Select the **Vendors V2** entity.</span></span>
    
    3. <span data-ttu-id="6a1be-155">Kattintson a menüsor **Beállítások** elemére, majd a **Változáskövetés** elemre.</span><span class="sxs-lookup"><span data-stu-id="6a1be-155">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás 5](media/selfref_options.png)
    
    4. <span data-ttu-id="6a1be-157">Kattintson a **Változáskövetés tiltása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6a1be-157">Click **Disable Change Tracking**.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás 6](media/selfref_tracking.png)

3. <span data-ttu-id="6a1be-159">Futtassa a **Szállítók v2 (msdyn_vendors)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-159">Run the initial sync of **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="6a1be-160">A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.</span><span class="sxs-lookup"><span data-stu-id="6a1be-160">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="6a1be-161">Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-161">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="6a1be-162">Akkor kell szinkronizálnia ezt a leképezést, ha szinkronizálni szeretné az elsődleges kapcsolattartó mezőt a szállítók entitásban, mert a kapcsolattartók rekordjainak kezdeti szinkronizálását is el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="6a1be-162">You must sync this mapping if you want to sync primary contact field on vendors entity as the contacts records also need to be initial synced.</span></span>

5. <span data-ttu-id="6a1be-163">Adja hozzá ismét a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** mezőket a **Szállítók v2 (msdyn_vendors)** leképezéshez, és mentse a leképezést.</span><span class="sxs-lookup"><span data-stu-id="6a1be-163">Add the fields **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** back to the **Vendors V2 (msdyn_vendors)** mapping and save the mapping.</span></span>

6. <span data-ttu-id="6a1be-164">Futtassa ismét a **Szállítók v2 (msdyn_vendors)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-164">Run the initial sync again for the **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="6a1be-165">Minden rekord szinkronizálva lesz, mert a változások követése le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="6a1be-165">All the records will be synced, because change tracking is disabled.</span></span>

7. <span data-ttu-id="6a1be-166">Engedélyezze a **Szállító V2** entitás módosításainak nyomon követését.</span><span class="sxs-lookup"><span data-stu-id="6a1be-166">Enable change tracking for the **Vendors V2** entity.</span></span>

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="6a1be-167">Hiba elhárítása a Vevők v3 – Ügyfelek a entitás-leképezésben</span><span class="sxs-lookup"><span data-stu-id="6a1be-167">Resolve an error in Customers V3 to Accounts entity mapping</span></span>

<span data-ttu-id="6a1be-168">Előfordulhat, hogy a következő kezdeti szinkronizálási hibákkal találkozik az **Ügyfelek V3** – **Partnerek** leképezés során, ha az entitások rendelkeznek meglévő rekordokkal amelyek értékeket tartalmaznak a **ContactPersonID** és **InvoiceAccount** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="6a1be-168">You might run into the following initial sync errors on the **Customers V3** to **Accounts** mapping if the entities have existing records with values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="6a1be-169">Ez azért van így, mert az **InvoiceAccount** egy saját magára hivatkozó mező, és a **ContactPersonID** egy körkörös hivatkozás a szállítói hozzárendelésben.</span><span class="sxs-lookup"><span data-stu-id="6a1be-169">This because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="6a1be-170">*Nem sikerült a mező GUID-értékét feloldani: <field> . A keresés nem található: <value> . Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="6a1be-170">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

- <span data-ttu-id="6a1be-171">*Nem sikerült feloldani a GUID-értéket a mezőhöz: primarycontactid.msdyn_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="6a1be-171">*Couldn't resolve the guid for the field: primarycontactid.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="6a1be-172">*Nem sikerült feloldani a GUID-értéket a mezőhöz: msdyn_billingaccount.accountnumber. A keresés nem található: 1206-1. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span><span class="sxs-lookup"><span data-stu-id="6a1be-172">*Couldn't resolve the guid for the field: msdyn_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span></span>

<span data-ttu-id="6a1be-173">Ha az ügyfél entitásnak ezekben a mezőiben értékekkel rendelkező rekordok találhatók akkor a kezdeti szinkronizálás sikeres befejezéséhez kövesse az alábbi szakasz lépéseit.</span><span class="sxs-lookup"><span data-stu-id="6a1be-173">If you have records with values in these fields in the customer entity follow the steps in the below section to complete initial sync successfully.</span></span> <span data-ttu-id="6a1be-174">Ezt a megközelítést használhatja bármely gyári entitáshoz például a Partnerek és Kapcsolattartók entitásokhoz.</span><span class="sxs-lookup"><span data-stu-id="6a1be-174">You can use this approach for any out-of-the-box entities such Accounts and Contacts.</span></span>

1. <span data-ttu-id="6a1be-175">A Finance and Operations alkalmazásban törölje a **ContactPersonID** és **InvoiceAccount** mezőket az **Ügyfelek V3 (partnerek)** leképezésből, és mentse a leképezést.</span><span class="sxs-lookup"><span data-stu-id="6a1be-175">In the Finance and Operations app, delete the fields **ContactPersonID** and **InvoiceAccount** from the **Customers V3 (accounts)** mapping and save the mapping.</span></span>

    1. <span data-ttu-id="6a1be-176">Nyissa meg az **Ügyfelek V3 (partnerek)** kettős írás leképezési lapját , és válassza ki az **Entitás-leképezések** fület: A bel oldali szűrőben válassza a **Finance and Operations app.Customers V3** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a1be-176">Navigate to the dual-write mapping page for **Customers V3 (accounts)**, select the **Entity mappings** tab. In the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="6a1be-177">A jobb oldali szűrőben válassza a **Common Data Service.Account** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a1be-177">In the right filter, select **Common Data Service.Account**.</span></span>

    2. <span data-ttu-id="6a1be-178">Keressen rá a **contactperson** elemre a **ContactPersonID** forrásmező megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="6a1be-178">Search for **contactperson** to find the source field **ContactPersonID**.</span></span>
    
    3. <span data-ttu-id="6a1be-179">Kattintson a **Műveletek** gombra, majd válassza a **Törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="6a1be-179">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás 3](media/cust_selfref3.png)
    
    4. <span data-ttu-id="6a1be-181">Az **InvoiceAccount** mező törléséhez ismételje meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="6a1be-181">Repeat to delete the **InvoiceAccount** field.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás](media/cust_selfref4.png)
    
    5. <span data-ttu-id="6a1be-183">Mentse a leképezés módosításait.</span><span class="sxs-lookup"><span data-stu-id="6a1be-183">Save the mapping changes.</span></span>

2. <span data-ttu-id="6a1be-184">Tiltsa le az **Ügyfelek V3** entitás módosítási nyomon követését.</span><span class="sxs-lookup"><span data-stu-id="6a1be-184">Disable the change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="6a1be-185">Navigáljon az **Adatkezelés \> Adatentitások** részhez.</span><span class="sxs-lookup"><span data-stu-id="6a1be-185">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="6a1be-186">Válassza ki az **Ügyfelek V3** entitást.</span><span class="sxs-lookup"><span data-stu-id="6a1be-186">Select the **Customers V3** entity.</span></span>
    
    3. <span data-ttu-id="6a1be-187">Kattintson a menüsor **Beállítások** elemére, majd a **Változáskövetés** elemre.</span><span class="sxs-lookup"><span data-stu-id="6a1be-187">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás 5](media/selfref_options.png)
    
    4. <span data-ttu-id="6a1be-189">Kattintson a **Változáskövetés tiltása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6a1be-189">Click **Disable Change Tracking**.</span></span>
    
        ![önmagára mutató vagy körkörös hivatkozás 6](media/selfref_tracking.png)

3. <span data-ttu-id="6a1be-191">Futtassa az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-191">Run the initial sync for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6a1be-192">A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.</span><span class="sxs-lookup"><span data-stu-id="6a1be-192">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="6a1be-193">Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-193">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="6a1be-194">2 azonos nevű leképezés van.</span><span class="sxs-lookup"><span data-stu-id="6a1be-194">There are 2 maps with the same name.</span></span> <span data-ttu-id="6a1be-195">Válassza ki azt, amelyiknek a leírása **Kettős írású sablon a FO.CDS Vendor Contacts V2 – CDS.Contacts szinkronizálásához. Új csomag szükséges \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="6a1be-195">Select the one with the description **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span> <span data-ttu-id="6a1be-196">a leképezés **Részletek** lapján.</span><span class="sxs-lookup"><span data-stu-id="6a1be-196">on the **Details** tab of the map.</span></span>

5. <span data-ttu-id="6a1be-197">Adja hozzá ismét az **InvoiceAccount** és **ContactPersonId** mezőket az **Ügyfelek V3 (partnerek)** leképezéshez, és mentse a leképezést.</span><span class="sxs-lookup"><span data-stu-id="6a1be-197">Add the fields **InvoiceAccount** and **ContactPersonId** back to the **Customers V3 (Accounts)** mapping and save the mapping.</span></span> <span data-ttu-id="6a1be-198">Most az **InvoiceAccount** és a **ContactPersonId** mező is újra része az élő szinkronizálási üzemmódnak.</span><span class="sxs-lookup"><span data-stu-id="6a1be-198">Now, both the **InvoiceAccount** field and the **ContactPersonId** field are again part of live sync mode.</span></span> <span data-ttu-id="6a1be-199">A következő lépésben végre kell hajtania ezeknek a mezőknek a kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-199">In the next step, you complete the initial sync for these fields.</span></span>

6. <span data-ttu-id="6a1be-200">Futtassa ismét az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-200">Run the initial sync again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="6a1be-201">Mivel a változások követése le van tiltva, a szinkronizálás futtatása szinkronizálja az **InvoiceAccount** és a **ContactPersonId** adatait a Finance and Operations alkalmazásból a Common Data Service-szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="6a1be-201">Because change tracking is disabled, running the sync will sync the data for **InvoiceAccount** and **ContactPersonId** from the Finance and Operations app to Common Data Service.</span></span>

7. <span data-ttu-id="6a1be-202">Ha szinkronizálni szeretné az **InvoiceAccount** és a **ContactPersonId** adatait a Common Data Service-szolgáltatásból a Finance and Operations alkalmazásba, akkor egy adatintegrációs projektet használ.</span><span class="sxs-lookup"><span data-stu-id="6a1be-202">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations, you use a data integration project.</span></span>

    1. <span data-ttu-id="6a1be-203">A Power Apps felületén hozzon létre egy adatintegrációs projektet az **Sales.Account** és a **Finance and Operations apps.Customers V3** entitások között.</span><span class="sxs-lookup"><span data-stu-id="6a1be-203">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="6a1be-204">Az adatok irányának a következőnek kell lennie: Common Data Service – Finance and Operations alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="6a1be-204">The data direction must be from Common Data Service to the Finance and Operations app.</span></span>  <span data-ttu-id="6a1be-205">Mivel az **InvoiceAccount** egy új attribútum a kettős írás funkcióban, érdemes kihagyni kezdeti szinkronizálást ehhez az attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="6a1be-205">Because **InvoiceAccount** is a new attribute in dual-write, you may want to skip initial sync for this attribute.</span></span> <span data-ttu-id="6a1be-206">További információkért tekintse át az [Adatok integrálása a Common Data Service-szolgáltatásba](https://docs.microsoft.com/power-platform/admin/data-integrator) című részt.</span><span class="sxs-lookup"><span data-stu-id="6a1be-206">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="6a1be-207">A következő képen egy olyan projekt látható, amely frissíti a **CustomerAccount** és a **ContactPersonId** entitásokat.</span><span class="sxs-lookup"><span data-stu-id="6a1be-207">The following image shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![önmagára mutató vagy körkörös hivatkozás](media/cust_selfref6.png)

    2. <span data-ttu-id="6a1be-209">Adja meg a vállalat feltételeit a szűrőben a Common Data Service oldalán, mivel csak a szűrőfeltételeknek megfelelő rekordok lesznek frissítve a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="6a1be-209">Add the company criteria in the filter on Common Data Service side, because only the records that match filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="6a1be-210">Szűrő hozzáadásához kattintson a szűrő ikonra.</span><span class="sxs-lookup"><span data-stu-id="6a1be-210">To add a filter, click the filter icon.</span></span> <span data-ttu-id="6a1be-211">A **Lekérdezés szerkesztése** párbeszédpanelen hozzáadhat egy ilyen szűrőlekérdezést **_msdyn_company_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="6a1be-211">In the **Edit query** dialog, you can add a filter query like **_msdyn_company_value eq '\<guid\>'**.</span></span> <span data-ttu-id="6a1be-212">Ha a szűrő ikon nem látszik, akkor hozzon létre egy támogató jegyet, és kérje meg az adatintegrációs csoportot, hogy engedélyezze a szűrő képességét a bérlőjén.</span><span class="sxs-lookup"><span data-stu-id="6a1be-212">If the filter icon is not present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span> <span data-ttu-id="6a1be-213">Ha nem ír be szűrő lekérdezést az **_msdyn_company_value** elemhez, akkor az összes rekord szinkronizálva lesz.</span><span class="sxs-lookup"><span data-stu-id="6a1be-213">If you do not enter a filter query for **_msdyn_company_value**, then all the records are synced.</span></span>

        ![önmagára mutató vagy körkörös hivatkozás](media/cust_selfref7.png)

        <span data-ttu-id="6a1be-215">Ezzel végrehajtja a rekordok kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="6a1be-215">This completes the initial sync of the records.</span></span>

8. <span data-ttu-id="6a1be-216">Engedélyezze **Ügyfelek V3 entitás** változáskövetését a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="6a1be-216">Enable change tracking for the **Customers V3** entity in the Finance and Operations app.</span></span>

