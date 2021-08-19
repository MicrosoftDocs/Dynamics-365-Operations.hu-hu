---
title: Elektronikus jelentéskészítés speciális képlet-szerkesztő
description: Ez a témakör azt mutatja be, hogyan használható a speciális képletszerkesztő kifejezések konfigurálására az elektronikus jelentési (ER) modell hozzárendelési és formátum összetevőiben.
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
ms.openlocfilehash: 58d7a936f94e1cd453c904ef6404e0db65083c54235c8420b9cfa561bcde1584
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714659"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>Elektronikus jelentéskészítés speciális képlet-szerkesztő

[!include [banner](../includes/banner.md)]

Az [Elektronikus jelentéskészítés](general-electronic-reporting.md) [képlet szerkesztőn](general-electronic-reporting-formula-designer.md) kívül a fejlett elektronikus jelentéskészítési képletszerkesztőt is használhatja az elektronikus jelentéskészítési (ER) kifejezések beállításának élményének javítására. A speciális szerkesztő a [Monaco-szerkesztő által működtetett böngésző-alapú ](https://microsoft.github.io/monaco-editor). Ez a témakör a leggyakrabban használt speciális szerkesztési funkciókat írja le:

- [Kód automatikus formázása](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Kódkiegészítés](#CodeCompletion)
- [Kódnavigáció](#CodeNavigation)
- [Kód strukturálása](#CodeStructuring)
- [Keresés és csere](#FindAndReplace)
- [Adatok beillesztése](#DataPasting)
- [Szintaxis szerinti színezés](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">A speciális képletszerkesztő aktiválása</a>

A következő lépések végrehajtásával kezdheti el használni Microsoft Dynamics 365 Finance-példányának speciális képletszerkesztőjét.

1.  Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2.  A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3.  A **Felhasználói paraméterek** párbeszédpanel **Végrehajtási nyomkövetés** szakaszában állítsa **A speciális képletszerkesztő aktiválása** paramétert **Igen** értékre.

[![Felhasználói paraméterek párbeszédpanel, Speciális képletszerkesztő paraméter engedélyezése kiemelve.](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> Ne feledje, hogy ez a paraméter a felhasználó- és a vállalatspecifikus.

A Microsoft Dynamics 365 Finance 10.0.19-es verziójától kezdve szabályozható, hogy alapértelmezés szerint milyen ER képletszerkesztőt kínálnak. A következő lépések segítségével engedélyezheti a speciális képletszerkesztőt az aktuális Pénzügyi példány összes felhasználója és vállalata számára.

1.  Nyissa meg a **Funkciókezelés** munkaterületet.
2.  Keresse meg és válassza ki a listában található **Összes felhasználó alapértelmezettként az ER speciális képletszerkesztő beállítása** funkciót, majd válassza az **Engedélyezés most** lehetőséget.
3.  Nyissa meg a következőt: **Szervezeti adminisztráció** > **Elektronikus jelentés** > **Konfigurációk**.
4.  A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
5.  A **Felhasználói paraméterek** párbeszédpanelen keresse meg a **Speciális képletszerkesztő letiltása** paramétert, és ellenőrizze, hogy a **Nem** beállítás van-e megadva.

[![Felhasználói paraméterek párbeszédpanel, Speciális képletszerkesztő paraméter letiltása kiemelve.](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)

> [!NOTE]
> A **Speciális képlet-szerkesztő engedélyezése** és a **Speciális képletszerkesztő letiltása** paraméterértékek minden felhasználónál külön maradnak, és a **Felhasználói paraméterek** párbeszédpanelen jelennek meg, az **ER speciális képlet-szerkesztő beállítása** alapértelmezettként való beállításának állapotától függően minden felhasználó funkciónál.

## <a name=""></a><a name="Autoformatting">Kód automatikus formázása</a>

Ha egy összetett kifejezést ír be, amely több kódsorból áll, akkor az új megadott sor behúzása automatikusan az előző sor behúzása alapján történik. Kiválaszthatja a sorokat, és megváltoztathatja a behúzást a **Tab** vagy a **Shift+Tab** megnyomásával.

[![ER-képletszerkesztő GIF-fájlja a sorok kiválasztásának és a behúzás módosításának megjelenítésével.](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

Az automatikus formázás lehetővé teszi a teljes kifejezés megfelelő formázását a további karbantartás megkönnyítésére, valamint a konfigurált logika megértésének egyszerűsítésére.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

A szerkesztő a szavak kiegészítését nyújtja, segítve a kifejezés írását és az elgépelés elkerülését. Új szöveg hozzáadásának elkezdése esetén a szerkesztő automatikusan felkínálja a megadott karaktereket tartalmazó funkciókban használható ER-funkciók listáját. A **Ctrl+Szóköz** beírásával a konfigurált kifejezés tetszőleges pontján aktiálható az IntelliSense.

[![ER-képletszerkesztő GIF-fájlja, amelyen az IntelliSense aktiválása látható.](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">Kódkiegészítés</a>

A szerkesztő automatikusan elvégzi a kód kiegészítését:

- Záró zárójel beszúrása a nyitó zárójel beírásakor, a kurzort a zárójelen belül tartva.
- A második idézőjel szimbólum beszúrása az első beírásakor, a kurzort az idézőjeleken belül tartva.
- A második dupla idézőjel szimbólum beszúrása az első beírásakor, a kurzort az idézőjeleken belül tartva.

[![Az ER-képletszerkesztő GIF-fájlja mutatja, hogy a szerkesztő automatikusan biztosít kódkiegészítést.](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

Ha kijelöli a begépelt zárójelet, akkor a páros második zárójele automatikusan kiemelődik az általuk támogatott konstrukciót megmutatva.

## <a name=""></a><a name="CodeNavigation">Kódnavigáció</a>

A kifejezésben a szükséges szimbólumok vagy sorok megtalálhatók úgy, hogy az **Ugrás** parancsot a parancspaletta vagy a helyi menü segítségével adja meg.

A **8.** sorra történő ugráshoz például tegye a következőket:

- Nyomja le a **Ctrl+G** billentyűkombinációt adja meg a **8** értéket, majd nyomja le az **Enter** billentyűt.

  – vagy –

- Nyomja le az **F1** billentyűt, írja be: **G**, válassza az **Ugrás a sorhoz** elemet, írja be a **8** értéket, majd nyomja meg az **Enter** billentyűt.

[![Az ER-képletszerkesztő GIF-fájlja, amely megmutatja, hogyan keresse meg a kifejezés egyes részeit a parancspaletta segítségével.](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

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

[![Az ER-képletszerkesztő GIF-fájlja, amely a kód kibontását mutatja be.](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

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

[![Az ER-képletszerkesztő GIF-fájlja, amely a keresést és a cserét mutatja be.](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">Az adatforrások és a funkciók beillesztése</a>

Kiválaszthatja az **Adatforrás hozzáadását**, amely az aktuális kifejezéshez beszúrja az adatforrást, amely az **Adatforrás** bal oldali paneljén jelenleg kiválasztott. Hasonlóan, kiválaszthatja a **Funkció hozzáadását**, amely az aktuális kifejezéshez beszúrja a funkciót, amely a **Funkciók** jobb oldali paneljén jelenleg kiválasztott. Ha használja az ER-képletszerkesztőt, akkor egy kiválasztott funkció vagy egy kiválasztott adatforrás mindig beillesztődik a konfigurált kifejezés végére. Ha használja a speciális ER-képletszerkesztőt, akkor egy kiválasztott funkció vagy egy kiválasztott adatforrás beilleszthető a konfigurált kifejezés bármelyik részébe. A kurzor segítségével megadhatja, hogy hová szeretné beilleszteni az adatokat.

[![Az ER-képletszerkesztő GIF-fájlja, amely adatforrás hozzáadását és egy függvény beillesztését mutatja.](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">Szintaxis szerinti színezés</a>

Jelenleg a különböző színek a kifejezések következő részeinek kiemelésére használhatók:

- A dupla zárójelben lévő szöveg, amely egy szöveges állandó címkéjének azonosítóját jeleníti meg.

[![ER-képletszerkesztő](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>Korlátozások

A szerkesztőt jelenleg a következő webböngészők támogatják:

- Chrome
- Edge
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)
- [Monaco szerkesztő](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
