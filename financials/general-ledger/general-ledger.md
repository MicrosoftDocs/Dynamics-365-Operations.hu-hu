---
title: "Főkönyv és a pénzügyi kimutatási honlapja"
description: "A Főkönyv segítségével meghatározhatja és kezelheti a jogi személy pénzügyi nyilvántartásait. A főkönyvben a tartozik és követel tételek jegyzéke. Ezek a bejegyzések sorolják be a felsorolt számláknak használata a számlatükörben."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 78f3d9c27767c089ac686f333cae3cb50c03ee18
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="general-ledger"></a><span data-ttu-id="0d6e1-105">Főkönyv</span><span class="sxs-lookup"><span data-stu-id="0d6e1-105">General ledger</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0d6e1-106">A Főkönyv segítségével meghatározhatja és kezelheti a jogi személy pénzügyi nyilvántartásait.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-106">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="0d6e1-107">A főkönyvben a tartozik és követel tételek jegyzéke.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-107">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="0d6e1-108">Ezek a bejegyzések sorolják be a felsorolt számláknak használata a számlatükörben.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-108">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

<span data-ttu-id="0d6e1-109">A felosztás pénzösszegeknek a felosztási szabályok alapján egy vagy több számlára való elosztását jelenti.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="0d6e1-110">Két típusú felosztás használható, a fix és a változó felosztás.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="0d6e1-111">Főkönyvi számlák közötti tranzakciók kiegyenlítése és pénznemösszegek átértékelése is.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="0d6e1-112">A pénzügyi év végén a számlákat elő kell készíteni a következő pénzügyi évre, és le kell zárni az aktuális pénzügyi évet.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="0d6e1-113">A konszolidálási funkciók segítségével számos leányvállalat jogi személyek pénzügyi eredményeit egyesítése egyetlen, a konszolidált szervezet eredménye.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="0d6e1-114">A leányvállalatok lehetnek ugyanabban az egy Microsoft Dynamics 365 for Finance and Operations adatbázisban és különböző adatbázisokban is.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

# <a name="sales-tax"></a><span data-ttu-id="0d6e1-115">Forgalmi adó</span><span class="sxs-lookup"><span data-stu-id="0d6e1-115">Sales tax</span></span>
<span data-ttu-id="0d6e1-116">Minden vállalat adót szed be és fizet különféle adóhatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-116">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="0d6e1-117">A szabályok és a mérték eltérők ország/régió, megye, állam és város.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-117">The rules and rates vary by country/region, state, county, and city.</span></span> <span data-ttu-id="0d6e1-118">Ezenkívül a szabályokat frissíteni kell rendszeresen módosításakor adóhatóság által előírt követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-118">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="0d6e1-119">Az áfakód alapvetően azt határozza meg, hogy mennyi áfát kell begyűjteni és befizetni a hatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-119">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="0d6e1-120">Az áfakódok beállításakor megadhatja a begyűjtendő összeget vagy a százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-120">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="0d6e1-121">Azon különböző módszereket is megadhatja, amelyekkel meghatározzák ezen összegeket vagy százalékokat a tranzakcióösszegekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-121">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="0d6e1-122">Ebben a szakaszban található témakörök nyújtanak tájékoztatást a módok és díjak az adóhatóságnak igénylő áfakódok beállításával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="0d6e1-122">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>







