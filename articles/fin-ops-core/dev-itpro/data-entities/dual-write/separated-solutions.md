---
title: Két írásos alkalmazás- és előírásos csomag elválasztása
description: A kettős írású Application Orchestration csomag már nem egy csomag, hanem kisebb csomagokra lett bontva. Ez a cikk bemutatja az egyes csomagok megoldásait és leképezését, valamint a többi csomagtól való függőségét.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: 504939f1f98c18005c092cabc1d040b420402c93
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874812"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Két írásos alkalmazás- és előírásos csomag elválasztása

[!include [banner](../../includes/banner.md)]



Korábban a Dual-write Application Orchestration csomag egy olyan csomag volt, amely a következő megoldásokat tartalmazza:

- Dynamics 365 Megjegyzések
- Dynamics 365 Pénzügy és Műveletek közös horgonya
- Dynamics 365 Pénzügy és Műveletek – Két írásos entitás leképezés
- Dynamics 365 eszközkezelési alkalmazás
- Dynamics 365 Eszközkezelés
- HCM Közös
- Dynamics 365 Ellátási lánc kiterjesztve
- Dynamics 365 Finance Extended
- Dynamics 365 Pénzügy és Műveletek – Közös
- Dynamics 365 vállalat
- Devizaárfolyamok
- Field Service - általános

Mivel ez egy csomag volt, ez a csomag "minden vagy semmi" helyzetet hozott létre a vevők számára. A Microsoft azonban kisebb csomagokra bontotta. Ebből következően a vevők csak a szükséges megoldáscsomagokat választhatják ki. Ha például Ön Microsoft-ügyfél Dynamics 365 Supply Chain Management, Dynamics 365 Human Resources és nincs szükség a – megjegyzések és eszközkezelés – integrációra, akkor ezeket a megoldásokat ki lehet zárni a telepített megoldásokból. Mivel a mögöttes megoldásnevek, közzétevők és leképezésverziók változatlanok maradnak, ez a módosítás nem törés. A meglévő telepítéseket frissíteni kell.

![Csomag elválasztva.](media/separated-package-1.png)

Ez a cikk bemutatja az egyes csomagok megoldásait és leképezését, valamint a többi csomagtól való függőségét.

## <a name="dual-write-application-core"></a>Két írásos Application Core

A kettős írású Application Core csomag lehetővé teszi a felhasználók számára a kettős írású, ügyfél-kapcsolati alkalmazás nélküli telepítést és konfigurálást. A következő öt megoldást tartalmazza.

| Egyedi név                           | Megjelenítendő név                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 vállalat                       |
| Dynamics365FinanceAndOperationsCommon | Dynamics 365 Pénzügy és Műveletek – Közös |
| CurrencyExchangeRates                 | Devizaárfolyamok                    |
| msdyn_DualWriteAppCoreMaps            | Két írásos alkalmazások alapentitás-leképezések   |
| msdyn_DualWriteAppCoreAnchor          | Két írásos alkalmazások központi horgonya        |

A következő térképeket tartalmazza ez a csomag.

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

**Függőségi információ**

A kettős írású Application Core csomag nem függ más csomagoktól.

## <a name="dual-write-human-resources"></a>Kettős írású emberi erőforrások

A kettős írású Emberi erőforrások csomag tartalmazza az emberi erőforrások adatainak szinkronizálásához szükséges megoldásokat és térképeket. A következő három megoldást tartalmazza.

| Egyedi név                | Megjelenítendő név                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | HCM Közös                               |
| msdyn_Dynamics365HCMMaps   | Dynamics 365 Human Resources entitás-leképezések |
| msdyn_Dynamics365HCMAnchor | Dynamics 365 Human Resources Horgony      |

A következő térképeket tartalmazza ez a csomag.

| Finance and Operations alkalmazások | Customer Engagement alkalmazások         |
|-----------------------------|----------------------------------|
| Etnikumok              | cdm_ethnicorigins                |
| Kompenzáció - beosztás funkciója   | cdm_jobfunctions                 |
| Pozíciók V2                | cdm_jobpositions                 |
| Feladatok                        | cdm_jobs                         |
| Kompenzáció - beosztás típusa       | cdm_jobtypes                     |
| Nyelvkódok              | cdm_languages                    |
| Beosztás típusa               | cdm_positiontypes                |
| Beosztáshoz rendelt dolgozók | cdm_positionworkerassignmentmaps |
| Veteránállapot              | cdm_veteranstatuses              |
| Dolgozó                      | cdm_workers                      |
| Foglalkoztatás vállalkozásonként      | cdm_employments                  |

**Függőségi információ**

A kettős írású Emberi erőforrások csomag a kettős írású Application Core csomagtól függ. Ezért a kettős írású Application Core csomagot még a kétírásos Emberi erőforrások csomag telepítése előtt telepítenie kell.

## <a name="dual-write-supply-chain"></a>Kettős írású ellátási lánc

A kettős írású Ellátásilánc-kezelés csomag tartalmazza az ellátásilánc-kezelés adatainak szinkronizálásához szükséges megoldásokat és térképeket. A következő három megoldást tartalmazza.

| Egyedi név                                | Megjelenítendő név                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Ellátási lánc kiterjesztve                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Dynamics 365 Supply Chain Management kiterjesztett entitás leképezések |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Dynamics 365 Supply Chain Management kiterjesztett horgony      |

A következő térképeket tartalmazza ez a csomag.

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
| CDS-készlet a                            | msdyn_inventoryonhandentries                  |
| Termékkategóriák                          | msdyn_productcategories                       |
| CDS-készlet a                            | msdyn_inventoryonhandrequests                 |
| Termékszám alapján azonosított vonalkód           | msdyn_productbarcodes                         |
| Hűségkártya                                | msdyn_loyaltycards                            |
| Hűségpontok                       | msdyn_loyaltyrewardpoints                     |
| Ár vevőcsoportjai                       | msdyn_pricecustomergroups                     |
| Webhelyek                                       | msdyn_operationalsites                        |
| CDS értékesítési ajánlat sorai                   | quotedetails                                  |
| CDS értékesítési rendelés sorai                       | salesorderdetails                             |

**Függőségi információ**

A kettős írású Ellátásilánc-csomag a következő három csomagtól függ. Ezért ezeket a csomagokat még a két írásos Ellátásilánc-csomag telepítése előtt telepítenie kell.

- Két írásos Application Core csomag
- Két írású pénzügyi csomag
- Két írású emberi erőforrás csomag

## <a name="dual-write-finance"></a>Kettős írású pénzügy

A Dual-write Finance csomag tartalmazza a Dynamics 365 Pénzügyi adatok szinkronizálásához szükséges megoldásokat és térképeket. A következő négy megoldást tartalmazza.

| Egyedi név                            | Megjelenítendő név                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Dynamics 365 Pénzügyi kiterjesztett entitás leképezések |
| FieldServiceCommon                     | Field Service - általános                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Dynamics 365 Pénzügy kiterjesztett horgonya      |

A következő térképeket tartalmazza ez a csomag.

| Finance and Operations alkalmazások             | Customer Engagement alkalmazások        |
|-----------------------------------------|---------------------------------|
| Adóelőleg-csoportok                  | msdyn_withholdingtaxgroups      |
| CDS-kapcsolattartók V2 (vevő)              | kapcsolattartók                        |
| CDS -kapcsolattartók V2 (szállító)                | kapcsolattartók                        |
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
| Főkönyv                                  | msdyn_ledgers                   |
| Vevők V3                            | számlák                        |

**Függőségi információ**

A kettős írású pénzügyi csomag a kettős írású Application Core csomagtól függ. Ezért a Kettős írású Pénzügy csomag telepítése előtt telepítenie kell a Kettős írású Application Core csomagot.

## <a name="dual-write-notes"></a>Kettős írású megjegyzések

A kettős írású Megjegyzések csomag tartalmazza azokat a megoldásokat és térképeket, amelyek szükségesek a megjegyzés- vagy jegyzetadatok szinkronizálásához. A következő négy megoldást tartalmazza.

| Egyedi név                  | Megjelenítendő név                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Dynamics 365 Megjegyzések             |
| Dynamics365NotesExtended     | Dynamics 365 megjegyzések kiterjesztve    |
| msdyn_Dynamics365NotesMaps   | Dynamics 365 megjegyzések entitás-leképezések |
| msdyn_Dynamics365NotesAnchor | Dynamics 365 megjegyzések horgonya      |

A következő térképeket tartalmazza ez a csomag.

| Finance and Operations                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Értékesítési rendelési fejléc bizonylatmellékletei    | Széljegyzetek         |
| Vevői mellékletek                       | Széljegyzetek         |
| Szállítóidokumentum-mellékletek                | Széljegyzetek         |
| Beszerzési rendelési fejléc bizonylatmellékletei | Széljegyzetek         |

**Függőségi információ**

A kettős írású Megjegyzések csomag a következő két csomagtól függ. Ezért ezeket a csomagokat még a két írásos Megjegyzések csomag telepítése előtt telepítenie kell.

- Két írásos Application Core csomag
- Két írású pénzügyi csomag

## <a name="dual-write-asset-management"></a>Kettős írású eszközkezelés

A kettős írású eszközkezelési csomag azokat a megoldásokat és térképeket tartalmazza, amelyek szükségesek az eszközadatoknak az Ellátásilánc-kezelés vagy az Dynamics 365 Field Service. A következő négy megoldást tartalmazza.

| Egyedi név                          | Megjelenítendő név                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Dynamics 365 Eszközkezelés             |
| Dynamics365AssetManagementApp        | Dynamics365 eszközkezelési alkalmazás          |
| msdyn_DualWriteAssetManagementMaps   | Dynamics 365 Eszközkezelési entitás leképezések |
| msdyn_DualWriteAssetManagementAnchor | Dynamics 365 Eszközkezelés – horgony      |

A következő térképeket tartalmazza ez a csomag.

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

**Függőségi információ**

A kettős írású eszközkezelési csomag a kettős írású Application Core csomagtól függ. Ezért a kettős írású Application Core csomagot még a Kétírásos eszközkezelés csomag telepítése előtt telepítenie kell.

## <a name="packages-required-for-project-operations"></a>Projektművelethez szükséges csomagok
A projektműveletek a következő csomagoktól függnek. Ezért ezeket a csomagokat a Projektműveletek telepítése előtt telepítenie kell.

- Két írásos Application Core csomag
- Két írású pénzügyi csomag
- Két írású ellátásilánc-csomag
- Két írású eszközkezelési csomag
- Két írású emberi erőforrás csomag

## <a name="dual-write-party-and-global-address-book-solutions"></a>Kettős írású fél és globális címjegyzék megoldásai

A kettős írású fél és globális címjegyzék csomag a következő megoldásokat és térképeket tartalmazza, amelyek szükségesek a felek és a globális címjegyzék adatainak szinkronizálásához. 

| Egyedi név                       | Megjelenítendő név                            |
|-----------------------------------|-----------------------------------------|
| Fél                             | Fél                                   |
| Dynamics365GABExtended            | Dynamics 365 GAB kiterjesztve               |
| Dynamics365GABDualWriteEntityMaps | Dynamics 365 GAB két írású entitás leképezések |
| Dynamics365GABParty_Anchor        | Dynamics 365 GAB és fél              |

A következő térképeket tartalmazza ez a csomag.

| Finance and Operations alkalmazások | Customer Engagement alkalmazások | 
|-----------------------------|--------------------------|
| CDS-felek | msdyn_parties | 
| CDS postai címének helyei | msdyn_postaladdresscollections | 
| CDS-fél postai címének előzményei V2 | msdyn_postaladdresses | 
| CDS-fél postai címének helyei | msdyn_partypostaladdresses | 
| Ügyfél-kapcsolattartók V3 | msdyn_partyelectronicaddresses | 
| Vevők V3 | számlák | 
| Vevők V3 | kapcsolattartók | 
| Szállítók V2 | msdyn_vendors | 
| Kapcsolattartó megszólításai | msdyn_salescontactpersontitles | 
| Udvarias levélzárások | msdyn_complimentaryclosings | 
| Üdvözlések | msdyn_salutations | 
| Döntéshozatali szerepkörök | msdyn_decisionmakingroles | 
| Foglalkoztatási beosztásfunkciók | msdyn_employmentjobfunctions | 
| Hűségszintek | msdyn_loyaltylevels | 
| Személyes karaktertípusok | msdyn_personalcharactertypes | 
| Kapcsolattartók V2 | msdyn_contactforparties | 
| CDS értékesítésiajánlat-fejléc | ajánlatok | 
| CDS értékesítésirendelés-fejlécek | salesorders | 
| Értékesítésiszámla-fejlécek V2 | számlák | 
| CDS-címszerepkre | msdyn_addressroles |

**Függőségi információ**

A kettős írású fél és globális címjegyzék megoldásai a következő három csomagtól függenek. Ezért ezeket a csomagokat még a két írásos fél és globális címjegyzék megoldáscsomag telepítése előtt telepíteni kell.

- Két írásos Application Core csomag
- Két írású pénzügyi csomag
- Két írású ellátásilánc-csomag
