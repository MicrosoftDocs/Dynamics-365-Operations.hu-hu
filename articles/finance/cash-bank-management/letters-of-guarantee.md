---
title: Garancialevelek
description: Ez a cikk a garancia levelekkel kapcsolatban tartalmaz információkat. A garancialevélben a bank elfogadja, hogy egy bizonyos pénzösszeget fizet egy személynek, amennyiben a bank egy ügyfele késik a fizetéssel vagy nem teljesíti a megnevezett személy felé a kötelezettségeit.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: roschlom
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b86ccc46475babb302cdbf82f5c99c26e2091501
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978789"
---
# <a name="letters-of-guarantee"></a><span data-ttu-id="e27ac-104">Garancialevelek</span><span class="sxs-lookup"><span data-stu-id="e27ac-104">Letters of guarantee</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e27ac-105">Ez a cikk a garancia levelekkel kapcsolatban tartalmaz információkat.</span><span class="sxs-lookup"><span data-stu-id="e27ac-105">This article provides information about letters of guarantee.</span></span> <span data-ttu-id="e27ac-106">A garancialevélben a bank elfogadja, hogy egy bizonyos pénzösszeget fizet egy személynek, amennyiben a bank egy ügyfele késik a fizetéssel vagy nem teljesíti a megnevezett személy felé a kötelezettségeit.</span><span class="sxs-lookup"><span data-stu-id="e27ac-106">In a letter of guarantee, a bank agrees to pay a specific amount of money to a person if one of the bank's customers defaults on a payment or obligation to that person.</span></span> 

<span data-ttu-id="e27ac-107">A garancialevél egy bank (kezes) megállapodása, vállalja egy megadott pénzösszeg kifizetését egy személynek (kedvezményezettnek), ha a bank ügyfele (meghatalmazott) kihagy egy befizetést vagy egy kötelezettséget a kedvezményezett irányába.</span><span class="sxs-lookup"><span data-stu-id="e27ac-107">A letter of guarantee is an agreement by a bank (the guarantor) to pay a set amount of money to some person (the beneficiary) if a bank customer (the principal) defaults on a payment or an obligation to the beneficiary.</span></span> <span data-ttu-id="e27ac-108">A garancialevelek nem átruházhatóak.</span><span class="sxs-lookup"><span data-stu-id="e27ac-108">Letters of guarantee aren't transferable.</span></span> <span data-ttu-id="e27ac-109">Csak a megállapodásban foglalt kedvezményezettre érvényesek.</span><span class="sxs-lookup"><span data-stu-id="e27ac-109">They apply only to the beneficiary who is named in the agreement.</span></span> <span data-ttu-id="e27ac-110">A meghatalmazott kérelmezhet növekedést vagy csökkentést a garancialevél értékén, a megállapodás feltételei szerint.</span><span class="sxs-lookup"><span data-stu-id="e27ac-110">The principal can request an increase or decrease in the value of a letter of guarantee, subject to the terms of the agreement.</span></span> 

<span data-ttu-id="e27ac-111">A garancialevél kiegyenlítéséhez a kedvezményezettnek be kell küldenie az eredeti garancialevelet, és a lejárat dátumát megelőzően tájékoztatnia kell a garancianyújtó bankját.</span><span class="sxs-lookup"><span data-stu-id="e27ac-111">To liquidate a letter of guarantee, the beneficiary must submit the original letter of guarantee and inform the bank of the principal’s default before the expiration date.</span></span> <span data-ttu-id="e27ac-112">A bank ekkor a garancialevélnek megfelelően átutalja az esedékes összeget a kedvezményezett számlájára.</span><span class="sxs-lookup"><span data-stu-id="e27ac-112">The bank then pays the amount that is due to the beneficiary's account, according to the terms in the letter of guarantee.</span></span> <span data-ttu-id="e27ac-113">A bank lefoglalja a fizetés egy százalékát haszonént.</span><span class="sxs-lookup"><span data-stu-id="e27ac-113">The bank reserves a percentage of the payment as a margin.</span></span> <span data-ttu-id="e27ac-114">Ez a százalék a megállapodás feltételeiben meghatározott.</span><span class="sxs-lookup"><span data-stu-id="e27ac-114">The percentage is agreed upon and specified in the terms of the agreement.</span></span> 

<span data-ttu-id="e27ac-115">Garancialevél céljának nyomon követésére kódot is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="e27ac-115">You can create a code to track the purpose of a letter of guarantee.</span></span> <span data-ttu-id="e27ac-116">Megadhatja a garancialevél visszavonása esetén társítható indokokat is.</span><span class="sxs-lookup"><span data-stu-id="e27ac-116">You can also specify the reasons that can be associated with a letter of guarantee when the letter is canceled.</span></span> <span data-ttu-id="e27ac-117">Megtekintheti a célkódokat és a bank okkódokat a **Kifizetés célkódjai** és a **Banki okkódok** oldalakon.</span><span class="sxs-lookup"><span data-stu-id="e27ac-117">You can view the purpose codes and bank reasons on the **Payment purpose codes** and **Bank reasons** pages.</span></span> 

<span data-ttu-id="e27ac-118">Használhatja a **Garancialevél** oldalt a következő feladatok végrehajtásakor:</span><span class="sxs-lookup"><span data-stu-id="e27ac-118">You can use the **Letter of guarantee** page to complete these tasks:</span></span>

-   <span data-ttu-id="e27ac-119">Megfelelő főkönyvi bejegyzések létrehozása, és a manuális adatbevitel kiküszöbölése.</span><span class="sxs-lookup"><span data-stu-id="e27ac-119">Create correct ledger entries, and eliminate manual entry.</span></span>
-   <span data-ttu-id="e27ac-120">Az összes pénzügyi és nem pénzügyi tranzakció rögzítése és a garancialevelek egyenlegeinek nyomon követése.</span><span class="sxs-lookup"><span data-stu-id="e27ac-120">Record all monetary and nonmonetary transactions, and track balances of letters of guarantee.</span></span>
-   <span data-ttu-id="e27ac-121">A garancialevelek lejáratának rögzítése és nyomon követése.</span><span class="sxs-lookup"><span data-stu-id="e27ac-121">Record and track the status and expiration of letters of guarantee.</span></span>
-   <span data-ttu-id="e27ac-122">Garancialevelet használó bankokat felsoroló jelentés készítése.</span><span class="sxs-lookup"><span data-stu-id="e27ac-122">Generate a report that lists the banks that are holding letters of guarantee.</span></span>

<span data-ttu-id="e27ac-123">A következő táblázat leírja a garancialevelen végrehajtható műveleteket.</span><span class="sxs-lookup"><span data-stu-id="e27ac-123">The following table describes the actions that you can perform on a letter of guarantee.</span></span>

| <span data-ttu-id="e27ac-124">Művelet</span><span class="sxs-lookup"><span data-stu-id="e27ac-124">Action</span></span>              | <span data-ttu-id="e27ac-125">Cél</span><span class="sxs-lookup"><span data-stu-id="e27ac-125">Purpose</span></span>                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e27ac-126">Elküldés a banknak</span><span class="sxs-lookup"><span data-stu-id="e27ac-126">Submit to bank</span></span>      | <span data-ttu-id="e27ac-127">Kérelem küldése a banknak garancialevél kibocsátására vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="e27ac-127">Submit the letter of guarantee request to the bank.</span></span>                                                                       |
| <span data-ttu-id="e27ac-128">Fogadás a banktól</span><span class="sxs-lookup"><span data-stu-id="e27ac-128">Receive from bank</span></span>   | <span data-ttu-id="e27ac-129">Miután a bank elfogadja a beküldött kérelmet, a garancialevél átvehető a banktól.</span><span class="sxs-lookup"><span data-stu-id="e27ac-129">After the bank agrees to the submitted request, collect the letter of guarantee from the bank.</span></span>                            |
| <span data-ttu-id="e27ac-130">Kedvezményezettnek átadandó</span><span class="sxs-lookup"><span data-stu-id="e27ac-130">Give to beneficiary</span></span> | <span data-ttu-id="e27ac-131">Miután megkapta a garancialevelet a banktól, adja át a garancialevelet a kedvezményezettnek.</span><span class="sxs-lookup"><span data-stu-id="e27ac-131">After you receive the letter of guarantee from the bank, provide the letter of guarantee to the beneficiary.</span></span>              |
| <span data-ttu-id="e27ac-132">Érték növelése</span><span class="sxs-lookup"><span data-stu-id="e27ac-132">Increase value</span></span>      | <span data-ttu-id="e27ac-133">Ha a kedvezményezett és a meghatalmazott megegyezik, a pénzügyi érték növelhető.</span><span class="sxs-lookup"><span data-stu-id="e27ac-133">If the beneficiary and the principal agree, increase the monetary value.</span></span>                                                  |
| <span data-ttu-id="e27ac-134">Érték csökkentése</span><span class="sxs-lookup"><span data-stu-id="e27ac-134">Decrease value</span></span>      | <span data-ttu-id="e27ac-135">Ha a kedvezményezett és a meghatalmazott megegyezik, a pénzügyi érték csökkenthető.</span><span class="sxs-lookup"><span data-stu-id="e27ac-135">If the beneficiary and the principal agree, decrease the monetary value.</span></span>                                                  |
| <span data-ttu-id="e27ac-136">Kiterjesztés</span><span class="sxs-lookup"><span data-stu-id="e27ac-136">Extend</span></span>              | <span data-ttu-id="e27ac-137">Miután átadta a garancialevelet a kedvezményezett számára, növelheti az érvényesség időtartamát, ha az szükséges.</span><span class="sxs-lookup"><span data-stu-id="e27ac-137">After you provide the letter of guarantee to the beneficiary, extend the period of validity, if an extension is required.</span></span> |
| <span data-ttu-id="e27ac-138">Megszakítás</span><span class="sxs-lookup"><span data-stu-id="e27ac-138">Cancel</span></span>              | <span data-ttu-id="e27ac-139">Ha a garancialevél okafogyottá válik, visszavonhatja a szerződést.</span><span class="sxs-lookup"><span data-stu-id="e27ac-139">When the purpose that the letter of guarantee was requested for no longer applies, cancel the agreement.</span></span>                  |
| <span data-ttu-id="e27ac-140">Kiegyenlítés</span><span class="sxs-lookup"><span data-stu-id="e27ac-140">Liquidate</span></span>           | <span data-ttu-id="e27ac-141">Miután a kedvezményezett bemutatja a garancialevelet a banknak, fizesse ki készpénzben a garancialevelet.</span><span class="sxs-lookup"><span data-stu-id="e27ac-141">When the beneficiary presents the letter of guarantee to the bank, cash out the letter of guarantee.</span></span>                      |


<span data-ttu-id="e27ac-142">További információ a következő témakörökben olvasható:</span><span class="sxs-lookup"><span data-stu-id="e27ac-142">For more information, see the following topics:</span></span>

[<span data-ttu-id="e27ac-143">Garancialevél-tranzakció</span><span class="sxs-lookup"><span data-stu-id="e27ac-143">Letter of guarantee transaction</span></span>](tasks/letter-guarantee-transaction.md)

[<span data-ttu-id="e27ac-144">Bankhitelek beállítása és a garancialevélhez tartozó profilok feladása</span><span class="sxs-lookup"><span data-stu-id="e27ac-144">Set up bank facilities and posting profiles for letters of guarantee</span></span>](tasks/set-up-bank-facilities-posting-profiles.md)


