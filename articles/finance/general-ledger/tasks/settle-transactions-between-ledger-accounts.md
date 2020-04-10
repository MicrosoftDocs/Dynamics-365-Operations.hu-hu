---
title: Kiegyenlítési tranzakciók a főkönyvi számlák között
description: Ez az eljárás bemutatja a tranzakciók kiegyenlítését a főkönyvi számlák között, illetve a főkönyvi kiegyenlítés érvénytelenítését.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb53e9fee35712343f034389f00f3d4539cc652d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144674"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="692a8-103">Kiegyenlítési tranzakciók a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="692a8-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="692a8-104">Ez az eljárás bemutatja a tranzakciók kiegyenlítését a főkönyvi számlák között, illetve a főkönyvi kiegyenlítés érvénytelenítését.</span><span class="sxs-lookup"><span data-stu-id="692a8-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="692a8-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="692a8-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="692a8-106">Kiegyenlítési tranzakció a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="692a8-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="692a8-107">Ugorjon a Főkönyv > Időszaki feladatok > Főkönyvi kiegyenlítések pontra.</span><span class="sxs-lookup"><span data-stu-id="692a8-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="692a8-108">A listán keresse meg a kiegyenlítendő tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="692a8-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="692a8-109">Az összeg egyenlegnek nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="692a8-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="692a8-110">Kattintson a Befoglalás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="692a8-110">Click Include.</span></span>
4. <span data-ttu-id="692a8-111">Kattintson az Elfogadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="692a8-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="692a8-112">Főkönyvi kiegyenlítés érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="692a8-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="692a8-113">Ugorjon a Főkönyv > Lekérdezések és jelentések y Főkönyvi kivonat pontra.</span><span class="sxs-lookup"><span data-stu-id="692a8-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="692a8-114">A „Paraméter” gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="692a8-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="692a8-115">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="692a8-115">Click Update.</span></span>
4. <span data-ttu-id="692a8-116">A listán keresse meg a számlát, amelyen kiegyenlített tranzakció szerepel.</span><span class="sxs-lookup"><span data-stu-id="692a8-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="692a8-117">Kattintson az Összes tranzakció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="692a8-117">Click All transactions.</span></span>
6. <span data-ttu-id="692a8-118">Használjon szűrőt a tranzakció könnyebb megtalálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="692a8-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="692a8-119">Kattintson a Főkönyvi kiegyenlítések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="692a8-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="692a8-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="692a8-120">In the list, mark the selected row.</span></span>

