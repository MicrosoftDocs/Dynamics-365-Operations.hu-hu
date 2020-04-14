---
title: Elektronikus jelentéskészítés speciális képlet-szerkesztő
description: Ez a témakör azt mutatja be, hogyan használható a speciális receptúraszerkesztő kifejezések konfigurálására az elektronikus jelentési (ER) modell hozzárendelési és formátum összetevőiben.
author: NickSelin
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: df402bc20753d2ba14295592f4b40e20f9fdc7bf
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138898"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>Elektronikus jelentéskészítés speciális képlet-szerkesztő

[!include [banner](../includes/banner.md)]

Az [Elektronikus jelentéskészítés](general-electronic-reporting.md) [receptúra szerkesztőn](general-electronic-reporting-formula-designer.md) kívül a fejlett elektronikus jelentéskészítési receptúraszerkesztőt is használhatja az elektronikus jelentéskészítési (ER) kifejezések beállításának élményének javítására. A speciális szerkesztő a [Monaco-szerkesztő által működtetett böngésző-alapú ](https://microsoft.github.io/monaco-editor). Ez a témakör a leggyakrabban használt speciális szerkesztési funkciókat írja le:

- [Kód automatikus formázása](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Kódkiegészítés](#CodeCompletion)
- [Kódnavigáció](#CodeNavigation)
- [Kód strukturálása](#CodeStructuring)
- [Keresés és csere](#FindAndReplace)
- [Adatok beillesztése](#DataPasting)
- [Szintaxis szerinti színezés](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">A speciális receptúraszerkesztő aktiválása</a>

A következő lépések végrehajtásával kezdheti el használni Microsoft Dynamics 365 Finance-példányának speciális receptúraszerkesztőjét.

1.  Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2.  A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3.  A **Felhasználói paraméterek** párbeszédpanel **Végrehajtási nyomkövetés** szakaszában állítsa **A speciális receptúraszerkesztő aktiválása** paramétert **Igen** értékre.

[![ER-konfigurációk oldal](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> Ne feledje, hogy ez a paraméter a felhasználó- és a vállalatspecifikus.

## <a name=""></a><a name="Autoformatting">Kód automatikus formázása</a>

Ha egy összetett kifejezést ír be, amely több kódsorból áll, akkor az új megadott sor behúzása automatikusan az előző sor behúzása alapján történik. Kiválaszthatja a sorokat, és megváltoztathatja a behúzást a **Tab** vagy a **Shift+Tab** megnyomásával.

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

Az automatikus formázás lehetővé teszi a teljes kifejezés megfelelő formázását a további karbantartás megkönnyítésére, valamint a konfigurált logika megértésének egyszerűsítésére.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

A szerkesztő a szavak kiegészítését nyújtja, segítve a kifejezés írását és az elgépelés elkerülését. Új szöveg hozzáadásának elkezdése esetén a szerkesztő automatikusan felkínálja a megadott karaktereket tartalmazó funkciókban használható ER-funkciók listáját. A **Ctrl+Szóköz** beírásával a konfigurált kifejezés tetszőleges pontján aktiálható az IntelliSense.

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">Kódkiegészítés</a>

A szerkesztő automatikusan elvégzi a kód kiegészítését:

- Záró zárójel beszúrása a nyitó zárójel beírásakor, a kurzort a zárójelen belül tartva.
- A második idézőjel szimbólum beszúrása az első beírásakor, a kurzort az idézőjeleken belül tartva.
- A második dupla idézőjel szimbólum beszúrása az első beírásakor, a kurzort az idézőjeleken belül tartva.

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

Ha kijelöli a begépelt zárójelet, akkor a páros második zárójele automatikusan kiemelődik az általuk támogatott konstrukciót megmutatva.

## <a name=""></a><a name="CodeNavigation">Kódnavigáció</a>

A kifejezésben a szükséges szimbólumok vagy sorok megtalálhatók úgy, hogy az **Ugrás** parancsot a parancspaletta vagy a helyi menü segítségével adja meg.

A **8.** sorra történő ugráshoz például tegye a következőket:

- Nyomja le a **Ctrl+G** billentyűkombinációt adja meg a **8** értéket, majd nyomja le az **Enter** billentyűt.

  – vagy –

- Nyomja le az **F1** billentyűt, írja be: **G**, válassza az **Ugrás a sorhoz** elemet, írja be a **8** értéket, majd nyomja meg az **Enter**billentyűt.

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">Kód strukturálása</a>

Bizonyos funkciók kódja (például [IF](er-functions-logical-if.md) vagy [CASE](er-functions-logical-case.md)) automatikusan strukturálódik. A kód bármely vagy összes része összecsukható és kibontható: így csökkentheti a kifejezés szerkeszthető részeit, hogy csak arra a részre lehessen összpontosítani, amelyek megköveteli a figyelmet. Az összecsukás/kibontás parancsok használhatók erre.

Például az összes régió összecsukásához tegye a következőket:

- Nyomja meg a **Ctrl+K** billentyűkombinációt

  – vagy –

- Nyomja le az **F1**, az **FO** billentyűt, nyomja meg az **Összes összecsukása** elemet, majd nyomja le az **Enter** billentyűt

Az összes régió kibontásához tegye a következőket:

- Nyomja meg a **Ctrl+J** billentyűkombinációt

  – vagy –
  
- Nyomja le az **F1** billentyűt, írja be: **UN** billentyűt, nyomja meg az **Összes kibontása** elemet, majd nyomja le az **Enter** billentyűt

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">Keresés és csere</a>

Bizonyos szövegek előfordulásának megtalálásához jelölje ki a kifejezés szövegét, és tegye a következőket:

- Nyomja le a **Ctrl+F** billentyűkombinációt, majd az **F3** billentyű megnyomásával keresse meg a kiválasztott szöveg következő előfordulását, vagy nyomja le a **Shift+F3** billentyűkombinációt a korábbi előfordulás megtalálásához.

  – vagy –
  
- Nyomja le az **F1** billentyűt, írja be az **F** karaktert, majd válassza ki a kívánt beállítást a kiválasztott szöveg megtalálásához.

Bizonyos szövegek előfordulásának cseréjéhez jelölje ki a kifejezés szövegét, és tegye a következőket:

- Nyomja meg a **Ctrl+H** billentyűkombinációt. Adja meg a helyettesítő szöveget, és válassza a helyettesítés lehetőséget, ha a kijelölt szöveget vagy a szöveg összes előfordulását helyettesíteni szeretné az aktuális kifejezésben.

  – vagy –
  
- Nyomja le az **F1** billentyűt, írja be az **R** karaktert, majd válassza ki a kívánt beállítást a kiválasztott szöveg cseréjéhez. Adja meg a helyettesítő szöveget, és válassza a helyettesítés lehetőséget, ha a kijelölt szöveget vagy a szöveg összes előfordulását helyettesíteni szeretné az aktuális kifejezésben.

Bizonyos szövegek összes előfordulásának cseréjéhez jelölje ki a kifejezés szövegét, és tegye a következőket:

- Nyomja le a **Ctrl+F2** billentyűkombinációt, majd adja meg a helyettesítő szöveget.

  – vagy –
  
- Nyomja le az **F1** billentyűt, írja be a **C** karaktert, majd válassza ki a kívánt beállítást a kiválasztott szöveg módosításához. Írja be a helyettesítő szöveget.

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">Az adatforrások és a funkciók beillesztése</a>

Kiválaszthatja az **Adatforrás hozzáadását**, amely az aktuális kifejezéshez beszúrja az adatforrást, amely az **Adatforrás** bal oldali paneljén jelenleg kiválasztott. Hasonlóan, kiválaszthatja a **Funkció hozzáadását**, amely az aktuális kifejezéshez beszúrja a funkciót, amely a **Funkciók** jobb oldali paneljén jelenleg kiválasztott. Ha használja az ER-receptúraszerkesztőt, akkor egy kiválasztott funkció vagy egy kiválasztott adatforrás mindig beillesztődik a konfigurált kifejezés végére. Ha használja a speciális ER-receptúraszerkesztőt, akkor egy kiválasztott funkció vagy egy kiválasztott adatforrás beilleszthető a konfigurált kifejezés bármelyik részébe. A kurzor segítségével megadhatja, hogy hová szeretné beilleszteni az adatokat.

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">Szintaxis szerinti színezés</a>

Jelenleg a különböző színek a kifejezések következő részeinek kiemelésére használhatók:

- A dupla zárójelben lévő szöveg, amely egy szöveges állandó címkéjének azonosítóját jeleníti meg.

[![ER-receptúraszerkesztő](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)
- [Monaco szerkesztő](https://microsoft.github.io/monaco-editor)
