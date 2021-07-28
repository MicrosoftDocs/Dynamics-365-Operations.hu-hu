---
title: Lépésikonok és -címek hozzárendelése a Warehouse Management mobilalkalmazáshoz
description: Ez a témakör azt ismerteti, hogyan lehet lépésikonokat és -címeket hozzárendelni a Warehouse Management mobilalkalmazás új vagy testre szabott feladatfolyamataihoz.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a74847b50512d2f712e5a9a5125e520afc732591
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344495"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Lépésikonok és -címek hozzárendelése a Warehouse Management mobilalkalmazáshoz

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet lépésikonokat és lépéscímeket hozzárendelni a Warehouse Management mobilalkalmazás új vagy testre szabott feladatfolyamataihoz.

A következő ábrákon az látható, hogyan jelennek meg a lépésikonok és -címek a Warehouse Management mobilalkalmazásban.

![Példa lépésikonra és lépéscímre a Warehouse Management mobilalkalmazásban.](media/step-icon-example.png "Példa lépésikonra és lépéscímre a Warehouse Management mobilalkalmazásban")

## <a name="turn-on-this-feature-in-your-system"></a>A funkció bekapcsolása a rendszerben

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításait a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkciónév:** *Felhasználói beállítások, ikonok és lépéscímek az új raktári alkalmazáshoz*

## <a name="standard-step-ids-classes-and-icons"></a>Szabványos lépések azonosítói, osztályai és ikonjai

Egy feladatfolyamat mindegyik lépését egy lépésazonosító azonosítja, és mindegyik lépésazonosítóhoz egy adott lépésosztály tartozik. A lépésikon és -cím minden lépésosztályban meg van határozva.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>Lépésazonosítók és lépésosztályok

A következő táblázatban az aktuálisan elérhető összes lépésazonosító és a hozzá tartozó lépésosztály látható. Az elsődleges beviteli mező vezérlőneve használatos lépésazonosítóként.

A lépésazonosítók és -osztályok használatát bemutató példára vonatkozóan tekintse meg a `WHSMobileAppStepInfoBuilder.stepId()` metódus implementációját a cikk későbbi részében: [Példa: Lépésikonok és -címek hozzárendelése egyéni folyamatokhoz](#example).

| Lépésazonosító | Lépés osztálya |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Fuvarozó | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Visszaigazolás | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| BRszám | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Hatóanyag-tartalom | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Eltárolás | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Mennyiség | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Betűvastagság | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>Elérhető lépésikonok

A rendszer standard lépésikonok gyűjteményét tartalmazza, amelyeket egyéni lépésekhez is lehet használni. Jelenleg nem lehet feltölteni egyéni ikonokat a lépésekhez. Ez azt jelenti, hogy mindig ki kell választania a standard lépésikonok valamelyikét.

A következő táblázatban megtekintheti az aktuálisan elérhető összes szabványos lépésikont és az ikon nevét.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="A lépésikonok"><br>Névjegy</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Azonosítótábla vagy cikk lépésikonjának hozzáadása"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Kötegrendelkezés lépésikon"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Szolgáltató lépésikon"><br>Fuvarozó</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Tényleges súly címkéjének lépésikon"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Tényleges súly címkéjével megjelölt súly lépésikon"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Ellenőrző számjegy lépésikon"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Azonosító beadása vagy kivétele lépésikon"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Gyermek-azonosítótábla lépésikon"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Fürtazonosító lépésikon"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Fürtpozíció lépésikon"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Konfigurációazonosító lépésikon"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Konfigurált mező lépésikon"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Megerősítés vagy azonosítótábla lépésikon"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Konszolidálás az azonosítótábla azonosítójából lépésikon"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Konszolidálás az azonosítótábla azonosítójába lépésikon"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Tárolótípus lépésikon"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Leltár lépésikon"><br>Leltár</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Leltározási okkód lépésikon"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Származási ország kódjának lépésikon"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Intézkedés lépésikon"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Kész lépésikon"><br>Kész</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Járművezető bejelentkezésének megerősítése lépésikon"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Járművezető bejelentkezésének azonosítója lépésikon"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Járművezető kijelentkezésének azonosítója lépésikon"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Lejárati dátum lépésikon"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Mező lépésikon"><br>Mező</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Kötegrendelkezésből lépésikon"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Készletállapotból lépésikon"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Azonosítóattribútum lépésikon"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Azonosító kötegazonosítója lépésikon"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Készlet színazonosítója lépésikon"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Készlet helye lépésikon"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Készlet sorozatazonosítója lépésikon"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Készlet méretazonosítója lépésikon"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Készlet állapotazonosítója lépésikon"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Készlet stílusazonosítója lépésikon"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Készlet verzióazonosítója lépésikon"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Cikkazonosító lépésikon"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="ITM tárolóazonosító lépésikon"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="ITM szállítmányazonosító lépésikon"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Kanbankártya-azonosító lépésikon"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Kanban vagy kártyaazonosító lépésikon"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Azonosítótábla azonosítója lépésikon"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Rakományazonosító lépésikon"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Hely azonosítótáblájának helye lépésikon"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Hely vagy azonosítótábla lépésikon"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Hely vagy azonosítótábla ellenőrzése lépésikon"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Hely vagy azonosítótábla innen lépésikon"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Hely vagy azonosítótábla ide lépésikon"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Hosszú folyamat befejeződött lépésikon"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Azonosítótábla szünet, szülő azonosítótábla lépésikon"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Tárolóazonosító egyesítése lépésikon"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Vegyes azonosítótábla sorszáma lépésikon"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Kimenő súly lépésikon"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Tulajdonos lépésikon"><br>Tulajdonos</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Szülő-azonosítótábla lépésikon"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Erősítse meg lépésikon"><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Beszerzési rendelés sorszáma lépésikon"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Beszerzési rendelés száma lépésikon"><br>BRszám</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Pozíció tele lépésikon"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Tartalom lépésikon"><br>Hatóanyag-tartalom</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Nyomtató neve lépésikon"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Gyártási azonosító lépésikon"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Termék visszaigazolása lépésikon"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Eltárolás lépésikon"><br>Eltárolás</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Betárolási fürtazonosító lépésikon"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Mennyiség lépésikon"><br>Mennyiség</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Mennyiség módosítása lépésikon"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Mennyiség kevés lépésikon"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Felhasználandó mennyiség lépésikon"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Elhelyezendő mennyiség lépésikon"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Leselejtezendő mennyiség lépésikon"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Mennyiség megerősítése lépésikon"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Befejezettként jelentett feladat lépésikon"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Fogadási hely azonosítója lépésikon"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Tárolóazonosító eltávolítása lépésikon"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="RMA-szám lépésikonja"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Rendelés kiválasztása lépésikon"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Rövid ok kiválasztása lépésikon"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Pozícióazonosító rendezése lépésikon"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Cél azonosítótábla azonosítója lépésikon"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Sorszámba lépésikon"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Helyre lépésikon"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Számba lépésikon"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Raktárba lépésikon"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Szállítás rakományazonosítója lépésikon"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Szállító kötegazonosítója lépésikon"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Hullám címkeazonosítója lépésikon"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Hullám címkemennyisége lépésikon"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Súly lépésikon"><br>Betűvastagság</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Felhasználandó súly lépésikon"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="WHS-korrekció típusa lépésikon"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="WHS-bevételezési kivétel lépésikonja"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="WMS-helyazonosító lépésikon"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Munkaazonosító lépésikon"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Visszavonandó munkaazonosító lépésikon"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Munka szonosítótáblájának azonosítója lépésikon"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Munka szonosítótáblájának azonosítójához tartozó betárolási fürt lépésikon"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Munkakészlet azonosítója lépésikon"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Zónaazonosító lépésikon"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>Példa: Lépésikonok és -címek hozzárendelése egyéni folyamatokhoz

Az alábbi példa bemutatja, hogyan állíthatók be lépésikonok és -címek egyéni feladatfolyamathoz. Az eset olyan egyéni feladatfolyamat példájára épül fel, amely a következő blogbejegyzésben részletesen is elérhető és áttekinthető: [A Warehousing mobilalkalmazás testreszabása](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app). A feladatfolyamat a következő módon működik:

1. Az alkalmazás megjelenít egy olyan lapot, amely azt kéri a dolgozót, hogy adjon meg tárolóazonosítót (például vonalkód beolvasásával).
1. Ha a tároló azonosítója érvényes, akkor az alkalmazás egy olyan új oldalt nyit meg, amely a súly megadására kéri a dolgozót. (Ha a tárolóazonosító nem érvényes, a dolgozó az első oldalra kerül vissza.)
1. Amikor a dolgozó érvényes súlyt ír be, a rendszer eltárolja a súlyt, és visszairányítja az első oldalra a dolgozót.

Ez a feladatfolyamat a következő ábrán látható.

![Feladatfolyamat ábrája.](media/step-icons-example-task-flow.png "Feladatfolyamat ábrája")

### <a name="create-a-step-class-for-the-container-input-page"></a>Lépésosztály létrehozása a tároló beviteli oldalához

A tároló beviteli oldalán a dolgozó beolvashatja vagy beírhatja a tároló azonosítóját.

![Tároló beviteli oldala.](media/step-icons-example-container-input.png "Tároló beviteli oldala")

A tároló beviteli oldalán a beviteli mező vezérlőneve `ContainerId`. Mivel ez a vezérlőnév nem szerepel a [lépésazonosítók listájában](#step-ids-classes), nem található rajta alapuló lépés. Ezért létre kell hoznia egy olyan lépésosztályt, amely a lépést képviseli. Íme, egy példa.

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

A lépésikon azonosítója a `defaultStepIcon` osztálytagban, a lépés címe pedig a `defaultStepTitle` osztálytagban van tárolva.

Lépésikon hozzárendeléséhez állítsa be a témakör korábbi részén, az [Elérhető lépésikonok](#step-icons) szakaszban lévő ikonok valamelyikére a `defaultStepIcon` tagot.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>Standard vagy egyéni lépésikon és -cím használata a súly beviteléhez

A súlybeviteli oldalon a dolgozó súlyt adhat meg.

![Súlybeviteli oldal.](media/step-icons-example-weight-input.png "Súlybeviteli oldal")

A súlybeviteli oldalon a beviteli mező vezérlőneve `Weight`, amely szerepel a [lépésazonosítók listájában](#step-ids-classes). Ezért ha a `WHSMobileAppStepWeight` osztályban meghatározott lépésikon és -cím elfogadható Önnek, akkor ennél a lépésnél semmit nem kell módosítania.

Ha azonban másik ikont vagy címet szeretne használni ehhez a lépéshez, felülbírálhatja a `stepId()` vagy a `stepInfo()` metódust a készítő osztályában. Minden feladatfolyamatnak saját lépésinformáció-készítője van.

#### <a name="override-the-stepid-method"></a>A stepId() metódus felülbírálása

A következő példa arra mutat módot, hogy a `stepId()` metódus felülbírálásával módosíthatók a szerkesztőosztályok.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

Ezután létre kell hoznia egy lépésosztályt a `NewWeight` lépéshez. A kódnak hasonlítania kell a témakörben korábban bemutatott `ContainerId` példa kódjához.

#### <a name="override-the-stepinfo-method"></a>A stepInfo() metódus felülbírálása

A következő példa arra mutat módot, hogy a `stepInfo()` metódus felülbírálásával módosíthatók a szerkesztőosztályok.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

Ezt követően létrehoz egy `WHSMobileAppStepInfo` objektumot, és közvetlenül beállítja az ikont és/vagy a címet.

## <a name="additional-resources"></a>További erőforrások

- [A Raktárkezelés mobilalkalmazás telepítése és csatlakoztatása](install-configure-warehouse-management-app.md)
- [Mobileszköz felhasználói beállításai](mobile-device-user-settings.md)
