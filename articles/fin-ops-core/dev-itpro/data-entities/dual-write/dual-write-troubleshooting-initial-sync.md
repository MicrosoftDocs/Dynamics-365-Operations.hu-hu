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
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172714"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="01620-103">Problémák elhárítása a kezdeti szinkronizációkor</span><span class="sxs-lookup"><span data-stu-id="01620-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="01620-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="01620-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="01620-105">Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák.</span><span class="sxs-lookup"><span data-stu-id="01620-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="01620-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="01620-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="01620-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="01620-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="01620-108">A kezdeti szinkronizálási hibák keresése egy Finance and Operations-alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="01620-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="01620-109">Miután engedélyezte a leképezési sablonokat, a leképezések állapotának **Fut** állapotnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="01620-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="01620-110">Ha az állapot **Nem fut**, akkor hiba történt a kezdeti szinkronizálás során.</span><span class="sxs-lookup"><span data-stu-id="01620-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="01620-111">A hibák megtekintéséhez válassza a **Kettős írás** oldal **Kezdeti szinkronizálás adatai** lapját.</span><span class="sxs-lookup"><span data-stu-id="01620-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Kezdeti szinkronizálás adatai lapja](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="01620-113">A kezdeti szinkronizálás nem hajtható végre: 400 hibás kérelem</span><span class="sxs-lookup"><span data-stu-id="01620-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="01620-114">**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="01620-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="01620-115">A következő hibaüzenetek jelenhetnek meg a leképezlés és a kezdeti szinkronizálás futtatása során:</span><span class="sxs-lookup"><span data-stu-id="01620-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="01620-116">*A távoli kiszolgáló hibát adott vissza: (400) hibás kérelem.), AX exportálás hibát észlelt*</span><span class="sxs-lookup"><span data-stu-id="01620-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="01620-117">Íme, egy példa a teljes hibaüzenetre.</span><span class="sxs-lookup"><span data-stu-id="01620-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="01620-118">Ha ez a hiba folyamatosan történik, és a kezdeti szinkronizálás nem hajtható végre, hajtsa végre az alábbi lépéseket a probléma megoldásához.</span><span class="sxs-lookup"><span data-stu-id="01620-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="01620-119">Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre (VM).</span><span class="sxs-lookup"><span data-stu-id="01620-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="01620-120">Nyissa meg a Microsoft Management Console programot.</span><span class="sxs-lookup"><span data-stu-id="01620-120">Open Microsoft Management Console.</span></span> 
3. <span data-ttu-id="01620-121">Győződjön meg arról, hogy a **Szolgáltatások** panelen fut a Microsoft Dynamics 365 adatimportálási és -exportálási keretrendszer szolgáltatása.</span><span class="sxs-lookup"><span data-stu-id="01620-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="01620-122">Indítsa újra, ha leállították, mert erre szükség van a kezdeti szinkronizáláshoz.</span><span class="sxs-lookup"><span data-stu-id="01620-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="01620-123">Kezdeti szinkronizálási hiba: 403 Tiltott</span><span class="sxs-lookup"><span data-stu-id="01620-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="01620-124">A következő hibaüzenetek jelenhetnek meg a kezdeti szinkronizálás során:</span><span class="sxs-lookup"><span data-stu-id="01620-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="01620-125">*(\[Tiltott\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.), AX exportálás hibát észlelt*</span><span class="sxs-lookup"><span data-stu-id="01620-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="01620-126">Egy hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="01620-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="01620-127">Bejelentkezés a Finance and Operations alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="01620-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="01620-128">Az **Azure Active Directory-alkalmazások** oldalon törölje a **DtAppID** klienst, majd adja hozzá újra.</span><span class="sxs-lookup"><span data-stu-id="01620-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Azure AD alkalmazások listájának megnyitása](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a><span data-ttu-id="01620-130">Önmagára mutató hivatkozással kapcsolatos hibák a kezdeti szinkronizálás során</span><span class="sxs-lookup"><span data-stu-id="01620-130">Self-reference failures during initial synchronization</span></span>

<span data-ttu-id="01620-131">Hibaüzenet jelenhet meg, ami a következő példára hasonlít, ha bármely leképezésben önmagára mutató hivatkozás szerepel:</span><span class="sxs-lookup"><span data-stu-id="01620-131">You might receive an error message that resembles the following example if any of your mappings have self-references:</span></span>

<span data-ttu-id="01620-132">*A Szállítók V2 elemen a következő hiba: Rekordazonosító: új rekord, ErrorMessage: Nem sikerült a mező GUID-értékét feloldani: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. A keresési érték nem tlaálható: CN-001. PRóbálja ki ezt az URL-címet annak ellenőrzésére, higy a hivatkozási adat létezik-e: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span><span class="sxs-lookup"><span data-stu-id="01620-132">*On the Vendors V2, the following error: Record Id: new record, ErrorMessage: Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup value was not found: CN-001. Try this URL(s) to check if the reference data exists: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span></span>

<span data-ttu-id="01620-133">Ez a hibatípus olyan leképezések kezdeti szinkronizálásakor fordul elő, amelyek önmagukra hivatkoznak.</span><span class="sxs-lookup"><span data-stu-id="01620-133">This type of error occurs during initial synchronization of mappings that have self-references.</span></span> <span data-ttu-id="01620-134">Az előző példában a mező számlázási fiókja a szállító entitásra hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="01620-134">In the preceding example, the field invoice account references the vendor entity.</span></span>

<span data-ttu-id="01620-135">A hiba elhárításához a kezdeti szinkronizálás sikeres elvégzése előtt a leképezést két alkalommal kell futtatnia.</span><span class="sxs-lookup"><span data-stu-id="01620-135">To fix the issue, you might have to run the mapping two times before the initial synchronization is successful.</span></span>

