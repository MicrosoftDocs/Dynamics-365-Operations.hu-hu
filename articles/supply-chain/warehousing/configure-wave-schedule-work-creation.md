---
title: Munka létrehozásának ütemezése hullám közben
description: Ez a témakör a munka-létrehozási hullámfeldolgozás ütemezésének beállítását és használatát ismerteti.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 36a450f78695f617056875f8d236fe46bc66aaaf
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501222"
---
# <a name="schedule-work-creation-during-wave"></a><span data-ttu-id="7c1e5-103">Munka létrehozásának ütemezése hullám közben</span><span class="sxs-lookup"><span data-stu-id="7c1e5-103">Schedule work creation during wave</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="7c1e5-104">A hullámfeldolgozási folyamat részeként használja a *Munka létrehozásának ütemezése* funkciót a hullámfeldolgozás teljesítményének növeléséhez azáltal, hogy a rendszer párhuzamos feldolgozással hozza létre a munkát.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-104">Use the *Schedule work creation* feature as part of your waving process to help increase wave processing throughput by having the system create work using parallel processing.</span></span>

<span data-ttu-id="7c1e5-105">Ha ez a funkció engedélyezve van, akkor automatikusan létrejön a tervezett munka, amelyet a rendszer végül feldolgoz a tényleges munka létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-105">When the functionality is enabled, planned work will automatically get created, which the system will eventually process to create actual work.</span></span> <span data-ttu-id="7c1e5-106">Ha a hullámra vonatkozó rakománysorok száma eléri az előre meghatározott küszöbértéket, a rendszer gyorsabb munkát hoz létre párhuzamos, aszinkron feldolgozás alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-106">If the number of wave load lines reaches a predetermined threshold, the system will create actual work more quickly by applying parallel, asynchronous processing.</span></span>

## <a name="enable-the-schedule-work-creation-feature"></a><span data-ttu-id="7c1e5-107">A Munka létrehozásának ütemezése funkció engedélyezése</span><span class="sxs-lookup"><span data-stu-id="7c1e5-107">Enable the Schedule work creation feature</span></span>

### <a name="enable-the-feature-in-feature-management"></a><span data-ttu-id="7c1e5-108">Szolgáltatások engedélyezése a szolgáltatások kezelésében</span><span class="sxs-lookup"><span data-stu-id="7c1e5-108">Enable the feature in feature management</span></span>

<span data-ttu-id="7c1e5-109">A *Munka létrehozásának* ütemezése funkciót a használata előtt be kell kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-109">Before you can use the *Schedule work creation* feature, it must be turned on in your system.</span></span> <span data-ttu-id="7c1e5-110">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="7c1e5-111">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="7c1e5-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7c1e5-112">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="7c1e5-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="7c1e5-113">**Funkció neve:** *Munka létrehozásának ütemezése*</span><span class="sxs-lookup"><span data-stu-id="7c1e5-113">**Feature name:** *Schedule work creation*</span></span>

> [!NOTE]
> <span data-ttu-id="7c1e5-114">A *Munka létrehozásának ütemezése* engedélyezése előtt engedélyezni kell a *Szervezeti szintű munkazárolás* funkciót.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-114">The *Organization-wide work blocking* feature must be enabled before you can enable *Schedule work creation*.</span></span>

### <a name="manually-enable-batch-processing-of-waves"></a><span data-ttu-id="7c1e5-115">Hullámok kötegelt feldolgozásának manuális engedélyezése</span><span class="sxs-lookup"><span data-stu-id="7c1e5-115">Manually enable batch processing of waves</span></span>

<span data-ttu-id="7c1e5-116">Ahhoz, hogy egy párhuzamos aszinkron módszert kihasználva raktári munkát hozzon létre, a hullámfolyamatnak kötegben kell futnia.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-116">To take advantage of a parallel asynchronous method to create warehouse work, your wave process must be running in batch.</span></span> <span data-ttu-id="7c1e5-117">Ennek a beállításához:</span><span class="sxs-lookup"><span data-stu-id="7c1e5-117">To set this up:</span></span>

1. <span data-ttu-id="7c1e5-118">Ugorjon a  **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** elemre.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-118">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>

1. <span data-ttu-id="7c1e5-119">Állítsa be az **Általános** lapon a **Hullámok kötegelt feldolgozása** lehetőséget *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-119">On the **General** tab, set **Process waves in batch** to *Yes*.</span></span> <span data-ttu-id="7c1e5-120">Ki is választhat egy külön **Hullámfeldolgozási kötegcsoportot**, hogy megakadályozza a kötegelt feladatok várólistájának feldolgozását a többi folyamattal egyidejűleg történő futását.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-120">Optionally, you can also select a dedicated **Wave processing batch group** to prevent your batch queue processing from running at the same time as other processes.</span></span>

1. <span data-ttu-id="7c1e5-121">A **Zárolásra való várakozás (ms) idő** beállítása, amely akkor érvényes, ha a rendszer egyszerre több hullámot dolgoz fel.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-121">Set the **Wait for lock (ms) time**, which applies when the system is processing several waves at the same time.</span></span> <span data-ttu-id="7c1e5-122">A legtöbb nagyobb hullámfolyamatnál a *60000* értéket javasoljuk.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-122">For most larger waving processes, we recommend a value of *60000*.</span></span>

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a><span data-ttu-id="7c1e5-123">Az új hullámlépés metódusának manuális engedélyezése a meglévő hullámsablonok számára</span><span class="sxs-lookup"><span data-stu-id="7c1e5-123">Manually enable the new wave step method for existing wave templates</span></span>

<span data-ttu-id="7c1e5-124">Indítsa el az új hullámlépés-metódus létrehozásával, majd az aszinkron feladatok párhuzamos feldolgozásának engedélyezésével.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-124">Start by creating the new wave step method and enabling it for parallel asynchronous task processing.</span></span>

1. <span data-ttu-id="7c1e5-125">Ugorjon a  **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-125">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>

1. <span data-ttu-id="7c1e5-126">Válassza ki az  **Újragenerálás** metódust, és jegyezze fel, hogy a *WHSScheduleWorkCreationWaveStepMethod* felkerült a szállítási hullámsablonok során használható hullámfolyamati metódusok listájára.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-126">Select  **Regenerate method** and note that *WHSScheduleWorkCreationWaveStepMethod* has been added to the list of wave process methods you can use in your shipping wave templates.</span></span>

1. <span data-ttu-id="7c1e5-127">Válassza ki a *WHSScheduleWorkCreationAluStepMethod* **Metódusnevű** rekordot, és válassza a **Feladatkonfigurációt**.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-127">Select the record with the **Method name** *WHSScheduleWorkCreationWaveStepMethod* and select **Task configuration**.</span></span>

1. <span data-ttu-id="7c1e5-128">A Művelet panelen válassza az **Új** lehetőséget egy új dimenzió rácshoz való hozzáadásához, és használja a következő beállításokat:</span><span class="sxs-lookup"><span data-stu-id="7c1e5-128">To add a new row to the grid, select **New** on the Action Pane and use the following settings:</span></span>

    - <span data-ttu-id="7c1e5-129">**Raktár** – a munka-létrehozás feldolgozásának ütemezése során használt raktár kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-129">**Warehouse** - Select the warehouse you will use to schedule work creation processing.</span></span>

    - <span data-ttu-id="7c1e5-130">**Kötegelt feladatok maximális száma** – adja meg a kötegelt feladatok maximális számát.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-130">**Maximum number of batch tasks** - Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="7c1e5-131">A legtöbb esetben ennek az értéknek a 8–16 tartományban kell lennie, de javasoljuk, hogy az esetektől függően az optimális beállítással kísérletezzen.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-131">In most cases, this value should be in the range from 8-16, however we recommend that you experiment with the optimal setting based on your scenarios.</span></span>

    - <span data-ttu-id="7c1e5-132">**Hullámfeldolgozási kötegcsoport** – a kötegelt várólisták feldolgozásának optimalizálása érdekében válasszon ki egy külön hullámfeldolgozási kötegcsoportot.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-132">**Wave processing batch group** - Select a dedicated wave processing batch group to optimize your batch queue processing.</span></span>

<span data-ttu-id="7c1e5-133">Ezzel készen áll arra, hogy egy meglévő hullámsablont frissítsen (vagy újat hozzon létre), hogy a *Munka létrehozásának ütemezése* hullámfeldolgozási módszert használja.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-133">Now you are ready to update an existing wave template (or create a new one) to use the *Schedule work creation* wave processing method.</span></span>

1. <span data-ttu-id="7c1e5-134">Ugorjon a  **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-134">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>

1. <span data-ttu-id="7c1e5-135">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-135">Select **Edit** on the Action Pane.</span></span>

1. <span data-ttu-id="7c1e5-136">A lista ablaktáblában válassza ki a frissíteni kívánt hullámsablont (ha bemutatóadatokkal tesztel, akkor a *24 Alapértelmezett szállítás* használható).</span><span class="sxs-lookup"><span data-stu-id="7c1e5-136">In the list pane, select the wave template you would like to update (if you are testing using demo data, then you could use *24 Shipping default*).</span></span>

1. <span data-ttu-id="7c1e5-137">Bontsa ki a **Metódusok** gyorslapot, és válassza ki azt a sort, amelynek a **Fennmaradó metódusok** rácsban a **Név** értéke *Munka létrehozásának ütemezése*.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-137">Expand the **Methods** FastTab and select the row with the **Name** *Schedule work creation* in the **Remaining methods** grid.</span></span>

1. <span data-ttu-id="7c1e5-138">Válassza a **Kijelölt metódusok** oszlopra mutató nyalat a kijelölt sornak az oszlopba való mozgatásához.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-138">Select the arrow pointing to the **Selected methods** column to move the selected row to that column.</span></span> <span data-ttu-id="7c1e5-139">(Egyszerre csak egy kiválasztott metódus lehet, amely vagy a *WHSScheduleWorkCreationAluStepMethod* vagy a *createWork* lehetőséget használja, így a *createWork* **metódusnévvel** létrehozott meglévő sor automatikusan átkerül a **Fennmaradó metódusok** rácsba.)</span><span class="sxs-lookup"><span data-stu-id="7c1e5-139">(You can only have one selected method at a time that uses either *WHSScheduleWorkCreationWaveStepMethod* or *createWork*, so the existing row with **Method name** *createWork* is automatically moved to the **Remaining methods** grid.)</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="7c1e5-140">Hullámfeladat-feldolgozási küszöbérték adatainak beállítása</span><span class="sxs-lookup"><span data-stu-id="7c1e5-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="7c1e5-141">A rendszer akkor hozza létre az alapértelmezett hullámfeladat-feldolgozási küszöbérték-adatokat, amikor egy hullámfolyamat bármilyen feladatalapú feldolgozással fut.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-141">The system will create default wave task processing threshold data the first time a wave process runs using any task-based processing.</span></span> <span data-ttu-id="7c1e5-142">Az adatok segítségével lehet szabályozni, hogy mikor fusson aszinkron módon és feladatalapúan a hullámfeldolgozás, így lehetővé válik a feldolgozás és a munka létrehozása párhuzamosan.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-142">The data is used to control when wave processing will run asynchronously and be task-based, which enables it to process and create work in parallel.</span></span>

<span data-ttu-id="7c1e5-143">Az alapértelmezett adatok kezdetben 15-ös küszöbértéket használnak a rakománysorok minimális számára (MINIMUMLOADLINES).</span><span class="sxs-lookup"><span data-stu-id="7c1e5-143">The default data will initially use a threshold value of 15 for the minimum number of load lines (MINIMUMWAVELOADLINES).</span></span> <span data-ttu-id="7c1e5-144">Ez azt jelenti, hogy amikor a rendszer egy hullámot több mint 15 rakománysorral dolgoz fel, aszinkron feladatfeldolgozást fog használni.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-144">This means that when the system processes a wave with more than 15 loads lines, it will use asynchronous task processing.</span></span> <span data-ttu-id="7c1e5-145">Ezt az adatot manuálisan is beszúrhatja a **WHSTopTaskProcessingThresholdParameters** táblába a tesztkörnyezetben, de ha éles környezetben módosítania kell ezt a beállítást, frissítés kéréséhez forduljon a Microsoft támogatási szolgálatához.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-145">You can manually insert/update this data in the **WHSWaveTaskProcessingThresholdParameters** table in your test environments, but if you need to change this setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="work-with-the-feature"></a><span data-ttu-id="7c1e5-146">A funkció használata</span><span class="sxs-lookup"><span data-stu-id="7c1e5-146">Work with the feature</span></span>

<span data-ttu-id="7c1e5-147">Ha a *Munka létrehozásának ütemezése* funkció engedélyezve van, akkor a hullámfeldolgozás tervezett munkát hoz létre, amelyet végül az új munka-létrehozási folyamat fog alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-147">When the *Schedule work creation* functionality is enabled, wave processing will create planned work, which will eventually be used by the new work creation process.</span></span> <span data-ttu-id="7c1e5-148">A munka létrehozása során a rendszer letiltja a munkát az *egész szervezetre kiterjedő munkazárolási* funkcióval.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-148">During work creation, the work will be blocked using the *Organization-wide work blocking* feature.</span></span>

<span data-ttu-id="7c1e5-149">Az alábbi folyamatábra bemutatja, hogyan jön létre tervezett munka a hullámfeldolgozás során.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-149">The following flowchart shows how planned work is created during wave processing.</span></span>

![Munka létrehozásának ütemezése](media/schedule-work-creation-process.png)

### <a name="planned-work"></a><span data-ttu-id="7c1e5-151">Tervezett munka</span><span class="sxs-lookup"><span data-stu-id="7c1e5-151">Planned work</span></span>

<span data-ttu-id="7c1e5-152">A **Tervezett munka részletei** lap (**Raktárkezelés \> Munka \> Tervezett munka részletei**) a hullámfeldolgozás során kezdetben létrehozott tervezett munka adatait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-152">The **Planned work details** page (**Warehouse management \> Work \> Planned work details**) shows information about the planned work, which is initially created during wave processing.</span></span> <span data-ttu-id="7c1e5-153">A következő **Folyamatállapot** értékek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="7c1e5-153">The following **Process status** values are available:</span></span>

- <span data-ttu-id="7c1e5-154">**Várakozás** – a tervezett munka várakozik a munka létrehozására.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-154">**Queued** - The planned work is waiting to be used to create work.</span></span>
- <span data-ttu-id="7c1e5-155">**Kész** – a tervezett munkát használták munka létrehozására.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-155">**Completed** - The planned work has been used to create work.</span></span>
- <span data-ttu-id="7c1e5-156">**Sikertelen** – a hullámfeldolgozás nem sikerült.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-156">**Failed** – The wave processing has failed.</span></span> <span data-ttu-id="7c1e5-157">A tervezett munka **Sikertelen** állapotban lehet tényleges munkával vagy anélkül.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-157">Note that the planned work can be in a **Failed** state with or without related actual work.</span></span> <span data-ttu-id="7c1e5-158">Ha a tényleges munkalétrehozási folyamat sikertelen, a tényleges munka *Visszavonva* állapotú marad.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-158">When the actual work creation process fails, the actual work remains in status *Cancelled*.</span></span>

### <a name="batch-job-for-the-work-creation-process"></a><span data-ttu-id="7c1e5-159">Kötegelt feladat a munkalétrehozási folyamathoz</span><span class="sxs-lookup"><span data-stu-id="7c1e5-159">Batch job for the work creation process</span></span>

<span data-ttu-id="7c1e5-160">A hullámok feldolgozásához szükséges kötegelt feladatok megtekintéséhez jelölje ki a **Kötegelt feladatok** lehetőséget a **Minden hullám** oldal műveletablakában.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-160">To view the batch jobs for processing waves, select **Batch jobs** on the Action Pane on the **All waves** page.</span></span>

<span data-ttu-id="7c1e5-161">Innen megtekintheti a kötegelt feladatok minden egyes adatát a kötegeltfeladat-azonosítókhoz.</span><span class="sxs-lookup"><span data-stu-id="7c1e5-161">From here, you can view all the batch task details for each of the batch job IDs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]