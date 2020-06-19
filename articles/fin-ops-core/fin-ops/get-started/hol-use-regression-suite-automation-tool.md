---
title: A Regression Suite Automation Tool-oktatóanyag használata
description: Ez a témakör bemutatja, hogy hogyan használható a Regression Suite Automation Tool (RSAT). Leírja a különböző funkciókat, és speciális parancsfájlkezelést használó példákat tartalmaz.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 0c2babc3144cae5c68075bd853a2587505263776
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410150"
---
# <a name="regression-suite-automation-tool-tutorial"></a><span data-ttu-id="dbe5c-104">Regression Suite Automation Tool-oktatóanyag</span><span class="sxs-lookup"><span data-stu-id="dbe5c-104">Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="dbe5c-105">Az internetböngésző eszközeivel letöltheti és mentheti ezt a lapot PDF-formátumban.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="dbe5c-106">Ez az oktatóanyag végigvezet a Regression Suite Automation Tool (RSAT) néhány speciális funkcióján, tartalmaz bemutatófeladatot, és leírja a stratégiát és a fontos tanulási pontokat is.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span> 

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="dbe5c-107">A RSAT és a Feladatrögzítő fontos jellemzői</span><span class="sxs-lookup"><span data-stu-id="dbe5c-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="dbe5c-108">Egy mezőérték ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="dbe5c-108">Validate a field value</span></span>

<span data-ttu-id="dbe5c-109">A RSAT ellenőrzési lépéseket tesz lehetővé a tesztesetéhez a várt értékek érvényesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="dbe5c-110">Ha további tájékoztatást szeretne erről a funkcióról, olvassa el a [Várható értékek érvényesítése](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md) című cikket.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-110">For information about this feature, see the article [Validate expected values](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).</span></span>

<span data-ttu-id="dbe5c-111">A következő példa bemutatja, hogyan használható ez a funkció annak ellenőrzésére, hogy az aktuális készlet nagyobb mint 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="dbe5c-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="dbe5c-112">Hozzon létre egy olyan feladatrögzítést a **USMF** vállalat bemutató adatai között, amelynek a következő lépései vannak:</span><span class="sxs-lookup"><span data-stu-id="dbe5c-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="dbe5c-113">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="dbe5c-114">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="dbe5c-115">Például szűrjön az **1000** értékre a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="dbe5c-116">Válassza az **Aktuális készlet** elemet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="dbe5c-117">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="dbe5c-118">Például szűrjön az **1** értékre a **Telephely** mezőben.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="dbe5c-119">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="dbe5c-120">Ellenőrizze, hogy az **Összes rendelkezésre álló** mező értéke **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="dbe5c-121">Mentse a feladatrögzítést, és csatolja a tesztesetéhez az Azure Devops-ban.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-121">Save the task recording and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="dbe5c-122">Adja hozzá a tesztesetet a tesztelési tervhez, és töltse be a tesztesetet a RSAT-be.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="dbe5c-123">Nyissa meg az Excel-paraméterfájlt.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-123">Open the Excel parameter file.</span></span> <span data-ttu-id="dbe5c-124">Az **InventOnhandItem** lapon látható az **InventOnhandItem ellenőrzése** szakasz, amelyben szerepel egy **Operátor** mező.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-124">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Operátor mező](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="dbe5c-126">Ha ellenőrizni szeretné, hogy az aktuális készlet mindig nagyobb, mint 0, akkor módosítsa az **Érték** mező értékét **411**-ről **0** értékre, és az **Operátor** mező értékét egyenlőségjelről (**=**) a nagyobb mint jelre (**\>**).</span><span class="sxs-lookup"><span data-stu-id="dbe5c-126">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Az Érték és az Operátor mező értéke megváltozott](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="dbe5c-128">Mentse és zárja be az Excel-paraméterfájlt.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-128">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="dbe5c-129">A **Feltöltés** gombra kattintva mentheti a módosításokat az Azure DevOps rendszerbe, amelyeket az Excel-paraméterfájlban tett.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-129">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="dbe5c-130">Ha most a megadott cikk **Összes rendelkezésre álló** mezője értéke meghaladja a 0 (nulla) értéket, akkor a tesztek sikeresek lesznek, függetlenül a tényleges aktuális készlet értékétől.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-130">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="dbe5c-131">Mentett változók és a tesztesetek láncolása</span><span class="sxs-lookup"><span data-stu-id="dbe5c-131">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="dbe5c-132">A RSAT egyik alapvető funkciója a tesztesetek láncolása, tehát az a képesség, amellyel egy teszt változókat adhat át más teszteknek.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-132">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="dbe5c-133">A további tudnivalókat lásd a [Változók másolása tesztesetekre](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md) című cikkben.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-133">For more information, see the article [Copy variables to chain test cases](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="dbe5c-134">Származtatott teszteset</span><span class="sxs-lookup"><span data-stu-id="dbe5c-134">Derived test case</span></span>

<span data-ttu-id="dbe5c-135">A RSAT használatával több feladatrögzítést is felhasználhat több tesztesettel így a feladatok különböző adatkonfigurációkkal futtathatók.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-135">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="dbe5c-136">További tájékoztatás a [Származtatott tesztesetek](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) cikkben található.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-136">See the article [Derived test cases](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="dbe5c-137">Értesítések és üzenetek érvényesítése</span><span class="sxs-lookup"><span data-stu-id="dbe5c-137">Validate notifications and messages</span></span>

<span data-ttu-id="dbe5c-138">Ez a funkció annak ellenőrzésére használható, hogy történt-e művelet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-138">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="dbe5c-139">Például egy termelési rendelés létrehozása, becslése, majd elindítása történt, megjelenik a „Termelés – Indítás” üzenetet, amellyel értesíti, hogy a termelési rendelés elindult.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-139">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Termelés – Indítás értesítés](./media/use_rsa_tool_05.png)

<span data-ttu-id="dbe5c-141">Ezt az üzenetet a RSAT programon keresztül ellenőrizni lehet, ha megadja az üzenet szövegét a megfelelő rögzítéshez tartozó Excel paraméterfájl **MessageValidation** lapján.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-141">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Üzenet ellenőrzése lap](./media/use_rsa_tool_06.png)

<span data-ttu-id="dbe5c-143">Miután lefutott a teszteset, az Excel-paraméterfájlban szereplő üzenetet a program összehasonlítja az üzenettel.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-143">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="dbe5c-144">Ha az üzenetek nem egyeznek, a teszteset nem fog sikerülni.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-144">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="dbe5c-145">Az Excel-paraméterfájl **MessageValidation** lapján egynél több üzenetet is megadhat.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-145">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="dbe5c-146">Az üzenetek a tájékoztató üzenetek helyett hiba- vagy figyelmeztető üzenetek is lehetnek.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-146">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="dbe5c-147">Pillanatkép</span><span class="sxs-lookup"><span data-stu-id="dbe5c-147">Snapshot</span></span>

<span data-ttu-id="dbe5c-148">Ez a funkció képernyőképeket készít a feladatrögzítés során végrehajtott lépésekről.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-148">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="dbe5c-149">Ez a ellenőrzés vagy hibakeresés céljából hasznos.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-149">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="dbe5c-150">A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elem értékét **hamis** értékről **igaz** értékre.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-150">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="dbe5c-151">Amikor futtatja a tesztesetet, az RSAT pillanatképeket (képeket) fog generálni a lépésekről a visszajátszási mappában munkakönyvtárban.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-151">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="dbe5c-152">Ha egy korábbi RSAT-verziót használ a képek a különálló **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback** mappába lesznek mentve, és minden futtatott tesztesethez egy külön mappa jön létre.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-152">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="dbe5c-153">Hozzárendelés</span><span class="sxs-lookup"><span data-stu-id="dbe5c-153">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="dbe5c-154">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="dbe5c-154">Scenario</span></span>

1. <span data-ttu-id="dbe5c-155">A termék tervezője létrehoz egy új kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-155">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="dbe5c-156">A termelési vezető kezdeményez egy termelési rendelést, hogy a készlet szintje két darabra növekedjen.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-156">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="dbe5c-157">A gyártás elindítja és befejezi a termelési rendelést, és ellenőrzi, hogy a készleten lévő mennyiség két darab.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-157">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="dbe5c-158">Az értékesítési csoport rendelést kap négy darabra az új termékből.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-158">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="dbe5c-159">Ezért az értékesítési csoport frissíti a nettó szükségletet a dinamikus terven keresztül.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-159">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="dbe5c-160">Mivel nem áll rendelkezésre további kapacitás, az alapértelmezett rendelési irányelv beállítása „vásárlás gyártás helyett”.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-160">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="dbe5c-161">Így létrejön egy tervezett beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-161">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="dbe5c-162">A vevő hozzáadja a szállítót, megerősíti a tervezett beszerzési rendelést, majd megerősíti a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-162">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="dbe5c-163">Amikor a megvásárolt áruk megérkeznek az üzletbe, az üzlet operátora megkeresi a kapcsolódó beszerzési rendelést, és bevételezi az árukat.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-163">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="dbe5c-164">Mivel a rendelést már befejeződött, az árukat az értékesítési rendeléshez lehet kitárolni és csomagolni.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-164">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="dbe5c-165">A pénzügy felad egy beszerzési számlát és egy értékesítési számlát.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-165">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="dbe5c-166">A következő ábra bemutatja az adott eset folyamatát.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-166">The following illustration shows the flow for this scenario.</span></span>

![A bemutató eset folyamata](./media/use_rsa_tool_14.png)

<span data-ttu-id="dbe5c-168">A következő ábra bemutatja az üzleti folyamatok hierarchiáját ehhez a forgatókönyvhöz az LCS Üzletifolyamat-modellező moduljában.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-168">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![A bemutató eset üzleti folyamatai](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="dbe5c-170">Stratégia – Kulcsfontosságú tanulási pontok</span><span class="sxs-lookup"><span data-stu-id="dbe5c-170">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="dbe5c-171">Adat</span><span class="sxs-lookup"><span data-stu-id="dbe5c-171">Data</span></span>

- <span data-ttu-id="dbe5c-172">Győződjön meg róla, hogy rendelkezik reprezentatív adatmennyiséggel (termelési/arany konfigurációs adatok másolata és áttelepített adatok).</span><span class="sxs-lookup"><span data-stu-id="dbe5c-172">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="dbe5c-173">Amikor a feladatrögzítőn keresztül új adatokat hoz létre, olyan tesztneveket hozzon létre, amelyek nem ütköznek a meglévő nevekkel (például használjon **RSATxxx** előtagot).</span><span class="sxs-lookup"><span data-stu-id="dbe5c-173">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="dbe5c-174">Az Azure Időponthoz kötött visszaállítás használatával futtassa újra a teszteket a nem 1. szintű környezetekben.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-174">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="dbe5c-175">Annak ellenére, hogy a **RANDOM** és **NOW** Excel-funkciók segítségével egyedi kombinációt generálhat, az erőfeszítés jelentősen magas.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-175">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="dbe5c-176">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-176">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="dbe5c-177">Feladatrögzítő</span><span class="sxs-lookup"><span data-stu-id="dbe5c-177">Task recorder</span></span>

- <span data-ttu-id="dbe5c-178">Forgatókönyvek meghatározása a rögzítés megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-178">Define scenarios before you start recording.</span></span> <span data-ttu-id="dbe5c-179">A jól kezelt projekt előre meghatározott teszt-forgatókönyveket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-179">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="dbe5c-180">Egy teszteset létrehozásakor vegye figyelembe, hogy mennyire kiszámítható a tesztesetek kimenete.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-180">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="dbe5c-181">Ossza fel a rögzítéseket, ha különböző szerepkörök hajtják őket végre, vagy ha várakozási idő van, vagy külső esemény történik a következő lépés előtt.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-181">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="dbe5c-182">Ne válassza ki listákban szereplő értékeket.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-182">Avoid selecting values in lists.</span></span> <span data-ttu-id="dbe5c-183">Ehelyett használjon szöveges formátumokat, mint **FIFO**, **AudioRM**, és **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-183">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="dbe5c-184">Ha listából választ, az érték listában elfoglalt pozícióját rögzíti, nem magát az értéket.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-184">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="dbe5c-185">Ha elemeket adnak hozzá az adott listához, az adott érték pozíciója megváltozhat.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-185">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="dbe5c-186">Emiatt a rögzítés más paramétert fog használni, és ez a többi forgatókönyvet is érintheti.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-186">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="dbe5c-187">Gondoljon a többfelhasználós viselkedésre is.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-187">Think about multi-user behavior.</span></span> <span data-ttu-id="dbe5c-188">Például ne feltételezze, hogy mindig az újonnan létrehozott értékesítési rendelést jelöli ki automatikusan a rendszer.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-188">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="dbe5c-189">Ehelyett mindig használjon szűrőket a helyes rendelés megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-189">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="dbe5c-190">A Feladatrögzítő Másolás funkciójával mentse el az újonnan létrehozott termék nevét, így használhatja láncolt tesztesetekben.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-190">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="dbe5c-191">A Feladatrögzítő Ellenőrzés funkciójával határozzon meg ellenőrzési pontokat, amelyek ellenőrzik, hogy a lépések megfelelően futottak le.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-191">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="dbe5c-192">RSAT</span><span class="sxs-lookup"><span data-stu-id="dbe5c-192">RSAT</span></span>

- <span data-ttu-id="dbe5c-193">Ha egy másik vállalatnál szeretné futtatni a tesztet, módosíthatja a vállalatot az Excel-paraméterfájl **Általános** lapján.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-193">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="dbe5c-194">Győződjön meg róla, hogy a beállítások és az adatok elérhetők az újonnan kiválasztott vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-194">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="dbe5c-195">A tesztfelhasználót az Excel-paraméterfájl **általános** lapján lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-195">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="dbe5c-196">Adja meg annak a felhasználónak az e-mail-azonosítóját, aki futtatja a tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-196">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="dbe5c-197">Ily módon a teszteset a megadott felhasználó biztonsági engedélyeinek használatával futtatható.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-197">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="dbe5c-198">Ha szeretne várni a teszt elindítása előtt, akkor az Excel-paraméterfájl **Általános** lapján megadhat egy szünetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-198">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="dbe5c-199">Ez a szünet kötegelt feladatban is használható (például akkor, ha egy munkafolyamatot a következő lépés végrehajtása előtt futtatni kell.)</span><span class="sxs-lookup"><span data-stu-id="dbe5c-199">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="dbe5c-200">Speciális parancsfájlkezelés</span><span class="sxs-lookup"><span data-stu-id="dbe5c-200">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="dbe5c-201">CLI</span><span class="sxs-lookup"><span data-stu-id="dbe5c-201">CLI</span></span>

<span data-ttu-id="dbe5c-202">Az RSAT-ot a **Parancssor** vagy a **PowerShell** ablakból is be lehet hívni.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-202">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="dbe5c-203">Győződjön meg róla, hogy a **TestRoot** környezeti változó az RSAT telepítési útvonalára van állítva.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-203">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="dbe5c-204">(Microsoft Windows rendszerben nyissa meg a **Vezérlőpult** elemet, válassza a **Rendszer és biztonság \> Rendszer \> Speciális rendszerbeállítások** menüpontot, majd válassza a **Környezet változók** lehetőséget.)</span><span class="sxs-lookup"><span data-stu-id="dbe5c-204">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="dbe5c-205">Nyissa meg a **Parancssor** vagy **PowerShell** ablakot rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-205">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="dbe5c-206">Keresse meg a RSAT telepítési könyvtárat.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-206">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="dbe5c-207">Listázza az összes parancsot.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-207">List all commands.</span></span>

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a><span data-ttu-id="dbe5c-208">?</span><span class="sxs-lookup"><span data-stu-id="dbe5c-208">?</span></span> 
<span data-ttu-id="dbe5c-209">A rendelkezésre álló parancsokkal és a paraméterekkel kapcsolatos súgó megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-209">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="dbe5c-210">Nem kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-210">Optional parameters</span></span>

**``command``**


<span data-ttu-id="dbe5c-211">A ``[command]`` az alább megadott parancsok egyike.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-211">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="dbe5c-212">névjegy</span><span class="sxs-lookup"><span data-stu-id="dbe5c-212">about</span></span>
<span data-ttu-id="dbe5c-213">Az aktuális verziót jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-213">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="dbe5c-214">cls</span><span class="sxs-lookup"><span data-stu-id="dbe5c-214">cls</span></span>
<span data-ttu-id="dbe5c-215">Törli az adatokat a képernyőről.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-215">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="dbe5c-216">letöltés</span><span class="sxs-lookup"><span data-stu-id="dbe5c-216">download</span></span>
<span data-ttu-id="dbe5c-217">Letölti a megadott tesztesethez tartozott mellékleteket a kimeneti környvtárba.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-217">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="dbe5c-218">A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-218">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="dbe5c-219">Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-219">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-220">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-220">Required parameters</span></span>
<span data-ttu-id="dbe5c-221">**``test_case_id``** A teszteset azonosítóját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-221">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="dbe5c-222">**``output_dir``** A kimeneti könyvtárat jelöli.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-222">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="dbe5c-223">A könyvtárnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-223">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-224">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-224">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="dbe5c-225">szerkesztés</span><span class="sxs-lookup"><span data-stu-id="dbe5c-225">edit</span></span>
<span data-ttu-id="dbe5c-226">Lehetővé teszi a paraméterek fájl megnyitását Excel programban, és annak szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-226">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-227">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-227">Required parameters</span></span>
<span data-ttu-id="dbe5c-228">**``excel_file``** Egy meglévő Excel-fájl teljes elérési útját kell tartalmaznia.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-228">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-229">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-229">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="dbe5c-230">létrehozás</span><span class="sxs-lookup"><span data-stu-id="dbe5c-230">generate</span></span>
<span data-ttu-id="dbe5c-231">Létrehozza a tesztvégrehajtási és paraméterfájlokat a megadott tesztesethez a kimeneti könyvtárban.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-231">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="dbe5c-232">A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-232">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="dbe5c-233">Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-233">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-234">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-234">Required parameters</span></span>
<span data-ttu-id="dbe5c-235">**``test_case_id``** A teszteset azonosítóját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-235">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="dbe5c-236">**``output_dir``** A kimeneti könyvtárat jelöli.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-236">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="dbe5c-237">A könyvtárnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-237">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-238">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-238">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="dbe5c-239">generatederived</span><span class="sxs-lookup"><span data-stu-id="dbe5c-239">generatederived</span></span>
<span data-ttu-id="dbe5c-240">Új tesztesetet hoz létre, amely a megadott tesztesetből származik.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-240">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="dbe5c-241">A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-241">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="dbe5c-242">Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-242">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-243">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-243">Required parameters</span></span>
<span data-ttu-id="dbe5c-244">**``parent_test_case_id``** A fölérendelt teszteset azonosítóját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-244">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="dbe5c-245">**``test_plan_id``** A tesztkonstrukció azonosítóját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-245">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="dbe5c-246">**``test_suite_id``** A tesztcsomag azonosítóját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-246">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-247">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-247">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="dbe5c-248">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="dbe5c-248">generatetestonly</span></span>
<span data-ttu-id="dbe5c-249">Csak a tesztvégrehajtási fájlt hozza létre a megadott tesztesethez a kimeneti könyvtárban.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-249">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="dbe5c-250">A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-250">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="dbe5c-251">Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-251">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-252">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-252">Required parameters</span></span>
<span data-ttu-id="dbe5c-253">**``test_case_id``** A teszteset azonosítóját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-253">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="dbe5c-254">**``output_dir``** A kimeneti könyvtárat jelöli.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-254">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="dbe5c-255">A könyvtárnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-255">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-256">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-256">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="dbe5c-257">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="dbe5c-257">generatetestsuite</span></span>
<span data-ttu-id="dbe5c-258">Létrehozza az összes tesztesetet a megadott csomaghoz a kimeneti könyvtárban.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-258">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="dbe5c-259">A ``listtestsuitenames`` paranccsal lekérheti az összes rendelkezésre álló tesztcsomagot.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-259">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="dbe5c-260">Az oszlopból bármelyik értéket használhatja **test_suite_name** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-260">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-261">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-261">Required parameters</span></span>
<span data-ttu-id="dbe5c-262">**``test_suite_name``** A tesztcsomag nevét jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-262">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="dbe5c-263">**``output_dir``** A kimeneti könyvtárat jelöli.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-263">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="dbe5c-264">A könyvtárnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-264">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-265">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-265">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="dbe5c-266">súgó</span><span class="sxs-lookup"><span data-stu-id="dbe5c-266">help</span></span>
<span data-ttu-id="dbe5c-267">Azonos a következővel: [?](#section)</span><span class="sxs-lookup"><span data-stu-id="dbe5c-267">Identical to the [?](#section)</span></span> <span data-ttu-id="dbe5c-268">parancs</span><span class="sxs-lookup"><span data-stu-id="dbe5c-268">command</span></span>


#### <a name="list"></a><span data-ttu-id="dbe5c-269">listában</span><span class="sxs-lookup"><span data-stu-id="dbe5c-269">list</span></span>
<span data-ttu-id="dbe5c-270">Felsorolja az összes elérhető teszt esetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-270">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="dbe5c-271">listtestplans</span><span class="sxs-lookup"><span data-stu-id="dbe5c-271">listtestplans</span></span>
<span data-ttu-id="dbe5c-272">Felsorolja az összes elérhető tesztkonstrukciót.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-272">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="dbe5c-273">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="dbe5c-273">listtestsuite</span></span>
<span data-ttu-id="dbe5c-274">Felsorolja a megadott tesztcsomag teszteseteit.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-274">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="dbe5c-275">A ``listtestsuitenames`` paranccsal lekérheti az összes rendelkezésre álló tesztcsomagot.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-275">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="dbe5c-276">Az első oszlopból bármelyik értéket használhatja **suite_name** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-276">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-277">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-277">Required parameters</span></span>
<span data-ttu-id="dbe5c-278">**``suite_name``** A kívánt csomag neve.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-278">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-279">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-279">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="dbe5c-280">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="dbe5c-280">listtestsuitenames</span></span>
<span data-ttu-id="dbe5c-281">Felsorolja az összes elérhető tesztcsomagot.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-281">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="dbe5c-282">visszajátszás</span><span class="sxs-lookup"><span data-stu-id="dbe5c-282">playback</span></span>
<span data-ttu-id="dbe5c-283">Visszajátszik egy tesztesetet Excel-fájl segítségével.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-283">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-284">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-284">Required parameters</span></span>
<span data-ttu-id="dbe5c-285">**``excel_file``** Az Excel-fájl teljes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-285">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="dbe5c-286">A fájlnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-286">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="dbe5c-287">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-287">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="dbe5c-288">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="dbe5c-288">playbackbyid</span></span>
<span data-ttu-id="dbe5c-289">Egyszerre több tesztesetet játszik le.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-289">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="dbe5c-290">A ``list`` paranccsal lekérheti az összes rendelkezésre álló tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-290">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="dbe5c-291">Az első oszlopból bármelyik értéket használhatja **test_case_id** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-291">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-292">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-292">Required parameters</span></span>
<span data-ttu-id="dbe5c-293">**``test_case_id1``** A meglévő teszteset azonosítója.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-293">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="dbe5c-294">**``test_case_id2``** A meglévő teszteset azonosítója.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-294">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="dbe5c-295">**``test_case_idN``** A meglévő teszteset azonosítója.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-295">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="dbe5c-296">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-296">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="dbe5c-297">playbackmany</span><span class="sxs-lookup"><span data-stu-id="dbe5c-297">playbackmany</span></span>
<span data-ttu-id="dbe5c-298">Több tesztesetet játszik le egyszerre, Excel-fájlok használatával.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-298">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-299">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-299">Required parameters</span></span>
<span data-ttu-id="dbe5c-300">**``excel_file1``** Az Excel-fájl teljes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-300">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="dbe5c-301">A fájlnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-301">File must exist.</span></span>  
<span data-ttu-id="dbe5c-302">**``excel_file2``** Az Excel-fájl teljes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-302">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="dbe5c-303">A fájlnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-303">File must exist.</span></span>  
<span data-ttu-id="dbe5c-304">**``excel_fileN``** Az Excel-fájl teljes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-304">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="dbe5c-305">A fájlnak léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-305">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="dbe5c-306">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-306">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="dbe5c-307">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="dbe5c-307">playbacksuite</span></span>
<span data-ttu-id="dbe5c-308">A megadott tesztcsomagból minden tesztesetet lejátszik.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-308">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="dbe5c-309">A ``listtestsuitenames`` paranccsal lekérheti az összes rendelkezésre álló tesztcsomagot.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="dbe5c-310">Az első oszlopból bármelyik értéket használhatja **suite_name** paraméterként.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-311">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-311">Required parameters</span></span>
<span data-ttu-id="dbe5c-312">**``suite_name``** A kívánt csomag neve.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-313">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-313">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="dbe5c-314">kilépés</span><span class="sxs-lookup"><span data-stu-id="dbe5c-314">quit</span></span>
<span data-ttu-id="dbe5c-315">Bezárja az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-315">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="dbe5c-316">feltöltés</span><span class="sxs-lookup"><span data-stu-id="dbe5c-316">upload</span></span>
<span data-ttu-id="dbe5c-317">A megadott tesztcsomaghoz vagy tesztesetekhez tartozó összes fájlt feltölti.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-317">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="dbe5c-318">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-318">Required parameters</span></span>
<span data-ttu-id="dbe5c-319">**``suite_name``** A megadott tesztcsomaghoz tartozó összes fájlt feltölti.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-319">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="dbe5c-320">**``testcase_id``** A megadott teszteset(ek)hez tartozó összes fájlt feltölti.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-320">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-321">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-321">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="dbe5c-322">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="dbe5c-322">uploadrecording</span></span>
<span data-ttu-id="dbe5c-323">Csak a megadott tesztesetekhez tartozó rögzítési fájlt tölti fel.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-323">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="dbe5c-324">Kötelező paraméterek</span><span class="sxs-lookup"><span data-stu-id="dbe5c-324">Required parameters</span></span>
<span data-ttu-id="dbe5c-325">**``testcase_id``** Csak a megadott tesztesetekhez tartozó rögzítési fájlt tölti fel.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-325">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="dbe5c-326">Példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-326">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="dbe5c-327">használat</span><span class="sxs-lookup"><span data-stu-id="dbe5c-327">usage</span></span>
<span data-ttu-id="dbe5c-328">Kétféle módszert mutat be az alkalmazás meghívására: az egyik alapértelmezett beállítási fájlt használ, a másik egy beállítási fájlt ad meg.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-328">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="dbe5c-329">Windows PowerShell-példák</span><span class="sxs-lookup"><span data-stu-id="dbe5c-329">Windows PowerShell examples</span></span>

[!IMPORTANT] <span data-ttu-id="dbe5c-330">A lenti forgatókönyvek a következők JELEN ÁLLAPOTUKBAN érhetők el, és a Microsoft nem támogatja ezeket.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-330">The example scripts below are provided AS IS for illustration purposes and are not supported by Microsoft.</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="dbe5c-331">Teszteset futtatása egy hurokban</span><span class="sxs-lookup"><span data-stu-id="dbe5c-331">Run a test case in a loop</span></span>

<span data-ttu-id="dbe5c-332">Van egy tesztparancsfájl, amely új vevőt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-332">You have a test script that creates a new customer.</span></span> <span data-ttu-id="dbe5c-333">A parancsfájlkezeléssel ezt a tesztesetet egy hurokban futtathatja, ha minden egyes iteráció futtatása előtt a következő adatokat véletlenszerűvé teszi:</span><span class="sxs-lookup"><span data-stu-id="dbe5c-333">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="dbe5c-334">Vevő azonosítója</span><span class="sxs-lookup"><span data-stu-id="dbe5c-334">Customer ID</span></span>
- <span data-ttu-id="dbe5c-335">Vevő neve</span><span class="sxs-lookup"><span data-stu-id="dbe5c-335">Customer name</span></span>
- <span data-ttu-id="dbe5c-336">Vevő címe</span><span class="sxs-lookup"><span data-stu-id="dbe5c-336">Customer address</span></span>

<span data-ttu-id="dbe5c-337">Az ügyfélazonosító formátuma a következő lesz: *ATCUS\<number\>*, ahol a \<number\> egy érték **000000001** és **999999999** között.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-337">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="dbe5c-338">A következő példában a program egy paramétert, az **indítás** paramétert használja az először használt szám meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-338">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="dbe5c-339">Egy második paramétert (**nr**) a létrehozni kívánt ügyfelek számának meghatározására használ.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-339">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="dbe5c-340">Minden iteráció esetében az Excel-paraméterfájl paraméterei egy UpdateCustomer-funkcióval változtathatók.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-340">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="dbe5c-341">Ezt követően a RSAT parancssor lehívása RunTestCase-funkcióban történik.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-341">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="dbe5c-342">Nyissa meg a Microsoft Windows PowerShell integrált parancsfájl-kezelési környezetet (ISE) rendszergazdai módban, majd illessze be az alábbi kódot az **Untitled1.ps1** elnevezésű ablakba.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-342">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="dbe5c-343">Parancsfájl futtatása, amely a Microsoft Dynamics 365 adataitól függ</span><span class="sxs-lookup"><span data-stu-id="dbe5c-343">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="dbe5c-344">A következő példa egy Open Data protokoll (OData) hívással keresi meg a beszerzési rendelések rendelési állapotát.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-344">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="dbe5c-345">Ha az állapot nem **számlázott**, akkor például lehívhat egy RSAT-tesztet, amely feladja a számlát.</span><span class="sxs-lookup"><span data-stu-id="dbe5c-345">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```xpp
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```
