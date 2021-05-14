---
title: Problémák elhárítása a kezdeti szinkronizációkor
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 709a3c332bb6d086910b257fee9cdec8d2bc81a2
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941055"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Problémák elhárítása a kezdeti szinkronizációkor

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz. Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>A kezdeti szinkronizálási hibák keresése egy Finance and Operations-alkalmazásban

Miután engedélyezte a leképezési sablonokat, a leképezések állapotának **Fut** állapotnak kell lennie. Ha az állapot **Nem fut**, akkor hiba történt a kezdeti szinkronizálás során. A hibák megtekintéséhez válassza a **Kettős írás** oldal **Kezdeti szinkronizálás adatai** lapját.

![Hiba a kezdeti szinkronizálás részletek lapján](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>A kezdeti szinkronizálás nem hajtható végre: 400 hibás kérelem

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A következő hibaüzenetek jelenhetnek meg a leképezlés és a kezdeti szinkronizálás futtatása során:

*(\[Hibás kérelem\], A távoli kiszolgáló hibát adott vissza: (400) hibás kérelem.), AX exportálás hibát észlelt*

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

![DtAppID-ügyfél a Azure AD alkalmazások listáján](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Önmagára mutató hivatkozással vagy körkörös hivatkozással kapcsolatos hibák a kezdeti szinkronizálás során

Hibaüzenet jelenhet meg, ha bármely leképezésben önmagára mutató hivatkozás szerepel: A hibák a következő kategóriákba sorolhatók:

- [Hiba elhárítása a szállítók V2–to–msdyn_vendors táblaleképezésben](#error-vendor-map)
- [Hiba elhárítása a vevők v3 – ügyfelek táblaleképezésben](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>Hibák elhárítása a szállítók V2–to–msdyn_vendors táblaleképezésben

Előfordulhat, hogy kezdeti szinkronizálási hibákkal találkozik a **Szállítók V2** – **msdyn\_vendors** leképezés során, ha az táblák rendelkeznek meglévő sorokkal amelyek értékeket tartalmaznak a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** oszlopokban. Ezek a hibák azért fordulnak elő, mert az **InvoiceVendorAccountNumber** egy saját magára hivatkozó oszlop, és a **PrimaryContactPersonId** egy körkörös hivatkozás a szállítói hozzárendelésben.

A kapott hibaüzenetek a következő formátumban jelennek meg.

*Nem sikerült a mező GUID-értékét feloldani: \<field\>. A keresés nem található: \<value\>. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Íme néhány példa:

- *Nem sikerült a mező GUID-értékét feloldani: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Nem sikerült a mező GUID-értékét feloldani: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. A keresés nem található: V24-1. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Ha a szállítói táblának a **PrimaryContactPersonId** és az **InvoiceVendorAccountNumber** oszlopaiban értékei vannak, akkor a kezdeti szinkronizálás befejezéséhez kövesse az alábbi szakasz lépéseit.

1. A Finance and Operations alkalmazásban törölje a **PrimaryContactPersonId** és az **InvoiceVendorAccountNumber** oszlopokat a leképezésből, és mentse a leképezést.

    1. Nyissa meg a **Vendors V2 (msdyn\_vendors)** kettős írás leképezési lapját , és válassza ki az **Táblaleképezések** fület: A bal oldali szűrőben válassza a **Finance and Operations apps.Vendors V2** lehetőséget. A jobb oldali szűrőben válassz a **Sales.Vendor** lehetőséget.
    2. Keressen rá a **primarycontactperson** elemre a **PrimaryContactPersonId** forrásoszlop megkereséséhez.
    3. Válassza a **Műveletek**, majd a **Törlés** lehetőséget.

        ![A PrimaryContactPersonId oszlop törlése](media/vend_selfref3.png)

    4. Az **InvoiceVendorAccountNumber** oszlop törléséhez ismételje meg ezeket a lépéseket.

        ![Az InvoiceVendorAccountNumber oszlop törlése](media/vend-selfref4.png)

    5. Mentse a leképezésen végrehajtott módosításokat.

2. Kapcsolja ki a **Szállító V2** tábla módosításainak nyomon követését.

    1. Az **Adatkezelés** munkaterületen válassza az **Adattáblák** csempét.
    2. Válassza ki a **Szállítók V2** táblát.
    3. A műveleti ablaktáblán válassza a **Beállítások**, majd a **Változáskövetés** elemet.

        ![A módosítás nyomon követése beállítás kiválasztása](media/selfref_options.png)

    4. Kattintson a **Változáskövetés tiltása** lehetőségre.

        ![Kattintás a Változáskövetés tiltása lehetőségre](media/selfref_tracking.png)

3. Futtassa a **Szállítók v2 (msdyn\_vendors)** hozzárendelésének kezdeti szinkronizálását. A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.
4. Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását. Akkor kell szinkronizálnia ezt a leképezést, ha szinkronizálni szeretné az elsődleges kapcsolattartó oszlopot a szállítók táblában, mert a kapcsolattartók sorainak kezdeti szinkronizálását is el kell végezni.
5. Adja hozzá ismét a **PrimaryContactPersonId** és **InvoiceVendorAccountNumber** oszlopokat a **Szállítók v2 (msdyn\_vendors)** leképezéshez, és mentse a leképezést.
6. Futtassa ismét a **Szállítók v2 (msdyn\_vendors)** hozzárendelésének kezdeti szinkronizálását. Minden sor szinkronizálva lesz, mert a változások követése le van tiltva.
7. Kapcsolja be a **Szállító V2** tábla módosításainak nyomon követését ismét.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Hibák elhárítása a Vevők v3 – Ügyfelek a táblaleképezésben

Előfordulhat, hogy kezdeti szinkronizálási hibákkal találkozik a **Szállítók V3** – **Fiókok** leképezés során, ha az táblák rendelkeznek meglévő sorokkal amelyek értékeket tartalmaznak a **ContactPersonID** és **InvoiceAccount** oszlopokban. Ezek a hibák azért fordulnak elő, mert az **InvoiceAccount** egy saját magára hivatkozó oszlop, és a **ContactPersonID** egy körkörös hivatkozás a szállítói hozzárendelésben.

A kapott hibaüzenetek a következő formátumban jelennek meg.

*Nem sikerült a mező GUID-értékét feloldani: \<field\>. A keresés nem található: \<value\>. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Íme néhány példa:

- *Nem sikerült a mező GUID-értékét feloldani: primarycontactid.msdyn\_contactpersonid. A keresés nem található: 000056. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Nem sikerült a mező GUID-értékét feloldani: msdyn\_billingaccount.accountnumber. A keresés nem található: 1206-1. Próbálja meg ezt az URL-címet, és ellenőrizze, hogy létezik-e a hivatkozási adat: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Ha az ügyféltábla bármelyik sorának a **ContactPersonId** és az **InvoiceAccount** oszlopokban értékei vannak, akkor a kezdeti szinkronizálás befejezéséhez kövesse az alábbi szakasz lépéseit. Ezt a megközelítést használhatja bármely gyári táblákhoz például a **Partnerek** és **Kapcsolattartók** entitásokhoz.

1. A Finance and Operations alkalmazásban törölje a **ContactPersonID** és **InvoiceAccount** oszlopokat az **Ügyfelek V3 (partnerek)** leképezésből, és mentse a leképezést.

    1. Nyissa meg az **Ügyfelek V3 (partnerek)** kettős írás leképezési lapját , és válassza ki az **Táblaleképezések** fület: A bal oldali szűrőben válassza a **Finance and Operations app.Customers V3** lehetőséget. A jobb oldali szűrőben válassza a **Dataverse.Account** lehetőséget.
    2. Keressen rá a **contactperson** elemre a **ContactPersonID** forrásoszlop megkereséséhez.
    3. Válassza a **Műveletek**, majd a **Törlés** lehetőséget.

        ![A ContactPersonID oszlop törlése](media/cust_selfref3.png)

    4. Az **InvoiceAccount** oszlop törléséhez ismételje meg ezeket a lépéseket.

        ![A InvoiceAccount oszlop törlése](media/cust_selfref4.png)

    5. Mentse a leképezésen végrehajtott módosításokat.

2. Kapcsolja ki az **Ügyfél V3** tábla módosításainak nyomon követését.

    1. Az **Adatkezelés** munkaterületen válassza az **Adattáblák** csempét.
    2. Válassza ki az **Ügyfelek V3** táblát.
    3. A műveleti ablaktáblán válassza a **Beállítások**, majd a **Változáskövetés** elemet.

        ![A módosítás nyomon követése beállítás kiválasztása](media/selfref_options.png)

    4. Kattintson a **Változáskövetés tiltása** lehetőségre.

        ![Kattintás a Változáskövetés tiltása lehetőségre](media/selfref_tracking.png)

3. Futtassa le az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását. A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.
4. Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását.

    > [!NOTE]
    > Két olyan megfeleltetés van, amelyeknek ugyanaz a neve. Válassza ki azt a leképezést, amelynek a következő a leírása a **Részletek** lapon: **Kettős írású sablon a FO.CDS Vendor Contacts V2 – CDS.Contacts szinkronizálásához. Új csomag szükséges \[Dynamics365SupplyChainExtended\].**

5. Adja hozzá ismét az **InvoiceAccount** és **ContactPersonId** oszlopot az **Ügyfelek V3 (partnerek)** leképezéshez, majd mentse a leképezést. Most az **InvoiceAccount** és a **ContactPersonId** oszlop is újra része az élő szinkronizálási üzemmódnak. A következő lépésben végre fogja hajtani ezeknek az oszlopoknak a kezdeti szinkronizálását.
6. Futtassa le az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását ismét. Mivel a változások követése ki van kapcsolva, szinkronizálva lesznek az **InvoiceAccount** és a **ContactPersonId** adatai a Finance and Operations alkalmazásból a Dataverse-szolgáltatásba.
7. Ha szinkronizálni szeretné az **InvoiceAccount** és a **ContactPersonId** adatait a Dataverse-szolgáltatásból a Finance and Operations alkalmazásba, akkor egy adatintegrációs projektet kell használnia.

    1. A Power Apps felületén hozzon létre egy adatintegrációs projektet az **Sales.Account** és a **Finance and Operations apps.Customers V3** táblák között. Az adatok irányának a következőnek kell lennie: Dataverse – Finance and Operations alkalmazás. Mivel az **InvoiceAccount** egy új attribútum a kettős írás funkcióban, érdemes lehet kihagyni kezdeti szinkronizálást ehhez az attribútumhoz. További információkért tekintse át az [Adatok integrálása a Dataverse-szolgáltatásba](/power-platform/admin/data-integrator) című részt.

        A következő képen egy olyan projekt látható, amely frissíti a **CustomerAccount** és a **ContactPersonId** entitásokat.

        ![Adatintegrációs projekt a CustomerAccount és a ContactPersonId frissítéséhez](media/cust_selfref6.png)

    2. Adja meg a vállalat feltételeit a szűrőben a Dataverse oldalán, hogy csak a szűrőfeltételeknek megfelelő sorok legyenek frissítve a Finance and Operations alkalmazásban. Szűrő hozzáadásához kattintson a szűrő ikonra. Ezután a **Lekérdezés szerkesztése** párbeszédpanelen hozzáadhat egy olyan szűrőlekérdezést, mint az **\_msdyn\_company\_value eq '\<guid\>'**. 

        > [MEGJEGYZÉS] Ha a szűrő gomb nem látszik, akkor hozzon létre egy támogató jegyet, és kérje meg az adatintegrációs csoportot, hogy engedélyezze a szűrő képességét a bérlőjén.

        Ha nem ír be szűrő lekérdezést az **\_msdyn\_company\_value** elemhez, az összes sor szinkronizálva lesz.

        ![Szűrő lekérdezés hozzáadása](media/cust_selfref7.png)

    A sorok kezdeti szinkronizálása most befejeződött.

8. Engedélyezze újra Finance and Operations alkalmazásban az **Ügyfelek V3** tábla változáskövetését.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]