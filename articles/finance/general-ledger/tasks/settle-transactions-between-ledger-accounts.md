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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6813871a4773d39d4abfdecc896a2aa8b320cbe0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222095"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="b31d6-103">Kiegyenlítési tranzakciók a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="b31d6-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b31d6-104">Ez az eljárás bemutatja a tranzakciók kiegyenlítését a főkönyvi számlák között, illetve a főkönyvi kiegyenlítés érvénytelenítését.</span><span class="sxs-lookup"><span data-stu-id="b31d6-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="b31d6-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b31d6-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="b31d6-106">Kiegyenlítési tranzakció a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="b31d6-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="b31d6-107">Ugorjon a Főkönyv > Időszaki feladatok > Főkönyvi kiegyenlítések pontra.</span><span class="sxs-lookup"><span data-stu-id="b31d6-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="b31d6-108">A listán keresse meg a kiegyenlítendő tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="b31d6-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b31d6-109">Az összeg egyenlegnek nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b31d6-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="b31d6-110">Kattintson a Befoglalás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b31d6-110">Click Include.</span></span>
4. <span data-ttu-id="b31d6-111">Kattintson az Elfogadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b31d6-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="b31d6-112">Főkönyvi kiegyenlítés érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="b31d6-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="b31d6-113">Ugorjon a Főkönyv > Lekérdezések és jelentések y Főkönyvi kivonat pontra.</span><span class="sxs-lookup"><span data-stu-id="b31d6-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="b31d6-114">A „Paraméter” gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b31d6-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="b31d6-115">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="b31d6-115">Click Update.</span></span>
4. <span data-ttu-id="b31d6-116">A listán keresse meg a számlát, amelyen kiegyenlített tranzakció szerepel.</span><span class="sxs-lookup"><span data-stu-id="b31d6-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="b31d6-117">Kattintson az Összes tranzakció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b31d6-117">Click All transactions.</span></span>
6. <span data-ttu-id="b31d6-118">Használjon szűrőt a tranzakció könnyebb megtalálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="b31d6-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="b31d6-119">Kattintson a Főkönyvi kiegyenlítések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b31d6-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="b31d6-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b31d6-120">In the list, mark the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]