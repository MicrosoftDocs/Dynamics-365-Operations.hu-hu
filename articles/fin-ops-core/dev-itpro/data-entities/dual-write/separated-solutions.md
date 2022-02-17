---
title: Elkülönített, kétírásos alkalmazáshangosítási csomag
description: A Dual-write Application Orchestration csomag már nem egyetlen csomag, hanem kisebb csomagokra lett szétválasztva. Ez a témakör bemutatja az egyes csomagokban található megoldásokat és leképezéseket, valamint a többi csomagtól való függőségét.
author: RamaKrishnamoorthy
ms.date: 11/29/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: e2f870368dc662032a3e7ca7ddca902feb23a713
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063262"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Elkülönített, kétírásos alkalmazáshangosítási csomag

[!include [banner](../../includes/banner.md)]



Korábban a Dual-write Application Orchestration csomag egyetlen csomag volt, amely a következő megoldásokat tartalmazta:

- Dynamics 365 Notes
- Dynamics 365 Finance és Operations Common Anchor
- Dynamics 365 Finance és Műveletek Dual Write Entity Maps
- Dynamics 365 Asset Management alkalmazás
- Dynamics 365 Asset Management
- HCM Közös
- Dynamics 365 Supply Chain Extended
- Dynamics 365 Finance Extended
- Dynamics 365 Finance és Operations Common
- Dynamics 365 Company
- Valuta árfolyamok
- Field Service Common

Mivel egyetlen csomagról volt szó, ez a csomag "mindent vagy semmit" helyzetet teremtett az ügyfelek számára. A Microsoft azonban most kisebb csomagokra bontotta. Ezért az ügyfél csak az általa igényelt megoldásokhoz választhatja ki a csomagokat. Például, ha Ön egy Microsoft Dynamics 365 Supply Chain Management ügyfél, és nincs szükség integrációra Dynamics 365 Human Resources, jegyzetek és eszközkezelés, kizárhatja ezeket a megoldásokat a telepített megoldások közül. Mivel az alapul szolgáló megoldásnevek, a kiadók és a térképváltozatok változatlanok maradnak, ez a változás nem töretlen. A meglévő telepítéseket frissíteni kell.

![Külön csomag.](media/separated-package-1.png)

Ez a témakör bemutatja az egyes csomagokban található megoldásokat és leképezéseket, valamint a többi csomagtól való függőségét.

## <a name="dual-write-application-core"></a>Kettős írású alkalmazásmag

A Dual-write Application Core csomag lehetővé teszi a felhasználók számára a kettős írási mód telepítését és konfigurálását az ügyfelek bevonása nélkül. A következő öt megoldást tartalmazza.

| Egyedi név                           | Megjelenítendő név                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 Company                       |
| Dynamics365FinanceAndOperationsCommon | Dynamics 365 Finance és Operations Common |
| CurrencyExchangeRates                 | Valuta árfolyamok                    |
| msdyn_DualWriteAppCoreMaps            | Kettős írásmódú alkalmazások alapvető entitástérképei   |
| msdyn_DualWriteAppCoreAnchor          | Kettős írású alkalmazások mag horgony        |

A következő térképek érhetők el ebben a csomagban.

| Finance and Operations alkalmazások     | Customer Engagement alkalmazások                    |
|---------------------------------|---------------------------------------------|
| Üzemi egység                  | msdyn_internalorganizations                 |
| Szervezeti hierarchia          | msdyn_internalorganizationhierarchies       |
| Jogi személyek                  | msdyn_internalorganizations                 |
| Jogi személyek                  | cdm_companies                               |
| Szervezeti hierarchiához kapcsolódó célok | msdyn_internalorganizationhierarchypurposes |
| Az árfolyam pénznempárja     | msdyn_currencyexchangeratepairs             |
| Névutótagok                    | msdyn_nameaffixes                           |
| Árfolyamtípus              | msdyn_exchangeratetypes                     |
| CDS-árfolyamok              | msdyn_currencyexchangerates                 |
| Szervezeti hierarchia típusa     | msdyn_internalorganizationhierarchytypes    |
| Pénznemek                      | transactioncurrencies                       |
| Vegyes valóság útmutatók entitás     | msmrw_guides                                |

**Függőségi információk**

A Dual-write Application Core csomag nem függ más csomagoktól.

## <a name="dual-write-human-resources"></a>Kettős írásmódú emberi erőforrások

A Dual-write Human Resources csomag tartalmazza azokat a megoldásokat és térképeket, amelyek az emberi erőforrások adatainak szinkronizálásához szükségesek. A következő három megoldást tartalmazza.

| Egyedi név                | Megjelenítendő név                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | HCM Közös                               |
| msdyn_Dynamics365HCMMaps   | Dynamics 365 Human Resources entitástérképek |
| msdyn_Dynamics365HCMAchor | Dynamics 365 Human Resources horgony      |

A következő térképek érhetők el ebben a csomagban.

| Finance and Operations alkalmazások | Customer Engagement alkalmazások         |
|-----------------------------|----------------------------------|
| Etnikumok              | cdm_ethnicorigins                |
| Kompenzáció - beosztás funkciója   | cdm_jobfunctions                 |
| Pozíciók V2                | cdm_jobpositions                 |
| Beosztások                        | cdm_jobs                         |
| Kompenzáció - beosztás típusa       | cdm_jobtypes                     |
| Nyelvkódok              | cdm_languages                    |
| Beosztás típusa               | cdm_positiontypes                |
| Beosztáshoz rendelt dolgozók | cdm_positionworkerassignmentmaps |
| Veteránállapot              | cdm_veteranstatus              |
| Dolgozó                      | cdm_workers                      |
| Foglalkoztatás vállalkozásonként      | cdm_employments                  |

**Függőségi információk**

A kettős írásmódú emberi erőforrás csomag a Dual-write Application Core csomagtól függ. Ezért a Dual-write Application Core csomagot a Dual-write Human Resources csomag telepítése előtt telepítenie kell.

## <a name="dual-write-supply-chain"></a>Kettős írású ellátási lánc

A Dual-Write Supply Chain csomag tartalmazza azokat a megoldásokat és térképeket, amelyek a Supply Chain Management adatok szinkronizálásához szükségesek. A következő három megoldást tartalmazza.

| Egyedi név                                | Megjelenítendő név                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain Extended                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Dynamics 365 Supply Chain Management kiterjesztett entitástérképek |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Dynamics 365 Supply Chain Management kiterjesztett horgony      |

A következő térképek érhetők el ebben a csomagban.

| Finance and Operations alkalmazások                 | Customer Engagement alkalmazások                      |
|---------------------------------------------|-----------------------------------------------|
| Egységek                                       | uoms                                          |
| CDS értékesítésirendelés-fejlécek                     | salesorders                                   |
| CDS értékesítési rendelés sorai                       | salesorderdetails                             |
| CDS értékesítésiajánlat-fejléc                  | ajánlatok                                        |
| CDS értékesítési ajánlat sorai                   | quotedetails                                  |
| Kiadott CDS-egyedi termékek              | termék                                      |
| Raktári zónák                             | msdyn_warehousezones                          |
| Raktár zónacsoportjai                       | msdyn_warehousezonegroups                     |
| Raktári munkasorok                        | msdyn_warehouseworklines                      |
| Raktári munkafejlécek                      | msdyn_warehouseworkheaders                    |
| Raktárak                                  | msdyn_warehouses                              |
| Raktárfolyosó                             | msdyn_warehouseaisles                         |
| Egységek átváltása                            | msdyn_unitofmeasureconversions                |
| Szállítási feltételek                           | msdyn_termsofdeliveries                       |
| Szállítási módok                           | msdyn_shipvias                                |
| Alaptermékstílusok                       | msdyn_sharedproductstyles                     |
| Értékesítésiszámla-sorok V2                      | invoicedetails                                |
| Értékesítésiszámla-fejlécek V2                    | számlák                                      |
| Alaptermékméretek                        | msdyn_sharedproductsizes                      |
| Kiadott termékek V2                        | msdyn_sharedproductdetails                    |
| Alaptermék-konfigurációk               | msdyn_sharedproductconfigurations             |
| Alaptermékszínek                       | msdyn_sharedproductcolors                     |
| Értékesítési rendelés eredetkódjai                    | msdyn_salesorderorigins                       |
| Termékbevételezések fejléce                      | msdyn_purchaseorderreceipts                   |
| Termékbevételezési sor                        | msdyn_purchaseorderreceiptproducts            |
| Beszerzési rendelési fejlécek V2                   | msdyn_purchaseorders                          |
| CDS beszerzési rendelési sora – puhán törölt entitás | msdyn_purchaseorderproducts                   |
| CDS beszerzésirendelés-sor entitás              | msdyn_purchaseorderproducts                   |
| Nyomonkövetésidimenzió-csoportok                   | msdyn_producttrackingdimensiongroups          |
| Stílusok                                      | msdyn_productstyles                           |
| Tárolásidimenzió-csoportok                    | msdyn_productstoragedimensiongroups           |
| Termékspecifikus egységátváltások           | msdyn_productspecificunitofmeasureconversions |
| Termék alapértelmezett rendelésbeállításai V2           | msdyn_productspecificdefaultordersettings     |
| Méretek                                       | msdyn_productsizes                            |
| Termékdimenzió-csoportok                    | msdyn_productdimensiongroups                  |
| Alapértelmezett rendelésbeállítások                      | msdyn_productdefaultordersettings             |
| Konfigurációk                              | msdyn_productconfigurations                   |
| Minden termék                                | msdyn_globalproducts                          |
| Színek                                      | msdyn_productcolors                           |
| Termékkategória-hierarchiához tartozó szerepkörök            | msdyn_productcategoryhierarchyroles           |
| Termékkategóriák hierarchiái                | msdyn_productcategoryhierarchies              |
| Termékkategóriák hozzárendelései                | msdyn_productcategoryassignments              |
| Termékkategóriák                          | msdyn_productcategories                       |
| Raktárhelyek                         | msdyn_inventorylocations                      |
| CDS-leltár bekapcsolva                            | msdyn_inventoryonhandentries                  |
| Termékkategóriák                          | msdyn_productcategories                       |
| CDS-leltár bekapcsolva                            | msdyn_inventoryonhandrequests                 |
| Termékszám alapján azonosított vonalkód           | msdyn_productbarcodes                         |
| Hűségkártya                                | msdyn_loyaltycards                            |
| Hűségpontok                       | msdyn_loyaltyrewardpoints                     |
| Ár vevőcsoportjai                       | msdyn_pricecustomergroups                     |
| Helyek                                       | msdyn_operationalsites                        |
| CDS értékesítési ajánlat sorai                   | quotedetails                                  |
| CDS értékesítési rendelés sorai                       | salesorderdetails                             |

**Függőségi információk**

A Dual-Write Supply Chain csomag a következő három csomagtól függ. Ezért ezeket a csomagokat a Dual-write Supply Chain csomag telepítése előtt telepítenie kell.

- Dual Write Application Core csomag
- Kettős írásos pénzügyi csomag
- Kétszeres emberi erőforrás csomag

## <a name="dual-write-finance"></a>Kettős írásmódú pénzügyek

A Dual-write Finance csomag tartalmazza a szinkronizáláshoz szükséges megoldásokat és térképeket Dynamics 365 Finance adat. A következő négy megoldást tartalmazza.

| Egyedi név                            | Megjelenítendő név                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Dynamics 365 Finance kiterjesztett entitástérképek |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Dynamics 365 Finance kiterjesztett horgony      |

A következő térképek érhetők el ebben a csomagban.

| Finance and Operations alkalmazások             | Customer Engagement alkalmazások        |
|-----------------------------------------|---------------------------------|
| Adóelőleg-csoportok                  | msdyn_withholdingtaxgroups      |
| CDS Contacts V2 (ügyfél)              | kapcsolattartók                        |
| CDS Contacts V2 (szállító)                | kapcsolattartók                        |
| Vevők V3                            | kapcsolattartók                        |
| Adóelőlegkódok                   | msdyn_withholdingtaxcodes       |
| Szállítók V2                              | msdyn_vendors                   |
| Szállítói fizetési mód                   | msdyn_vendorpaymentmethods      |
| Szállítói csoportok                           | msdyn_vendorgroups              |
| Számlatükör                       | msdyn_chartofaccountses         |
| Áfás főkönyvi feladási csoportok V2      | msdyn_taxpostinggroups          |
| Cikkáfacsoport                    | msdyn_taxitemgroups             |
| Áfacsoportok                        | msdyn_taxgroups                 |
| Áfamentességi kódentitáshoz tartozó CDS        | msdyn_taxexemptcodes            |
| Vevőcsoportok                         | msdyn_customergroups            |
| Vevő fizetési módszere                 | msdyn_customerpaymentmethods    |
| Pénzügyi dimenziók                    | msdyn_dimensionattributes       |
| Adóhatóságok                   | msdyn_taxauthorities            |
| Pénzügyi dimenzió formátuma              | msdyn_financialdimensionformats |
| Pénzügyi naptári időszak                  | msdyn_fiscalcalendarperiods     |
| Pénzügyi naptár integrációs entitása      | msdyn_fiscalcalendars           |
| Pénzügyi naptári év integrációs entitása | msdyn_fiscalcalendaryears       |
| Fizetési feltételek                        | msdyn_paymentterms              |
| Kifizetés ütemezése                        | msdyn_paymentschedules          |
| Kifizetési lista sorai                  | msdyn_paymentschedulelines      |
| Fizetési napok, CDS                        | msdyn_paymentdays               |
| Fizetési nap sorai, CDS V2                | msdyn_paymentdaylines           |
| Fő számla                            | msdyn_mainaccounts              |
| Főszámla-kategóriák                 | msdyn_mainaccountcategories     |
| Ledger                                  | msdyn_ledgers                   |
| Vevők V3                            | számlák                        |

**Függőségi információk**

A Dual-write Finance csomag a Dual-write Application Core csomagtól függ. Ezért telepítenie kell a Dual-write Application Core csomagot a Dual-write Finance csomag telepítése előtt.

## <a name="dual-write-notes"></a>Kettős írásjegyek

A Dual-write Notes csomag tartalmazza azokat a megoldásokat és leképezéseket, amelyek a jegyzet- vagy annotációs adatok szinkronizálásához szükségesek. A következő négy megoldást tartalmazza.

| Egyedi név                  | Megjelenítendő név                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Dynamics 365 Notes             |
| Dynamics365NotesExtended     | Dynamics 365 jegyzetek kiterjesztve    |
| msdyn_Dynamics365NotesMaps   | A Dynamics 365 jegyzetek entitásleképezéseket |
| msdyn_Dynamics365NotesAnchor | Dynamics 365 jegyzethorgony      |

A következő térképek érhetők el ebben a csomagban.

| Finance and Operations                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Értékesítési rendelési fejléc bizonylatmellékletei    | megjegyzések         |
| Vevői mellékletek                       | megjegyzések         |
| Szállítóidokumentum-mellékletek                | megjegyzések         |
| Beszerzési rendelési fejléc bizonylatmellékletei | megjegyzések         |

**Függőségi információk**

A Dual-write Notes csomag a következő két csomagtól függ. Ezért ezeket a csomagokat a Dual-write Notes csomag telepítése előtt telepítenie kell.

- Dual Write Application Core csomag
- Kettős írásos pénzügyi csomag

## <a name="dual-write-asset-management"></a>Kettős írásmódú eszközkezelés

A Dual-write Asset Management csomag tartalmazza azokat a megoldásokat és térképeket, amelyek szükségesek az eszközadatok szinkronizálásához a Supply Chain Management ill.Dynamics 365 Field Service. A következő négy megoldást tartalmazza.

| Egyedi név                          | Megjelenítendő név                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Dynamics 365 Asset Management             |
| Dynamics365AssetManagementApp        | Dynamics365 Asset Management alkalmazás          |
| msdyn_DualWriteAssetManagementMaps   | Dynamics 365 Asset Management entitástérképek |
| msdyn_DualWriteAssetManagementAnchor | Dynamics 365 Asset Management horgony      |

A következő térképek érhetők el ebben a csomagban.

| Finance and Operations alkalmazások                           | Customer Engagement alkalmazások                |
|-------------------------------------------------------|-----------------------------------------|
| Tárgyeszköz-kezelés garancia                             | msdyn_warranties                        |
| Tárgyieszköz-kezelési modellek                               | msdyn_models                            |
| Tárgyieszközök gyártói                        | msdyn_manufacturers                     |
| Tárgyieszköz-kezelés munkavégzési helyszíntípusok            | msdyn_functionallocationtypes           |
| Tárgyieszköz-kezelés munkavégzési helyszínek                 | msdyn_functionallocations               |
| Eszközkezelés munkavégési helyszín életciklusállapotok | msdyn_functionallocationlifecyclestates |
| Eszközkezelés munkavégési helyszín életciklusmodellek | msdyn_functionallocationlifecyclemodels |
| Tárgyieszköz-kezelő eszközök                               | msdyn_customerassets                    |
| Tárgyieszköz-kezelő eszköztípusok                          | msdyn_customerassetcategories           |
| Tárgyieszközkezelés eszközéletciklus állapotai               | msdyn_assetlifecyclestates              |
| Tárgyieszközkezelés eszközéletciklus modelljei               | msdyn_assetlifecyclemodels              |

**Függőségi információk**

A kettős írásmódú eszközkezelési csomag a kettős írásmódú alkalmazásmag-csomagtól függ. Ezért telepítenie kell a Dual-write Application Core csomagot a Dual-write Asset Management csomag telepítése előtt.

## <a name="packages-required-for-project-operations"></a>Projektműveletekhez szükséges csomagok
A projektműveletek a következő csomagoktól függenek. Ezért ezeket a csomagokat a Project Operations telepítése előtt telepítenie kell.

- Dual Write Application Core csomag
- Kettős írásos pénzügyi csomag
- Kettős írású Supply Chain csomag
- Kettős írásmódú Asset Management csomag
- Kétszeres emberi erőforrás csomag
