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
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Problémák elhárítása a kezdeti szinkronizációkor

[!include [banner](../../includes/banner.md)]



Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák. 

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>A kezdeti szinkronizálási hibák keresése egy Finance and Operations-alkalmazásban

Miután engedélyezte a leképezési sablonokat, a leképezések állapotának **Fut** állapotnak kell lennie. Ha az állapot **Nem fut**, akkor hiba történt a kezdeti szinkronizálás során. A hibák megtekintéséhez válassza a **Kettős írás** oldal **Kezdeti szinkronizálás adatai** lapját.

![Kezdeti szinkronizálás adatai lapja](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>A kezdeti szinkronizálás nem hajtható végre: 400 hibás kérelem

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A következő hibaüzenetek jelenhetnek meg a leképezlés és a kezdeti szinkronizálás futtatása során:

*A távoli kiszolgáló hibát adott vissza: (400) hibás kérelem.), AX exportálás hibát észlelt*

Íme, egy példa a teljes hibaüzenetre.

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

Ha ez a hiba folyamatosan történik, és a kezdeti szinkronizálás nem hajtható végre, hajtsa végre az alábbi lépéseket a probléma megoldásához.

1. Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre (VM).
2. Nyissa meg a Microsoft Management Console programot. 
3. Győződjön meg arról, hogy a **Szolgáltatások** panelen fut a Microsoft Dynamics 365 adatimportálási és -exportálási keretrendszer szolgáltatása. Indítsa újra, ha leállították, mert erre szükség van a kezdeti szinkronizáláshoz.

## <a name="initial-synchronization-error-403-forbidden"></a>Kezdeti szinkronizálási hiba: 403 Tiltott

A következő hibaüzenetek jelenhetnek meg a kezdeti szinkronizálás során:

*(\[Tiltott\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.), AX exportálás hibát észlelt*

Egy hiba javításához kövesse az alábbi lépéseket.

1. Bejelentkezés a Finance and Operations alkalmazásba.
2. Az **Azure Active Directory-alkalmazások** oldalon törölje a **DtAppID** klienst, majd adja hozzá újra.

![Azure AD alkalmazások listájának megnyitása](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a>Önmagára mutató hivatkozással kapcsolatos hibák a kezdeti szinkronizálás során

Hibaüzenet jelenhet meg, ami a következő példára hasonlít, ha bármely leképezésben önmagára mutató hivatkozás szerepel:

*A Szállítók V2 elemen a következő hiba: Rekordazonosító: új rekord, ErrorMessage: Nem sikerült a mező GUID-értékét feloldani: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. A keresési érték nem tlaálható: CN-001. PRóbálja ki ezt az URL-címet annak ellenőrzésére, higy a hivatkozási adat létezik-e: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*

Ez a hibatípus olyan leképezések kezdeti szinkronizálásakor fordul elő, amelyek önmagukra hivatkoznak. Az előző példában a mező számlázási fiókja a szállító entitásra hivatkozik.

A hiba elhárításához a kezdeti szinkronizálás sikeres elvégzése előtt a leképezést két alkalommal kell futtatnia.

