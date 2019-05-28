---
title: Részleges szállítói kifizetés rendezése, amely szállítói jóváírásokra vonatkozó engedménnyel rendelkezik
description: Ez a cikk végigvezeti Önt egy eseten, amelyben egy jóváírás egy számlával van kiegyenlítve.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed8232445a89ded122108ef369357845c06b3033
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509037"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-vendor-credit-notes"></a>Részleges szállítói kifizetés rendezése, amely szállítói jóváírásokra vonatkozó engedménnyel rendelkezik

[!include [banner](../includes/banner.md)]

Ez a cikk végigvezeti Önt egy eseten, amelyben egy jóváírás egy számlával van kiegyenlítve.

A FAbrikam szállítói készpénzfizetési engedményeket kínálnak a jóváírásokra. A 3050. számú szállító 1 százalékos készpénzfizetési engedményt ad a Fabrikamnak, ha a számlát 14 napon belül fizetik.

## <a name="invoice-and-credit-memo"></a>Számla és jóváírás
Június 29-én April egy 1.000,00 értékű számlát hoz létre 3050-es szállító számára. Július 2-án 200,00 értékű jóváírást hoz létre. A **Szállítók** oldalon April megnyitja a **Tranzakciók kiegyenlítése** lapot. A **Tranzakciók kiegyenlítése** lapon megjelöli a kiegyenlítéshez tartozó jóváírást és számlát is. Az 2,00 értékű engedményt a rendszer kiszámítja a jóváíráson. Így a jóváírás összértéke 198,00-ra csökken.

| Jelölés                     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve                 | Normál            | Inv-10070 | 3050    | 2015/29/6 | 2015/29/7 | 10070   | -1000,00                      | dollár      | -990,00          |
| Kiválasztva és kiemelve | Normál            | CR-10070  | 3050    | 2015/7/2  | 2015/29/7 |         | 200,00                         | dollár      | 198,00           |

A jóváírás engedményadatai a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015/13/7 |
| Készpénzfizetési engedmény összege         | 2,00      |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 2,00      |

April a **Feladás** gombra kattint. Ezután ellenőrzi a befejezett kiegyenlítést. Azt látja, hogy a jóváírásból 198,00 lett alkalmazva, és 2,00 engedmény is jár. A teljes összeg ezért 200,00.

| Jelölés                     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla  | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Kiválasztva és kiemelve | Normál            | Inv-10070 | 3050    | 2015/29/6 | 2015/29/7 | 10070    | -1000,00                      | dollár      | -200,00          |
| Kijelölve                 | Normál            | CR-10070  | 3050    | 2015/7/2  | 2015/29/7 | CR-10070 | 200,00                         | dollár      | 198,00           |

April a **Szállítói tranzakciók** oldalon tudja áttekinteni a szállítói tranzakciókat, úgy, hogy kiválaszt egyet a **Minden szállító**lapon, és a műveleti ablakban a **Tranzakciók** elemre kattint. Ezen a lapon April azt láthatja, hogy a számla egyenlege -800,00. Emellett egy 198,00 értékű jóváírást, és egy 2,00 értékű engedményt talál.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg | Pénznem |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | Számla          | 2015/29/6 | 10070   |                                      | 1000,00                              | -800,00 | dollár      |
| Inv-10071  |                  | 2015/7/2  | CR10071 | 200,00                               |                                       | 0,00    | dollár      |
| DISC-10071 |  Készpénzfizetési engedmény   | 2015/7/2  |         | 2,00                                 |                                       | 0,00    | dollár      |
| DISC-10071 |  Készpénzfizetési engedmény   | 2015/7/2  |         |                                      | 2,00                                  | 0,00    | dollár      |





