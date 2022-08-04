---
title: Problémák elhárítása a kezdeti szinkronizációkor
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek a kezdeti szinkronizálás során esetleg előforduló problémák kijavításában segítenek.
author: RamaKrishnamoorthy
ms.date: 06/24/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f8fb27a6af2962be31288a3d2260110e5fe6a201
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112082"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Problémák elhárítása a kezdeti szinkronizációkor

[!include [banner](../../includes/banner.md)]



Ez a témakör hibaelhárítási információkat tartalmaz a pénzügyek és a műveletalkalmazások, valamint a Dataverse. Pontosabban, ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a kezdeti szinkronizálás során fellépő problémák.

> [!IMPORTANT]
> Az ebben a témakörben említett problémák egy része a rendszergazdai szerepkörhöz vagy a Microsoft Azure Active Directory (Azure AD) bérlői rendszergazdai hitelesítő adatokhoz lehet szükséges. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Kezdeti szinkronizálási hibák ellenőrzése a pénzügyek és műveletek alkalmazásában

Miután engedélyezte a leképezési sablonokat, a leképezések állapotának **Fut** állapotnak kell lennie. Ha az állapot **Nem fut**, akkor hiba történt a kezdeti szinkronizálás során. A hibák megtekintéséhez válassza a **Kettős írás** oldal **Kezdeti szinkronizálás adatai** lapját.

![Hiba a kezdeti szinkronizálás részletek lapján.](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>A kezdeti szinkronizálás nem hajtható végre: 400 hibás kérelem

**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda

A következő hibaüzenetek jelenhetnek meg a leképezlés és a kezdeti szinkronizálás futtatása során:

*(\[Bad Request\], A távoli szerver hibát küldött vissza: (400) Bad Request.), az AX export hibát észlelt.*

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

1. Jelentkezzen be a Pénzügy és műveletek alkalmazás virtuális gépbe (VM).
2. Nyissa meg a Microsoft Management Console programot.
3. Győződjön meg arról, hogy a **Szolgáltatások** panelen fut a Microsoft Dynamics 365 adatimportálási és -exportálási keretrendszer szolgáltatása. Indítsa újra, ha leállították, mert erre szükség van a kezdeti szinkronizáláshoz.

## <a name="initial-synchronization-error-403-forbidden"></a>Kezdeti szinkronizálási hiba: 403 Tiltott

A következő hibaüzenetek jelenhetnek meg a kezdeti szinkronizálás során:

*(\[Tiltott\], A távoli kiszolgáló hibát adott vissza: (403) Tiltott.), AX exportálás hibát észlelt*

Egy hiba javításához kövesse az alábbi lépéseket.

1. Jelentkezzen be a Pénzügy és műveletek alkalmazásba.
2. Az **Azure Active Directory-alkalmazások** oldalon törölje a **DtAppID** klienst, majd adja hozzá újra.

![DtAppID-ügyfél a Azure AD alkalmazások listáján.](media/aad_applications.png)

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

1. A Pénzügy és műveletek alkalmazásban törölje **a megfeleltetésből az PrimaryContactPersonId** **és a InvoiceVendorAccountNumber** oszlopot, majd mentse a megfeleltetést.

    1. A V2 szállítók **(msdyn\_ szállítók)** **két** írásos hozzárendelési lapján, a Táblaleképezések lapon, **a bal oldali szűrőben válassza ki a Pénzügy és az Üzemeltetés alkalmazásokat. V2. szállító** A jobb oldali szűrőben válassz a **Sales.Vendor** lehetőséget.
    2. Keressen rá a **primarycontactperson** elemre a **PrimaryContactPersonId** forrásoszlop megkereséséhez.
    3. Válassza a **Műveletek**, majd a **Törlés** lehetőséget.

        ![A PrimaryContactPersonId oszlop törlése.](media/vend_selfref3.png)

    4. Az **InvoiceVendorAccountNumber** oszlop törléséhez ismételje meg ezeket a lépéseket.

        ![Az InvoiceVendorAccountNumber oszlop törlése.](media/vend-selfref4.png)

    5. Mentse a leképezésen végrehajtott módosításokat.

2. Kapcsolja ki a **Szállító V2** tábla módosításainak nyomon követését.

    1. Az **Adatkezelés** munkaterületen válassza az **Adattáblák** csempét.
    2. Válassza ki a **Szállítók V2** táblát.
    3. A műveleti ablaktáblán válassza a **Beállítások**, majd a **Változáskövetés** elemet.

        ![A módosítás nyomon követése beállítás kiválasztása.](media/selfref_options.png)

    4. Kattintson a **Változáskövetés tiltása** lehetőségre.

        ![Kattintás a Változáskövetés tiltása lehetőségre.](media/selfref_tracking.png)

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

1. A Pénzügy és műveletek alkalmazásban törölje **a ContactPersonID** **és a InvoiceAccount** **oszlopot a Vevők V3 (számlák)** hozzárendelésből, majd mentse a hozzárendelést.

    1. A V3 vevők (**számlák)** **két** írásos hozzárendelési lapján, a Táblaleképezések lapon a **bal oldali szűrőben válassza ki a Pénzügy és a Műveletek alkalmazást. V3** vevők A jobb oldali szűrőben válassza a **Dataverse.Account** lehetőséget.
    2. Keressen rá a **contactperson** elemre a **ContactPersonID** forrásoszlop megkereséséhez.
    3. Válassza a **Műveletek**, majd a **Törlés** lehetőséget.

        ![A ContactPersonID oszlop törlése.](media/cust_selfref3.png)

    4. Az **InvoiceAccount** oszlop törléséhez ismételje meg ezeket a lépéseket.

        ![A InvoiceAccount oszlop törlése.](media/cust_selfref4.png)

    5. Mentse a leképezésen végrehajtott módosításokat.

2. Kapcsolja ki az **Ügyfél V3** tábla módosításainak nyomon követését.

    1. Az **Adatkezelés** munkaterületen válassza az **Adattáblák** csempét.
    2. Válassza ki az **Ügyfelek V3** táblát.
    3. A műveleti ablaktáblán válassza a **Beállítások**, majd a **Változáskövetés** elemet.

        ![A módosítás nyomon követése beállítás kiválasztása.](media/selfref_options.png)

    4. Kattintson a **Változáskövetés tiltása** lehetőségre.

        ![Kattintás a Változáskövetés tiltása lehetőségre.](media/selfref_tracking.png)

3. Futtassa le az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását. A kezdeti szinkronizálásnak hiba nélkül kell lefutnia.
4. Futtassa a **CDS kapcsolattartók V2 (kapcsolattartók)** hozzárendelésének kezdeti szinkronizálását.

    > [!NOTE]
    > Két olyan megfeleltetés van, amelyeknek ugyanaz a neve. Válassza ki azt a leképezést, amelynek a következő a leírása a **Részletek** lapon: **Kettős írású sablon a FO.CDS Vendor Contacts V2 – CDS.Contacts szinkronizálásához. Új csomag szükséges \[Dynamics365SupplyChainExtended\].**

5. Adja hozzá ismét az **InvoiceAccount** és **ContactPersonId** oszlopot az **Ügyfelek V3 (partnerek)** leképezéshez, majd mentse a leképezést. Most az **InvoiceAccount** és a **ContactPersonId** oszlop is újra része az élő szinkronizálási üzemmódnak. A következő lépésben végre fogja hajtani ezeknek az oszlopoknak a kezdeti szinkronizálását.
6. Futtassa le az **Ügyfelek V3 (Partnerek)** hozzárendelésének kezdeti szinkronizálását ismét. Mivel a változáskövetés ki van kapcsolva, **a Rendszer szinkronizálja a InvoiceAccount** **és a ContactPersonId** adatait a pénzügyi és műveleti alkalmazásból a következőbe Dataverse.
7. Ahhoz, **hogy a InvoiceAccount** **és a ContactPersonId** Dataverse adatait szinkronizálja a Pénzügyi és műveletek alkalmazással, adatintegrációs projektet kell használnia.

    1. Ebben Power Apps a műveletben hozzon létre egy adatintegrációs projektet **a Sales.Account, a** **Pénzügy és a műveletalkalmazások között. Vevők V3 táblái** Az adatiránynak a Pénzügyi és műveletek Dataverse alkalmazásba kell átesnie. Mivel az **InvoiceAccount** egy új attribútum a kettős írás funkcióban, érdemes lehet kihagyni kezdeti szinkronizálást ehhez az attribútumhoz. További információkért tekintse át az [Adatok integrálása a Dataverse-szolgáltatásba](/power-platform/admin/data-integrator) című részt.

        A következő képen egy olyan projekt látható, amely frissíti a **CustomerAccount** és a **ContactPersonId** entitásokat.

        ![Adatintegrációs projekt a CustomerAccount és a ContactPersonId frissítéséhez.](media/cust_selfref6.png)

    2. Adja hozzá a vállalati feltételeket Dataverse az oldal szűrőjéhez, hogy csak a szűrési feltételeknek megfelelő sorokat frissítve legyen a Pénzügy és a Műveletek alkalmazásban. Szűrő hozzáadásához kattintson a szűrő ikonra. Ezután a **Lekérdezés szerkesztése** párbeszédpanelen hozzáadhat egy olyan szűrőlekérdezést, mint az **\_msdyn\_company\_value eq '\<guid\>'**.

        > [MEGJEGYZÉS] Ha a szűrő gomb nem látszik, akkor hozzon létre egy támogató jegyet, és kérje meg az adatintegrációs csoportot, hogy engedélyezze a szűrő képességét a bérlőjén.

        Ha nem ír be szűrő lekérdezést az **\_msdyn\_company\_value** elemhez, az összes sor szinkronizálva lesz.

        ![Szűrő lekérdezés hozzáadása.](media/cust_selfref7.png)

    A sorok kezdeti szinkronizálása most befejeződött.

8. A Pénzügy és műveletek alkalmazásban kapcsolja vissza a változások követését a **Vevők V3 táblánál**.

## <a name="initial-sync-failures-on-maps-with-more-than-10-lookup-fields"></a>Kezdeti szinkronizálási hibák 10-nél több keresési mezőt tartalmazó térképeken

A következő hibaüzenetet kaphatja, amikor megpróbálja futtatni a kezdeti szinkronizálási hibákat az **Ügyfelek V3 - Számlák**, **értékesítési megrendelések** leképezéseken vagy bármely olyan leképezésen, amely több mint 10 keresési mezőt tartalmaz:

*CRMExport: A csomag végrehajtása befejeződött. Hiba Leírás 5 Az adatok lekérdezése a https://xxxxx//datasets/yyyyy/tables/accounts/items?$select=accountnumber, address2_city, address2_country, ... (msdyn_company/cdm_companyid eq 'id')&$orderby=accountnumber asc oldalról sikertelen.*

A lekérdezés keresési korlátozása miatt a kezdeti szinkronizálás sikertelen, ha az entitás-leképezés 10-nél több keresést tartalmaz. További információért lásd: [Kapcsolódó tábla rekordjainak lekérdezéssel történő lekérdezése](/powerapps/developer/common-data-service/webapi/retrieve-related-entities-query).

A probléma megoldásához kövesse az alábbi lépéseket:

1. Az opcionális keresési mezők eltávolítása a kettős írású entitástérképből, hogy a keresések száma 10 vagy kevesebb legyen.
2. Mentse a térképet, és végezze el a kezdeti szinkronizálást.
3. Ha az első lépés kezdeti szinkronizálása sikeres, adja hozzá a többi keresési mezőt, és távolítsa el az első lépésben szinkronizált keresési mezőket. Győződjön meg róla, hogy a keresési mezők száma 10 vagy annál kevesebb. Mentse a térképet, és futtassa a kezdeti szinkronizálást.
4. Ismételje meg ezeket a lépéseket, amíg az összes keresési mezőt szinkronizáljuk.
5. Adja vissza az összes keresési mezőt a térképhez, mentse a térképet, és futtassa a térképet a **kezdeti szinkronizálás kihagyásával**.

Ez a folyamat engedélyezi a térképet az élő szinkronizálási módhoz.

## <a name="known-issue-during-initial-sync-of-party-postal-addresses-and-party-electronic-addresses"></a>Ismert probléma a felek postai címeinek és elektronikus címeinek kezdeti szinkronizálásakor

A következő hibaüzenetet kaphatja, amikor megpróbálja lefuttatni a Fél postai címek és a Fél elektronikus címek kezdeti szinkronizálását:

*A fél száma nem található a Dataverse-en.*

A pénzügyi és műveletalkalmazások DirPartyCDSEntity tartománya szűri a **Személy** **és szervezet típusú feleket**.**·** Ennek eredményeképpen a **CDS felek - msdyn_parties** leképezés kezdeti szinkronizálása nem szinkronizálja a más típusú feleket, beleértve a **Jogi személyt** és a **Működési egységet**. A **CDS Party postai címek (msdyn_partypostaladdresses)** vagy a **Party Contacts V3 (msdyn_partyelectronicaddresses)** kezdeti szinkronizálásakor előfordulhat, hogy a következő hiba jelentkezik.

Egy javításon dolgozunk, hogy a Dataverse pénzügyi és műveletentitások féltípus-tartományát eltávolítsuk, hogy az összes típusú fél szinkronizálható legyen a sikeres szinkronizáláshoz.

## <a name="are-there-any-performance-issues-while-running-initial-sync-for-customers-or-contacts-data"></a>Vannak teljesítményproblémák az ügyfelek vagy a névjegyek adatainak kezdeti szinkronizálása során?

Ha lefuttatta az **Ügyféladatok** kezdeti szinkronizálását, és futnak az **Ügyféltérképek**, majd lefuttatja a **Kapcsolatok** adatainak kezdeti szinkronizálását, teljesítményproblémák léphetnek fel a **LogisticsPostalAddress** és **LogisticsElectronicAddress** táblákba történő beillesztések és frissítések során a **Kapcsolatok** címei esetében. A **CustCustomerV3Entity** és a **VendVendorV2Entity** esetében ugyanazokat a globális postai cím és elektronikus cím táblákat követik, és a kettős írás több lekérdezést próbál létrehozni az adatok másik oldalra történő írásához. Ha már lefuttatta a kezdeti szinkronizálást az **Ügyféladatokhoz**, akkor állítsa le a megfelelő leképezést a **Kapcsolatok** adatainak kezdeti szinkronizálása közben. Ugyanígy járjon el a **Szállító** adatokkal is. Ha a kezdeti szinkronizálás befejeződött, a kezdeti szinkronizálás kihagyásával az összes térképet futtathatja.

## <a name="float-data-type-that-has-a-zero-value-cant-be-synchronized"></a>Nulla értékű lebegőpontos adattípus nem szinkronizálható

A kezdeti szinkronizálás sikertelen lehet az ármezőben nulla értékű rekordoknál, **·** **például** a tranzakció pénznemében a Fix fizetési összeg vagy az Összeg esetében. Ebben az esetben a következő példához hasonló hibaüzenet jelenik meg:

*Hiba történt a bemeneti paraméterek érvényesség-beállításakor: Microsoft.OData.ODataException: A(z) "0000000" szöveg konstans nem alakítható át a várt "Edm" típusra. Tizedesjegy,...*

A probléma az, hogy **az** **Adatkezelési modul Forrás adatformátumai** **alatt található Language területi beállítások értékkel** van probléma. Módosítsa a Nyelv területi beállítások **mezőjének értékét** **, hogy az hu-us** értéket válassza, majd próbálkozzon újra.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

