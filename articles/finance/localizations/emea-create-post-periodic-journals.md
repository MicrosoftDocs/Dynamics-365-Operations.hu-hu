---
title: Osztott időszakok az időszaki naplókban
description: Ez a témakör ismerteti az időszaki naplókban vagy ismétlődő naplókban használt időszakok felosztása funkciót a Csehországban, Észtországban, Magyarországon, Lettországban, Litvániában, Lengyelországban és Oroszországban levő jogi személyek számára.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 261354
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5ea11e94c188c04c6d3d8ab0173fcc2ba56335c3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408045"
---
# <a name="split-periods-in-periodic-journals"></a><span data-ttu-id="1f9b0-103">Osztott időszakok az időszaki naplókban</span><span class="sxs-lookup"><span data-stu-id="1f9b0-103">Split periods in periodic journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f9b0-104">Az időszaki naplókat olykor ismétlődő naplónak is nevezik, mivel az összeg, a szöveg és más adatok a napló feladásakor minden alkalommal megismétlődnek.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the journal is posted.</span></span> <span data-ttu-id="1f9b0-105">Napló létrehozásakor adja meg az ismétlődéshez tartozó időszakot (pl. nap vagy hónap).</span><span class="sxs-lookup"><span data-stu-id="1f9b0-105">When you create the journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="1f9b0-106">Azoknak az időszakoknak a számát is adja meg, amelyek szerint a napló fel lesz adva.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-106">You also specify the number of periods for which the journal will be posted.</span></span>

<span data-ttu-id="1f9b0-107">Tranzakciósorok többszöri beolvasásához és feladásához használja az **Időszaki naplók** oldalt.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-107">To repeatedly retrieve and post transaction lines, you can use the **Periodic journals** page.</span></span> <span data-ttu-id="1f9b0-108">A Cseh Köztársaság, Észtország, Magyarország, Lettország, Litvánia, Lengyelország és Oroszország területén működő jogi személyek esetében az **Időszaki naplók** oldal az időszaki felosztás funkció révén bővítésre került.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-108">For legal entities in Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, and Russia, the **Periodic journals** page is extended by the split for periods functionality.</span></span> <span data-ttu-id="1f9b0-109">További tudnivalók: [Időszaki naplók feladása](../general-ledger/tasks/post-periodic-journals.md)</span><span class="sxs-lookup"><span data-stu-id="1f9b0-109">For more information, see [Post periodic journals](../general-ledger/tasks/post-periodic-journals.md)</span></span>

### <a name="example-split-for-periods-in-periodic-journals"></a><span data-ttu-id="1f9b0-110">Példa: Időszaki felosztás időszaki naplókban</span><span class="sxs-lookup"><span data-stu-id="1f9b0-110">Example: Split for periods in periodic journals</span></span>

<span data-ttu-id="1f9b0-111">Egy biztosítótársaság egyéves kedvezményt ajánl a szervezetének, ha előre kifizeti a biztosítást.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-111">An insurance company offers your organization a discount for prepaying the insurance policy for an entire year.</span></span> <span data-ttu-id="1f9b0-112">A kifizetést egy eszközszámlán adják fel például előre kifizetett biztosításként.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-112">The payment is posted to an asset account such as prepaid insurance.</span></span> <span data-ttu-id="1f9b0-113">A biztosítás havidíja ezután egész évben csökken egy olyan időszaki napló létrehozásával, amelyhez tartozik egy követelés az előre kifizetett biztosítási számlán, illetve egy tartozás a biztosítási költségszámlán.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-113">You then amortize your monthly insurance expense throughout the year by creating a periodic journal that contains a credit to the prepaid insurance account and a debit to an insurance expense account.</span></span> <span data-ttu-id="1f9b0-114">Ebben az esetben használhatja az időszaki felosztás funkciót.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-114">In this case, you can use the split for periods functionality.</span></span> <span data-ttu-id="1f9b0-115">Kattintson az **Időszaki felosztás** gombra a műveletpanelen a **Időszaki** **naplósorok** oldalon, és adja meg a következő mezőket.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-115">Click the **Split for periods** button on the Action Pane on the **Periodic journal** **lines** page, and then specify the following fields.</span></span>


| <span data-ttu-id="1f9b0-116">Mező</span><span class="sxs-lookup"><span data-stu-id="1f9b0-116">Field</span></span>            | <span data-ttu-id="1f9b0-117">Leírás</span><span class="sxs-lookup"><span data-stu-id="1f9b0-117">Description</span></span>                                                                                                                                                                                             |
|-----------------------|---------------------------------------------------------------|
| <span data-ttu-id="1f9b0-118">**Kezdő dátum**</span><span class="sxs-lookup"><span data-stu-id="1f9b0-118">**Start date**</span></span>        | <span data-ttu-id="1f9b0-119">Válassza ki az első időszakinapló-sorhoz tartozó dátumot.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-119">Select the date for the first periodic journal line.</span></span>                                                                                                                                                        |
| <span data-ttu-id="1f9b0-120">**Időszakok száma**</span><span class="sxs-lookup"><span data-stu-id="1f9b0-120">**Number of periods**</span></span> | <span data-ttu-id="1f9b0-121">Adja meg azon időszakok számát, amelyek alapján felosztja a naplósort.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-121">Enter the number of periods across which to split the journal line.</span></span> <span data-ttu-id="1f9b0-122">Ez az érték határozza meg, hány új tranzakció jön létre.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-122">This value determines how many new transactions are generated.</span></span> <span data-ttu-id="1f9b0-123">A tranzakció összege egyenlően oszlik meg az új tranzakciók között.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-123">The transaction amount is distributed evenly among the new transactions.</span></span> |
| <span data-ttu-id="1f9b0-124">**Egység**</span><span class="sxs-lookup"><span data-stu-id="1f9b0-124">**Unit**</span></span>              | <span data-ttu-id="1f9b0-125">Válassza ki az időszakhoz tartozó mértékegységet.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-125">Select the unit of measure for the period.</span></span>                                                                                                                                                                  |
| <span data-ttu-id="1f9b0-126">**Időszak intervalluma**</span><span class="sxs-lookup"><span data-stu-id="1f9b0-126">**Period interval**</span></span>   | <span data-ttu-id="1f9b0-127">Adja meg a feladási időszakok közötti időközt.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-127">Determine an interval between posting periods.</span></span>                                                                                                                                                              |

<span data-ttu-id="1f9b0-128">Például negyedéves feladások létrehozásához írja a **4**-es számot az **Időszakok száma** mezőbe, válassza a **Hónapok** értéket az **Egység** mezőben, majd írja a **3**-as számot az **Időszak intervalluma** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-128">For example, to generate quarterly postings, enter **4** in the **Number of periods** field, select **Months** in the **Unit** field, and enter **3** in the **Period interval** field.</span></span> <span data-ttu-id="1f9b0-129">A rendszer négy naplósort hoz létre, egyet-egyet a megadott naplósor-összegek egynegyedéhez, 3 hónapos időszakonként.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-129">The system generates four journal lines, each for one fourth of the journal line amount that you entered, at 3-month intervals.</span></span> <span data-ttu-id="1f9b0-130">A főkönyvi naplóban is elérhető hasonló funkcionalitás.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-130">Similar functionality is also available for the general journal.</span></span> <span data-ttu-id="1f9b0-131">Főkönyvi napló sorainak megtekintésekor válassza az **Időszaknapló** &gt; **Napló mentése** elemet.</span><span class="sxs-lookup"><span data-stu-id="1f9b0-131">When viewing general journal lines, select **Period journal** &gt; **Save journal**.</span></span>



