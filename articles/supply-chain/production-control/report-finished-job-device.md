---
title: Jelentés befejezettként a feladatkártya eszközből
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a rendszert úgy, hogy a Feladatkártya-eszköz felhasználói a termelési rendelésből a készletbe bejelenthetik a kész termékeket.
author: johanhoffmann
manager: tfehr
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f5d34893ddc8adc3785ec50dbd72438cf8f68c5d
ms.sourcegitcommit: 52ba8d3e6af72df5dab6c04b9684a61454d353ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/26/2020
ms.locfileid: "3403262"
---
# <a name="report-as-finished-from-the-job-card-device"></a><span data-ttu-id="9c83b-103">Jelentés befejezettként a feladatkártya eszközből</span><span class="sxs-lookup"><span data-stu-id="9c83b-103">Report as finished from the job card device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c83b-104">A dolgozók a munkakártya eszköz **jelentés-végrehajtási** lapját használják a termelési feladatokra kitöltött mennyiségek jelentése céljából.</span><span class="sxs-lookup"><span data-stu-id="9c83b-104">Workers use the **Report progress** page on the job card device to report quantities that have been completed for a production job.</span></span>

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a><span data-ttu-id="9c83b-105">Annak megadása, hogy a készként jelentett mennyiségeket adja-e a program a készlethez</span><span class="sxs-lookup"><span data-stu-id="9c83b-105">Control whether quantities that are reported as finished are added to inventory</span></span>

<span data-ttu-id="9c83b-106">A következő lépésekkel szabályozhatja, hogy az utolsó műveletben befejezettként jelentett mennyiségeket adja-e a rendszer a készlethez.</span><span class="sxs-lookup"><span data-stu-id="9c83b-106">To control whether and how the quantities that are reported as finished on the last operation should be added to inventory, follow these steps.</span></span>

1. <span data-ttu-id="9c83b-107">Kattintson a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> Termelési rendelés alapértékei** pontra.</span><span class="sxs-lookup"><span data-stu-id="9c83b-107">Go to **Product control \> Setup \> Manufacturing execution \> Production order defaults**.</span></span>
1. <span data-ttu-id="9c83b-108">A **Jelentés készként** lapon adja meg a **Készként jelentés online frissítése** mezőt a következő értékek valamelyikeként:</span><span class="sxs-lookup"><span data-stu-id="9c83b-108">On the **Report as finished** tab, set the **Update finished report on-line** field to one of the following values:</span></span>

    - <span data-ttu-id="9c83b-109">**Nem** – a rendszer nem adja hozzá a mennyiséget a készlethez, ha a legutóbbi műveletben mennyiséget jelentenek.</span><span class="sxs-lookup"><span data-stu-id="9c83b-109">**No** – No quantity will be added to inventory when quantities are reported on the last operation.</span></span> <span data-ttu-id="9c83b-110">A termelés állapota soha nem változik.</span><span class="sxs-lookup"><span data-stu-id="9c83b-110">The status of the production order will never change.</span></span>
    - <span data-ttu-id="9c83b-111">**Állapot + mennyiség** – A termelési rendelés állapota *Készként jelentve lesz*, és a program készként jelenti a mennyiséget a készletbe.</span><span class="sxs-lookup"><span data-stu-id="9c83b-111">**Status + Quantity** – The status of the production order will change to *Reported as finished*, and the quantity will be reported as finished to inventory.</span></span>
    - <span data-ttu-id="9c83b-112">**Mennyiség** – A termelési rendelés állapota készként lesz jelentve a készletbe, de termelési rendelés állapota soha nem változik.</span><span class="sxs-lookup"><span data-stu-id="9c83b-112">**Quantity** – The quantity will be reported as finished to inventory, but the status of the production order will never change.</span></span>
    - <span data-ttu-id="9c83b-113">**Állapot** – Csak a termelési rendelés állapota változik.</span><span class="sxs-lookup"><span data-stu-id="9c83b-113">**Status** – Only the status of the production order will change.</span></span> <span data-ttu-id="9c83b-114">A rendszer nem adja hozzá a mennyiségeket a készlethez, ha a legutóbbi műveletben mennyiséget jelentenek.</span><span class="sxs-lookup"><span data-stu-id="9c83b-114">No quantities will be added to inventory when quantities are reported on the last operation.</span></span>

> [!NOTE]
> <span data-ttu-id="9c83b-115">A mennyiségek nem követhetők a készletben, ha az ezeket készként jelentő műveletek nem az utolsó műveletként vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="9c83b-115">Quantities aren't tracked in inventory if the operations that they are reported as finished on aren't defined as the last operation.</span></span> <span data-ttu-id="9c83b-116">Ezek a mennyiségek azonban felhasználhatók a haladás megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="9c83b-116">However, those quantities can be used to view progress.</span></span> <span data-ttu-id="9c83b-117">Olyan szabályok is szerepelhetnek, amelyek meghatározzák, hogy a dolgozók elindíthatják-e a következő műveletet, mielőtt a korábbi műveletre vonatkozóan meghatározott küszöbértéket elérnek.</span><span class="sxs-lookup"><span data-stu-id="9c83b-117">They can also be included in rules that control whether workers can start the next operation before a defined threshold of reported quantities on the previous operation is reached.</span></span> <span data-ttu-id="9c83b-118">Ezeket a szabályokat a **Mennyiségi ellenőrzés** lapja határozza meg a **Termelési rendelés alapértelmezései** lapnak.</span><span class="sxs-lookup"><span data-stu-id="9c83b-118">You can define these rules on the **Quantity validation** tab of the **Production order defaults** page.</span></span>

<span data-ttu-id="9c83b-119">A **termelési rendelés alapadatai** munkalapjával kapcsolatos további tudnivalókat lásd: [Termelési paraméterek a gyártás végrehajtásánál](production-parameters-manufacturing-execution.md).</span><span class="sxs-lookup"><span data-stu-id="9c83b-119">For more information about how to work with the **Production order defaults** page, see [Production parameters in Manufacturing execution](production-parameters-manufacturing-execution.md).</span></span>

## <a name="report-batch-controlled-items-as-finished"></a><span data-ttu-id="9c83b-120">Kötegelt vezérelt cikkek jelentése készként</span><span class="sxs-lookup"><span data-stu-id="9c83b-120">Report batch-controlled items as finished</span></span>

<span data-ttu-id="9c83b-121">A feladatkártya-eszköz három esetet támogat a kötegelt cikkek jelentéséhez.</span><span class="sxs-lookup"><span data-stu-id="9c83b-121">The job card device supports three scenarios for reporting on batch items.</span></span> <span data-ttu-id="9c83b-122">Ezek a helyzetek mind a speciális raktári folyamatokhoz engedélyezett cikkekre, mind a speciális raktári folyamatokhoz nem engedélyezett cikkekre vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="9c83b-122">These scenarios apply both to items that are enabled for advanced warehouse processes and to items that aren't enabled for advanced warehouse processes.</span></span>

- <span data-ttu-id="9c83b-123">**Kötegelt számok kézi hozzárendelése:** A dolgozók egyéni kötegszámot adnak meg.</span><span class="sxs-lookup"><span data-stu-id="9c83b-123">**Manually assigned batch numbers:** Workers enter a custom batch number.</span></span> <span data-ttu-id="9c83b-124">Ez a kötegszám olyan külső forrásból származhat, amelyet a rendszer nem ismer.</span><span class="sxs-lookup"><span data-stu-id="9c83b-124">This batch number might come from an external source that isn't known to the system.</span></span>
- <span data-ttu-id="9c83b-125">**Előre definiált kötegszám:** A dolgozók egy kötegszámnak a kiválasztását végzik el egy listáról, amelyet a rendszer automatikusan generált, a termelési rendelésnek a feladatkártya-eszközbe történő kiadása előtt.</span><span class="sxs-lookup"><span data-stu-id="9c83b-125">**Predefined batch numbers:** Workers select a batch number in a list of batch numbers that the system automatically generates before the production order is released to the job card device.</span></span>
- <span data-ttu-id="9c83b-126">**Rögzített kötegszámok:** A dolgozók kötegszámot nem adnak meg.</span><span class="sxs-lookup"><span data-stu-id="9c83b-126">**Fixed batch numbers:** Workers don't enter or select a batch number.</span></span> <span data-ttu-id="9c83b-127">Helyette a rendszer automatikusan hozzárendel egy kötegszámot a termelési rendeléshez a kiadás előtt.</span><span class="sxs-lookup"><span data-stu-id="9c83b-127">Instead, the system automatically assigns a batch number to the production order before it's released.</span></span>

<span data-ttu-id="9c83b-128">Kövesse az alábbi lépéseket az egyes forgatókönyvek engedélyezéséhez:</span><span class="sxs-lookup"><span data-stu-id="9c83b-128">To enable each scenario, follow these steps.</span></span>

1. <span data-ttu-id="9c83b-129">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9c83b-129">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="9c83b-130">Válassza ki az konfigurálni kívánt terméket.</span><span class="sxs-lookup"><span data-stu-id="9c83b-130">Select the product to configure.</span></span>
1. <span data-ttu-id="9c83b-131">A **Készlet kezelése** gyorslap **Kötegszámcsoport** mezőjében válassza ki azt a nyomon követési számot, amely a forgatókönyv támogatásához van beállítva.</span><span class="sxs-lookup"><span data-stu-id="9c83b-131">On the **Manage inventory** FastTab, in the **Batch number group** field, select the tracking number group that is set up to support your scenario.</span></span>

> [!NOTE]
> <span data-ttu-id="9c83b-132">Alapértelmezés szerint, ha egy köteg által vezérelt termékhez nem rendel hozzá kötegszám-csoportot, a Feladatkártya-eszköz a készként való jelentés során manuális bejegyzést ad a kötegszám számára.</span><span class="sxs-lookup"><span data-stu-id="9c83b-132">By default, if no batch number group is assigned to a batch-controlled product, the job card device provides manual entry for the batch number during reporting as finished.</span></span>

<span data-ttu-id="9c83b-133">A következő alszakaszok azt írják le, hogyan lehet beállítani a követésiszám-csoportokat, hogy a fenti három forgatókönyvet támogassák a kötegelt cikkek jelentéséhez.</span><span class="sxs-lookup"><span data-stu-id="9c83b-133">The following subsections describe how to set up tracking number groups to support each of the three scenarios for reporting on batch items.</span></span>

### <a name="enable-batch-number-reporting-on-the-job-card-device"></a><span data-ttu-id="9c83b-134">Kötegszám-jelentés engedélyezése a feladatkártya-eszközön</span><span class="sxs-lookup"><span data-stu-id="9c83b-134">Enable batch number reporting on the job card device</span></span>

<span data-ttu-id="9c83b-135">Ha engedélyezni szeretné, hogy a feladatkártya-eszközök elfogadhassanak egy kötegszámot a készként való jelentés során, akkor a [szolgáltatások kezelésével](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) be kell kapcsolni a következő szolgáltatásokat (ebben a sorrendben):</span><span class="sxs-lookup"><span data-stu-id="9c83b-135">To enable your job card devices to accept a batch number during reporting as finished, you must use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the following features (in this order):</span></span>

1. <span data-ttu-id="9c83b-136">Javított felhasználói élmény a feladatkártya eszközében lévő jelentés az előrehaladásról párbeszédpanelhez</span><span class="sxs-lookup"><span data-stu-id="9c83b-136">Improved user experience for the Report progress dialog in the Job Card Device</span></span>
1. <span data-ttu-id="9c83b-137">Engedélyezze, hogy a köteg-és sorozatszámokat megadhassa befejezettként a Feladatkártya eszközéből (előzetes)</span><span class="sxs-lookup"><span data-stu-id="9c83b-137">Enable to enter batch and serial numbers while reporting as finished from the Job Card Device (Preview)</span></span>

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a><span data-ttu-id="9c83b-138">Olyan követésiszám-csoport megadása, amellyel a dolgozók manuálisan rendelhetik hozzá a köteg számát</span><span class="sxs-lookup"><span data-stu-id="9c83b-138">Set up a tracking number group that lets workers manually assign a batch number</span></span>

<span data-ttu-id="9c83b-139">A kötegszámok manuális kiosztásának engedélyezéséhez, kövesse az alábbi lépéseket egy követési számcsoportot beállításához:</span><span class="sxs-lookup"><span data-stu-id="9c83b-139">To allow for manually assigned batch numbers, follow these steps to set up a tracking number group.</span></span>

1. <span data-ttu-id="9c83b-140">Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.</span><span class="sxs-lookup"><span data-stu-id="9c83b-140">Go to **Inventory management \> Setup \> Dimensions \> Tracking number groups**.</span></span>
1. <span data-ttu-id="9c83b-141">Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.</span><span class="sxs-lookup"><span data-stu-id="9c83b-141">Create or select the tracking number group to set up.</span></span>
1. <span data-ttu-id="9c83b-142">Az **Általános** gyorslapon állítsa a **Manuális** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="9c83b-142">On the **General** FastTab, set the **Manual** option to **Yes**.</span></span>

    <span data-ttu-id="9c83b-143">![Követésiszám-csoportok lap](media/tracking-number-group-manual.png "Követésiszám-csoportok lap")</span><span class="sxs-lookup"><span data-stu-id="9c83b-143">![Tracking number groups page](media/tracking-number-group-manual.png "Tracking number groups page")</span></span>

1. <span data-ttu-id="9c83b-144">A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.</span><span class="sxs-lookup"><span data-stu-id="9c83b-144">Set other values as you require, and then select this tracking number group as the batch number group for released products that you want to use this scenario for.</span></span>

<span data-ttu-id="9c83b-145">Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy szövegmezőt jelenít meg, ahol a dolgozók bármilyen értéket meghatározhatnak.</span><span class="sxs-lookup"><span data-stu-id="9c83b-145">When you use this scenario, the **Batch number** field that the **Report progress** page on the job card device provides is a text box where workers can enter any value.</span></span>

<span data-ttu-id="9c83b-146">![Előrehaladás jelentése lap a manuális kötegszám mezővel](media/job-card-device-batch-manual.png "Előrehaladás jelentése lap a manuális kötegszám mezővel")</span><span class="sxs-lookup"><span data-stu-id="9c83b-146">![Report progress page with a field for manual batch numbers](media/job-card-device-batch-manual.png "Report progress page with a field for manual batch numbers")</span></span>

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a><span data-ttu-id="9c83b-147">Egy követésiszám-csoport beállítása, amely előre definiált kötegszámok listáját tartalmazza</span><span class="sxs-lookup"><span data-stu-id="9c83b-147">Set up a tracking number group that provides a list of predefined batch numbers</span></span>

<span data-ttu-id="9c83b-148">Előre meghatározott kötegszámok listájának megadásához, kövesse az alábbi lépéseket egy követésiszám-csoport beállításához:</span><span class="sxs-lookup"><span data-stu-id="9c83b-148">To provide a list of predefined batch numbers, follow these steps to set up a tracking number group.</span></span>

1. <span data-ttu-id="9c83b-149">Ugrás: **Készletkezelés \> Beállítás > Dimenziók \> Követésiszám-csoportok**.</span><span class="sxs-lookup"><span data-stu-id="9c83b-149">Go to **Inventory management \> Setup > Dimensions \> Tracking number groups**.</span></span>
1. <span data-ttu-id="9c83b-150">Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.</span><span class="sxs-lookup"><span data-stu-id="9c83b-150">Create or select the tracking number group to set up.</span></span>
1. <span data-ttu-id="9c83b-151">Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="9c83b-151">On the **General** FastTab, set the **Only for inventory transactions** option to **Yes**.</span></span>
1. <span data-ttu-id="9c83b-152">A **Mennyiségenként** mező használatával a kötegek számát a megadott érték alapján osztja fel.</span><span class="sxs-lookup"><span data-stu-id="9c83b-152">Use the **Per qty.** field to split batch numbers per quantity, based on the value that you enter.</span></span> <span data-ttu-id="9c83b-153">Például van egy termelési rendelés tíz darabra, és a **Mennyiségenként** mező értéke *2*.</span><span class="sxs-lookup"><span data-stu-id="9c83b-153">For example, you have a production order for ten pieces, and the **Per qty.** field is set to *2*.</span></span> <span data-ttu-id="9c83b-154">Ebben az esetben a létrehozáskor öt kötegszám lesz hozzárendelve a termelési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="9c83b-154">In this case, five batch numbers will be assigned to the production order when it's created.</span></span>

    <span data-ttu-id="9c83b-155">![Követésiszám-csoportok lap](media/tracking-number-group-predefined.png "Követésiszám-csoportok lap")</span><span class="sxs-lookup"><span data-stu-id="9c83b-155">![Tracking number groups page](media/tracking-number-group-predefined.png "The Tracking number groups page")</span></span>

1. <span data-ttu-id="9c83b-156">A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.</span><span class="sxs-lookup"><span data-stu-id="9c83b-156">Set other values as you require, and then select this tracking number group as the batch number group for released products that you want to use this scenario for.</span></span>

<span data-ttu-id="9c83b-157">Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy legördülő menüt jelenít meg, ahol a dolgozóknak egy előre megadott értéket kell megadniuk.</span><span class="sxs-lookup"><span data-stu-id="9c83b-157">When you use this scenario, the **Batch number** field that the **Report progress** page on the job card device provides is a drop-down list where workers must select a predefined value.</span></span>

<span data-ttu-id="9c83b-158">![Előrehaladás jelentése lap előre megadott kötegszámok listájával](media/job-card-device-batch-predefined.png "Előrehaladás jelentése lap előre megadott kötegszámok listájával")</span><span class="sxs-lookup"><span data-stu-id="9c83b-158">![Report progress page with a list of predefined batch numbers](media/job-card-device-batch-predefined.png "Report progress page with a list of predefined batch numbers")</span></span>

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a><span data-ttu-id="9c83b-159">Olyan követésiszám-csoport megadása, amely automatikusan osztja a kötegszámokat</span><span class="sxs-lookup"><span data-stu-id="9c83b-159">Set up a tracking number group that automatically assigns batch numbers</span></span>

<span data-ttu-id="9c83b-160">Ha a kötegek számát automatikusan kell hozzárendelni, a dolgozói beavatkozás nélkül, a következő lépésekkel lehet beállítani a követésiszám-csoportot.</span><span class="sxs-lookup"><span data-stu-id="9c83b-160">If batch numbers should be assigned automatically, without worker input, follow these steps to set up a tracking number group.</span></span>

1. <span data-ttu-id="9c83b-161">Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.</span><span class="sxs-lookup"><span data-stu-id="9c83b-161">Go to **Inventory management \> Setup \> Dimensions \> Tracking number groups**.</span></span>
1. <span data-ttu-id="9c83b-162">Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.</span><span class="sxs-lookup"><span data-stu-id="9c83b-162">Create or select the tracking number group to set up.</span></span>
1. <span data-ttu-id="9c83b-163">Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="9c83b-163">On the **General** FastTab, set the **Only for inventory transactions** option to **No**.</span></span>
1. <span data-ttu-id="9c83b-164">Állítsuk a **Manuális** beállítást **Nem** értékre.</span><span class="sxs-lookup"><span data-stu-id="9c83b-164">Set the **Manual** option to **No**.</span></span>

    <span data-ttu-id="9c83b-165">![Követésiszám-csoportok lap](media/tracking-number-group-fixed.png "Követésiszám-csoportok lap")</span><span class="sxs-lookup"><span data-stu-id="9c83b-165">![Tracking number groups page](media/tracking-number-group-fixed.png "Tracking number groups page")</span></span>

1. <span data-ttu-id="9c83b-166">A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.</span><span class="sxs-lookup"><span data-stu-id="9c83b-166">Set other values as you require, and then select this tracking number group as the batch number group for released products that you want to use this scenario for.</span></span>

<span data-ttu-id="9c83b-167">Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy értéket jelenít meg, amelyet a dolgozók nem módosíthatnak.</span><span class="sxs-lookup"><span data-stu-id="9c83b-167">When you use this scenario, the **Batch number** field that the **Report progress** page on the job card device provides shows a value, but workers can't edit it.</span></span>

<span data-ttu-id="9c83b-168">![Előrehaladás jelentése lap a rögzített kötegszámmal](media/job-card-device-batch-fixed.png "Előrehaladás jelentése lap a rögzített kötegszámmal")</span><span class="sxs-lookup"><span data-stu-id="9c83b-168">![Report progress page with a fixed batch number](media/job-card-device-batch-fixed.png "Report progress page with a fixed batch number")</span></span>

## <a name="report-as-finished-to-a-license-plate"></a><span data-ttu-id="9c83b-169">Jelentés készként egy azonosítótáblára</span><span class="sxs-lookup"><span data-stu-id="9c83b-169">Report as finished to a license plate</span></span>

<span data-ttu-id="9c83b-170">A speciális raktári folyamatok az azonosítótábla-dimenzió segítségével nyomon követhetik az erre a célra beállított raktári helyeket.</span><span class="sxs-lookup"><span data-stu-id="9c83b-170">Advanced warehouse processes can use the license plate dimension to track inventory on warehouse locations that have been set up for this purpose.</span></span> <span data-ttu-id="9c83b-171">Ebben az esetben az azonosítótábla számának megadása szükséges, ha a dolgozó készként jelenti a mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="9c83b-171">In this case, the license plate number is required when a worker reports quantities as finished.</span></span>

### <a name="enable-license-plate-reporting-and-label-printing"></a><span data-ttu-id="9c83b-172">Azonosítótábla jelentésének és címke nyomtatásának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="9c83b-172">Enable license plate reporting and label printing</span></span>

<span data-ttu-id="9c83b-173">Az ebben a szakaszban ismertetett szolgáltatások használatához a [szolgáltatások kezelésénél](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) be kell kapcsolni a következő szolgáltatásokat (ebben a sorrendben):</span><span class="sxs-lookup"><span data-stu-id="9c83b-173">To use the features that are described in this section, you must use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the following features (in this order):</span></span>

1. <span data-ttu-id="9c83b-174">A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla</span><span class="sxs-lookup"><span data-stu-id="9c83b-174">License plate for reporting as finished added to the Job Card Device</span></span>
1. <span data-ttu-id="9c83b-175">Az azonosítótábla-szám automatikus létrehozásának engedélyezése, amikor a feladatkártya eszközében befejezettként jelentik</span><span class="sxs-lookup"><span data-stu-id="9c83b-175">Enable automatic generation of license plate number when reporting as finished in the job card device</span></span>
1. <span data-ttu-id="9c83b-176">Címke nyomtatása a Feladatkártya eszközéből</span><span class="sxs-lookup"><span data-stu-id="9c83b-176">Print label from Job Card Device</span></span>

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a><span data-ttu-id="9c83b-177">Jelentés készként egy azonosítótáblára beállítása</span><span class="sxs-lookup"><span data-stu-id="9c83b-177">Set up reporting as finished to a license plate</span></span>

<span data-ttu-id="9c83b-178">A következő lépésekkel szabályozhatja, hogy a dolgozók egy meglévő azonosítótábla újra felhasználható-e, vagy új rendszámtábla előállítása történjen, a mennyiségek készként jelentésekor.</span><span class="sxs-lookup"><span data-stu-id="9c83b-178">To control whether workers should reuse an existing license plate or generate a new license plate when they report quantities as finished, follow these steps.</span></span>

1. <span data-ttu-id="9c83b-179">Ugrás a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> Feladatkártya eszközének konfigurálása** részre.</span><span class="sxs-lookup"><span data-stu-id="9c83b-179">Go to **Production control \> Setup \> Manufacturing execution \> Configure job card for devices**.</span></span>
2. <span data-ttu-id="9c83b-180">Állítsa be a következő lehetőségeket minden egyes eszköznél:</span><span class="sxs-lookup"><span data-stu-id="9c83b-180">Set the following options for each device:</span></span>

    - <span data-ttu-id="9c83b-181">**Azonosítótábla előállítása** – Ezt a lehetőséget **Igen** értékre állítsa új azonosítótábla előállításához minden készként történő jelentésenél.</span><span class="sxs-lookup"><span data-stu-id="9c83b-181">**Generate license plate** – Set this option to **Yes** to generate a new license plate for each report as finished.</span></span> <span data-ttu-id="9c83b-182">A beállítása **Nem** legyen, ha minden készként jelentéshez egy meglévő rendszámtábla használandó.</span><span class="sxs-lookup"><span data-stu-id="9c83b-182">Set it to **No** if an existing license plate should be used for each report as finished.</span></span>
    - <span data-ttu-id="9c83b-183">**Címke nyomtatása** – Ez a lehetőséget akkor legyen **Igen**, ha a dolgozó minden készként jelentéshez azonosítótábla-címkét nyomtat.</span><span class="sxs-lookup"><span data-stu-id="9c83b-183">**Print label** – Set this option to **Yes** if the worker must print a license plate label for each report as finished.</span></span> <span data-ttu-id="9c83b-184">Állítsa **Nem** értékre, ha nem szükséges címke.</span><span class="sxs-lookup"><span data-stu-id="9c83b-184">Set it to **No** if no label is required.</span></span> 

<span data-ttu-id="9c83b-185">![Feladatkártya konfigurálása az eszközökhöz oldal](media/config-job-card-raf.png "Feladatkártya konfigurálása az eszközökhöz oldal")</span><span class="sxs-lookup"><span data-stu-id="9c83b-185">![Configure job card for devices page](media/config-job-card-raf.png "Configure job card for devices page")</span></span>

> [!NOTE]
> <span data-ttu-id="9c83b-186">A címke konfigurálásához ugrás ide: **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Dokumentumirányítás**.</span><span class="sxs-lookup"><span data-stu-id="9c83b-186">To configure the label, go to **Warehouse management \> Setup \> Document routing \> Document routing**.</span></span> <span data-ttu-id="9c83b-187">A további tudnivalókat lásd az [Azonosítótábla címke nyomtatásának engedélyezése](../warehousing/tasks/license-plate-label-printing.md) című témakörben.</span><span class="sxs-lookup"><span data-stu-id="9c83b-187">For more information, see [Enable license plate label printing](../warehousing/tasks/license-plate-label-printing.md).</span></span>
