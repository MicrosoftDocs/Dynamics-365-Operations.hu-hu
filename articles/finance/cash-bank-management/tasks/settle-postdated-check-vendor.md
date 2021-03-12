---
title: Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése
description: Rendezzen egy jövőben esedékes, szállító számára kibocsátott csekket, amennyiben bank a csekk lejárta és törlése után törölte a csekktranzakciót.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08cf4ec805e632470ef778f31beb87597e0ca096
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976191"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="fb9f3-103">Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése</span><span class="sxs-lookup"><span data-stu-id="fb9f3-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fb9f3-104">Rendezzen egy jövőben esedékes, szállító számára kibocsátott csekket, amennyiben bank a csekk lejárta és törlése után törölte a csekktranzakciót.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="fb9f3-105">Ez előtt a folyamat előtt végezze el a következőeket.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="fb9f3-106">Jövőben esedékes csekkek beállítása</span><span class="sxs-lookup"><span data-stu-id="fb9f3-106">Set up postdated checks</span></span>

2) <span data-ttu-id="fb9f3-107">Szállító részére kiállított, jövőben esedékes csekk regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="fb9f3-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="fb9f3-108">Ezen eljárás szerepköre: Pénztáros.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="fb9f3-109">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="fb9f3-110">Ugorjon a Kötelezettségek > Kifizetések > Szállító jövőben esedékes csekkjei pontra.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="fb9f3-111">Kattintson a Kiegyenlítés elemre.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-111">Click Settle.</span></span>
3. <span data-ttu-id="fb9f3-112">Kattintson az Elszámolási tételek kiegyenlítése elemre.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="fb9f3-113">Rendezze a csekktranzakció szállítói számláját.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="fb9f3-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-114">Close the page.</span></span>
5. <span data-ttu-id="fb9f3-115">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="fb9f3-116">A Megjelenítés mezőben válassza ki a következőt: „Mind”.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="fb9f3-117">Jelölje be vagy törölje a jelölést a Megjelenítés csak a felhasználó által létrehozott jelölőnégyzetéből.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="fb9f3-118">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="fb9f3-119">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-119">Click Lines.</span></span>
10. <span data-ttu-id="fb9f3-120">Kattintson a Bizonylat elemre.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-120">Click Voucher.</span></span>
11. <span data-ttu-id="fb9f3-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fb9f3-121">Close the page.</span></span>

