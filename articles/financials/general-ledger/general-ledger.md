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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: f3defa29581c6c90994a673bd73d96613101a391
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="general-ledger"></a><span data-ttu-id="839ac-103">Főkönyv</span><span class="sxs-lookup"><span data-stu-id="839ac-103">General ledger</span></span> 

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="839ac-104">A Főkönyv segítségével meghatározhatja és kezelheti a jogi személy pénzügyi nyilvántartásait.</span><span class="sxs-lookup"><span data-stu-id="839ac-104">Use General ledger to define and manage the legal entity’s financial records.</span></span> <span data-ttu-id="839ac-105">A főkönyvben a tartozik és követel tételek jegyzéke.</span><span class="sxs-lookup"><span data-stu-id="839ac-105">The general ledger is a register of debit and credit entries.</span></span> <span data-ttu-id="839ac-106">Ezek a bejegyzések sorolják be a felsorolt számláknak használata a számlatükörben.</span><span class="sxs-lookup"><span data-stu-id="839ac-106">These entries are classified using the accounts that are listed in a chart of accounts.</span></span> 

 - [<span data-ttu-id="839ac-107">Számlatükör tervezése</span><span class="sxs-lookup"><span data-stu-id="839ac-107">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md)
 - [<span data-ttu-id="839ac-108">Főszámla típusai</span><span class="sxs-lookup"><span data-stu-id="839ac-108">Main account types</span></span>](main-account-types.md)

<span data-ttu-id="839ac-109">A felosztás pénzösszegeknek a felosztási szabályok alapján egy vagy több számlára való elosztását jelenti.</span><span class="sxs-lookup"><span data-stu-id="839ac-109">You can allocate, or distribute, monetary amounts to one or more accounts or account and dimension combinations based on allocation rules.</span></span> <span data-ttu-id="839ac-110">Két típusú felosztás használható, a fix és a változó felosztás.</span><span class="sxs-lookup"><span data-stu-id="839ac-110">There are two types of allocations: fixed and variable.</span></span> <span data-ttu-id="839ac-111">Főkönyvi számlák közötti tranzakciók kiegyenlítése és pénznemösszegek átértékelése is.</span><span class="sxs-lookup"><span data-stu-id="839ac-111">You can also settle transactions between ledger accounts and revalue currency amounts.</span></span> <span data-ttu-id="839ac-112">A pénzügyi év végén a számlákat elő kell készíteni a következő pénzügyi évre, és le kell zárni az aktuális pénzügyi évet.</span><span class="sxs-lookup"><span data-stu-id="839ac-112">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span> <span data-ttu-id="839ac-113">A konszolidálási funkciók segítségével számos leányvállalat jogi személyek pénzügyi eredményeit egyesítése egyetlen, a konszolidált szervezet eredménye.</span><span class="sxs-lookup"><span data-stu-id="839ac-113">You can use the consolidation functionality to combine the financial results for several subsidiary legal entities into results for a single, consolidated organization.</span></span> <span data-ttu-id="839ac-114">A leányvállalatok lehetnek ugyanabban az egy Microsoft Dynamics 365 for Finance and Operations adatbázisban és különböző adatbázisokban is.</span><span class="sxs-lookup"><span data-stu-id="839ac-114">The subsidiaries can be in the same Microsoft Dynamics 365 for Finance and Operations database or in separate databases.</span></span>

- [<span data-ttu-id="839ac-115">Konszolidáció és megszüntetés áttekintése</span><span class="sxs-lookup"><span data-stu-id="839ac-115">Consolidation and elimination overview</span></span>](../budgeting/consolidation-elimination-overview.md)
- [<span data-ttu-id="839ac-116">Főkönyvi számlaegyenlegek</span><span class="sxs-lookup"><span data-stu-id="839ac-116">General ledger account balances</span></span>](general-ledger-account-balances.md)
- [<span data-ttu-id="839ac-117">Pénzügyi dimenziók</span><span class="sxs-lookup"><span data-stu-id="839ac-117">Financial dimensions</span></span>](financial-dimensions.md)

<span data-ttu-id="839ac-118">[![Üzleti folyamat](./media/GL-process.PNG)](./media/GL-process.PNG)</span><span class="sxs-lookup"><span data-stu-id="839ac-118">[![Business process](./media/GL-process.PNG)](./media/GL-process.PNG)</span></span>

## <a name="sales-tax"></a><span data-ttu-id="839ac-119">Áfa</span><span class="sxs-lookup"><span data-stu-id="839ac-119">Sales tax</span></span>
<span data-ttu-id="839ac-120">Minden vállalat adót szed be és fizet különféle adóhatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="839ac-120">Every company collects and pays taxes to various tax authorities.</span></span> <span data-ttu-id="839ac-121">A szabályok és a mérték eltérők ország/régió, megye, állam és város.</span><span class="sxs-lookup"><span data-stu-id="839ac-121">The rules and rates vary by country/region, state, county, and city.</span></span>
<span data-ttu-id="839ac-122">Ezenkívül a szabályokat frissíteni kell rendszeresen módosításakor adóhatóság által előírt követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="839ac-122">In addition, the rules must be updated periodically when tax authorities change their requirements.</span></span> <span data-ttu-id="839ac-123">Az áfakód alapvetően azt határozza meg, hogy mennyi áfát kell begyűjteni és befizetni a hatóságoknak.</span><span class="sxs-lookup"><span data-stu-id="839ac-123">Sales tax codes contain the basic information about how much you collect and pay to the authorities.</span></span> <span data-ttu-id="839ac-124">Az áfakódok beállításakor megadhatja a begyűjtendő összeget vagy a százalékos értéket.</span><span class="sxs-lookup"><span data-stu-id="839ac-124">When you set up sales tax codes, you define the amounts or percentages that must be collected.</span></span> <span data-ttu-id="839ac-125">Azon különböző módszereket is megadhatja, amelyekkel meghatározzák ezen összegeket vagy százalékokat a tranzakcióösszegekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="839ac-125">You also define the various methods by which those amounts or percentages are applied to transaction amounts.</span></span> <span data-ttu-id="839ac-126">Ebben a szakaszban található témakörök nyújtanak tájékoztatást a módok és díjak az adóhatóságnak igénylő áfakódok beállításával kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="839ac-126">The topics in this section provide information about how to set up sales tax codes for the methods and rates that your tax authorities require.</span></span>

 - [<span data-ttu-id="839ac-127">Áfa áttekintése</span><span class="sxs-lookup"><span data-stu-id="839ac-127">Sales tax overview</span></span>](indirect-taxes-overview.md)
 - [<span data-ttu-id="839ac-128">Áfaérték a Számítás alapja és a Számítási módszerek lapján</span><span class="sxs-lookup"><span data-stu-id="839ac-128">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)
 - [<span data-ttu-id="839ac-129">Áfakifizetések és kerekítési szabályok</span><span class="sxs-lookup"><span data-stu-id="839ac-129">Sales tax payments and rounding rules</span></span>](round-sales-tax-payments.md)


## <a name="additional-resources"></a><span data-ttu-id="839ac-130">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="839ac-130">Additional resources</span></span>

### <a name="whats-new-and-in-development"></a><span data-ttu-id="839ac-131">Újdonságok és fejlesztés alatt levő megoldások</span><span class="sxs-lookup"><span data-stu-id="839ac-131">What's new and in development</span></span>

<span data-ttu-id="839ac-132">Keresse fel a [Microsoft Dynamics 365 ütemterv](https://roadmap.dynamics.com/) oldalt a már kiadott új funkciók és a kidolgozás alatt álló új szolgáltatások megtekintése érdekében.</span><span class="sxs-lookup"><span data-stu-id="839ac-132">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span> 

### <a name="blogs"></a><span data-ttu-id="839ac-133">Blogok</span><span class="sxs-lookup"><span data-stu-id="839ac-133">Blogs</span></span>

<span data-ttu-id="839ac-134">A [Microsoft Dynamics 365 blogon](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) véleményeket, híreket és egyéb információkat talál a Kötelezettségek modullal és egyéb megoldásokkal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="839ac-134">You can find opinions, news, and other information about Accounts payable and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).</span></span>

<span data-ttu-id="839ac-135">A [Microsoft Dynamics AX termékcsapat blogjában](https://blogs.msdn.microsoft.com/dax/) több bejegyzés is szól a Főkönyv modul által nyújtott lehetőségekről.</span><span class="sxs-lookup"><span data-stu-id="839ac-135">There are many posts about General ledger on the [Microsoft Dynamics AX product team blog](https://blogs.msdn.microsoft.com/dax/).</span></span> <span data-ttu-id="839ac-136">A bejegyezések egy része ugyan a Főkönyv előző verziójához íródott, de ugyanazon fogalmak érvényesek továbbra is, és az eljárások is hasonlóak az aktuális verzióban.</span><span class="sxs-lookup"><span data-stu-id="839ac-136">Although some of these posts were written for the previous version of General ledger, the same concepts still apply, and the procedures are also similar in the current version.</span></span>

<span data-ttu-id="839ac-137">A [Microsoft Dynamics Operations Partner közösségi blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) egyetlen erőforrás segítségével tájékoztatja a Microsoft Dynamics-partnereket az MBS Operations új és népszerű fejlesztéseiről.</span><span class="sxs-lookup"><span data-stu-id="839ac-137">The [Microsoft Dynamics Operations Partner Community Blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) gives Microsoft Dynamics Partners a single resource where they can learn what is new and trending in MBS Operations.</span></span>

### <a name="task-guides"></a><span data-ttu-id="839ac-138">Feladat-útmutatók</span><span class="sxs-lookup"><span data-stu-id="839ac-138">Task guides</span></span>
<span data-ttu-id="839ac-139">Feladat-útmutatók formájában további segítség áll rendelkezésre a Finance and Operations alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="839ac-139">Additional help is available as task guides inside Finance and Operations.</span></span> <span data-ttu-id="839ac-140">A feladat-útmutatók eléréséhez kattintson bármelyik lapon a Súgó gombjára.</span><span class="sxs-lookup"><span data-stu-id="839ac-140">To access task guides, click the Help button on any page.</span></span>

### <a name="videos"></a><span data-ttu-id="839ac-141">Videók</span><span class="sxs-lookup"><span data-stu-id="839ac-141">Videos</span></span>

<span data-ttu-id="839ac-142">Tekintse meg az útmutató-videókat, amelyek [a Microsoft Dynamics 365 YouTube csatornáján](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ) láthatók.</span><span class="sxs-lookup"><span data-stu-id="839ac-142">Check out the how-to videos that are now available on the [Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).</span></span>


