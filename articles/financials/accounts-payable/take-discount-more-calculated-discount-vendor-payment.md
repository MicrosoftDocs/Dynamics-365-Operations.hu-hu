---
title: "A szállítói kifizetésre vonatkozóan kiszámított engedménynél nagyobb engedmény alkalmazása"
description: "A cikk végigvezeti egy eseten, ahol egy készpénzfizetési engedmény nagyobb, mint az az engedmény, ami a számlán eredeti rendelkezésre álló összegként szerepelt. Ez az eset akkor fordulhat elő, ha egy szervezet megállapodik a szállítóval a számlán szereplő kisebb összeg kifizetésére."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 39830014593b7b1bc2868afffcca0f77a0c8a029
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a>A szállítói kifizetésre vonatkozóan kiszámított engedménynél nagyobb engedmény alkalmazása

[!include[banner](../includes/banner.md)]


A cikk végigvezeti egy eseten, ahol egy készpénzfizetési engedmény nagyobb, mint az az engedmény, ami a számlán eredeti rendelkezésre álló összegként szerepelt. Ez az eset akkor fordulhat elő, ha egy szervezet megállapodik a szállítóval a számlán szereplő kisebb összeg kifizetésére. 

A 3051. számú szállító 4 százalékos készpénzfizetési engedményt ad a Fabrikamnak, ha a számlát hét napon belül fizetik. Június 29-én April egy 1000,00 értékű számlát rögzít. A szállító 60,00 értékű kedvezményt ad Aprilnek az alapértelmezett engedmény helyett, amely a számlára vonatkozóan 40,00 lenne. April egyszeri kifizetést rögzít a Kötelezettségek fizetési naplóban. Megadja a kifizetéshez tartozó szállítót, majd megnyitja a **Tranzakciók kiegyenlítése** oldalt. Megjelöli a számlát, és a **Készpénzfizetési engedmény összege** mezőt **-60,00** értékre módosítja.
| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat   | Fiók | Dátum      | Fiz. határidő  | Számla | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | Inv-10040 | 3051    | 2015/29/6 | 2015/29/7 | 10040   | 1000,00                       | dollár      | 940,00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.
|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015/7/12 |
| Készpénzfizetési engedmény összege         | 60,00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | 60,00     |

April ezután feladja ezt a naplót. A számla teljesen ki van egyenlítve a 940,00 értékű fizetéssel és a 60,00 engedménnyel.




