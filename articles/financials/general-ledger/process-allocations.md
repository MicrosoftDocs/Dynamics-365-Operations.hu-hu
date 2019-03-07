---
title: Felosztások feldolgozása
description: A cikk tájékoztatást nyújt a felosztásokról, azok Microsoft Dynamics 365 for Finance and Operations rendszerben történő feldolgozásukról és arról, hogy hogyan alkalmazzuk őket a költségvetési tervben. A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac531726e04ebec4da9062f47726568723364cce
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "322214"
---
# <a name="process-allocations"></a><span data-ttu-id="9f7c2-105">Felosztások feldolgozása</span><span class="sxs-lookup"><span data-stu-id="9f7c2-105">Process allocations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f7c2-106">A cikk tájékoztatást nyújt a felosztásokról, azok Microsoft Dynamics 365 for Finance and Operations rendszerben történő feldolgozásukról és arról, hogy hogyan alkalmazzuk őket a költségvetési tervben.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-106">This article provides information about allocations, the options for processing them in Microsoft Dynamics 365 for Finance and Operations, and how they can be used in budget planning.</span></span> <span data-ttu-id="9f7c2-107">A felosztások segítségével összegeket oszthat fel több főkönyvi számla kombináció között.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="9f7c2-108">Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-108">They help guarantee that expenses or revenue is charged to the correct object in accounting.</span></span>

<span data-ttu-id="9f7c2-109">A Microsoft Dynamics 365 for Finance and Operations a folyamat támogatásához az alábbi funkciókat biztosítja:</span><span class="sxs-lookup"><span data-stu-id="9f7c2-109">Microsoft Dynamics 365 for Finance and Operations provides the following capabilities to support this process:</span></span>

-   <span data-ttu-id="9f7c2-110">Manuálisan is lefoglalhatók tranzakcióösszegek a Felosztás művelettel a könyvelési felosztás pontban, vagy pénzügyi dimenzió alapértelmezett sablonjainak használatával egy dokumentumre.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="9f7c2-111">További tudnivalókért lásd: [Könyvelési felosztások.](../accounts-payable/accounting-distributions.md)</span><span class="sxs-lookup"><span data-stu-id="9f7c2-111">For more information, see [Accounting distributions.](../accounts-payable/accounting-distributions.md)</span></span>
-   <span data-ttu-id="9f7c2-112">Tranzakcióösszegek automatikus felosztása az egyes fő számlán megadott felosztási feltételek alapján.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="9f7c2-113">Felosztási számlabejegyzések generálódnak minden naplóhoz, a százalék és a főkönyvi célszámla alapján, amikor egy számlázási bejegyzés megfelel a forrás főkönyvi számlában megadott feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span>
-   <span data-ttu-id="9f7c2-114">főkönyvi egyenlegek, vagy fix összegek automatikus felosztása a főkönyvi felosztási szabályok alapján.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-114">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="9f7c2-115">A főkönyvi felosztási szabályok feldolgozása rendszeres időközönként történik, felosztási naplók használatával.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-115">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> 

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="9f7c2-116">Felosztások a költségvetési tervezésben</span><span class="sxs-lookup"><span data-stu-id="9f7c2-116">Allocations in budget planning</span></span>

<span data-ttu-id="9f7c2-117">Főkönyvi felosztási szabályok a költségvetési tervekhez is használhatóak.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-117">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="9f7c2-118">Főkönyvi felosztási szabályok használatakor a költségvetés-tervezési felosztási szabályok munka a ugyanúgy, ahogy az a főkönyvben, de a forrásadatok, és a cél adatainak a költségvetési terv származik.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-118">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="9f7c2-119">Kezdődő a Főkönyvi felosztási szabályok költségvetési tervek.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-119">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="9f7c2-120">Másik lehetőségként használhatja a munkafolyamatok részeként futó egy felosztási ütemezés.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-120">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="9f7c2-121">Kezdődő   , használhatja a Főkönyvi felosztási szabályok költségvetési tervek.</span><span class="sxs-lookup"><span data-stu-id="9f7c2-121">You can’t use intercompany ledger allocation rules for budget planning.</span></span>





