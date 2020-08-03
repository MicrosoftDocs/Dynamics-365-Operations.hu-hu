---
title: A hullámcímkék nyomtatásának beállítása és használata
description: Ez a témakör bemutatja a hullámcímkék nyomtatását, és elmagyarázza, hogy kell beállítani.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: configure-wave-label-printing
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 49e0ef1b3020cd1236203c0f243f145dd7a7c10d
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546435"
---
# <a name="set-up-and-use-wave-label-printing"></a><span data-ttu-id="c9ee3-103">A hullámcímkék nyomtatásának beállítása és használata</span><span class="sxs-lookup"><span data-stu-id="c9ee3-103">Set up and use wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9ee3-104">A hullámcímke nyomtatás alternatív megközelítést tesz lehetővé a címkék nyomtatásához egy új hullám lépés módszer bevezetésével, amellyel a címkék közvetlenül a hullámsablonból is létrehozhatók és kinyomtathatók a hullámvégrehajtás során.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="c9ee3-105">Így a címkék már akkor elérhetők lesznek, mielőtt a dolgozók a munkarendelést futtatják egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="c9ee3-106">A dolgozók ezt követően kitároláskor csatolhatják a szükséges címkéket, ahelyett, hogy a kitárolás után tennék.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="c9ee3-107">A hullámcímkék kinyomtatása Zebra programnyelvet (ZPL meghatározó mező) használ a címkék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="c9ee3-108">A címkék elrendezése három szakaszra (fejléc, szövegtörzs és lábléc) van osztva, amelyek lehetővé teszik az ismétlődő struktúrával rendelkező címkék használatát.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="c9ee3-109">A hullámcímkesablon mondja meg a rendszernek, melyik címkeelrendezést használja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="c9ee3-110">A felhasználók megadhatják, hogy melyik nyomtató legyen használatban.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-110">Users can specify which printer is used.</span></span> <span data-ttu-id="c9ee3-111">Szükség szerint egyszerre több nyomtatón is nyomtathatnak címkéket.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="c9ee3-112">A **hullámcímkék előzményei** lap a jelen beállítással létrehozott összes címke rekordját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="c9ee3-113">A címkék a munkafejlécek alapján is kinyomtathatók és leválogathatók, ezért szünetcímkék a munkfejlécek alapján is nyomtathatók, valamint nyomtathatók a konténerek tartalmát jelző címkék, esetcímkék és más hasonló címkék is.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="c9ee3-114">Ez a funkció nem helyettesíti a dokumentumátirányításon alapuló meglévő címkenyomtatási funkciókat.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="c9ee3-115">A hullámcímke-nyomtatás a következő fejlesztéseket kínálja:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="c9ee3-116">A címkék nyomtatása egyetlen munkasoron a kartondobozok számának megfelelően, a tárolóra bontás használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="c9ee3-117">(A "kartondoboz" egy egység, amely az egységszekvencia-csoport sorain van megjelölve.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="c9ee3-118">Több különböző címkefájl (például kartondoboz és raklapcímke) nyomtatása.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="c9ee3-119">A címkék felsorolásának szerepeltetése (például 1/124, 2/124, ... 124/124), és megadja a felsorolás tartományát (például a munkasort, a rakománysort vagy a szállítmányt).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="c9ee3-120">Fuvarlevél-azonosítók létrehozása és nyomtatása a címkékre a fuvarlevél létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="c9ee3-121">Egyedi szállítási tároló sorozatkód (SSCC) létrehozása mindegyik kartondobozhoz, és elhelyezése minden címkén.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="c9ee3-122">GS1-kompatibilis számsorozatok létrehozása a fuvarlevél-azonosítók és a SSCC-k számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="c9ee3-123">A címkék újranyomtatása mind a mobil eszközökből, mind a funkciógazdag kliensből.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="c9ee3-124">A címkék érvénytelenítése (például rövid kitárolási helyzetekben), majd újranyomtatása.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="c9ee3-125">Hullámcímke-előzmények törlése.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="c9ee3-126">A dokumentumátirányítási elrendezések javításai megoszlanak a dokumentumátirányítási elrendezések és a hullámcímkék elrendezései között.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="c9ee3-127">(További tájékoztatás: [Azonosítótáblák dokumentumátirányítási elrendezése](../warehousing/document-routing-layout-for-license-plates.md).)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="c9ee3-128">Ezek a javítások hatékonyabbá teszik a kartondobozok raklaposítás előtti címkézését.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="c9ee3-129">Különösen előnyös azoknak a vállalatoknak, amelyek nagy méretű kiskereskedőkhöz szállítanak, akik automatikusan megerősítik a rendelés bevételezését az egyes kartondobozok külön beolvasásával.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="c9ee3-130">Az ebben a témakörben leírt konfigurációs forgatókönyveket akár külön, akár együttesen is végre lehet hajtani az üzleti igényektől függően.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="c9ee3-131">A különböző hullámcímke-sablonokat tervezhet, amelyek sorozatban működnek (3. forgatókönyvben látható módon).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="c9ee3-132">Például az 1. forgatókönyvvel kartondobozcímkéket nyomtathat, a 2. forgatókönyvvel raklapcímkéket nyomtathat (ha a raklapok méretben és összetételben változnak).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="c9ee3-133">A Hullámcímke-nyomtatás funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="c9ee3-134">A *Hullámcímke-nyomtatás* funkciót használata előtt be kell kapcsolni a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="c9ee3-135">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c9ee3-136">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c9ee3-137">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c9ee3-138">**Funkció neve:** *Hullámcímke-nyomtatás*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="c9ee3-139">1. eset: Hullámcímke-nyomtatás, amelyben egyetlen hullámcímke jön létre</span><span class="sxs-lookup"><span data-stu-id="c9ee3-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="c9ee3-140">Ez a példa azt mutatja be, hogyan nyomtathat levélcímkéket egy nagyméretű kiskereskedő számára, amely automatikusan visszaigazolja a rendelések bevételezését a kartondobozok külön beolvasásával.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="c9ee3-141">Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="c9ee3-142">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="c9ee3-142">Make demo data available</span></span>

<span data-ttu-id="c9ee3-143">A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="c9ee3-144">Ellenőrizze, hogy a hullámcímke módszer elérhető-e</span><span class="sxs-lookup"><span data-stu-id="c9ee3-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="c9ee3-145">Előfordulhat, hogy újra kell generálnia a hullámfeldolgozási módszereket, hogy a hullámcímke-nyomtatási módszer elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="c9ee3-146">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="c9ee3-147">Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="c9ee3-148">Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="c9ee3-149">Hullámsablon konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-149">Configure a wave template</span></span>

<span data-ttu-id="c9ee3-150">A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonnal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="c9ee3-151">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="c9ee3-152">Válasszon sablont, például a **62 Szállítási alapértelmezés** sablont.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="c9ee3-153">A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="c9ee3-154">A **kiválasztott metódusok** oszlopban válassza ki a **hullámcímke nyomtatás** módját, és állítsa be a **Hullámlépéskód** mező értékét *PrintLabel* értékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="c9ee3-155">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="c9ee3-156">Hullámcímke elrendezésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-156">Create a wave label layout</span></span>

<span data-ttu-id="c9ee3-157">A címke elrendezése határozza meg, hogy milyen adatok jelennek meg a címkén, és milyen módon kell elrendezni. Itt megadhatja a nyomtatónak küldött ZPL kódot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="c9ee3-158">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="c9ee3-159">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-160">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-161">**Leírás:** *Kartondoboz (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="c9ee3-162">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-163">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c9ee3-164">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c9ee3-165">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c9ee3-166">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-167">**Sorazonosító:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="c9ee3-168">**Sor táblaneve:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="c9ee3-169">**Sor kezdő pozíciója:** *0*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="c9ee3-170">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c9ee3-171">**Sormagasság** *0*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-171">**Row height:** *0*</span></span>

        <span data-ttu-id="c9ee3-172">Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="c9ee3-173">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="c9ee3-174">Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="c9ee3-175">**Sorok száma oldalanként** *1*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="c9ee3-176">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c9ee3-177">Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="c9ee3-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-178">Close the page.</span></span>
1. <span data-ttu-id="c9ee3-179">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c9ee3-180">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-181">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-182">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-183">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c9ee3-184">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="c9ee3-185">Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="c9ee3-186">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="c9ee3-187">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c9ee3-188">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c9ee3-189">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c9ee3-190">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="c9ee3-191">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c9ee3-192">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-192">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="c9ee3-193">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c9ee3-194">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ee3-195">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="c9ee3-196">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c9ee3-197">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="c9ee3-198">A címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="c9ee3-199">Hullámcímke típusának létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-199">Create a wave label type</span></span>

<span data-ttu-id="c9ee3-200">A hullámcímkék típusaival a hullámcímkesablonok egy egységhez kapcsolhatók egy egységszekvencia-csoport soraiban.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="c9ee3-201">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímketípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="c9ee3-202">Adjon hozzá egy hullámcímketípust, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-203">**Címke típusa:** *kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-204">**Leírás:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="c9ee3-205">Egységszekvencia-csoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-205">Set up unit sequence groups</span></span>

<span data-ttu-id="c9ee3-206">Ezután állítsa be a hullámcímke típusának egységszekvencia-csoportját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="c9ee3-207">Lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Egységszekvencia-csoportok** részre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="c9ee3-208">Válassza az **Ea Box PL** csoportot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="c9ee3-209">A **Doboz** sorban állítsa a **Hullámcímketípus** mezőt *Kartondoboz* értékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="c9ee3-210">Hullámcímkesablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-210">Create a wave label template</span></span>

<span data-ttu-id="c9ee3-211">Ezután hozza létre a hullámcímke sablonját a hullámcímkék típusához.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="c9ee3-212">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="c9ee3-213">Adjon hozzá egy hullámcímkesablont, és állítsa be a következő értékeket a fejlécben:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="c9ee3-214">**Címkesablon neve:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="c9ee3-215">**Leírás:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="c9ee3-216">**Hullámlépés kódja:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="c9ee3-217">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c9ee3-218">Az **általános** gyorslapon adja meg a **hullámcímke típusa** mezőt *kartondoboz* értékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="c9ee3-219">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy új sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-220">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-221">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c9ee3-222">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c9ee3-223">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-224">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c9ee3-225">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c9ee3-226">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-227">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-228">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-229">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c9ee3-230">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c9ee3-231">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="c9ee3-232">A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="c9ee3-233">A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-234">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-235">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-236">**Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="c9ee3-237">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c9ee3-238">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="c9ee3-239">Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="c9ee3-240">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="c9ee3-241">A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="c9ee3-242">A **Hullámcímkesablon-csoport**párbeszédablakban válassza ki azt a sort, amelynek **Hivatkozási mező neve** mezője *Hivatkozási rakománysor-azonosító* értékre van állítva, majd jelölje be a sorhoz tartozó **Címke-összeállítási azonosító** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ee3-243">Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="c9ee3-244">Ezt a címksorozatot a címke elrendezésére lehet nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="c9ee3-245">Számsorozat-bővítések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-245">Configure number sequence extensions</span></span>

<span data-ttu-id="c9ee3-246">A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="c9ee3-247">Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="c9ee3-248">További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="c9ee3-249">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="c9ee3-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="c9ee3-250">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="c9ee3-251">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-252">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c9ee3-253">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c9ee3-254">Adjon hozzá két értékesítési sort a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="c9ee3-255">1. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-255">Sales order line 1:</span></span>

        - <span data-ttu-id="c9ee3-256">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="c9ee3-257">**Mennyiség:** *9024*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="c9ee3-258">**Egység:** *ea* (9024 ea = 376 Box = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="c9ee3-259">2. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-259">Sales order line 2:</span></span>

        - <span data-ttu-id="c9ee3-260">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="c9ee3-261">**Mennyiség:** *9016*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="c9ee3-262">**Egység:** *ea* (9016 ea = 322 Box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ee3-263">Az itt megadott cikkek és mennyiségek csak példák.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="c9ee3-264">A korábban megadott egységszekvencia-csoportot kell használnia, meg kell határozni a egységátváltást *ea* elemről *Box* elemről *PL* elemre, és rendelkezniük kell készlettel a *62.* raktárban.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="c9ee3-265">További tájékoztatás: [Mértékegység- és készletezési irányelvek](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="c9ee3-266">Jelölje ki az 1. értékesítésirendelés-sort.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-266">Select sales order line 1.</span></span> <span data-ttu-id="c9ee3-267">Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="c9ee3-268">A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="c9ee3-269">Ismételje meg a 4. és 5. lépést a 2. értékesítésirendelési-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="c9ee3-270">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c9ee3-271">A következő események zajlanak le:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-271">The following events occur:</span></span>

    - <span data-ttu-id="c9ee3-272">A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="c9ee3-273">A címke elrendezése a címke formátumának meghatározására szolgál, az eredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="c9ee3-274">A hullámcímkék létrehozása és nyomtatása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="c9ee3-275">A címkék számának meg kell egyeznie a kartondobozok számával (ebben a példában 376 dobozcímke az 1. sorhoz és 322 dobozcímke a 2. sorhoz).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="c9ee3-276">Létrejön egy új fuvarlevél-azonosító a szállítmányok számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="c9ee3-277">Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="c9ee3-278">A következő lapokon megtekintheti és újranyomtathatja a hullámcímkéket.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="c9ee3-279">A Művelet ablaktábla **Szállítmányok** lapjának **Kapcsolódó információk** csoportjában válassza a **Hullámcímkék** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="c9ee3-280">Minden szállítmány \> Szállítmány adatai</span><span class="sxs-lookup"><span data-stu-id="c9ee3-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="c9ee3-281">Minden rakomány \> Rakomány adatai</span><span class="sxs-lookup"><span data-stu-id="c9ee3-281">All loads \> Load details</span></span>
- <span data-ttu-id="c9ee3-282">Minden hullám</span><span class="sxs-lookup"><span data-stu-id="c9ee3-282">All waves</span></span>
- <span data-ttu-id="c9ee3-283">Hullámcímkék</span><span class="sxs-lookup"><span data-stu-id="c9ee3-283">Wave labels</span></span>
- <span data-ttu-id="c9ee3-284">Hullámcímke előzményei</span><span class="sxs-lookup"><span data-stu-id="c9ee3-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="c9ee3-285">2. eset: Hullámcímke-nyomtatás a tárolóra bontáshoz (hullámcímkerekordok nélkül)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="c9ee3-286">Ez a forgatókönyv lehetővé teszi a hullámcímkék kinyomtatását, amikor a tárolóra bontás használatával automatikusan felosztja a cikkeket a kartondobozokba, ezért nem szükséges a hullámcímkerekord.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="c9ee3-287">Ebben az esetben a tároló azonosítója helyőrzőként működik a SSCC-hez.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="c9ee3-288">Itt találhatók a jelen forgatókönyv és az 1. eset közötti legfontosabb különbségek:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="c9ee3-289">**Hullámcímkesablonok:** Nem kell kiválasztani a hullámcímkék típusát a hullámcímkesablonon, és a címke-összeállítás csoportosítására nem lesz szükség.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="c9ee3-290">Ellenkező esetben a hullámcímke sablonját kell konfigurálni, és a hullámsablonra mutató hivatkozást ugyanúgy kell konfigurálni, mint az 1. forgatókönyvben leírt módon.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="c9ee3-291">Ha meg szeretné akadályozni a hullámcímkék létrehozását, hagyja üresen a hullámcímke típusát.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="c9ee3-292">**Hullámcímke-elrendezések**: a hullámcímkék elrendezési sorait a hullámcímkerekordok helyett a munkasorokhoz konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="c9ee3-293">Konfigurálnia kell a sor beállításait a címkeelrendezéshez a **WHSWorkLine** tábla használatával a **WHSWaveLabel** tábla helyett.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="c9ee3-294">A **sorok oldalanként** beállítás határozza meg, hogy hány sor lesz a szövegtörzsben.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="c9ee3-295">Ez a konfiguráció olyan üzleti esetekhez is használható, amikor több különböző cikket csomagolnak be egy címkézett dobozba vagy egy raklapra, és ezt a csomagolási folyamatot munkalétrehozással (például szállítmány szerint csoportosított munka) lehet definiálni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="c9ee3-296">Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="c9ee3-297">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="c9ee3-297">Make demo data available</span></span>

<span data-ttu-id="c9ee3-298">A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="c9ee3-299">Ellenőrizze, hogy a hullámcímke módszer elérhető-e</span><span class="sxs-lookup"><span data-stu-id="c9ee3-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="c9ee3-300">Előfordulhat, hogy újra kell generálnia a hullámfeldolgozási módszereket, hogy a hullámcímke-nyomtatási módszer elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="c9ee3-301">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="c9ee3-302">Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="c9ee3-303">Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="c9ee3-304">Állítsa be a hullámsablon lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c9ee3-304">Set up a wave template</span></span>

<span data-ttu-id="c9ee3-305">A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonnal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="c9ee3-306">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="c9ee3-307">Válasszon sablont, például a **63 Tárolóra bontás** sablont.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="c9ee3-308">A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="c9ee3-309">A **kiválasztott metódusok** oszlopban válassza ki a **hullámcímke nyomtatás** módját, és állítsa be a **Hullámlépéskód** mező értékét *PrintLabel* értékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="c9ee3-310">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="c9ee3-311">Hullámcímke elrendezésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-311">Create a wave label layout</span></span>

1. <span data-ttu-id="c9ee3-312">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="c9ee3-313">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-314">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-315">**Leírás:** *Kartondoboz (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="c9ee3-316">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-317">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c9ee3-318">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c9ee3-319">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c9ee3-320">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-321">**Sorazonosító:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="c9ee3-322">**Sor táblaneve:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="c9ee3-323">**Sor kezdő pozíciója:** *500*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="c9ee3-324">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c9ee3-325">**Sormagasság** *-50*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="c9ee3-326">Ez a mező határozza meg az egyes sorok magasságát.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-326">This field defines the height of each row.</span></span> <span data-ttu-id="c9ee3-327">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="c9ee3-328">**Sorok száma oldalanként** *5*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="c9ee3-329">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c9ee3-330">Ez a beállítás számos ZPL címkét fog nyomtatni munkánként, ahol mindegyik lap legfeljebb öt munkasorral rendelkezhet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="c9ee3-331">Ha például egy 12 soros tárolóhoz nyomtat egy címkét, akkor három címkét nyomtat.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="c9ee3-332">Ha minden egyes kitárolási sorhoz külön címkét szeretne nyomtatni, akkor ezt az értéket *1*-re kell állítania.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="c9ee3-333">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-333">Close the page.</span></span>
1. <span data-ttu-id="c9ee3-334">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c9ee3-335">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-336">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-337">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-338">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c9ee3-339">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="c9ee3-340">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="c9ee3-341">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c9ee3-342">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c9ee3-343">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c9ee3-344">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="c9ee3-345">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c9ee3-346">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-346">Here is an example.</span></span>

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="c9ee3-347">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c9ee3-348">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ee3-349">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="c9ee3-350">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c9ee3-351">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="c9ee3-352">A címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="c9ee3-353">Hullámcímkesablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-353">Create a wave label template</span></span>

1. <span data-ttu-id="c9ee3-354">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="c9ee3-355">Adjon hozzá egy hullámcímkesablont, és állítsa be a következő értékeket a fejlécben:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="c9ee3-356">**Címkesablon neve:** *Tárolócímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="c9ee3-357">**Leírás:** *Tárolócímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="c9ee3-358">**Hullámlépés kódja:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="c9ee3-359">**Raktár:** *63*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="c9ee3-360">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-361">**Címkeelrendezés azonosítója:** *Tároló*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="c9ee3-362">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c9ee3-363">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c9ee3-364">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-365">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c9ee3-366">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c9ee3-367">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-368">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-369">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-370">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c9ee3-371">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c9ee3-372">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="c9ee3-373">Számsorozat-bővítések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-373">Configure number sequence extensions</span></span>

<span data-ttu-id="c9ee3-374">A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="c9ee3-375">Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="c9ee3-376">További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="c9ee3-377">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="c9ee3-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="c9ee3-378">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="c9ee3-379">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-380">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c9ee3-381">**Raktár:** *63*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="c9ee3-382">Adjon hozzá 5 értékesítésirendelési-sort:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="c9ee3-383">1. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-383">Sales order line 1:</span></span>

        - <span data-ttu-id="c9ee3-384">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="c9ee3-385">**Mennyiség:** *10*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="c9ee3-386">2. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-386">Sales order line 2:</span></span>

        - <span data-ttu-id="c9ee3-387">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="c9ee3-388">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="c9ee3-389">3. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-389">Sales order line 3:</span></span>

        - <span data-ttu-id="c9ee3-390">**Cikkszám:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="c9ee3-391">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="c9ee3-392">4. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-392">Sales order line 4:</span></span>

        - <span data-ttu-id="c9ee3-393">**Cikkszám:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="c9ee3-394">**Mennyiség:** *40*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="c9ee3-395">5. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-395">Sales order line 5:</span></span>

        - <span data-ttu-id="c9ee3-396">**Cikkszám:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="c9ee3-397">**Mennyiség:** *50*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ee3-398">Az itt megadott cikkek és mennyiségek csak példák.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="c9ee3-399">A megadott raktárban készlettel kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="c9ee3-400">Jelölje ki az 1. értékesítésirendelés-sort.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-400">Select sales order line 1.</span></span> <span data-ttu-id="c9ee3-401">Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="c9ee3-402">A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="c9ee3-403">Ismételje meg a 4. és 5. lépést minden egyes értékesítésirendelési-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="c9ee3-404">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c9ee3-405">A következő események zajlanak le:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-405">The following events occur:</span></span>

    - <span data-ttu-id="c9ee3-406">A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="c9ee3-407">A címke elrendezése a címke formátumának meghatározására szolgál, a végeredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz, amely 5 sorral rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="c9ee3-408">Létrejön egy új fuvarlevél-azonosító a szállítmányok számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="c9ee3-409">Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="c9ee3-410">A hullámcímkék újranyomtathatók a **Raktárkezelés \> lekérdezések és a jelentések \> hullámcímkék előzményei** pontban.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="c9ee3-411">3. forgatókönyv: Többszintű címkék hullámcímke-nyomtatása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="c9ee3-412">Ez a példa azt mutatja be, hogyan kell használni a hullámcímkék nyomtatási funkcióit, amikor a raktározási folyamatokban a szállítási címkék több szintje szükséges.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="c9ee3-413">Például külön címkéket kell nyomtatni a kartondobozok és raklapok számára, és előfordulhat, hogy egy teljes szállítmányhoz ki kell nyomtatni egy szünetcímkét.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="c9ee3-414">A szünetcímkék külön típusú címkék, amelyek a tekercsek és a tárolók közti elválasztóként használhatók, például a szállítmány azonosítója és a vonalkód között, így a címkék nyomtatás után egyszerűen rendezhetők.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="c9ee3-415">A jelen forgatókönyv konfiguráció és az 1. eset konfigurációja közti legfontosabb különbség, a szünetcímkék engedélyezésén kívül, hogy több hullámcímketípust kell társítani a hullámcímkesablonokhoz és az egységszekvencia-csoportsorokhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="c9ee3-416">Ennek a konfigurációnak a végrehajtásához a következő elemeket kell beállítania erre az esetre:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="c9ee3-417">**A hullámfeldolgozási módok:** "ismételhető" módszerként jelöli meg a hullámcímkét, és adja hozzá két (vagy több) alkalommal a hullámsablonhoz, és adjon meg különböző hullámlépéskódokat.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="c9ee3-418">**Hullámcímkesablonok:** Beállítja a hullámcímkesablonokat, és csatolja őket a hullámsablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="c9ee3-419">Minden hullámcímke sablonjának saját hullámcímketípusának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="c9ee3-420">**Hullámcímke-elrendezések:** Több hullámcímke-elrendezést fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="c9ee3-421">A címkék mindegyik "rétegét" külön címkeelrendezéssel kell ellátni, és a program egy szünetcímke elrendezést is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="c9ee3-422">Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="c9ee3-423">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="c9ee3-423">Make demo data available</span></span>

<span data-ttu-id="c9ee3-424">A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="c9ee3-425">Hullámfeldolgozási mód beállítása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-425">Set up a wave process method</span></span>

1. <span data-ttu-id="c9ee3-426">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="c9ee3-427">Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="c9ee3-428">Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="c9ee3-429">A **waveLabelPrinting** módszernél jelölje be a **metódus ismétlődővé tétele** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="c9ee3-430">Állítsa be a hullámsablon lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c9ee3-430">Set up a wave template</span></span>

1. <span data-ttu-id="c9ee3-431">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="c9ee3-432">Válasszon sablont, például a **62 Szállítási alapértelmezés** sablont.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="c9ee3-433">A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="c9ee3-434">A **kiválasztott metódusok** oszlopában állítsa be a **hullámlépés kódja** értékét (például *kartondoboz*) a **Hullámcímke-nyomtatás** módhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="c9ee3-435">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="c9ee3-436">Ismét helyezze át a **Hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="c9ee3-437">A **kiválasztott metódusok** oszlopában állítson be eltérő **hullámlépés kódja** értékét (például *raklap*) a második **Hullámcímke-nyomtatás** módhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="c9ee3-438">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="c9ee3-439">Három hullámcímke-elrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="c9ee3-440">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="c9ee3-441">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-442">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-443">**Leírás:** *Kartondoboz (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="c9ee3-444">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-445">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c9ee3-446">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c9ee3-447">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c9ee3-448">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-449">**Sorazonosító:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="c9ee3-450">**Sor táblaneve:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="c9ee3-451">**Sor kezdő pozíciója:** *0*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="c9ee3-452">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c9ee3-453">**Sormagasság** *0*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-453">**Row height:** *0*</span></span>

        <span data-ttu-id="c9ee3-454">Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="c9ee3-455">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="c9ee3-456">Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="c9ee3-457">**Sorok száma oldalanként** *1*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="c9ee3-458">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c9ee3-459">Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="c9ee3-460">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-460">Close the page.</span></span>
1. <span data-ttu-id="c9ee3-461">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c9ee3-462">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-463">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-464">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-465">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c9ee3-466">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="c9ee3-467">Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="c9ee3-468">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="c9ee3-469">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c9ee3-470">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c9ee3-471">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c9ee3-472">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="c9ee3-473">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c9ee3-474">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-474">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="c9ee3-475">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c9ee3-476">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ee3-477">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="c9ee3-478">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c9ee3-479">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="c9ee3-480">Az első címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="c9ee3-481">Hozzon létre egy második elrendezésrekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-482">**Címkeelrendezés azonosítója:** *Raklap*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="c9ee3-483">**Leírás:** *raklap*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="c9ee3-484">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-485">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c9ee3-486">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c9ee3-487">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c9ee3-488">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-489">**Sorazonosító:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="c9ee3-490">**Sor táblaneve:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="c9ee3-491">**Sor kezdő pozíciója:** *0*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="c9ee3-492">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c9ee3-493">**Sormagasság** *0*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-493">**Row height:** *0*</span></span>

        <span data-ttu-id="c9ee3-494">Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="c9ee3-495">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="c9ee3-496">Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="c9ee3-497">**Sorok száma oldalanként** *1*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="c9ee3-498">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c9ee3-499">Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="c9ee3-500">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-500">Close the page.</span></span>
1. <span data-ttu-id="c9ee3-501">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c9ee3-502">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-503">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-504">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-505">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c9ee3-506">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="c9ee3-507">Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="c9ee3-508">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="c9ee3-509">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c9ee3-510">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c9ee3-511">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c9ee3-512">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="c9ee3-513">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c9ee3-514">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="c9ee3-515">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c9ee3-516">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c9ee3-517">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="c9ee3-518">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c9ee3-519">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="c9ee3-520">A második címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="c9ee3-521">Hozzon létre egy harmadik elrendezésrekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-522">**Címkeelrendezés azonosítója:** *Szünet*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="c9ee3-523">**Leírás:** *Szünetcímke*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="c9ee3-524">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-525">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c9ee3-526">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc ZPL-kódját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="c9ee3-527">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="c9ee3-528">Ez alkalommal nem kell megadni szövegtörzset.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-528">This time, no body is required.</span></span> <span data-ttu-id="c9ee3-529">Ezért csak írja be a szükséges szöveget az **Lábléc szakasz** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="c9ee3-530">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="c9ee3-531">A harmadik címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ee3-532">Ez a harmadik címke egy szünetcímke, amely elválasztóként fog szerepelni a címketekercsek között.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="c9ee3-533">Két hullámcímke típus létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-533">Create two wave label types</span></span>

1. <span data-ttu-id="c9ee3-534">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímketípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="c9ee3-535">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-536">**Címke típusa:** *kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-537">**Leírás:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="c9ee3-538">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-539">**Címke típusa:** *raklap*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="c9ee3-540">**Leírás:** *raklap*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="c9ee3-541">Egységszekvencia-csoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="c9ee3-542">Lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Egységszekvencia-csoportok** részre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="c9ee3-543">Válassza ki vagy hozzon létre egy **Ea Box PL** csoportot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="c9ee3-544">A **Doboz** sorban állítsa a **Hullámcímketípus** mezőt *Kartondoboz* értékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="c9ee3-545">A **PL** sorban állítsa a **Hullámcímketípus** mezőt *Raklap* értékre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="c9ee3-546">Hullámcímkesablonok létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-546">Create wave label templates</span></span>

1. <span data-ttu-id="c9ee3-547">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="c9ee3-548">Hozzon létre egy címkesablont, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-549">**Címkesablon neve:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="c9ee3-550">**Leírás:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="c9ee3-551">**Hullámlépés kódja:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-552">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c9ee3-553">Az **Általános** gyorslapon a **Hullámcímketípus** mezőben válasszon egy értéket, pl. az *Kartondoboz* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="c9ee3-554">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-555">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c9ee3-556">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c9ee3-557">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c9ee3-558">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-559">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c9ee3-560">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c9ee3-561">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-562">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-563">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-564">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c9ee3-565">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c9ee3-566">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="c9ee3-567">A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="c9ee3-568">A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-569">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-570">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-571">**Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="c9ee3-572">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c9ee3-573">Adjon hozzá egy második sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-574">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-575">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-576">**Mező:** *Szállítmány azonosítója*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="c9ee3-577">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c9ee3-578">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="c9ee3-579">Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="c9ee3-580">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="c9ee3-581">A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="c9ee3-582">A **Hullámcímkesablon-csoport** párbeszédpanel azon sorához, ahol a **hivatkozási mező neve** mező a *szállítmányazonosító* értékre van állítva, adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="c9ee3-583">**Szünet címkéjének nyomtatása:** jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="c9ee3-584">**Címke elrendezésének azonosítója:** Jelöljön ki egy szünetcímkét.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="c9ee3-585">(Például válassza ki az ebben a helyzetben korábban létrehozott *Szünet* címkeelrendezést.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="c9ee3-586">**Nyomtató neve:** Válassza ki a szünet címkéjének nyomtatóját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="c9ee3-587">(A címkék felosztásának céljából általában ugyanaz a nyomtató van kiválasztva, mint a **hullámcímkesablon részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="c9ee3-588">Más forgatókönyvek azonban lehetségesek.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="c9ee3-589">Abban a sorban, ahol a **hivatkozási mező neve** mező a *hivatkozási rakománysor azonosítójára* van állítva , jelölje be a **címke-összeállítás azonosítója** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ee3-590">Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="c9ee3-591">Ezt a címksorozatot a címke elrendezésére lehet nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="c9ee3-592">Ezenkívül a különböző szállítmányok címkéit a kiválasztott szünetcímke elválasztja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="c9ee3-593">Az **OK** gombra kattintva zárja be a **Hullámcímkesablon csoportja** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="c9ee3-594">Hozzon létre egy második címkesablont, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-595">**Címkesablon neve:** *Raklapcímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="c9ee3-596">**Leírás:** *raklapcímkék*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="c9ee3-597">**Hullámlépés kódja:** *Raklap*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="c9ee3-598">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c9ee3-599">Az **Általános** gyorslapon a **Hullámcímketípus** mezőben válasszon egy értéket, pl. az *Raklap* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="c9ee3-600">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-601">**Címkeelrendezés azonosítója:** *Raklap*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="c9ee3-602">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c9ee3-603">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c9ee3-604">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c9ee3-605">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c9ee3-606">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c9ee3-607">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-608">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-609">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c9ee3-610">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c9ee3-611">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c9ee3-612">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="c9ee3-613">A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="c9ee3-614">A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-615">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-616">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-617">**Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="c9ee3-618">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c9ee3-619">Adjon hozzá egy második sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-620">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-621">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c9ee3-622">**Mező:** *Szállítmány azonosítója*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="c9ee3-623">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c9ee3-624">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="c9ee3-625">Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="c9ee3-626">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="c9ee3-627">A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="c9ee3-628">A **Hullámcímkesablon-csoport** párbeszédpanel azon sorához, ahol a **hivatkozási mező neve** mező a *szállítmányazonosító* értékre van állítva, adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="c9ee3-629">**Szünet címkéjének nyomtatása:** jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="c9ee3-630">**Címke elrendezésének azonosítója:** Jelöljön ki egy szünetcímkét.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="c9ee3-631">(Például válassza ki az ebben a helyzetben korábban létrehozott *Szünet* címkeelrendezést.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="c9ee3-632">**Nyomtató neve:** Válassza ki a szünet címkéjének nyomtatóját.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="c9ee3-633">(A címkék felosztásának céljából általában ugyanaz a nyomtató van kiválasztva, mint a **hullámcímkesablon részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="c9ee3-634">Más forgatókönyvek azonban lehetségesek.)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="c9ee3-635">Abban a sorban, ahol a **hivatkozási mező neve** mező a *hivatkozási rakománysor azonosítójára* van állítva , jelölje be a **címke-összeállítás azonosítója** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ee3-636">Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="c9ee3-637">Ezt a címksorozatot a címke elrendezésére lehet nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="c9ee3-638">Ezenkívül a különböző szállítmányok címkéit a kiválasztott szünetcímke elválasztja.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="c9ee3-639">Számsorozat-bővítések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c9ee3-639">Configure number sequence extensions</span></span>

<span data-ttu-id="c9ee3-640">A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="c9ee3-641">Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="c9ee3-642">További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="c9ee3-643">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="c9ee3-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="c9ee3-644">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="c9ee3-645">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c9ee3-646">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c9ee3-647">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c9ee3-648">Adjon hozzá 2 értékesítésirendelési-sort:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="c9ee3-649">1. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-649">Sales order line 1:</span></span>

        - <span data-ttu-id="c9ee3-650">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="c9ee3-651">**Mennyiség:** *9024*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="c9ee3-652">**Egység:** *ea* (9024 ea = 376 Box = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="c9ee3-653">2. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-653">Sales order line 2:</span></span>

        - <span data-ttu-id="c9ee3-654">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="c9ee3-655">**Mennyiség:** *9016*</span><span class="sxs-lookup"><span data-stu-id="c9ee3-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="c9ee3-656">**Egység:** *ea* (9016 ea = 322 Box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="c9ee3-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9ee3-657">Az itt megadott cikkek és mennyiségek csak példák.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="c9ee3-658">A korábban megadott egységszekvencia-csoportot kell használnia, meg kell határozni a egységátváltást *ea* elemről *Box* elemről *PL* elemre, és rendelkezniük kell készlettel a *62.* raktárban.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="c9ee3-659">További tájékoztatás: [Mértékegység- és készletezési irányelvek](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="c9ee3-660">Jelölje ki az 1. értékesítésirendelés-sort.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-660">Select sales order line 1.</span></span> <span data-ttu-id="c9ee3-661">Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="c9ee3-662">A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="c9ee3-663">Ismételje meg a 4. és 5. lépést a 2. értékesítésirendelési-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="c9ee3-664">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c9ee3-665">A következő események zajlanak le:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-665">The following events occur:</span></span> 

    - <span data-ttu-id="c9ee3-666">A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="c9ee3-667">A címke elrendezése a címke formátumának meghatározására szolgál, az eredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="c9ee3-668">A hullámcímkék létrehozása és nyomtatása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="c9ee3-669">A címkék számának meg kell egyeznie a kartondobozok számával (ebben a példában 376 dobozcímke az 1. sorhoz, 322 dobozcímke a 2. sorhoz, 47 raklapcímke a 2. sorhoz és két szünetcímke, amely a szállítmány azonosítójával rendelkezik).</span><span class="sxs-lookup"><span data-stu-id="c9ee3-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="c9ee3-670">Létrejön egy új fuvarlevél-azonosító a szállítmányok számára.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="c9ee3-671">Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="c9ee3-672">A következő lapokon megtekintheti és újranyomtathatja a hullámcímkéket:</span><span class="sxs-lookup"><span data-stu-id="c9ee3-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="c9ee3-673">Minden szállítmány \> Szállítmány adatai</span><span class="sxs-lookup"><span data-stu-id="c9ee3-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="c9ee3-674">Minden rakomány \> Rakomány adatai</span><span class="sxs-lookup"><span data-stu-id="c9ee3-674">All loads \> Load details</span></span>
- <span data-ttu-id="c9ee3-675">Minden hullám</span><span class="sxs-lookup"><span data-stu-id="c9ee3-675">All waves</span></span>
- <span data-ttu-id="c9ee3-676">Hullámcímkék</span><span class="sxs-lookup"><span data-stu-id="c9ee3-676">Wave labels</span></span>
- <span data-ttu-id="c9ee3-677">Hullámcímke előzményei</span><span class="sxs-lookup"><span data-stu-id="c9ee3-677">Wave label history</span></span>

<span data-ttu-id="c9ee3-678">A legtöbb ilyen lap esetében a megfelelő függvényt megtalálhatja, ha ki választja a műveleti ablaktábla **Szállítmányok** lapján a **Kapcsolódó információk** csoport **Hullámcímkék** elemét.</span><span class="sxs-lookup"><span data-stu-id="c9ee3-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>
