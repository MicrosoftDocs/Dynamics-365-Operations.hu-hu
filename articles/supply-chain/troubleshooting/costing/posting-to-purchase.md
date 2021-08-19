---
title: Nulla összegű beszerzési elhatárolás feladása nulla értékű termékbevételezéshez
description: Ha egy nulla értékű termékbevételezést ad fel, a rendszer létrehoz egy feladást a beszerzési elhatárolásba, ahol az összeg 0 (nulla).
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 304609e065389d4f56913ae3f2f7fc562de2eadc9f0885ddbe2c8f4747081c66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722175"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a>Nulla összegű beszerzési elhatárolás feladása nulla értékű termékbevételezéshez

Tudásbáziscikk száma: 4612588

## <a name="symptoms"></a>Tünetek

Ha egy nulla értékű termékbevételezést ad fel, a rendszer létrehoz egy feladást a beszerzési elhatárolásba, ahol az összeg 0 (nulla).

## <a name="resolution"></a>Felbontás

Alapértelmezés szerint a *Beszerzés, elhatárolás* típusú főkönyvi feladásai esetén a `IsTransferredIndetail` mezőben mindig *Összegzés* az analitikus tranzakciókban a beállítás. Emiatt a rendszer akkor is létrehoz egy kapcsolódó bizonylatbejegyzést, ha az összeg 0 (nulla).

Ha ki kell hagyni ezt a feladási típust, ha az összeg 0 (nulla), akkor bővítse ki a `subledgerJournalizer.markDoNotTransferEntries` módszert úgy, hogy tartalmazza a `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount` módszert, amint azt az alábbi példa mutatja.

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
