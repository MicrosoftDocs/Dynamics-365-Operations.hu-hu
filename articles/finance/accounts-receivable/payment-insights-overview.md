---
title: Vevő fizetési információi (Előzetes)
description: Ez a témakör bemutatja az egyes vevők szokásos fizetési gyakorlatának megértését elősegítő fizetési betekintő információkkal kapcsolatos lehetőséget, amellyel olyan körülményeket is meghatározhat, amelyek indokolttá teszik a beszedési folyamatok elindítását a megszokottnál korábban.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773970"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="6bd63-103">Vevő fizetési információi (Előzetes)</span><span class="sxs-lookup"><span data-stu-id="6bd63-103">Customer payment insights (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6bd63-104">Ez a témakör bemutatja az egyes vevők szokásos fizetési gyakorlatának megértését elősegítő fizetési betekintő információkkal kapcsolatos lehetőséget, amellyel olyan körülményeket is meghatározhat, amelyek indokolttá teszik a beszedési folyamatok elindítását a megszokottnál korábban.</span><span class="sxs-lookup"><span data-stu-id="6bd63-104">This topic describes the payment insights capability that helps improve understanding of individual customers' typical payment practices and that can identify circumstances that justify initiating collection processes earlier than you might have done otherwise.</span></span> 

## <a name="overview"></a><span data-ttu-id="6bd63-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="6bd63-105">Overview</span></span>

<span data-ttu-id="6bd63-106">Szervezetek gyakran nehezen jósolják meg, hogy a vevők mikor fizetik ki a számláikat.</span><span class="sxs-lookup"><span data-stu-id="6bd63-106">Organizations often find it challenging to predict when customers will pay their invoices.</span></span> <span data-ttu-id="6bd63-107">A háttérinformációk hiánya kevésbé pontos pénzforgalmi előrejelzéseket eredményezhet, túl későn elinduló beszedési folyamatokat, valamint rendelések kiadását olyan vevőknek, akik elmulaszthatják a kifizetést.</span><span class="sxs-lookup"><span data-stu-id="6bd63-107">This lack of insight leads to less accurate cash flow forecasts, collections processes that start too late, and orders that are released to customers who may default on their payment.</span></span> <span data-ttu-id="6bd63-108">A Vevői kifizetésre vonatkozó háttérinformációk (előzetes verzió) segítségével megjósolhatja egy vevői számla kifizetésének időpontját és segíthet a szervezetnek az optimalizálási stratégia létrehozásában, amely javítja a határidőre fizetések arányát.</span><span class="sxs-lookup"><span data-stu-id="6bd63-108">Customer payment insights (Preview) helps organizations predict when a customer invoice will be paid, helping organization create collections strategies that improve the probability of being paid on time.</span></span> 

## <a name="predictions"></a><span data-ttu-id="6bd63-109">Előrejelzések</span><span class="sxs-lookup"><span data-stu-id="6bd63-109">Predictions</span></span>

<span data-ttu-id="6bd63-110">A kifizetési előrejelzések lehetővé teszik a szervezetek számára, hogy javítsák az üzleti folyamataikat, mivel így könnyebben azonosíthatják azokat a számlákat, amelyeket valószínűleg késve fizetnek, és hogy a megfelelő intézkedéseket megtegyék, hogy javítsák az idejüket az időben történő kifizetésre.</span><span class="sxs-lookup"><span data-stu-id="6bd63-110">Payment predictions will enable organizations to improve their business processes by helping them easily identify the invoices that are likely to be paid late, and to take appropriate measures that improve their chances of getting paid on time.</span></span>

<span data-ttu-id="6bd63-111">Egy gépi tanulási modellt alkalmaznak, amely a múltbeli számlákat, a kifizetéseket és a vevői adatokat használja fel, a vevői kifizetéssel kapcsolatos háttériformációk (előzetes verzió) pontosabban jósolja meg, ha a vevő mikor fizeti ki a kiegyenlítetlen számlát.</span><span class="sxs-lookup"><span data-stu-id="6bd63-111">Using a machine learning model, which leverages historical invoices, payments and customer data, Customer payment insights (Preview) more accurately predicts when a customer will pay an outstanding invoice.</span></span>

<span data-ttu-id="6bd63-112">Minden nyitott számla esetében a Vevői fizetési háttérinformációk (előzetes verzió) három fizetési valószínűséget jósol:</span><span class="sxs-lookup"><span data-stu-id="6bd63-112">For each open invoice, Customer payment insights (Preview) predicts three payment probabilities:</span></span>

-   <span data-ttu-id="6bd63-113">Időben történő fizetés valószínűsége</span><span class="sxs-lookup"><span data-stu-id="6bd63-113">Probability of payment being made on time</span></span> 
-   <span data-ttu-id="6bd63-114">Késve történő fizetés valószínűsége</span><span class="sxs-lookup"><span data-stu-id="6bd63-114">Probability of payment being made late</span></span>
-   <span data-ttu-id="6bd63-115">Nagyon késedelmesen történő fizetés valószínűsége</span><span class="sxs-lookup"><span data-stu-id="6bd63-115">Probability of payment being made very late</span></span>

<span data-ttu-id="6bd63-116">Annak érdekében, hogy a szervezetek megértsék a három kategória egyikében a vevőtől elvárható teljes kifizetett összeget, az időben, későn és nagyon későn kategóriákban, a vevői kifizetéssel kapcsolatos háttérinformációk (előzetes verzió) a várható kifizetések összesített megjelenítését is lehetővé teszi.</span><span class="sxs-lookup"><span data-stu-id="6bd63-116">To help Organizations understand the total payment amount they can expect from a customer in one of the three buckets, On time, Late and Very late, Customer payment insights (Preview) also provides an aggregated view of expected payments.</span></span>

<span data-ttu-id="6bd63-117">[![Kifizetési előrejelzések összesített nézete](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span><span class="sxs-lookup"><span data-stu-id="6bd63-117">[![Aggregated view of payment predictions](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span></span>

<span data-ttu-id="6bd63-118">Ezenkívül minden számlához hozzárendeli a rendszer az időben való fizetés valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="6bd63-118">Also, each invoice is assigned a probability of payment on time.</span></span> <span data-ttu-id="6bd63-119">Ha az időben való fizetés valószínűsége 50%-nál alacsonyabb, akkor a rendszer a számlát piros körrel jelöli meg, amellyel jelzi, hogy ezekre a számlákra a beszedés fokozott figyelme szükséges.</span><span class="sxs-lookup"><span data-stu-id="6bd63-119">If the probability of payment on time is less than 50%, the invoices are tagged with a red circle to  indicate that these invoices may require collections attention.</span></span> 

<span data-ttu-id="6bd63-120">[![Kifizetési valószínűségek listája](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span><span class="sxs-lookup"><span data-stu-id="6bd63-120">[![List of payment probabilities](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span></span>

<span data-ttu-id="6bd63-121">A vevői kifizetésre vonatkozó háttérinformációk (előzetes verzió) környezeti információkat is nyújt az előrejelzés magyarázataként, például az előrejelzést leginkább befolyásoló tényezők, a vevővel folytatott üzleti kapcsolat aktuális állapota, valamint részletek a múltbéli vevői kifizetési viselkedésről.</span><span class="sxs-lookup"><span data-stu-id="6bd63-121">Customer Payment Insights (Preview) also provides contextual information to explain the prediction, such as the top factors that influenced the predictions, the current state of business with the customer, and details about the historical customer payment behavior.</span></span> <span data-ttu-id="6bd63-122">A beszedési folyamat számos vállalkozásban reaktív tevékenység volt; a beszedési folyamat addig nem kezdődik, amíg a számlák esedékessé nem válnak.</span><span class="sxs-lookup"><span data-stu-id="6bd63-122">In many businesses, the collections process has been a reactive activity; the collections process doesn’t start until invoices come due.</span></span> 

<span data-ttu-id="6bd63-123">A vevői kifizetésekkel kapcsolatos háttérinformációk (előzetes verzió) segítségével a vállalatok proaktívabban kezelhetik a beszedéseket.</span><span class="sxs-lookup"><span data-stu-id="6bd63-123">With Customer payment insights (Preview), organizations can be more proactive about collections.</span></span> <span data-ttu-id="6bd63-124">A programnak már nem kell megvárnia a beszedési folyamat elkezdéséhez, hogy a tranzakciók esedékessé váljanak.</span><span class="sxs-lookup"><span data-stu-id="6bd63-124">They no longer have to wait for the transactions to become due to start the collection process.</span></span> <span data-ttu-id="6bd63-125">Helyette a fizetési előrejelzési képességgel meghatározhatja, hogy a proaktív beszedések javítják-e az időben történő fizetés valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="6bd63-125">Instead, they can use the payment prediction capability to determine whether proactive collections will improve the probability of being paid on time.</span></span> <span data-ttu-id="6bd63-126">A kifizetés előrejelzése azt is lehetővé teszi a vállalatok számára, hogy rendelkezzenek a beszedési folyamat korai megkezdéséhez szükséges információkkal.</span><span class="sxs-lookup"><span data-stu-id="6bd63-126">Payment prediction also gives businesses the information needed to justify starting the collection process early.</span></span>

## <a name="methodology"></a><span data-ttu-id="6bd63-127">Módszertan</span><span class="sxs-lookup"><span data-stu-id="6bd63-127">Methodology</span></span>

<span data-ttu-id="6bd63-128">Az AI-megoldások fejlesztése és bevezetése nehéz.</span><span class="sxs-lookup"><span data-stu-id="6bd63-128">Developing and deploying an AI solution is hard.</span></span> <span data-ttu-id="6bd63-129">Adatszakértők, adott téma szakértői és mérnökök csapatára van szükség, akik egy hosszabb ideig dolgoznak egy használható AI-megoldás kialakításán, fejlesztésén, üzembe helyezésén és karbantartásán.</span><span class="sxs-lookup"><span data-stu-id="6bd63-129">It takes a team of data scientists, subject matter experts and engineers, working for an extended period of time to formulate, develop, deploy and maintain a usable AI solution.</span></span> <span data-ttu-id="6bd63-130">Az AI-megoldások a Finance modulban egyszerűen telepíthetők és használhatók.</span><span class="sxs-lookup"><span data-stu-id="6bd63-130">We are making it easy to deploy and use AI solutions in Finance.</span></span> <span data-ttu-id="6bd63-131">A Microsoft AI Builder tetejére épülő AI megoldásokat építünk be a Finance szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="6bd63-131">We are prepackaging AI solutions in Finance that are built on top of Microsoft AI Builder.</span></span> <span data-ttu-id="6bd63-132">Egy végfelhasználó egyetlen kattintással telepítheti az AI-megoldást, és elindíthatja az intelligens előrejelzések előnyeinek kihasználását.</span><span class="sxs-lookup"><span data-stu-id="6bd63-132">An end user, with the single click of button, can deploy the AI solution and start leveraging the benefits of intelligent predictions.</span></span> <span data-ttu-id="6bd63-133">Ha egy szervezet nem elégedett az előrejelzések pontosságával, egy kiemelt felhasználó, szintén egy kattintással újra beléphet az AI Builder bővítmény gyakorlatába, majd kiválaszthatja vagy törölheti azon mezők kiválasztását, amiket az előrejelzések létrehozásához szeretne használni.</span><span class="sxs-lookup"><span data-stu-id="6bd63-133">If an organization isn't satisfied with the accuracy of predictions, a power user, again using a single click, can enter the AI builder extension experience, and then select or deselect the fields used to generate predictions.</span></span> <span data-ttu-id="6bd63-134">Ha készen áll, betaníthatják és közzétehetik a módosításokat, és az újonnan kiképzett modellt a rendszer automatikusan felveszi az előrejelzésekhez a Finance szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="6bd63-134">Once ready, they can train and publish the changes, and the newly trained model will be automatically picked up for predictions in Finance.</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="6bd63-135">Hogyan szerezhetem be a Vevői fizetéssel kapcsolatos háttérinformációk (előzetes verzió) szolgáltatást</span><span class="sxs-lookup"><span data-stu-id="6bd63-135">How to get Customer payment insights (Preview)</span></span>

<span data-ttu-id="6bd63-136">Írjon e-mailt a [Vevői kifizetéssel kapcsolatos háttérinformációk (előzetes verzió)](mailto:fiap@microsoft.com) számára, ha szeretné kipróbálni a Vevői kifizetéssel kapcsolatos háttérinformációk (előzetes verzió) szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="6bd63-136">Please send email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in trying the Customer payment insights (Preview).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="6bd63-137">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="6bd63-137">Privacy Notice</span></span>

<span data-ttu-id="6bd63-138">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmaznak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="6bd63-138">Previews (1) may utilize less privacy and security measures than the Dynamics 365 Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>


