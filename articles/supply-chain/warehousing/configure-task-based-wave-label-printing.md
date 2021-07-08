---
title: Hullámcímke-nyomtatás ütemezése hullám közben
description: Ez a témakör leírja, hogyan lehet beállítani és használni a feladatalapú hullámcímke-nyomtatásban használható funkciókat.
author: MSFTGarm
ms.date: 06/09/2021
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-obaranov
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 32842c32599b3ca5d84cc9f715a1453d55e176dc
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301886"
---
# <a name="schedule-wave-label-printing-during-wave"></a><span data-ttu-id="0b5a5-103">Hullámcímke-nyomtatás ütemezése hullám közben</span><span class="sxs-lookup"><span data-stu-id="0b5a5-103">Schedule wave label printing during wave</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b5a5-104">A *Feladatalapú hullámcímke-nyomtatási* funkció a hullámba ásási folyamat részeként a hatékonyság javítása, valamint a rendszer hullámcímkék létrehozása és külön feladatokban való végrehajtása érdekében használható.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-104">Use the *Task based wave label printing* feature as part of your waving process to help improve efficiency, and to have the system create wave labels and work in separate tasks.</span></span>

<span data-ttu-id="0b5a5-105">A hullámcímke-nyomtatás konfigurálása összetett feladat, a pontos konfiguráción és az alapadatokon alapul.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-105">The process of configuring wave label printing is complex and relies on accurate configuration and master data.</span></span> <span data-ttu-id="0b5a5-106">Ez nem jelenti azt, hogy a hullámcímkerekordok generálása sikertelen lesz, és ha így tesz, akkor az egész hullámfeldolgozás visszagörgetésre kerül.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-106">It isn't uncommon for the generation of wave label records to fail, and when it does, the whole wave processing is rolled back.</span></span> <span data-ttu-id="0b5a5-107">A *Feladatalapú hullámcímke-nyomtatási* funkcióval elkerülhető a munka és munkasorok újra létrehozása a hullámcímke helytelen nyomtatása esetén.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-107">The *Task based wave label printing* feature helps you avoid having to re-create work and work lines every time that a wave label is incorrectly printed.</span></span>

<span data-ttu-id="0b5a5-108">A *Feladat alapú hullámcímke-nyomtatási* funkció használata esetén a rendszer először munka- és munkasorokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-108">When you use the *Task based wave label printing* feature, the system first creates work and work lines.</span></span> <span data-ttu-id="0b5a5-109">Ezután létrehozza és kinyomtatja a hullámcímkéket.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-109">It then creates and prints wave labels.</span></span> <span data-ttu-id="0b5a5-110">Végül, ha a hullámcímkék helyesen vannak létrehozva, kiadja a munkát és a hullámot kitárolásra.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-110">Finally, if the wave labels are correctly created, it releases the work and wave for picking.</span></span>

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a><span data-ttu-id="0b5a5-111">A Feladat alapú hullámcímke-nyomtatási funkció bekapcsolva a funkciókezelésben</span><span class="sxs-lookup"><span data-stu-id="0b5a5-111">Turn on the Task based wave label printing feature in feature management</span></span>

<span data-ttu-id="0b5a5-112">Az ebben a témakörben leírt funkciók csak akkor használhatók, ha a rendszerben be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-112">To use the features that are described in this topic, they must be turned on for your system.</span></span> <span data-ttu-id="0b5a5-113">Használja a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a következő funkcióknak az alábbi sorrendben történő bekapcsolásához:</span><span class="sxs-lookup"><span data-stu-id="0b5a5-113">Use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to turn on the features in the following order:</span></span>

1. <span data-ttu-id="0b5a5-114">*Hullámcímke-nyomtatás* – Ez a funkció szükséges a hullámfolyamat metódusának engedélyezéséhez hullámcímke-nyomtatáshoz.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-114">*Wave label printing* – This feature is required to enable the wave process method for wave label printing.</span></span>
1. <span data-ttu-id="0b5a5-115">*Szervezeti szintű munkazárolás* – Az ütemezett munkalétrehozás kézi és automatikus konfigurálásához egyaránt szükséges ez a funkció.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-115">*Organization-wide work blocking* – This feature is required for both manual and automatic configuration of scheduled work creation.</span></span>
1. <span data-ttu-id="0b5a5-116">*Feladatalapú hullámcímke-nyomtatás* – Ez a funkció szükséges a hullámcímke-nyomtatás külön tranzakció-hatókörre való felosztásához.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-116">*Task based wave label printing* – This feature is required to split off wave label printing to a separate transaction scope.</span></span>

## <a name="manually-enable-the-new-wave-step-method"></a><span data-ttu-id="0b5a5-117">Az új hullámlépés metódus manuális engedélyezése</span><span class="sxs-lookup"><span data-stu-id="0b5a5-117">Manually enable the new wave step method</span></span>

<span data-ttu-id="0b5a5-118">Először készítse el az új hullámlépés-metódust, majd engedélyezze az aszinkron feladatok párhuzamos feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-118">You must first create the new wave step method and enable it for parallel, asynchronous task processing.</span></span>

1. <span data-ttu-id="0b5a5-119">Ugorjon a  **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-119">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="0b5a5-120">A Művelet ablaktáblán válassza ki a **Metódus újragenerálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-120">On the Action Pane, select **Regenerate method**.</span></span> <span data-ttu-id="0b5a5-121">A *waveLabelPrinting* megjelenik a szállítási hullámsablonok során használható hullámfolyamati metódusok listájában.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-121">Notice that *waveLabelPrinting* is added to the list of wave process methods that you can use in your shipping wave templates.</span></span>
1. <span data-ttu-id="0b5a5-122">Válassza ki azt a rekordot, amelyben a **Metódus neve** mezőben a *waveLabelPrinting* beállítás van beállítva, majd a műveletpanelen válassza ki a **Feladat** konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-122">Select the record where the **Method name** field is set to *waveLabelPrinting*, and then, on the Action Pane, select **Task configuration**.</span></span>
1. <span data-ttu-id="0b5a5-123">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-123">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="0b5a5-124">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="0b5a5-124">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="0b5a5-125">**Raktár** – A munka-létrehozás feldolgozásának ütemezése során használt raktár kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-125">**Warehouse** – Select the warehouse that you will use to schedule work creation processing.</span></span> <span data-ttu-id="0b5a5-126">(Ha tesztelési célokra bemutatóadatokat használ, a *24*-es raktárat választhatja ki.)</span><span class="sxs-lookup"><span data-stu-id="0b5a5-126">(If you're using demo data for testing purposes, you can select warehouse *24*.)</span></span>
    - <span data-ttu-id="0b5a5-127">**Kötegelt feladatok maximális száma** – Adja meg a kötegelt feladatok maximális számát.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-127">**Maximum number of batch tasks** – Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="0b5a5-128">A legtöbb esetben az értéknek *8* és *16* között kell lennie.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-128">In most cases, the value should be from *8* through *16*.</span></span> <span data-ttu-id="0b5a5-129">Ugyanakkor javasoljuk, hogy csak egy kísérlettel keresse meg az optimális beállítást az esetekhez.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-129">However, we recommend that you experiment to find the optimal setting for your scenarios.</span></span>
    - <span data-ttu-id="0b5a5-130">**Hullámfeldolgozási kötegcsoport** – A kötegelt várólistájának feldolgozásának optimalizálása érdekében válasszon ki egy külön hullámfeldolgozási kötegcsoportot.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-130">**Wave processing batch group** – Select a dedicated wave processing batch group to optimize batch queue processing.</span></span>

<span data-ttu-id="0b5a5-131">Most frissíthet egy meglévő hullámsablont, hogy az a *Hullámcímke-nyomtatási* mhullámfeldolgozási metódust használja.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-131">You can now update an existing wave template so that it uses the *Wave label printing* wave processing method.</span></span> <span data-ttu-id="0b5a5-132">Másik lehetőségként létrehozhat egy új hullámsablont, amely azt használja.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-132">Alternatively, you can create a new wave template that uses it.</span></span>

1. <span data-ttu-id="0b5a5-133">Ugorjon a  **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-133">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="0b5a5-134">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="0b5a5-135">A lista ablaktáblában válassza ki a frissíteni kívánt hullámsablont.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-135">In the list pane, select the wave template to update.</span></span> <span data-ttu-id="0b5a5-136">(Ha tesztelési célokra bemutatóadatokat használ, a *24 Szállítási alapértelmezés* választhatja ki.)</span><span class="sxs-lookup"><span data-stu-id="0b5a5-136">(If you're using demo data for testing purposes, you can select *24 Shipping default*.)</span></span>
1. <span data-ttu-id="0b5a5-137">A **Módszerek** Gyorslapon a **Fennmaradó módszerek** oszlopban válassza ki a sort, ahol a **Név** mező a *waveLabelPrinting* értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-137">On the **Methods** FastTab, in the **Remaining methods** column, select the row where the **Name** field is set to *waveLabelPrinting*.</span></span>
1. <span data-ttu-id="0b5a5-138">Válassza ki a **hozzáadás** (jobbra nyíl gombot), hogy a kiválasztott sort áthelyezze a **Kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-138">Select **add** (right arrow button) to move the selected row to the **Selected methods** column.</span></span>
1. <span data-ttu-id="0b5a5-139">A **Hullámlépés kódja** mezőben adja meg a hullámlépés kódját, amely a hullámsablon és egy hullámcímkesablon kapcsolatának adható.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-139">In the **Wave step code** field, enter a wave step code that will be used to connect the wave template with a wave label template.</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="0b5a5-140">Hullámfeladat-feldolgozási küszöbérték adatainak beállítása</span><span class="sxs-lookup"><span data-stu-id="0b5a5-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="0b5a5-141">Az első alkalommal, amikor egy hullámfolyamat bármilyen feladatalapú feldolgozással fut, a rendszer létrehozza az alapértelmezett hullámfeladat-feldolgozási küszöbadatokat.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-141">The first time that a wave process runs by using any task-based processing, the system creates default wave task processing threshold data.</span></span> <span data-ttu-id="0b5a5-142">Ennek az adatnak a segítségével lehet szabályozni, hogy fusson-e aszinkron módon és feladatalapúan a hullámfeldolgozás, így lehetővé válik a feldolgozás és a hullámcímkék létrehozása párhuzamosan.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-142">This data is used to control whether wave processing will run asynchronously and be task-based, so that it can process and create wave labels in parallel.</span></span>

<span data-ttu-id="0b5a5-143">Az alapértelmezett adatok kezdetben *1*-es küszöbértéket használnak a munkaazonosítók minimális számára (`MinimumWorkThresholdForLabelPrinting`).</span><span class="sxs-lookup"><span data-stu-id="0b5a5-143">The default data initially uses a threshold value of *1* for the minimum number of work IDs (`MinimumWorkThresholdForLabelPrinting`).</span></span> <span data-ttu-id="0b5a5-144">Ezért amikor a rendszer egynél több munkaazonosítójú hullámot dolgoz fel, a hullámcímkék feladat alapú feldolgozását fogja használni egy külön tranzakcióban.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-144">Therefore, when the system processes a wave that has more than one work ID, it will use task-based processing of wave labels in a separate transaction.</span></span> <span data-ttu-id="0b5a5-145">A tesztkörnyezetben manuálisan is beszúrhatja, vagy frissítheti a `WHSWaveTaskProcessingThresholdParameters` táblázat adatait.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-145">You can manually insert or update this data in the `WHSWaveTaskProcessingThresholdParameters` table in your test environments.</span></span> <span data-ttu-id="0b5a5-146">Ha éles környezetben módosítja a beállítást, forduljon a Microsoft ügyfélszolgálatához, és kérje a frissítés kérését.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-146">To change the setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a><span data-ttu-id="0b5a5-147">A hullámfeldolgozási logika változtatása feladatalapú hullámcímke-nyomtatás használata esetén</span><span class="sxs-lookup"><span data-stu-id="0b5a5-147">Changes to the wave processing logic when task-based wave label printing is used</span></span>

<span data-ttu-id="0b5a5-148">Ha a hullámcímke-feldolgozás meghaladja a hullámfeladatok feldolgozásának küszöbértékét, a rendszer elindítja a feladat alapú feldolgozást.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-148">If the wave label processing exceeds the wave task processing threshold, task-based processing is initiated.</span></span> <span data-ttu-id="0b5a5-149">A hullámsablonnak megfelelő következő hullámfeldolgozásban a hullámcímke-nyomtatás közvetlenül a munka létrehozása után, önálló *ttsbegin*/*ttscommit* tranzakcióban fog futni.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-149">In the next wave processing that fits the wave template, wave label printing will run in a standalone *ttsbegin*/*ttscommit* transaction immediately after work creation.</span></span> <span data-ttu-id="0b5a5-150">Ha a hullámsablonban be van állítva a munka feloldása (zárolás feloldása) automatikus futásra, csak a hullámcímke-nyomtatási folyamat sikeres befejezése után fordul elő.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-150">If work release (unblocking) is configured on the wave template to run automatically, it occurs only after the wave label printing process is successfully completed.</span></span>

<span data-ttu-id="0b5a5-151">Ha a hullámcímke létrehozása sikertelen (például a munkamennyiség hullámcímke-mennyiségre történő konvertálása sikertelen, és hibát eredményez), csak a megfelelő tranzakció sikertelen.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-151">If wave label generation fails (for example, if conversion of the work quantity to the wave label quantity fails and throws an error), only the appropriate transaction fails.</span></span> <span data-ttu-id="0b5a5-152">A korábban létrehozott munka befagyasztva marad.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-152">The work that was previously created remains frozen.</span></span> <span data-ttu-id="0b5a5-153">A hibák kijavítása és a hullámcímkék nyomtatása érdekében hajtsa végre a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-153">To correct errors and print the wave labels, follow these steps.</span></span>

1. <span data-ttu-id="0b5a5-154">Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-154">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="0b5a5-155">Válassza ki a releváns hullámot a rácsban.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-155">Select the relevant wave in the grid.</span></span>
1. <span data-ttu-id="0b5a5-156">A Műveleti ablaktáblán a **Hullám** lapon a **Nyomtatás** csoportban válassza a **Hullámcímkék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-156">On the Action Pane, on the **Wave** tab, in the **Print** group, select **Wave labels**.</span></span>
1. <span data-ttu-id="0b5a5-157">A címkék nyomtatásához kövesse a képernyőn látható utasításokat.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-157">Follow the on-screen instructions to send the labels for printing.</span></span>
1. <span data-ttu-id="0b5a5-158">A műveletpanel **Hullám** lapján, a **Hullám** csoportban válassza a **Kiadás** lehetőséget a kiválasztott hullám munkához való manuális kiadáshoz.</span><span class="sxs-lookup"><span data-stu-id="0b5a5-158">On the Action Pane, on the **Wave** tab, in the **Wave** group, select **Release** to manually release the work for the selected wave.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0b5a5-159">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0b5a5-159">Additional resources</span></span>

- [<span data-ttu-id="0b5a5-160">Hullámcímke nyomtatása</span><span class="sxs-lookup"><span data-stu-id="0b5a5-160">Wave label printing</span></span>](configure-wave-label-printing.md)
- [<span data-ttu-id="0b5a5-161">Munka létrehozásának ütemezése a hullám során</span><span class="sxs-lookup"><span data-stu-id="0b5a5-161">Schedule work creation during wave</span></span>](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]