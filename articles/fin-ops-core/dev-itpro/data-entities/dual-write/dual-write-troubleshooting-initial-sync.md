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

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Önmagára mutató hivatkozással vagy körkörös hivatkozással kapcsolatos hibák a kezdeti szinkronizálás során

Hibaüzenet jelenhet meg, ha bármely leképezésben önmagára mutató hivatkozás szerepel: A hibák a következő kategóriákba sorolhatók:

- [Vendors V2 – msdyn_vendors entitás-hozzárendelés](#error-vendor-map)
- [Customers V3 – Fiókok entitásleképezés](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Hiba elhárítása a Szállítók V2 – msdyn_vendors entitásleképezésben

Előfordulhat, hogy a következő kezdeti szinkronizálási hibákkal találkozik a **Szállítók V2** – **msdyn_vendors** leképezés során, ha az entitások rendelkeznek meglévő rekordokkal amelyek értékeket tartalmaznak a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** mezőkben. Ez azért van így, mert az **InvoiceVendorAccountNumber** egy saját magára hivatkozó mező, és a **PrimaryContactPersonId** egy körkörös hivatkozás a szállítói hozzárendelésben.

*Nem sikerült a mező GUID-értékét feloldani: <field> . A keresés nem található: <value> . Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

Íme néhány példa:

- *Nem sikerült feloldani a GUID-értéket a mezőhöz: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Nem sikerült feloldani a GUID-értéket a mezőhöz: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. A keresés nem található: V24-1. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*

Ha a szállítói entitásnak ezekben a mezőiben értékekkel rendelkező rekordok találhatók akkor a kezdeti szinkronizálás sikeres befejezéséhez kövesse az alábbi szakasz lépéseit.

1. A Finance and Operations alkalmazásban törölje a **PrimaryContactPersonId** és az **InvoiceVendorAccountNumber** mezőket a leképezésből, és mentse a változtatásokat.

    1. Nyissa meg a **Vendors V2 (msdyn_vendors)** kettős írás leképezési lapját , és válassza ki az **Entitás-leképezések** fület: A bel oldali szűrőben válassza a **Finance and Operations apps.Vendors V2** lehetőséget. A jobb oldali szűrőben válassz a **Sales.Vendor** lehetőséget.

    2. Keressen rá a **primarycontactperson** elemre a **PrimaryContactPersonId** forrásmező megkereséséhez.
    
    3. Kattintson a **Műveletek** gombra, majd válassza a **Törlés** elemet.
    
        ![önmagára mutató vagy körkörös hivatkozás 3](media/vend_selfref3.png)
    
    4. Az **InvoiceVendorAccountNumber** mező törléséhez ismételje meg a műveletet.
    
        ![önmagára mutató vagy körkörös hivatkozás 4](media/vend-selfref4.png)
    
    5. Mentse a leképezés módosításait.

2. Tiltsa le a **Szállító V2** entitás módosítási nyomon követését.

    1. Navigáljon az **Adatkezelés \> Adatentitások** részhez.
    
    2. Válassza ki a **Szállítók V2** entitást.
    
    3. Kattintson a menüsor **Beállítások** elemére, majd a **Változáskövetés** elemre.
    
        ![önmagára mutató vagy körkörös hivatkozás 5](media/selfref_options.png)
    
    4. Kattintson a **Változáskövetés tiltása** lehetőségre.
    
        ![önmagára mutató vagy körkörös hivatkozás 6](media/selfref_tracking.png)

3. Futtassa a **Szállítók v2 (msdyn_vendors)** hozzárendelésének kezdeti szinkronizálását. A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.

4. Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását. Akkor kell szinkronizálnia ezt a leképezést, ha szinkronizálni szeretné az elsődleges kapcsolattartó mezőt a szállítók entitásban, mert a kapcsolattartók rekordjainak kezdeti szinkronizálását is el kell végezni.

5. Adja hozzá ismét a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** mezőket a **Szállítók v2 (msdyn_vendors)** leképezéshez, és mentse a leképezést.

6. Futtassa ismét a **Szállítók v2 (msdyn_vendors)** hozzárendelésének kezdeti szinkronizálását. Minden rekord szinkronizálva lesz, mert a változások követése le van tiltva.

7. Engedélyezze a **Szállító V2** entitás módosításainak nyomon követését.

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a>Hiba elhárítása a Vevők v3 – Ügyfelek a entitás-leképezésben

Előfordulhat, hogy a következő kezdeti szinkronizálási hibákkal találkozik az **Ügyfelek V3** – **Partnerek** leképezés során, ha az entitások rendelkeznek meglévő rekordokkal amelyek értékeket tartalmaznak a **ContactPersonID** és **InvoiceAccount** mezőkben. Ez azért van így, mert az **InvoiceAccount** egy saját magára hivatkozó mező, és a **ContactPersonID** egy körkörös hivatkozás a szállítói hozzárendelésben.

*Nem sikerült a mező GUID-értékét feloldani: <field> . A keresés nem található: <value> . Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

- *Nem sikerült feloldani a GUID-értéket a mezőhöz: primarycontactid.msdyn_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Nem sikerült feloldani a GUID-értéket a mezőhöz: msdyn_billingaccount.accountnumber. A keresés nem található: 1206-1. Próbálja meg ezt az URL-címet/-címeket annak ellenőrzéséhez, hogy az adatok léteznek-e: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*

Ha az ügyfél entitásnak ezekben a mezőiben értékekkel rendelkező rekordok találhatók akkor a kezdeti szinkronizálás sikeres befejezéséhez kövesse az alábbi szakasz lépéseit. Ezt a megközelítést használhatja bármely gyári entitáshoz például a Partnerek és Kapcsolattartók entitásokhoz.

1. A Finance and Operations alkalmazásban törölje a **ContactPersonID** és **InvoiceAccount** mezőket az **Ügyfelek V3 (partnerek)** leképezésből, és mentse a leképezést.

    1. Nyissa meg az **Ügyfelek V3 (partnerek)** kettős írás leképezési lapját , és válassza ki az **Entitás-leképezések** fület: A bel oldali szűrőben válassza a **Finance and Operations app.Customers V3** lehetőséget. A jobb oldali szűrőben válassza a **Common Data Service.Account** lehetőséget.

    2. Keressen rá a **contactperson** elemre a **ContactPersonID** forrásmező megkereséséhez.
    
    3. Kattintson a **Műveletek** gombra, majd válassza a **Törlés** elemet.
    
        ![önmagára mutató vagy körkörös hivatkozás 3](media/cust_selfref3.png)
    
    4. Az **InvoiceAccount** mező törléséhez ismételje meg a műveletet.
    
        ![önmagára mutató vagy körkörös hivatkozás](media/cust_selfref4.png)
    
    5. Mentse a leképezés módosításait.

2. Tiltsa le az **Ügyfelek V3** entitás módosítási nyomon követését.

    1. Navigáljon az **Adatkezelés \> Adatentitások** részhez.
    
    2. Válassza ki az **Ügyfelek V3** entitást.
    
    3. Kattintson a menüsor **Beállítások** elemére, majd a **Változáskövetés** elemre.
    
        ![önmagára mutató vagy körkörös hivatkozás 5](media/selfref_options.png)
    
    4. Kattintson a **Változáskövetés tiltása** lehetőségre.
    
        ![önmagára mutató vagy körkörös hivatkozás 6](media/selfref_tracking.png)

3. Futtassa az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását. A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.

4. Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását. 2 azonos nevű leképezés van. Válassza ki azt, amelyiknek a leírása **Kettős írású sablon a FO.CDS Vendor Contacts V2 – CDS.Contacts szinkronizálásához. Új csomag szükséges \[Dynamics365SupplyChainExtended\].** a leképezés **Részletek** lapján.

5. Adja hozzá ismét az **InvoiceAccount** és **ContactPersonId** mezőket az **Ügyfelek V3 (partnerek)** leképezéshez, és mentse a leképezést. Most az **InvoiceAccount** és a **ContactPersonId** mező is újra része az élő szinkronizálási üzemmódnak. A következő lépésben végre kell hajtania ezeknek a mezőknek a kezdeti szinkronizálását.

6. Futtassa ismét az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását. Mivel a változások követése le van tiltva, a szinkronizálás futtatása szinkronizálja az **InvoiceAccount** és a **ContactPersonId** adatait a Finance and Operations alkalmazásból a Common Data Service-szolgáltatásba.

7. Ha szinkronizálni szeretné az **InvoiceAccount** és a **ContactPersonId** adatait a Common Data Service-szolgáltatásból a Finance and Operations alkalmazásba, akkor egy adatintegrációs projektet használ.

    1. A Power Apps felületén hozzon létre egy adatintegrációs projektet az **Sales.Account** és a **Finance and Operations apps.Customers V3** entitások között. Az adatok irányának a következőnek kell lennie: Common Data Service – Finance and Operations alkalmazás.  Mivel az **InvoiceAccount** egy új attribútum a kettős írás funkcióban, érdemes kihagyni kezdeti szinkronizálást ehhez az attribútumhoz. További információkért tekintse át az [Adatok integrálása a Common Data Service-szolgáltatásba](https://docs.microsoft.com/power-platform/admin/data-integrator) című részt.

        A következő képen egy olyan projekt látható, amely frissíti a **CustomerAccount** és a **ContactPersonId** entitásokat.

        ![önmagára mutató vagy körkörös hivatkozás](media/cust_selfref6.png)

    2. Adja meg a vállalat feltételeit a szűrőben a Common Data Service oldalán, mivel csak a szűrőfeltételeknek megfelelő rekordok lesznek frissítve a Finance and Operations alkalmazásban. Szűrő hozzáadásához kattintson a szűrő ikonra. A **Lekérdezés szerkesztése** párbeszédpanelen hozzáadhat egy ilyen szűrőlekérdezést **_msdyn_company_value eq '\<guid\>'**. Ha a szűrő ikon nem látszik, akkor hozzon létre egy támogató jegyet, és kérje meg az adatintegrációs csoportot, hogy engedélyezze a szűrő képességét a bérlőjén. Ha nem ír be szűrő lekérdezést az **_msdyn_company_value** elemhez, akkor az összes rekord szinkronizálva lesz.

        ![önmagára mutató vagy körkörös hivatkozás](media/cust_selfref7.png)

        Ezzel végrehajtja a rekordok kezdeti szinkronizálását.

8. Engedélyezze **Ügyfelek V3 entitás** változáskövetését a Finance and Operations alkalmazásban.

