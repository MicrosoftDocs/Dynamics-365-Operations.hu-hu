---
title: Entitásfüggőségi lánc (szinkronizálási sorrend)
description: Ez a témakör azt a szinkronizálási sorrendet határozza meg, amelyet a kezdeti adatok létrehozásához követnie kell.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 4adb2c8d57ad8f67346b8d34212b7a4b0bd052ab
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173131"
---
# <a name="entity-dependency-chain-synchronization-order"></a>Entitásfüggőségi lánc (szinkronizálási sorrend)

[!include [banner](../../includes/banner.md)]



A következő következő táblákban az entitások abban a sorrendben vannak felsorolva, amelyben engedélyeznie kell őket. Ha engedélyezi a kezdeti szinkronizáláshoz tartozó megfeleltetést, akkor a kettős írás atutomatikusan észlel más megfeleltetéseket, amelyeket engedélyezni szükséges. A Finance and Operations alkalmazások **Kettős írás** oldala segítségével kijelölhet entitásokat a kezdeti szinkronizálás során, vagy visszavonhatja ezek kijelölését.

A Kettős írás legújabb verziójában akár csak néhány entitást is engedélyezhet, és a rendszer kezeli Ön helyett a függőségeket.

## <a name="dynamics-365-supply-chain-management-entities"></a>Dynamics 365 Supply Chain Management entitások

A Supply Chain Management következő entitásai abban a sorrendben vannak felsorolva, amelyben engedélyeznie kell őket.

| Név megfeleltetése a Kettős írás oldalon | Entitás metaadatainak neve a Supply Chain Management modulban | Entitás metaadatainak neve a Common Data Service modulban | Jegyzetek |
|---|---|---|---|
| Egységek ... mértékegységek                                                                      | UnitOfMeasureEntity                                    | mértékegység                                          | |
| Mértékegység-átváltások ... msdyn_unitofmeasureconversions                                 | UnitOfMeasureConversionEntity                          | msdyn_unitofmeasureconversion                | |
| Összes termék ... msdyn_globalproducts                                               | EcoResEveryProductEntity                               | msdyn_globalproduct                          | |
| Termékdimenzió-csoportok ... msdyn_productdimensiongroups                           | EcoResProductDimensionGroupEntity                      | msdyn_productdimensiongroup                  | |
| Tárolásidimenzió-csoportok ... msdyn_productstoragedimensiongroups                    | EcoResStorageDimensionGroupEntity                      | msdyn_productstoragedimensiongroup           | |
| Nyomon követési dimenziócsoportok ... msdyn_producttrackingdimensiongroups                  | EcoResTrackingDimensionGroupEntity                     | msdyn_producttrackingdimensiongroup          | |
| Színek ... msdyn_productcolors                                                      | EcoResProductColorEntity                               | msdyn_productcolor                           | |
| Méretek ... msdyn_productsizes                                                        | EcoResProductSizeEntity                                | msdyn_productsize                            | |
| Stílusok ... msdyn_productstyles                                                      | EcoResProductStyleEntity                               | msdyn_productstyle                           | |
| Konfigurációk ... msdyn_productconfigurations                                      | EcoResProductConfigurationEntity                       | msdyn_productconfiguration                   | |
| Kibocsátott termékek V2 ... msdyn_sharedproductdetails                                 | EcoResReleasedProductV2Entity                          | msdyn_sharedproductdetail                    | |
| Common Data Service kibocsátott egyedi termékek ... termékek                         | EcoResReleasedDistinctProductCommon Data ServiceEntity | termék                                      | |
| Termékszám-azonosított vonalkód ... msdyn_productbarcodes                         | EcoResProductNumberIdentifiedBarcodeEntity             | msdyn_productbarcode                         | |
| Alapértelmezett rendelési beállítások ... msdyn_productdefaultordersettings                        | InventProductDefaultOrderSettingsEntity                | msdyn_productdefaultordersetting             | |
| Termék alapértelmezett rendelési beállításai V2 ... msdyn_productspecificdefaultordersettings     | InventProductSpecificOrderSettingsV2Entity             | msdyn_productspecificdefaultordersetting     | |
| Termékspecifikus mértékegység-átváltások ... msdyn_productspecificunitofmeasureconversions | EcoResProductSpecificUnitConversionEntity              | msdyn_productspecificunitofmeasureconversion | |
| Telephelyek ... msdyn_operationalsites                                                    | InventOperationalSiteEntity                            | msdyn_operationalsite                        | |
| Raktárak ... msdyn_warehouses                                                     | InventWarehouseEntity                                  | msdyn_warehouse                              | Lásd: [1. megjegyzés](#scm-notes). |
| Alaptermék színei ... msdyn_sharedproductcolors                                 | EcoResProductMasterColorEntity                         | msdyn_sharedproductcolor                     | |
| Alaptermék méretei ... msdyn_sharedproductsizes                                   | EcoResProductMasterSizeEntity                          | msdyn_sharedproductsize                      | |
| Alaptermék stílusai ... msdyn_sharedproductstyles                                 | EcoResProductMasterStyleEntity                         | msdyn_sharedproductstyle                     | |
| Alaptermék konfigurációi ... msdyn_sharedproductconfigurations                 | EcoResProductMasterConfigurationEntity                 | msdyn_sharedproductconfiguration             | |
| Termékkategóriák ... msdyn_productcategories                                      | EcoResProductCategoryEntity                            | msdyn_productcategory                        | Lásd: [2. megjegyzés](#scm-notes). |
| Termékkategória-hozzárendelések ... msdyn_productcategoryassignments                   | EcoResProductCategoryAssignmentEntity                  | msdyn_productcategoryassignment              | |
| Termékkategória-hierarchiák ... msdyn_productcategoryhierarchies                   | EcoResProductCategoryHierarchyEntity                   | msdyn_productcategoryhierarchy               | |
| Termékkategória-hierarchia szerepkörei ... msdyn_productcategoryhierarchyroles            | EcoResProductCategoryHierarchyRoleEntity               | msdyn_productcategoryhierarchyrole           | |
| Raktárfolyosó ... msdyn_warehouseaisles                                           | WMSWarehouseAisleEntity                                | msdyn_warehouseaisle                         | |
| Raktárzónák ... msdyn_warehousezones                                            | WHSWarehouseZoneEntity                                 | msdyn_warehousezone                          | |
| Raktárzónacsoportok ... msdyn_warehousezonegroups                                 | WHSWarehouseZoneGroupEntity                            | msdyn_warehousezonegroup                     | |
| Raktárhelyszínek ... msdyn_inventorylocations                                    | WMSWarehouseLocationEntity                             | msdyn_inventorylocation                      | Lásd: [3. megjegyzés](#scm-notes). |
| Raktárimunka-fejlécek ... msdyn_warehouseworkheaders                               | WHSWarehouseWorkHeaderEntity                           | msdyn_warehouseworkheader                    | |
| Raktári munkasorok... msdyn_warehouseworklines                                    | WHSWarehouseWorkLineEntity                             | msdyn_warehouseworklines                     | Lásd: [4. megjegyzés](#scm-notes). |
| Szállítási módok ... msdyn_shipvias                                                | DlvDeliveryModeEntity                                  | msdyn_shipvias                               | |
| Szállítási feltételek ... msdyn_termsofdeliveries                                       | DeliveryTermsEntity                                    | msdyn_termsofdelivery                        | |
| Értékesítési rendelés forráskódjai ... msdyn_salesorderorigins                                | SalesOrderOriginEntity                                 | msdyn_salesorderorigin                       | |
| Common Data Service értékesítési rendelések fejlécei ... salesorders                             | SalesOrderHeaderCommon Data ServiceEntity              | salesorder                                   | |
| Common Data Service értékesítési rendelési sorok ... salesorderdetails                         | SalesOrderLineCommon Data ServiceEntity                | salesorderdetails                            | |
| Common Data Service értékesítési ajánlat fejléce ... quotes                               | SalesQuotationHeaderCommon Data ServiceEntity          | árajánlat                                        | |
| Common Data Service értékesítési ajánlat sorai ... quotedetails                          | SalesQuotationLineCommon Data ServiceEntity            | QuoteDetails                                 | |
| Értékesítésiszámla-fejlécek V2 ... számlák                                               | SalesInvoiceHeaderV2Entity                             | számla                                      | |
| Értékesítésiszámla-sorok V2 ... invoicedetails                                           | SalesInvoiceLineV2Entity                               | invoicedetail                                | |

### <a name="mapping-specific-notes"></a><a id='scm-notes'></a>Megfeleltetésspecifikus megjegyzések

1. Az önmagától függőség miatt előfordulhat, hogy a kezdeti szinkronizálást kétszer kell futtatnia.
2. Alapértelmezés szerint a kezdeti szinkronizálás le van tiltva, mert a szülő-gyermek kapcsolat ("okos" rendelés nem a platform által kezelt). Ennek megfelelően a meglévő termékkategóriák kézi szinkronizálása szükséges (például a kategória leírásának frissítése alapján) a megfelelő sorrendben (először a gyökér kategóriát, a gyermekeket, majd a gyermek gyermekeit). Ugorjon a következő útvonalra: **Termékinformációk kezelése \> Beállítás \> Kategóriák és attribútumok \> Kategóriahierarchiák**. A **Kategóriahierarchiák** lapon kiválaszthatja az egyes hierarchiákat, és megtekintheti azokban levő termékkategóriákat.
3. Az üres **ItemNumberInLocation** keresési mezők és az első, második és harmadik további raktári zónák leképezése a kezdeti szinkronizálás sikertelenségét fogja eredményezni. Ezért a rendszer most eltávolítja ezeket a leképezéseket.
4. Az üres **CaptureWeight** mező leképezése a kezdeti szinkronizálás sikertelenségét fogja eredményezni. Ezért a rendszer most eltávolítja ezt a leképezést.

### <a name="setup-related-information"></a>Telepítéssel kapcsolatos információk

+ Amikor a rekordokat először létrehozzák a Dynamics 365 modellvezérelt alkalmazásaiban levő **Termékek** entitásban, először **Vázlat** állapotúak. Ahhoz, hogy **Aktív** állapotra állítsa, lépjen a **Beállítások \> Felügyelet \> Rendszerbeállítások \> Értékesítés** pontra a modellvezérelt alkalmazásban, és állítsa a **Termékek létrehozása aktív állapotban** beállítást **Igen** értékre.
+ Ha a Dynamics 365 modellvezérelt alkalmazásainak **Termékek** entitásában vagy a Common Data Service szolgáltatásban azelőtt hoz létre rekordokat, mielőtt engedélyezia kettős írást, ezeket a rekordokat a rendszer csak akkor frissíti, ha a teljes kulcs, beleértve a **Vállalat** mezőt, megegyezik a Finance and Operations alkalmazásban szereplő adatokkal.
+ A **Termékek** entitásának szinkronizálása egyirányú, a Finance and Operations alkalmazásokból a Common Data Service szolgáltatásba. Ha a Dynamics 365 modellvezérelt alkalmazások **Termékek** entitásában egy megfeleltetett mező frissül, akkor a frissítést a Finance and Operations alkalmazás legközelebbi frissítésekor a rendszer felülírja.

### <a name="known-issues"></a>Ismert problémák

- Hiba történik, amikor a Finance and Operations alkalmazásban egy egység törlődik. Amikor a mértékegységeket a rendszer szinkronizálja a Finance and Operations alkalmazásból a Common Data Service szolgáltatásba, létrejön egy specifikus osztály első egysége elsődleges egységként, és ez megakadályozza a törlést.

    **Kockázatcsökkentés:** Először törölje az egységet a Common Data Service szolgáltatásban. Ezt követően lehet törölni a Finance and Operations alkalmazásban.

- Hiba történik, amikor a Common Data Service alkalmazásban egy üzemeltetési hely törlődik. A hibaüzenet a következő: „Információs napló: Figyelmeztetés: Az elsődleges címet nem lehet törölni.; Figyelmeztetés: Az entitásrekord nem törölhető, mert a következő adatforrás ellenőrzése sikertelen volt: InventSiteLogisticsLocation (InventSiteLogisticsLocation).” A hibát a Finance and Operations alkalmazásban található adatentitás okozza.

    **Kockázatcsökkentés:** Először törölheti a helyet a Finance and Operations alkalmazásban. A hely ezután törlődik a Common Data Service szolgáltatásban, ha a kapcsolódó kettős írási megfeleltetés fut.

## <a name="dynamics-365-finance-entities"></a>Dynamics 365 Finance entitások

A Dynamics 365 Finance következő entitásai abban a sorrendben vannak felsorolva, amelyben engedélyeznie kell őket.

| Név megfeleltetése a Kettős írás oldalon | Entitás metaadatainak neve a Finance modulban | Entitás metaadatainak neve a Common Data Service modulban | Jegyzetek |
|---|---|---|---|
| Pénznemek ... transactioncurrencies                                            | CurrencyEntity                              | Pénznem                                   | |
| Árfolyamtípus ... msdyn_exchangeratetypes                                  | ExchangeRateTypeEntity                      | msdyn_exchangeratetype                     | |
| Árfolyam pénznempárja ... msdyn_currencyexchangeratepairs                 | ExchangeRateCurrencyPairEntity              | msdyn_currencyexchangeratepair             | |
| Common Data Service árfolyamok ... msdyn_currencyexchangerates              | ExchangeRateCommon Data ServiceEntity       | msdyn_currencyexchangerate                 | Lásd: [1. megjegyzés](#fin-notes). |
| Pénzügyi naptár integrációs entitása ... msdyn_fiscalcalendars                    | FiscalCalendarEntity                        | msdyn_fiscalcalendar                       | |
| Pénzügyi naptári év integrációs entitása ... msdyn_fiscalcalendaryears           | FiscalCalendarYearEntity                    | msdyn_fiscalcalendaryear                   | |
| Pénzügyi naptár időszaka ... msdyn_fiscalcalendarperiods                          | FiscalPeriodEntity                          | msdyn_fiscalcalendarperiod                 | |
| Szervezeti hierarchia típusa ... msdyn_internalorganizationhierarchytypes        | OMOrganizationHierarchyTypeEntity           | msdyn_internalorganizationhierarchytype    | Lásd: [1. megjegyzés](#fin-notes). |
| Szervezeti hierarchia céljai ... msdyn_internalorganizationhierarchypurposes | OMOrganizationHierarchyPurposeEntity        | msdyn_internalorganizationhierarchypurpose | Lásd: [1. megjegyzés](#fin-notes). |
| Jogi személyek ... msdyn_internalorganizations                                  | OMLegalEntity                               | msdyn_internalorganization                 | Lásd: [1. megjegyzés](#fin-notes). |
| Jogi személyek ... cdm_companies                                                | OMLegalEntity                               | cdm_company                                | |
| Üzemi egység ... msdyn_internalorganizations                                  | OMOperatingUnitEntity                       | msdyn_internalorganization                 | Lásd: [1. megjegyzés](#fin-notes). |
| A szervezeti hierarchia - közzétéve ... msdyn_internalorganizationhierarchies    | OMOrganizationHierarchyPublishedEntity      | msdyn_internalorganizationhierarchy        | Lásd: [1. megjegyzés](#fin-notes). |
| Névutók ... msdyn_nameaffixes                                              | DirNameAffixEntity                          | msdyn_nameaffix                            | |
| Fizetési napok Common Data Service ... msdyn_paymentdays                          | PaymentDayCommon Data ServiceEntity         | msdyn_paymentday                           | |
| Fizetési nap sorai Common Data Service V2 ... msdyn_paymentdaylines              | PaymentDayLineCommon Data ServiceV2Entity   | msdyn_paymentdayline                       | |
| Fizetési ütemezés ... msdyn_paymentschedules                                     | PaymentScheduleEntity                       | msdyn_paymentschedule                      | |
| Fizetési ütemezés sorai ... msdyn_paymentschedulelines                           | PaymentScheduleLineEntity                   | msdyn_paymentscheduleline                  | |
| Fizetési feltételek ... msdyn_paymentterms                                         | PaymentTermEntity                           | msdyn_paymentterm                          | |
| Vevő fizetési módja ... msdyn_customerpaymentmethods                        | CustomerPaymentMethodEntity                 | msdyn_customerpaymentmethod                | |
| Szállító fizetési módja ... msdyn_vendorpaymentmethods                            | VendorPaymentMethodEntity                   | msdyn_vendorpaymentmethod                  | |
| Vevői csoportok ... msdyn_customergroups                                        | CustCustomerGroupEntity                     | msdyn_customergroup                        | |
| Szállítói csoportok ... msdyn_vendorgroups                                            | VendVendorGroupEntity                       | msdyn_vendorgroup                          | |
| Áfacsoportok ... msdyn_taxgroups                                            | TaxGroupEntity                              | msdyn_taxgroup                             | |
| Cikk áfacsoportjai ... msdyn_taxitemgroups                                   | TaxItemGroupEntity                          | msdyn_taxitemgroup                         | |
| Áfafőkönyv-feladási csoportok V2 ... msdyn_taxpostinggroups                   | TaxPostingGroupEntityV2                     | msdyn_taxpostinggroup                      | |
| Áfamentességi kódentitás Common Data Service ... msdyn_taxexemptcodes       | TaxExemptCodeCommon Data ServiceEntity      | msdyn_taxexemptcode                        | |
| Áfahatóságok ... msdyn_taxauthorities                                  | TaxAuthorityEntity                          | msdyn_taxauthority                         | |
| Áfakód ... msdyn_taxcodes                                               | TaxCodeEntity                               | msdyn_taxcode                              | Lásd: [1. megjegyzés](#fin-notes). |
| Pénzügyi dimenzió formátuma ... msdyn_financialdimensionformats                  | DimensionIntegrationFormatEntity            | msdyn_financialdimensionformat             | |
| Pénzügyi dimenziók ... msdyn_dimensionattributes                              | DimensionAttributeEntity                    | msdyn_dimensionattribute                   | |
| Adóelőleg-csoportok ... msdyn_withholdingtaxgroups                           | TaxWithholdingGroupEntity                   | msdyn_withholdingtaxgroup                  | |
| Adóelőlegkódok ... msdyn_withholdingtaxcodes                             | TaxWithholdingTaxCodes                      | msdyn_withholdingtaxcode                   | |
| Számlatükör ... msdyn_chartofaccountses                                   | LedgerChartOfAccountsEntity                 | msdyn_chartofaccounts                      | |
| Főkönyv ... msdyn_ledgers                                                        | LedgerEntity                                | msdyn_ledger                               | Lásd: [1. megjegyzés](#fin-notes). |
| Fő számla kategóriái ... msdyn_mainaccountcategories                         | MainAccountCategoryEntity                   | msdyn_mainaccountcategory                  | |
| Fő számla ... msdyn_mainaccounts                                             | MainAccountEntity                           | msdyn_mainaccount                          | |
| Vevők V3 ... accounts                                                       | CustCustomerV3Entity                        | számla                                    | Lásd: [2. megjegyzés](#fin-notes). |
| Vevők V3 ... contacts                                                       | CustCustomerV3Entity                        | kapcsolat                                    | Lásd: [3. megjegyzés](#fin-notes). |
| Szállítók V2 ... msdyn_vendors                                                    | VendVendorV2Entity                          | msdyn_vendor                               | Lásd: [2. megjegyzés](#fin-notes). |
| Common Data Service Kapcsolattartók V2 ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | kapcsolat                                    | Lásd: [4. megjegyzés](#fin-notes). |
| Common Data Service Kapcsolattartók V2 ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | kapcsolat                                    | Lásd: [5. megjegyzés](#fin-notes). |

### <a name="mapping-specific-notes"></a><a id='fin-notes'></a>Megfeleltetésspecifikus megjegyzések

1. Egyirányú szinkronizáció történik a Finance and Operations alkalmazásokból a Common Data Service szolgáltatásba.
2. Az önmagától függőség miatt előfordulhat, hogy a kezdeti szinkronizálást egynél többször kell futtatnia. Ne feledje el kapcsolattípusként a **Vevő** értéket kiválasztani, amikor a Common Data Service **Partnerek** oldalán létrehoz egy partnert. Ha probléma merül fel az **Elsődleges kapcsolattartó** mezővel a kezdeti szinkronizálás során, távolítsa el a mezőt a megfeleltetésből, és futtassa ismét a kezdeti szinkronizálást. A kezdeti szinkronizálás sikeres végrehajtása után állítsa le a megfeleltetést, és adja hozzá ismét az **Elsődleges kapcsolattartó** mezőt. Ezután indítsa el a megfeleltetést, de hagyja ki a kezdeti szinkronizálást. Az **Elsődleges kapcsolattartó** mező értéke nem fog szerepelni a kezdeti szinkronizálásban, és manuálisan kell áttelepítenie az értékeket.
3. Győződjön meg arról, hogy a Common Data Service **Kapcsolattartók** oldalán az **Értékesíthető** beállítás értéke **Igen**, amikor **Személy** típusú vevőt hoz létre.
4. Ennek a megfeleltetésnek mind a két oldalán szűrő található a vevői kapcsolattartók összekötése érdekében. Nyissa meg a megfeleltetési adatokat, válassza ki a szűrő gombot (tölcsér szimbólum) a **Sales.Contact** entitás neve mellett, és ellenőrizze, hogy a fájl feltételei között szerepel a **msdyn_contactforvendor eq igaz és msdyn_sellable eq hamis**.
5. Ennek a megfeleltetésnek mind a két oldalán szűrő található a szállítói kapcsolattartók összekötése érdekében. Nyissa meg a megfeleltetési adatokat, válassza ki a szűrő gombot (tölcsér szimbólum) a **Sales.Contact** entitás neve mellett, és ellenőrizze, hogy a szűrés feltételei között szerepel a **msdyn_contactforvendor eq igaz és msdyn_sellable eq hamis**. 

## <a name="dynamics-365-human-resources-entities"></a>Dynamics 365 Human Resources entitások

A Dynamics 365 Human Resources következő entitásai abban a sorrendben vannak felsorolva, amelyben engedélyeznie kell őket.

| Név megfeleltetése a Kettős írás oldalon | Entitás metaadatainak neve a Human Resources-ban | Entitás metaadatainak neve a Common Data Service modulban | Jegyzetek |
|---|---|---|---|
| cdm_jobfunction – Beosztás                                |                                   | cdm_jobfunction                  | |
| cdm_jobtypes – Feladattípusok                                      |                                   | cdm_jobtypes                     | |
| cdm_jobs – Feladatok                                               |                                   | cdm_jobs                         | |
| cdm_jobs – Feladat részletei                                        |                                   | cdm_jobs                         | |
| cdm_positiontype – PositionType                               | HcmPositionTypeEntity             | cdm_positiontype                 | |
| cdm_jobpositions – Alappozíció                              | HcmPositionBaseEntity             | cdm_jobposition                  | Lásd: [1. megjegyzés](#hr-notes). |
| cdm_jobposition – Pozíció részletei                            | HcmPositionDetailEntity           | cdm_jobposition                  | Lásd: [1. megjegyzés](#hr-notes). |
| cdm_jobposition – Pozíció időtartama                           | HcmPositionDurationEntity         | cdm_jobposition                  | Lásd: [1. megjegyzés](#hr-notes). |
| cdm_jobposition – Pozícióhierarchiák                        | HcmPositionHierarchyEntity        | cdm_jobposition                  | Lásd: [1. megjegyzés](#hr-notes). |
| cdm_veteranstatus – Veterán állapot                            |                                   | cdm_veteranstatus                | |
| cdm_ethnicorigin – Etnikum                              |                                   | cdm_ethnicorigin                 | |
| cdm_languagecode – Nyelvkód                              |                                   | cdm_languagecode                 | |
| cdm_worker – Dolgozó                                           | HcmWorkerEntity                   | cdm_worker                       | |
| cdm_employments – Munkaviszonyok                                 |                                   | cdm_employments                  | |
| cdm_employments – Munkaviszony részletei                           |                                   | cdm_employments                  | |
| cdm_positionworkerassignmentmaps – Beosztáshoz rendelt dolgozó | HcmPositionWorkerAssignmentEntity | cdm_positionworkerassignmentmaps | Lásd: [2. megjegyzés](#hr-notes).|

### <a name="mapping-specific-notes"></a><a id='hr-notes'></a>Megfeleltetésspecifikus megjegyzések

1. Egy Common Data Service entitás több Finance and Operations alkalmazásentitással van megfeleltetve.
2. Az adott megfeleltetés önmagára hivatkozik.

## <a name="asset-management-entities"></a>Eszközkezelési entitások

A Dynamics 365 Supply Chain Management Eszközkezelésének következő entitásai abban a sorrendben vannak felsorolva, amelyben engedélyeznie kell őket.

| Név megfeleltetése a Kettős írás oldalon | Entitás metaadatainak neve az Eszközkezelésben | Entitás metaadatainak neve a Common Data Service modulban | Jegyzetek |
|---|---|---|---|
| FO.AssetManagementAssetLifecycleStates--Common Data Service.msdyn_assetlifecyclestates                           | Tárgyieszközkezelés eszközéletciklus állapotai               | msdyn_assetlifecyclestates               | |
| FO.AssetManagementAssetLifecycleModels--Common Data Service.msdyn_assetlifecyclemodels                           | Tárgyieszközkezelés eszközéletciklus modelljei               | msdyn_assetlifecyclemodels               | |
| FO.AssetManagementFunctionalLocationLifecycleModels--Common Data Service.msdyn_functionallocationlifecyclemodels | Eszközkezelés munkavégési helyszín életciklusmodellek | msdyn_functionallocationlifecyclemodels  | |
| FO.AssetManagementFunctionalLocationLifecycleStates--Common Data Service.msdyn_functionallocationlifecyclestates | Eszközkezelés munkavégési helyszín életciklusállapotok | msdyn_functionallocationlifecyclestates  | |
| FO.AssetManagementAssetTypes--Common Data Service.msdyn_customerassetcategories                                  | Tárgyieszköz-kezelő eszköztípusok                          | msdyn_customerassetcategories            | |
| FO.AssetManagementFunctionalLocationTypes--Common Data Service.msdyn_functionallocationtypes                     | Tárgyieszköz-kezelés munkavégzési helyszíntípusok            | msdyn_functionallocationtypes            | |
| FO.AssetManagementFunctionalLocations--Common Data Service.msdyn_functionallocations                             | Tárgyieszköz-kezelés munkavégzési helyszínek                 | msdyn_functionallocations                | Lásd [a megjegyzést](#am-notes). |
| FO.AssetManagementAssets--Common Data Service.msdyn_customerassets                                               | Tárgyieszköz-kezelő eszközök                               | msdyn_customerassets                     | Lásd [a megjegyzést](#am-notes). |
| FO.AssetManagementManufacturers--Common Data Service.msdyn_manufacturers                                         | Tárgyieszközök gyártói                        | msdyn_manufacturers                      | |
| FO.AssetManagementModels--Common Data Service.msdyn_models                                                       | Tárgyieszköz-kezelési modellek                               | msdyn_models                             | |
| FO.AssetManagementWarranty--Common Data Service.msdyn_warranties                                                 | Tárgyeszköz-kezelés garancia                             | msdyn_warranties                         | |

### <a name="mapping-specific-notes"></a><a id='am-notes'></a>Megfeleltetésspecifikus megjegyzések

- Az önmagától függőség miatt előfordulhat, hogy a kezdeti szinkronizálást egynél többször kell futtatnia.
