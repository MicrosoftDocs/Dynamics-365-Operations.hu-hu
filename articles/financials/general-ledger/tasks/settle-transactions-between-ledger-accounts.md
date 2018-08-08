--- 
title: "Kiegyenlítési tranzakciók a főkönyvi számlák között"
description: "Ez az eljárás bemutatja a tranzakciók kiegyenlítését a főkönyvi számlák között, illetve a főkönyvi kiegyenlítés érvénytelenítését."
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 2dbb45b142b575b6a7b0379be68718c14d906a90
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="a5bd0-103">Kiegyenlítési tranzakciók a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="a5bd0-103">Settle transactions between ledger accounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a5bd0-104">Ez az eljárás bemutatja a tranzakciók kiegyenlítését a főkönyvi számlák között, illetve a főkönyvi kiegyenlítés érvénytelenítését.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="a5bd0-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="a5bd0-106">Kiegyenlítési tranzakció a főkönyvi számlák között</span><span class="sxs-lookup"><span data-stu-id="a5bd0-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="a5bd0-107">Ugorjon a Főkönyv > Időszaki feladatok > Főkönyvi kiegyenlítések pontra.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="a5bd0-108">A listán keresse meg a kiegyenlítendő tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-108">In the list, find the transaction that you want to settle.</span></span>
    * <span data-ttu-id="a5bd0-109">Az összeg egyenlegnek nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="a5bd0-110">Kattintson a Befoglalás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-110">Click Include.</span></span>
4. <span data-ttu-id="a5bd0-111">Kattintson az Elfogadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="a5bd0-112">Főkönyvi kiegyenlítés érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="a5bd0-112">Cancel a ledger settlement</span></span>
1. <span data-ttu-id="a5bd0-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-113">Close the page.</span></span>
2. <span data-ttu-id="a5bd0-114">Ugorjon a Főkönyv > Lekérdezések és jelentések y Főkönyvi kivonat pontra.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-114">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
3. <span data-ttu-id="a5bd0-115">A „Paraméter” gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-115">Click Parameters to open the drop dialog.</span></span>
4. <span data-ttu-id="a5bd0-116">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-116">Click Update.</span></span>
5. <span data-ttu-id="a5bd0-117">A listán keresse meg a számlát, amelyen kiegyenlített tranzakció szerepel.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-117">In the list, find the account that has the settled transaction.</span></span>
6. <span data-ttu-id="a5bd0-118">Kattintson az Összes tranzakció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-118">Click All transactions.</span></span>
7. <span data-ttu-id="a5bd0-119">Használjon szűrőt a tranzakció könnyebb megtalálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-119">Use a filter to easily find the transaction in the list.</span></span>
8. <span data-ttu-id="a5bd0-120">Kattintson a Főkönyvi kiegyenlítések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-120">Click Ledger settlements.</span></span>
9. <span data-ttu-id="a5bd0-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a5bd0-121">In the list, mark the selected row.</span></span>


