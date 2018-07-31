---
title: "Főkönyv és a pénzügyi kimutatási honlapja"
description: "A Főkönyv segítségével meghatározhatja és kezelheti a jogi személy pénzügyi nyilvántartásait."
author: twheeloc
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 03bab1d03be71c0e23a6ea93f542d6a52a212a1f
ms.openlocfilehash: 9ee3f73cd11b38ed2237ea3fe08db18000e55f07
ms.contentlocale: hu-hu
ms.lasthandoff: 06/25/2018

---

# <a name="general-ledger"></a><span data-ttu-id="d0a40-103">Főkönyv</span><span class="sxs-lookup"><span data-stu-id="d0a40-103">General ledger</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0a40-104">A Főkönyv segítségével meghatározhatja és kezelheti a jogi személy pénzügyi nyilvántartásait.</span><span class="sxs-lookup"><span data-stu-id="d0a40-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="d0a40-105">A főkönyvben a tartozik és követel tételek jegyzéke.</span><span class="sxs-lookup"><span data-stu-id="d0a40-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="d0a40-106">Ezek a bejegyzések sorolják be a felsorolt számláknak használata a számlatükörben.</span><span class="sxs-lookup"><span data-stu-id="d0a40-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="d0a40-107">Számlatükör tervezése</span><span class="sxs-lookup"><span data-stu-id="d0a40-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="d0a40-108">Főszámla típusai</span><span class="sxs-lookup"><span data-stu-id="d0a40-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="d0a40-109">A felosztás pénzösszegeknek a felosztási szabályok alapján egy vagy több számlára való elosztását jelenti.</span><span class="sxs-lookup"><span data-stu-id="d0a40-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="d0a40-110">Két típusú felosztás használható, a fix és a változó felosztás.</span><span class="sxs-lookup"><span data-stu-id="d0a40-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="d0a40-111">Főkönyvi számlák közötti tranzakciók kiegyenlítése és pénznemösszegek átértékelése is.</span><span class="sxs-lookup"><span data-stu-id="d0a40-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="d0a40-112">A pénzügyi év végén a számlákat elő kell készíteni a következő pénzügyi évre, és le kell zárni az aktuális pénzügyi évet.</span><span class="sxs-lookup"><span data-stu-id="d0a40-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="d0a40-113">A konszolidálási funkciók segítségével számos leányvállalat jogi személyek pénzügyi eredményeit egyesítése egyetlen, a konszolidált szervezet eredménye.</span><span class="sxs-lookup"><span data-stu-id="d0a40-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="d0a40-114">A leányvállalatok lehetnek ugyanabban az egy Microsoft Dynamics 365 for Finance and Operations adatbázisban és különböző adatbázisokban is.</span><span class="sxs-lookup"><span data-stu-id="d0a40-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="d0a40-115">Konszolidáció és megszüntetés áttekintése</span><span class="sxs-lookup"><span data-stu-id="d0a40-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="d0a40-116">Főkönyvi számlaegyenlegek</span><span class="sxs-lookup"><span data-stu-id="d0a40-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="d0a40-117">Pénzügyi dimenziók</span><span class="sxs-lookup"><span data-stu-id="d0a40-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="d0a40-118">[![Üzleti folyamat](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="d0a40-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="d0a40-119">Áfa</span><span class="sxs-lookup"><span data-stu-id="d0a40-119">Sales tax</span></span>
<span data-ttu-id="d0a40-120">Minden vállalat adót szed be és fizet különféle adóhatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="d0a40-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="d0a40-121">A szabályok és a mérték eltérők ország/régió, megye, állam és város.</span><span class="sxs-lookup"><span data-stu-id="d0a40-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="d0a40-122">Ezenkívül a szabályokat frissíteni kell rendszeresen módosításakor adóhatóság által előírt követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="d0a40-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="d0a40-123">Az áfakód alapvetően azt határozza meg, hogy mennyi áfát kell begyűjteni és befizetni a hatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="d0a40-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="d0a40-124">Az áfakódok beállításakor megadhatja a begyűjtendő összeget vagy a százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="d0a40-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="d0a40-125">Azon különböző módszereket is megadhatja, amelyekkel meghatározzák ezen összegeket vagy százalékokat a tranzakcióösszegekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="d0a40-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="d0a40-126">Ebben a szakaszban található témakörök nyújtanak tájékoztatást a módok és díjak az adóhatóságnak igénylő áfakódok beállításával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="d0a40-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="d0a40-127">Áfa áttekintése</span><span class="sxs-lookup"><span data-stu-id="d0a40-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="d0a40-128">Áfaérték a Számítás alapja és a Számítási módszerek lapján</span><span class="sxs-lookup"><span data-stu-id="d0a40-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="d0a40-129">Áfakifizetések és kerekítési szabályok</span><span class="sxs-lookup"><span data-stu-id="d0a40-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="d0a40-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d0a40-130">Additional resources</span></span>

### <a name="whats-new"></a><span data-ttu-id="d0a40-131">Újdonságok</span><span class="sxs-lookup"><span data-stu-id="d0a40-131">What's new</span></span>

<span data-ttu-id="d0a40-132">Ugrás a [Programverzióra vonatkozó megjegyzésekre](https://docs.microsoft.com/en-us/business-applications-release-notes/), ahol megtekintheti, milyen új szolgáltatások lettek kiadva.</span><span class="sxs-lookup"><span data-stu-id="d0a40-132">Go to the [Release notes](https://docs.microsoft.com/en-us/business-applications-release-notes/) to see what new features have been released.</span></span> 

### <a name="videos"></a><span data-ttu-id="d0a40-133">Videók</span><span class="sxs-lookup"><span data-stu-id="d0a40-133">Videos</span></span>

<span data-ttu-id="d0a40-134">Tekintse meg az útmutató-videókat, amelyek [a Microsoft Dynamics 365 YouTube csatornáján](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ) láthatók.</span><span class="sxs-lookup"><span data-stu-id="d0a40-134">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>

### <a name="blogs"></a><span data-ttu-id="d0a40-135">Blogok</span><span class="sxs-lookup"><span data-stu-id="d0a40-135">Blogs</span></span>

<span data-ttu-id="d0a40-136">A [Microsoft Dynamics 365 blogon](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) véleményeket, híreket és egyéb információkat talál a Kötelezettségek modullal és egyéb megoldásokkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="d0a40-136">You can find opinions, news, and other information about Accounts payable and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span></span>

<span data-ttu-id="d0a40-137">A [Microsoft Dynamics AX termékcsapat blogjában](https://blogs.msdn.microsoft.com/dax/) több bejegyzés is szól a Főkönyv modul által nyújtott lehetőségekről.</span><span class="sxs-lookup"><span data-stu-id="d0a40-137">There are many posts about General ledger on the [Microsoft Dynamics AX product team blog](https://blogs.msdn.microsoft.com/dax/).</span></span> <span data-ttu-id="d0a40-138">A bejegyezések egy része ugyan a Főkönyv előző verziójához íródott, de ugyanazon fogalmak érvényesek továbbra is, és az eljárások is hasonlóak az aktuális verzióban.</span><span class="sxs-lookup"><span data-stu-id="d0a40-138">Although some of these posts were written for the previous version of General ledger, the same concepts still apply, and the procedures are also similar in the current version.</span></span>

<span data-ttu-id="d0a40-139">A [Microsoft Dynamics Operations Partner közösségi blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) egyetlen erőforrás segítségével tájékoztatja a Microsoft Dynamics-partnereket az MBS Operations új és népszerű fejlesztéseiről.</span><span class="sxs-lookup"><span data-stu-id="d0a40-139">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="d0a40-140">Közösségi blogok</span><span class="sxs-lookup"><span data-stu-id="d0a40-140">Community blogs</span></span>

- [<span data-ttu-id="d0a40-141">Főkönyvvel kapcsolatos tudnivalók Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d0a40-141">What you should know about ledger in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)


