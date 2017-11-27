---
title: "Osztott időszakok időszaki naplókban"
description: "Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok a napló feladásakor minden alkalommal megismétlődnek. Napló létrehozásakor adja meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap). Azoknak az időszakoknak a számát is adja meg, amelyek szerint a napló fel lesz adva."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261354
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 73ccfc906e8d7a91e7bae5ae21d9ddad9d58f109
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="split-periods-in-periodic-journals"></a><span data-ttu-id="eebb8-105">Osztott időszakok időszaki naplókban</span><span class="sxs-lookup"><span data-stu-id="eebb8-105">Split periods in periodic journals</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="eebb8-106">Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok a napló feladásakor minden alkalommal megismétlődnek.</span><span class="sxs-lookup"><span data-stu-id="eebb8-106">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the journal is posted.</span></span> <span data-ttu-id="eebb8-107">Napló létrehozásakor adja meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap).</span><span class="sxs-lookup"><span data-stu-id="eebb8-107">When you create the journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="eebb8-108">Azoknak az időszakoknak a számát is adja meg, amelyek szerint a napló fel lesz adva.</span><span class="sxs-lookup"><span data-stu-id="eebb8-108">You also specify the number of periods for which the journal will be posted.</span></span>

<span data-ttu-id="eebb8-109">Tranzakciósorok többszöri beolvasásához és feladásához használja az **Időszaki naplók** oldalt.</span><span class="sxs-lookup"><span data-stu-id="eebb8-109">To repeatedly retrieve and post transaction lines, you can use the **Periodic journals** page.</span></span> <span data-ttu-id="eebb8-110">A Cseh Köztársaság, Észtország, Magyarország, Lettország, Litvánia, Lengyelország és Oroszország területén működő jogi személyek esetében az **Időszaki naplók** oldal az időszaki felosztás funkció révén bővítésre került.</span><span class="sxs-lookup"><span data-stu-id="eebb8-110">For legal entities in Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, and Russia, the **Periodic journals** page is extended by the split for periods functionality.</span></span> <span data-ttu-id="eebb8-111">További tudnivalókért lásd: [Időszaki napló feladása](../general-ledger/tasks/post-periodic-journals.md)</span><span class="sxs-lookup"><span data-stu-id="eebb8-111">For more information, see [Post a periodic journal](../general-ledger/tasks/post-periodic-journals.md)</span></span>

### <a name="example-split-for-periods-in-periodic-journals"></a><span data-ttu-id="eebb8-112">Példa: Időszaki felosztás időszaki naplókban</span><span class="sxs-lookup"><span data-stu-id="eebb8-112">Example: Split for periods in periodic journals</span></span>

<span data-ttu-id="eebb8-113">Egy biztosítótársaság egyéves kedvezményt ajánl a szervezetének, ha előre kifizeti a biztosítást.</span><span class="sxs-lookup"><span data-stu-id="eebb8-113">An insurance company offers your organization a discount for prepaying the insurance policy for an entire year.</span></span> <span data-ttu-id="eebb8-114">A kifizetést egy eszközszámlán adják fel például előre kifizetett biztosításként.</span><span class="sxs-lookup"><span data-stu-id="eebb8-114">The payment is posted to an asset account such as prepaid insurance.</span></span> <span data-ttu-id="eebb8-115">A biztosítás havidíja ezután egész évben csökken egy olyan időszaki napló létrehozásával, amelyhez tartozik egy követelés az előre kifizetett biztosítási számlán, illetve egy tartozás a biztosítási költségszámlán.</span><span class="sxs-lookup"><span data-stu-id="eebb8-115">You then amortize your monthly insurance expense throughout the year by creating a periodic journal that contains a credit to the prepaid insurance account and a debit to an insurance expense account.</span></span> <span data-ttu-id="eebb8-116">Ebben az esetben használhatja az időszaki felosztás funkciót.</span><span class="sxs-lookup"><span data-stu-id="eebb8-116">In this case, you can use the split for periods functionality.</span></span> <span data-ttu-id="eebb8-117">Kattintson az **Időszaki felosztás** gombra a műveletpanelen a **Időszaki** **naplósorok** oldalon, és adja meg a következő mezőket.</span><span class="sxs-lookup"><span data-stu-id="eebb8-117">Click the **Split for periods** button on the Action Pane on the **Periodic journal** **lines** page, and then specify the following fields.</span></span>

|                       |                                                                                                                                                                                                             |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="eebb8-118">**Mező**</span><span class="sxs-lookup"><span data-stu-id="eebb8-118">**Field**</span></span>             | <span data-ttu-id="eebb8-119">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="eebb8-119">**Description**</span></span>                                                                                                                                                                                             |
| <span data-ttu-id="eebb8-120">**Kezdő dátum**</span><span class="sxs-lookup"><span data-stu-id="eebb8-120">**Start date**</span></span>        | <span data-ttu-id="eebb8-121">Válassza ki az első időszakinapló-sorhoz tartozó dátumot.</span><span class="sxs-lookup"><span data-stu-id="eebb8-121">Select the date for the first periodic journal line.</span></span>                                                                                                                                                        |
| <span data-ttu-id="eebb8-122">**Időszakok száma**</span><span class="sxs-lookup"><span data-stu-id="eebb8-122">**Number of periods**</span></span> | <span data-ttu-id="eebb8-123">Adja meg azon időszakok számát, amelyek alapján felosztja a naplósort.</span><span class="sxs-lookup"><span data-stu-id="eebb8-123">Enter the number of periods across which to split the journal line.</span></span> <span data-ttu-id="eebb8-124">Ez az érték határozza meg, hány új tranzakció jön létre.</span><span class="sxs-lookup"><span data-stu-id="eebb8-124">This value determines how many new transactions are generated.</span></span> <span data-ttu-id="eebb8-125">A tranzakció összege egyenlően oszlik meg az új tranzakciók között.</span><span class="sxs-lookup"><span data-stu-id="eebb8-125">The transaction amount is distributed evenly among the new transactions.</span></span> |
| <span data-ttu-id="eebb8-126">**Egység**</span><span class="sxs-lookup"><span data-stu-id="eebb8-126">**Unit**</span></span>              | <span data-ttu-id="eebb8-127">Válassza ki az időszakhoz tartozó mértékegységet.</span><span class="sxs-lookup"><span data-stu-id="eebb8-127">Select the unit of measure for the period.</span></span>                                                                                                                                                                  |
| <span data-ttu-id="eebb8-128">**Időszak intervalluma**</span><span class="sxs-lookup"><span data-stu-id="eebb8-128">**Period interval**</span></span>   | <span data-ttu-id="eebb8-129">Adja meg a feladási időszakok közötti időközt.</span><span class="sxs-lookup"><span data-stu-id="eebb8-129">Determine an interval between posting periods.</span></span>                                                                                                                                                              |

<span data-ttu-id="eebb8-130">Például negyedéves feladások létrehozásához írja a **4**-es számot az **Időszakok száma** mezőbe, válassza a **Hónapok** értéket az **Egység** mezőben, majd írja a **3**-as számot az **Időszak intervalluma** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="eebb8-130">For example, to generate quarterly postings, enter **4** in the **Number of periods** field, select **Months** in the **Unit** field, and enter **3** in the **Period interval** field.</span></span> <span data-ttu-id="eebb8-131">A rendszer négy naplósort hoz létre, egyet-egyet a megadott naplósor-összegek egynegyedéhez, 3 hónapos időszakonként.</span><span class="sxs-lookup"><span data-stu-id="eebb8-131">The system generates four journal lines, each for one fourth of the journal line amount that you entered, at 3-month intervals.</span></span> <span data-ttu-id="eebb8-132">A főkönyvi naplóban is elérhető hasonló funkcionalitás.</span><span class="sxs-lookup"><span data-stu-id="eebb8-132">Similar functionality is also available for the general journal.</span></span> <span data-ttu-id="eebb8-133">Főkönyvi napló sorainak megtekintésekor válassza az **Időszaknapló** &gt; **Napló mentése** elemet.</span><span class="sxs-lookup"><span data-stu-id="eebb8-133">When viewing general journal lines, select **Period journal** &gt; **Save journal**.</span></span>




