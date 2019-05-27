---
title: Főkönyv és a pénzügyi kimutatási honlapja
description: A Főkönyv segítségével meghatározhatja és kezelheti a jogi személy pénzügyi nyilvántartásait.
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b6683107f4b2dbe36af78749612ce950ea19582
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569290"
---
# <a name="general-ledger"></a><span data-ttu-id="6b4f4-103">Főkönyv</span><span class="sxs-lookup"><span data-stu-id="6b4f4-103">General ledger</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b4f4-104">A Főkönyv segítségével meghatározhatja és kezelheti a jogi személy pénzügyi nyilvántartásait.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="6b4f4-105">A főkönyvben a tartozik és követel tételek jegyzéke.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="6b4f4-106">Ezek a bejegyzések sorolják be a felsorolt számláknak használata a számlatükörben.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="6b4f4-107">Számlatükör tervezése</span><span class="sxs-lookup"><span data-stu-id="6b4f4-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="6b4f4-108">Főszámla típusai</span><span class="sxs-lookup"><span data-stu-id="6b4f4-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="6b4f4-109">A felosztás pénzösszegeknek a felosztási szabályok alapján egy vagy több számlára való elosztását jelenti.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="6b4f4-110">Két típusú felosztás használható, a fix és a változó felosztás.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="6b4f4-111">Főkönyvi számlák közötti tranzakciók kiegyenlítése és pénznemösszegek átértékelése is.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="6b4f4-112">A pénzügyi év végén a számlákat elő kell készíteni a következő pénzügyi évre, és le kell zárni az aktuális pénzügyi évet.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="6b4f4-113">A konszolidálási funkciók segítségével számos leányvállalat jogi személyek pénzügyi eredményeit egyesítése egyetlen, a konszolidált szervezet eredménye.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="6b4f4-114">A leányvállalatok lehetnek ugyanabban az egy Microsoft Dynamics 365 for Finance and Operations adatbázisban és különböző adatbázisokban is.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="6b4f4-115">Konszolidáció és megszüntetés áttekintése</span><span class="sxs-lookup"><span data-stu-id="6b4f4-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="6b4f4-116">Főkönyvi számlaegyenlegek</span><span class="sxs-lookup"><span data-stu-id="6b4f4-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="6b4f4-117">Pénzügyi dimenziók</span><span class="sxs-lookup"><span data-stu-id="6b4f4-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="6b4f4-118">[![Üzleti folyamat](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="6b4f4-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="6b4f4-119">Áfa</span><span class="sxs-lookup"><span data-stu-id="6b4f4-119">Sales tax</span></span>
<span data-ttu-id="6b4f4-120">Minden vállalat adót szed be és fizet különféle adóhatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="6b4f4-121">A szabályok és a mérték eltérők ország/régió, megye, állam és város.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="6b4f4-122">Ezenkívül a szabályokat frissíteni kell rendszeresen módosításakor adóhatóság által előírt követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="6b4f4-123">Az áfakód alapvetően azt határozza meg, hogy mennyi áfát kell begyűjteni és befizetni a hatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="6b4f4-124">Az áfakódok beállításakor megadhatja a begyűjtendő összeget vagy a százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="6b4f4-125">Azon különböző módszereket is megadhatja, amelyekkel meghatározzák ezen összegeket vagy százalékokat a tranzakcióösszegekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="6b4f4-126">Ebben a szakaszban található témakörök nyújtanak tájékoztatást a módok és díjak az adóhatóságnak igénylő áfakódok beállításával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="6b4f4-127">Áfa áttekintése</span><span class="sxs-lookup"><span data-stu-id="6b4f4-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="6b4f4-128">Áfaérték a Számítás alapja és a Számítási módszerek lapján</span><span class="sxs-lookup"><span data-stu-id="6b4f4-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="6b4f4-129">Áfakifizetések és kerekítési szabályok</span><span class="sxs-lookup"><span data-stu-id="6b4f4-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="6b4f4-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6b4f4-130">Additional resources</span></span>

#### <a name="whats-new-and-in-development"></a><span data-ttu-id="6b4f4-131">Újdonságok és fejlesztés alatt levő megoldások</span><span class="sxs-lookup"><span data-stu-id="6b4f4-131">What's new and in development</span></span>

<span data-ttu-id="6b4f4-132">Lépjen a [Microsoft Dynamics 365 Kibocsátási megjegyzések](https://go.microsoft.com/fwlink/?linkid=2010158) oldalára a tervezett új funkciók megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-132">Go to the [Microsoft Dynamics 365 Release Notes](https://go.microsoft.com/fwlink/?linkid=2010158) to see what new features have been planned.</span></span> 

#### <a name="blogs"></a><span data-ttu-id="6b4f4-133">Blogok</span><span class="sxs-lookup"><span data-stu-id="6b4f4-133">Blogs</span></span>

<span data-ttu-id="6b4f4-134">A [Microsoft Dynamics 365 blogon](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) és a [Microsoft Dynamics 365 Finance and Operations – Pénzügyek blogon](https://community.dynamics.com/365/financeandoperations/b/financials) véleményeket, híreket és egyéb információkat talál.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-134">You can find opinions, news, and other information on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) and the [Microsoft Dynamics 365 Finance and Operations - Financials blog](https://community.dynamics.com/365/financeandoperations/b/financials).</span></span>

<span data-ttu-id="6b4f4-135">A [Microsoft Dynamics Operations Partner közösségi blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) egyetlen erőforrás segítségével tájékoztatja a Microsoft Dynamics-partnereket az MBS Operations új és népszerű fejlesztéseiről.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-135">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

### <a name="videos"></a><span data-ttu-id="6b4f4-136">Videók</span><span class="sxs-lookup"><span data-stu-id="6b4f4-136">Videos</span></span>

<span data-ttu-id="6b4f4-137">Tekintse meg az útmutató-videókat, amelyek a [Microsoft Dynamics 365 YouTube csatornáján](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ) láthatók.</span><span class="sxs-lookup"><span data-stu-id="6b4f4-137">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="6b4f4-138">Közösségi blogok</span><span class="sxs-lookup"><span data-stu-id="6b4f4-138">Community blogs</span></span>

- [<span data-ttu-id="6b4f4-139">Mit kell tudni a főkönyvről a Dynamics 365 for Finance and Operations szolgáltatásban?</span><span class="sxs-lookup"><span data-stu-id="6b4f4-139">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)

