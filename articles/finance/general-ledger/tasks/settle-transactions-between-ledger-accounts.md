---
title: Kiegyenlítési tranzakciók a főkönyvi számlák között
description: Ez az eljárás bemutatja a tranzakciók kiegyenlítését a főkönyvi számlák között, illetve a főkönyvi kiegyenlítés érvénytelenítését.
author: aprilolson
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2594b90ed58a1e7f12c8a94d3c48266faef557f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817053"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="0bbeb-103">Kiegyenlítési tranzakciók a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="0bbeb-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0bbeb-104">Ez az eljárás bemutatja a tranzakciók kiegyenlítését a főkönyvi számlák között, illetve a főkönyvi kiegyenlítés érvénytelenítését.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="0bbeb-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="0bbeb-106">Kiegyenlítési tranzakció a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="0bbeb-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="0bbeb-107">Ugorjon a Főkönyv > Időszaki feladatok > Főkönyvi kiegyenlítések pontra.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="0bbeb-108">A listán keresse meg a kiegyenlítendő tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0bbeb-109">Az összeg egyenlegnek nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="0bbeb-110">Kattintson a Befoglalás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-110">Click Include.</span></span>
4. <span data-ttu-id="0bbeb-111">Kattintson az Elfogadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="0bbeb-112">Főkönyvi kiegyenlítés érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="0bbeb-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="0bbeb-113">Ugorjon a Főkönyv > Lekérdezések és jelentések y Főkönyvi kivonat pontra.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="0bbeb-114">A „Paraméter” gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="0bbeb-115">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-115">Click Update.</span></span>
4. <span data-ttu-id="0bbeb-116">A listán keresse meg a számlát, amelyen kiegyenlített tranzakció szerepel.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="0bbeb-117">Kattintson az Összes tranzakció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-117">Click All transactions.</span></span>
6. <span data-ttu-id="0bbeb-118">Használjon szűrőt a tranzakció könnyebb megtalálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="0bbeb-119">Kattintson a Főkönyvi kiegyenlítések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="0bbeb-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0bbeb-120">In the list, mark the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]