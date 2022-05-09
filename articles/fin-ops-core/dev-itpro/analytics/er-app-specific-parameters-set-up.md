---
title: Az ER-formátum paramétereinek beállítása jogi személyenként
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy Elektronikus jelentéskészítési (ER) formátum paramétereit jogi személyenként.
author: NickSelin
ms.date: 03/25/2022
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
ms.openlocfilehash: f72ce72e9cbd268efc6ab09dbec7009794d69613
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644499"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Az ER-formátum paramétereinek beállítása jogi személyenként

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Előfeltételek

Ezeknek a lépéseknek a végrehajtásához először végre kell hajtania az [ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md) szakaszban megadott lépéseket.

Az ebben a témakörben található példák befejezéséhez Microsoft Dynamics a következő szerepkörök valamelyikével hozzá kell férnie a 365 Pénzügy hez:

- Elektronikus jelentések fejlesztője
- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

## <a name="import-er-configurations"></a>ER-konfigurációk importálása
ER konfigurációk importálásához hajtsa végre az alábbi lépéseket: 

1. Jelentkezzen be a környezetébe.
2. Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** elemet.
3. Válassza a **Jelentéskészítési konfigurációk** elemet.
4. A Finance aktuális példányában importálja a Regulatory Configuration Services (RCS) alkalmazásból az [ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára](er-app-specific-parameters-configure-format.md) témakörben leírt lépések végrehajtása során exportált konfigurációkat. Hajtsa végre az alábbi lépéseket minden egyes [Elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) konfigurációjában, a következő sorrendben: adatmodell, modell-leképezés és formátumok.

    1. Válassza az **Exchange \> Betöltés XML-fájlból** lehetőségre.
    2. A **Tallózás** gombra kattintva válassza ki az XML-formátumú fájlt a szükséges ER-konfigurációhoz.
    3. Válassza ki az **OK** lehetőséget.

    A következő ábra bemutatja azokat a konfigurációkat, amelyekkel a befejezést követően rendelkeznie kell.

    ![ER-konfigurációk oldal.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Paraméterek beállítása a DEMF vállalathoz

Az ER keretrendszerrel beállíthatja az alkalmazásra jellemző paramétereket egy ER formátumhoz.

1. Válassza a **DEMF** jogi személyt.
2. A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
3. A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.

    ![ER alkalmazásspecifikus paraméterek oldal a paraméterek beállításához.](./media/GER-AppSpecParms-LookupForm.PNG)

    Az **alkalmazás-specifikus paraméterek** oldalon beállíthatja a **LE adatok keresésének tanulási formátuma** formátum **Választó** adatforrásra vonarkotó szabályokat.

    Ha az alap ER formátum számos **Keresés** típusú adatforrást tartalmaz, akkor az adatforrás szabályainak konfigurálása előtt ki kell választania a kívánt adatforrást a **Keresések** gyorslapon.

    Minden egyes adatforrás esetében külön szabályokat állíthat be a kiválasztott ER-formátum mindegyik verziójához.

    Az összes keresési adatforrásra vonatkozó teljes szabálycsoport, amely elérhető az alap ER formátum kiválasztott verziójában, alkotja az ER formátum alkalmazásspecifikus paramétereit.

4. Válassza az ER formátum **1.1.1** verzióját.
5. Válassza a **Feltételek** gyorslap **Hozzáadás** elemét.
6. Az új rekord **Kód** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához.

    A keresés megjeleníti a kiválasztható adókódok listáját. Ezt a listát visszaadja a **Model.Data.Tax** adatforrás, amelyet az adott ER formátumban konfigurált. Mivel az adatforrás tartalmazza a **Név** mezőt, a keresésben megjelenik az egyes adókódok neve.

    ![Kódmez keresése az ER alkalmazásspecifikus paramétereinek oldalán.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)

7. Válassza ki a **VAT19** áfakódot.
8. Az új rekord **Keresési eredmény** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához. A keresési lista felsorolja azokat a kiválasztható értékeket a TaxationLevel formátumfelsorolásához.

    Ne feledje, hogy ha a német a felhasználó preferált nyelve, amellyel be van jelentkezve, akkor a keresés értékeinek címkéi németül jelennek meg, feltéve, ha az alap ER formátumban ezeket lefordították. Ezenkívül ha a keresési adatforrás címkéjét már lefordították, akkor a címke a felhasználó preferált nyelvén jelenik meg a **Keresések** lapon.

    ![A keresési mező német nyelvre fordítva, az ER-alkalmazásspecifikus paraméterek oldalon.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9. Válassza a **Rendes adózás** értéket.

    A rekord hozzáadásával megadhatja a következő szabályt: Amikor a **Választó** keresési adatforrást kérik le, és a **VAT19** adókódot argumentumként adja át a rendszer, a kért adózási szintként a **Rendes adózás** eredményt adja vissza.

10. Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **InVAT19** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Rendes adózás** értéket.

11. Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **VAT7** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Csökkentett adózás** értéket.

12. Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **InVAT7** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Csökkentett adózás** értéket.

13. Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **THIRD** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Nincs adózás** értéket.

14. Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza ki az **InVAT0** adókódot.
    2. A **keresési eredmény** mezőben válassza ki a **Nincs adózás** értéket.

15. Válassza a **Hozzáadás** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Kód** mezőben válassza a **\*Nem üres\*** beállítást.
    2. A **keresési eredmény** mezőben válassza ki az **Egyéb** értéket.

    Az utolsó rekord hozzáadásával megadhatja a következő szabályt: Amikor az arugmentumként átadott adókód nem teljesíti a korábbi szabályok egyikét sem, a keresési adatforrás **Egyéb** értéket ad vissza a kért adózási szintként.

    ![Utolsó hozzáadott rekord az ER alkalmazásspecifikus paramétereinek oldalán.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)

16. Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.

    A **Befejeződött** vagy **Megosztott** állapotú ER formátumverzió futtatásakor a szabálycsoportnak **Befejeződött** állapotban kell lennie. Ellenkező esetben a rendszer megszakítja az alap ER formátum végrehajtását, amikor a formátum adatokat próbál ebből a szabálycsoportból betölteni a **Választó** keresési adatforrás futtatásakor.

    A **Tervezet** állapotú ER formátumú verzió futtatásakor az alap ER formátum hozzáférhet ehhez a szabálycsoporthoz állapottól függetlenül.

17. Válassza a **Mentés** lehetőséget.
18. Zárja be az **Alkalmazásspecifikus paraméterek** oldalt.

## <a name="run-the-er-format-in-the-demf-company"></a>Az ER formátum futtatása a DEMF vállalatban
Az ER-formátum futtatásához a DEMF vállalatban kövesse az alábbi lépéseket: 

1. A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
2. A Műveleti ablaktáblán kattintson a **Futtatás** elemre.
3. A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.
4. Töltse le a létrehozott kimutatást, és tárolja helyben.

    A létrehozott kimutatásban figyelje meg, hogy az **InVAT7** áfakód összefoglalása a **Csökkentett** szintű, és a **VAT19** és a **InVA19** adókódok összesítése a **Rendes** szintű. Ezt a viselkedést a jogi személytől függő szabálycsoportban található konfiguráció határozza meg.

5. Ugrás az **Adó \> Közvetett adók \> Áfa \> Áfakódok** pontra.
6. Válassza ki a **InVAT7** áfakódot.
7. A műveleti ablaktáblán az **Áfakód** lapon a **Lekérdezések** csoportban válassza a **Feladott áfa** elemet, ahol információkat tekinthet meg az adó értékével és az adókódonként alkalmazott adókulccsal kapcsolatban.

    ![Feladott áfa oldal.](./media/GER-AppSpecParms-Statement.PNG)

8. Zárja be a **Feladott áfa** oldalt.

## <a name="set-up-parameters-for-the-usmf-company"></a>Paraméterek beállítása a USMF vállalathoz
Az USMF vállalat paramétereinek beállítását a következő lépések szerint kell végrehajtani: 

1. Válassza a **USMF** jogi személyt.
2. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
3. A konfigurációk fájában bontsa ki a **Modell paraméterezett hívások tanulásához** elemet, bontsa ki a **Formátum paraméterezett hívások tanulásához** elemet, és válassza a **LE adatok keresésének tanulási formátuma** formátumot.
4. A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.
5. Válassza a kiválasztott ER formátum **1.1.1** verzióját.
6. Válassza a **Feltételek** gyorslap **Hozzáadás** elemét.
7. Az új rekord **Kód** mezőjében kattintson a legördítő nyílra a keresőlista megnyitásához.

    A keresés megjeleníti az **USMF** vállalati adóhoz tartozó választható adókódok listáját.

    ![Az USMF vállalat adójához tartozó adókódok.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)

8. Válassza ki a **EXEMPT** áfakódot.
9. Az új rekord **keresési eredmény** mezőjében válassza ki a **Nincs adózás** értéket.
10. Válassza a **Hozzáadás** lehetőséget.
11. Az új rekord **Kód** mezőjében válassza a **\*Nem üres\*** beállítást.
12. Az új rekord **keresési eredmény** mezőjében válassza ki a **Rendes adózás** értéket.
13. Az **Állapot** mezőben válassza ki a **Befejeződött** értéket.
14. Válassza a **Mentés** lehetőséget.

    ![ER alkalmazásspecifikus paramétereinek oldala.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)

15. Zárja be az **Alkalmazásspecifikus paraméterek** oldalt.

## <a name="run-the-er-format-in-the-usmf-company"></a>Az ER formátum futtatása a USMF vállalatban
Az ER-formátum futtatásához a USMF vállalatban végezze el az alábbi lépéseket:

1. A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
2. A Műveleti ablaktáblán kattintson a **Futtatás** elemre.
3. A megjelenő párbeszédpanelen jelölje be az **OK** lehetőséget.
4. Töltse le a létrehozott kimutatást, és tárolja helyben.

    A létrejövő kimutatásban figyelje meg, hogy egy másik jogi személyhez ugyanezt az ER formátumot használta fel, de nem végzett módosítást az ER formátumában.

## <a name="reuse-legal-entitydependent-parameters"></a>Jogi személytől függő paraméterek újbóli felhasználása

### <a name="duplicate-existing-parameters"></a>Meglévő paraméterek duplikálása

#### <a name="export-parameters"></a>Exportálási paraméterek
A paraméterek exportálása a következő lépésekkel végezhető el:

1. Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
4. A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.
5. Válassza az ER formátum **1.1.1** verzióját.
6. A műveleti ablaktáblán válassza az **Exportálás** lehetőséget.
7. Töltse le a létrehozott fájlt, és tárolja helyben.

    Az alkalmazásfüggő paraméterek megadott készlete már exportálva van XML-fájlként.

#### <a name="import-parameters"></a>Importálási paraméterek
A paraméterek importálása a következő lépésekkel végezhető el:

1. Válassza az ER formátum **1.1.2** verzióját.
2. A műveleti ablaktáblán válassza az **Importálás** lehetőséget.
3. Válassza az **Igen** lehetőséget, ha azt szeretné, hogy felülbírálja a formátum verziójának meglévő alkalmazásfüggő paramétereit.
4. A **Tallózás** gombra kattintva megkeresheti a **1.1.1**-es verzió exportált alkalmazásfüggő paramétereit tartalmazó fájlt.
5. Válassza ki az **OK** lehetőséget.

    Az ER-formátum **1.1.2**-es verziójának ugyanolyan alkalmazásfüggő paraméterei vannak, amelyeket eredetileg az **1.1.1**-es verzióhoz konfigurált.

##### <a name="applicability-considerations"></a>Alkalmazhatósági megfontolások

Az ER formátum alkalmazásfüggő paraméterei jogi személyektől-függőek. Ha egy adott jogi személyre konfigurált alkalmazásspecifikus paramétereket másik jogi személyben szeretné újból használni, exportálnia kell őket, miközben be van jelentkezve az első jogi személybe. Ezután importálja őket, miután bejelentkezett a másik jogi személybe.

Ezzel az exportálás-importálás módszerrel olyan ER formátumhoz kapcsolódó alkalmazásspecifikus paramétereket is átvihet a Finance másik példányába, amely eredetileg az egyik Finance példányhoz volt konfigurálva.

Ha egy ER-formátum alkalmazásspecifikus paramétereit konfigurálja, majd egy későbbi verzióját importálja ugyanannak a formátumnak az aktuális Finance példányá, a meglévő alkalmazásspecifikus paramétereket nem alkalmazza a program az importált verzióra, hacsak nem az **Alkalmazásspecifikus paraméterek használata az elektronikus jelentéskészítési formátumok előző verzióiból** funkciót használja. További tudnivalókat a [Meglévő paraméterek újrafelhasználása](#reuse-existing-parameters) részben olvashat, a témakör későbbi részében.

Amikor importálásra kiválaszt egy fájlt, akkor az adott fájl alkalmazásspecifikus paramétereinek szerkezetét összeveti az importálásra kijelölt ER formátum kapcsolódó, **Keresés** típusú adatforrásainak szerkezetével. Az importálás alapértelmezetten csak akkor történik meg, amikor az alkalmazásspecifikus paraméterek szerkezete megfelel a kapcsolódó adatforrás struktúrájának az importáláshoz kiválasztott ER-formátumban. Ha a szerkezetek nem egyeznek, akkor egy figyelmeztető üzenet tájékoztatja, hogy az importálás nem hajtható végre. Ha kényszeríti az importálást, akkor a program a kijelölt ER formátumra vonatkozó meglévő alkalmazásfüggő paramétereket kitörli, és a kezdetektől fogva újra be kell állítani őket.


A Pénzügy szolgáltatás 10.0.24-es verziójának megfelelően módosíthatja az alapértelmezett viselkedést, és így nem kap figyelmeztető üzenetet: **engedélyezi az ER-alkalmazásspecifikus** **paraméterek** beállítását a Szolgáltatáskezelési munkaterületen történő importálás közben. Ha ez a funkció engedélyezve van, amikor az adott fájl alkalmazásspecifikus paramétereinek szerkezete eltér a cél ER-formátum kapcsolódó adatforrásainak struktúrájától, amely ki van választva importálásra, az importálás a következő esetekben lesz sikeres:

- A cél ER-formátum szerkezete úgy módosult, hogy új feltételoszlopokat adott hozzá a meglévő **Keresés** típusú adatforrásokhoz. Az importálás befejeztével frissülnek az alkalmazásspecifikus paraméterek. Az alkalmazásspecifikus paraméterek minden importált rekordjánál az értékek minden hozzáadott feltételoszlopban inicializálva lesznek az adott oszlop [adattípusának](er-formula-supported-data-types-primitive.md) alapértelmezett értékével.
- A cél ER-formátum szerkezete úgy módosult, hogy új feltételoszlopokat távolított el a meglévő **Keresés** típusú adatforrásokból. Az importálás befejeztével frissülnek az alkalmazásspecifikus paraméterek. Az alkalmazásspecifikus paraméterek minden importált rekordjában az összes eltávolított feltételoszlop értékei törölve lesznek.
- A cél ER-formátum szerkezete úgy módosult, hogy **Keresés** típusú adatforrások lettek hozzáadva. Az importálás befejeztével a hozzáadott keresések hozzá lesznek fűzve az alkalmazásspecifikus paraméterekhez.
- A cél ER-formátum szerkezete úgy módosult, hogy el lettek távolítva **Keresés** típusú meglévő adatforrások. Az importálás befejeztével a rendszer törli az importált alkalmazásspecifikus paraméterekből azokat a műtermékeket, amelyek a cél ER-formátumból eltávolított **Keresés** típusú adatforrásához kapcsolódnak.

Amikor az importálás befejeződik, az előbb leírt módosításokon túl az importált alkalmazásspecifikus paraméterek állapota **Folyamatban** értékre lesz módosítva. Figyelmeztető üzenet tájékoztatja, hogy az automatikusan módosított alkalmazásspecifikus paramétereket manuálisan kell szerkeszteni.

#### <a name="replicate-parameters"></a>Paraméterek replikálása

A Pénzügy 10.0.27-es verziója szerint az egyik vállalatban beállított paramétereket egyszerre más vállalatokba másolhatja.

A paraméterek másolása a következő lépésekkel adatokat tartalmazza.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** formátumot.
4. A Műveleti ablaktáblán a **Konfigurációk** lapon a **Alkalmazásspecifikus paraméterek** csoportban válassza a **Beállítás** lehetőséget.
5. Válassza az ER formátum **1.1.1** verzióját.
6. A műveletpanelen válassza a Replikáció **lehetőséget**.
7. A Vállalatok **lap** Replikáció párbeszédpanelén **válassza** ki azokat a vállalatokat, amelyekbe paramétereket szeretne másolni.

    > [!NOTE]
    > A célvállalatok listáját csak azok a [felhasználók](../sysadmin/role-based-security.md#security-roles) kapják meg, akikhez olyan biztonsági szerepkör van hozzárendelve, amely az összes szervezethez való hozzáférés megadására van konfigurálva.

8. Válassza ki az **OK** lehetőséget.

    > [!NOTE]
    > A megerősítő párbeszédpanel arról tájékoztat, hogy egyes célvállalatok korábban konfigurált paramétereket tartalmaznak az ER-formátum kiválasztott verziójához. Válassza az **Igen** lehetőséget, ha felül szeretné bírálni a paramétereket az aktuális vállalatból való másolással.

    A konfigurált alkalmazásspecifikus paramétereket a program átmásolja a kiválasztott vállalatokba.

### <a name="reuse-existing-parameters"></a>Meglévő paraméterek újrafelhasználása

A Pénzügy 10.0.23-as verziója szerint újra fel lehet használni az alkalmazásspecifikus paramétereket, amelyek az ER-formátum egy verziójához vannak konfigurálva, amikor ugyanannak a formátumnak a magasabb verzióját futtatja. A meglévő paraméterek újbóli használatához engedélyezni **kell az ER-formátumok** **korábbi verziói alkalmazásspecifikus paramétereinek használatát a Funkciókezelés munkaterületen**. Ha ez a funkció engedélyezve van, és egy OLYAN ER-formátumot futtat, amely alkalmazásspecifikus paramétereket próbál olvasni, az ER megpróbálja megtalálni a formátum futó verziójához beállított alkalmazásspecifikus paramétereket. Ha nem érhetők el, az erszes megpróbálja megtalálni őket a formátum legközelebbi alacsonyabb verziójához.

> [!NOTE]
> Az alkalmazásspecifikus paraméterek csak az aktuális jogi személy hatókörében használhatók újra.
>
> Futásidőben hiba jelenik meg, amikor egy ER-formátum magasabb verzióját futtatja, amely az azonos formátumú alacsonyabb verzióhoz beállított alkalmazásspecifikus paramétereket próbál újra felhasználni, és a magasabb formátumverziójú **Keresés** típus legalább egy adatforrásának szerkezete megváltozott.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Az alkalmazásfüggő paraméterek és az ER formátum közötti kapcsolat

Az ER formátum és az alkalmazásspecifikus paraméterei közötti kapcsolatot az ER formátum példánytól független egyedi azonosító kódja határozza meg. Ennélfogva amikor a Finance alkalmazásból eltávolít egy ER-formátumot, a program megtartja az ER formátumhoz konfigurált alkalmazásspecifikus paramétereket a Finance aktuális példányában. Elérhetők, ha az alap ER formátumot újra importálják ebbe a Finance példányba.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Alkalmazás-specifikus paraméterek elérése az ER keretrendszer használatával

Az előző példában az ER keretrendszer használatával hozzáfért egy ER formátum alkalmazásspecifikus paramétereihez. Ez a megközelítés nem teszi lehetővé a hozzáférés korlátozását egy adott ER-formátum alkalmazásspecifikus paraméterei számára. Ha ilyen korlátozásokat kell alkalmaznia, hajtsa végre az alábbi lépéseket. 

1. Vagy használja újra a meglévő **ERSolutionAppSpecificParametersDesigner** menüelemet, vagy hajtsa végre saját **ERSolutionAppSpecificParametersDesigner** menüelemét.

    ![Az ERSolutionAppSpecificParametersDesigner menüelem-megjelenítése.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)

2. Tegye a következők egyikét:

    1. Hozzon létre egy új menüelemgombot, és csatolja a megfelelő rekordhoz az **ERSolutionTable** táblából az **Adatforrás** tulajdonságának **ERSolutionTable** értékre történő beállításával.

        ![Új menüelem-beállítások megjelenítése.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)

    2. Hozzon létre egy egyszerű gombot, és a következő példában bemutatott módon bírálja felül a **Rákattintva** módszert.

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
