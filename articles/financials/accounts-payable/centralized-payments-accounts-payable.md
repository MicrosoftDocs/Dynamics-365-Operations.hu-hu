---
title: Központosított kifizetések a Kötelezettségekhez
description: Olyan szervezetek, amelyek több jogi személyt tartalmaznak létrehozhatnak és kezelhetnek kifizetéseket, egyetlen, minden kifizetést kezelő jogi személy alkalmazásával. Ebből adódóan ugyanazon kifejezést nem lehet több jogi személyben megadni. A cikk néhány példát mutat be, amelyek a különböző helyzetekben felmerülő központosított kifizetések feladási módjait jelenítik meg.
author: abruer
manager: AnnBe
ms.date: 02/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41d94f4327268ef24388d97fc24804b650a84d57
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1507074"
---
# <a name="centralized-payments-for-accounts-payable"></a>Központosított kifizetések a Kötelezettségekhez

[!include [banner](../includes/banner.md)]

Olyan szervezetek, amelyek több jogi személyt tartalmaznak létrehozhatnak és kezelhetnek kifizetéseket, egyetlen, minden kifizetést kezelő jogi személy alkalmazásával. Ebből adódóan ugyanazon kifejezést nem lehet több jogi személyben megadni. A cikk néhány példát mutat be, amelyek a különböző helyzetekben felmerülő központosított kifizetések feladási módjait jelenítik meg.

Olyan szervezetek, amelyek több jogi személyt tartalmaznak létrehozhatnak és kezelhetnek kifizetéseket, egy jogi személy használatával, amely minden kifizetést kezel. Ebből adódóan ugyanazon kifejezést nem lehet több jogi személyben megadni. Továbbá a szervezet időt takarít meg, mivel a kifizetési folyamat hatékony.

Egy szervezet központosított kifizetéseiben több jogi személy létezik a műveletekhez és minden működő jogi személy kezeli a saját beszállítói számláit. A kifizetések minden működő jogi személyhez egyetlen jogi személy által jönnek létre, amely a kifizetés jogi személyeként ismert. A kiegyenlítési folyamat során mindkét irányban létrejönnek a vonatkozó esedékességi tranzakciók. Megadhatja, hogy a szervezet melyik jogi személye kap realizált nyereség vagy realizált veszteség tranzakciókat, és hogy a vállalatközi kifizetésekhez kapcsolódó készpénzfizetési-engedmény tranzakciók hogyan legyenek kezelve. A központosított kifizetési naplósoron a **Számlatípus** értékét Szállítóra kell állítani. Az **Ellenszámla típusa** Bank vagy Főkönyv kell legyen. A bankszámlának az aktuális vállalatban kell lennie. 

A következő példák bemutatják, hogyan kezeli a rendszer a feladást a különböző helyzetekben. Mindegyik példa a következő konfigurációból indul ki:

-   A jogi személyek a Gyár, Keleti gyár és Nyugati gyár. A kifizetések a Gyárból érkeznem.
-   A **Készpénzfizetési engedmény feladása** mező a **Vállalatközi könyvelés** lapon **A számlán szereplő jogi személy** elemre van állítva.
-   Az **Árfolyamnyereség- vagy -veszteség feladása** mező a **Vállalatközi könyvelés** lapon **A kifizetéshez megadott jogi személy** elemre van állítva.
-   A Babszem Kávézó nevű szállító minden jogi személyben szállítóként van beállítva. A szállítók a különböző jogi személyekből ugyanazon szállítóként vannak azonosítva, mivel ugyanazt a globális címjegyzék-azonosítót használják.

| Címtár-azonosító | Szállítói számla | Név          | Jogi személy  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Babszem Kávézó | Gyár      |
| 1050         | 100            | Babszem Kávézó | Keleti Gyár |
| 1050         | 3004           | Babszem Kávézó | Nyugati Gyár |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>1. példa: Másik jogi személyből érkező számla szállítói kifizetése
A Keleti Gyárnak van egy nyitott számlája a 100-as szállítói számla (a Babszem Kávézó) felé. A Gyár rögzít és felad egy kifizetést a 3004-es (Babszem Kávézó) szállítói számlára. A kifizetés kiegyenlítése a nyitott számlával történik.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>A Keleti Gyár feladja a számlát a 100-as szállítónak

| Számla                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Költség (Keleti Gyár)          | 600,00       |               |
| Kötelezettségek (Keleti Gyár) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Kifizetés generálása és feladása a Gyár 3004-es szállítójára

| Számla                     | Tartozik összeg | Követel összeg |
|-----------------------------|--------------|---------------|
| Kötelezettségek (Gyár) | 600,00       |               |
| Készpénz (Gyár)             |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                           | Tartozik összeg | Követel összeg |
|-----------------------------------|--------------|---------------|
| Esedékes a Keleti Gyártól (Gyár) | 600,00       |               |
| Kötelezettségek (Gyár)       |              | 600,00        |

**Keleti Gyár – feladás**

| Számla                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Kötelezettségek (Keleti Gyár) | 600,00       |               |
| Esedékes a Gyárnak (Keleti Gyár)  |              | 600,00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>2. példa: Egy másik jogi személy számlájának készpénzfizetési engedménnyel történő szállítói kifizetése
A Keleti Gyárnak van egy nyitott számlája a 100-as (Babszem Kávézó) szállító felé. A számlán 20,00 készpénzfizetési engedmény van. A Gyár rögzít és felad egy 580,00 összegű kifizetést a Gyár 3004-es szállítójára, amely a Babszem Kávézó. A kifizetés elszámolása a nyitott Keleti Gyár-számlákkal szemben történik. A készpénzfizetési engedményt feladja a rendszer a számla jogi személyének, a Keleti Gyárnak.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Számla feladása a Keleti Gyárban a Keleti Gyár 100-as szállítójára

| Számla                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Költség (Keleti Gyár)          | 600,00       |               |
| Kötelezettségek (Keleti Gyár) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Kifizetés generálása és feladása a Gyárban a Gyár 3004-es szállítójára

| Számla                     | Tartozik összeg | Követel összeg |
|-----------------------------|--------------|---------------|
| Kötelezettségek (Gyár) | 58000       |               |
| Készpénz (Gyár)             |              | 58000        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                           | Tartozik összeg | Követel összeg |
|-----------------------------------|--------------|---------------|
| Esedékes a Keleti Gyártól (Gyár) | 58000       |               |
| Kötelezettségek (Gyár)       |              | 58000        |

**Keleti Gyár – feladás**

| Számla                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Kötelezettségek (Keleti Gyár) | 58000       |               |
| Esedékes a Gyárnak (Keleti Gyár)  |              | 58000        |
| Kötelezettségek (Keleti Gyár) | 20,00        |               |
| Készpénzfizetési engedmény (Keleti Gyár)    |              | 20,00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>3. példa: Egy másik jogi személy számlájának árfolyamveszteséggel történő szállítói kifizetése
A Keleti Gyárnak van egy nyitott számlája a 100-as (Babszem Kávézó) szállító felé. A Gyár rögzít és felad egy kifizetést a Gyár 3004-es szállítójának, a Babszem Kávézónak. A kifizetés kiegyenlítése a Keleti Gyár nyitott számlájával történik. Egy árfolyam-veszteségi tranzakció generálódik az kiegyenlítési folyamat közben.

-   Az EUR-USD átváltási árfolyam a számladátumon: 1,2062
-   Az EUR-USD átváltási árfolyam a kifizetési dátumon: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>Számla feladása a Keleti Gyárban a Keleti Gyár 100-as szállítójára

| Számla                          | Tartozik összeg            | Követel összeg           |
|----------------------------------|-------------------------|-------------------------|
| Költség (Keleti Gyár)          | 600,00 EUR / 723,72 USD |                         |
| Kötelezettségek (Keleti Gyár) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>Kifizetés generálása és feladása a Gyárban a Gyár 3004-es szállítójára

| Számla                     | Tartozik összeg            | Követel összeg           |
|-----------------------------|-------------------------|-------------------------|
| Kötelezettségek (Gyár) | 600,00 EUR / 736,62 USD |                         |
| Készpénz (Gyár)             |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                           | Tartozik összeg            | Követel összeg           |
|-----------------------------------|-------------------------|-------------------------|
| Esedékes a Keleti Gyártól (Gyár) | 600,00 EUR / 736,62 USD |                         |
| Kötelezettségek (Gyár)       |                         | 600,00 EUR / 736,62 USD |
| Realizált veszteség (Gyár)          | 0,00 EUR / 12,90 USD    |                         |
| Esedékes a Keleti Gyártól (Gyár) |                         | 0,00 EUR / 12,90 USD    |

**Keleti Gyár – feladás**

| Számla                          | Tartozik összeg            | Követel összeg           |
|----------------------------------|-------------------------|-------------------------|
| Kötelezettségek (Keleti Gyár) | 600,00 EUR / 736,62 USD |                         |
| Esedékes a Gyárnak (Keleti Gyár)  |                         | 600,00 EUR / 736,62 USD |
| Esedékes a Gyárnak (Keleti Gyár)  | 0,00 EUR / 12,90 USD    |                         |
| Kötelezettségek (Keleti Gyár) |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>4. példa: Egy másik jogi személy számlájának készpénzfizetési engedménnyel és árfolyamveszteséggel történő szállítói kifizetése
A Keleti Gyárnak van egy nyitott számlája a 100-as (Babszem Kávézó) szállító felé. A számlán készpénzfizetési engedmény szerepel, valamint áfatranzakció jön létre. A Gyár felad egy kifizetést a Gyár 3004-es számú szállítójának, a Babszem Kávézónak. A kifizetés elszámolása a nyitott Keleti Gyár-számlával szemben történik. Egy árfolyam-veszteségi tranzakció generálódik az kiegyenlítési folyamat közben. A készpénzfizetési engedmény feladásra kerül a számla jogi személyéhez (Keleti Gyár), az árfolyamveszteség pedig feladásra kerül a kifizetés jogi személyéhez (Gyár).

-   Az EUR-USD átváltási árfolyam a számladátumon: 1,2062
-   Az EUR-USD átváltási árfolyam a kifizetési dátumon: 1,2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>A számlát feladja a program, és egy adótranzakciót generál a Keleti Gyárnál a 100-as vevőhöz.

| Számla                          | Tartozik összeg            | Követel összeg           |
|----------------------------------|-------------------------|-------------------------|
| Költség (Keleti Gyár)          | 564,07 EUR / 680,38 USD |                         |
| Áfa (Keleti Gyár)        | 35,93 EUR / 43,34 USD   |                         |
| Kötelezettségek (Keleti Gyár) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>Kifizetés generálása és feladása a Gyár 3004-es szállítójára

| Számla                     | Tartozik összeg            | Követel összeg           |
|-----------------------------|-------------------------|-------------------------|
| Kötelezettségek (Gyár) | 588,72 EUR / 722,77 USD |                         |
| Készpénz (Keleti Gyár)        |                         | 588,72 EUR / 722,77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                           | Tartozik összeg            | Követel összeg           |
|-----------------------------------|-------------------------|-------------------------|
| Esedékes a Keleti Gyártól (Gyár) | 588,72 EUR / 722,77 USD |                         |
| Kötelezettségek (Gyár)       |                         | 588,72 EUR / 722,77 USD |
| Realizált veszteség (Gyár)          | 0,00 EUR / 12,66 USD    |                         |
| Esedékes a Keleti Gyártól (Gyár) |                         | 0,00 EUR / 12,66 USD    |

**Keleti Gyár – feladás**

| Számla                          | Tartozik összeg            | Követel összeg           |
|----------------------------------|-------------------------|-------------------------|
| Kötelezettségek (Keleti Gyár) | 588,72 EUR / 722,77 USD |                         |
| Esedékes a Gyárnak (Keleti Gyár)  |                         | 588,72 EUR / 722,77 USD |
| Esedékes a Gyárnak (Keleti Gyár)   | 0,00 EUR / 12,66 USD    |                         |
| Kötelezettségek (Keleti Gyár) |                         | 0,00 EUR / 12,66 USD    |
| Kötelezettségek (Keleti Gyár) | 11,28 EUR / 13,61 USD   |                         |
| Készpénzfizetési engedmény (Keleti Gyár)    |                         | 11,28 EUR / 13,61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>5. példa: Szállítói jóváírás elsődleges kifizetéssel
A Gyár generál egy kifizetést 75,00-ről a 3004 szállítónak (Babszem Kávézó). A kifizetés elszámolása a Nyugati Gyár 3004-es szállítójának egy nyitott számlájával, és a Keleti Gyár 100-as szállítójának egy nyitott jóváírásával történik. A kifizetést a **Tranzakciók kiegyenlítése** képernyőn elsődleges kifizetésként jelölik meg.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Számla feladása a Nyugati Gyár 3004-es szállítójára

| Fiók                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Költség (Nyugati Gyár)          | 100,00       |               |
| Kötelezettségek (Nyugati gyár) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Jóváírás feladása a Keleti Gyár 100-as szállítójára

| Számla                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Kötelezettségek (Keleti Gyár) | 25,00        |               |
| Beszerzések visszáruja (Keleti Gyár) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Kifizetés feladása a Gyár 3004-es szállítójára

| Számla                     | Tartozik összeg | Követel összeg |
|-----------------------------|--------------|---------------|
| Kötelezettségek (Gyár) | 75,00        |               |
| Készpénz (Gyár)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>A Gyár kifizetésének elszámolása a Nyugati Gyár számlájával és a Keleti Gyár jóváírásával szemben

**Gyár – feladás**

| Számla                           | Tartozik összeg | Követel összeg |
|-----------------------------------|--------------|---------------|
| Kötelezettségek (Gyár)       | 25,00        |               |
| Esedékes a Keleti Gyárnak (Gyár)   |              | 25,00         |
| Esedékes a Nyugati Gyártól (Gyár) | 100,00       |               |
| Kötelezettségek (Gyár)       |              | 100,00        |

**Keleti Gyár – feladás**

| Számla                           | Tartozik összeg | Követel összeg |
|-----------------------------------|--------------|---------------|
| Esedékes a Gyártól (Keleti gyár) | 25,00        |               |
| Kötelezettségek (Keleti Gyár)  |              | 25,00         |

**Nyugati Gyár – feladás**

| Számla                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Kötelezettségek (Nyugati gyár) | 100,00       |               |
| Esedékes a Gyárnak (Nyugati Gyár)  |              | 100,00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>6. példa: Szállítói jóváírás elsődleges kifizetés nélkül
A Gyár generál egy kifizetést 75,00-ről a 3004 szállítónak (Babszem Kávézó). A kifizetés elszámolása a Nyugati Gyár 3004-es szállítójának egy nyitott számlájával, és a Keleti Gyár 100-as szállítójának egy nyitott jóváírásával történik. A kifizetést a **Tranzakciók kiegyenlítése** képernyőn nem jelölik meg elsődleges kifizetésként.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>Számla feladása a Nyugati Gyár 3004-es szállítójára

| Fiók                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Költség (Nyugati Gyár)          | 100,00       |               |
| Kötelezettségek (Nyugati gyár) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Jóváírás feladása a Keleti Gyár 100-as szállítójára

| Számla                          | Tartozik összeg | Követel összeg |
|----------------------------------|--------------|---------------|
| Kötelezettségek (Keleti Gyár) | 25,00        |               |
| Beszerzések visszáruja (Keleti Gyár) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>Kifizetés feladása a Gyár 3004-es szállítójára

| Számla                     | Tartozik összeg | Követel összeg |
|-----------------------------|--------------|---------------|
| Kötelezettségek (Gyár) | 75,00        |               |
| Készpénz (Gyár)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>A Gyár kifizetésének elszámolása a Nyugati Gyár számlájával és a Keleti Gyár jóváírásával szemben

**Gyár – feladás**

| Számla                           | Tartozik összeg | Követel összeg |
|-----------------------------------|--------------|---------------|
| Esedékes a Nyugati Gyártól (Gyár) | 75,00        |               |
| Kötelezettségek (Gyár)       |              | 75,00         |

**Keleti Gyár – feladás**

| Számla                                | Tartozik összeg | Követel összeg |
|----------------------------------------|--------------|---------------|
| Esedékes a Nyugati Gyártól (Keleti Gyár) | 25,00        |               |
| Kötelezettségek (Keleti Gyár)       |              | 25,00         |

**Nyugati Gyár – feladás**

| Számla                              | Tartozik összeg | Követel összeg |
|--------------------------------------|--------------|---------------|
| Kötelezettségek (Nyugati gyár)     | 75,00        |               |
| Esedékes a Gyárnak (Nyugati Gyár)      |              | 75,00         |
| Kötelezettségek (Nyugati gyár)     | 25,00        |               |
| Esedékes a Keleti Gyártól (Nyugati Gyár) |              | 25,00         |





