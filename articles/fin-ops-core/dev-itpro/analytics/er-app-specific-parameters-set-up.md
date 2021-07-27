---
title: Az ER-formátum paramétereinek beállítása jogi személyenként
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy Elektronikus jelentéskészítési (ER) formátum paramétereit jogi személyenként.
author: NickSelin
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 9276a633d560bc95c868b9c12438b4f625ed169a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351890"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Az ER-formátum paramétereinek beállítása jogi személyenként

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Előfeltételek

Ezeknek a lépéseknek a végrehajtásához először végre kell hajtania az [ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md) témában megadott lépéseket.

A jelen témakörben szereplő példák végrehajtásához hozzáféréssel kell rendelkeznie a Microsoft Dynamics 365 Finance (Finance) modulnál a következő szerepkörök egyikéhez:

- Elektronikus jelentések fejlesztője
- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

## <a name="import-er-configurations"></a>ER-konfigurációk importálása

1.  Jelentkezzen be a környezetébe.
2.  Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** elemet.
3.  Válassza a **Jelentéskészítési konfigurációk** elemet.
4.  A Finance aktuális példányába importálja a Regulatory Configuration Service (RCS) alkalmazásból az [ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md) témakörben leírt lépések végrehajtása során exportált konfigurációkat. Hajtsa végre az alábbi lépéseket minden egyes Elektronikus jelentéskészítési (ER) konfigurációjában, a következő sorrendben: adatmodell, modell-leképezés és formátumok.

    1. Válassza az **Exchange \> Betöltés XML-fájlból** lehetőségre.
    2. A **Tallózás** gombra kattintva válassza ki az XML-formátumú fájlt a szükséges ER-konfigurációhoz.
    3. Válassza ki az **OK** lehetőséget.
    
    A következő ábra bemutatja azokat a konfigurációkat, amelyekkel a befejezést követően rendelkeznie kell.

    ![ER-konfigurációk oldal.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Paraméterek beállítása a DEMF vállalathoz

Az ER keretrendszerrel beállíthatja az alkalmazásra jellemző paramétereket egy ER formátumhoz.

1.  Válassza a **DEMF** jogi személyt.
2.  A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
3.  A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.

    ![ER alkalmazásspecifikus paramétereinek oldala.](./media/GER-AppSpecParms-LookupForm.PNG)
    
    Az **alkalmazás-specifikus paraméterek** oldalon beállíthatja a **LE adatok keresésének tanulási formátuma** formátum **Választó** adatforrásra vonarkotó szabályokat.
    
    Ha az alap ER formátum számos **Keresés** típusú adatforrást tartalmaz, akkor az adatforrás szabályainak konfigurálása előtt ki kell választania a kívánt adatforrást a **Keresések** gyorslapon.
    
    Minden egyes adatforrás esetében külön szabályokat állíthat be a kiválasztott ER-formátum mindegyik verziójához.
    
    Az összes keresési adatforrásra vonatkozó teljes szabálycsoport, amely elérhető az alap ER formátum kiválasztott verziójában, alkotja az ER formátum alkalmazásspecifikus paramétereit.

4.  Válassza az ER formátum **1.1.1** verzióját.
5.  Válassza a **Feltételek** gyorslap **Hozzáadás** elemét.
6.  Az új rekord **Kód** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához.

    A keresés megjeleníti a kiválasztható adókódok listáját. Ezt a listát visszaadja a **Model.Data.Tax** adatforrás, amelyet az adott ER formátumban konfigurált. Mivel az adatforrás tartalmazza a **Név** mezőt, a keresésben megjelenik az egyes adókódok neve.

    ![ER alkalmazásspecifikus paramétereinek oldala.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  Válassza ki a **VAT19** áfakódot.
8.  Az új rekord **Keresési eredmény** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához. A keresési lista felsorolja azokat a kiválasztható értékeket a TaxationLevel formátumfelsorolásához.

    Ne feledje, hogy ha a német a felhasználó preferált nyelve, amellyel be van jelentkezve, kakor a keresés értékeinek címkéi németül jelennek meg, feltéve, ha az alap ER formátumban ezeket lefordították. Ezenkívül ha a keresési adatforrás címkéjét már lefordították, akkor a címke a felhasználó preferált nyelvén jelenik meg a **Keresések** lapon.

    ![ER alkalmazásspecifikus paramétereinek oldala.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  Válassza a **Rendes adózás** értéket.

    A rekord hozzáadásával megadhatja a következő szabályt: Valahányszor a **választó** keresési adatforrást kérik le, és a **VAT19** adókódot argumentumként adja át a rendszer, a kért adózási szintként a **Rendes adózás** eredményt adja vissza.

10. Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **InVAT19** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Rendes adózás** értéket.
    
11. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **VAT7** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Csökkentett adózás** értéket.
    
12. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **InVAT7** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Csökkentett adózás** értéket.
    
13. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **THIRD** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Nincs adózás** értéket.
    
14. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **InVAT0** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Nincs adózás** értéket.
    
15. Válassza ismét a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza a **\*Nem üres\*** beállítást.
    2. A **keresési eredmény** mezőben válassza ki az **Egyéb** értéket.
    
    Az utolsó rekord hozzáadásával megadhatja a következő szabályt: Valahányszor az arugmentumként átadott adókód nem teljesíti a korábbi szabályok egyikét sem, a keresési adatforrás **Egyéb** értéket ad vissza a kért adózási szintként.

    ![ER alkalmazásspecifikus paramétereinek oldala.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.

    A **Befejeződött** vagy **Megosztott** állapotú ER formátumverzió futtatásakor a szabálycsoportnak **Befejeződött** állapotban kell lennie. Ellenkező esetben a rendszer megszakítja az alap ER formátum végrehajtását, amikor a formátum adatokat próbál ebből a szabálycsoportból betölteni a **Választó** keresési adatforrás futtatásakor.
    
    A **Tervezet** állapotú ER formátumú verzió futtatásakor az alap ER formátum hozzáférhet ehhez a szabálycsoporthoz állapottól függetlenül.
    
17. Válassza a **Mentés** lehetőséget.
18. Zárja be az **Alkalmazásspecifikus paraméterek** oldalt.

## <a name="run-the-er-format-in-the-demf-company"></a>Az ER formátum futtatása a DEMF vállalatban

1.  A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
2.  A Műveleti ablaktáblán kattintson a **Futtatás** elemre.
3.  A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.
4.  Töltse le a létrehozott kimutatást, és tárolja helyben.

    A létrehozott kimutatásban figyelje meg, hogy az **InVAT7** áfakód összefoglalása a **Csökkentett** szintre került, és a **VAT19** és a **InVA19** adókódok összesítése a **Rendes** szintre került. Ezt a viselkedést a jogi személytől függő szabálycsoportban található konfiguráció határozza meg.
    
5.  Ugrás az **Adó \> Közvetett adók \> Áfa \> Áfakódok** pontra.
6.  Válassza ki a **InVAT7** áfakódot.
7.  A műveleti ablaktáblán az **Áfakód** lapon a **Lekérdezések** csoportban válassza a **Feladott áfa** elemet, ahol információkat tekinthet meg az adó értékével és az adókódonként alkalmazott adókulccsal kapcsolatban.

    ![Feladott áfa oldal.](./media/GER-AppSpecParms-Statement.PNG)

8.  Zárja be a Feladott áfa oldalt.

## <a name="set-up-parameters-for-the-usmf-company"></a>Paraméterek beállítása a USMF vállalathoz

1.  Válassza a **USMF** jogi személyt.
2.  Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
3.  A konfigurációk fájában bontsa ki a **Modell paraméterezett hívások tanulásához** elemet, bontsa ki a **Formátum paraméterezett hívások tanulásához** elemet, és válassza a **LE adatok keresésének tanulási formátuma** formátumot.
4.  A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.
5.  Válassza a kiválasztott ER formátum **1.1.1** verzióját.
6.  Válassza a **Feltételek** gyorslap **Hozzáadás** elemét.
7.  Az új rekord **Kód** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához.

    A keresés megjeleníti az **USMF** vállalati adóhoz tartozó választható adókódok listáját.

    ![ER alkalmazásspecifikus paramétereinek oldala.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  Válassza ki a **EXEMPT** áfakódot.
9.  Az új rekord **keresési eredmény** mezőjében válassza ki a **Nincs adózás** értéket.
10. Válassza ismét a **Hozzáadás** lehetőséget.
11. Az új rekord **Kód** mezőjében válassza a **\*Nem üres\*** beállítást.
12. Az új rekord **keresési eredmény** mezőjében válassza ki a **Rendes adózás** értéket.
13. Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.
14. Válassza a **Mentés** lehetőséget.

    ![ER alkalmazásspecifikus paramétereinek oldala.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. Zárja be az **Alkalmazásspecifikus paraméterek** oldalt.

## <a name="run-the-er-format-in-the-usmf-company"></a>Az ER formátum futtatása a USMF vállalatban

1.  A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
2.  A Műveleti ablaktáblán kattintson a **Futtatás** elemre.
3.  A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.
4.  Töltse le a létrehozott kimutatást, és tárolja helyben.

    A létrejövő kimutatásban figyelje meg, hogy egy másik jogi személyhez ugyanezt az ER formátumot használta fel, de nem végzett módosítást az ER formátumában.

## <a name="reuse-legal-entitydependent-parameters"></a>Jogi személytől függő paraméterek újbóli felhasználása

### <a name="export-parameters"></a>Exportálási paraméterek

1.  Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.
2.  Válassza a **Jelentéskészítési konfigurációk** elemet.
3.  A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
4.  A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.
5.  Válassza az ER formátum **1.1.1** verzióját.
6.  A műveleti ablaktáblán válassza az **Exportálás** lehetőséget.
7.  Töltse le a létrehozott fájlt, és tárolja helyben.

    Az alkalmazásfüggő paraméterek megadott készlete már exportálva van XML-fájlként.

### <a name="import-parameters"></a>Importálási paraméterek

1.  Válassza az ER formátum **1.1.2** verzióját.
2.  A műveleti ablaktáblán válassza az **Importálás** lehetőséget.
3.  Válassza az **Igen** lehetőséget, ha azt szeretné, hogy felülbírálja a formátum verziójának meglévő alkalmazásfüggő paramétereit.
4.  A **Tallózás** gombra kattintva megkeresheti a **1.1.1**-es verzió exportált alkalmazásfüggő paramétereit tartalmazó fájlt.
5.  Válassza ki az **OK** lehetőséget.

    Az ER-formátum **1.1.2**-es verziójának ugyanolyan alkalmazásfüggő paraméterei vannak, amelyeket eredetileg az **1.1.1**-es verzióhoz konfigurált.
    
    Ne feledje, hogy az ER formátum alkalmazásfüggő paraméterei jogi személyektől-függőek. Ha egy adott jogi személyre konfigurált alkalmazásspecifikus paramétereket másik jogi személyben szeretné újból használni, exportálnia kell őket, miközben be van jelentkezve az első jogi személybe, majd importálja őket, miután bejelentkezett a másik jogi személybe.

    Ezzel a módszerrel olyan ER formátumhoz kapcsolódó alkalmazásspecifikus paramétereket is átvihet a Finance másik példányába, amely eredetileg az egyik Finance példányhoz volt konfigurálva.

    Ne feledje, hogy ha egy ER formátumának adott verziójához alkalmazásfüggő paramétereket konfigurál, és ugyanazon formátum magasabb verziószámát importálja az aktuális Finance példányba, akkor a program nem alkalmazza az importált verzióhoz a meglévő alkalmazásfüggő paramétereket.
    
    Ügyeljen arra is, ha importálásra kiválaszt egy fájlt, akkor az adott fájl alkalmazásspecifikus paramétereinek szerkezetét összeveti az importálásra kijelölt ER formátum kapcsolódó, **Keresés** típusú adatforrásának szerkezetével. Az importálás akkor történik meg, amikor az alkalmazásspecifikus paraméterek szerkezete megfelel a kapcsolódó adatforrás struktúrájának az importáláshoz kiválasztott ER-formátumban. Ha a szerkezetek nem egyeznek, akkor egy figyelmeztető üzenet jelenik meg, amely jelzi, hogy az importálás nem hajtható végre. Ha kényszeríti az importálást, akkor a program a kijelölt ER formátumra vonatkozó meglévő alkalmazásfüggő paramétereket kitörli, és a kezdetektől fogva újra be kell állítani őket.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Az alkalmazásfüggő paraméterek és az ER formátum közötti kapcsolat

Az ER formátum és az alkalmazásspecifikus paraméterei közötti kapcsolatot az ER formátum példánytól független egyedi azonosító kódja határozza meg. Ennélfogva amikor a Finance alkalmazásból eltávolít egy ER-formátumot, a program megtartja az ER formátumhoz konfigurált alkalmazásspecifikus paramétereket a Finance aktuális példányában. Bármikor elérhetők el, ha az alap ER formátumot újra importálják ebbe a Finance példányba.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Alkalmazás-specifikus paraméterek elérése az ER keretrendszer használatával

Az előző példában az ER keretrendszer használatával hozzáfért egy ER formátum alkalmazásspecifikus paramétereihez. Ez a megközelítés nem teszi lehetővé a hozzáférés korlátozását egy adott ER-formátum alkalmazásspecifikus paraméterei számára. Ha ilyen korlátozásokat kell alkalmaznia, hajtsa végre az alábbi lépéseket. 

1.  Vagy használja újra a meglévő **ERSolutionAppSpecificParametersDesigner** menüelemet, vagy hajtsa végre saját **ERSolutionAppSpecificParametersDesigner** menüelemét.

    ![Visual Studio oldala.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  Tegye a következők egyikét:

    1.  Hozzon létre egy új menüelemgombot, és csatolja a megfelelő rekordhoz az **ERSolutionTable** táblából az **Adatforrás** tulajdonságának **ERSolutionTable** értékre történő beállításával.
    
        ![Visual Studio oldala.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  Hozzon létre egy egyszerű gombot, és a következő példában bemutatott módon bírálja felül a **Rákattintva** módszert.
    
        Ennek a módszernek a használatával megadható egy egyedi megoldásazonosító (a **GUID** értékkel meghatározva), amely lehetővé teszi, hogy csak a megadott ER formátum alkalmazásspecifikus paramétereihez és az ebből származtatott leszármazott másolatokhoz férjen hozzá.
        
        ```xpp
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

## <a name="additional-resources"></a>További erőforrások

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]