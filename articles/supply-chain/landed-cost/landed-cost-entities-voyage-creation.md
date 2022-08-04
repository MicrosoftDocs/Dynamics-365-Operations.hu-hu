---
title: Útlétrehozás entitásai
description: Ez a cikk az hajóút-létrehozási adatentitásokkal kapcsolatban tartalmaz tájékoztatást, amelyek a munkaút létrehozásához szükséges adatentitásokat csoportosítják.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 6234dfa61a5859e2ecaca75594c69c49ba326629
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/15/2022
ms.locfileid: "9167671"
---
# <a name="voyage-creation-entities"></a>Útlétrehozás entitásai

[!include [banner](../includes/banner.md)]

Az út-létrehozási adatentitások csoportosítják a munkaút létrehozásához szükséges adatentitásokat. Ön vagy a szállítmányozója ezeket az adatentitásokat használhatja hajóút, szállítási tároló, levél és hajóútsorrekordok létrehozására, amelyek a meglévő beszerzői rendelésre vagy átszállítási rendelési sorokra hivatkoznak.

## <a name="voyages-itmtableentity"></a>Hajóút (ITMTableEntity)

Az út a bejövő áruk utazását képviseli, és a partra áras költség legmagasabb szintű költségterületeként szolgál. Fejlécszintű információkat tartalmaz, amelyek a hajóval, a származási kikötővel és a célkikötővel kapcsolatosak. Ezt a funkciót az entitás támogatja `ITMTableEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Szállítás módja | ITMTable.DlvModeId | Nvarchar(10) | Nem | Nem |
| Ügynök tanácsa szerint | ITMTable.ITMBrokerAdvised | Dátum és idő | Nem | Nem |
| Vevői találkozó | ITMTable.ITMCustomerAppointment | Dátum és idő | Nem | Nem |
| Kiszállítva a raktárba | ITMTable.ITMDelAtWare raktár | Dátum és idő | Nem | Nem |
| Szállítási utasítások | ITMTable.ITMDeliveryInstructions | Dátum és idő | Nem | Nem |
| Indulás dátuma | ITMTable.ITMDepartureDate | Dátum és idő | Nem | Nem |
| Kiadott áruk | ITMTable.ITMGoodsReleased | Dátum és idő | Nem | Nem |
| Helyi szállítás dátuma | ITMTable.ITMLocalTransportDate | Dátum és idő | Nem | Nem |
| Helyi szállítás időpontja | ITMTable.ITMLocalTransportTime | Int | Nem | Nem |
| Eredeti fuvarlevél elküldve | ITMTable.ITMOriginalBOLSebt | Dátum és idő | Nem | Nem |
| Az eredeti dokumentumok beérkeztek | ITMTable.ITMOriginalDocsReceived | Dátum és idő | Nem | Nem |
| Beszerzési rendelés állapota | ITMTable.ITMPurchStatus | Int | Nem | Nem |
| Ellenőrzési dátum | ITMTable.ITMVerificationDate | Dátum és idő | Nem | Nem |
| Vámügyi bejegyzés azonosítója | ITMTable.ShipCustomsEntryId | Nvarchar(20) | Nem | Nem |
| Szállítási dátum | ITMTable.ShipDate | Dátum és idő | Nem | Nem |
| Leírás | ITMTable.ShipDescription | Nvarchar(60) | Nem | Nem |
| Dokumentumok bevételezve | ITMTable.ShipDocReceived | Int | Nem | Nem |
| Becsült szállítási dátum | ITMTable.ShipEstDlvDate | Dátum és idő | Nem | Nem |
| A becsült érkezési időpont a szállítási kikötőnél | ITMTable.ShipEstPortDate | Dátum és idő | Nem | Nem |
| Kiindulási kikötő | ITMTable.ShipFromPort | Nvarchar(20) | Nem | Nem |
| Ház légi úton/fuvarlevélen | ITMTable.ShipHAWB | Nvarchar(20) | Nem | Nem |
| Út | ITMTable.ShipId | Nvarchar(20) | **Igen** | **Igen** |
| Foglalási hivatkozás | ITMTable.ShipIdExternal | Nvarchar(20) | Nem | Nem |
| Utazássablon | ITMTable.ShipJouroidId | Nvarchar(20) | Nem | Nem |
| Helyi fuvarozó | ITMTable.ShipLocalForwarder | Nvarchar(20) | Nem | Nem |
| Fő légi út/fuvarlevél | ITMTable.ShipMMUSB | Nvarchar(20) | Nem | Nem |
| Mértékegység | ITMTable.ShipMeasurement | Numerikus (32, 6) | Nem | Nem |
| Mértékegység | ITMTable.ShipMeasurementUnit | Int | Nem | Nem |
| Raklapok száma | ITMTable.ShipNoOfPallets | Int | Nem | Nem |
| Függőben lévő út | ITMTable.ShipPending | Int | Nem | Nem |
| Megjegyzések | ITMTable.ShipRemarks | Nvarchar(MAX) | Nem | Nem |
| Bérelhető | ITMTable.ShipRental | Int | Nem | Nem |
| Út állapota | ITMTable.ShipStatusId | Nvarchar(20) | Nem | Nem |
| Számmal szám | ITMTable.ShipTallyInNumber | Nvarchar(20) | Nem | Nem |
| Célkikötő | ITMTable.ShipToPort | Nvarchar(20) | Nem | Nem |
| Értékelés dátuma | ITMTable.ShipValuationDate | Dátum és idő | Nem | Nem |
| Szállítmányozási vállalat | ITMTable.ShipVendAccount | Nvarchar(20) | Nem | Nem |
| Hajó | ITMTable.ShipVesselId | Nvarchar(20) | Nem | **Igen** |
| Külső útazonosító | ITMTable.ShipVoyage | Nvarchar(20) | Nem | Nem |

### <a name="number-sequences-for-voyages"></a>Hajóút számsorozatai

Az hajóút megosztott számsorozata szabályozza az hajóút-számozások foglalását.

Az adatentitásnak **hajóút**-azonosítóként (`ShipId` Hajóút azonosítója) értékként átadott érték egy létező rekord azonosítására használható frissítésre. Ha a rekord nem létezik, akkor a viselkedés attól függ, hogy a hozzárendelt számsorozat lehetővé teszi-e a manuális bevitelt:

- Ha a manuális bevitel engedélyezve van, akkor egy új rekord jön létre, amely az átadott értéket használja.
- Ha a manuális bevitel nincs engedélyezve, akkor a rendszer az átadott érték helyett a hozzárendelt számsorozat következő számát használja.

Az importálási munkamenet során a program megtartja az útazonosítóként importált helyőrző értéket. Ez a viselkedés gondoskodik arról, hogy a helyőrzőre hivatkozó szállítási tárolók és hajóútsorok bekerülnek az hajóútba, és hogy a számsorozatból származó értéket tükrözzék.

### <a name="automatic-cost-transactions"></a>Automatikus költségtranzakciók

Az automatikus költségek a **Microsoft** Dynamics 365 Supply Chain Management Automatikus költségek lapja alapján hozzáadható hajóúthoz (**Partra \> kerülés költségszámításának automatikus \> költségei**). Az automatikus költségek rekordjai a Partra költségeket támogató minden költségterülethez külön költségtranzakció-adatentitások használatával is létre lehet hozva.

Az ellátásilánc-kezelésben beállított automatikus költségek az hajóútra vonatkoznak, amikor hajóútsort hoznak létre. Amíg a fejlécrekord soradatokat nem társít, nem lesznek látható költségek a rekordon.

## <a name="shipping-containers-itmcontainersentity"></a>Szállítási tárolók (ITMContainersEntity)

A szállítási tároló olyan fizikai tároló, amelybe árukat szállít. Ez a fizikai tároló lehet egy fuvartároló a óceáni fuvarozás számára, vagy egy raklap a légi szállításhoz. A szállítási tároló fejléc szintű információkat tartalmaz, amelyek a szállítási tároló azonosítójával, pecsétszámával és a szállítási tároló típusával kapcsolatosak. (A szállítási tároló típusa dimenzióadatokat tartalmaz.) Ezt a funkciót az entitás támogatja `ITMContainersEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Indulás dátuma | ITMContainers.ITMDepartureDate | Dátum és idő | Nem | Nem |
| Helyi szállítás dátuma | ITMContainers.ITMLocalTransportDate | Dátum és idő | Nem | Nem |
| Helyi szállítás időpontja | ITMContainers.ITMLocalTransportTime | Int | Nem | Nem |
| Eredeti út | ITMContainers.OrigShipId | Nvarchar(20) | Nem | Nem |
| Tényleges súly | ITMContainers.ShipActualWeight | Numerikus (32, 6) | Nem | Nem |
| Ügynök tanácsa szerint | ITMContainers.ShipBrokerAdvised | Dátum és idő | Nem | Nem |
| Szállítási konténer | ITMContainers.ShipContainerId | Nvarchar(20) | **Igen** | **Igen** |
| Szállítási konténer típusa | ITMContainers.ShipContainerTypeId | Nvarchar(20) | Nem | Nem |
| Egységtípus | ITMContainers.ShipContainerUnitTypeId | Nvarchar(10) | Nem | Nem |
| Átalakítva bérelhető típusúvá | ITMContainers.ShipConvertedToRental | Int | Nem | Nem |
| Vevői találkozó | ITMContainers.ShipCustomerAppointment | Dátum és idő | Nem | Nem |
| Szállítási dátum | ITMContainers.ShipDate | Dátum és idő | Nem | Nem |
| Kiszállítva a raktárba | ITMContainers.ShipDelAtWare raktár | Dátum és idő | Nem | Nem |
| Szállítási utasítások | ITMContainers.ShipDeliveryInstructions | Dátum és idő | Nem | Nem |
| Vizsgálati tanúsítvány alkalmazásának dátuma | ITMContainers.ShipECAppliedDate | Dátum és idő | Nem | Nem |
| Vizsgálati tanúsítvány lejáratának dátuma | ITMContainers.ShipECExpiryDate | Dátum és idő | Nem | Nem |
| Vizsgálati tanúsítvány száma | ITMContainers.ShipECNum | Nvarchar(20) | Nem | Nem |
| Vizsgálati tanúsítvány beérkezésének dátuma | ITMContainers.ShipECReceivedDate | Dátum és idő | Nem | Nem |
| Becsült szállítási dátum | ITMContainers.ShipEstDlvDate | Dátum és idő | Nem | Nem |
| A becsült érkezési időpont a szállítási kikötőnél | ITMContainers.ShipEstPortDate | Dátum és idő | Nem | Nem |
| Várható berakodási dátum | ITMContainers.ShipExpectedLoadingDate | Dátum és idő | Nem | Nem |
| Kiindulási kikötő | ITMContainers.ShipFromPort | Nvarchar(20) | Nem | Nem |
| Áruk leírása | ITMContainers.ShipGoodsDesc | Nvarchar(60) | Nem | Nem |
| Kiadott áruk | ITMContainers.ShipGoodsReleased | Dátum és idő | Nem | Nem |
| GPS-nyomkövető egysége | ITMContainers.ShipGPSUnit | Nvarchar(30) | Nem | Nem |
| Ház légi úton/fuvarlevélen | ITMContainers.ShipHAWB | Nvarchar(20) | Nem | Nem |
| Út | ITMContainers.ShipId | Nvarchar(20) | **Igen** | **Igen** |
| Utazássablon | ITMContainers.ShipJouroidId | Nvarchar(20) | Nem | Nem |
| Helyi fuvarozó | ITMContainers.ShipLocalForwarder | Nvarchar(20) | Nem | Nem |
| Mértékegység | ITMContainers.ShipMeasurement | Numerikus (32, 6) | Nem | Nem |
| Mértékegység | ITMContainers.ShipMeasurementUnit | Int | Nem | Nem |
| Kartondobozok száma | ITMContainers.ShipNoOfCartons | Numerikus (32, 6) | Nem | Nem |
| Eredeti fuvarlevél elküldve | ITMContainers.ShipOriginalBOLSebt | Dátum és idő | Nem | Nem |
| Az eredeti dokumentumok beérkeztek | ITMContainers.ShipOriginalDocsReceived | Dátum és idő | Nem | Nem |
| Saját pecsét száma | ITMContainers.ShipOurSealNum | Nvarchar(20) | Nem | Nem |
| Felhasználva | ITMContainers.ShipPendingUsed | Int | Nem | Nem |
| Beszerzési rendelés állapota | ITMContainers.ShipPurchStatus | Int | Nem | Nem |
| Hűtés típusa | ITMContainers.ShipRefrigerationTypeId | Nvarchar(10) | Nem | Nem |
| Megjegyzések | ITMContainers.ShipRemarks | Nvarchar(MAX) | Nem | Nem |
| Bérelhető | ITMContainers.ShipRental | Int | Nem | Nem |
| Visszaküldhető | ITMContainers.ShipReturnable | Int | Nem | Nem |
| Út állapota | ITMContainers.ShipStatusId | Nvarchar(20) | Nem | Nem |
| Szállítmányozási vállalat pecsétjének száma | ITMContainers.ShipTheirSealNum | Nvarchar(20) | Nem | Nem |
| Célkikötő | ITMContainers.ShipToPort | Nvarchar(20) | Nem | Nem |
| Ellenőrzési dátum | ITMContainers.ShipVerificationDate | Dátum és idő | Nem | Nem |
| Hajó | ITMContainers.ShipVesselId | Nvarchar(20) | Nem | **Igen** |

### <a name="voyage-id-validation"></a>Hajóút-azonosító ellenőrzése

A szállítási tároló azonosítója nincs számsorozat által szabályozva. Egyedi, csak abban az út környezetében, amely az út során használatos.

Ha a szállítási tároló entitását (`ITMContainersEntity`) a hajóút entitástól függetlenül használják`ITMTableEntity`, **akkor a Hajóút** azonosítója (`ShipId`) értéknek meg kell egyeznie a hajóút táblájának egy meglévő rekordjával. Ellenkező esetben az importálás sikertelen lesz.

Ha a szállítási tároló entitását (`ITMContainersEntity`) és az hajó útentitását (`ITMTableEntity`) ugyanannak az importálási munkamenetnek a részeként használják, akkor az útentitásnak meg kell előznie a szállítási tároló létrehozását. Ellenkező esetben **nem lehet** sikeres módon érvényesíteni a Hajóút azonosítója (`ShipId`) értéket. Ha helyőrző **értéket használ a Hajóút** azonosítója (`ShipId`) értékhez, akkor a társítás csak akkor jön létre, **ha** ugyanaz a helyőrző van használva a hajóazonosító (`ShipId`) értékként a szállítási tároló entitásban.

### <a name="other-field-validations"></a>Egyéb mezőellenőrzések

Az alábbi táblázat bemutatja a szállítási tároló tábla azon mezőit,`ITMContainers` amelyek a Partraszállítási költségbeállítási táblákkal szemben vannak ellenőrizve. Megjeleníti azokat a partraszállítási költségadat-entitásokat is, amelyek használatával a fuvarozó olvashatja a meglévő értékeket, és gondoskodhat arról, hogy érvényes értékek érkeziknek a környezetben.

| Az ITMContainers tábla mezője | Partrahozott költségadatok entitása |
|---|---|
| Szállítási konténer típusa | ITMShippingContainerTypeEntity |
| Áruk leírása | ITMGoodsDescriptionEntity |
| Hűtés típusa | ITMShippingContainerRefrigerationTypeEntity |

## <a name="folios-itmfolioentity"></a>Folios (ITMFocellEntity)

A számla a cikkeknek a szállítási tárolóban való csoportosítását jelenti vámáru-nyilatkozat céljából. A levél fejléc szintű információkat tartalmaz, amelyek a vámügynökről és az áruk leírásával kapcsolatosak. Ezt a funkciót az entitás támogatja `ITMFolioEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Ügynök tanácsa szerint | ITMFobroTable.ShipBrokerAdvised | Dátum és idő | Nem | Nem |
| Rakomány-ellenőrzési szám | ITMForollTable.ShipCargoControlNumber | Nvarchar(20) | Nem | Nem |
| Vevői találkozó | ITMFonicTable.ShipCustomerAppointment | Dátum és idő | Nem | Nem |
| Vámügynök | ITMFobroTable.ShipCustomsBroker | Nvarchar(20) | Nem | Nem |
| Vám azonosítója | ITMFobleTable.ShipCustomsId | Nvarchar(60) | Nem | Nem |
| Vállalat | ITMFodataTable.ShipDataArea | Nvarchar(4) | Nem | **Igen** |
| Kiszállítva a raktárba | ITMFo egyformaTable.ShipDelAtWarecelle | Dátum és idő | Nem | Nem |
| Szállítási utasítások | ITMFobilTable.ShipDeliveryInstructions | Dátum és idő | Nem | Nem |
| Dokumentumok bevételezve | ITMFodarTable.ShipDocReceived | Int | Nem | Nem |
| Becsült szállítási dátum | ITMFolvTable.ShipEstDlvDate | Dátum és idő | Nem | Nem |
| A becsült érkezési időpont a szállítási kikötőnél | ITMFoolásTable.ShipEstPortDate | Dátum és idő | Nem | Nem |
| Exportőr | ITMFobleTable.ShipExporterId | Nvarchar(20) | Nem | Nem |
| Név | ITMFocellTable.ShipExporterName | Nvarchar(60) | Nem | Nem |
| Ívlap dátuma | ITMFocellTable.ShipFo egyate | Dátum és idő | Nem | Nem |
| Ívlap | ITMFobleTable.ShipFoállításId | Nvarchar(20) | **Igen** | **Igen** |
| Kiindulási kikötő | ITMFodarTable.ShipFromPort | Nvarchar(20) | Nem | Nem |
| Áruk leírása | ITMFozarTable.ShipGoodsDesc | Nvarchar(60) | Nem | Nem |
| Kiadott áruk | ITMFomusTable.ShipGoodsReleased | Dátum és idő | Nem | Nem |
| Ház légi úton/fuvarlevélen | ITMFohaiTable.ShipHAWB | Nvarchar(20) | Nem | Nem |
| Út | ITMFobleTable.ShipId | Nvarchar(20) | Nem | **Igen** |
| Mértékegység | ITMFobilisTable.ShipMeasurement | Numerikus (32, 6) | Nem | Nem |
| Mértékegység | ITMFocellTable.ShipMeasurementUnit | Int | Nem | Nem |
| Kartondobozok száma | ITMFoínTable.ShipNoOfCartons | Numerikus (32, 6) | Nem | Nem |
| Eredeti fuvarlevél elküldve | ITMFooriTable.ShipOriginalBOLSebt | Dátum és idő | Nem | Nem |
| Az eredeti dokumentumok beérkeztek | ITMFooriTable.ShipOriginalDocsReceived | Dátum és idő | Nem | Nem |
| Beszerzési rendelés állapota | ITMFoandaTable.ShipPurchStatus | Int | Nem | Nem |
| Megjegyzések | ITMFodarTable.ShipRemarks | Nvarchar(MAX) | Nem | Nem |
| Út állapota | ITMFobleTable.ShipStatusId | Nvarchar(20) | Nem | Nem |
| Vámtarifakód | ITMForifTable.ShipTariffCode | Nvarchar(10) | Nem | Nem |
| Célkikötő | ITMFoolásTable.ShipToPort | Nvarchar(20) | Nem | Nem |
| Értékelés dátuma | ITMFomatikusTable.ShipValuationDate | Dátum és idő | Nem | Nem |
| Ellenőrzési dátum | ITMFoolásTable.ShipVerificationDate | Dátum és idő | Nem | Nem |
| Szállítói számla | ITMFochoTable.VendAccount | Nvarchar(20) | Nem | Nem |

### <a name="number-sequences-for-folios"></a>Számsorozatok a levelhez

A levélszámok számsorozata szabályozza a pénzügyi kiosztást.

Az adatentitásnak **a Levélazonosító (** Folio ID`FolioId`) értékként átadott érték segítségével azonosít egy létező rekordot frissítésre. Ha a rekord nem létezik, akkor a viselkedés attól függ, hogy a hozzárendelt számsorozat lehetővé teszi-e a manuális bevitelt:

- Ha a manuális bevitel engedélyezve van, akkor egy új rekord jön létre, amely az átadott értéket használja.
- Ha a manuális bevitel nincs engedélyezve, akkor a rendszer az átadott érték helyett a hozzárendelt számsorozat következő számát használja.

Az importálási munkamenet során a program megtartja a levélazonosítóként importált helyőrző értéket. Ez a viselkedés gondoskodik arról, hogy a helyőrzőre hivatkozó hajóútsorok megfelelően társítva vannak, és frissítésük a számsorozatból származó értéknek megfelelően frissüljön.

### <a name="field-validations"></a>Mezőellenőrzések

A **rendszer a**`ITMFolioTable` () levéltábla Áruleírás mezőjét az azonos nevű landolt költségbeállítási táblával szemben ellenőrzi. A szállítmányozó a `ITMGoodsDescriptionEntity` Partraszállítási költségadat-entitás használatával olvassa el a meglévő értékeket, és gondoskodjon arról, hogy az adott környezetben érvényes értékek érkeziknek.

## <a name="voyage-lines-for-purchase-orders-itmpurchaselineentity"></a>Beszerzési rendelések hajóútsorai (ITMPurchaseLineEntity)

Az hajóútsor egyetlen beszerzésirendelés-sort jelent, amely az útba tartozik. Ez a kapcsolat a **Beszerzési** **rendelés száma és a Beszerzési sor száma mezők alapján jött létre.** Az hajóútsor minden korábbi rekordra hivatkozik, amely az hajóúthoz, a szállítási tárolóhoz és a levélhez készült. Ezt a funkciót az entitás támogatja `ITMPurchaseLineEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Pénznem | ITMLine.CurrencyCode | Nvarchar(3) | Nem | Nem |
| Nettó összeg | ITMLine.LineAmountmST | Numerikus (32, 6) | Nem | Nem |
| Beszerzési sor száma | ITMLine.RefRecId | Numerikus (32, 6) | **Igen** | Nem |
| Szállítási konténer | ITMLine.ShipContainerId | Int | Nem | Nem |
| Vállalat | ITMLine.ShipDataArea | Nvarchar(20) | **Igen** | Nem |
| Bevallott mennyiség | ITMLine.ShipDeclaredQty | Nvarchar(4) | Nem | Nem |
| Ívlap | ITMLine.ShipFooidId | Numerikus (32, 6) | Nem | Nem |
| Út | ITMLine.ShipId | Nvarchar(20) | **Igen** | Nem |
| Cikkszám | ITMLine.ShipItemId | Nvarchar(20) | Nem | Nem |
| Mértékegység | ITMLine.ShipMeasurement | Nvarchar(20) | Nem | Nem |
| Mértékegység | ITMLine.ShipMeasurementUnit | Numerikus (32, 6) | Nem | Nem |
| Kartondobozok száma | ITMLine.ShipNoOfCartons | Int | Nem | Nem |
| Sorszám | ITMLine.ShipPosition | Numerikus (32, 6) | Nem | Nem |
| Mennyiség | ITMLine.ShipQty | Int | Nem | Nem |
| Beszerzési rendelés száma | ITMLine.TransRefId | Numerikus (32, 6) | **Igen** | Nem |
| Egység | ITMLine.UnitId | Int | Nem | Nem |
| Mennyiség | ITMLine.Volume | Nvarchar(10) | Nem | Nem |
| Betűvastagság | ITMLine.Weight | Numerikus (32, 6) | Nem | Nem |

## <a name="voyage-lines-for-transfer-orders-itmtransferlineentity"></a>Áthozott rendelések hajóútsorai (ITMTransferLineEntity)

Az hajóútsor egyetlen átrakodó rendeléssort jelent, amely az útba tartozik. Ez a kapcsolat az Átátviteli **rendelés száma és** Az **átsor száma mezők alapján jött létre**. Az hajóútsor minden korábbi rekordra hivatkozik, amely az hajóúthoz, a szállítási tárolóhoz és a levélhez készült. Ezt a funkciót az entitás támogatja `ITMTransferLineEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Pénznem | ITMLine.CurrencyCode | Nvarchar(3) | Nem | Nem |
| Nettó összeg | ITMLine.LineAmountmST | Numerikus (32, 6) | Nem | Nem |
| Szállítási konténer | ITMLine.ShipContainerId | Int | Nem | Nem |
| Vállalat | ITMLine.ShipDataArea | Nvarchar(20) | **Igen** | Nem |
| Bevallott mennyiség | ITMLine.ShipDeclaredQty | Nvarchar(4) | Nem | Nem |
| Ívlap | ITMLine.ShipFooidId | Numerikus (32, 6) | Nem | Nem |
| Út | ITMLine.ShipId | Nvarchar(20) | **Igen** | Nem |
| Cikkszám | ITMLine.ShipItemId | Nvarchar(20) | Nem | Nem |
| Mértékegység | ITMLine.ShipMeasurement | Nvarchar(20) | Nem | Nem |
| Mértékegység | ITMLine.ShipMeasurementUnit | Numerikus (32, 6) | Nem | Nem |
| Kartondobozok száma | ITMLine.ShipNoOfCartons | Int | Nem | Nem |
| Sorszám | ITMLine.ShipPosition | Numerikus (32, 6) | Nem | Nem |
| Mennyiség | ITMLine.ShipQty | Int | Nem | Nem |
| Átmozgatási sor száma | ITMLine.TransferLineNumber | Numerikus (32, 6) | **Igen** | Nem |
| Átmozgatási rendelés száma | ITMLine.TransRefId | Numerikus (32, 6) | **Igen** | Nem |
| Egység | ITMLine.UnitId | Int | Nem | Nem |
| Mennyiség | ITMLine.Volume | Nvarchar(10) | Nem | Nem |
| Betűvastagság | ITMLine.Weight | Numerikus (32, 6) | Nem | Nem |

### <a name="reference-table"></a>Hivatkozási tábla

Az hajóútsorok egy nyitott bejövő rendelési s sorhoz való társításon keresztül jön létre. Ez a sor lehet egy beszerzési rendelésen, vagy egy átrendelt rendelés fogadási tranzakciója. Az `RefTableId` hajóútsor táblája () mezője határozza`ITMLine` meg, hogy a sor melyik rendeléstípushoz kapcsolódik, ha a táblaszámra hivatkozik. Ha az adatokat létrehozó táblában konkrét táblaszámok vannak hivatkozva, akkor az entitások felosztása ezen értékek alapján történik.

A hivatkozási tábla (`RefTableId`) és a tranzakciótípus (`TransType`) értékeit implicit módon lehet kiválasztásában a Partrahozott költség beszerzési sor entitása vagy a Partra átvitele sor entitás.

### <a name="validation"></a>Ellenőrzés

Az hajóútsor közvetlenül hivatkozik egy hajóútrekordra, egy kiszállítási tároló rekordra és egy levélrekordra. Ha a beszerzési sor entitását (`ITMPurchaseLinesEntity`) vagy átátviteli sor entitását (`ITMPurchaseLinesEntity`) a hivatkozási rekordok létrehozásához használt entitásoktől függetlenül használják, **akkor a Hajóazonosító** (`ShipId`), a Szállítási **tároló (**) `ShipContainerId`**és a Folio** (`ShipFolioId`) értékeknek meg kell egyezniük a megfelelő táblák egy meglévő rekordjával. Ellenkező esetben az importálás sikertelen lesz.

Ha valamelyik sorentitás ugyanannak az importálási munkamenetnek a része, akkor ezeknek az entitásoknak meg kell előzniük egy hajóútsor létrehozását. Ellenkező esetben nem lehet megfelelően érvényesíteni az értékeket. Ha helyőrző értéket használ az hajóút vagy a levél száma, akkor a társítás csak akkor jön létre, ha ugyanaz a helyőrző van használva az hajóút vagy a levélszám számára az hajóút sorának entitásában.

Ha a beszerzési rendelés vagy az áthozott rendelési sor már hozzá van rendelve egy meglévő hajóútsorhoz, nem jön létre új hajóútsor. Ahhoz, hogy a rendeléssort új hajóúthoz rendelje hozzá, el kell távolítani az aktuális hajóútról.

### <a name="order-line-identification"></a>Rendeléssor azonosítója

Az hajóútsorok közvetlenül hivatkoznak a hivatkozási rekordazonosítóra (), a készletdimenzió-azonosítóra **(**) `RefRecId` és a készlettranzakció-azonosító **(**) értékeire. `InventDimId`**·**`InventTransId` Ezeknek az értékeknek már nem kell szerepelniük az adatentitás használata esetén. Ehelyett a rendelési sor számát kell szerepeletni. A rendelési sor száma és a rendelésszám együtt lehetővé teszi ezeknek a hivatkozási értékeknek az azonosítását.

### <a name="voyage-line-quantity"></a>Hajóút sorának mennyisége

Mivel egy hajóútsor közvetlenül kapcsolódik egy rendeléssorhoz, **az** entitás használatával megadott Mennyiség (`ShipQty`) értéknek egyeznie kell. Az ellenőrzés a beszerzésirendelés-sorban vagy az átátviteli sorban szereplő mennyiséggel szemben fut le. Ha az ellenőrzés sikertelen, a rekord nem lesz feldolgozva.

### <a name="calculated-fields"></a>Számított mezők

A **Súly és** **Térfogat számított** mezői az adatentitáson keresztül fogadott értékeket is elfogadják. Ha nem ad meg értékeket, akkor a rendszer értékeit használja a rendszer ezeknek a mezőknek a frissítéséhez, amennyiben elérhetők a rendszer értékei. A Partra ár esetén az értékek számítása a következőképpen történik:

- *·* = *Cikk*× *mennyiségének súlya*
- *Térfogat* = *mennyisége* × (*Cikk bruttó mélysége* × *Cikk bruttó magassága ×* *Cikk bruttó szélessége*)

## <a name="sequencing"></a>Szekvenálás

A táblák közötti függőségek miatt először az útrekordot kell létrehozni. Az hajóútsor csak az út, a kiszállítási tároló és alevelek létrehozása után lehet létrehozni.

Ahhoz, hogy ellenőrzési figyelmeztetések nélkül hajóút hozzon létre, a rendszernek a következő sorrendben kell feldolgoznia az entitásokat:

1. Hajóút (`ITMTableEntity`)
1. Szállítási tárolók (`ITMContainersEntity`)
1. Fóliók (`ITMFolioTableEntity`)
1. Hajóútsorok (vagy`ITMPurchaseLinesEntity``ITMTransferLinesEntity`)
