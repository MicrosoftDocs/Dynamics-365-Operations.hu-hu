---
title: Havi naplóbejegyzések létrehozása kötegben
description: Ez a témakör bemutatja, hogyan hozhat létre naplóbejegyzéseket egy kötegben a havi lízingköltségek rögzítésekor a hatékonyság növelése érdekében.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7f46f289c58c32c535dd20fb510cf2812625c49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971328"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="78fbe-103">Havi naplóbejegyzések létrehozása kötegben</span><span class="sxs-lookup"><span data-stu-id="78fbe-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78fbe-104">Ez a témakör bemutatja, hogyan hozhat létre naplóbejegyzéseket egy kötegben a havi lízingköltségek rögzítésekor a hatékonyság növelése érdekében.</span><span class="sxs-lookup"><span data-stu-id="78fbe-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="78fbe-105">A kötegelt feldolgozás segítségével több ütemezésből hozhat létre naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="78fbe-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="78fbe-106">Ezek a naplóbejegyzések magukban foglalhatják a lízingkifizetéseket, a kötelezettségamortizációt, a használatijog-eszköz (ROU) amortizációját és a végrehajtási költségköltségeket.</span><span class="sxs-lookup"><span data-stu-id="78fbe-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="78fbe-107">Kötegelt feldolgozással egyszerre több lízing kezdeti megjelenítését is elvégezheti, vagy egyszerre több lízinghez is létrehozhat átmeneti korrekciókat.</span><span class="sxs-lookup"><span data-stu-id="78fbe-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="78fbe-108">Kötegelt feldolgozás beállításához, illetve több lízing kifizetési számláinak, értékcsökkenésének vagy kamatának feldolgozásához nyissa meg az **Eszközlízing \> Időszakos \> Kötegnapló létrehozása** című szakaszt.</span><span class="sxs-lookup"><span data-stu-id="78fbe-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="78fbe-109">A megjelenő párbeszédpanelen kiválaszthatja azt az ütemezést, amelyből a naplóbejegyzéseket létre kell hozni.</span><span class="sxs-lookup"><span data-stu-id="78fbe-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="78fbe-110">Azt is megadhatja, hogy a kötegelt folyamatot meghatározott entitásokhoz, lízingcsoportokhoz vagy lízingkönyvekhez kell-e futtatni.</span><span class="sxs-lookup"><span data-stu-id="78fbe-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="78fbe-111">A későbbi tranzakciók, például a kötelezettségek amortizációs ütemezései, a kifizetések, az értékcsökkenés és a kiadások csak a megfelelő lízingek kezdeti megjelenítésének feladása után kerülnek feladásra.</span><span class="sxs-lookup"><span data-stu-id="78fbe-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="78fbe-112">A naplóbejegyzések létrejönnek, de nem kerülnek feladásra, amíg ki nem választja a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="78fbe-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>
