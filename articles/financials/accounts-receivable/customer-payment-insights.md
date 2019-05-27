---
title: Vevőikifizetés-információk (előnézet)
description: Ez a témakör leírja, hogyan segíthet a vevőikifizetés-információk megjósolni egy számla kifizetésének időpontját és segíti a szervezetet optimalizálási stratégiájának létrehozásához, mely javítja a határidőre fizetések arányát.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566244"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="0f2e6-103">Vevőikifizetés-információk (előnézet)</span><span class="sxs-lookup"><span data-stu-id="0f2e6-103">Customer payment insights (preview)</span></span>

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="0f2e6-104">Ez a funkció egy célzott kiadés része, és csak azoknak a felhasználóknak érhető el, akik részt vesznek a Privát előnézet programban.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-104">This feature is part of a targeted release and is only available to users who have opted into the Private Preview.</span></span> <span data-ttu-id="0f2e6-105">Ez a funkció egy, a közeljövőben kiadandó általános rendelkezésre állású verzióban fog szerepelni.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-105">This feature will be included in an upcoming general availability release.</span></span>

# <a name="overview"></a><span data-ttu-id="0f2e6-106">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="0f2e6-106">Overview</span></span>

<span data-ttu-id="0f2e6-107">Szervezetek gyakran nehezen jósolják meg, hogy a vevő mikor fizeti ki a számláikat.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-107">Organizations often find it challenging to predict when a customer will pay their invoices.</span></span> <span data-ttu-id="0f2e6-108">Betekintést hiánya pontatlan pénzforgalmi előrejelzéseket nem hatékony behajtási folyamatokat és rendeléseket kiadását okozhatja olyan vevőknek, akik pénzügyi kockázatot jelentenek.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-108">This lack of insight can lead to inaccurate cash flow forecasts, inefficient collection processes, and the possibility of orders being released to customers who may pose a credit risk.</span></span> <span data-ttu-id="0f2e6-109">A Vevői kifizetés információk (előnézet) gépi tanulással jósolja meg egy számla kifizetését..</span><span class="sxs-lookup"><span data-stu-id="0f2e6-109">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="0f2e6-110">Optimalizálási stratégiákat is kínál, amelyek testreszabhatók, hogy maximalizálni lehessen annak valószínűségét, hogy a vevők időre fizessenek.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-110">It also provides optimization strategies that can be tailored to maximize the probability of customers paying on time.</span></span>

## <a name="predictions"></a><span data-ttu-id="0f2e6-111">Előrejelzések</span><span class="sxs-lookup"><span data-stu-id="0f2e6-111">Predictions</span></span>

<span data-ttu-id="0f2e6-112">Fizetési előrejelzésekhez segítségével a szervezet javíthatja üzleti folyamatait, azáltal, hogy segít:</span><span class="sxs-lookup"><span data-stu-id="0f2e6-112">Payment predictions allow organizations to improve their business processes by helping to:</span></span>

-   <span data-ttu-id="0f2e6-113">Könnyen azonosítani a várhatóan késedelmesen fizetett számlákat.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-113">Easily identify the invoices that are predicted to be paid late.</span></span>
-   <span data-ttu-id="0f2e6-114">Megfelelő intézkedéseket tehessenek, melyek növelik az időre fizetés valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-114">Take appropriate measures to improve chances of getting paid on time.</span></span>

<span data-ttu-id="0f2e6-115">A Vevői kifizetés információk (előnézet) gépi tanulással jósolja meg egy számla kifizetését..</span><span class="sxs-lookup"><span data-stu-id="0f2e6-115">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="0f2e6-116">Korábbi számla- fizetési és a vevői adatok használatával egy számítógépes tanulási modellt hoz létre, mellyel megjósolható a számla fizetésének időpontja.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-116">It uses historical invoice, payment, and customer data to create a machine learning model that is used to predict when an invoice will be paid.</span></span>

<span data-ttu-id="0f2e6-117">Minden nyitott számla esetében a Vevői fizetési információk (előnézet) három fizetési valószínűséget jósol:</span><span class="sxs-lookup"><span data-stu-id="0f2e6-117">For each open invoice, Customer payment insights (preview) predicts three payment probabilities:</span></span>

-  <span data-ttu-id="0f2e6-118">Kifizetés időben valószínűsége ( a számla esedékességi dátumán belül).</span><span class="sxs-lookup"><span data-stu-id="0f2e6-118">Probability of payment being made on time (within the invoice due date).</span></span>
-  <span data-ttu-id="0f2e6-119">Kifizetés valószínűsége a lejárattól számított 30 napon belül.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-119">Probability of payment being made within 30 days of the invoice due date.</span></span>
-  <span data-ttu-id="0f2e6-120">Kifizetés valószínűsége a lejárattól számított 30 napon túl.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-120">Probability of payment being made beyond 30 days of the invoice due date.</span></span>

<span data-ttu-id="0f2e6-121">A kifizetések valószínűsége az előrejelzés szakaszban tekinthetők meg.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-121">The probability of payments can be viewed in the prediction section.</span></span>

<span data-ttu-id="0f2e6-122">[![Fizetési előrejelzések](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span><span class="sxs-lookup"><span data-stu-id="0f2e6-122">[![Payment predictions](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span></span>

<span data-ttu-id="0f2e6-123">Minden számlához hozzárendeli a legjobb fizetési valószínűséget a fent meghatározott három előre jelzett fizetési valószínűségek közül.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-123">Each invoice is also assigned a winning probability of payment using one of the three predicted payment probabilities scenarios defined above.</span></span> <span data-ttu-id="0f2e6-124">A legnagyobb fizetési valószínűséggel rendelkező eset a nyertes eset.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-124">The scenario with the highest probability of payment is the winning scenario.</span></span>


<span data-ttu-id="0f2e6-125">Például tegyük fel, hogy egy számlához az előrejelzés szerint 71 százalékos valószínűsége, hogy a számla fizetése időben történik a 13 százalékos valószínűsége, hogy a számla kifizetése az esedékességi dátumot követő 30 napon belül történik, és 16 százalékos valószínűsége, hogy a számla fizetése az esedékességi dátumot követő 30 napon túl történik.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-125">For example, let’s assume for an invoice the prediction shows a 71 percent probability that the invoice will be paid on time, 13 percent probability that the invoice will be paid within 30 days of due date, and 16 percent probability that the invoice will be paid beyond 30 days of the due date.</span></span> <span data-ttu-id="0f2e6-126">A legnagyobb valószínűséggel a számla ki lesz időben fizetve helyzetnek van, így a számlát valószínűleg időben kifizetve címkét kap.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-126">The highest probability shows that the invoice will be in the on-time scenario, so the invoice will be tagged with the probability of being paid on time.</span></span>

<span data-ttu-id="0f2e6-127">[![Fizetési előrejelzések](./media/payment-predict.png)](./media/payment-predict.png)</span><span class="sxs-lookup"><span data-stu-id="0f2e6-127">[![Payment predictions](./media/payment-predict.png)](./media/payment-predict.png)</span></span>

## <a name="optimization-strategies"></a><span data-ttu-id="0f2e6-128">Optimalizálási stratégiák</span><span class="sxs-lookup"><span data-stu-id="0f2e6-128">Optimization strategies</span></span>

<span data-ttu-id="0f2e6-129">Kívül fizetési előrejelzéseken túl a Vevői kifizetési információk (előnézet) használatával optimalizálási stratégiákkal javíthatja az időben fizetés valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-129">In addition to payment predictions, the Customer Payment Insights (preview) can use optimization strategies to improve the chances of getting paid on time.</span></span> <span data-ttu-id="0f2e6-130">Ez lehetővé teszi a szervezeteknek egy"Mi történik, ha" elemzés elvégzését. úgy, hogy a felhasználóknak megengedi számla és a vevői paraméterek beállítását, és azok hatásának elemzését az időbeni számlafizetés valószínűségére</span><span class="sxs-lookup"><span data-stu-id="0f2e6-130">This lets organizations do 'What if' analysis by allowing users to adjust invoice and customer parameters and then compare the corresponding effect on the probability of receiving payment on invoices on time.</span></span>

<span data-ttu-id="0f2e6-131">Például egy szervezet szeretné kiértékelni, hogy milyen hatással lenne a készpénzfizetési engedmény frissítése a számlákon az időben történő kifizetés valószínűségére.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-131">For example, an organization may want to evaluate the effect of updating the cash discount on invoices on the probability of receiving the payment on time.</span></span> <span data-ttu-id="0f2e6-132">Amikor számlák optimalizálva vannak az új engedmény használata, a felhasználók áttekinthetik az engedmény alkalmazásnak hatását ezen számlák időben történő kifizetésének valószínűségére.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-132">When the invoices are optimized to use the new discount, the users can review the effect of applying the discount on the probability of receiving payments for those invoices on time.</span></span> <span data-ttu-id="0f2e6-133">Ha az engedmény alkalmazásának költsége minimális az időben történő kifizetés előnyeihez képest esetén a vállalat dönthet a kijelölt engedmény alkalmazása mellett az összes jövőbeni nyitott rendelésre.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-133">If the cost of applying the discount is minimal when compared to the benefit of collecting the payment on time, the organization may choose to apply the selected discount to all future open orders.</span></span>

> [!NOTE] 
> <span data-ttu-id="0f2e6-134">Jelenleg csak az engedmény érhető el optimalizálási stratégiának.a Vevői kifizetés információk (előnézet) funkcióban.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-134">Currently, only discount is available as an optimization strategy for Customer payment insights (preview).</span></span>

<span data-ttu-id="0f2e6-135">[![Optimalizált előrejelzések](./media/optimized-pay.png)](./media/optimized-pay.png)</span><span class="sxs-lookup"><span data-stu-id="0f2e6-135">[![Optimized predictions](./media/optimized-pay.png)](./media/optimized-pay.png)</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="0f2e6-136">Vevőikifizetés-információk (előnézet) lekérése</span><span class="sxs-lookup"><span data-stu-id="0f2e6-136">How to get Customer payment insights (preview)</span></span>

<span data-ttu-id="0f2e6-137">Ha szeretné kipróbálni a vevőikifizetés-információkat (előnézet) lépett fel, kérjük, írjon e-mailt a [Pénzügyi információk előnézet csapatnak](mailto:fiap@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0f2e6-137">If you are interested in trying Customer payment insights (preview), please email [Finance Insights Preview team](mailto:fiap@microsoft.com).</span></span> 

## <a name="privacy-statement"></a><span data-ttu-id="0f2e6-138">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="0f2e6-138">Privacy Statement</span></span>

<span data-ttu-id="0f2e6-139">Az előnézetek az Egyesült Államokban tárolják az ügyféladatokat.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-139">Previews store customer data in the United States.</span></span> <span data-ttu-id="0f2e6-140">Mindemellett az előnézetek (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmaznak, mint a Dynamics 365 for Finance and Operations szolgáltatás (2) és nem tartalmazza s szolgáltatásiszint szerződés ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="0f2e6-140">In addition, previews (1) may utilize less privacy and security measures than the Dynamics 365 for Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>
