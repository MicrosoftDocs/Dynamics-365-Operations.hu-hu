---
title: "A számlatükör megtervezése"
description: "A cikk olyan információkat tartalmaz, melyek segítik önt számlatükröt tervezni szervezete számára."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 848da7ec8f4a7915f3b78945b808b564f4510434
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="4b8a8-103">A számlatükör megtervezése</span><span class="sxs-lookup"><span data-stu-id="4b8a8-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4b8a8-104">A cikk olyan információkat tartalmaz, melyek segítik önt számlatükröt tervezni szervezete számára.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="4b8a8-105">A szervezet pénzügyi adatainak nyomon követésére és karbantartására számlatükröt állíthat be.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="4b8a8-106">A számlatükör a számlák összessége, amelyek meghatározzák a pénzügyi keretet.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="4b8a8-107">Az ezen számlákon szereplő tranzakciók további követésére szegmenseket is hozzáadhat, pénzügyi dimenziók néven.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="4b8a8-108">Például egy költségszámla magába foglalhat olyan pénzügyi dimenziókat, mint a részleg, a költséghely és a cél.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="4b8a8-109">A számlastruktúrának és speciális szabályoknak nevezett felhasználó által definiált szabályok határozzák meg, hogyan kapcsolódnak ezek a pénzügyi dimenziók a fő számlákhoz és más pénzügyi dimenziókhoz, és hogyan lehet bevinni tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="4b8a8-110">A számlatükör a jogi személy főkönyvi számláinak rendszerezett felsorolása.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="4b8a8-111">A lista alapján lehet előkészíteni a pénzügyi jelentéseket a hatóságok és a tulajdonosok részére.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="4b8a8-112">A számlák számlatípusok szerint vannak csoportosítva, és további nagyobb kategóriákba vannak gyűjtve.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="4b8a8-113">A legáltalánosabb szinten a számlák a bevétel- és költségszámlák (eredményszámlák) csoportjára, illetve az eszközök és források (mérlegszámlák) csoportjára vannak felosztva.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="4b8a8-114">A Számlatükör osztva, és a szervezeten belüli olyan jogi személy által használt is.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="4b8a8-115">A jogi személy által használt számlatükör a **Főkönyv** oldalon van definiálva.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="4b8a8-116">A szervezeti számlatükör szerkezetével kapcsolatos döntések meghozatalakor többek között a következő tényezőket kell figyelembe venni:</span><span class="sxs-lookup"><span data-stu-id="4b8a8-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="4b8a8-117">Milyen jelentési kötelezettségek vannak érvényben abban az országban/régióban, ahol a szervezet működik?</span><span class="sxs-lookup"><span data-stu-id="4b8a8-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="4b8a8-118">A jelentési kötelezettségeket a jogi személy</span><span class="sxs-lookup"><span data-stu-id="4b8a8-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="4b8a8-119">Milyen szintű részletezést szükséges, mind külső szervezetek, mind a a szervezet számára</span><span class="sxs-lookup"><span data-stu-id="4b8a8-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="4b8a8-120">A számlatükröket a **Számlatükör** oldalon állíthatja be.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="4b8a8-121">A fő számlák a **Számlatükör** lapon vagy a **Fő számlák** oldalon hozhatók létre.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="4b8a8-122">A fő számlák nevében nem használható olyan speciális karakter, amelyet a számlatükör elválasztójelként használ.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="4b8a8-123">Ha a számlatükör-elválasztójelekkel megegyező különleges karaktert használ, akkor a rendszer instabillá válhat, vagy mindig kereséssel vagy helyi menüvel kell megadnia a számla és a dimenzió kombinációját.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="4b8a8-124">További tudnivalókkal kapcsolatban lásd: [Fő számla létrehozása](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="4b8a8-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="4b8a8-125">Rendkívül hasznos lehet a fő számlákat összekapcsolni főszámla-kategóriákkal, így kiélvezheti az alapértelmezett pénzügyi jelentések előnyeit anélkül, hogy módosításokat kellene végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="4b8a8-126">Így gyorsaban és egyszerűbben tud jelentéseket tervezni és karbantartani.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="4b8a8-127">A **Számlastruktúrák konfigurálása** oldalon hozhat létre számlastruktúrákat.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="4b8a8-128">A számlastruktúrák határozzák meg az érvényes kombinációkat.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-128">Account structures define valid combinations.</span></span> <span data-ttu-id="4b8a8-129">A kombinációkat, a fő számlákat, valamint a Számlatükör képernyő.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="4b8a8-130">További tudnivalókkal kapcsolatban lásd: [Számlastruktúra létrehozása](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="4b8a8-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="4b8a8-131">**Jogi személy felülbírálásai**</span><span class="sxs-lookup"><span data-stu-id="4b8a8-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="4b8a8-132">Nem minden fő számla érvényes minden jogi személyre, és néhány csak egy adott időszakra vonatkozhat.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="4b8a8-133">Ebben az esetben a Jogi személy felülbírálása szakasz használható annak azonosítására, hogy mely vállalatok számára kell felfüggeszteni a fő számlát, ki a tulajdonos, és mely időszakban aktív a dimenzió.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="4b8a8-134">A megosztott szinten történő felülbírálások nem lehet szigorúbban korlátozóak, mint a jogi személy szintjén történőek.</span><span class="sxs-lookup"><span data-stu-id="4b8a8-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="4b8a8-135">További tájékoztatást a következő témakörökben talál: [Pénzügyi dimenziók](financial-dimensions.md)
[Speciális szabálystruktúrák létrehozása és hozzárendelése](tasks/create-assign-advanced-rule-structures.md)</span><span class="sxs-lookup"><span data-stu-id="4b8a8-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>




