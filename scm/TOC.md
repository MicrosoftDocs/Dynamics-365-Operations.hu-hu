# [Költségkezelés](cost-management/TOC.md)
# [Készletgazdálkodás](inventory/TOC.md)
# Alaptervezés
## Igény-előrejelzés létrehozása
### [Igény-előrejelzés áttekintése](master-planning/introduction-demand-forecasting.md)
### [Igény-előrejelzés beállítása](master-planning/demand-forecasting-setup.md)
### [Statisztikai kiinduló előrejelzés létrehozása](master-planning/generate-statistical-baseline-forecast.md)
### [Manuális módosítás a kiinduló előrejelzésen](master-planning/manual-adjustments-baseline-forecast.md)
### [Módosított előrejelzés engedélyezése](master-planning/authorize-adjusted-forecast.md)
### [Előrejelzés pontosságának követése](master-planning/monitor-forecast-accuracy.md)
### [Korábbi tranzakcióadatok kiugró értékeinek eltávolítása](master-planning/remove-historical-outliers-calculating-demand-forecast.md)
### [Csökkentési kulcsok](master-planning/reduction-keys.md)
## Alapterv
### [Műveletkérő üzenetek](master-planning/action-messages.md)
### [Fedezeti beállítások](master-planning/coverage-settings.md)
### [Késések](master-planning/delays.md)
### [Alaptervek](master-planning/master-plans.md)
### [Az alaptervezek és a többhelyes funkció](master-planning/master-plan-multisite-functionality.md)
#### [Telephely fedezet tervezése, kötelező raktár](master-planning/master-plan-site-coverage-warehouse-mandatory.md)
#### [Telephely fedezet tervezése, raktár nem kötelező](master-planning/master-plan-site-coverage-warehouse-not-mandatory.md)
#### [Telephely és raktárfedezet tervezése, kötelező raktár](master-planning/master-plan-site-warehouse-coverage-warehouse-mandatory.md)
#### [Telephely és raktárfedezet tervezése, nem kötelező raktár](master-planning/master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)
#### [Anyagjegyzék-verzió](master-planning/master-plan-bom-version-determined.md)
### [Az Anyagjegyzék-verzió alábontása](master-planning/master-plan-explosion-bom-version.md)
### [Tervezett rendelések karbantartása](master-planning/maintain-planned-orders.md)
### [Alábontás nyomon követése](master-planning/trace-explosion.md)
# Beszerzés és forrás
## [A Beszerzés és forrás modul áttekintése](procurement/procurement-sourcing-overview.md)
## [Beszerzésekkel és forrásokkal kapcsolatos munkafolyamat](procurement/procurement-sourcing-workflows.md)
## [Beszerzési irányelvek](procurement/purchase-policies.md)
## [Beszerzési katalógusok](procurement/procurement-catalogs.md)
## [Beszerzési igénylések](procurement/purchase-requisitions-overview.md)
### [Beszerzési igénylési munkafolyamat](procurement/purchase-requisitions-workflow.md) 
## [Ajánlatkérések](procurement/request-quotations.md)
## Beszerzési rendelések
### [Beszerzési rendelések áttekintése](procurement/purchase-order-overview.md)
### [Beszerzési rendelések létrehozása](procurement/purchase-order-creation.md)
### [Beszerzési rendelések jóváhagyása és megerősítése](procurement/purchase-order-approval-confirmation.md)
## Szállítókezelés és együttműködés
### [Szállítói együttműködés beállítása és karbantartása](procurement/set-up-maintain-vendor-collaboration.md)
### [Szállítói együttműködés felhasználóinak kezelése](procurement/manage-vendor-collaboration-users.md)
### [Szállítói számlák beállítása](procurement/set-up-vendor-accounts.md)
### [A külső szállítókkal történő szállítói együttműködés](procurement/vendor-collaboration-work-external-vendors.md)
### [Szállítói együttműködés a vevőkkel](procurement/vendor-collaboration-work-customers-dynamics-365-operations.md)
### [Együttműködés a szállítókkal a Szállítói portálon keresztül](procurement/collaborate-vendors-vendor-portal.md)
### [Szállítói együttműködési mobil munkaterület](procurement/vendor-collaboration-mobile-workspace.md)
### [Szállítói portál felhasználói biztonság](procurement/configure-security-vendor-portal-users.md)
## Árak és engedmények
### [Beszerzési szerződések](procurement/purchase-agreements.md)
## Termékbevételezések és számlázás
### [Termékbevételezés összevetése a beszerzési rendelésekkel](procurement/product-receipt-against-purchase-orders.md)
### [Szállítói számlák áttekintése](/dynamics365/operations/financials/accounts-payable/vendor-invoices-overview?toc=/dynamics365/operations/supply-chain/toc.json)
### [Szállítói feladási profilok](/dynamics365/operations/financials/accounts-payable/vendor-posting-profiles?toc=/dynamics365/operations/supply-chain/toc.json)
# Termékinformációk kezelése
## Termékinformációk
### [Anyagjegyzék és receptúra](production-control/bill-of-material-bom.md)
### [Anyagjegyzék-tervező funkciója](production-control/bom-designer-functionality.md)
### [Termékdimenzió](pim/product-dimensions.md)
### [Termékszám elnevezési rendszere](pim/product-variant-identification-nomenclature.md)
### [Termékkel kapcsolatos fordítás GYIK](pim/translations-product-related-information.md)
### [Sorozatszám bejegyzése az értékesítési folyamat során](sales-marketing/register-serial-numbers-sales-process.md)
### [Termék keresése rendelésbevitel során](pim/search-products-product-variants.md)
## Termékkonfiguráció létrehozása
### [Termékkonfigurációs modell felépítése](pim/build-product-configuration-model.md)
### [Számítás a termékkonfigurációs modellhez GYIK](pim/calculate-product-configuration-models.md)
### [Konfigurációs szabály](pim/configuration-rules.md)
### [Dimenzión alapuló konfiguráció](pim/dimension-based-product-configuration.md)
### [Kifejezésmegszorítás és táblamegszorítás](pim/expression-constraints-table-constraints-product-configuration-models.md)
### [Termékkonfiguráció újrafelhasználása](pim/reuse-product-configurations.md)
### [Konfigurációs modell beállítása](pim/set-up-maintain-product-configuration-model.md)
### [Rendszer által definiált és felhasználó által definiált táblamegszorítás](pim/system-defined-user-defined-table-constraints.md)
# Gyártásvezérlés
## Termelési folyamat    
### [Tevékenységalapú alvállalkozásba adás](production-control/activity-based-subcontracting.md)
### [Kötegattribútumok](production-control/batch-attributes.md)
### [Anyagjegyzékek és receptúrák](production-control/bill-of-material-bom.md)
### [Anyagjegyzék-tervező funkciója](production-control/bom-designer-functionality.md)
### [Összesített kötegrendelések](production-control/consolidated-batch-orders.md)
### [Alvállalkozói munka kezelése a termelésben](production-control/manage-subcontract-work-production.md)
### [Vegyes módú tervezés: Elkülönített, folyamatos és lean típusú források kombinálása](production-control/mixed-mode-plan.md)
### [Termelési folyamat](production-control/production-process-overview.md)
### [A termelésbeállítás követelményei](production-control/production-set-up-requirements.md)
### [Útvonalak és műveletek](production-control/routes-operations.md)
## Termelési rendelések
### [Termelési rendelések létrehozása](production-control/create-production-orders.md)
### [Dimenziókra és termékváltozatokra vonatkozó alapértelmezett rendelésbeállítások](production-control/default-order-settings.md)
### [Termelési rendelések kiadása](production-control/release-production-orders.md)
### [Termelési rendelési állapot sztornírozása](production-control/reverse-production-order-status.md)
### [Anyagjegyzékek jelentése befejezettként](production-control/report-boms-as-finished.md)
### [Termelési rendelések jelentése befejezettként](production-control/report-production-orders-as-finished.md)
## Lean termelés 
### [Kanban átviteli tábla támogatás vonalkódolvasókhoz](production-control/kanban-transfer-board-support-barcode-scanner.md) 
### [Kanbanfeladat ütemezése – Lean manufacturing](production-control/lean-manufacturing-kanban-job-scheduling.md)
### [Lean manufacturing (áttekintés)](production-control/lean-manufacturing-overview.md)
### [Lean szervezet modellezése](production-control/lean-manufacturing-modeling-lean-organization.md)
## Műveletek és feladatok ütemezése
### [Idők hozzárendelése egy feladatköteg feladataihoz](production-control/allocate-time-jobs-job-bundle.md)
### [Feladat ütemezése](production-control/job-scheduling.md)
### [A műveletek ütemezésének beállításai](production-control/operation-scheduling-options.md)
### [Műveletek ütemezése](production-control/operations-scheduling.md)
## Erőforrások
### [Üzemi erőforrások](production-control/operations-resources.md)
### [Erőforrás-képességek](production-control/resource-capabilities.md)
### [Munkaidő és jelenlét rögzítése](production-control/time-attendance-registrations.md)
## Gyártásvégrehajtás
### [Anyaghelyettesítés a gyártásban](production-control/substitute-items-bom-lines.md)
### [Anyagfelhasználás kiszámítása](production-control/consumption.md)
### [Termelési visszajelzés](production-control/production-feedback.md)
### [Termelési rendelés alapbeállításai a gyártásvégrehajtásban](production-control/production-order-defaults-manufacturing-execution.md)
### [Termelés feladása](cost-management/production-posting.md)
### [Gyártásvégrehajtás regisztrációja](production-control/registration-manufacturing-execution.md)
# Értékesítés és marketing
## [Marketing](sales-marketing/overview-sales-marketing.md)
## Értékesítési rendelések
### [Rendelési ígéretek](sales-marketing/delivery-dates-available-promise-calculations.md)
### [Rendelésbeviteli határidők](sales-marketing/order-entry-deadlines.md)
### [Közvetlen kiszállítások](sales-marketing/direct-deliveries.md)
### [Szállítási ütemezések](sales-marketing/delivery-schedules.md)
### [Sorozatszámok az értékesítési folyamatban](sales-marketing/register-serial-numbers-sales-process.md)
### [Foglalás ugyanazon kötegelt adagból](sales-marketing/reserve-same-batch-sales-order.md)
## [Értékesítési szerződések](sales-marketing/sales-agreements.md)
## Értékesítési ajánlatok
### [Árszimuláció](sales-marketing/price-simulation.md)
## Visszáru
### [Értékesítési visszáruk](warehousing/sales-returns.md)
# Szállításkezelés
## [Új szállítási kalkulátor](transportation/create-new-transportation-management-engine.md)
## [Fuvarlevél létrehozása](transportation/create-bill-of-lading.md)
## [Szállítmányozási útvonaltervezés](transportation/plan-freight-transportation-routes-multiple-stops.md)
## [Rakományok tervezése központ-összevonás használatával](transportation/plan-loads-hub-consolidation.md)
## [Fuvarlevél egyeztetése](transportation/reconcile-freight-transportation-management.md)
## [Szállításkezelés](transportation/transportation-management-overview.md)
## [Szállítási kalkulátor](transportation/transportation-management-engines.md)
# Raktárkezelés
## Beállítás 
### [Munka ellenőrzése munkasablonok és helyutasítások használatával](warehousing/control-warehouse-location-directives.md)
### [Raktári dolgozók kezelése](warehousing/manage-warehouse-workers.md)
### [Elrendezés beállítása](warehousing/warehouse-configuration.md)
### [Raktári munkairányelvek](warehousing/warehouse-work-policies.md)
### [Mértékegység és rakodási irányelvek](warehousing/unit-measure-stocking-policies.md)
## Kitárolás és csomagolás
### [Csomagolóanyagok és díjak](warehousing/pack-materials-packing-material-fees.md)
## Készletszámlálás
### [Készletzárolás](inventory/inventory-blocking.md)
### [Ciklikus leltározás](warehousing/cycle-counting.md)
### [Készletnapló](inventory/inventory-journals.md)
### [Készlethely](inventory/inventory-locations.md)
### [Készlet állapota](inventory/inventory-statuses.md)
### [Készletcímke számlálása](inventory/inventory-tag-counting.md)
## Tárolóra bontás 
## Feltöltés
### [Feltöltés](warehousing/replenishment.md)
## Mobileszközök
### [Mezőnevek konfigurálása a raktározási alkalmazásban](warehousing/configure-app-field-names-priorities-warehouse.md)
### [Mobileszközök beállítása raktári munkához](warehousing/configure-mobile-devices-warehouse.md)
### [Raktári mobileszközportál (WMDP)](warehousing/warehouse-mobile-devices-portal.md)
### [Raktári mobileszköz megjelenítési beállításai](warehousing/change-warehouse-mobile-device-displays.md)