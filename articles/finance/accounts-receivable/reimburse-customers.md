---
title: Visszatérítés vevőknek
description: Ez a cikk ismerteti a vásárlók egy csoportját érintő visszatérítési tranzakciók létrehozásának folyamatát. Ha a vevőnek követel egyenlege van, visszatéríthet a vevőnek az egyenleg összegéért.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae6a3078743fc9cd43c71bc1d4531c0553ee53bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012139"
---
# <a name="reimburse-customers"></a><span data-ttu-id="8bfe7-104">Visszatérítés vevőknek</span><span class="sxs-lookup"><span data-stu-id="8bfe7-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8bfe7-105">Ez a cikk ismerteti a vásárlók egy csoportját érintő visszatérítési tranzakciók létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="8bfe7-106">Ha a vevőnek követel egyenlege van, visszatéríthet a vevőnek az egyenleg összegéért.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="8bfe7-107">Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="8bfe7-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8bfe7-108">Prerequisite</span></span>                                                            | <span data-ttu-id="8bfe7-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="8bfe7-109">Description</span></span> |
|-------------------------------------------------------------------------|-------------|
| <span data-ttu-id="8bfe7-110">Adja meg a legalacsonyabb visszatérítés összegét a jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="8bfe7-111">Az a **Kinnlevőségek paraméterei** oldalon, az **Általános** területen, a **A legalacsonyabb visszatérítés** mezőbe írja be azt a minimális összeget, amely a vevő általi túlfizetések miatt vissza kell fizetni.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="8bfe7-112">Választható: Szállítói számla hozzáadása minden vevőhöz, akit vissza lehet téríteni.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="8bfe7-113">A **Vevők** oldalon, a **Vegyes részletek** gyorslapon, a **Szállítókód** mezőben, válassza ki a szállítói számlát a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span> |

<span data-ttu-id="8bfe7-114">A visszatérítési tranzakciók létrehozásakor a szállítói számla a követel egyenleg összegéhez jön létre.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="8bfe7-115">A visszatérítési folyamat eltávolítja a követel egyenleget a vevői számlához, és létrehoz egy egyenleget, amely esedékes a szállítói számlához, amely megfelel a veőnek.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1. <span data-ttu-id="8bfe7-116">A Kinnlevőségekben futtassa a **Visszatérítés** folyamatot (**Kinnlevőségek \> Időszakos feladatok \> Visszatérítés**).</span><span class="sxs-lookup"><span data-stu-id="8bfe7-116">In Accounts receivable, run the **Reimbursement** process (**Accounts receivable \> Periodic tasks \> Reimbursement**).</span></span>
2. <span data-ttu-id="8bfe7-117">Az összes tranzakció csoportosításához a főkönyvi dimenzióktól függetlenül állítsa be a **Vevő összegzése** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-117">To group all transactions, regardless of ledger dimensions, set the **Summarize customer** option to **Yes**.</span></span> <span data-ttu-id="8bfe7-118">Ha csak a hasonló főkönyvi dimenziókkal rendelkező tranzakciókat szeretné csoportosítani, állítsa a lehetőséget **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-118">To group only transactions that have similar ledger dimensions, set the option to **No**.</span></span>
3. <span data-ttu-id="8bfe7-119">Válassza a **Elmaradási megbízási tranzakciókkal rendelkező vevők felvétele** lehetőséget a kiegyenlítetlen összegekkel rendelkező vevők kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-119">Select **Include customers with outstanding debit transactions** to select customers who have unsettled debit amounts.</span></span>
4. <span data-ttu-id="8bfe7-120">Adott vevőszámlák visszatérítéséhez a **Rekordok felvétele** gyorslapon válassza a **Szűrő** lehetőséget, majd adja meg a lekérdezésben a vevői számlákat.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-120">To reimburse specific customer accounts, on the **Records to include** FastTab, select **Filter**, and then specify the customer accounts in the query.</span></span>

    <span data-ttu-id="8bfe7-121">A követel összegek átkerülnek a vevők szállítói számláira, és normál kifizetésként dolgozza fel őket a program.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-121">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="8bfe7-122">Ha a vevő nem rendelkezik szállítói számlával, a program automatikusan létrehoz a vevő számára egy egyszer használatos szállítói számlát.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-122">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>

5. <span data-ttu-id="8bfe7-123">A létrehozott visszatérítési tranzakciók megtekintéséhez használja a **Visszatérítési** jelentést (**Kinnlevőségek \> Lekérdezések és jelentések \> Visszatérítési jelentés**).</span><span class="sxs-lookup"><span data-stu-id="8bfe7-123">To view the reimbursement transactions that were created, use the **Reimbursement** report (**Accounts Receivable \> Inquiries and reports \> Reimbursement report**).</span></span>
6. <span data-ttu-id="8bfe7-124">A kötelezettségekben hozzon létre kifizetést a szállítói számlákhoz, amelyek a bevételezési folyamat során jöttek létre.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-124">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span> <span data-ttu-id="8bfe7-125">A szállítók kifizetéséről a [Szállítói kifizetések áttekintése](../accounts-payable/Vendor-payments-workspace.md) című témakörben olvashat.</span><span class="sxs-lookup"><span data-stu-id="8bfe7-125">For information about how to pay vendors, see [Vendor payment overview](../accounts-payable/Vendor-payments-workspace.md).</span></span>
