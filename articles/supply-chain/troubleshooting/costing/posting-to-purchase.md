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
ms.openlocfilehash: f8d9d857590dc788d16b01edf77600d8fd8c8444
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026591"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a><span data-ttu-id="3964e-103">Nulla összegű beszerzési elhatárolás feladása nulla értékű termékbevételezéshez</span><span class="sxs-lookup"><span data-stu-id="3964e-103">Purchase accrual that has a zero amount is posted for a zero-value product receipt</span></span>

<span data-ttu-id="3964e-104">Tudásbáziscikk száma: 4612588</span><span class="sxs-lookup"><span data-stu-id="3964e-104">KB number: 4612588</span></span>

## <a name="symptoms"></a><span data-ttu-id="3964e-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="3964e-105">Symptoms</span></span>

<span data-ttu-id="3964e-106">Ha egy nulla értékű termékbevételezést ad fel, a rendszer létrehoz egy feladást a beszerzési elhatárolásba, ahol az összeg 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="3964e-106">When a product receipt that has zero value is posted, the system creates a posting to purchase accrual where the amount is 0 (zero).</span></span>

## <a name="resolution"></a><span data-ttu-id="3964e-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="3964e-107">Resolution</span></span>

<span data-ttu-id="3964e-108">Alapértelmezés szerint a *Beszerzés, elhatárolás* típusú főkönyvi feladásai esetén a `IsTransferredIndetail` mezőben mindig *Összegzés* az analitikus tranzakciókban a beállítás.</span><span class="sxs-lookup"><span data-stu-id="3964e-108">By default, for ledger postings of the *Purchase, accrual* type, the `IsTransferredIndetail` field is always set to *Summary* in subledger transactions.</span></span> <span data-ttu-id="3964e-109">Emiatt a rendszer akkor is létrehoz egy kapcsolódó bizonylatbejegyzést, ha az összeg 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="3964e-109">Therefore, the system creates a related voucher entry even if the amount is 0 (zero).</span></span>

<span data-ttu-id="3964e-110">Ha ki kell hagyni ezt a feladási típust, ha az összeg 0 (nulla), akkor bővítse ki a `subledgerJournalizer.markDoNotTransferEntries` módszert úgy, hogy tartalmazza a `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount` módszert, amint azt az alábbi példa mutatja.</span><span class="sxs-lookup"><span data-stu-id="3964e-110">To skip this posting type when the amount is 0 (zero), extend the `subledgerJournalizer.markDoNotTransferEntries` method so that it includes `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, as shown in the following example.</span></span>

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
