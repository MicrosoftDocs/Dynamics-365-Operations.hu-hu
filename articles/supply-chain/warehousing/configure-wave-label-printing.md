---
title: Hullámcímke nyomtatása
description: Ez a témakör bemutatja a hullámcímkék nyomtatását, és elmagyarázza, hogy kell beállítani.
author: perlynne
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 14a32f7fc4608ef8910646f80786a188c46dc89d
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102614"
---
# <a name="wave-label-printing"></a><span data-ttu-id="c09fc-103">Hullámcímke nyomtatása</span><span class="sxs-lookup"><span data-stu-id="c09fc-103">Wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c09fc-104">A hullámcímke nyomtatás alternatív megközelítést tesz lehetővé a címkék nyomtatásához egy új hullám lépés módszer bevezetésével, amellyel a címkék közvetlenül a hullámsablonból is létrehozhatók és kinyomtathatók a hullámvégrehajtás során.</span><span class="sxs-lookup"><span data-stu-id="c09fc-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="c09fc-105">Így a címkék már akkor elérhetők lesznek, mielőtt a dolgozók a munkarendelést futtatják egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="c09fc-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="c09fc-106">A dolgozók ezt követően kitároláskor csatolhatják a szükséges címkéket, ahelyett, hogy a kitárolás után tennék.</span><span class="sxs-lookup"><span data-stu-id="c09fc-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="c09fc-107">A hullámcímkék kinyomtatása Zebra programnyelvet (ZPL meghatározó mező) használ a címkék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c09fc-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="c09fc-108">A címkék elrendezése három szakaszra (fejléc, szövegtörzs és lábléc) van osztva, amelyek lehetővé teszik az ismétlődő struktúrával rendelkező címkék használatát.</span><span class="sxs-lookup"><span data-stu-id="c09fc-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="c09fc-109">A hullámcímkesablon mondja meg a rendszernek, melyik címkeelrendezést használja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="c09fc-110">A felhasználók megadhatják, hogy melyik nyomtató legyen használatban.</span><span class="sxs-lookup"><span data-stu-id="c09fc-110">Users can specify which printer is used.</span></span> <span data-ttu-id="c09fc-111">Szükség szerint egyszerre több nyomtatón is nyomtathatnak címkéket.</span><span class="sxs-lookup"><span data-stu-id="c09fc-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="c09fc-112">A **hullámcímkék előzményei** lap a jelen beállítással létrehozott összes címke rekordját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c09fc-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="c09fc-113">A címkék a munkafejlécek alapján is kinyomtathatók és leválogathatók, ezért szünetcímkék a munkfejlécek alapján is nyomtathatók, valamint nyomtathatók a konténerek tartalmát jelző címkék, esetcímkék és más hasonló címkék is.</span><span class="sxs-lookup"><span data-stu-id="c09fc-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="c09fc-114">Ez a funkció nem helyettesíti a dokumentumátirányításon alapuló meglévő címkenyomtatási funkciókat.</span><span class="sxs-lookup"><span data-stu-id="c09fc-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="c09fc-115">A hullámcímke-nyomtatás a következő fejlesztéseket kínálja:</span><span class="sxs-lookup"><span data-stu-id="c09fc-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="c09fc-116">A címkék nyomtatása egyetlen munkasoron a kartondobozok számának megfelelően, a tárolóra bontás használata nélkül.</span><span class="sxs-lookup"><span data-stu-id="c09fc-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="c09fc-117">(A "kartondoboz" egy egység, amely az egységszekvencia-csoport sorain van megjelölve.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="c09fc-118">Több különböző címkefájl (például kartondoboz és raklapcímke) nyomtatása.</span><span class="sxs-lookup"><span data-stu-id="c09fc-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="c09fc-119">A címkék felsorolásának szerepeltetése (például 1/124, 2/124, ... 124/124), és megadja a felsorolás tartományát (például a munkasort, a rakománysort vagy a szállítmányt).</span><span class="sxs-lookup"><span data-stu-id="c09fc-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="c09fc-120">Fuvarlevél-azonosítók létrehozása és nyomtatása a címkékre a fuvarlevél létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="c09fc-121">Egyedi szállítási tároló sorozatkód (SSCC) létrehozása mindegyik kartondobozhoz, és elhelyezése minden címkén.</span><span class="sxs-lookup"><span data-stu-id="c09fc-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="c09fc-122">GS1-kompatibilis számsorozatok létrehozása a fuvarlevél-azonosítók és a SSCC-k számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="c09fc-123">A címkék újranyomtatása mind a mobil eszközökből, mind a funkciógazdag kliensből.</span><span class="sxs-lookup"><span data-stu-id="c09fc-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="c09fc-124">A címkék érvénytelenítése (például rövid kitárolási helyzetekben), majd újranyomtatása.</span><span class="sxs-lookup"><span data-stu-id="c09fc-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="c09fc-125">Hullámcímke-előzmények törlése.</span><span class="sxs-lookup"><span data-stu-id="c09fc-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="c09fc-126">A dokumentumátirányítási elrendezések javításai megoszlanak a dokumentumátirányítási elrendezések és a hullámcímkék elrendezései között.</span><span class="sxs-lookup"><span data-stu-id="c09fc-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="c09fc-127">(További tájékoztatás: [Azonosítótáblák dokumentumátirányítási elrendezése](../warehousing/document-routing-layout-for-license-plates.md).)</span><span class="sxs-lookup"><span data-stu-id="c09fc-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="c09fc-128">Ezek a javítások hatékonyabbá teszik a kartondobozok raklaposítás előtti címkézését.</span><span class="sxs-lookup"><span data-stu-id="c09fc-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="c09fc-129">Különösen előnyös azoknak a vállalatoknak, amelyek nagy méretű kiskereskedőkhöz szállítanak, akik automatikusan megerősítik a rendelés bevételezését az egyes kartondobozok külön beolvasásával.</span><span class="sxs-lookup"><span data-stu-id="c09fc-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="c09fc-130">Az ebben a témakörben leírt konfigurációs forgatókönyveket akár külön, akár együttesen is végre lehet hajtani az üzleti igényektől függően.</span><span class="sxs-lookup"><span data-stu-id="c09fc-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="c09fc-131">A különböző hullámcímke-sablonokat tervezhet, amelyek sorozatban működnek (3. forgatókönyvben látható módon).</span><span class="sxs-lookup"><span data-stu-id="c09fc-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="c09fc-132">Például az 1. forgatókönyvvel kartondobozcímkéket nyomtathat, a 2. forgatókönyvvel raklapcímkéket nyomtathat (ha a raklapok méretben és összetételben változnak).</span><span class="sxs-lookup"><span data-stu-id="c09fc-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="c09fc-133">A Hullámcímke-nyomtatás funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="c09fc-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="c09fc-134">A *Hullámcímke-nyomtatás* funkciót használata előtt be kell kapcsolni a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="c09fc-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="c09fc-135">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="c09fc-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c09fc-136">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="c09fc-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c09fc-137">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="c09fc-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c09fc-138">**Funkció neve:** *Hullámcímke-nyomtatás*</span><span class="sxs-lookup"><span data-stu-id="c09fc-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="c09fc-139">1. eset: Hullámcímke-nyomtatás, amelyben egyetlen hullámcímke jön létre</span><span class="sxs-lookup"><span data-stu-id="c09fc-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="c09fc-140">Ez a példa azt mutatja be, hogyan nyomtathat levélcímkéket egy nagyméretű kiskereskedő számára, amely automatikusan visszaigazolja a rendelések bevételezését a kartondobozok külön beolvasásával.</span><span class="sxs-lookup"><span data-stu-id="c09fc-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="c09fc-141">Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c09fc-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="c09fc-142">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="c09fc-142">Make demo data available</span></span>

<span data-ttu-id="c09fc-143">A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="c09fc-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="c09fc-144">Ellenőrizze, hogy a hullámcímke módszer elérhető-e</span><span class="sxs-lookup"><span data-stu-id="c09fc-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="c09fc-145">Előfordulhat, hogy újra kell generálnia a hullámfeldolgozási módszereket, hogy a hullámcímke-nyomtatási módszer elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="c09fc-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="c09fc-146">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="c09fc-147">Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="c09fc-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="c09fc-148">Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="c09fc-149">Hullámsablon konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c09fc-149">Configure a wave template</span></span>

<span data-ttu-id="c09fc-150">A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonnal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="c09fc-151">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="c09fc-152">Válasszon sablont, például a **62 Szállítási alapértelmezés** sablont.</span><span class="sxs-lookup"><span data-stu-id="c09fc-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="c09fc-153">A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c09fc-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="c09fc-154">A **kiválasztott metódusok** oszlopban válassza ki a **hullámcímke nyomtatás** módját, és állítsa be a **Hullámlépéskód** mező értékét *PrintLabel* értékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="c09fc-155">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="c09fc-156">Hullámcímke elrendezésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-156">Create a wave label layout</span></span>

<span data-ttu-id="c09fc-157">A címke elrendezése határozza meg, hogy milyen adatok jelennek meg a címkén, és milyen módon kell elrendezni. Itt megadhatja a nyomtatónak küldött ZPL kódot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="c09fc-158">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="c09fc-159">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-160">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-161">**Leírás:** *Kartondoboz (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="c09fc-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="c09fc-162">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-163">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c09fc-164">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c09fc-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c09fc-165">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c09fc-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c09fc-166">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-167">**Sorazonosító:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="c09fc-168">**Sor táblaneve:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="c09fc-169">**Sor kezdő pozíciója:** *0*</span><span class="sxs-lookup"><span data-stu-id="c09fc-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="c09fc-170">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c09fc-171">**Sormagasság** *0*</span><span class="sxs-lookup"><span data-stu-id="c09fc-171">**Row height:** *0*</span></span>

        <span data-ttu-id="c09fc-172">Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint.</span><span class="sxs-lookup"><span data-stu-id="c09fc-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="c09fc-173">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c09fc-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="c09fc-174">Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="c09fc-175">**Sorok száma oldalanként** *1*</span><span class="sxs-lookup"><span data-stu-id="c09fc-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="c09fc-176">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c09fc-177">Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="c09fc-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-178">Close the page.</span></span>
1. <span data-ttu-id="c09fc-179">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c09fc-180">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-181">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-182">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-183">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c09fc-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c09fc-184">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c09fc-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="c09fc-185">Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.</span><span class="sxs-lookup"><span data-stu-id="c09fc-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="c09fc-186">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c09fc-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="c09fc-187">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c09fc-188">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c09fc-189">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c09fc-190">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

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

1. <span data-ttu-id="c09fc-191">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c09fc-192">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-192">Here is an example.</span></span>

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

1. <span data-ttu-id="c09fc-193">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c09fc-194">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c09fc-195">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c09fc-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="c09fc-196">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c09fc-197">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="c09fc-198">A címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="c09fc-199">Hullámcímke típusának létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-199">Create a wave label type</span></span>

<span data-ttu-id="c09fc-200">A hullámcímkék típusaival a hullámcímkesablonok egy egységhez kapcsolhatók egy egységszekvencia-csoport soraiban.</span><span class="sxs-lookup"><span data-stu-id="c09fc-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="c09fc-201">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímketípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="c09fc-202">Adjon hozzá egy hullámcímketípust, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-203">**Címke típusa:** *kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-204">**Leírás:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="c09fc-205">Egységszekvencia-csoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="c09fc-205">Set up unit sequence groups</span></span>

<span data-ttu-id="c09fc-206">Ezután állítsa be a hullámcímke típusának egységszekvencia-csoportját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="c09fc-207">Lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Egységszekvencia-csoportok** részre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="c09fc-208">Válassza az **Ea Box PL** csoportot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="c09fc-209">A **Doboz** sorban állítsa a **Hullámcímketípus** mezőt *Kartondoboz* értékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="c09fc-210">Hullámcímkesablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-210">Create a wave label template</span></span>

<span data-ttu-id="c09fc-211">Ezután hozza létre a hullámcímke sablonját a hullámcímkék típusához.</span><span class="sxs-lookup"><span data-stu-id="c09fc-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="c09fc-212">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="c09fc-213">Adjon hozzá egy hullámcímkesablont, és állítsa be a következő értékeket a fejlécben:</span><span class="sxs-lookup"><span data-stu-id="c09fc-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="c09fc-214">**Címkesablon neve:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="c09fc-215">**Leírás:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="c09fc-216">**Hullámlépés kódja:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="c09fc-217">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c09fc-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c09fc-218">Az **általános** gyorslapon adja meg a **hullámcímke típusa** mezőt *kartondoboz* értékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="c09fc-219">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy új sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c09fc-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-220">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-221">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c09fc-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c09fc-222">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c09fc-223">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-224">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c09fc-225">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c09fc-226">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-227">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-228">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-229">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c09fc-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c09fc-230">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c09fc-231">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="c09fc-232">A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="c09fc-233">A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-234">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-235">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-236">**Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*</span><span class="sxs-lookup"><span data-stu-id="c09fc-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="c09fc-237">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c09fc-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c09fc-238">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="c09fc-239">Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri.</span><span class="sxs-lookup"><span data-stu-id="c09fc-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="c09fc-240">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="c09fc-241">A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="c09fc-242">A **Hullámcímkesablon-csoport** párbeszédablakban válassza ki azt a sort, amelynek **Hivatkozási mező neve** mezője *Hivatkozási rakománysor-azonosító* értékre van állítva, majd jelölje be a sorhoz tartozó **Címke-összeállítási azonosító** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c09fc-243">Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="c09fc-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="c09fc-244">Ezt a címksorozatot a címke elrendezésére lehet nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="c09fc-245">Számsorozat-bővítések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c09fc-245">Configure number sequence extensions</span></span>

<span data-ttu-id="c09fc-246">A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="c09fc-247">Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében.</span><span class="sxs-lookup"><span data-stu-id="c09fc-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="c09fc-248">További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="c09fc-249">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="c09fc-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="c09fc-250">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="c09fc-251">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-252">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c09fc-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c09fc-253">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c09fc-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c09fc-254">Adjon hozzá két értékesítési sort a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="c09fc-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="c09fc-255">1. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-255">Sales order line 1:</span></span>

        - <span data-ttu-id="c09fc-256">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c09fc-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="c09fc-257">**Mennyiség:** *9024*</span><span class="sxs-lookup"><span data-stu-id="c09fc-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="c09fc-258">**Egység:** *ea* (9024 ea = 376 Box = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="c09fc-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="c09fc-259">2. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-259">Sales order line 2:</span></span>

        - <span data-ttu-id="c09fc-260">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="c09fc-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="c09fc-261">**Mennyiség:** *9016*</span><span class="sxs-lookup"><span data-stu-id="c09fc-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="c09fc-262">**Egység:** *ea* (9016 ea = 322 Box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="c09fc-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c09fc-263">Az itt megadott cikkek és mennyiségek csak példák.</span><span class="sxs-lookup"><span data-stu-id="c09fc-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="c09fc-264">A korábban megadott egységszekvencia-csoportot kell használnia, meg kell határozni a egységátváltást *ea* elemről *Box* elemről *PL* elemre, és rendelkezniük kell készlettel a *62.* raktárban.</span><span class="sxs-lookup"><span data-stu-id="c09fc-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="c09fc-265">További tájékoztatás: [Mértékegység- és készletezési irányelvek](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="c09fc-266">Jelölje ki az 1. értékesítésirendelés-sort.</span><span class="sxs-lookup"><span data-stu-id="c09fc-266">Select sales order line 1.</span></span> <span data-ttu-id="c09fc-267">Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="c09fc-268">A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="c09fc-269">Ismételje meg a 4. és 5. lépést a 2. értékesítésirendelési-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="c09fc-270">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c09fc-271">A következő események zajlanak le:</span><span class="sxs-lookup"><span data-stu-id="c09fc-271">The following events occur:</span></span>

    - <span data-ttu-id="c09fc-272">A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával.</span><span class="sxs-lookup"><span data-stu-id="c09fc-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="c09fc-273">A címke elrendezése a címke formátumának meghatározására szolgál, az eredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="c09fc-274">A hullámcímkék létrehozása és nyomtatása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="c09fc-275">A címkék számának meg kell egyeznie a kartondobozok számával (ebben a példában 376 dobozcímke az 1. sorhoz és 322 dobozcímke a 2. sorhoz).</span><span class="sxs-lookup"><span data-stu-id="c09fc-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="c09fc-276">Létrejön egy új fuvarlevél-azonosító a szállítmányok számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="c09fc-277">Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="c09fc-278">A következő lapokon megtekintheti és újranyomtathatja a hullámcímkéket.</span><span class="sxs-lookup"><span data-stu-id="c09fc-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="c09fc-279">A Művelet ablaktábla **Szállítmányok** lapjának **Kapcsolódó információk** csoportjában válassza a **Hullámcímkék** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="c09fc-280">Minden szállítmány \> Szállítmány adatai</span><span class="sxs-lookup"><span data-stu-id="c09fc-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="c09fc-281">Minden rakomány \> Rakomány adatai</span><span class="sxs-lookup"><span data-stu-id="c09fc-281">All loads \> Load details</span></span>
- <span data-ttu-id="c09fc-282">Minden hullám</span><span class="sxs-lookup"><span data-stu-id="c09fc-282">All waves</span></span>
- <span data-ttu-id="c09fc-283">Hullámcímkék</span><span class="sxs-lookup"><span data-stu-id="c09fc-283">Wave labels</span></span>
- <span data-ttu-id="c09fc-284">Hullámcímke előzményei</span><span class="sxs-lookup"><span data-stu-id="c09fc-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="c09fc-285">2. eset: Hullámcímke-nyomtatás a tárolóra bontáshoz (hullámcímkerekordok nélkül)</span><span class="sxs-lookup"><span data-stu-id="c09fc-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="c09fc-286">Ez a forgatókönyv lehetővé teszi a hullámcímkék kinyomtatását, amikor a tárolóra bontás használatával automatikusan felosztja a cikkeket a kartondobozokba, ezért nem szükséges a hullámcímkerekord.</span><span class="sxs-lookup"><span data-stu-id="c09fc-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="c09fc-287">Ebben az esetben a tároló azonosítója helyőrzőként működik a SSCC-hez.</span><span class="sxs-lookup"><span data-stu-id="c09fc-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="c09fc-288">Itt találhatók a jelen forgatókönyv és az 1. eset közötti legfontosabb különbségek:</span><span class="sxs-lookup"><span data-stu-id="c09fc-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="c09fc-289">**Hullámcímkesablonok:** Nem kell kiválasztani a hullámcímkék típusát a hullámcímkesablonon, és a címke-összeállítás csoportosítására nem lesz szükség.</span><span class="sxs-lookup"><span data-stu-id="c09fc-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="c09fc-290">Ellenkező esetben a hullámcímke sablonját kell konfigurálni, és a hullámsablonra mutató hivatkozást ugyanúgy kell konfigurálni, mint az 1. forgatókönyvben leírt módon.</span><span class="sxs-lookup"><span data-stu-id="c09fc-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="c09fc-291">Ha meg szeretné akadályozni a hullámcímkék létrehozását, hagyja üresen a hullámcímke típusát.</span><span class="sxs-lookup"><span data-stu-id="c09fc-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="c09fc-292">**Hullámcímke-elrendezések**: a hullámcímkék elrendezési sorait a hullámcímkerekordok helyett a munkasorokhoz konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="c09fc-293">Konfigurálnia kell a sor beállításait a címkeelrendezéshez a **WHSWorkLine** tábla használatával a **WHSWaveLabel** tábla helyett.</span><span class="sxs-lookup"><span data-stu-id="c09fc-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="c09fc-294">A **sorok oldalanként** beállítás határozza meg, hogy hány sor lesz a szövegtörzsben.</span><span class="sxs-lookup"><span data-stu-id="c09fc-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="c09fc-295">Ez a konfiguráció olyan üzleti esetekhez is használható, amikor több különböző cikket csomagolnak be egy címkézett dobozba vagy egy raklapra, és ezt a csomagolási folyamatot munkalétrehozással (például szállítmány szerint csoportosított munka) lehet definiálni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="c09fc-296">Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c09fc-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="c09fc-297">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="c09fc-297">Make demo data available</span></span>

<span data-ttu-id="c09fc-298">A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="c09fc-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="c09fc-299">Ellenőrizze, hogy a hullámcímke módszer elérhető-e</span><span class="sxs-lookup"><span data-stu-id="c09fc-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="c09fc-300">Előfordulhat, hogy újra kell generálnia a hullámfeldolgozási módszereket, hogy a hullámcímke-nyomtatási módszer elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="c09fc-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="c09fc-301">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="c09fc-302">Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="c09fc-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="c09fc-303">Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="c09fc-304">Állítsa be a hullámsablon lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c09fc-304">Set up a wave template</span></span>

<span data-ttu-id="c09fc-305">A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonnal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="c09fc-306">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="c09fc-307">Válasszon sablont, például a **63 Tárolóra bontás** sablont.</span><span class="sxs-lookup"><span data-stu-id="c09fc-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="c09fc-308">A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c09fc-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="c09fc-309">A **kiválasztott metódusok** oszlopban válassza ki a **hullámcímke nyomtatás** módját, és állítsa be a **Hullámlépéskód** mező értékét *PrintLabel* értékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="c09fc-310">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="c09fc-311">Hullámcímke elrendezésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-311">Create a wave label layout</span></span>

1. <span data-ttu-id="c09fc-312">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="c09fc-313">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-314">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-315">**Leírás:** *Kartondoboz (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="c09fc-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="c09fc-316">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-317">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c09fc-318">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c09fc-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c09fc-319">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c09fc-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c09fc-320">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-321">**Sorazonosító:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="c09fc-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="c09fc-322">**Sor táblaneve:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="c09fc-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="c09fc-323">**Sor kezdő pozíciója:** *500*</span><span class="sxs-lookup"><span data-stu-id="c09fc-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="c09fc-324">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c09fc-325">**Sormagasság** *-50*</span><span class="sxs-lookup"><span data-stu-id="c09fc-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="c09fc-326">Ez a mező határozza meg az egyes sorok magasságát.</span><span class="sxs-lookup"><span data-stu-id="c09fc-326">This field defines the height of each row.</span></span> <span data-ttu-id="c09fc-327">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c09fc-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="c09fc-328">**Sorok száma oldalanként** *5*</span><span class="sxs-lookup"><span data-stu-id="c09fc-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="c09fc-329">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c09fc-330">Ez a beállítás számos ZPL címkét fog nyomtatni munkánként, ahol mindegyik lap legfeljebb öt munkasorral rendelkezhet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="c09fc-331">Ha például egy 12 soros tárolóhoz nyomtat egy címkét, akkor három címkét nyomtat.</span><span class="sxs-lookup"><span data-stu-id="c09fc-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="c09fc-332">Ha minden egyes kitárolási sorhoz külön címkét szeretne nyomtatni, akkor ezt az értéket *1*-re kell állítania.</span><span class="sxs-lookup"><span data-stu-id="c09fc-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="c09fc-333">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-333">Close the page.</span></span>
1. <span data-ttu-id="c09fc-334">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c09fc-335">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-336">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-337">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-338">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c09fc-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c09fc-339">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c09fc-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="c09fc-340">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c09fc-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="c09fc-341">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c09fc-342">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c09fc-343">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c09fc-344">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="c09fc-345">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c09fc-346">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-346">Here is an example.</span></span>

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

1. <span data-ttu-id="c09fc-347">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c09fc-348">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c09fc-349">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c09fc-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="c09fc-350">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c09fc-351">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="c09fc-352">A címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="c09fc-353">Hullámcímkesablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-353">Create a wave label template</span></span>

1. <span data-ttu-id="c09fc-354">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="c09fc-355">Adjon hozzá egy hullámcímkesablont, és állítsa be a következő értékeket a fejlécben:</span><span class="sxs-lookup"><span data-stu-id="c09fc-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="c09fc-356">**Címkesablon neve:** *Tárolócímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="c09fc-357">**Leírás:** *Tárolócímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="c09fc-358">**Hullámlépés kódja:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="c09fc-359">**Raktár:** *63*</span><span class="sxs-lookup"><span data-stu-id="c09fc-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="c09fc-360">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c09fc-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-361">**Címkeelrendezés azonosítója:** *Tároló*</span><span class="sxs-lookup"><span data-stu-id="c09fc-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="c09fc-362">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c09fc-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c09fc-363">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c09fc-364">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-365">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c09fc-366">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c09fc-367">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-368">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-369">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-370">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c09fc-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c09fc-371">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c09fc-372">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="c09fc-373">Számsorozat-bővítések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c09fc-373">Configure number sequence extensions</span></span>

<span data-ttu-id="c09fc-374">A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="c09fc-375">Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében.</span><span class="sxs-lookup"><span data-stu-id="c09fc-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="c09fc-376">További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="c09fc-377">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="c09fc-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="c09fc-378">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="c09fc-379">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-380">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c09fc-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c09fc-381">**Raktár:** *63*</span><span class="sxs-lookup"><span data-stu-id="c09fc-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="c09fc-382">Adjon hozzá 5 értékesítésirendelési-sort:</span><span class="sxs-lookup"><span data-stu-id="c09fc-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="c09fc-383">1. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-383">Sales order line 1:</span></span>

        - <span data-ttu-id="c09fc-384">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c09fc-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="c09fc-385">**Mennyiség:** *10*</span><span class="sxs-lookup"><span data-stu-id="c09fc-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="c09fc-386">2. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-386">Sales order line 2:</span></span>

        - <span data-ttu-id="c09fc-387">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="c09fc-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="c09fc-388">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="c09fc-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="c09fc-389">3. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-389">Sales order line 3:</span></span>

        - <span data-ttu-id="c09fc-390">**Cikkszám:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="c09fc-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="c09fc-391">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="c09fc-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="c09fc-392">4. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-392">Sales order line 4:</span></span>

        - <span data-ttu-id="c09fc-393">**Cikkszám:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="c09fc-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="c09fc-394">**Mennyiség:** *40*</span><span class="sxs-lookup"><span data-stu-id="c09fc-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="c09fc-395">5. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-395">Sales order line 5:</span></span>

        - <span data-ttu-id="c09fc-396">**Cikkszám:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="c09fc-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="c09fc-397">**Mennyiség:** *50*</span><span class="sxs-lookup"><span data-stu-id="c09fc-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="c09fc-398">Az itt megadott cikkek és mennyiségek csak példák.</span><span class="sxs-lookup"><span data-stu-id="c09fc-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="c09fc-399">A megadott raktárban készlettel kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="c09fc-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="c09fc-400">Jelölje ki az 1. értékesítésirendelés-sort.</span><span class="sxs-lookup"><span data-stu-id="c09fc-400">Select sales order line 1.</span></span> <span data-ttu-id="c09fc-401">Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="c09fc-402">A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="c09fc-403">Ismételje meg a 4. és 5. lépést minden egyes értékesítésirendelési-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="c09fc-404">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c09fc-405">A következő események zajlanak le:</span><span class="sxs-lookup"><span data-stu-id="c09fc-405">The following events occur:</span></span>

    - <span data-ttu-id="c09fc-406">A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával.</span><span class="sxs-lookup"><span data-stu-id="c09fc-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="c09fc-407">A címke elrendezése a címke formátumának meghatározására szolgál, a végeredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz, amely 5 sorral rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="c09fc-408">Létrejön egy új fuvarlevél-azonosító a szállítmányok számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="c09fc-409">Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="c09fc-410">A hullámcímkék újranyomtathatók a **Raktárkezelés \> lekérdezések és a jelentések \> hullámcímkék előzményei** pontban.</span><span class="sxs-lookup"><span data-stu-id="c09fc-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="c09fc-411">3. forgatókönyv: Többszintű címkék hullámcímke-nyomtatása</span><span class="sxs-lookup"><span data-stu-id="c09fc-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="c09fc-412">Ez a példa azt mutatja be, hogyan kell használni a hullámcímkék nyomtatási funkcióit, amikor a raktározási folyamatokban a szállítási címkék több szintje szükséges.</span><span class="sxs-lookup"><span data-stu-id="c09fc-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="c09fc-413">Például külön címkéket kell nyomtatni a kartondobozok és raklapok számára, és előfordulhat, hogy egy teljes szállítmányhoz ki kell nyomtatni egy szünetcímkét.</span><span class="sxs-lookup"><span data-stu-id="c09fc-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="c09fc-414">A szünetcímkék külön típusú címkék, amelyek a tekercsek és a tárolók közti elválasztóként használhatók, például a szállítmány azonosítója és a vonalkód között, így a címkék nyomtatás után egyszerűen rendezhetők.</span><span class="sxs-lookup"><span data-stu-id="c09fc-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="c09fc-415">A jelen forgatókönyv konfiguráció és az 1. eset konfigurációja közti legfontosabb különbség, a szünetcímkék engedélyezésén kívül, hogy több hullámcímketípust kell társítani a hullámcímkesablonokhoz és az egységszekvencia-csoportsorokhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="c09fc-416">Ennek a konfigurációnak a végrehajtásához a következő elemeket kell beállítania erre az esetre:</span><span class="sxs-lookup"><span data-stu-id="c09fc-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="c09fc-417">**A hullámfeldolgozási módok:** "ismételhető" módszerként jelöli meg a hullámcímkét, és adja hozzá két (vagy több) alkalommal a hullámsablonhoz, és adjon meg különböző hullámlépéskódokat.</span><span class="sxs-lookup"><span data-stu-id="c09fc-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="c09fc-418">**Hullámcímkesablonok:** Beállítja a hullámcímkesablonokat, és csatolja őket a hullámsablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="c09fc-419">Minden hullámcímke sablonjának saját hullámcímketípusának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c09fc-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="c09fc-420">**Hullámcímke-elrendezések:** Több hullámcímke-elrendezést fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="c09fc-421">A címkék mindegyik "rétegét" külön címkeelrendezéssel kell ellátni, és a program egy szünetcímke elrendezést is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="c09fc-422">Ez a forgatókönyv a végpontok közötti folyamatot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c09fc-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="c09fc-423">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="c09fc-423">Make demo data available</span></span>

<span data-ttu-id="c09fc-424">A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.</span><span class="sxs-lookup"><span data-stu-id="c09fc-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="c09fc-425">Hullámfeldolgozási mód beállítása</span><span class="sxs-lookup"><span data-stu-id="c09fc-425">Set up a wave process method</span></span>

1. <span data-ttu-id="c09fc-426">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="c09fc-427">Győződjön meg róla, hogy a **waveLabelPrinting** szerepel a listán.</span><span class="sxs-lookup"><span data-stu-id="c09fc-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="c09fc-428">Ha nincs, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="c09fc-429">A **waveLabelPrinting** módszernél jelölje be a **metódus ismétlődővé tétele** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="c09fc-430">Állítsa be a hullámsablon lehetőséget</span><span class="sxs-lookup"><span data-stu-id="c09fc-430">Set up a wave template</span></span>

1. <span data-ttu-id="c09fc-431">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="c09fc-432">Válasszon sablont, például a **62 Szállítási alapértelmezés** sablont.</span><span class="sxs-lookup"><span data-stu-id="c09fc-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="c09fc-433">A **metódusok** gyorslapon helyezze át a **hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c09fc-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="c09fc-434">A **kiválasztott metódusok** oszlopában állítsa be a **hullámlépés kódja** értékét (például *kartondoboz*) a **Hullámcímke-nyomtatás** módhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="c09fc-435">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="c09fc-436">Ismét helyezze át a **Hullámcímke-nyomtatás** módszert a **kiválasztott metódusok** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="c09fc-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="c09fc-437">A **kiválasztott metódusok** oszlopában állítson be eltérő **hullámlépés kódja** értékét (például *raklap*) a második **Hullámcímke-nyomtatás** módhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="c09fc-438">További tájékoztatás: [Hullámlépéskódok](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="c09fc-439">Három hullámcímke-elrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="c09fc-440">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímke-elrendezések** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="c09fc-441">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-442">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-443">**Leírás:** *Kartondoboz (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="c09fc-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="c09fc-444">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-445">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c09fc-446">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c09fc-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c09fc-447">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c09fc-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c09fc-448">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-449">**Sorazonosító:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="c09fc-450">**Sor táblaneve:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="c09fc-451">**Sor kezdő pozíciója:** *0*</span><span class="sxs-lookup"><span data-stu-id="c09fc-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="c09fc-452">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c09fc-453">**Sormagasság** *0*</span><span class="sxs-lookup"><span data-stu-id="c09fc-453">**Row height:** *0*</span></span>

        <span data-ttu-id="c09fc-454">Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint.</span><span class="sxs-lookup"><span data-stu-id="c09fc-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="c09fc-455">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c09fc-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="c09fc-456">Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="c09fc-457">**Sorok száma oldalanként** *1*</span><span class="sxs-lookup"><span data-stu-id="c09fc-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="c09fc-458">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c09fc-459">Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="c09fc-460">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-460">Close the page.</span></span>
1. <span data-ttu-id="c09fc-461">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c09fc-462">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-463">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-464">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-465">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c09fc-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c09fc-466">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c09fc-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="c09fc-467">Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.</span><span class="sxs-lookup"><span data-stu-id="c09fc-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="c09fc-468">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c09fc-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="c09fc-469">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c09fc-470">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c09fc-471">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c09fc-472">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


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

1. <span data-ttu-id="c09fc-473">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c09fc-474">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-474">Here is an example.</span></span>

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

1. <span data-ttu-id="c09fc-475">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c09fc-476">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c09fc-477">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c09fc-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="c09fc-478">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c09fc-479">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="c09fc-480">Az első címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="c09fc-481">Hozzon létre egy második elrendezésrekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-482">**Címkeelrendezés azonosítója:** *Raklap*</span><span class="sxs-lookup"><span data-stu-id="c09fc-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="c09fc-483">**Leírás:** *raklap*</span><span class="sxs-lookup"><span data-stu-id="c09fc-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="c09fc-484">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-485">A műveleti panelen válassza a **hullámcímkék sorbeállításai** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="c09fc-486">Megjelenik a **Hullámcímke sorbeállításai** lap.</span><span class="sxs-lookup"><span data-stu-id="c09fc-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="c09fc-487">Itt beállítható a címke dinamikus része.</span><span class="sxs-lookup"><span data-stu-id="c09fc-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="c09fc-488">Adjon hozzá egy sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-489">**Sorazonosító:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="c09fc-490">**Sor táblaneve:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="c09fc-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="c09fc-491">**Sor kezdő pozíciója:** *0*</span><span class="sxs-lookup"><span data-stu-id="c09fc-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="c09fc-492">Ez a mező azt a függőleges pozíciót határozza meg, ahol a sor a címkén kezdődik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="c09fc-493">**Sormagasság** *0*</span><span class="sxs-lookup"><span data-stu-id="c09fc-493">**Row height:** *0*</span></span>

        <span data-ttu-id="c09fc-494">Ez a mező határozza meg az egyes sorok magasságát (pontban) a ZPL szabvány szerint.</span><span class="sxs-lookup"><span data-stu-id="c09fc-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="c09fc-495">A sormagasság pozitív a vízszintes címkéknél, és negatív a függőleges címkéknél.</span><span class="sxs-lookup"><span data-stu-id="c09fc-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="c09fc-496">Mivel ebben a példában csak egy sor van, az értéket *0* (nulla) értékre lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="c09fc-497">**Sorok száma oldalanként** *1*</span><span class="sxs-lookup"><span data-stu-id="c09fc-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="c09fc-498">Ez a mező határozza meg, hogy hány sort lehet nyomtatni az egyes címkékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="c09fc-499">Ez a beállítás külön ZPL címkét fog okozni a hullámcímkék táblában szereplő mindegyik rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="c09fc-500">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-500">Close the page.</span></span>
1. <span data-ttu-id="c09fc-501">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c09fc-502">A lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-503">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-504">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-505">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="c09fc-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="c09fc-506">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c09fc-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="c09fc-507">Ez a lekérdezés gondoskodik arról, hogy csak a kitárolás típusú munkasorok legyenek kinyomtatva a címkére, és ne legyenek betárolás típusú munkasorok.</span><span class="sxs-lookup"><span data-stu-id="c09fc-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="c09fc-508">Ha azt szeretné, hogy a fuvarlevél-azonosító kinyomtatása megtörténjen, az **illesztések** lapon válassza ki a **munkasorok** táblát, majd a **szállítmányok** tábláját illessze hozzá.</span><span class="sxs-lookup"><span data-stu-id="c09fc-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="c09fc-509">Zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="c09fc-510">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c09fc-511">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="c09fc-512">Ha például Zebra nyomtatókat használ, a következő kódot használhatja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="c09fc-513">A **Szövegtörzs szakasz** szakaszban a **Címke szövegtörzse** mezőben adja meg a kívánt szövegtörzs ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="c09fc-514">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="c09fc-515">A **Szövegtörzs szakasz** szakaszban a **Címke lábléce** mezőben adja meg a kívánt lábléc ZPL kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="c09fc-516">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="c09fc-517">Ez a beállítás kinyomtatja az egyes címkék egy példányát.</span><span class="sxs-lookup"><span data-stu-id="c09fc-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="c09fc-518">Ha több példányra van szükség (például egy példány a raklap mindkét oldalára), akkor állítsa be a lábléc **\^PQn** szakaszának **n** értékét a példányok szükséges számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="c09fc-519">Ha például az egyes címkékből négy másolatot szeretne nyomtatni, adja meg: **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="c09fc-520">A második címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="c09fc-521">Hozzon létre egy harmadik elrendezésrekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-522">**Címkeelrendezés azonosítója:** *Szünet*</span><span class="sxs-lookup"><span data-stu-id="c09fc-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="c09fc-523">**Leírás:** *Szünetcímke*</span><span class="sxs-lookup"><span data-stu-id="c09fc-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="c09fc-524">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-525">A **nyomtató szövegének elrendezése** gyorslap három szakaszból áll, ahol megadhatja a nyomtató kódját: **fejléc szakasz** , **szövegtörzs** és **lábléc szakasz**.</span><span class="sxs-lookup"><span data-stu-id="c09fc-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="c09fc-526">A **Fejléc szakasz** szakaszban a **Címkefejléc** mezőben adja meg a kívánt fejléc ZPL-kódját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="c09fc-527">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="c09fc-528">Ez alkalommal nem kell megadni szövegtörzset.</span><span class="sxs-lookup"><span data-stu-id="c09fc-528">This time, no body is required.</span></span> <span data-ttu-id="c09fc-529">Ezért csak írja be a szükséges szöveget az **Lábléc szakasz** szakaszba.</span><span class="sxs-lookup"><span data-stu-id="c09fc-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="c09fc-530">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="c09fc-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="c09fc-531">A harmadik címke készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c09fc-532">Ez a harmadik címke egy szünetcímke, amely elválasztóként fog szerepelni a címketekercsek között.</span><span class="sxs-lookup"><span data-stu-id="c09fc-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="c09fc-533">Két hullámcímke típus létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-533">Create two wave label types</span></span>

1. <span data-ttu-id="c09fc-534">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímketípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="c09fc-535">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-536">**Címke típusa:** *kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-537">**Leírás:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="c09fc-538">Hozzon létre egy második rekordot, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-539">**Címke típusa:** *raklap*</span><span class="sxs-lookup"><span data-stu-id="c09fc-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="c09fc-540">**Leírás:** *raklap*</span><span class="sxs-lookup"><span data-stu-id="c09fc-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="c09fc-541">Egységszekvencia-csoportok beállítása</span><span class="sxs-lookup"><span data-stu-id="c09fc-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="c09fc-542">Lépjen a **Raktárkezelés \> Beállítás \> Raktár \> Egységszekvencia-csoportok** részre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="c09fc-543">Válassza ki vagy hozzon létre egy **Ea Box PL** csoportot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="c09fc-544">A **Doboz** sorban állítsa a **Hullámcímketípus** mezőt *Kartondoboz* értékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="c09fc-545">A **PL** sorban állítsa a **Hullámcímketípus** mezőt *Raklap* értékre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="c09fc-546">Hullámcímkesablonok létrehozása</span><span class="sxs-lookup"><span data-stu-id="c09fc-546">Create wave label templates</span></span>

1. <span data-ttu-id="c09fc-547">Ugrás a **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Hullámcímkesablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="c09fc-548">Hozzon létre egy címkesablont, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-549">**Címkesablon neve:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="c09fc-550">**Leírás:** *Kartondobozcímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="c09fc-551">**Hullámlépés kódja:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-552">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c09fc-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c09fc-553">Az **Általános** gyorslapon a **Hullámcímketípus** mezőben válasszon egy értéket, pl. az *Kartondoboz* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="c09fc-554">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c09fc-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-555">**Címkeelrendezés azonosítója:** *Kartondoboz*</span><span class="sxs-lookup"><span data-stu-id="c09fc-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="c09fc-556">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c09fc-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c09fc-557">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c09fc-558">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-559">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c09fc-560">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c09fc-561">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-562">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-563">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-564">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c09fc-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c09fc-565">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c09fc-566">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="c09fc-567">A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="c09fc-568">A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-569">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-570">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-571">**Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*</span><span class="sxs-lookup"><span data-stu-id="c09fc-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="c09fc-572">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c09fc-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c09fc-573">Adjon hozzá egy második sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-574">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-575">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-576">**Mező:** *Szállítmány azonosítója*</span><span class="sxs-lookup"><span data-stu-id="c09fc-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="c09fc-577">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c09fc-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c09fc-578">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="c09fc-579">Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri.</span><span class="sxs-lookup"><span data-stu-id="c09fc-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="c09fc-580">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="c09fc-581">A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="c09fc-582">A **Hullámcímkesablon-csoport** párbeszédpanel azon sorához, ahol a **hivatkozási mező neve** mező a *szállítmányazonosító* értékre van állítva, adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c09fc-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="c09fc-583">**Szünet címkéjének nyomtatása:** jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="c09fc-584">**Címke elrendezésének azonosítója:** Jelöljön ki egy szünetcímkét.</span><span class="sxs-lookup"><span data-stu-id="c09fc-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="c09fc-585">(Például válassza ki az ebben a helyzetben korábban létrehozott *Szünet* címkeelrendezést.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="c09fc-586">**Nyomtató neve:** Válassza ki a szünet címkéjének nyomtatóját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="c09fc-587">(A címkék felosztásának céljából általában ugyanaz a nyomtató van kiválasztva, mint a **hullámcímkesablon részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="c09fc-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="c09fc-588">Más forgatókönyvek azonban lehetségesek.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="c09fc-589">Abban a sorban, ahol a **hivatkozási mező neve** mező a *hivatkozási rakománysor azonosítójára* van állítva , jelölje be a **címke-összeállítás azonosítója** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c09fc-590">Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="c09fc-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="c09fc-591">Ezt a címksorozatot a címke elrendezésére lehet nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="c09fc-592">Ezenkívül a különböző szállítmányok címkéit a kiválasztott szünetcímke elválasztja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="c09fc-593">Az **OK** gombra kattintva zárja be a **Hullámcímkesablon csoportja** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="c09fc-594">Hozzon létre egy második címkesablont, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-595">**Címkesablon neve:** *Raklapcímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="c09fc-596">**Leírás:** *raklapcímkék*</span><span class="sxs-lookup"><span data-stu-id="c09fc-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="c09fc-597">**Hullámlépés kódja:** *Raklap*</span><span class="sxs-lookup"><span data-stu-id="c09fc-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="c09fc-598">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c09fc-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c09fc-599">Az **Általános** gyorslapon a **Hullámcímketípus** mezőben válasszon egy értéket, pl. az *Raklap* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="c09fc-600">A **Hullámcímkesablon adatai** gyorslapján vegyen fel egy sort, amely a következő beállításokkal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="c09fc-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-601">**Címkeelrendezés azonosítója:** *Raklap*</span><span class="sxs-lookup"><span data-stu-id="c09fc-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="c09fc-602">**Nyomtató neve:** válassza ki a megfelelő ZPL nyomtatót.</span><span class="sxs-lookup"><span data-stu-id="c09fc-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="c09fc-603">**Lekérdezés futtatása:** *Igen* (ez a beállítás nem kötelező, de ajánlott az optimális teljesítmény érdekében.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="c09fc-604">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c09fc-605">Nem kötelező: Ha ügyfélre vonatkozó címkét állít be, akkor egy lekérdezést kell létrehoznia, hogy megkeresse a vevő számláját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="c09fc-606">A **Hullámcímkesablon adatai** gyorslapján válassza a **lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="c09fc-607">Ezután a lekérdezésszerkesztő párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-608">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-609">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="c09fc-610">**Mező:** *Számlaszám*</span><span class="sxs-lookup"><span data-stu-id="c09fc-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="c09fc-611">**Feltételek:** Adja meg a megfelelő vevői számlaszámot.</span><span class="sxs-lookup"><span data-stu-id="c09fc-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="c09fc-612">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a lekérdezéstervező párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="c09fc-613">A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához a teljes címkesablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="c09fc-614">A lekérdezésszerkesztő párbeszédpanelen, a **Rendezés** lapon adjon hozzá egy sort a következő beállításokkal.</span><span class="sxs-lookup"><span data-stu-id="c09fc-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-615">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-616">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-617">**Mező:** *Hivatkozási terhelési sor azonosítója (rekord azonosítója)*</span><span class="sxs-lookup"><span data-stu-id="c09fc-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="c09fc-618">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c09fc-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c09fc-619">Adjon hozzá egy második sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-620">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-621">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="c09fc-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="c09fc-622">**Mező:** *Szállítmány azonosítója*</span><span class="sxs-lookup"><span data-stu-id="c09fc-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="c09fc-623">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="c09fc-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="c09fc-624">Az lekérdezésszerkesztő párbeszédablak bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c09fc-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="c09fc-625">Egy üzenet jelenik meg, amely a csoportosítás-visszaállítási művelet jóváhagyását kéri.</span><span class="sxs-lookup"><span data-stu-id="c09fc-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="c09fc-626">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="c09fc-627">A műveleti ablaktáblán válassza ki a **Hullámcímkesablon-csoport** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="c09fc-628">A **Hullámcímkesablon-csoport** párbeszédpanel azon sorához, ahol a **hivatkozási mező neve** mező a *szállítmányazonosító* értékre van állítva, adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c09fc-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="c09fc-629">**Szünet címkéjének nyomtatása:** jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="c09fc-630">**Címke elrendezésének azonosítója:** Jelöljön ki egy szünetcímkét.</span><span class="sxs-lookup"><span data-stu-id="c09fc-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="c09fc-631">(Például válassza ki az ebben a helyzetben korábban létrehozott *Szünet* címkeelrendezést.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="c09fc-632">**Nyomtató neve:** Válassza ki a szünet címkéjének nyomtatóját.</span><span class="sxs-lookup"><span data-stu-id="c09fc-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="c09fc-633">(A címkék felosztásának céljából általában ugyanaz a nyomtató van kiválasztva, mint a **hullámcímkesablon részletek** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="c09fc-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="c09fc-634">Más forgatókönyvek azonban lehetségesek.)</span><span class="sxs-lookup"><span data-stu-id="c09fc-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="c09fc-635">Abban a sorban, ahol a **hivatkozási mező neve** mező a *hivatkozási rakománysor azonosítójára* van állítva , jelölje be a **címke-összeállítás azonosítója** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="c09fc-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c09fc-636">Ez a beállítás egy címkesorozatot hoz létre („X 1. kartondoboz”) rakománysoronként az egész hullámban, a munkacsoportosítási beállítástól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="c09fc-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="c09fc-637">Ezt a címksorozatot a címke elrendezésére lehet nyomtatni.</span><span class="sxs-lookup"><span data-stu-id="c09fc-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="c09fc-638">Ezenkívül a különböző szállítmányok címkéit a kiválasztott szünetcímke elválasztja.</span><span class="sxs-lookup"><span data-stu-id="c09fc-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="c09fc-639">Számsorozat-bővítések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c09fc-639">Configure number sequence extensions</span></span>

<span data-ttu-id="c09fc-640">A számsorozat-bővítések meghatározott számsorozatok GS1 megfelelőségét vezérlik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="c09fc-641">Ez a konfiguráció nem kötelező az aktuális forgatókönyv esetében.</span><span class="sxs-lookup"><span data-stu-id="c09fc-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="c09fc-642">További tájékoztatás és konfigurációs utasítások: [a számsorozat-kiterjesztések konfigurálása](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="c09fc-643">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="c09fc-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="c09fc-644">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c09fc-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="c09fc-645">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c09fc-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c09fc-646">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c09fc-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c09fc-647">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="c09fc-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="c09fc-648">Adjon hozzá 2 értékesítésirendelési-sort:</span><span class="sxs-lookup"><span data-stu-id="c09fc-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="c09fc-649">1. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-649">Sales order line 1:</span></span>

        - <span data-ttu-id="c09fc-650">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c09fc-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="c09fc-651">**Mennyiség:** *9024*</span><span class="sxs-lookup"><span data-stu-id="c09fc-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="c09fc-652">**Egység:** *ea* (9024 ea = 376 Box = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="c09fc-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="c09fc-653">2. értékesítésirendelés-sor:</span><span class="sxs-lookup"><span data-stu-id="c09fc-653">Sales order line 2:</span></span>

        - <span data-ttu-id="c09fc-654">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="c09fc-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="c09fc-655">**Mennyiség:** *9016*</span><span class="sxs-lookup"><span data-stu-id="c09fc-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="c09fc-656">**Egység:** *ea* (9016 ea = 322 Box = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="c09fc-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c09fc-657">Az itt megadott cikkek és mennyiségek csak példák.</span><span class="sxs-lookup"><span data-stu-id="c09fc-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="c09fc-658">A korábban megadott egységszekvencia-csoportot kell használnia, meg kell határozni a egységátváltást *ea* elemről *Box* elemről *PL* elemre, és rendelkezniük kell készlettel a *62.* raktárban.</span><span class="sxs-lookup"><span data-stu-id="c09fc-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="c09fc-659">További tájékoztatás: [Mértékegység- és készletezési irányelvek](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c09fc-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="c09fc-660">Jelölje ki az 1. értékesítésirendelés-sort.</span><span class="sxs-lookup"><span data-stu-id="c09fc-660">Select sales order line 1.</span></span> <span data-ttu-id="c09fc-661">Ezután az **Értékesítési rendelés sora** szakasz **Készlet** menüjében válassza a **Foglalások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="c09fc-662">A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet, mjad zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="c09fc-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="c09fc-663">Ismételje meg a 4. és 5. lépést a 2. értékesítésirendelési-sorhoz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="c09fc-664">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c09fc-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c09fc-665">A következő események zajlanak le:</span><span class="sxs-lookup"><span data-stu-id="c09fc-665">The following events occur:</span></span> 

    - <span data-ttu-id="c09fc-666">A rendszer feldolgozza a létrehozott szállítmányt a címkenyomtatási lépést tartalmazó sablon használatával.</span><span class="sxs-lookup"><span data-stu-id="c09fc-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="c09fc-667">A címke elrendezése a címke formátumának meghatározására szolgál, az eredmény pedig a címkesablonban kiválasztott nyomtatón kinyomtatott címke lesz.</span><span class="sxs-lookup"><span data-stu-id="c09fc-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="c09fc-668">A hullámcímkék létrehozása és nyomtatása megtörténik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="c09fc-669">A címkék számának meg kell egyeznie a kartondobozok számával (ebben a példában 376 dobozcímke az 1. sorhoz, 322 dobozcímke a 2. sorhoz, 47 raklapcímke a 2. sorhoz és két szünetcímke, amely a szállítmány azonosítójával rendelkezik).</span><span class="sxs-lookup"><span data-stu-id="c09fc-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="c09fc-670">Létrejön egy új fuvarlevél-azonosító a szállítmányok számára.</span><span class="sxs-lookup"><span data-stu-id="c09fc-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="c09fc-671">Ha beállította a számsorozat-kiterjesztéseket, akkor a hullámcímke-azonosítók az **SSCC-18** számformátumot követik.</span><span class="sxs-lookup"><span data-stu-id="c09fc-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="c09fc-672">A következő lapokon megtekintheti és újranyomtathatja a hullámcímkéket:</span><span class="sxs-lookup"><span data-stu-id="c09fc-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="c09fc-673">Minden szállítmány \> Szállítmány adatai</span><span class="sxs-lookup"><span data-stu-id="c09fc-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="c09fc-674">Minden rakomány \> Rakomány adatai</span><span class="sxs-lookup"><span data-stu-id="c09fc-674">All loads \> Load details</span></span>
- <span data-ttu-id="c09fc-675">Minden hullám</span><span class="sxs-lookup"><span data-stu-id="c09fc-675">All waves</span></span>
- <span data-ttu-id="c09fc-676">Hullámcímkék</span><span class="sxs-lookup"><span data-stu-id="c09fc-676">Wave labels</span></span>
- <span data-ttu-id="c09fc-677">Hullámcímke előzményei</span><span class="sxs-lookup"><span data-stu-id="c09fc-677">Wave label history</span></span>

<span data-ttu-id="c09fc-678">A legtöbb ilyen lap esetében a megfelelő függvényt megtalálhatja, ha ki választja a műveleti ablaktábla **Szállítmányok** lapján a **Kapcsolódó információk** csoport **Hullámcímkék** elemét.</span><span class="sxs-lookup"><span data-stu-id="c09fc-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c09fc-679">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c09fc-679">Additional resources</span></span>

- [<span data-ttu-id="c09fc-680">Hullámcímkék újranyomtatása és érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="c09fc-680">Reprint and void wave labels</span></span>](reprint-and-void-wave-labels.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]