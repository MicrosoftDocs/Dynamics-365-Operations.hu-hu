---
title: Elektronikus jelentéskészítés speciális képlet-szerkesztő
description: Ez a témakör azt mutatja be, hogyan használható a speciális receptúraszerkesztő kifejezések konfigurálására az elektronikus jelentési (ER) modell hozzárendelési és formátum összetevőiben.
author: NickSelin
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f7f80928e1d3f5d4892f72d4bd2fd09b70a26c1f
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270707"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="2ef93-103">Elektronikus jelentéskészítés speciális képlet-szerkesztő</span><span class="sxs-lookup"><span data-stu-id="2ef93-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ef93-104">Az [Elektronikus jelentéskészítés](general-electronic-reporting.md) [receptúra szerkesztőn](general-electronic-reporting-formula-designer.md) kívül a fejlett elektronikus jelentéskészítési receptúraszerkesztőt is használhatja az elektronikus jelentéskészítési (ER) kifejezések beállításának élményének javítására.</span><span class="sxs-lookup"><span data-stu-id="2ef93-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="2ef93-105">A speciális szerkesztő a [Monaco-szerkesztő által működtetett böngésző-alapú ](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="2ef93-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="2ef93-106">Ez a témakör a leggyakrabban használt speciális szerkesztési funkciókat írja le:</span><span class="sxs-lookup"><span data-stu-id="2ef93-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="2ef93-107">Kód automatikus formázása</span><span class="sxs-lookup"><span data-stu-id="2ef93-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="2ef93-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2ef93-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="2ef93-109">Kódkiegészítés</span><span class="sxs-lookup"><span data-stu-id="2ef93-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="2ef93-110">Kódnavigáció</span><span class="sxs-lookup"><span data-stu-id="2ef93-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="2ef93-111">Kód strukturálása</span><span class="sxs-lookup"><span data-stu-id="2ef93-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="2ef93-112">Keresés és csere</span><span class="sxs-lookup"><span data-stu-id="2ef93-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="2ef93-113">Adatok beillesztése</span><span class="sxs-lookup"><span data-stu-id="2ef93-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="2ef93-114">Szintaxis szerinti színezés</span><span class="sxs-lookup"><span data-stu-id="2ef93-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="2ef93-115"><a name="ActivateAdvEditor">A speciális receptúraszerkesztő aktiválása</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="2ef93-116">A következő lépések végrehajtásával kezdheti el használni Microsoft Dynamics 365 Finance-példányának speciális receptúraszerkesztőjét.</span><span class="sxs-lookup"><span data-stu-id="2ef93-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="2ef93-117">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="2ef93-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="2ef93-118">A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2ef93-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="2ef93-119">A **Felhasználói paraméterek** párbeszédpanel **Végrehajtási nyomkövetés** szakaszában állítsa **A speciális receptúraszerkesztő aktiválása** paramétert **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="2ef93-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="2ef93-120">[![Felhasználói paraméterek párbeszédpanel, Speciális képletszerkesztő paraméter engedélyezése kiemelve](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="2ef93-120">[![User parameters dialog box, Enable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="2ef93-121">Ne feledje, hogy ez a paraméter a felhasználó- és a vállalatspecifikus.</span><span class="sxs-lookup"><span data-stu-id="2ef93-121">Be aware that this parameter is user specific and company specific.</span></span>

<span data-ttu-id="2ef93-122">A Microsoft Dynamics 365 Finance 10.0.19-es verziójától kezdve szabályozható, hogy alapértelmezés szerint milyen ER receptúraszerkesztőt kínálnak.</span><span class="sxs-lookup"><span data-stu-id="2ef93-122">Starting in Microsoft Dynamics 365 Finance version 10.0.19, you can control what ER formula editor is offered by default.</span></span> <span data-ttu-id="2ef93-123">A következő lépések segítségével engedélyezheti a speciális képletszerkesztőt az aktuális Pénzügyi példány összes felhasználója és vállalata számára.</span><span class="sxs-lookup"><span data-stu-id="2ef93-123">Complete the following steps to enable the advanced formula editor for all users and companies of the current Finance instance.</span></span>

1.  <span data-ttu-id="2ef93-124">Nyissa meg a **Funkciókezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="2ef93-124">Open the **Feature management** workspace.</span></span>
2.  <span data-ttu-id="2ef93-125">Keresse meg és válassza ki a listában található **Összes felhasználó alapértelmezettként az ER speciális képletszerkesztő beállítása** funkciót, majd válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2ef93-125">Find and select the feature **Set the ER advanced formula editor as the default one for all users** in the list, and then select **Enable now**.</span></span>
3.  <span data-ttu-id="2ef93-126">Nyissa meg a következőt: **Szervezeti adminisztráció** > **Elektronikus jelentés** > **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="2ef93-126">Go to **Organization administration** > **Electronic reporting** > **Configurations**.</span></span>
4.  <span data-ttu-id="2ef93-127">A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2ef93-127">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
5.  <span data-ttu-id="2ef93-128">A **Felhasználói paraméterek** párbeszédpanelen keresse meg a **Speciális képletszerkesztő letiltása** paramétert, és ellenőrizze, hogy a **Nem** beállítás van-e megadva.</span><span class="sxs-lookup"><span data-stu-id="2ef93-128">In the **User parameters** dialog box, find the **Disable advanced formula editor** parameter and verify that it is set to **No**.</span></span>

<span data-ttu-id="2ef93-129">[![Felhasználói paraméterek párbeszédpanel, Speciális képletszerkesztő paraméter letiltása kiemelve](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span><span class="sxs-lookup"><span data-stu-id="2ef93-129">[![User parameters dialog box, Disable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span></span>

> [!NOTE]
> <span data-ttu-id="2ef93-130">A **Speciális receptúra-szerkesztő engedélyezése** és a **Speciális receptúraszerkesztő letiltása** paraméterértékek minden felhasználónál külön maradnak, és a **Felhasználói paraméterek** párbeszédpanelen jelennek meg, az **ER speciális receptúra-szerkesztő beállítása** alapértelmezettként való beállításának állapotától függően minden felhasználó funkciónál.</span><span class="sxs-lookup"><span data-stu-id="2ef93-130">The values of the parameters **Enable advanced formula editor** and **Disable advanced formula editor** are kept separate for each user and offered on the **User parameters** dialog box depending on the status of the **Set the ER advanced formula editor as the default one for all users** feature.</span></span>

## <a name=""></a><span data-ttu-id="2ef93-131"><a name="Autoformatting">Kód automatikus formázása</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-131"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="2ef93-132">Ha egy összetett kifejezést ír be, amely több kódsorból áll, akkor az új megadott sor behúzása automatikusan az előző sor behúzása alapján történik.</span><span class="sxs-lookup"><span data-stu-id="2ef93-132">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="2ef93-133">Kiválaszthatja a sorokat, és megváltoztathatja a behúzást a **Tab** vagy a **Shift+Tab** megnyomásával.</span><span class="sxs-lookup"><span data-stu-id="2ef93-133">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="2ef93-134">[![ER képletszerkesztő gif megjelenítése sorok kiválasztásával és a behúzás módosításával](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="2ef93-134">[![ER formula editor gif showing selecting lines and changing the indentation](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="2ef93-135">Az automatikus formázás lehetővé teszi a teljes kifejezés megfelelő formázását a további karbantartás megkönnyítésére, valamint a konfigurált logika megértésének egyszerűsítésére.</span><span class="sxs-lookup"><span data-stu-id="2ef93-135">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="2ef93-136"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-136"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="2ef93-137">A szerkesztő a szavak kiegészítését nyújtja, segítve a kifejezés írását és az elgépelés elkerülését.</span><span class="sxs-lookup"><span data-stu-id="2ef93-137">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="2ef93-138">Új szöveg hozzáadásának elkezdése esetén a szerkesztő automatikusan felkínálja a megadott karaktereket tartalmazó funkciókban használható ER-funkciók listáját.</span><span class="sxs-lookup"><span data-stu-id="2ef93-138">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="2ef93-139">A **Ctrl+Szóköz** beírásával a konfigurált kifejezés tetszőleges pontján aktiálható az IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2ef93-139">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="2ef93-140">[![ER receptúraszerkesztő GIF-fájlja, amely az IntelliSense eseményindítót mutatja](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="2ef93-140">[![ER formula editor gif showing triggering IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="2ef93-141"><a name="CodeCompletion">Kódkiegészítés</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-141"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="2ef93-142">A szerkesztő automatikusan elvégzi a kód kiegészítését:</span><span class="sxs-lookup"><span data-stu-id="2ef93-142">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="2ef93-143">Záró zárójel beszúrása a nyitó zárójel beírásakor, a kurzort a zárójelen belül tartva.</span><span class="sxs-lookup"><span data-stu-id="2ef93-143">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="2ef93-144">A második idézőjel szimbólum beszúrása az első beírásakor, a kurzort az idézőjeleken belül tartva.</span><span class="sxs-lookup"><span data-stu-id="2ef93-144">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="2ef93-145">A második dupla idézőjel szimbólum beszúrása az első beírásakor, a kurzort az idézőjeleken belül tartva.</span><span class="sxs-lookup"><span data-stu-id="2ef93-145">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="2ef93-146">[![AZ ER képletszerkesztő gif-fájlja mutatja, hogy a szerkesztő automatikusan biztosítja a kód kiegészítését](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="2ef93-146">[![ER formula editor gif showing the editor automatically providing code completion](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="2ef93-147">Ha kijelöli a begépelt zárójelet, akkor a páros második zárójele automatikusan kiemelődik az általuk támogatott konstrukciót megmutatva.</span><span class="sxs-lookup"><span data-stu-id="2ef93-147">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="2ef93-148"><a name="CodeNavigation">Kódnavigáció</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-148"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="2ef93-149">A kifejezésben a szükséges szimbólumok vagy sorok megtalálhatók úgy, hogy az **Ugrás** parancsot a parancspaletta vagy a helyi menü segítségével adja meg.</span><span class="sxs-lookup"><span data-stu-id="2ef93-149">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="2ef93-150">A **8.** sorra történő ugráshoz például tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="2ef93-150">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="2ef93-151">Nyomja le a **Ctrl+G** billentyűkombinációt adja meg a **8** értéket, majd nyomja le az **Enter** billentyűt.</span><span class="sxs-lookup"><span data-stu-id="2ef93-151">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="2ef93-152">– vagy –</span><span class="sxs-lookup"><span data-stu-id="2ef93-152">-or-</span></span>

- <span data-ttu-id="2ef93-153">Nyomja le az **F1** billentyűt, írja be: **G**, válassza az **Ugrás a sorhoz** elemet, írja be a **8** értéket, majd nyomja meg az **Enter** billentyűt.</span><span class="sxs-lookup"><span data-stu-id="2ef93-153">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="2ef93-154">[![AZ ER képletszerkesztő GIF-fájlja, amely megmutatja, hogyan keresse meg a kifejezés egyes részeit a parancspaletta segítségével](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="2ef93-154">[![ER formula editor gif showing how to locate parts of an expression using the command palette](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="2ef93-155"><a name="CodeStructuring">Kód strukturálása</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-155"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="2ef93-156">Bizonyos funkciók kódja (például [IF](er-functions-logical-if.md) vagy [CASE](er-functions-logical-case.md)) automatikusan strukturálódik.</span><span class="sxs-lookup"><span data-stu-id="2ef93-156">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="2ef93-157">A kód bármely vagy összes része összecsukható és kibontható: így csökkentheti a kifejezés szerkeszthető részeit, hogy csak arra a részre lehessen összpontosítani, amelyek megköveteli a figyelmet.</span><span class="sxs-lookup"><span data-stu-id="2ef93-157">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="2ef93-158">Az összecsukás/kibontás parancsok használhatók erre.</span><span class="sxs-lookup"><span data-stu-id="2ef93-158">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="2ef93-159">Például az összes régió összecsukásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="2ef93-159">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="2ef93-160">Nyomja meg a **Ctrl+K** billentyűkombinációt</span><span class="sxs-lookup"><span data-stu-id="2ef93-160">Press **Ctrl+K**</span></span>

  <span data-ttu-id="2ef93-161">– vagy –</span><span class="sxs-lookup"><span data-stu-id="2ef93-161">-or-</span></span>

- <span data-ttu-id="2ef93-162">Nyomja le az **F1**, az **FO** billentyűt, nyomja meg az **Összes összecsukása** elemet, majd nyomja le az **Enter** billentyűt</span><span class="sxs-lookup"><span data-stu-id="2ef93-162">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="2ef93-163">Az összes régió kibontásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="2ef93-163">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="2ef93-164">Nyomja meg a **Ctrl+J** billentyűkombinációt</span><span class="sxs-lookup"><span data-stu-id="2ef93-164">Press **Ctrl+J**</span></span>

  <span data-ttu-id="2ef93-165">– vagy –</span><span class="sxs-lookup"><span data-stu-id="2ef93-165">-or-</span></span>
  
- <span data-ttu-id="2ef93-166">Nyomja le az **F1** billentyűt, írja be: **UN** billentyűt, nyomja meg az **Összes kibontása** elemet, majd nyomja le az **Enter** billentyűt</span><span class="sxs-lookup"><span data-stu-id="2ef93-166">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="2ef93-167">[![ER receptúraszerkesztő GIF-fájlja, amely a kód kihajtását mutatja](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="2ef93-167">[![ER formula editor gif showing code being unfolded](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="2ef93-168"><a name="FindAndReplace">Keresés és csere</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-168"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="2ef93-169">Bizonyos szövegek előfordulásának megtalálásához jelölje ki a kifejezés szövegét, és tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="2ef93-169">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="2ef93-170">Nyomja le a **Ctrl+F** billentyűkombinációt, majd az **F3** billentyű megnyomásával keresse meg a kiválasztott szöveg következő előfordulását, vagy nyomja le a **Shift+F3** billentyűkombinációt a korábbi előfordulás megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="2ef93-170">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="2ef93-171">– vagy –</span><span class="sxs-lookup"><span data-stu-id="2ef93-171">-or-</span></span>
  
- <span data-ttu-id="2ef93-172">Nyomja le az **F1** billentyűt, írja be az **F** karaktert, majd válassza ki a kívánt beállítást a kiválasztott szöveg megtalálásához.</span><span class="sxs-lookup"><span data-stu-id="2ef93-172">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="2ef93-173">Bizonyos szövegek előfordulásának cseréjéhez jelölje ki a kifejezés szövegét, és tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="2ef93-173">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="2ef93-174">Nyomja meg a **Ctrl+H** billentyűkombinációt.</span><span class="sxs-lookup"><span data-stu-id="2ef93-174">Press **Ctrl+H**.</span></span> <span data-ttu-id="2ef93-175">Adja meg a helyettesítő szöveget, és válassza a helyettesítés lehetőséget, ha a kijelölt szöveget vagy a szöveg összes előfordulását helyettesíteni szeretné az aktuális kifejezésben.</span><span class="sxs-lookup"><span data-stu-id="2ef93-175">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="2ef93-176">– vagy –</span><span class="sxs-lookup"><span data-stu-id="2ef93-176">-or-</span></span>
  
- <span data-ttu-id="2ef93-177">Nyomja le az **F1** billentyűt, írja be az **R** karaktert, majd válassza ki a kívánt beállítást a kiválasztott szöveg cseréjéhez.</span><span class="sxs-lookup"><span data-stu-id="2ef93-177">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="2ef93-178">Adja meg a helyettesítő szöveget, és válassza a helyettesítés lehetőséget, ha a kijelölt szöveget vagy a szöveg összes előfordulását helyettesíteni szeretné az aktuális kifejezésben.</span><span class="sxs-lookup"><span data-stu-id="2ef93-178">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="2ef93-179">Bizonyos szövegek összes előfordulásának cseréjéhez jelölje ki a kifejezés szövegét, és tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="2ef93-179">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="2ef93-180">Nyomja le a **Ctrl+F2** billentyűkombinációt, majd adja meg a helyettesítő szöveget.</span><span class="sxs-lookup"><span data-stu-id="2ef93-180">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="2ef93-181">– vagy –</span><span class="sxs-lookup"><span data-stu-id="2ef93-181">-or-</span></span>
  
- <span data-ttu-id="2ef93-182">Nyomja le az **F1** billentyűt, írja be a **C** karaktert, majd válassza ki a kívánt beállítást a kiválasztott szöveg módosításához.</span><span class="sxs-lookup"><span data-stu-id="2ef93-182">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="2ef93-183">Írja be a helyettesítő szöveget.</span><span class="sxs-lookup"><span data-stu-id="2ef93-183">Enter the alternative text.</span></span>

<span data-ttu-id="2ef93-184">[![ER receptúraszerkesztő GIF-fájlja, amely a keresést és helyettesítését mutatja](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="2ef93-184">[![ER formula editor gif showing find and replace](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="2ef93-185"><a name="DataPasting">Az adatforrások és a funkciók beillesztése</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-185"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="2ef93-186">Kiválaszthatja az **Adatforrás hozzáadását**, amely az aktuális kifejezéshez beszúrja az adatforrást, amely az **Adatforrás** bal oldali paneljén jelenleg kiválasztott.</span><span class="sxs-lookup"><span data-stu-id="2ef93-186">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="2ef93-187">Hasonlóan, kiválaszthatja a **Funkció hozzáadását**, amely az aktuális kifejezéshez beszúrja a funkciót, amely a **Funkciók** jobb oldali paneljén jelenleg kiválasztott.</span><span class="sxs-lookup"><span data-stu-id="2ef93-187">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="2ef93-188">Ha használja az ER-receptúraszerkesztőt, akkor egy kiválasztott funkció vagy egy kiválasztott adatforrás mindig beillesztődik a konfigurált kifejezés végére.</span><span class="sxs-lookup"><span data-stu-id="2ef93-188">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="2ef93-189">Ha használja a speciális ER-receptúraszerkesztőt, akkor egy kiválasztott funkció vagy egy kiválasztott adatforrás beilleszthető a konfigurált kifejezés bármelyik részébe.</span><span class="sxs-lookup"><span data-stu-id="2ef93-189">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="2ef93-190">A kurzor segítségével megadhatja, hogy hová szeretné beilleszteni az adatokat.</span><span class="sxs-lookup"><span data-stu-id="2ef93-190">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="2ef93-191">[![AZ ER képletszerkesztő gif-fájlja adatforrás hozzáadását és funkció beillesztését mutatja](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="2ef93-191">[![ER formula editor gif showing adding a data source and pasting a function](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="2ef93-192"><a name="SyntaxColorization">Szintaxis szerinti színezés</a></span><span class="sxs-lookup"><span data-stu-id="2ef93-192"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="2ef93-193">Jelenleg a különböző színek a kifejezések következő részeinek kiemelésére használhatók:</span><span class="sxs-lookup"><span data-stu-id="2ef93-193">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="2ef93-194">A dupla zárójelben lévő szöveg, amely egy szöveges állandó címkéjének azonosítóját jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2ef93-194">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="2ef93-195">[![ER-receptúraszerkesztő](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="2ef93-195">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="2ef93-196">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="2ef93-196">Limitations</span></span>

<span data-ttu-id="2ef93-197">A szerkesztőt jelenleg a következő webböngészők támogatják:</span><span class="sxs-lookup"><span data-stu-id="2ef93-197">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="2ef93-198">Chrome</span><span class="sxs-lookup"><span data-stu-id="2ef93-198">Chrome</span></span>
- <span data-ttu-id="2ef93-199">Edge</span><span class="sxs-lookup"><span data-stu-id="2ef93-199">Edge</span></span>
- <span data-ttu-id="2ef93-200">Firefox</span><span class="sxs-lookup"><span data-stu-id="2ef93-200">Firefox</span></span>
- <span data-ttu-id="2ef93-201">Opera</span><span class="sxs-lookup"><span data-stu-id="2ef93-201">Opera</span></span>
- <span data-ttu-id="2ef93-202">Safari</span><span class="sxs-lookup"><span data-stu-id="2ef93-202">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2ef93-203">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2ef93-203">Additional resources</span></span>

- [<span data-ttu-id="2ef93-204">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="2ef93-204">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="2ef93-205">Képletszerkesztő az Elektronikus jelentéskészítésben</span><span class="sxs-lookup"><span data-stu-id="2ef93-205">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="2ef93-206">Monaco szerkesztő</span><span class="sxs-lookup"><span data-stu-id="2ef93-206">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
