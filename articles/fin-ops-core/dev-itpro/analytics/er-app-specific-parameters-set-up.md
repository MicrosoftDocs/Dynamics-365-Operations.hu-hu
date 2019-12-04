---
title: Az ER-formátum paramétereinek beállítása jogi személyenként
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy Elektronikus jelentéskészítési (ER) formátum paramétereit jogi személyenként.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 9c5884bba494d2dd44f9204667144402a88ddec8
ms.sourcegitcommit: d6196d83c7b9166ddb4fe43a91e6bd0ad9da2099
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2019
ms.locfileid: "2694338"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a><span data-ttu-id="5bd5b-103">Az ER-formátum paramétereinek beállítása jogi személyenként</span><span class="sxs-lookup"><span data-stu-id="5bd5b-103">Set up the parameters of an ER format per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="5bd5b-104">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="5bd5b-104">Prerequisites</span></span>

<span data-ttu-id="5bd5b-105">Ezeknek a lépéseknek a végrehajtásához először végre kell hajtania az [ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md) témában megadott lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-105">To complete these steps, you must first complete the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span>

<span data-ttu-id="5bd5b-106">A jelen témakörben szereplő példák végrehajtásához hozzáféréssel kell rendelkeznie a Microsoft Dynamics 365 Finance (Finance) modulnál a következő szerepkörök egyikéhez:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-106">To complete the examples in this topic, you must have access to Microsoft Dynamics 365 Finance (Finance) for one of the following roles:</span></span>

- <span data-ttu-id="5bd5b-107">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="5bd5b-107">Electronic reporting developer</span></span>
- <span data-ttu-id="5bd5b-108">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="5bd5b-108">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="5bd5b-109">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="5bd5b-109">System administrator</span></span>

## <a name="import-er-configurations"></a><span data-ttu-id="5bd5b-110">ER-konfigurációk importálása</span><span class="sxs-lookup"><span data-stu-id="5bd5b-110">Import ER configurations</span></span>

1.  <span data-ttu-id="5bd5b-111">Jelentkezzen be a környezetébe.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-111">Sign in to your environment.</span></span>
2.  <span data-ttu-id="5bd5b-112">Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés**elemet.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-112">On the default dashboard, select **Electronic reporting**.</span></span>
3.  <span data-ttu-id="5bd5b-113">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-113">Select **Reporting configurations**.</span></span>
4.  <span data-ttu-id="5bd5b-114">A Finance aktuális példányába importálja a Regulatory Configuration Service (RCS) alkalmazásból az [ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md) témakörben leírt lépések végrehajtása során exportált konfigurációkat.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-114">Import, into the current instance of Finance, the configurations that you exported from Regulatory Configuration Services (RCS) while you were completing the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span> <span data-ttu-id="5bd5b-115">Hajtsa végre az alábbi lépéseket minden egyes Elektronikus jelentéskészítési (ER) konfigurációjában, a következő sorrendben: adatmodell, modell-leképezés és formátumok.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-115">Follow these steps for each Electronic reporting (ER) configuration, in the following order: data model, model mapping, and formats.</span></span>

    1. <span data-ttu-id="5bd5b-116">Válassza az **Exchange \> Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-116">Select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="5bd5b-117">A **Tallózás** gombra kattintva válassza ki az XML-formátumú fájlt a szükséges ER-konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-117">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="5bd5b-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-118">Select **OK**.</span></span>
    
    <span data-ttu-id="5bd5b-119">A következő ábra bemutatja azokat a konfigurációkat, amelyekkel a befejezést követően rendelkeznie kell.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-119">The following illustration shows the configurations that you must have when you've finished.</span></span>

    ![ER-konfigurációk oldal](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a><span data-ttu-id="5bd5b-121">Paraméterek beállítása a DEMF vállalathoz</span><span class="sxs-lookup"><span data-stu-id="5bd5b-121">Set up parameters for the DEMF company</span></span>

<span data-ttu-id="5bd5b-122">Az ER keretrendszerrel beállíthatja az alkalmazásra jellemző paramétereket egy ER formátumhoz.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-122">You can use the ER framework to set up application-specific parameters for an ER format.</span></span>

1.  <span data-ttu-id="5bd5b-123">Válassza a **DEMF** jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-123">Select the **DEMF** legal entity.</span></span>
2.  <span data-ttu-id="5bd5b-124">A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-124">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
3.  <span data-ttu-id="5bd5b-125">A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-125">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>

    ![ER alkalmazásspecifikus paramétereinek oldala](./media/GER-AppSpecParms-LookupForm.PNG)
    
    <span data-ttu-id="5bd5b-127">Az **alkalmazás-specifikus paraméterek** oldalon beállíthatja a **LE adatok keresésének tanulási formátuma** formátum **Választó** adatforrásra vonarkotó szabályokat.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-127">On the **Application specific parameters** page, you can configure the rules for the **Selector** data source of the **Format to learn how to lookup LE data** format.</span></span>
    
    <span data-ttu-id="5bd5b-128">Ha az alap ER formátum számos **Keresés** típusú adatforrást tartalmaz, akkor az adatforrás szabályainak konfigurálása előtt ki kell választania a kívánt adatforrást a **Keresések** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-128">If the base ER format will contain several data sources of the **Lookup** type, you must select the desired data source on the **Lookups** FastTab before you can start to configure the set of rules for the data source.</span></span>
    
    <span data-ttu-id="5bd5b-129">Minden egyes adatforrás esetében külön szabályokat állíthat be a kiválasztott ER-formátum mindegyik verziójához.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-129">For each data source, you can configure separate rules for each version of the selected ER format.</span></span>
    
    <span data-ttu-id="5bd5b-130">Az összes keresési adatforrásra vonatkozó teljes szabálycsoport, amely elérhető az alap ER formátum kiválasztott verziójában, alkotja az ER formátum alkalmazásspecifikus paramétereit.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-130">The whole set of rules for all lookup data sources that are available in the selected version of the base ER format makes up the application-specific parameters for the ER format.</span></span>

4.  <span data-ttu-id="5bd5b-131">Válassza az ER formátum **1.1.1** verzióját.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-131">Select version **1.1.1** of the ER format.</span></span>
5.  <span data-ttu-id="5bd5b-132">Válassza a **Feltételek** gyorslap **Hozzáadás** elemét.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-132">On the **Conditions** FastTab, select **Add**.</span></span>
6.  <span data-ttu-id="5bd5b-133">Az új rekord **Kód** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-133">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="5bd5b-134">A keresés megjeleníti a kiválasztható adókódok listáját.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-134">The lookup presents the list of tax codes for selection.</span></span> <span data-ttu-id="5bd5b-135">Ezt a listát visszaadja a **Model.Data.Tax** adatforrás, amelyet az adott ER formátumban konfigurált.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-135">This list is returned by the **Model.Data.Tax** data source that has been configured in the base ER format.</span></span> <span data-ttu-id="5bd5b-136">Mivel az adatforrás tartalmazza a **Név** mezőt, a keresésben megjelenik az egyes adókódok neve.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-136">Because this data source contains the **Name** field, the name of each tax code appears in the lookup.</span></span>

    ![ER alkalmazásspecifikus paramétereinek oldala](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  <span data-ttu-id="5bd5b-138">Válassza ki a **VAT19** áfakódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-138">Select the **VAT19** tax code.</span></span>
8.  <span data-ttu-id="5bd5b-139">Az új rekord **Keresési eredmény** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-139">In the **Lookup result** field of the new record, select the drop-down arrow to open the lookup.</span></span> <span data-ttu-id="5bd5b-140">A keresési lista felsorolja azokat a kiválasztható értékeket a TaxationLevel formátumfelsorolásához.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-140">The lookup presents the list of values for the TaxationLevel format enumeration for selection.</span></span>

    <span data-ttu-id="5bd5b-141">Ne feledje, hogy ha a német a felhasználó preferált nyelve, amellyel be van jelentkezve, kakor a keresés értékeinek címkéi németül jelennek meg, feltéve, ha az alap ER formátumban ezeket lefordították.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-141">Note that, if German is selected as the preferred language of the user that you're signed in as, the labels of the values in the lookup will be in German, provided that they have been translated in the base ER format.</span></span> <span data-ttu-id="5bd5b-142">Ezenkívül ha a keresési adatforrás címkéjét már lefordították, akkor a címke a felhasználó preferált nyelvén jelenik meg a **Keresések** lapon.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-142">Additionally, if the label of a lookup data source has been translated, that label will appear in the user's preferred language on the **Lookups** tab.</span></span>

    ![ER alkalmazásspecifikus paramétereinek oldala](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  <span data-ttu-id="5bd5b-144">Válassza a **Rendes adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-144">Select the **Regular taxation** value.</span></span>

    <span data-ttu-id="5bd5b-145">A rekord hozzáadásával megadhatja a következő szabályt: Valahányszor a **választó** keresési adatforrást kérik le, és a **VAT19** adókódot argumentumként adja át a rendszer, a kért adózási szintként a **Rendes adózás** eredményt adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-145">By adding this record, you define the following rule: Whenever the **Selector** lookup data source is requested, and the **VAT19** tax code is passed as an argument, **Regular taxation** will be returned as the requested taxation level.</span></span>

10. <span data-ttu-id="5bd5b-146">Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-146">Select **Add**, and then follow these steps:</span></span>

    1. <span data-ttu-id="5bd5b-147">A **Kód** mezőben válassza ki az **InVAT19** adókódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-147">In the **Code** field, select the **InVAT19** tax code.</span></span>
    2. <span data-ttu-id="5bd5b-148">A **keresési eredmény** mezőben válassza ki a **Rendes adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-148">In the **Lookup result** field, select the **Regular taxation** value.</span></span>
    
11. <span data-ttu-id="5bd5b-149">Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-149">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="5bd5b-150">A **Kód** mezőben válassza ki az **VAT7** adókódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-150">In the **Code** field, select the **VAT7** tax code.</span></span>
    2. <span data-ttu-id="5bd5b-151">A **keresési eredmény** mezőben válassza ki a **Csökkentett adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-151">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
12. <span data-ttu-id="5bd5b-152">Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-152">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="5bd5b-153">A **Kód** mezőben válassza ki az **InVAT7** adókódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-153">In the **Code** field, select the **InVAT7** tax code.</span></span>
    2. <span data-ttu-id="5bd5b-154">A **keresési eredmény** mezőben válassza ki a **Csökkentett adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-154">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
13. <span data-ttu-id="5bd5b-155">Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-155">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="5bd5b-156">A **Kód** mezőben válassza ki az **THIRD** adókódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-156">In the **Code** field, select the **THIRD** tax code.</span></span>
    2. <span data-ttu-id="5bd5b-157">A **keresési eredmény** mezőben válassza ki a **Nincs adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-157">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
14. <span data-ttu-id="5bd5b-158">Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-158">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="5bd5b-159">A **Kód** mezőben válassza ki az **InVAT0** adókódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-159">In the **Code** field, select the **InVAT0** tax code.</span></span>
    2. <span data-ttu-id="5bd5b-160">A **keresési eredmény** mezőben válassza ki a **Nincs adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-160">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
15. <span data-ttu-id="5bd5b-161">Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-161">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="5bd5b-162">A **Kód** mezőben válassza a **\*Nem üres\*** beállítást.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-162">In the **Code** field, select the **\*Not blank\*** option.</span></span>
    2. <span data-ttu-id="5bd5b-163">A **keresési eredmény** mezőben válassza ki az **Egyéb** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-163">In the **Lookup result** field, select the **Other** value.</span></span>
    
    <span data-ttu-id="5bd5b-164">Az utolsó rekord hozzáadásával megadhatja a következő szabályt: Valahányszor az arugmentumként átadott adókód nem teljesíti a korábbi szabályok egyikét sem, a keresési adatforrás **Egyéb** értéket ad vissza a kért adózási szintként.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-164">By adding this last record, you define the following rule: Whenever the tax code that is passed as an argument doesn't satisfy any of the previous rules, the lookup data source will return **Other** as the requested taxation level.</span></span>

    ![ER alkalmazásspecifikus paramétereinek oldala](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. <span data-ttu-id="5bd5b-166">Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-166">In the **State** field, select **Completed**.</span></span>

    <span data-ttu-id="5bd5b-167">A **Befejeződött** vagy **Megosztott**állapotú ER formátumverzió futtatásakor a szabálycsoportnak **Befejeződött** állapotban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-167">When you run an ER format version that has a status of either **Completed** or **Shared**, this set of rules must be in the **Completed** state.</span></span> <span data-ttu-id="5bd5b-168">Ellenkező esetben a rendszer megszakítja az alap ER formátum végrehajtását, amikor a formátum adatokat próbál ebből a szabálycsoportból betölteni a **Választó** keresési adatforrás futtatásakor.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-168">Otherwise, execution of the base ER format will be interrupted when the format tries to load data from this set of rules while the **Selector** lookup data source is being run.</span></span>
    
    <span data-ttu-id="5bd5b-169">A **Tervezet**állapotú ER formátumú verzió futtatásakor az alap ER formátum hozzáférhet ehhez a szabálycsoporthoz állapottól függetlenül.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-169">When you run an ER format version that has a status of **Draft**, the base ER format can access this set of rules, regardless of its state.</span></span>
    
17. <span data-ttu-id="5bd5b-170">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-170">Select **Save**.</span></span>
18. <span data-ttu-id="5bd5b-171">Zárja be az **Alkalmazásspecifikus paraméterek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-171">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-demf-company"></a><span data-ttu-id="5bd5b-172">Az ER formátum futtatása a DEMF vállalatban</span><span class="sxs-lookup"><span data-stu-id="5bd5b-172">Run the ER format in the DEMF company</span></span>

1.  <span data-ttu-id="5bd5b-173">A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-173">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="5bd5b-174">A Műveleti ablaktáblán kattintson a **Futtatás** elemre.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-174">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="5bd5b-175">A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-175">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="5bd5b-176">Töltse le a létrehozott kimutatást, és tárolja helyben.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-176">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="5bd5b-177">A létrehozott kimutatásban figyelje meg, hogy az **InVAT7** áfakód összefoglalása a **Csökkentett** szintre került, és a **VAT19** és a **InVA19** adókódok összesítése a **Rendes** szintre került.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-177">In the generated statement, notice that the summary of the **InVAT7** tax code has been put on the **Reduced** level, and the summaries of the **VAT19** and **InVA19** tax codes have been put on the **Regular** level.</span></span> <span data-ttu-id="5bd5b-178">Ezt a viselkedést a jogi személytől függő szabálycsoportban található konfiguráció határozza meg.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-178">This behavior is determined by the configuration in the legal entity–dependent set of rules.</span></span>
    
5.  <span data-ttu-id="5bd5b-179">Ugrás az **Adó \> Közvetett adók \> Áfa \> Áfakódok** pontra.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-179">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**.</span></span>
6.  <span data-ttu-id="5bd5b-180">Válassza ki a **InVAT7** áfakódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-180">Select the **InVAT7** tax code.</span></span>
7.  <span data-ttu-id="5bd5b-181">A műveleti ablaktáblán az **Áfakód** lapon a **Lekérdezések** csoportban válassza a **Feladott áfa** elemet, ahol információkat tekinthet meg az adó értékével és az adókódonként alkalmazott adókulccsal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-181">On the Action Pane, on the **Sales tax code** tab, in the **Inquiries** group, select **Posted sales tax** to view information about the tax value and applied tax rate per tax code.</span></span>

    ![Feladott áfa oldal](./media/GER-AppSpecParms-Statement.PNG)

8.  <span data-ttu-id="5bd5b-183">Zárja be a Feladott áfa oldalt.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-183">Close the Posted sales tax page.</span></span>

## <a name="set-up-parameters-for-the-usmf-company"></a><span data-ttu-id="5bd5b-184">Paraméterek beállítása a USMF vállalathoz</span><span class="sxs-lookup"><span data-stu-id="5bd5b-184">Set up parameters for the USMF company</span></span>

1.  <span data-ttu-id="5bd5b-185">Válassza a **USMF** jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-185">Select the **USMF** legal entity.</span></span>
2.  <span data-ttu-id="5bd5b-186">Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-186">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3.  <span data-ttu-id="5bd5b-187">A konfigurációk fájában bontsa ki a **Modell paraméterezett hívások tanulásához** elemet, bontsa ki a **Formátum paraméterezett hívások tanulásához** elemet, és válassza a **LE adatok keresésének tanulási formátuma** formátumot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-187">In the configurations tree, expand the **Model to learn parameterized calls** item, expand the **Format to learn parameterized calls** item, and select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="5bd5b-188">A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-188">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="5bd5b-189">Válassza a kiválasztott ER formátum **1.1.1** verzióját.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-189">Select version **1.1.1** of the selected ER format.</span></span>
6.  <span data-ttu-id="5bd5b-190">Válassza a **Feltételek** gyorslap **Hozzáadás** elemét.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-190">On the **Conditions** FastTab, select **Add**.</span></span>
7.  <span data-ttu-id="5bd5b-191">Az új rekord **Kód** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-191">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="5bd5b-192">A keresés megjeleníti az **USMF** vállalati adóhoz tartozó választható adókódok listáját.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-192">The lookup now presents the list of tax codes for the **USMF** company tax for selection.</span></span>

    ![ER alkalmazásspecifikus paramétereinek oldala](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  <span data-ttu-id="5bd5b-194">Válassza ki a **EXEMPT** áfakódot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-194">Select the **EXEMPT** tax code.</span></span>
9.  <span data-ttu-id="5bd5b-195">Az új rekord **keresési eredmény** mezőjében válassza ki a **Nincs adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-195">In the **Lookup resul**t field of the new record, select the **No taxation** value.</span></span>
10. <span data-ttu-id="5bd5b-196">Válassza ismét a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-196">Select **Add** again.</span></span>
11. <span data-ttu-id="5bd5b-197">Az új rekord **Kód** mezőjében válassza a **\*Nem üres\*** beállítást.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-197">In the **Code** field of the new record, select the **\*Not blank\*** option.</span></span>
12. <span data-ttu-id="5bd5b-198">Az új rekord **keresési eredmény** mezőjében válassza ki a **Rendes adózás** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-198">In the **Lookup result** field of the new record, select the **Regular taxation** value.</span></span>
13. <span data-ttu-id="5bd5b-199">Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-199">In the **State** field, select **Completed**.</span></span>
14. <span data-ttu-id="5bd5b-200">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-200">Select **Save**.</span></span>

    ![ER alkalmazásspecifikus paramétereinek oldala](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. <span data-ttu-id="5bd5b-202">Zárja be az **Alkalmazásspecifikus paraméterek** oldalt.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-202">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-usmf-company"></a><span data-ttu-id="5bd5b-203">Az ER formátum futtatása a USMF vállalatban</span><span class="sxs-lookup"><span data-stu-id="5bd5b-203">Run the ER format in the USMF company</span></span>

1.  <span data-ttu-id="5bd5b-204">A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-204">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="5bd5b-205">A Műveleti ablaktáblán kattintson a **Futtatás** elemre.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-205">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="5bd5b-206">A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-206">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="5bd5b-207">Töltse le a létrehozott kimutatást, és tárolja helyben.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-207">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="5bd5b-208">A létrejövő kimutatásban figyelje meg, hogy egy másik jogi személyhez ugyanezt az ER formátumot használta fel, de nem végzett módosítást az ER formátumában.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-208">In the generated statement, notice that you've now reused the same ER format for a different legal entity, but without making any adjustments to the ER format.</span></span>

## <a name="reuse-legal-entitydependent-parameters"></a><span data-ttu-id="5bd5b-209">Jogi személytől függő paraméterek újbóli felhasználása</span><span class="sxs-lookup"><span data-stu-id="5bd5b-209">Reuse legal entity–dependent parameters</span></span>

### <a name="export-parameters"></a><span data-ttu-id="5bd5b-210">Exportálási paraméterek</span><span class="sxs-lookup"><span data-stu-id="5bd5b-210">Export parameters</span></span>

1.  <span data-ttu-id="5bd5b-211">Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-211">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2.  <span data-ttu-id="5bd5b-212">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-212">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="5bd5b-213">A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-213">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="5bd5b-214">A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-214">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="5bd5b-215">Válassza az ER formátum **1.1.1** verzióját.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-215">Select version **1.1.1** of the ER format.</span></span>
6.  <span data-ttu-id="5bd5b-216">A műveleti ablaktáblán válassza az **Exportálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-216">On the Action Pane, select **Export**.</span></span>
7.  <span data-ttu-id="5bd5b-217">Töltse le a létrehozott fájlt, és tárolja helyben.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-217">Download the file that is generated and store it locally.</span></span>

    <span data-ttu-id="5bd5b-218">Az alkalmazásfüggő paraméterek megadott készlete már exportálva van XML-fájlként.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-218">The configured set of application-specific parameters has now been exported as an XML file.</span></span>

### <a name="import-parameters"></a><span data-ttu-id="5bd5b-219">Importálási paraméterek</span><span class="sxs-lookup"><span data-stu-id="5bd5b-219">Import parameters</span></span>

1.  <span data-ttu-id="5bd5b-220">Válassza az ER formátum **1.1.2** verzióját.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-220">Select version **1.1.2** of the ER format.</span></span>
2.  <span data-ttu-id="5bd5b-221">A műveleti ablaktáblán válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-221">On the Action Pane, select **Import**.</span></span>
3.  <span data-ttu-id="5bd5b-222">Válassza az **Igen** lehetőséget, ha azt szeretné, hogy felülbírálja a formátum verziójának meglévő alkalmazásfüggő paramétereit.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-222">Select **Yes** to confirm that you want to override the existing application-specific parameters for this format version.</span></span>
4.  <span data-ttu-id="5bd5b-223">A **Tallózás** gombra kattintva megkeresheti a **1.1.1**-es verzió exportált alkalmazásfüggő paramétereit tartalmazó fájlt.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-223">Select **Browse** to find the file that contains the exported application-specific parameters for version **1.1.1**.</span></span>
5.  <span data-ttu-id="5bd5b-224">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-224">Select **OK**.</span></span>

    <span data-ttu-id="5bd5b-225">Az ER-formátum **1.1.2**-es verziójának ugyanolyan alkalmazásfüggő paraméterei vannak, amelyeket eredetileg az **1.1.1**-es verzióhoz konfigurált.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-225">Version **1.1.2** of the ER format now has the same application-specific parameters that you originally configured for version **1.1.1**.</span></span>
    
    <span data-ttu-id="5bd5b-226">Ne feledje, hogy az ER formátum alkalmazásfüggő paraméterei jogi személyektől-függőek.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-226">Note that the application-specific parameters of an ER format are legal entity–dependent.</span></span> <span data-ttu-id="5bd5b-227">Ha egy adott jogi személyre konfigurált alkalmazásspecifikus paramétereket másik jogi személyben szeretné újból használni, exportálnia kell őket, miközben be van jelentkezve az első jogi személybe, majd importálja őket, miután bejelentkezett a másik jogi személybe.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-227">To reuse the application-specific parameters that were configured for one legal entity in a different legal entity, you must export them while you're signed in to the first legal entity and then import them after you sign in to the other legal entity.</span></span>

    <span data-ttu-id="5bd5b-228">Ezzel a módszerrel olyan ER formátumhoz kapcsolódó alkalmazásspecifikus paramétereket is átvihet a Finance másik példányába, amely eredetileg az egyik Finance példányhoz volt konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-228">You can also use this approach to transfer an ER format related application-specific parameters that were originally configured in one instance of Finance to another instance of Finance.</span></span>

    <span data-ttu-id="5bd5b-229">Ne feledje, hogy ha egy ER formátumának adott verziójához alkalmazásfüggő paramétereket konfigurál, és ugyanazon formátum magasabb verziószámát importálja az aktuális Finance példányba, akkor a program nem alkalmazza az importált verzióhoz a meglévő alkalmazásfüggő paramétereket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-229">Be aware that if you configure application-specific parameters for one version of an ER format and import a higher version of the same format into the current Finance instance, the existing application-specific parameters won't be applied for the imported version.</span></span>
    
    <span data-ttu-id="5bd5b-230">Ügyeljen arra is, ha importálásra kiválaszt egy fájlt, akkor az adott fájl alkalmazásspecifikus paramétereinek szerkezetét összeveti az importálásra kijelölt ER formátum kapcsolódó, **Keresés** típusú adatforrásának szerkezetével.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-230">Also be aware that, when you select a file for import, the structure of the application-specific parameters in that file is compared with the structure of the corresponding data source of the **Lookup** type in the ER format that is selected for import.</span></span> <span data-ttu-id="5bd5b-231">Az importálás akkor történik meg, amikor az alkalmazásspecifikus paraméterek szerkezete megfelel a kapcsolódó adatforrás struktúrájának az importáláshoz kiválasztott ER-formátumban.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-231">The import is done when the structure of each application-specific parameter matches the structure of the corresponding data source in the ER format that is selected for import.</span></span> <span data-ttu-id="5bd5b-232">Ha a szerkezetek nem egyeznek, akkor egy figyelmeztető üzenet jelenik meg, amely jelzi, hogy az importálás nem hajtható végre.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-232">If the structures don't match, you receive a warning message that states that the import can't be done.</span></span> <span data-ttu-id="5bd5b-233">Ha kényszeríti az importálást, akkor a program a kijelölt ER formátumra vonatkozó meglévő alkalmazásfüggő paramétereket kitörli, és a kezdetektől fogva újra be kell állítani őket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-233">If you force the import to be done, the existing application-specific parameters for the selected ER format will be cleaned up, and you must set them up from the beginning.</span></span>

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a><span data-ttu-id="5bd5b-234">Az alkalmazásfüggő paraméterek és az ER formátum közötti kapcsolat</span><span class="sxs-lookup"><span data-stu-id="5bd5b-234">Relationship between application-specific parameters and an ER format</span></span>

<span data-ttu-id="5bd5b-235">Az ER formátum és az alkalmazásspecifikus paraméterei közötti kapcsolatot az ER formátum példánytól független egyedi azonosító kódja határozza meg.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-235">The relationship between an ER format and its application-specific parameters is established by the ER format's instance-independent unique identification code.</span></span> <span data-ttu-id="5bd5b-236">Ennélfogva amikor a Finance alkalmazásból eltávolít egy ER-formátumot, a program megtartja az ER formátumhoz konfigurált alkalmazásspecifikus paramétereket a Finance aktuális példányában.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-236">Therefore, when you remove an ER format from Finance, the application-specific parameters that are configured for the ER format are kept in the current instance of Finance.</span></span> <span data-ttu-id="5bd5b-237">Bármikor elérhetők el, ha az alap ER formátumot újra importálják ebbe a Finance példányba.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-237">They can be accessed whenever the base ER format is reimported into this instance of Finance.</span></span>

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a><span data-ttu-id="5bd5b-238">Alkalmazás-specifikus paraméterek elérése az ER keretrendszer használatával</span><span class="sxs-lookup"><span data-stu-id="5bd5b-238">Access application-specific parameters by using the ER framework</span></span>

<span data-ttu-id="5bd5b-239">Az előző példában az ER keretrendszer használatával hozzáfért egy ER formátum alkalmazásspecifikus paramétereihez.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-239">In the preceding example, you have accessed application-specific parameters of an ER format by using the ER framework.</span></span> <span data-ttu-id="5bd5b-240">Ez a megközelítés nem teszi lehetővé a hozzáférés korlátozását egy adott ER-formátum alkalmazásspecifikus paraméterei számára.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-240">This approach doesn't let you restrict access to the application-specific parameters of a specific ER format.</span></span> <span data-ttu-id="5bd5b-241">Ha ilyen korlátozásokat kell alkalmaznia, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-241">If you must apply such restrictions, follow these steps.</span></span> 

1.  <span data-ttu-id="5bd5b-242">Vagy használja újra a meglévő **ERSolutionAppSpecificParametersDesigner** menüelemet, vagy hajtsa végre saját **ERSolutionAppSpecificParametersDesigner** menüelemét.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-242">Either reuse an existing **ERSolutionAppSpecificParametersDesigner** menu item, or implement your own **ERSolutionAppSpecificParametersDesigner** menu item.</span></span>

    ![Visual Studio oldala](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  <span data-ttu-id="5bd5b-244">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="5bd5b-244">Follow one of these steps:</span></span>

    1.  <span data-ttu-id="5bd5b-245">Hozzon létre egy új menüelemgombot, és csatolja a megfelelő rekordhoz az **ERSolutionTable** táblából az **Adatforrás** tulajdonságának **ERSolutionTable** értékre történő beállításával.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-245">Create a new menu item button, and link it to the corresponding record from the **ERSolutionTable** table by setting its **Data Source** property to **ERSolutionTable**.</span></span>
    
        ![Visual Studio oldala](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  <span data-ttu-id="5bd5b-247">Hozzon létre egy egyszerű gombot, és a következő példában bemutatott módon bírálja felül a **Rákattintva** módszert.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-247">Create a simple button, and override the **Clicked** method as shown in the following example.</span></span>
    
        <span data-ttu-id="5bd5b-248">Ennek a módszernek a használatával megadható egy egyedi megoldásazonosító (a **GUID** értékkel meghatározva), amely lehetővé teszi, hogy csak a megadott ER formátum alkalmazásspecifikus paramétereihez és az ebből származtatott leszármazott másolatokhoz férjen hozzá.</span><span class="sxs-lookup"><span data-stu-id="5bd5b-248">By using this approach, you can specify a unique solution ID (defined via the **GUID** value) to allow access to the application-specific parameters of only a specific ER format and descendant copies that have been derived from it.</span></span>
        
        ```
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a><span data-ttu-id="5bd5b-249">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5bd5b-249">Additional resources</span></span>

[<span data-ttu-id="5bd5b-250">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="5bd5b-250">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="5bd5b-251">ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára</span><span class="sxs-lookup"><span data-stu-id="5bd5b-251">Configure ER formats to use parameters that are specified per legal entity</span></span>](er-app-specific-parameters-configure-format.md)
