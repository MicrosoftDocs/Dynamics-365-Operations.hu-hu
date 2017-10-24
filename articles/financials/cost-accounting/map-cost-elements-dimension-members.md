---
title: "Költségösszetevő-dimenziótagok hozzárendelése a dimenziótagok általános készletéhez"
description: "Azzal, hogy a különböző költségösszetevő-dimenziótagokat hozzárendeli a költségösszetevő-dimenziótagok egy közös csoportjához, az adatokat egy közös formátumnak megfelelően egyesíti elemzési célokra."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b15e251410937ff4f85ecdfaa55ca1a998d1d1ac
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a><span data-ttu-id="393f3-103">Költségösszetevő-dimenziótagok hozzárendelése a dimenziótagok általános készletéhez</span><span class="sxs-lookup"><span data-stu-id="393f3-103">Map cost element dimension members to a common set of dimension members</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="393f3-104">Azzal, hogy a különböző költségösszetevő-dimenziótagokat hozzárendeli a költségösszetevő-dimenziótagok egy közös csoportjához, az adatokat egy közös formátumnak megfelelően egyesíti elemzési célokra.</span><span class="sxs-lookup"><span data-stu-id="393f3-104">By mapping different cost element dimension members to a common set of cost element dimension members, you merge data into a common format for analysis purposes.</span></span>

<span data-ttu-id="393f3-105">Ha Ön vállalata egy globális vállalat, és teljesíti a kötelezően előírt számviteli követelményeket, akkor több számlatükröt is használhat.</span><span class="sxs-lookup"><span data-stu-id="393f3-105">If you're a global company and comply with statutory accounting requirements, you might use multiple charts of accounts.</span></span> <span data-ttu-id="393f3-106">Amikor költségösszetevő-dimenziótagokat importál különböző számlatükrökből, előfordulhat, hogy a végén különböző számlái lesznek.</span><span class="sxs-lookup"><span data-stu-id="393f3-106">When you import cost element dimension members from different charts of accounts, you can end up with a mix of accounts.</span></span> <span data-ttu-id="393f3-107">Ezek a számlák azonban lehet, hogy azonos jellegűek, és érdemes a hozzájuk tartozó költségeket közös formátumban elemezni és felosztani.</span><span class="sxs-lookup"><span data-stu-id="393f3-107">However, these accounts might actually have the same nature, and you might want to analyze and allocate costs for them by using a common format.</span></span>

## <a name="map-cost-element-dimension-members-to-a-common-format"></a><span data-ttu-id="393f3-108">Költségösszetevő-dimenziótagok hozzárendelése egy közös formátumhoz</span><span class="sxs-lookup"><span data-stu-id="393f3-108">Map cost element dimension members to a common format</span></span>
<span data-ttu-id="393f3-109">A következő példa azt mutatja meg, hogy Ön költségellenőrként létrehozhat egy olyan új költségösszetevő-dimenziótagot a költségkönyvelésben, amely az egyesült államokbeli számlatükör-struktúrából és a francia számlatükör-struktúrából származó költségösszetevő-dimenziótagokat hozzárendeli a költségösszetevő-dimenziótagok egy közös csoportjához.</span><span class="sxs-lookup"><span data-stu-id="393f3-109">The following example shows how you, as a cost controller, can create a new cost element dimension in Cost accounting that maps cost element dimension members from the US chart of accounts structure and the French chart of accounts structure to a common set of cost element dimension members.</span></span> <span data-ttu-id="393f3-110">A költségösszetevő-dimenziótagok közös csoportjának segítségével elemezheti a két jogi entitás költségkönyvelési főkönyvéből származó költségadatokat.</span><span class="sxs-lookup"><span data-stu-id="393f3-110">You can then use the common set of cost element dimension members to analyze cost data from the two legal entities in a cost accounting ledger.</span></span>

| <span data-ttu-id="393f3-111">Forrás: egyesült államokbeli számlatükrök</span><span class="sxs-lookup"><span data-stu-id="393f3-111">Source: US chart of accounts</span></span>                                          | <span data-ttu-id="393f3-112">Forrás: francia számlatükrök</span><span class="sxs-lookup"><span data-stu-id="393f3-112">Source: French chart of accounts</span></span>                                          | <span data-ttu-id="393f3-113">A költségösszetevő-dimenziótagok új, közös csoportja</span><span class="sxs-lookup"><span data-stu-id="393f3-113">New common set of cost element dimension members</span></span>                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="393f3-114">Egyesült államokbeli számlatükrökből importált költségösszetevő-dimenziótagok</span><span class="sxs-lookup"><span data-stu-id="393f3-114">Imported cost element dimension members from the US chart of accounts</span></span> | <span data-ttu-id="393f3-115">Francia számlatükrökből importált költségösszetevő-dimenziótagok</span><span class="sxs-lookup"><span data-stu-id="393f3-115">Imported cost element dimension members from the French chart of accounts</span></span> | <span data-ttu-id="393f3-116">Egyesült államokbeli és francia költségösszetevő-dimenziótagok hozzárendelése egy közös csoporthoz</span><span class="sxs-lookup"><span data-stu-id="393f3-116">Mapping of US and French cost element dimension members to a common set</span></span> |
| <span data-ttu-id="393f3-117">5001: Értékesítés</span><span class="sxs-lookup"><span data-stu-id="393f3-117">5001: Sales</span></span>                                                           | <span data-ttu-id="393f3-118">5001: Értékesítés és reklám</span><span class="sxs-lookup"><span data-stu-id="393f3-118">5001: Sales and advertising</span></span>                                               | <span data-ttu-id="393f3-119">5000: Értékesítés és reklám</span><span class="sxs-lookup"><span data-stu-id="393f3-119">5000: Sales and advertising</span></span>                                             |
| <span data-ttu-id="393f3-120">5030: Hirdetés</span><span class="sxs-lookup"><span data-stu-id="393f3-120">5030: Advertising</span></span>                                                     | <span data-ttu-id="393f3-121">6390: Készlet beszerzése\*</span><span class="sxs-lookup"><span data-stu-id="393f3-121">6390: Stock purchase\*</span></span>                                                    | <span data-ttu-id="393f3-122">7000: Takarítási költségek</span><span class="sxs-lookup"><span data-stu-id="393f3-122">7000: Cleaning expenses</span></span>                                                 |
| <span data-ttu-id="393f3-123">7001: Takarítási költségek</span><span class="sxs-lookup"><span data-stu-id="393f3-123">7001: Cleaning expenses</span></span>                                               | <span data-ttu-id="393f3-124">7001: Utazási költségek</span><span class="sxs-lookup"><span data-stu-id="393f3-124">7001: Travel expense</span></span>                                                      | <span data-ttu-id="393f3-125">7001: Utazási költségek</span><span class="sxs-lookup"><span data-stu-id="393f3-125">7001: Travel expenses</span></span>                                                   |

<span data-ttu-id="393f3-126">\*A készletbeszerzési francia költségösszetevő-dimenziótag nincs megfeleltetve.</span><span class="sxs-lookup"><span data-stu-id="393f3-126">\*The Stock purchase French cost element dimension member isn't mapped.</span></span>

## <a name="currency-conversion"></a><span data-ttu-id="393f3-127">Pénznemátváltás</span><span class="sxs-lookup"><span data-stu-id="393f3-127">Currency conversion</span></span>
<span data-ttu-id="393f3-128">Az Ön által használt különböző számlatükröket be lehet állítani eltérő pénznemek használatához.</span><span class="sxs-lookup"><span data-stu-id="393f3-128">The various charts of accounts that you use might be set up to use different currencies.</span></span> <span data-ttu-id="393f3-129">Ebben az esetben mindenképpen adja meg a pénznemátváltást úgy, hogy költségadatok feldolgozása a megfelelő pénznem használatával történjen, a költségkönyvelés főkönyvvében meghatározott módon, ahol a költségösszetevő-dimenziótagokat használják.</span><span class="sxs-lookup"><span data-stu-id="393f3-129">In this case, be sure to specify a currency conversion, so that cost data is processed by using the correct currency, as defined in the cost accounting ledger where the cost element dimension members are used.</span></span> <span data-ttu-id="393f3-130">Az előző példában, ha amerikai dollárt (USD) használnak a költségkönyvelés főkönyvében, létre kell hoznia egy pénznemátváltást USD-ről euróra (EUR) a hozzárendelt költségösszetevő-dimenziótagra vonatkozó tranzakciók feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="393f3-130">In the preceding example, if US dollars (USD) are used in the cost accounting ledger, you must create a currency conversion from USD to euros (EUR) to process transactions for the mapped cost element dimension members.</span></span>

## <a name="update-mappings-at-any-time"></a><span data-ttu-id="393f3-131">A hozzárendelések bármikor frissíthetők</span><span class="sxs-lookup"><span data-stu-id="393f3-131">Update mappings at any time</span></span>
<span data-ttu-id="393f3-132">Bármikor frissítheti a költségösszetevő-dimenziókhoz tartozó hozzárendelési definíciókat.</span><span class="sxs-lookup"><span data-stu-id="393f3-132">You can update the mapping definitions for a cost element dimension at any time.</span></span> <span data-ttu-id="393f3-133">Mivel a hozzárendelések érvényessége nem kötődik dátumhoz, a változások akkor lépnek érvénybe, amikor legközelebb dolgoznak fel költségtranzakciókat vagy futtatnak költségszámításokat.</span><span class="sxs-lookup"><span data-stu-id="393f3-133">Because mappings aren't date-effective, changes are applied the next time that you process cost transactions or run cost calculations.</span></span>



