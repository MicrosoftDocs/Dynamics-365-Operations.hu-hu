---
title: Lingek hozzáadása vagy másolása (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet új lízinget létrehozni az eszközlízingben való adatok megadásával vagy egy meglévő lízing adatainak másolásával.
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
ms.openlocfilehash: abbf04d009a4b347792cd8b317e334da2a4cbbee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969603"
---
# <a name="add-or-copy-leases-preview"></a><span data-ttu-id="04f6b-103">Lingek hozzáadása vagy másolása (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="04f6b-103">Add or copy leases (Preview)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04f6b-104">Ez a témakör azt mutatja be, hogyan lehet a nulláról új lízinget létrehozni az eszközlízingben, illetve hogyan lehet lízinget létrehozni egy meglévő lízing adatainak másolásával.</span><span class="sxs-lookup"><span data-stu-id="04f6b-104">This topic explains how to create a lease from scratch in Asset leasing, and also how to create a lease by copying an existing lease.</span></span> <span data-ttu-id="04f6b-105">A lízingek nulláról való létrehozásának folyamata az új lízing adatainak megadását, majd a lízing ütemezés létrehozását jelenti.</span><span class="sxs-lookup"><span data-stu-id="04f6b-105">The process for creating a lease from scratch involves entering information for the new lease and then creating a lease schedule.</span></span> <span data-ttu-id="04f6b-106">Ha legalább egy lízing be van állítva, akkor könnyebben megtalálhatja az adatok meglévő lízingből történő másolását, majd az új lízing létrehozásához szükséges adatok szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="04f6b-106">After at least one lease has been set up, you might find it easier to copy the information from an existing lease and then edit that information as you require to create a new lease.</span></span>

## <a name="create-a-lease"></a><span data-ttu-id="04f6b-107">Lízing létrehozása</span><span class="sxs-lookup"><span data-stu-id="04f6b-107">Create a lease</span></span>

<span data-ttu-id="04f6b-108">A következő lépéseket követve hozzon létre egy lízinget az Eszközlízingben.</span><span class="sxs-lookup"><span data-stu-id="04f6b-108">Follow these steps to create a lease in Asset leasing.</span></span>

1. <span data-ttu-id="04f6b-109">A **Lízing összefoglalása** lap műveleti paneljén válassza ki az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="04f6b-109">On the **Lease summary** page, on the Action Pane, select **New**.</span></span>
2. <span data-ttu-id="04f6b-110">Adja meg a lízing adatait.</span><span class="sxs-lookup"><span data-stu-id="04f6b-110">Enter the lease information.</span></span> <span data-ttu-id="04f6b-111">A kötelezően kitöltendő mezők piros szegéllyel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="04f6b-111">Fields that are required have red borders.</span></span>

## <a name="create-a-lease-schedule"></a><span data-ttu-id="04f6b-112">Lízingütemezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="04f6b-112">Create a lease schedule</span></span>

<span data-ttu-id="04f6b-113">Miután befejezte a lízing adatainak megadását, hajtsa végre az alábbi lépéseket a lízingütemezés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="04f6b-113">After you've finished entering information for the lease, follow these steps to create a lease schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="04f6b-114">Előfordulhat, hogy a pénzügyi dimenziók a saját pénzügyi dimenziók alapján változnak.</span><span class="sxs-lookup"><span data-stu-id="04f6b-114">The financial dimensions might change based on any custom financial dimensions.</span></span>

1. <span data-ttu-id="04f6b-115">A lízingkönyvek létrehozásához válassza az **Ütemezések létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04f6b-115">Select **Create schedules** to generate the lease books.</span></span> <span data-ttu-id="04f6b-116">A lízingek tartalmazzák a kifizetést, az amortizációt, az értékcsökkenést és a költségütemezéseket.</span><span class="sxs-lookup"><span data-stu-id="04f6b-116">The lease books include the payment, amortization, depreciation, and expense schedules.</span></span>
2. <span data-ttu-id="04f6b-117">A lízingek eléréséhez és az újonnan létrehozott ütemezések megtekintéséhez válassza ki a **Könyvek** fület.</span><span class="sxs-lookup"><span data-stu-id="04f6b-117">To access the lease books and view the newly created schedules, select the **Books** tab.</span></span>

    <span data-ttu-id="04f6b-118">A **Könyv részletei** lap mutatja, hogy a lízinget milyen módon kell elszámolni a hozzárendelt könyvek között.</span><span class="sxs-lookup"><span data-stu-id="04f6b-118">The **Book details** page shows how the lease is accounted for by the books that have been allocated to it.</span></span> <span data-ttu-id="04f6b-119">Itt megtekintheti a lízingütemezéseket.</span><span class="sxs-lookup"><span data-stu-id="04f6b-119">From here, you can view the lease schedules.</span></span>

    <span data-ttu-id="04f6b-120">A fizetési ütemezés tartalmazza a **Lízing hozzáadása** lap **Fizetési ütemezés sorai** fül bemeneteit.</span><span class="sxs-lookup"><span data-stu-id="04f6b-120">The payment schedule contains the inputs from the **Payment schedule lines** tab on the **Add lease** page.</span></span> <span data-ttu-id="04f6b-121">Továbbra is módosíthatja az egyes kifizetési összegeket és a változó fizetéseket.</span><span class="sxs-lookup"><span data-stu-id="04f6b-121">You can still change each payment amount and variable payment.</span></span> <span data-ttu-id="04f6b-122">A lízingkötelezettséget a módosított fizetési ütemezés alapján számítja ki a program.</span><span class="sxs-lookup"><span data-stu-id="04f6b-122">The lease liability is calculated based on the modified payment schedule.</span></span>

4. <span data-ttu-id="04f6b-123">Miután befejezte a kifizetési ütemezés áttekintését, jelölje be az **Ütemezés jóváhagyása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="04f6b-123">After you've finished reviewing the payment schedule, select **Confirm schedule**.</span></span> <span data-ttu-id="04f6b-124">Az ütemezés megerősítése után a lízing már nem érhető el szerkesztésre.</span><span class="sxs-lookup"><span data-stu-id="04f6b-124">After the schedule is confirmed, the lease is no longer available for editing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04f6b-125">A rendszer automatikusan kiszámítja a lízing feltételeit a **Lízing hozzáadása** lap kifizetési ütemezés soraiból.</span><span class="sxs-lookup"><span data-stu-id="04f6b-125">The system automatically calculates the lease term from the payment schedule lines on the **Add lease** page.</span></span>
    >
    > <span data-ttu-id="04f6b-126">A lízingfutamidő hónapok szerinti kiszámításához a rendszer megkeresi az adott fizetési ütemezési sor kezdő és záró dátuma közötti különbséget.</span><span class="sxs-lookup"><span data-stu-id="04f6b-126">To calculate the lease term in months, the system finds the difference between the start date and the end date for a specific payment schedule line.</span></span> <span data-ttu-id="04f6b-127">Ezt követően továbblép a következő fizetési ütemezési sorra, és megkeresi a különbözetet.</span><span class="sxs-lookup"><span data-stu-id="04f6b-127">It then moves to the next payment schedule line and finds the difference again.</span></span> <span data-ttu-id="04f6b-128">Végezetül a rendszer az összes összegből összegzi a lízing feltételeit hónapok szerint.</span><span class="sxs-lookup"><span data-stu-id="04f6b-128">Finally, the system sums all the amounts to determine the lease term in months.</span></span>

5. <span data-ttu-id="04f6b-129">A kiszámított időszakok kamatráfordításainak megtekintéséhez nyissa meg a **Lízingkötelezettség amortizációjának ütemezése** lapot.</span><span class="sxs-lookup"><span data-stu-id="04f6b-129">To view the calculated period interest expenses, open the **Liability amortization schedule** page.</span></span> <span data-ttu-id="04f6b-130">A számított lineáris értékcsökkenés megtekintéséhez nyissa meg az **Eszköz értékcsökkenésének ütemezése** lapját.</span><span class="sxs-lookup"><span data-stu-id="04f6b-130">To view calculated straight-line depreciation, open the **Asset depreciation schedule** page.</span></span>
6. <span data-ttu-id="04f6b-131">Miután befejezte a számított összeg áttekintését, létre lehet hozni a kezdeti felismerési napló bejegyzését a **Kezdeti felismerés** oldalon.</span><span class="sxs-lookup"><span data-stu-id="04f6b-131">After you've finished reviewing the calculated amount, you can create the initial recognition journal entry on the **Initial recognition** page.</span></span> <span data-ttu-id="04f6b-132">Egy üzenet jelenik meg, amely jelzi, hogy a napló létrejött.</span><span class="sxs-lookup"><span data-stu-id="04f6b-132">You receive a message that states that the journal has been created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04f6b-133">A naplóbejegyzés nem kerül feladásra a Főkönyvbe mindaddig, amíg a bejegyzést manuálisan fel nem adja.</span><span class="sxs-lookup"><span data-stu-id="04f6b-133">The journal entry isn't posted to General ledger until you manually post the entry.</span></span>

7. <span data-ttu-id="04f6b-134">Ha a feladást megelőzően át szeretné tekinteni a javasolt kezdeti felismerési bejegyzést, válassza ki az **Eszközlízing naplók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04f6b-134">To review the proposed initial recognition entry before you post it, select **Asset leasing journal**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04f6b-135">Az Eszközlízing napló nem hozható létre manuálisan.</span><span class="sxs-lookup"><span data-stu-id="04f6b-135">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="04f6b-136">Automatikusan létrejön a lízingütemezések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="04f6b-136">It's automatically created when lease schedules are created.</span></span>

8. <span data-ttu-id="04f6b-137">Amikor befejezte a kezdeti felismerési napló bejegyzésének áttekintését, és készen áll a feladásra, válassza a **Feladás** lehetőséget, ha a Főkönyvben a használaton kívüli (ROU) eszközt és lízingkötelezettséget szeretné elismerni.</span><span class="sxs-lookup"><span data-stu-id="04f6b-137">When you've finished reviewing the initial recognition journal entry and are ready to post it, select **Post** to recognize the right-of-use (ROU) asset and lease liability in General ledger.</span></span>

## <a name="copy-a-lease"></a><span data-ttu-id="04f6b-138">Lízing másolása</span><span class="sxs-lookup"><span data-stu-id="04f6b-138">Copy a lease</span></span>

<span data-ttu-id="04f6b-139">Az eszközlízing lehetővé teszi egy lízing adatainak másolását egy olyan új lízing létrehozásához, amelynek ugyanazok az adatai.</span><span class="sxs-lookup"><span data-stu-id="04f6b-139">Asset leasing lets you copy the details of a lease to create a new lease that has the same information.</span></span> <span data-ttu-id="04f6b-140">Ezt követően módosíthatja a lízing mezőket, mielőtt létrehozza a másolt lízing ütemezését.</span><span class="sxs-lookup"><span data-stu-id="04f6b-140">You can then change the lease fields before you create the schedules for the copied lease.</span></span>

1. <span data-ttu-id="04f6b-141">Válassza ki a másolni kívánt lízinget a **Lízing összegzése** oldalon, majd a művelet ablaktáblán válassza a **Lízing másolása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="04f6b-141">On the **Lease summary** page, select the lease to copy, and then, on the Action Pane, select **Copy lease**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04f6b-142">Ha a **Manuális** paraméter ki van kapcsolva a lízingazonosítók számsorozatához, a program automatikusan létrehozza a sorban szereplő következő számot a másolt lízing azonosítójaként.</span><span class="sxs-lookup"><span data-stu-id="04f6b-142">If the **Manual** parameter is turned off for the number sequence for lease IDs, the next number in the sequence is automatically generated as the lease ID of the copied lease.</span></span> <span data-ttu-id="04f6b-143">Ha a **Manuális** paraméter be van kapcsolva, akkor egy üzenet jelenik meg, amely kéri, hogy adja meg a lízingazonosítót, mielőtt továbblép a lízing másolásával.</span><span class="sxs-lookup"><span data-stu-id="04f6b-143">If the **Manual** parameter is turned on, you receive a message that prompts you to enter the lease ID before you proceed to copy the lease.</span></span>

2. <span data-ttu-id="04f6b-144">Válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="04f6b-144">Select **Copy**.</span></span> <span data-ttu-id="04f6b-145">A kiválasztott lízing adatait a program átmásolja egy új lízingbe.</span><span class="sxs-lookup"><span data-stu-id="04f6b-145">The lease details from the selected lease are copied to a new lease.</span></span> <span data-ttu-id="04f6b-146">Ezután a mentés előtt szerkesztheti az új lízing adatait, és létrehozhatja a lízingütemezéseket.</span><span class="sxs-lookup"><span data-stu-id="04f6b-146">You can then edit the details of the new lease before you save it and create the lease schedules.</span></span>

## <a name="asset-leasing-journal"></a><span data-ttu-id="04f6b-147">Eszközlízing-napló</span><span class="sxs-lookup"><span data-stu-id="04f6b-147">Asset leasing journal</span></span>

<span data-ttu-id="04f6b-148">Az eszközlízing-naplóban létrehozott összes naplóbejegyzés az eszközlízing naplóban szerepel.</span><span class="sxs-lookup"><span data-stu-id="04f6b-148">All journal entries that are created in Asset leasing are contained in the Asset leasing journal.</span></span> <span data-ttu-id="04f6b-149">Az **Eszközlízing-napló** oldalon (**Eszközlízing \> Naplóbejegyzések \> Eszközlízing-napló**) a megadott naplóbejegyzések és bizonylatok megtekintése, valamint a feladatlan naplóbejegyzések feladása alapján szűrhet.</span><span class="sxs-lookup"><span data-stu-id="04f6b-149">On the **Asset leasing journal** page (**Asset leasing \> Journal entries \> Asset leasing journal**), you can filter by posting status, view specific journal entries and the vouchers, and post unposted journal entries.</span></span>

> [!NOTE]
> <span data-ttu-id="04f6b-150">Az Eszközlízing napló nem hozható létre manuálisan.</span><span class="sxs-lookup"><span data-stu-id="04f6b-150">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="04f6b-151">Automatikusan létrejön a lízingütemezések létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="04f6b-151">It's automatically created when lease schedules are created.</span></span>
