---
title: A Regression Suite Automation Tool-oktatóanyag használata
description: Ez a témakör bemutatja, hogy hogyan használható a Regression Suite Automation Tool (RSAT). Leírja a különböző funkciókat, és speciális parancsfájlkezelést használó példákat tartalmaz.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 026d1d743b5150f152ef70aa642dcf6841a4e398
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025804"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="2730b-104">A Regression Suite Automation Tool-oktatóanyag használata</span><span class="sxs-lookup"><span data-stu-id="2730b-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="2730b-105">Az internetböngésző eszközeivel letöltheti és mentheti ezt a lapot PDF-formátumban.</span><span class="sxs-lookup"><span data-stu-id="2730b-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="2730b-106">Ez az oktatóanyag végigvezet a Regression Suite Automation Tool (RSAT) néhány speciális funkcióján, tartalmaz bemutatófeladatot, és leírja a stratégiát és a fontos tanulási pontokat is.</span><span class="sxs-lookup"><span data-stu-id="2730b-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="2730b-107">Az RSAT/Feladatrögzítő funkciói</span><span class="sxs-lookup"><span data-stu-id="2730b-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="2730b-108">Egy mezőérték ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="2730b-108">Validate a field value</span></span>

<span data-ttu-id="2730b-109">Ha további információra van szüksége a funkcióról, itt találhat: [Ellenőrzés funkciót tartalmazó új feladatrögzítés létrehozása](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="2730b-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="2730b-110">Mentett változó</span><span class="sxs-lookup"><span data-stu-id="2730b-110">Saved variable</span></span>

<span data-ttu-id="2730b-111">Ha további információra van szüksége a funkcióról, itt találhat: [Meglévő feladatrögzítés módosítása mentett változó létrehozásához](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="2730b-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="2730b-112">Származtatott teszteset</span><span class="sxs-lookup"><span data-stu-id="2730b-112">Derived test case</span></span>

1. <span data-ttu-id="2730b-113">Nyissa meg a Regression Suite Automation Tool (RSAT) eszközt, és válassza ki a [A Regression Suite Automation Tool beállítása és telepítése oktatóanyag](./hol-set-up-regression-suite-automation-tool.md) szakaszban létrehozott mindkét tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="2730b-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool tutorial](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="2730b-114">Válassza az **Új \> Származtatott teszteset létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="2730b-114">Select **New \> Create derived test case**.</span></span>

    ![Származtatott teszteset létrehozása parancs az Új menüben](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="2730b-116">Egy üzenet jelenik meg, amely jelzi, hogy az aktuális tesztcsomag mindegyik kiválasztott tesztesetéhez származtatott tesztesetet hoz létre, és minden egyes származtatott tesztesetnek saját másolata lesz az Excel-paraméterfájlból.</span><span class="sxs-lookup"><span data-stu-id="2730b-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="2730b-117">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2730b-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2730b-118">Származtatott teszteset futtatásakor a program a fölérendelt feladatrögzítést, valamint az Excel-paraméterfájlból származó saját másolatát használja.</span><span class="sxs-lookup"><span data-stu-id="2730b-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="2730b-119">Ily módon ugyanazon tesztet különböző paraméterekkel futtathatja, anélkül, hogy egynél több feladatrögzítést kellene karbantartania.</span><span class="sxs-lookup"><span data-stu-id="2730b-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="2730b-120">Egy származtatott tesztesetnek nem kell ugyanahhoz a tesztcsomaghoz tartoznia, mint a fölérendelt tesztesetnek.</span><span class="sxs-lookup"><span data-stu-id="2730b-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Üzenetpanel](./media/use_rsa_tool_02.png)

    <span data-ttu-id="2730b-122">Két további származtatott teszteset jön létre, és a **Származtatott?** jelölőnégyzet be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="2730b-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Származtatott tesztesetek létrehozva](./media/use_rsa_tool_03.png)

    <span data-ttu-id="2730b-124">A származtatott teszteset automatikusan létrejön az Azure DevOps rendszerben.</span><span class="sxs-lookup"><span data-stu-id="2730b-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="2730b-125">Ez az **Új termék létrehozása** teszteset alárendelt eleme, és speciális kulcsszóval van felcímkézve: **RSAT:DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="2730b-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="2730b-126">Ezeket a teszteseteket a program automatikusan hozzáadja az Azure DevOps tesztelési tervbe.</span><span class="sxs-lookup"><span data-stu-id="2730b-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![RSAT:DerivedTestSteps kulcsszó](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="2730b-128">Ha valamilyen oknál fogva a létrejövő származtatott tesztesetek nem megfelelő sorrendben vannak, akkor lépjen az Azure DevOps felületére, és rendezze át a teszteseteket a tesztcsomagban, hogy az RSAT megfelelő sorrendben futtassa őket.</span><span class="sxs-lookup"><span data-stu-id="2730b-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="2730b-129">Válassza ki csak a származtatott teszteseteket, majd a **Szerkesztés** parancsot a kapcsolódó Excel-paraméterfájlok megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="2730b-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="2730b-130">Szerkessze ezeket az Excel-paraméterfájlokat ugyanúgy, mint a fölérendelt fájlokat.</span><span class="sxs-lookup"><span data-stu-id="2730b-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="2730b-131">Más szóval győződjön meg arról, hogy a termékazonosító be van állítva úgy, hogy automatikusan létrejön.</span><span class="sxs-lookup"><span data-stu-id="2730b-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="2730b-132">Győződjön meg arról is, hogy a mentett változót a megfelelő mezőkbe másolja át a program.</span><span class="sxs-lookup"><span data-stu-id="2730b-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="2730b-133">Az Excel-paraméterfájlok **Általános** lapján frissítse a **Vállalat** mező értékét az **USSI** értékre, hogy a származtatott teszteseteket egy másik jogi személyre futtassa, mint a fölérendelt tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="2730b-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="2730b-134">Ha a teszteseteket egy megadott felhasználóra (vagy egy megadott felhasználóhoz társított szerepkörre) futtatja, akkor frissítheti a **Tesztfelhasználó** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="2730b-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="2730b-135">Válassza a **Futtatás** parancsot, és ellenőrizze, hogy a termék a USMF jogi személyben és a USSI jogi személyben egyaránt létrejött-e.</span><span class="sxs-lookup"><span data-stu-id="2730b-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="2730b-136">Értesítések ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="2730b-136">Validate notifications</span></span>

<span data-ttu-id="2730b-137">Ez a funkció annak ellenőrzésére használható, hogy történt-e művelet.</span><span class="sxs-lookup"><span data-stu-id="2730b-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="2730b-138">Például egy termelési rendelés létrehozása, becslése, majd elindítása történt, megjelenik a „Termelés – Indítás” üzenetet, amellyel értesíti, hogy a termelési rendelés elindult.</span><span class="sxs-lookup"><span data-stu-id="2730b-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Termelés – Indítás értesítés](./media/use_rsa_tool_05.png)

<span data-ttu-id="2730b-140">Ezt az üzenetet a RSAT programon keresztül ellenőrizni lehet, ha megadja az üzenet szövegét a megfelelő rögzítéshez tartozó Excel paraméterfájl **MessageValidation** lapján.</span><span class="sxs-lookup"><span data-stu-id="2730b-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Üzenet ellenőrzése lap](./media/use_rsa_tool_06.png)

<span data-ttu-id="2730b-142">Miután lefutott a teszteset, az Excel-paraméterfájlban szereplő üzenetet a program összehasonlítja az üzenettel.</span><span class="sxs-lookup"><span data-stu-id="2730b-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="2730b-143">Ha az üzenetek nem egyeznek, a teszteset nem fog sikerülni.</span><span class="sxs-lookup"><span data-stu-id="2730b-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="2730b-144">Az Excel-paraméterfájl **MessageValidation** lapján egynél több üzenetet is megadhat.</span><span class="sxs-lookup"><span data-stu-id="2730b-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="2730b-145">Az üzenetek a tájékoztató üzenetek helyett hiba- vagy figyelmeztető üzenetek is lehetnek.</span><span class="sxs-lookup"><span data-stu-id="2730b-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="2730b-146">Értékek ellenőrzése operátorok segítségével</span><span class="sxs-lookup"><span data-stu-id="2730b-146">Validate values by using operators</span></span>

<span data-ttu-id="2730b-147">Az RSAT korábbi verzióiban csak akkor lehet ellenőrizni az értékeket, ha egy ellenőrzési érték egy várt értékkel egyenlő volt.</span><span class="sxs-lookup"><span data-stu-id="2730b-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="2730b-148">Az új funkció segítségével ellenőrizhető, hogy egy változó nem egyenlő, kisebb, vagy nagyobb mint a megadott érték.</span><span class="sxs-lookup"><span data-stu-id="2730b-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="2730b-149">A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elemet **hamis** értékről **igaz** értékre.</span><span class="sxs-lookup"><span data-stu-id="2730b-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="2730b-150">Az Excel-paraméterfájlban megjelenik egy új **Operátor** mező.</span><span class="sxs-lookup"><span data-stu-id="2730b-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2730b-151">Ha egy korábbi RSAT-verziót használt, új Excel-paraméterfájlokat kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="2730b-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Operátor mező](./media/use_rsa_tool_07.png)

<span data-ttu-id="2730b-153">A következő példa bemutatja, hogyan használható ez a funkció annak ellenőrzésére, hogy az aktuális készlet nagyobb mint 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="2730b-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="2730b-154">Hozzon létre egy olyan feladatrögzítést a **USMF** vállalat bemutató adatai között, amelynek a következő lépései vannak:</span><span class="sxs-lookup"><span data-stu-id="2730b-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="2730b-155">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2730b-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="2730b-156">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="2730b-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2730b-157">Például szűrjön az **1000** értékre a **Cikkszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2730b-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="2730b-158">Válassza az **Aktuális készlet** elemet.</span><span class="sxs-lookup"><span data-stu-id="2730b-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="2730b-159">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="2730b-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2730b-160">Például szűrjön az **1** értékre a **Telephely** mezőben.</span><span class="sxs-lookup"><span data-stu-id="2730b-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="2730b-161">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="2730b-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="2730b-162">Ellenőrizze, hogy az **Összes rendelkezésre álló** mező értéke **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="2730b-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="2730b-163">Mentse a feladatrögzítést az LCS-ben a BPM-tárba, majd szinkronizálja az Azure DevOps rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="2730b-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="2730b-164">Adja hozzá a tesztesetet a tesztelési tervhez, és töltse be a tesztesetet a RSAT-be.</span><span class="sxs-lookup"><span data-stu-id="2730b-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="2730b-165">Nyissa meg az Excel-paraméterfájlt.</span><span class="sxs-lookup"><span data-stu-id="2730b-165">Open the Excel parameter file.</span></span> <span data-ttu-id="2730b-166">Az **InventOnhandItem** lapon látható az **InventOnhandItem ellenőrzése** szakasz, amelyben szerepel egy **Operátor** mező.</span><span class="sxs-lookup"><span data-stu-id="2730b-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Operátor mező](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="2730b-168">Ha ellenőrizni szeretné, hogy az aktuális készlet mindig nagyobb, mint 0, akkor módosítsa az **Érték** mező értékét **411**-ről **0** értékre, és az **Operátor** mező értékét egyenlőségjelről (**=**) a nagyobb mint jelre (**\>**).</span><span class="sxs-lookup"><span data-stu-id="2730b-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Az Érték és az Operátor mező értéke megváltozott](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="2730b-170">Mentse és zárja be az Excel-paraméterfájlt.</span><span class="sxs-lookup"><span data-stu-id="2730b-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="2730b-171">A **Feltöltés** gombra kattintva mentheti a módosításokat az Azure DevOps rendszerbe, amelyeket az Excel-paraméterfájlban tett.</span><span class="sxs-lookup"><span data-stu-id="2730b-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="2730b-172">Ha most a megadott cikk **Összes rendelkezésre álló** mezője értéke meghaladja a 0 (nulla) értéket, akkor a tesztek sikeresek lesznek, függetlenül a tényleges aktuális készlet értékétől.</span><span class="sxs-lookup"><span data-stu-id="2730b-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="2730b-173">Generátornaplók</span><span class="sxs-lookup"><span data-stu-id="2730b-173">Generator logs</span></span>

<span data-ttu-id="2730b-174">Ez a funkció létrehoz egy mappát, amely a futtatott tesztesetek naplóit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2730b-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="2730b-175">A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elemet **hamis** értékről **igaz** értékre.</span><span class="sxs-lookup"><span data-stu-id="2730b-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="2730b-176">A tesztek futtatása után a fájlok a **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs** helyen találhatók.</span><span class="sxs-lookup"><span data-stu-id="2730b-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![GeneratorLogs mappa](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="2730b-178">Ha már léteznek tesztesetek, mielőtt a .config fájlban megváltoztatta a értéket, akkor a naplók nem jönnek létre azokhoz a tesztesetekhez addig, amíg nem hoz létre új teszt-végrehajtási fájlokat.</span><span class="sxs-lookup"><span data-stu-id="2730b-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Csak tesztvégrehajtási fájlok létrehozása parancs az Új menüben](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="2730b-180">Pillanatkép</span><span class="sxs-lookup"><span data-stu-id="2730b-180">Snapshot</span></span>

<span data-ttu-id="2730b-181">Ez a funkció képernyőképeket készít a feladatrögzítés során végrehajtott lépésekről.</span><span class="sxs-lookup"><span data-stu-id="2730b-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="2730b-182">A funkció használatához nyissa meg a **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** fájlt az RSAT telepítési mappájából (például: **C:\\Program Files (x86)\\Regression Suite Automation Tool**), és módosítsa az alábbi elem értékét **hamis** értékről **igaz** értékre.</span><span class="sxs-lookup"><span data-stu-id="2730b-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="2730b-183">A **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback** helyen a program külön mappát hoz létre mindegyik futó tesztesethez.</span><span class="sxs-lookup"><span data-stu-id="2730b-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Pillanatkép mappa a tesztesethez](./media/use_rsa_tool_12.png)

<span data-ttu-id="2730b-185">Ezekben a mappákban megtalálhatja azokat a lépések pillanatképeit, amelyeket a tesztesetek futtatásakor végrehajtott.</span><span class="sxs-lookup"><span data-stu-id="2730b-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Pillanatfelvétel-fájlok](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="2730b-187">Hozzárendelés</span><span class="sxs-lookup"><span data-stu-id="2730b-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="2730b-188">Eset</span><span class="sxs-lookup"><span data-stu-id="2730b-188">Scenario</span></span>

1. <span data-ttu-id="2730b-189">A termék tervezője létrehoz egy új kiadott terméket.</span><span class="sxs-lookup"><span data-stu-id="2730b-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="2730b-190">A termelési vezető kezdeményez egy termelési rendelést, hogy a készlet szintje két darabra növekedjen.</span><span class="sxs-lookup"><span data-stu-id="2730b-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="2730b-191">A gyártás elindítja és befejezi a termelési rendelést, és ellenőrzi, hogy a készleten lévő mennyiség két darab.</span><span class="sxs-lookup"><span data-stu-id="2730b-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="2730b-192">Az értékesítési csoport rendelést kap négy darabra az új termékből.</span><span class="sxs-lookup"><span data-stu-id="2730b-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="2730b-193">Ezért az értékesítési csoport frissíti a nettó szükségletet a dinamikus terven keresztül.</span><span class="sxs-lookup"><span data-stu-id="2730b-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="2730b-194">Mivel nem áll rendelkezésre további kapacitás, az alapértelmezett rendelési irányelv beállítása „vásárlás gyártás helyett”.</span><span class="sxs-lookup"><span data-stu-id="2730b-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="2730b-195">Így létrejön egy tervezett beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="2730b-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="2730b-196">A vevő hozzáadja a szállítót, megerősíti a tervezett beszerzési rendelést, majd megerősíti a beszerzési rendelést.</span><span class="sxs-lookup"><span data-stu-id="2730b-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="2730b-197">Amikor a megvásárolt áruk megérkeznek az üzletbe, az üzlet operátora megkeresi a kapcsolódó beszerzési rendelést, és bevételezi az árukat.</span><span class="sxs-lookup"><span data-stu-id="2730b-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="2730b-198">Mivel a rendelést már befejeződött, az árukat az értékesítési rendeléshez lehet kitárolni és csomagolni.</span><span class="sxs-lookup"><span data-stu-id="2730b-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="2730b-199">A pénzügy felad egy beszerzési számlát és egy értékesítési számlát.</span><span class="sxs-lookup"><span data-stu-id="2730b-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="2730b-200">A következő ábra bemutatja az adott eset folyamatát.</span><span class="sxs-lookup"><span data-stu-id="2730b-200">The following illustration shows the flow for this scenario.</span></span>

![A bemutató eset folyamata](./media/use_rsa_tool_14.png)

<span data-ttu-id="2730b-202">A következő ábra bemutatja az adott eset üzleti folyamatait RSAT-ban.</span><span class="sxs-lookup"><span data-stu-id="2730b-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![A bemutató eset üzleti folyamatai](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="2730b-204">Stratégia – Kulcsfontosságú tanulási pontok</span><span class="sxs-lookup"><span data-stu-id="2730b-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="2730b-205">Adat</span><span class="sxs-lookup"><span data-stu-id="2730b-205">Data</span></span>

- <span data-ttu-id="2730b-206">Győződjön meg róla, hogy rendelkezik reprezentatív adatmennyiséggel (termelési/arany konfigurációs adatok másolata és áttelepített adatok).</span><span class="sxs-lookup"><span data-stu-id="2730b-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="2730b-207">Amikor a feladatrögzítőn keresztül új adatokat hoz létre, olyan tesztneveket hozzon létre, amelyek nem ütköznek a meglévő nevekkel (például használjon **RSATxxx** előtagot).</span><span class="sxs-lookup"><span data-stu-id="2730b-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="2730b-208">Az Azure Időponthoz kötött visszaállítás használatával futtassa újra a teszteket a nem 1. szintű környezetekben.</span><span class="sxs-lookup"><span data-stu-id="2730b-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="2730b-209">Annak ellenére, hogy a **RANDOM** és **NOW** Excel-funkciók segítségével egyedi kombinációt generálhat, az erőfeszítés jelentősen magas.</span><span class="sxs-lookup"><span data-stu-id="2730b-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="2730b-210">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="2730b-210">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="2730b-211">Feladatrögzítő</span><span class="sxs-lookup"><span data-stu-id="2730b-211">Task recorder</span></span>

- <span data-ttu-id="2730b-212">Forgatókönyvek meghatározása a rögzítés megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="2730b-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="2730b-213">A jól kezelt projekt előre meghatározott teszt-forgatókönyveket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="2730b-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="2730b-214">Egy teszteset létrehozásakor vegye figyelembe, hogy mennyire kiszámítható a tesztesetek kimenete.</span><span class="sxs-lookup"><span data-stu-id="2730b-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="2730b-215">Ossza fel a rögzítéseket, ha különböző szerepkörök hajtják őket végre, vagy ha várakozási idő van, vagy külső esemény történik a következő lépés előtt.</span><span class="sxs-lookup"><span data-stu-id="2730b-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="2730b-216">Ne válassza ki listákban szereplő értékeket.</span><span class="sxs-lookup"><span data-stu-id="2730b-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="2730b-217">Ehelyett használjon szöveges formátumokat, mint **FIFO**, **AudioRM**, és **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="2730b-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="2730b-218">Ha listából választ, az érték listában elfoglalt pozícióját rögzíti, nem magát az értéket.</span><span class="sxs-lookup"><span data-stu-id="2730b-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="2730b-219">Ha elemeket adnak hozzá az adott listához, az adott érték pozíciója megváltozhat.</span><span class="sxs-lookup"><span data-stu-id="2730b-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="2730b-220">Emiatt a rögzítés más paramétert fog használni, és ez a többi forgatókönyvet is érintheti.</span><span class="sxs-lookup"><span data-stu-id="2730b-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="2730b-221">Gondoljon a többfelhasználós viselkedésre is.</span><span class="sxs-lookup"><span data-stu-id="2730b-221">Think about multi-user behavior.</span></span> <span data-ttu-id="2730b-222">Például ne feltételezze, hogy mindig az újonnan létrehozott értékesítési rendelést jelöli ki automatikusan a rendszer.</span><span class="sxs-lookup"><span data-stu-id="2730b-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="2730b-223">Ehelyett mindig használjon szűrőket a helyes rendelés megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="2730b-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="2730b-224">A Feladatrögzítő Másolás funkciójával mentse el az újonnan létrehozott termék nevét, így használhatja láncolt tesztesetekben.</span><span class="sxs-lookup"><span data-stu-id="2730b-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="2730b-225">A Feladatrögzítő Ellenőrzés funkciójával határozzon meg ellenőrzési pontokat, amelyek ellenőrzik, hogy a lépések megfelelően futottak le.</span><span class="sxs-lookup"><span data-stu-id="2730b-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="2730b-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="2730b-226">RSAT</span></span>

- <span data-ttu-id="2730b-227">Ha egy másik vállalatnál szeretné futtatni a tesztet, módosíthatja a vállalatot az Excel-paraméterfájl **Általános** lapján.</span><span class="sxs-lookup"><span data-stu-id="2730b-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="2730b-228">Győződjön meg róla, hogy a beállítások és az adatok elérhetők az újonnan kiválasztott vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="2730b-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="2730b-229">A tesztfelhasználót az Excel-paraméterfájl **általános** lapján lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="2730b-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="2730b-230">Adja meg annak a felhasználónak az e-mail-azonosítóját, aki futtatja a tesztesetet.</span><span class="sxs-lookup"><span data-stu-id="2730b-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="2730b-231">Ily módon a teszteset a megadott felhasználó biztonsági engedélyeinek használatával futtatható.</span><span class="sxs-lookup"><span data-stu-id="2730b-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="2730b-232">Ha szeretne várni a teszt elindítása előtt, akkor az Excel-paraméterfájl **Általános** lapján megadhat egy szünetet.</span><span class="sxs-lookup"><span data-stu-id="2730b-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="2730b-233">Ez a szünet kötegelt feladatban is használható (például akkor, ha egy munkafolyamatot a következő lépés végrehajtása előtt futtatni kell.)</span><span class="sxs-lookup"><span data-stu-id="2730b-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="2730b-234">Speciális parancsfájlkezelés</span><span class="sxs-lookup"><span data-stu-id="2730b-234">Advanced scripting</span></span>

### <a name="command-line"></a><span data-ttu-id="2730b-235">Parancssor</span><span class="sxs-lookup"><span data-stu-id="2730b-235">Command line</span></span>

<span data-ttu-id="2730b-236">Az RSAT-ot a **Parancssor** ablakból is be lehet hívni.</span><span class="sxs-lookup"><span data-stu-id="2730b-236">RSAT can be called from a **Command Prompt** window.</span></span>

> [!NOTE]
> <span data-ttu-id="2730b-237">Győződjön meg róla, hogy a **TestRoot** környezeti változó az RSAT telepítési útvonalára van állítva.</span><span class="sxs-lookup"><span data-stu-id="2730b-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="2730b-238">(Microsoft Windows rendszerben nyissa meg a **Vezérlőpult** elemet, válassza a **Rendszer és biztonság \> Rendszer \> Speciális rendszerbeállítások** menüpontot, majd válassza a **Környezet változók** lehetőséget.)</span><span class="sxs-lookup"><span data-stu-id="2730b-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="2730b-239">Nyissa meg a **Parancssor** ablakot rendszergazdaként.</span><span class="sxs-lookup"><span data-stu-id="2730b-239">Open a **Command Prompt** window as an admin.</span></span>
2. <span data-ttu-id="2730b-240">Futtassa az eszközt a telepítési könyvtárból.</span><span class="sxs-lookup"><span data-stu-id="2730b-240">Run the tool from the installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="2730b-241">Listázza az összes parancsot.</span><span class="sxs-lookup"><span data-stu-id="2730b-241">List all commands.</span></span>

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a><span data-ttu-id="2730b-242">Windows PowerShell-példák</span><span class="sxs-lookup"><span data-stu-id="2730b-242">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="2730b-243">Teszteset futtatása egy hurokban</span><span class="sxs-lookup"><span data-stu-id="2730b-243">Run a test case in a loop</span></span>

<span data-ttu-id="2730b-244">Van egy tesztparancsfájl, amely új vevőt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="2730b-244">You have a test script that creates a new customer.</span></span> <span data-ttu-id="2730b-245">A parancsfájlkezeléssel ezt a tesztesetet egy hurokban futtathatja, ha minden egyes iteráció futtatása előtt a következő adatokat véletlenszerűvé teszi:</span><span class="sxs-lookup"><span data-stu-id="2730b-245">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="2730b-246">Vevő azonosítója</span><span class="sxs-lookup"><span data-stu-id="2730b-246">Customer ID</span></span>
- <span data-ttu-id="2730b-247">Vevő neve</span><span class="sxs-lookup"><span data-stu-id="2730b-247">Customer name</span></span>
- <span data-ttu-id="2730b-248">Vevő címe</span><span class="sxs-lookup"><span data-stu-id="2730b-248">Customer address</span></span>

<span data-ttu-id="2730b-249">Az ügyfélazonosító formátuma a következő lesz: *ATCUS\<number\>*, ahol \<number\> egy érték **000000001** és **999999999** között.</span><span class="sxs-lookup"><span data-stu-id="2730b-249">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="2730b-250">A következő példában a program egy paramétert, az **indítás** paramétert használja az először használt szám meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="2730b-250">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="2730b-251">Egy második paramétert (**nr**) a létrehozni kívánt ügyfelek számának meghatározására használ.</span><span class="sxs-lookup"><span data-stu-id="2730b-251">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="2730b-252">Minden iteráció esetében az Excel-paraméterfájl paraméterei egy UpdateCustomer-funkcióval változtathatók.</span><span class="sxs-lookup"><span data-stu-id="2730b-252">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="2730b-253">Ezt követően a RSAT parancssor lehívása RunTestCase-funkcióban történik.</span><span class="sxs-lookup"><span data-stu-id="2730b-253">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="2730b-254">Nyissa meg a Microsoft Windows PowerShell integrált parancsfájl-kezelési környezetet (ISE) rendszergazdai módban, majd illessze be az alábbi kódot az **Untitled1.ps1** elnevezésű ablakba.</span><span class="sxs-lookup"><span data-stu-id="2730b-254">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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
$excelFilename = "full path to excel file parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="2730b-255">Parancsfájl futtatása, amely a Microsoft Dynamics 365 adataitól függ</span><span class="sxs-lookup"><span data-stu-id="2730b-255">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="2730b-256">A következő példa egy Open Data protokoll (OData) hívással keresi meg a beszerzési rendelések rendelési állapotát.</span><span class="sxs-lookup"><span data-stu-id="2730b-256">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="2730b-257">Ha az állapot nem **számlázott**, akkor például lehívhat egy RSAT-tesztet, amely feladja a számlát.</span><span class="sxs-lookup"><span data-stu-id="2730b-257">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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
