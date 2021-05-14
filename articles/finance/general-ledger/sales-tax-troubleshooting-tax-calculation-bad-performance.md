---
title: Az adószámítás teljesítménye hatással van a tranzakciókra
description: Ez a témakör az adószámítás teljesítményével és a tranzakciókra gyakorolt hatásával kapcsolatos hibaelhárítási információkat tartalmaz.
author: shtao
manager: beya
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ff9d9b80172c3b337737b1cd53b4c56d1befe57
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947653"
---
# <a name="tax-calculation-performance-affects-transactions"></a><span data-ttu-id="b321f-103">Az adószámítás teljesítménye hatással van a tranzakciókra</span><span class="sxs-lookup"><span data-stu-id="b321f-103">Tax calculation performance affects transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b321f-104">Bizonyos esetekben egy tranzakcióra hatással vannak az adószámítást teljesítménybeli problémái.</span><span class="sxs-lookup"><span data-stu-id="b321f-104">Sometimes, a transaction is affected by performance issues that tax calculation is having.</span></span> <span data-ttu-id="b321f-105">A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit.</span><span class="sxs-lookup"><span data-stu-id="b321f-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="review-the-transaction-line-count"></a><span data-ttu-id="b321f-106">Ellenőrizze a tranzakciósorok számát</span><span class="sxs-lookup"><span data-stu-id="b321f-106">Review the transaction line count</span></span>

<span data-ttu-id="b321f-107">Határozza meg, hogy a tranzakcióban nagy számú sor van-e (például több száznál is több).</span><span class="sxs-lookup"><span data-stu-id="b321f-107">Determine whether the transaction has a large number of lines (for example, more than several hundred).</span></span> <span data-ttu-id="b321f-108">Ha nem, lépjen tovább a következő szakaszra.</span><span class="sxs-lookup"><span data-stu-id="b321f-108">If it doesn't, move on to the next section.</span></span> <span data-ttu-id="b321f-109">Ha a tranzakcióban több száz sor van, késleltesse az adószámítást.</span><span class="sxs-lookup"><span data-stu-id="b321f-109">If the transaction does have several hundred lines, delay the tax calculation.</span></span> <span data-ttu-id="b321f-110">A további tudnivalókat lásd: [Késleltetett adószámítás engedélyezése a naplókban](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="b321f-110">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span> 

<span data-ttu-id="b321f-111">Ezután meghatározhatja, hogy teljesülnek-e a következő feltételek:</span><span class="sxs-lookup"><span data-stu-id="b321f-111">Next, you can determine whether any of the following conditions are met:</span></span>

- <span data-ttu-id="b321f-112">Nagy fájlokból importált tranzakciók vannak.</span><span class="sxs-lookup"><span data-stu-id="b321f-112">There are import transactions from large files.</span></span>
- <span data-ttu-id="b321f-113">Több munkamenet ugyanazt a tranzakciós adószámítást egyszerre dolgozza fel.</span><span class="sxs-lookup"><span data-stu-id="b321f-113">Multiple sessions process the same transaction tax calculation at the same time.</span></span>
- <span data-ttu-id="b321f-114">A tranzakciónak több sora van, és a nézetek valós időben frissülnek.</span><span class="sxs-lookup"><span data-stu-id="b321f-114">The transaction has multiple lines, and the views are updated in real time.</span></span> <span data-ttu-id="b321f-115">Például az **Általános napló** lap **Számított áfaösszeg** mezőjét a program valós időben frissíti, amikor egy sor mezői megváltoznak.</span><span class="sxs-lookup"><span data-stu-id="b321f-115">For example, the **Calculated sales tax amount** field on the **General journal** page is updated in real time when a line's fields are changed.</span></span>

   <span data-ttu-id="b321f-116">[![Számított áfaösszeg mezője a Naplóbizonylat oldalon](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="b321f-116">[![Calculated sales tax amount field on the Jounal voucher page](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span></span>

<span data-ttu-id="b321f-117">Ha bármelyik feltétel teljesül, késleltesse az adószámítást.</span><span class="sxs-lookup"><span data-stu-id="b321f-117">If any of these conditions are met, delay the tax calculation.</span></span>

## <a name="review-the-call-stack"></a><span data-ttu-id="b321f-118">A hívásverem áttekintése</span><span class="sxs-lookup"><span data-stu-id="b321f-118">Review the call stack</span></span>

<span data-ttu-id="b321f-119">Tekintse át a hívásvermet annak megállapításához, hogy az adószámítás többször meg van-e hívva.</span><span class="sxs-lookup"><span data-stu-id="b321f-119">Review the call stack to determine whether tax calculation is called multiple times.</span></span> <span data-ttu-id="b321f-120">Ha nem, lépjen tovább a következő szakaszra.</span><span class="sxs-lookup"><span data-stu-id="b321f-120">If it isn't, move on to the next section.</span></span> <span data-ttu-id="b321f-121">Ha a hívásverem többször is meghívott, a következő lépések segítségével csökkentheti az adószámítási időket.</span><span class="sxs-lookup"><span data-stu-id="b321f-121">If the call stack is called multiple times, follow these steps to help reduce the tax calculation times.</span></span>

1. <span data-ttu-id="b321f-122">Ha a napló figyelembe vette a tranzakciót, késleltesse az adószámítást.</span><span class="sxs-lookup"><span data-stu-id="b321f-122">If the journal has considered the transaction, delay the tax calculation.</span></span> <span data-ttu-id="b321f-123">A további tudnivalókat lásd: [Késleltetett adószámítás engedélyezése a naplókban](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="b321f-123">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span>
2. <span data-ttu-id="b321f-124">Ha a tranzakció beszerzési rendelés, és az alkalmazás verziója újabb, mint 10.0.15, akkor az adószámítást elhalaszthatja a végső számításig, ha engedélyezi a **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch** tesztelését.</span><span class="sxs-lookup"><span data-stu-id="b321f-124">If the transaction is a purchase order, and the application version is later than 10.0.15, you can delay the tax calculation until the final calculation by enabling the flighting for **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span></span>

## <a name="review-the-call-stack-timeline"></a><span data-ttu-id="b321f-125">A hívásverem idősorának áttekintése</span><span class="sxs-lookup"><span data-stu-id="b321f-125">Review the call stack timeline</span></span>

<span data-ttu-id="b321f-126">Tekintse át a hívásverem idősorát, és ellenőrizze, hogy felmerülnek-e a következő problémák.</span><span class="sxs-lookup"><span data-stu-id="b321f-126">Review the call stack timeline to determine whether the following issues exist.</span></span> <span data-ttu-id="b321f-127">Ha ezt teszi, engedélyezze a **TaxUncommittedDoIsolateScopeFlighting** tesztelését a probléma megoldásához.</span><span class="sxs-lookup"><span data-stu-id="b321f-127">If they do, enable the flighting for **TaxUncommittedDoIsolateScopeFlighting** to fix the issue.</span></span>

- <span data-ttu-id="b321f-128">A tranzakció következtében a rendszer ne válaszol a munkamenet befejeződéséig.</span><span class="sxs-lookup"><span data-stu-id="b321f-128">The transaction causes the system to stop responding until the session ends.</span></span> <span data-ttu-id="b321f-129">Emiatt a tranzakció nem tudja kiszámítani az adóeredményt.</span><span class="sxs-lookup"><span data-stu-id="b321f-129">Therefore, the transaction can't calculate the tax result.</span></span> <span data-ttu-id="b321f-130">A következő ábra megjeleníti a "Munkamenet befejeződött" üzenetmezőt, ami megjelenik.</span><span class="sxs-lookup"><span data-stu-id="b321f-130">The following illustration shows the "Session ended" message box that you receive.</span></span>

    <span data-ttu-id="b321f-131">[![Munkamenet befejeződött üzenet](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="b321f-131">[![Session ended message](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span></span>

- <span data-ttu-id="b321f-132">A **TaxUncommitted** metódusok több időt vesznek igénybe, mint a többi metódus.</span><span class="sxs-lookup"><span data-stu-id="b321f-132">The **TaxUncommitted** methods take more time than other methods.</span></span> <span data-ttu-id="b321f-133">Például, az alábbi ábrán a **TaxUncommitted::updateTaxUncommitted()** metódus 43 347,42 másodpercet vesz igénybe, a többi metódus azonban 0,09 másodpercet.</span><span class="sxs-lookup"><span data-stu-id="b321f-133">For example, in the following illustration, the **TaxUncommitted::updateTaxUncommitted()** method takes 43,347.42 seconds, but other methods take 0.09 seconds.</span></span>

    <span data-ttu-id="b321f-134">[![Metódusok időtartamai](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="b321f-134">[![Method durations](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span></span>

## <a name="customizing-and-calling-tax-calculation"></a><span data-ttu-id="b321f-135">Adószámítás testreszabása és hívása</span><span class="sxs-lookup"><span data-stu-id="b321f-135">Customizing and calling tax calculation</span></span>

<span data-ttu-id="b321f-136">Testreszabáskor ne hívja meg az adószámítást az **insert()** vagy **update()** metódusnál minden sorhoz.</span><span class="sxs-lookup"><span data-stu-id="b321f-136">When you customize, don't call tax calculation at the **insert()** or **update()** method for each line.</span></span> <span data-ttu-id="b321f-137">Az adószámítást tranzakció szintjén kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="b321f-137">Tax calculation should be called at the transaction level.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="b321f-138">Annak meghatározása, hogy létezik-e testreszabás</span><span class="sxs-lookup"><span data-stu-id="b321f-138">Determine whether customization exists</span></span>

<span data-ttu-id="b321f-139">Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás.</span><span class="sxs-lookup"><span data-stu-id="b321f-139">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="b321f-140">Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.</span><span class="sxs-lookup"><span data-stu-id="b321f-140">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
