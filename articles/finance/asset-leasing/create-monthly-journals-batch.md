---
title: Havi naplóbejegyzések létrehozása kötegben
description: Ez a témakör bemutatja, hogyan hozhat létre naplóbejegyzéseket egy kötegben a havi lízingköltségek rögzítésekor a hatékonyság növelése érdekében.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ca84e56569ea5ddbb4d5335d0944a6bd8a50a1b1
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881204"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="e1f06-103">Havi naplóbejegyzések létrehozása kötegben</span><span class="sxs-lookup"><span data-stu-id="e1f06-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1f06-104">Ez a témakör bemutatja, hogyan hozhat létre naplóbejegyzéseket egy kötegben a havi lízingköltségek rögzítésekor a hatékonyság növelése érdekében.</span><span class="sxs-lookup"><span data-stu-id="e1f06-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="e1f06-105">A kötegelt feldolgozás segítségével több ütemezésből hozhat létre naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="e1f06-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="e1f06-106">Ezek a naplóbejegyzések magukban foglalhatják a lízingkifizetéseket, a kötelezettségamortizációt, a használatijog-eszköz (ROU) amortizációját és a végrehajtási költségköltségeket.</span><span class="sxs-lookup"><span data-stu-id="e1f06-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="e1f06-107">Kötegelt feldolgozással egyszerre több lízing kezdeti megjelenítését is elvégezheti, vagy egyszerre több lízinghez is létrehozhat átmeneti korrekciókat.</span><span class="sxs-lookup"><span data-stu-id="e1f06-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="e1f06-108">Kötegelt feldolgozás beállításához, illetve több lízing kifizetési számláinak, értékcsökkenésének vagy kamatának feldolgozásához nyissa meg az **Eszközlízing \> Időszakos \> Kötegnapló létrehozása** című szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e1f06-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="e1f06-109">A megjelenő párbeszédpanelen kiválaszthatja azt az ütemezést, amelyből a naplóbejegyzéseket létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="e1f06-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="e1f06-110">Azt is megadhatja, hogy a kötegelt folyamatot meghatározott entitásokhoz, lízingcsoportokhoz vagy lízingkönyvekhez kell-e futtatni.</span><span class="sxs-lookup"><span data-stu-id="e1f06-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="e1f06-111">A későbbi tranzakciók, például a kötelezettségek amortizációs ütemezései, a kifizetések, az értékcsökkenés és a kiadások csak a megfelelő lízingek kezdeti megjelenítésének feladása után kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="e1f06-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="e1f06-112">A naplóbejegyzések létrejönnek, de nem kerülnek feladásra, amíg ki nem választja a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e1f06-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
