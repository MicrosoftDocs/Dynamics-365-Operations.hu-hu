---
title: "Részleges szállítói kifizetés rendezése, amely szállítói jóváírásokra vonatkozó engedménnyel rendelkezik"
description: "Ez a cikk végigvezeti egy eseten, ahol készpénzfizetési engedményt vonnak le egy jóváírásból úgy, hogy az eredeti számla is rendelkezett készpénzfizetési engedménnyel."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5402aa886d7194c4dcfad329aa30eb19bae3bc84
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Részleges szállítói kifizetés rendezése, amely szállítói jóváírásokra vonatkozó engedménnyel rendelkezik

[!INCLUDE [banner](../includes/banner.md)]

Ez a cikk végigvezeti egy eseten, ahol készpénzfizetési engedményt vonnak le egy jóváírásból úgy, hogy az eredeti számla is rendelkezett készpénzfizetési engedménnyel. 

A gyár lehetővé teszi a felhasználóknak a készpénzfizetési engedmények végrehajtandó részfizetések, valamint a jóváírásokra a számlaadatokat (jóváírás). A készpénzfizetési engedmény vehető jóváírással bizonyult a vevő készpénzfizetési engedményt a számla a jóváírás kibocsátásakor. Helyett a teljes összeget a követelés kezeléséről, a vevő egyenlegét is követel összeg nem tartalmazza a készpénzfizetési engedmény százaléka, amikor a vevő történt. A Kiegyenlítési paraméterek a **Kinnlevőségek paraméterei** oldalon találhatóak.

## <a name="invoice-and-credit-note"></a>Számlajóváírás
4035-ös vevőnél 1000,00 számlát és 100,00 jóváírás. Az egyes dokumentumokból 14 napon kifizetett 1 százalékos engedmény van. Arnie megtekintheti ezt a tranzakciót a **Vevői tranzakciók** oldalon.

| Bizonylat    | Tranzakció típusa | Dátum      | Számla  | Összeg a tranzakció pénznemtartozásában | Összeg a tranzakció pénznemtartozásában | Egyenleg  | Pénznem |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Számla          | 2015/6/28 | 10050    | 1000,00                             |                                       | 1000,00 | dollár      |
| CCRN-10050 | Jóváírás      | 2015/6/28 | CR-10050 |                                      | 100,00                                | -100,00  | dollár      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Egy jóváírást a számla kiegyenlítése
A **Vevői tranzakciók** oldalon April megnyitja a **Tranzakciók kiegyenlítése** lapot. A **Tranzakciók kiegyenlítése** lapon megjelöli a kiegyenlítéshez tartozó jóváírást és számlát is. A kiegyenlítési folyamat részeként akkor megjeleníti a készpénzfizetési engedmény dátumát és összegét. Ő jelöli meg két dokumentumot, és majd kattint **Feladása** tranzakcióinak kiegyenlítéséhez. Nincs -1.00 a jóváíráson engedményt, mert a gyár lehetővé teszi, hogy az engedmények a jóváírásokra a számlaadatokat.

| Jelölés     | Készpénzfizetési engedmény használata | Bizonylat    | Fiók | Dátum      | Fiz. határidő  | Számla  | Összeg a tranzakció pénznemében. | Pénznem | Kiegyenlítendő összeg |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Kijelölve | Normál            | FTI-10050  | 4035    | 2015/6/28 | 2015/7/28 | 10050    | 1000,00                       | dollár      | 990,00           |
| Kijelölve | Normál            | CCRN-10050 | 4035    | 2015/6/28 | 2015/7/28 | CR-10050 | -100,00                        | dollár      | -99.00           |

Az engedményadatok a **Nyitott tranzakciók kiegyenlítése** lap alján jelennek meg.

|                              |           |
|------------------------------|-----------|
| Készpénzfizetési engedmény dátuma           | 2015/7/12 |
| Készpénzfizetési engedmény összege         | -1.00     |
| Készpénzfizetési engedmény használata            | Normál    |
| Alkalmazott készpénzfizetési engedmény          | 0,00      |
| Alkalmazandó készpénzfizetési engedmény összege | -1.00     |

A kiegyenlítés 100,00 lesz, és a fizetés esetén 99,00 és 1,00 engedményt fog szerepelni.




