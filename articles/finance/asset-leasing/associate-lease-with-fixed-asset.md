---
title: Lízingek társítása tárgyi eszközhöz
description: A témakör bemutatja, hogyan társítható egy meglévő tárgyi eszköz egy új lízinghez.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d627633e43c2e6f5cad90dfe4100ff95a71541f7
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444183"
---
# <a name="associate-fixed-assets-with-leases"></a><span data-ttu-id="84311-103">Lízingek társítása tárgyi eszközhöz</span><span class="sxs-lookup"><span data-stu-id="84311-103">Associate fixed assets with leases</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84311-104">A témakör bemutatja, hogyan társítható egy meglévő tárgyi eszköz egy új lízinghez.</span><span class="sxs-lookup"><span data-stu-id="84311-104">The topic explains how to associate an existing fixed asset with a new lease.</span></span> <span data-ttu-id="84311-105">Amikor egy tárgyi eszközt egy lízinghez társít, a használatijog-eszköz (ROU) értéke a kezdeti megjelenítéskor a tárgyi eszköz beszerzési költsége lesz.</span><span class="sxs-lookup"><span data-stu-id="84311-105">When you associate a fixed asset with a lease, the right-of-use (ROU) asset value at initial recognition will be the acquisition cost of the fixed asset.</span></span>

<span data-ttu-id="84311-106">Mielőtt egy befektetett eszközt egy lízinghez társítana, létre kell hoznia egy rekordot a tárgyi eszközhöz a Tárgyi eszközökben.</span><span class="sxs-lookup"><span data-stu-id="84311-106">Before you can associate a fixed asset with a lease, you must create a record for the fixed asset in Fixed assets.</span></span> <span data-ttu-id="84311-107">Ezután a **Lízing összegzése** lapon létre kell hoznia egy lízinget, és csatolnia kell az eszközt az adott lízinghez.</span><span class="sxs-lookup"><span data-stu-id="84311-107">Then, on the **Lease summary** page, you must create a lease and link the asset to that lease.</span></span>

1. <span data-ttu-id="84311-108">Lízing hozzáadása a [Lízing hozzáadása vagy másolása](add-lease.md) című részben leírt lépések végrehajtásával.</span><span class="sxs-lookup"><span data-stu-id="84311-108">Add a lease by following the steps in [Add or copy leases](add-lease.md).</span></span> <span data-ttu-id="84311-109">A **Lízing hozzáadása** lap **Tárgyi eszköz száma** mezőjében válassza ki azt az eszközt, amely még nem lett beszerezve.</span><span class="sxs-lookup"><span data-stu-id="84311-109">On the **Add lease** page, in the **Fixed asset number** field, select the asset that hasn't yet been acquired.</span></span>
2. <span data-ttu-id="84311-110">Válassza a **Könyvek** lehetőséget, és erősítse meg a fizetési ütemezést.</span><span class="sxs-lookup"><span data-stu-id="84311-110">Select **Books**, and confirm the payment schedule.</span></span>
3. <span data-ttu-id="84311-111">Válassza a **Kezdeti elszámolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="84311-111">Select **Initial recognition**.</span></span>
4. <span data-ttu-id="84311-112">Válassza az **Eszközlízing-napló** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="84311-112">Select **Asset leasing journal**.</span></span>

    <span data-ttu-id="84311-113">A lízing kezdeti kivezetési naplóbejegyzése a tárgyi eszközt a ROU eszközszámlára általában megterhelt összegre terheli.</span><span class="sxs-lookup"><span data-stu-id="84311-113">The initial recognition journal entry for the lease debits the fixed asset for the amount that is usually debited to the ROU asset account.</span></span>

    <span data-ttu-id="84311-114">Most már megtekintheti a tárgyi eszköz tranzakciótípusát és könyvét.</span><span class="sxs-lookup"><span data-stu-id="84311-114">You can now view the transaction type and book for the fixed asset.</span></span>

5. <span data-ttu-id="84311-115">Válassza a **Napló részletei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="84311-115">Select **Journal details**.</span></span>
6. <span data-ttu-id="84311-116">Válassza a **Sorok** lehetőséget a naplóbejegyzés egyes sorainak megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="84311-116">Select **Lines** to view the individual lines for the journal entry.</span></span>
7. <span data-ttu-id="84311-117">Jelölje ki az eszközt tartalmazó naplósort, majd válassza a **Tárgyi eszközök** lapot.</span><span class="sxs-lookup"><span data-stu-id="84311-117">Select the journal line that contains the asset, and then select the **Fixed Assets** tab.</span></span>

    <span data-ttu-id="84311-118">A **Tárgyi eszközök** lapon látható a tranzakció típusa és a könyv.</span><span class="sxs-lookup"><span data-stu-id="84311-118">The **Fixed assets** tab shows the transaction type and the book.</span></span> <span data-ttu-id="84311-119">Alapértelmezés szerint a **Tranzakció típusa** mező **Beszerzés** értékre, a **Könyv** mező pedig a tárgyi eszköz aktuális könyvére van állítva.</span><span class="sxs-lookup"><span data-stu-id="84311-119">By default, the **Transaction type** field is set to **Acquisition**, and the **Book** field is set to the current book for the fixed asset.</span></span>

<span data-ttu-id="84311-120">A kezdeti elszámolásnapló-bejegyzés könyvelése után a tranzakció a tárgyi eszköz beszerzési tranzakciójaként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="84311-120">After you post the initial recognition journal entry, the transaction appears as an acquisition transaction for the fixed asset.</span></span> <span data-ttu-id="84311-121">A tranzakciótábla megtekintéséhez lépjen a **Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** elemre, válassza ki a megfelelő eszközt, és az **Értékelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="84311-121">To view the transaction table, go to **Fixed assets \> Fixed assets \> Fixed assets**, select the appropriate asset, and then select **Valuations**.</span></span> <span data-ttu-id="84311-122">Azt kell látnia, hogy a kezdeti elszámolásnapló-bejegyzés létrehozta egy megadott tárgyi eszköz beszerzési tranzakcióját.</span><span class="sxs-lookup"><span data-stu-id="84311-122">You should see that the initial recognition journal entry has created an acquisition transaction for the specified fixed asset.</span></span>

<span data-ttu-id="84311-123">A tárgyi eszköz értékcsökkenése a tárgyi eszközök standard értékcsökkenési funkciójának használatával.</span><span class="sxs-lookup"><span data-stu-id="84311-123">The fixed asset can now be depreciated by using the standard depreciation functionality in Fixed assets.</span></span> <span data-ttu-id="84311-124">Az értékcsökkenéssel kapcsolatos további tudnivalókért lásd: [Értékcsökkenési módszerek és szabályok](../fixed-assets/depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="84311-124">For more information about depreciation, see [Depreciation methods and conventions](../fixed-assets/depreciation-methods-conventions.md).</span></span>

> [!NOTE]
> <span data-ttu-id="84311-125">Ha a tárgyi eszközt lízinghez rendeli hozzá, akkor az **Eszköz értékcsökkenése** és a **Lízing értékvesztése** gombok le vannak tiltva az Eszközlízingelésnél.</span><span class="sxs-lookup"><span data-stu-id="84311-125">If you associate a fixed asset with a lease, the **Asset depreciation** and **Lease impairment** buttons are disabled in Asset leasing.</span></span> <span data-ttu-id="84311-126">Megtekintheti a tárgyi eszközökből származó eszközök értékcsökkenését és a lízing-értékvesztési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="84311-126">You can view asset depreciation and lease impairment transactions from Fixed assets.</span></span> <span data-ttu-id="84311-127">Az **Eszköztranzakciók** gomb, amely megnyitja a lekérdezési képernyőt is, le van tiltva.</span><span class="sxs-lookup"><span data-stu-id="84311-127">The **Asset transactions** button, which opens an inquiry form is also disabled.</span></span> <span data-ttu-id="84311-128">Az **Eszközranzakciók** lekérdezési űrlapot a Tárgyi eszközökben is megnyithatja.</span><span class="sxs-lookup"><span data-stu-id="84311-128">You can also open the **Asset transactions** inquiry form in Fixed assets.</span></span>  
