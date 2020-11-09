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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 4d0ca1fb4b7a4964194516544686b6bb7d26e76c
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997326"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="9a230-103">Problémák elhárítása a kezdeti szinkronizációkor</span><span class="sxs-lookup"><span data-stu-id="9a230-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9a230-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="9a230-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="9a230-105">Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák.</span><span class="sxs-lookup"><span data-stu-id="9a230-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a230-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="9a230-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="9a230-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="9a230-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="9a230-108">A kezdeti szinkronizálási hibák keresése egy Finance and Operations-alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="9a230-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="9a230-109">Miután engedélyezte a leképezési sablonokat, a leképezések állapotának **Fut** állapotnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9a230-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="9a230-110">Ha az állapot **Nem fut** , akkor hiba történt a kezdeti szinkronizálás során.</span><span class="sxs-lookup"><span data-stu-id="9a230-110">If the status is **Not running** , errors occurred during initial synchronization.</span></span> <span data-ttu-id="9a230-111">A hibák megtekintéséhez válassza a **Kettős írás** oldal **Kezdeti szinkronizálás adatai** lapját.</span><span class="sxs-lookup"><span data-stu-id="9a230-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Hiba a kezdeti szinkronizálás részletek lapján](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="9a230-113">A kezdeti szinkronizálás nem hajtható végre: 400 hibás kérelem</span><span class="sxs-lookup"><span data-stu-id="9a230-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="9a230-114">**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="9a230-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="9a230-115">A következő hibaüzenetek jelenhetnek meg a leképezlés és a kezdeti szinkronizálás futtatása során:</span><span class="sxs-lookup"><span data-stu-id="9a230-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="9a230-116">*(\[Hibás kérelem\], A távoli kiszolgáló hibát adott vissza: (400) hibás kérelem.), AX exportálás hibát észlelt*</span><span class="sxs-lookup"><span data-stu-id="9a230-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="9a230-117">Íme, egy példa a teljes hibaüzenetre.</span><span class="sxs-lookup"><span data-stu-id="9a230-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="9a230-118">Ha ez a hiba folyamatosan történik, és a kezdeti szinkronizálás nem hajtható végre, hajtsa végre az alábbi lépéseket a probléma megoldásához.</span><span class="sxs-lookup"><span data-stu-id="9a230-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="9a230-119">Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre (VM).</span><span class="sxs-lookup"><span data-stu-id="9a230-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="9a230-120">Nyissa meg a Microsoft Management Console programot.</span><span class="sxs-lookup"><span data-stu-id="9a230-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="9a230-121">Győződjön meg arról, hogy a **Szolgáltatások** panelen fut a Microsoft Dynamics 365 adatimportálási és -exportálási keretrendszer szolgáltatása.</span><span class="sxs-lookup"><span data-stu-id="9a230-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="9a230-122">Indítsa újra, ha leállították, mert erre szükség van a kezdeti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="9a230-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="9a230-123">Kezdeti szinkronizálási hiba: 403 Tiltott</span><span class="sxs-lookup"><span data-stu-id="9a230-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="9a230-124">A következő hibaüzenetek jelenhetnek meg a kezdeti szinkronizálás során:</span><span class="sxs-lookup"><span data-stu-id="9a230-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="9a230-125">*(\[Tiltott\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.), AX exportálás hibát észlelt*</span><span class="sxs-lookup"><span data-stu-id="9a230-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="9a230-126">Egy hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9a230-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="9a230-127">Bejelentkezés a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9a230-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="9a230-128">Az **Azure Active Directory-alkalmazások** oldalon törölje a **DtAppID** klienst, majd adja hozzá újra.</span><span class="sxs-lookup"><span data-stu-id="9a230-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![DtAppID-ügyfél a Azure AD alkalmazások listáján](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="9a230-130">Önmagára mutató hivatkozással vagy körkörös hivatkozással kapcsolatos hibák a kezdeti szinkronizálás során</span><span class="sxs-lookup"><span data-stu-id="9a230-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="9a230-131">Hibaüzenet jelenhet meg, ha bármely leképezésben önmagára mutató hivatkozás szerepel:</span><span class="sxs-lookup"><span data-stu-id="9a230-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="9a230-132">A hibák a következő kategóriákba sorolhatók:</span><span class="sxs-lookup"><span data-stu-id="9a230-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="9a230-133">Hiba elhárítása a szállítók V2–to–msdyn_vendors entitásleképezésben</span><span class="sxs-lookup"><span data-stu-id="9a230-133">Errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="9a230-134">Hiba elhárítása a vevők v3 – ügyfelek entitásleképezésben</span><span class="sxs-lookup"><span data-stu-id="9a230-134">Errors in the Customers V3–to–Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="9a230-135">Hibák elhárítása a szállítók V2–to–msdyn_vendors entitásleképezésben</span><span class="sxs-lookup"><span data-stu-id="9a230-135">Resolve errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>

<span data-ttu-id="9a230-136">Előfordulhat, hogy kezdeti szinkronizálási hibákkal találkozik a **Szállítók V2** – **msdyn\_vendors** leképezés során, ha az entitások rendelkeznek meglévő rekordokkal amelyek értékeket tartalmaznak a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="9a230-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the entities have existing records where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="9a230-137">Ezek a hibák azért fordulnak elő, mert az **InvoiceVendorAccountNumber** egy saját magára hivatkozó mező, és a **PrimaryContactPersonId** egy körkörös hivatkozás a szállítói hozzárendelésben.</span><span class="sxs-lookup"><span data-stu-id="9a230-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="9a230-138">A kapott hibaüzenetek a következő formátumban jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="9a230-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="9a230-139">*Nem sikerült a mező GUID-értékét feloldani: \<field\>. A keresés nem található: \<value\>. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="9a230-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="9a230-140">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="9a230-140">Here are some examples:</span></span>

- <span data-ttu-id="9a230-141">*Nem sikerült a mező GUID-értékét feloldani: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="9a230-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="9a230-142">*Nem sikerült a mező GUID-értékét feloldani: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. A keresés nem található: V24-1. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="9a230-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="9a230-143">Ha a szállítói entitásnak a **PrimaryContactPersonId** és az **InvoiceVendorAccountNumber** mezőben értékei vannak, akkor a kezdeti szinkronizálás befejezéséhez kövesse az alábbi szakasz lépéseit.</span><span class="sxs-lookup"><span data-stu-id="9a230-143">If any records in the vendor entity have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="9a230-144">A Finance and Operations alkalmazásban törölje a **PrimaryContactPersonId** és az **InvoiceVendorAccountNumber** mezőket a leképezésből, és mentse a leképezést.</span><span class="sxs-lookup"><span data-stu-id="9a230-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="9a230-145">Nyissa meg a **Vendors V2 (msdyn\_vendors)** kettős írás leképezési lapját , és válassza ki az **Entitás-leképezések** fület: A bal oldali szűrőben válassza a **Finance and Operations apps.Vendors V2** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a230-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="9a230-146">A jobb oldali szűrőben válassz a **Sales.Vendor** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a230-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="9a230-147">Keressen rá a **primarycontactperson** elemre a **PrimaryContactPersonId** forrásmező megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="9a230-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source field.</span></span>
    3. <span data-ttu-id="9a230-148">Válassza a **Műveletek** , majd a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a230-148">Select **Actions** , and then select **Delete**.</span></span>

        ![A PrimaryContactPersonId mező törlése](media/vend_selfref3.png)

    4. <span data-ttu-id="9a230-150">Az **InvoiceVendorAccountNumber** mező törléséhez ismételje meg ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9a230-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** field.</span></span>

        ![Az InvoiceVendorAccountNumber mező törlése](media/vend-selfref4.png)

    5. <span data-ttu-id="9a230-152">Mentse a leképezésen végrehajtott módosításokat.</span><span class="sxs-lookup"><span data-stu-id="9a230-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="9a230-153">Kapcsolja ki a **Szállító V2** entitás módosításainak nyomon követését.</span><span class="sxs-lookup"><span data-stu-id="9a230-153">Turn off change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="9a230-154">Az **Adatkezelés** munkaterületen válassza az **Adatentitások** csempét.</span><span class="sxs-lookup"><span data-stu-id="9a230-154">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="9a230-155">Válassza ki a **Szállítók V2** entitást.</span><span class="sxs-lookup"><span data-stu-id="9a230-155">Select the **Vendors V2** entity.</span></span>
    3. <span data-ttu-id="9a230-156">A műveleti ablaktáblán válassza a **Beállítások** , majd a **Változáskövetés** elemet.</span><span class="sxs-lookup"><span data-stu-id="9a230-156">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![A módosítás nyomon követése beállítás kiválasztása](media/selfref_options.png)

    4. <span data-ttu-id="9a230-158">Kattintson a **Változáskövetés tiltása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9a230-158">Select **Disable Change Tracking**.</span></span>

        ![Kattintás a Változáskövetés tiltása lehetőségre](media/selfref_tracking.png)

3. <span data-ttu-id="9a230-160">Futtassa a **Szállítók v2 (msdyn\_vendors)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="9a230-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="9a230-161">A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.</span><span class="sxs-lookup"><span data-stu-id="9a230-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="9a230-162">Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="9a230-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="9a230-163">Akkor kell szinkronizálnia ezt a leképezést, ha szinkronizálni szeretné az elsődleges kapcsolattartó mezőt a szállítók entitásban, mert a kapcsolattartók rekordjainak kezdeti szinkronizálását is el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="9a230-163">You must sync this mapping if you want to sync the primary contact field on the vendors entity, because initial synchronization must also be done for the contact records.</span></span>
5. <span data-ttu-id="9a230-164">Adja hozzá ismét a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** mezőket a **Szállítók v2 (msdyn\_vendors)** leképezéshez, és mentse a leképezést.</span><span class="sxs-lookup"><span data-stu-id="9a230-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="9a230-165">Futtassa ismét a **Szállítók v2 (msdyn\_vendors)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="9a230-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="9a230-166">Minden rekord szinkronizálva lesz, mert a változások követése le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="9a230-166">Because change tracking is turned off, all the records will be synced.</span></span>
7. <span data-ttu-id="9a230-167">Kapcsolja be a **Szállító V2** entitás módosításainak nyomon követését ismét.</span><span class="sxs-lookup"><span data-stu-id="9a230-167">Turn change tracking back on for the **Vendors V2** entity.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="9a230-168">Hibák elhárítása a Vevők v3 – Ügyfelek a entitás-leképezésben</span><span class="sxs-lookup"><span data-stu-id="9a230-168">Resolve errors in the Customers V3–to–Accounts entity mapping</span></span>

<span data-ttu-id="9a230-169">Előfordulhat, hogy kezdeti szinkronizálási hibákkal találkozik a **Szállítók V3** – **Fiókok** leképezés során, ha az entitások rendelkeznek meglévő rekordokkal amelyek értékeket tartalmaznak a **ContactPersonID** és **InvoiceAccount** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="9a230-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the entities have existing records where there are values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="9a230-170">Ezek a hibák azért fordulnak elő, mert az **InvoiceAccount** egy saját magára hivatkozó mező, és a **ContactPersonID** egy körkörös hivatkozás a szállítói hozzárendelésben.</span><span class="sxs-lookup"><span data-stu-id="9a230-170">These errors occur because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="9a230-171">A kapott hibaüzenetek a következő formátumban jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="9a230-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="9a230-172">*Nem sikerült a mező GUID-értékét feloldani: \<field\>. A keresés nem található: \<value\>. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="9a230-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="9a230-173">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="9a230-173">Here are some examples:</span></span>

- <span data-ttu-id="9a230-174">*Nem sikerült a mező GUID-értékét feloldani: primarycontactid.msdyn\_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="9a230-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="9a230-175">*Nem sikerült a mező GUID-értékét feloldani: msdyn\_billingaccount.accountnumber. A keresés nem található: 1206-1. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="9a230-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="9a230-176">Ha az ügyfélentitásnak a **ContactPersonId** és az **InvoiceAccount** mezőben értékei vannak, akkor a kezdeti szinkronizálás befejezéséhez kövesse az alábbi szakasz lépéseit.</span><span class="sxs-lookup"><span data-stu-id="9a230-176">If any records in the customer entity have values in the **ContactPersonID** and **InvoiceAccount** fields, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="9a230-177">Ezt a megközelítést használhatja bármely gyári entitáshoz például a **Partnerek** és **Kapcsolattartók** entitásokhoz.</span><span class="sxs-lookup"><span data-stu-id="9a230-177">You can use this approach for any out-of-box entities, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="9a230-178">A Finance and Operations alkalmazásban törölje a **ContactPersonID** és **InvoiceAccount** mezőket az **Ügyfelek V3 (partnerek)** leképezésből, és mentse a leképezést.</span><span class="sxs-lookup"><span data-stu-id="9a230-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** fields from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="9a230-179">Nyissa meg az **Ügyfelek V3 (partnerek)** kettős írás leképezési lapját , és válassza ki az **Entitás-leképezések** fület: A bel oldali szűrőben válassza a **Finance and Operations app.Customers V3** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a230-179">On the dual-write mapping page for **Customers V3 (accounts)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="9a230-180">A jobb oldali szűrőben válassza a **Common Data Service.Account** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a230-180">In the right filter, select **Common Data Service.Account**.</span></span>
    2. <span data-ttu-id="9a230-181">Keressen rá a **contactperson** elemre a **ContactPersonID** forrásmező megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="9a230-181">Search for **contactperson** to find the **ContactPersonID** source field.</span></span>
    3. <span data-ttu-id="9a230-182">Válassza a **Műveletek** , majd a **Törlés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9a230-182">Select **Actions** , and then select **Delete**.</span></span>

        ![A ContactPersonID mező törlése](media/cust_selfref3.png)

    4. <span data-ttu-id="9a230-184">Az **InvoiceAccount** mező törléséhez ismételje meg ezeket a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9a230-184">Repeat these steps to delete the **InvoiceAccount** field.</span></span>

        ![A InvoiceAccount mező törlése](media/cust_selfref4.png)

    5. <span data-ttu-id="9a230-186">Mentse a leképezésen végrehajtott módosításokat.</span><span class="sxs-lookup"><span data-stu-id="9a230-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="9a230-187">Kapcsolja ki az **Ügyfél V3** entitás módosításainak nyomon követését.</span><span class="sxs-lookup"><span data-stu-id="9a230-187">Turn off change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="9a230-188">Az **Adatkezelés** munkaterületen válassza az **Adatentitások** csempét.</span><span class="sxs-lookup"><span data-stu-id="9a230-188">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="9a230-189">Válassza ki az **Ügyfelek V3** entitást.</span><span class="sxs-lookup"><span data-stu-id="9a230-189">Select the **Customers V3** entity.</span></span>
    3. <span data-ttu-id="9a230-190">A műveleti ablaktáblán válassza a **Beállítások** , majd a **Változáskövetés** elemet.</span><span class="sxs-lookup"><span data-stu-id="9a230-190">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![A módosítás nyomon követése beállítás kiválasztása](media/selfref_options.png)

    4. <span data-ttu-id="9a230-192">Kattintson a **Változáskövetés tiltása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9a230-192">Select **Disable Change Tracking**.</span></span>

        ![Kattintás a Változáskövetés tiltása lehetőségre](media/selfref_tracking.png)

3. <span data-ttu-id="9a230-194">Futtassa le az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="9a230-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="9a230-195">A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.</span><span class="sxs-lookup"><span data-stu-id="9a230-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="9a230-196">Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="9a230-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a230-197">Két olyan megfeleltetés van, amelyeknek ugyanaz a neve.</span><span class="sxs-lookup"><span data-stu-id="9a230-197">There are two maps that have the same name.</span></span> <span data-ttu-id="9a230-198">Válassza ki azt a leképezést, amelynek a következő a leírása a **Részletek** lapon: **Kettős írású sablon a FO.CDS Vendor Contacts V2 – CDS.Contacts szinkronizálásához. Új csomag szükséges \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="9a230-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="9a230-199">Adja hozzá ismét az **InvoiceAccount** és **ContactPersonId** mezőket az **Ügyfelek V3 (partnerek)** leképezéshez, majd mentse a leképezést.</span><span class="sxs-lookup"><span data-stu-id="9a230-199">Add the **InvoiceAccount** and **ContactPersonId** fields back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="9a230-200">Most az **InvoiceAccount** és a **ContactPersonId** mező is újra része az élő szinkronizálási üzemmódnak.</span><span class="sxs-lookup"><span data-stu-id="9a230-200">Both the **InvoiceAccount** field and the **ContactPersonId** field are now part of live synchronization mode again.</span></span> <span data-ttu-id="9a230-201">A következő lépésben végre fogja hajtani ezeknek a mezőknek a kezdeti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="9a230-201">In the next step, you will do the initial synchronization for these fields.</span></span>
6. <span data-ttu-id="9a230-202">Futtassa le az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását ismét.</span><span class="sxs-lookup"><span data-stu-id="9a230-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="9a230-203">Mivel a változások követése ki van kapcsolva, szinkronizálva lesznek az **InvoiceAccount** és a **ContactPersonId** adatai a Finance and Operations alkalmazásból a Common Data Service-szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="9a230-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Common Data Service.</span></span>
7. <span data-ttu-id="9a230-204">Ha szinkronizálni szeretné az **InvoiceAccount** és a **ContactPersonId** adatait a Common Data Service-szolgáltatásból a Finance and Operations alkalmazásba, akkor egy adatintegrációs projektet kell használnia.</span><span class="sxs-lookup"><span data-stu-id="9a230-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="9a230-205">A Power Apps felületén hozzon létre egy adatintegrációs projektet az **Sales.Account** és a **Finance and Operations apps.Customers V3** entitások között.</span><span class="sxs-lookup"><span data-stu-id="9a230-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="9a230-206">Az adatok irányának a következőnek kell lennie: Common Data Service – Finance and Operations alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="9a230-206">The data direction must be from Common Data Service to the Finance and Operations app.</span></span> <span data-ttu-id="9a230-207">Mivel az **InvoiceAccount** egy új attribútum a kettős írás funkcióban, érdemes lehet kihagyni kezdeti szinkronizálást ehhez az attribútumhoz.</span><span class="sxs-lookup"><span data-stu-id="9a230-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="9a230-208">További információkért tekintse át az [Adatok integrálása a Common Data Service-szolgáltatásba](https://docs.microsoft.com/power-platform/admin/data-integrator) című részt.</span><span class="sxs-lookup"><span data-stu-id="9a230-208">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="9a230-209">A következő képen egy olyan projekt látható, amely frissíti a **CustomerAccount** és a **ContactPersonId** entitásokat.</span><span class="sxs-lookup"><span data-stu-id="9a230-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Adatintegrációs projekt a CustomerAccount és a ContactPersonId frissítéséhez](media/cust_selfref6.png)

    2. <span data-ttu-id="9a230-211">Adja meg a vállalat feltételeit a szűrőben a Common Data Service oldalán, hogy csak a szűrőfeltételeknek megfelelő rekordok legyenek frissítve a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9a230-211">Add the company criteria in the filter on the Common Data Service side, so that only records that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="9a230-212">Szűrő hozzáadásához kattintson a szűrő ikonra.</span><span class="sxs-lookup"><span data-stu-id="9a230-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="9a230-213">Ezután a **Lekérdezés szerkesztése** párbeszédpanelen hozzáadhat egy olyan szűrőlekérdezést, mint az **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="9a230-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="9a230-214">[MEGJEGYZÉS] Ha a szűrő gomb nem látszik, akkor hozzon létre egy támogató jegyet, és kérje meg az adatintegrációs csoportot, hogy engedélyezze a szűrő képességét a bérlőjén.</span><span class="sxs-lookup"><span data-stu-id="9a230-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="9a230-215">Ha nem ír be szűrő lekérdezést az **\_msdyn\_company\_value** elemhez, az összes rekord szinkronizálva lesz.</span><span class="sxs-lookup"><span data-stu-id="9a230-215">If you don't enter a filter query for **\_msdyn\_company\_value** , all the records will be synced.</span></span>

        ![Szűrő lekérdezés hozzáadása](media/cust_selfref7.png)

    <span data-ttu-id="9a230-217">A rekordok kezdeti szinkronizálása most befejeződött.</span><span class="sxs-lookup"><span data-stu-id="9a230-217">The initial synchronization of the records is now completed.</span></span>

8. <span data-ttu-id="9a230-218">Engedélyezze újra Finance and Operations alkalmazásban az **Ügyfelek V3** entitás változáskövetését.</span><span class="sxs-lookup"><span data-stu-id="9a230-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** entity.</span></span>
