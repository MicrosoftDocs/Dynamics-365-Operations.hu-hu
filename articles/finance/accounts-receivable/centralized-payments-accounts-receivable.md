---
title: Kinnlevőségek központosított kifizetései
description: Olyan szervezetek, amelyek több jogi személyt tartalmaznak létrehozhatnak és kezelhetnek kifizetéseket, egyetlen, minden kifizetést kezelő jogi személy alkalmazásával. Ebből adódóan ugyanazt a tranzakciót nem kell több jogi személyhez megadni. A cikk néhány példát mutat be, amelyek a különböző helyzetekben felmerülő központosított kifizetések feladási módjait jelenítik meg.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 02/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 59942fadb0fb702c59c95f75359f1a3036e4668f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178152"
---
# <a name="centralized-payments-for-accounts-receivable"></a>Kinnlevőségek központosított kifizetései

[!include [banner](../includes/banner.md)]

Olyan szervezetek, amelyek több jogi személyt tartalmaznak létrehozhatnak és kezelhetnek kifizetéseket, egyetlen, minden kifizetést kezelő jogi személy alkalmazásával. Ebből adódóan ugyanazt a tranzakciót nem kell több jogi személyhez megadni. A cikk néhány példát mutat be, amelyek a különböző helyzetekben felmerülő központosított kifizetések feladási módjait jelenítik meg.

Olyan szervezetek, amelyek több jogi személyt tartalmaznak létrehozhatnak és kezelhetnek kifizetéseket, egy jogi személy használatával, amely minden kifizetést kezel. Ebből adódóan ugyanazt a tranzakciót nem kell több jogi személyhez megadni. Továbbá a szervezet időt takarít meg, mert a kifizetési javaslatok és elszámolások folyamatai és a nyílt és zárt tranzakciók szerkesztése a központosított kifizetésekhez rendszerezve vannak. 

Egy központosított kifizetésű szervezetben sok jogi személy létezik a műveletekhez, és minden működő jogi személy kezeli a saját kinnlevőségeire vonatkozó adatait. Minden működő jogi személy kifizetéseit egy jogi személy fogadja, ami a kifizetés jogi személyeként ismert. A kiegyenlítési folyamat során mindkét irányban létrejönnek a vonatkozó esedékességi tranzakciók. Megadhatja, hogy a szervezet melyik jogi személye kap realizált nyereség vagy veszteség tranzakciókat és hogy központosított kifizetéshez kapcsolódó készpénzfizetési engedmények tranzakciói hogyan vannak kezelve. A központosított kifizetési naplósoron a **Számlatípus** értékét Vevőre kell állítani. Az **Ellenszámla típusa** Bank vagy Főkönyv kell legyen. A bankszámlának az aktuális vállalatban kell lennie. 

A következő példák bemutatják, hogyan kezeli a rendszer a feladást a különböző helyzetekben. Mindegyik példa a következő konfigurációból indul ki:

-   A jogi személyek a Gyár, Keleti gyár és Nyugati gyár. A vevői kifizetések bekerülne a Gyárba.
-   A **Készpénzfizetési engedmény feladása** mező a **Vállalatközi könyvelés** lapon **A számlán szereplő jogi személy** elemre van állítva.
-   Az **Árfolyamnyereség- vagy -veszteség feladása** mező a **Vállalatközi könyvelés** lapon **A kifizetéshez megadott jogi személy** elemre van állítva.
-   A Hegyvidéki Kereskedők vevő vevőként van beállítva minden jogi személyhez. A vevők a különböző jogi személyekből ugyanazon vevőként vannak azonosítva, mivel ugyanazt a globális címjegyzék-azonosítót használják.

| Címjegyzék azonosítója | Vevői számla: | Név              | Jogi személy  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Hegyvidéki Kereskedők | Gyár      |
| 4050            | 4000             | Hegyvidéki Kereskedők | Keleti Gyár |
| 4050            | 10 000            | Hegyvidéki Kereskedők | Nyugati Gyár |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>1. példa: másik jogi személytől érkező számla vevői kifizetése
A Gyár 600,00 összegű kifizetést kap a Gyár 4000-es vevőkódjára (Hegyvidéki Kereskedők). A kifizetés a Keleti Gyár 4000-es vevőkódjához tartozó nyitott számlát egyenlít ki.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>A számla feladása a Keleti Gyárban a 4000-es vevőre

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Kinnlevőségek (Keleti Gyár) | 600,00       |               |
| Értékesítés (Keleti Gyár)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>A fizetés beérkezése és feladása a Gyár 4000-es vevőjére

| Számla                        | Tartozik összeg | Követel összeg |
|--------------------------------|--------------|---------------|
| Készpénz (Gyár)                | 600,00       |               |
| Kinnlevőségek (Gyár) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                         | Tartozik összeg | Követel összeg |
|---------------------------------|--------------|---------------|
| Kinnlevőségek (Gyár)  | 600,00       |               |
| Esedékes a Keleti Gyárnak (Gyár) |              | 600,00        |

**Keleti Gyár – feladás**

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Esedékes a Gyártól (Keleti gyár)   | 600,00       |               |
| Kinnlevőségek (Keleti Gyár) |              | 600,00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>2. példa: másik jogi személytől érkező, készpénzfizetési engedményt tartalmazó számla vevői kifizetése
A Gyár 580,00 összegű kifizetést kap a Gyár 4000-es vevőjére (Hegyvidéki Kereskedők). A Keleti Gyárnak van egy nyitott számlája a 4000-as vevővel szemben. A számlán 20,00 összegű készpénzfizetési engedmény szerepel. A kifizetés elszámolása a nyitott Keleti Gyár-számlákkal szemben történik. A készpénzfizetési engedményt feladja a rendszer a számla jogi személyének, a Keleti Gyárnak.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>A számla feladása a Keleti Gyárban a Keleti Gyár 4000-es vevőjére.

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Kinnlevőségek (Keleti Gyár) | 600,00       |               |
| Értékesítés (Keleti Gyár)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>A fizetés beérkezése és feladása a Gyárban a Gyár 4000-es vevőjére.

| Számla                        | Tartozik összeg | Követel összeg |
|--------------------------------|--------------|---------------|
| Készpénz (Gyár)                | 600,00       |               |
| Kinnlevőségek (Gyár) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                         | Tartozik összeg | Követel összeg |
|---------------------------------|--------------|---------------|
| Kinnlevőségek (Gyár)  | 580,00       |               |
| Esedékes a Keleti Gyárnak (Gyár) |              | 580,00        |

**Keleti Gyár – feladás**

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Esedékes a Gyártól (Keleti gyár)   | 580,00       |               |
| Kinnlevőségek (Keleti Gyár) |              | 580,00        |
| Készpénzfizetési engedmény (Keleti Gyár)       | 20,00        |               |
| Kinnlevőségek (Keleti Gyár) |              | 20,00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>3. példa: másik jogi személytől érkező, realizált árfolyamnyereséget tartalmazó számla vevői kifizetése
A Gyár 600,00 euró (EUR) összegű kifizetést kap a Gyár 4000-es vevőjére (Hegyvidéki Kereskedők). A kifizetés a Keleti Gyár 4000-es vevőjéhez tartozó nyitott számlát egyenlít ki. A kiegyenlítési folyamat során árfolyamnyereség-tranzakciót generál a rendszer.

-   Az EUR-USD átváltási árfolyam a számladátumon: 1,2062
-   Az EUR-USD átváltási árfolyam a kifizetési dátumon: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>A számla feladása a Keleti Gyárban a Keleti Gyár 4000-es vevőjére.

| Számla                             | Tartozik összeg            | Követel összeg           |
|-------------------------------------|-------------------------|-------------------------|
| Kinnlevőségek (Keleti Gyár) | 600,00 EUR / 723,72 USD |                         |
| Értékesítés (Keleti Gyár)               |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>A fizetés beérkezése és feladása a Gyárban a Gyár 4000-es vevőjére.

| Számla                        | Tartozik összeg            | Követel összeg           |
|--------------------------------|-------------------------|-------------------------|
| Készpénz (Gyár)                | 600,00 EUR / 736,62 USD |                         |
| Kinnlevőségek (Gyár) |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                         | Tartozik összeg            | Követel összeg           |
|---------------------------------|-------------------------|-------------------------|
| Kinnlevőségek (Gyár)  | 600,00 EUR / 736,62 USD |                         |
| Esedékes a Keleti Gyárnak (Gyár) |                         | 600,00 EUR / 736,62 USD |
| Esedékes a Keleti Gyárnak (Gyár) | 0,00 EUR / 12,90 USD    |                         |
| Realizált nyereség (Gyár)        |                         | 0,00 EUR / 12,90 USD    |

**Keleti Gyár – feladás**

| Számla                             | Tartozik összeg            | Követel összeg           |
|-------------------------------------|-------------------------|-------------------------|
| Esedékes a Gyártól (Keleti gyár)   | 600,00 EUR / 736,62 USD |                         |
| Kinnlevőségek (Keleti Gyár) |                         | 600,00 EUR / 736,62 USD |
| Kinnlevőségek (Keleti Gyár) | 0,00 EUR / 12,90 USD    |                         |
| Esedékes a Gyártól (Keleti gyár)   |                         | 0,00 EUR / 12,90 USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>4. példa: másik jogi személytől érkező, készpénzfizetési engedményt és realizált árfolyamnyereséget tartalmazó számla vevői kifizetése
A Gyár kifizetést ad fel a Gyár 4000-es vevőjére (Hegyvidéki Kereskedők) a Keleti Gyár egyik nyitott számlájával szemben. A számlán készpénzfizetési engedmény szerepel, valamint áfatranzakció jön létre. A kifizetés elszámolása a nyitott Keleti Gyár-számlával szemben történik. A kiegyenlítési folyamat során árfolyamnyereség-tranzakciót generál a rendszer. A rendszer feladja a készpénzfizetési engedményt a számla jogi személyének (Keleti Gyár), az árfolyamnyereséget a kifizető jogi személynek (Gyár).

-   Az EUR-USD átváltási árfolyam a számladátumon: 1,2062
-   Az EUR-USD átváltási árfolyam a kifizetési dátumon: 1,2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>A rendszer szabadszöveges számlát ad fel, valamint adótranzakciót hoz létre a Keleti Gyárban a 4000-es vevőre

| Számla                             | Tartozik összeg            | Követel összeg           |
|-------------------------------------|-------------------------|-------------------------|
| Kinnlevőségek (Keleti Gyár) | 638,22 EUR / 769,82 USD |                         |
| Értékesítés (Keleti Gyár)               |                         | 600,00 EUR / 723,72 USD |
| Áfa (Keleti Gyár)           |                         | 38,22 EUR / 46,10 USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>A fizetés beérkezése és feladása a Gyár 4000-es vevőjére.

| Számla                        | Tartozik összeg            | Követel összeg           |
|--------------------------------|-------------------------|-------------------------|
| Készpénz (Gyár)                | 626,22 EUR / 768,81 USD |                         |
| Kinnlevőségek (Gyár) |                         | 626,22 EUR / 768,81 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>A Gyár kifizetésének kiegyenlítése a Keleti Gyár számlájával szemben

**Gyár – feladás**

| Számla                         | Tartozik összeg            | Követel összeg           |
|---------------------------------|-------------------------|-------------------------|
| Kinnlevőségek (Gyár)  | 626,22 EUR / 768,81 USD |                         |
| Esedékes a Keleti Gyárnak (Gyár) |                         | 626,22 EUR / 768,81 USD |
| Esedékes a Keleti Gyárnak (Gyár) | 0,00 EUR / 13,46 USD    |                         |
| Realizált nyereség (Gyár)        |                         | 0,00 EUR / 13,46 USD    |

**Keleti Gyár – feladás**

| Számla                             | Tartozik összeg            | Követel összeg           |
|-------------------------------------|-------------------------|-------------------------|
| Esedékes a Gyártól (Keleti gyár)   | 626,22 EUR / 768,81 USD |                         |
| Kinnlevőségek (Keleti Gyár) |                         | 626,22 EUR / 768,81 USD |
| Kinnlevőségek (Keleti Gyár)  | 0,00 EUR / 13,46 USD    |                         |
| Esedékes a Gyártól (Keleti gyár)   |                         | 0,00 EUR / 13,46 USD    |
| Készpénzfizetési engedmény (Keleti Gyár)       | 12,00 EUR / 14,47 USD   |                         |
| Kinnlevőségek (Keleti Gyár) |                         | 12,00 EUR / 14,47 USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>5. példa: vevői jóváírás elsődleges kifizetéssel
A Gyár 75,00 összegű kifizetést kap a 4000-es vevőre (Hegyvidéki Kereskedők). A kifizetés elszámolása a Nyugati Gyár 10 000-es vevőjének egy nyitott számlájával és a Keleti Gyár 4000-es vevőjének egy nyitott jóváírásával szemben történik. A kifizetést a **Tranzakciók kiegyenlítése** képernyőn elsődleges kifizetésként jelölik meg.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Számla feladása a Nyugati Gyár 10 000-es vevőjére

| Fiók                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Kinnlevőségek (Nyugati Gyár) | 100,00       |               |
| Értékesítés (Nyugati Gyár)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Jóváírás feladása a Keleti Gyár 4000-es vevőjére

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Értékesítési visszáru (Keleti Gyár)       | 25,00        |               |
| Kinnlevőségek (Keleti Gyár) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Kifizetés feladása a Gyár 4000-es vevőjére

| Számla                        | Tartozik összeg | Követel összeg |
|--------------------------------|--------------|---------------|
| Készpénz (Gyár)                | 75,00        |               |
| Kinnlevőségek (Gyár) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>A Gyár kifizetésének elszámolása a Nyugati Gyár számlájával és a Keleti Gyár jóváírásával szemben

**Gyár – feladás**

| Számla                           | Tartozik összeg | Követel összeg |
|-----------------------------------|--------------|---------------|
| Esedékes a Keleti Gyártól (Gyár) | 25,00        |               |
| Kinnlevőségek (Gyár)    |              | 25,00         |
| Kinnlevőségek (Gyár)    | 100,00       |               |
| Esedékes a Nyugati Gyárnak (Gyár)   |              | 100,00        |

**Keleti Gyár – feladás**

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Kinnlevőségek (Keleti Gyár) | 25,00        |               |
| Esedékes a Gyárnak (Keleti Gyár)     |              | 25,00         |

**Nyugati Gyár – feladás**

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Esedékes a Gyártól (Nyugati Gyár)   | 100,00       |               |
| Kinnlevőségek (Nyugati Gyár) |              | 100,00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>6. példa: vevői jóváírás elsődleges kifizetés nélkül
A Gyár 75,00 összegű kifizetést kap a 4000-es vevőre (Hegyvidéki Kereskedők). A kifizetés elszámolása a Nyugati Gyár 10 000-es vevőjének egy nyitott számlájával és a Keleti Gyár 4000-es vevőjének egy nyitott jóváírásával szemben történik. A kifizetést a **Tranzakciók kiegyenlítése** képernyőn nem jelölik meg elsődleges kifizetésként.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Számla feladása a Nyugati Gyár 10 000-es vevőjére

| Fiók                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Kinnlevőségek (Nyugati Gyár) | 100,00       |               |
| Értékesítés (Nyugati Gyár)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Jóváírás feladása a Keleti Gyár 4000-es vevőjére

| Számla                             | Tartozik összeg | Követel összeg |
|-------------------------------------|--------------|---------------|
| Értékesítési visszáru (Keleti Gyár)       | 25,00        |               |
| Kinnlevőségek (Keleti Gyár) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Kifizetés feladása a Gyár 4000-es vevőjére

| Számla                        | Tartozik összeg | Követel összeg |
|--------------------------------|--------------|---------------|
| Készpénz (Gyár)                | 75,00        |               |
| Kinnlevőségek (Gyár) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>A Gyár kifizetésének elszámolása a Nyugati Gyár számlájával és a Keleti Gyár jóváírásával szemben

**Gyár – feladás**

| Számla                         | Tartozik összeg | Követel összeg |
|---------------------------------|--------------|---------------|
| Kinnlevőségek (Gyár)  | 75,00        |               |
| Esedékes a Nyugati Gyárnak (Gyár) |              | 75,00         |

**Keleti Gyár – feladás**

| Számla                              | Tartozik összeg | Követel összeg |
|--------------------------------------|--------------|---------------|
| Kinnlevőségek (Keleti Gyár)  | 25,00        |               |
| Esedékes a Nyugati Gyárnak (Keleti Gyár) |              | 25,00         |

**Nyugati Gyár – feladás**

| Számla                                | Tartozik összeg | Követel összeg |
|----------------------------------------|--------------|---------------|
| Esedékes a Gyártól (Nyugati Gyár)      | 75,00        |               |
| Kinnlevőségek (Nyugati Gyár)    |              | 75,00         |
| Esedékes a Keleti Gyártól (Nyugati Gyár) | 25,00        |               |
| Kinnlevőségek (Nyugati Gyár)    |              | 25,00         |
