---
title: Szállítói számla entitásai
description: Ez a cikk a szállítói számlákban szereplő entitásokkal kapcsolatban tartalmaz tájékoztatást, amelyek lehetővé teszik a költségtípuskódok belső költségekhez vagy külső származtatott költségekhez történő konfigurálát.
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
ms.openlocfilehash: 171b383e1549babd76fd18e4932436a66aa62cc1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873927"
---
# <a name="vendor-invoice-entities"></a>Szállítói számla entitásai

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

A **Partra kerülve költségmodulban** a költségtípuskódok belső költségekhez vagy külső származtatott költségekhez konfigurálhatók. Ha a költség a vállalaton kívül van, a szolgáltatótól egy számlát vár a rendszer. Ez a számla olyan számlanaplóként van feldolgozva, amely hajóúthoz társítható, és a számla értéke az út egy vagy több költsége között elosztható.

A szállítói számla entitásai lehetővé teszik egy naplósor értékének felosztását egy hajóút egy vagy több olyan költségében, amelyek azonos költségtípuskóddal osztoznak.

A költség csak akkor osztható fel, ha létezik a számlanapló fejléce és a számlanapló sorai.

## <a name="vendor-voyage-cost-allocations-itmledgerjournalcostlinesvoyagesentity"></a>Szállítói hajóút költségfelosztásai (ITMLedgerJournalCostLinesVoyagesEntity)

A szállítói hajóút költségfelosztási adatai entitás lehetővé teszi egy szállítói számlasor felosztását az út költségterületére alkalmazott egy vagy több költség között. Ezt a funkciót az entitás támogatja `ITMLedgerJournalCostLinesVoyagesEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Felosztott összeg | ITMLedgerJournalCostLines.Amount | Numerikus (32, 6) | Nem | Nem |
| Költségtranzakció-sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Naplósor száma | ITMLedgerJournalCostLines.RefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Napló száma | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Igen** | Nem |
| Út | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Igen** | Nem |

## <a name="vendor-shipping-container-cost-allocations-itmledgerjournalcostlinescontainersentity"></a>Szállító szállítási tárolójának költségfelosztásai (ITMLedgerJournalCostLinesContainersEntity)

A szállítói szállítási tároló költségfelosztási adatainak entitása lehetővé teszi egy szállítói számlasor felosztását a szállítási tároló költségterületére alkalmazott egy vagy több költség között. Ezt a funkciót az entitás támogatja `ITMLedgerJournalCostLinesContainersEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Felosztott összeg | ITMLedgerJournalCostLines.Amount | Numerikus (32, 6) | Nem | Nem |
| Szállítási konténer | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Igen** | Nem |
| Költségtranzakció-sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Naplósor száma | ITMLedgerJournalCostLines.RefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Napló száma | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Igen** | Nem |
| Út | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Igen** | Nem |

## <a name="vendor-folio-cost-allocations-itmledgerjournalcostlinesfoliosentity"></a>Szállítói számla költségfelosztásai (ITMLedgerJournalCostLinesFocossEntity)

A szállítói számla költségfelosztási adatainak entitása lehetővé teszi egy szállítói számlasor felosztását a számla költségterületére alkalmazott egy vagy több költség között. Ezt a funkciót az entitás támogatja `ITMLedgerJournalCostLinesFoliosEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Felosztott összeg | ITMLedgerJournalCostLines.Amount | Numerikus (32, 6) | Nem | Nem |
| Költségtranzakció-sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Ívlap | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Igen** | Nem |
| Naplósor száma | ITMLedgerJournalCostLines.RefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Napló száma | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Igen** | Nem |

## <a name="vendor-purchase-order-cost-allocations-itmledgerjournalcostlinespurchtableentity"></a>Szállítói beszerzési rendelés költségfelosztásai (ITMLedgerJournalCostLinesPurchTableEntity)

A szállítói beszerzési rendelés költségfelosztási adatai entitás lehetővé teszi egy szállítói számlasor felosztását a beszerzési rendelés költségterületére alkalmazott egy vagy több költség között. Ezt a funkciót az entitás támogatja `ITMLedgerJournalCostLinesPurchTableEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Felosztott összeg | ITMLedgerJournalCostLines.Amount | Numerikus (32, 6) | Nem | Nem |
| Költségtranzakció-sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Naplósor száma | ITMLedgerJournalCostLines.RefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Napló száma | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Igen** | Nem |
| Beszerzési rendelés | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Igen** | Nem |

## <a name="vendor-item-cost-allocations-itmledgerjournalcostlinespurchlineentity"></a>Szállítói cikk költségfelosztásai (ITMLedgerJournalCostLinesPurchLineEntity)

A szállítói cikk-költségfelosztási adatok entitása lehetővé teszi a szállítói számlasor felosztását a cikk költségterületére alkalmazott egy vagy több költség között. A cikk költségterülete fedezi a beszerzésirendelés-sorban található költségeket. Ezt a funkciót az entitás támogatja `ITMLedgerJournalCostLinesPurchLineEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Felosztott összeg | ITMLedgerJournalCostLines.Amount | Numerikus (32, 6) | Nem | Nem |
| Költségtranzakció-sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Naplósor száma | ITMLedgerJournalCostLines.RefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Napló száma | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Igen** | Nem |
| Beszerzési rendelés | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Igen** | Nem |
| Beszerzésirendelés-sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |

## <a name="vendor-transfer-order-line-cost-allocations-itmledgerjournalcostlinestransferlineentity"></a>Szállítói átrendeléssor költségfelosztásai (ITMLedgerJournalCostLinesTransferLineEntity)

A szállítói átsor költségfelosztási adatainak entitása lehetővé teszi egy szállítói számlasor felosztását az átviteli sor költségterületére alkalmazott egy vagy több költség között. Ezt a funkciót az entitás támogatja `ITMLedgerJournalCostLinesTransferLineEntity`. Az alábbi táblázat felsorolja az entitást felező mezőket és megfeleltetéseket.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Felosztott összeg | ITMLedgerJournalCostLines.Amount | Numerikus (32, 6) | Nem | Nem |
| Költségtranzakció-sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Naplósor száma | ITMLedgerJournalCostLines.RefRecId | Numerikus (32, 16) | **Igen** | Nem |
| Napló száma | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Igen** | Nem |
| Átmozgatási rendelés | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Igen** | Nem |
| Átrendelt rendelési sor száma | ITMLedgerJournalCostLines.CostTransRefRecId | Numerikus (32, 16) | **Igen** | Nem |

### <a name="reference-table"></a>Hivatkozási tábla

Az hajóút költségsorai közvetlen kapcsolatban vannak egy költségtranzakció-rekordkal. Ez a rekord tartalmazza a hivatkozási **tábla azonosítójának** értékét. Ez az érték minden költségterületre (hajóút, konténer stb.) egyedi. Ha az adatentitások segítségével létrehozott adatokhoz meghatározott táblaszámra hivatkoznak, **akkor az entitások felosztása a hivatkozási tábla azonosító értékei alapján történik**.

A hivatkozási tábla (`RefTableId`) és a tranzakciótípus (`TransType`) értékeit implicit módon lehet kiválasztotta a Partra áras költség beszerzési sor vagy a Partra átvitele sor entitás közül.

## <a name="vendor-invoice-journal-lines-vendorinvoicejournallineentity"></a>Szállítói számla naplósorai (VendorInvoiceJournalLineEntity)

Ahhoz, hogy egy naplósor **értékét** felosztani egy vagy több költséghez a Földelt költségmodulban, a naplósort egy költségterülethez kell hozzárendelni. Ennek a funkciónak a **támogatása érdekében a Landed költségmodul** hozzáad néhány új mezőt a naplósorok táblájába (`LedgerJournalTrans`).

### <a name="fields-added-to-the-vendor-invoice-journal-line-entity"></a>A szállítói számlanaplósor entitáshoz hozzáadott mezők

Az alábbi táblázat felsorolja azokat a mezőket, amelyekhez **a Landed** költségmodul hozzáadja a szállítói számlanapló sor entitását (`VendorInvoiceJournalLineEntity`). Ezek a mezők lehetővé teszik a rendszer számára a naplósorok létrehozására és a költségek felosztását.

| Név | Hozzárendelés | Adattípus | Kulcs | Kötelező |
|---|---|---|---|---|
| Költségterület | LedgerJournalTrans.ITMCostArea | Int | Nem | Nem |
| Költségtípus kódja | LedgerJournalTrans.ITMCostTypeId | Nvarchar(20) | Nem | Nem |

### <a name="mainoffset-account"></a>Fő/ellenszámla

A Landed költségúthoz kapcsolódó számlanaplósor fő/ellenszámláját a költségtípus kódja határozza meg. Ha a költségtípus kódja szerepel a számlanapló sorában, az esettől függően a kód elszámolószámlája lesz a fő számla vagy az ellenszámla:

- **Egysoros** napló – ha meg van adva egy fő számla (más szóval a szállítói számla), és meg van adva egy költségtípus-kód, akkor az adott költségtípuskód elszámolószámla-értéke az ellenszámlán lesz megadva.
- **Többsoros** napló – ha nincs megadva fő számla, de meg van adva egy költségtípuskód, az adott költségtípuskód elszámolószámla-értéke kerül a fő számlára. A szállítónak jóváírt naplósor nem hivatkozik költségtípuskódra.

## <a name="sequencing"></a>Szekvenálás

A napló- és naplósorok táblái közötti függőségek miatt először az hajóútrekordot kell létrehozni. Az hajóútsorok csak az hajóút, a kiszállítási tároló és alevelek létrehozása után lehet létrehozni.

Hajóúti számla foglalásához a rendszernek a következő sorrendben kell feldolgoznia az entitásokat:

1. Számlanapló fejléce (`VendInvoiceJournalHeaderEntity`)
1. Számlanaplósor (`VendInvoiceJournalLineEntity`)
1. Partra árasztott költségfelosztások (`ITMLedgerJournalEntities`)
