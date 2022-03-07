---
title: ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni az Elektronikus jelentéskészítési (ER) formátumokat a jogi személyeknél megadott paraméterek használatára.
author: NickSelin
ms.date: 03/24/2021
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
ms.openlocfilehash: 16eab3ffa7d4a780ec9709f5c8a5c263b1e75365
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751178"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>ER formátumok konfigurálása a jogi személyenként meghatározott paraméterek használatára

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Áttekintés

Számos olyan Elektronikus jelentéskészítési (ER) formátumban, amelyet a későbbiekben meg fog tervezni, az adatok szűréséhez olyan értékcsoportok szükségesek, amelyek a példány egyes jogi személyeire specifikusak (például adózási kódok az adótranzakciók szűréséhez). Jelenleg ha az ilyen típusú szűrést ER-formátumban konfigurálja, akkor a jogi személytől függő értékeket (például adózási kódok) a rendszer az ER formátum kifejezéseiben használja az adatszűrési szabályok meghatározásához. Ennek megfelelően az ER formátum jogi személy–specifikus, és a szükséges jelentések előállítása érdekében minden olyan jogi személynél létre kell hoznia az eredeti ER formátum származtatott másolatokat, ahol futtatnia kell az ER formátumot. Minden származtatott ER formátumot úgy kell módosítani, hogy jogiszemély-specifikus értékeket kell behúzni, új alapra helyezni, ha az eredeti (alap) verzió frissült, a tesztkörnyezetből exportálni, és termelési környezetbe importálni, amikor a termelési használatra telepíteni kell, és így tovább. Ennek megfelelően az ilyen típusú konfigurált ER megoldás karbantartása elég összetett és időigényes több okból is:

-   Minél több jogi személy van, annál több ER formátumkonfigurációt kell karbantartani.
-   Az ER konfigurációk karbantartása megköveteli, hogy az üzleti felhasználók rendelkeznek ER-ismeretekkel.

Az ER alkalmazásspecifikus paraméterek funkcióval a kiemelt felhasználók konfigurálhatják az adatszűrést egy ER formátumban, hogy az absztrakt szabályok egy csoportján alapuljon. Ezek a szabályok beállíthatók úgy, hogy az ER formátumban elérhető adatforrásokat használják. Az üzleti felhasználók ezután az ER-keretrendszeren túl valódi szabályokat is megadhatnak a felhasználói felület (UI) segítségével, amely a megfelelő ER formátum beállításain alapulva automatikusan létrejön, és az aktuális jogi személy adataihoz hozzáférnek az ER formátum adatforrásai. Az ER formátumhoz megadott szabályok csoportját exportálhatja a Dynamics 365 Finance (Finance) példány aktuális jogi személyéből. Ezt követően importálható egy másik jogi személybe akár ugyanazon a Finance példányon, akár egy másik példányon, ugyanazon ER formátum szabálycsoportjaként.

## <a name="prerequisites"></a>Előfeltételek

A jelen témakörben leírt példák végrehajtásához hozzáféréssel kell rendelkeznie a Regulatory Configuration Service (RCS) példányához, amelyet ugyanarra a bérlőre telepítettek, mint a Finance szolgáltatást, a következő szerepkörök egyikéhez:

- Elektronikus jelentések fejlesztője
- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Javasoljuk, hogy hajtsa végre az [ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban](er-calculated-field-type.md) témakörben leírt lépéseket. Ha már elvégezte ezeket a lépéseket, akkor kihagyhatja a következő, **ER konfigurációk importálása az RCS-be** szakaszban leírt lépéseket.

## <a name="import-er-configurations-into-rcs"></a>ER Konfigurációk importálása RCS-be

Töltse le és helyben tárolja a következő ER-konfigurációkat.

| **Tartalom leírása**                        | **Fájlnév**                                        |
|------------------------------------------------|------------------------------------------------------|
| Minta **ER-adatmodell** konfigurációs fájlja    | [Model to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| Minta **ER-metaadat** konfigurációs fájl      | [Metadata to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Minta **ER-modell-leképezés** konfigurációs fájlja | [Mapping to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Minta **ER-formátum** konfiguráció             | [Format to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

Ezután jelentkezzen be a RCS-példányba.

Ebben a példában egy konfigurációt hoz létre a Litware, Inc. mintavállalatra vonatkozóan. A jelen eljárás befejezése előtt hajtsa végre a [Konfigurációszolgáltató létrehozása és aktívként történő megjelölése](tasks/er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit az RCS-ben.

1.  Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** elemet.
2.  Válassza a **Jelentéskészítési konfigurációk** elemet.
3.  A korábban letöltött ER konfigurációkat importálja a következő sorrendben az RCS-be: adatmodell, metaadatok, modell-leképezés és formátum. Minden ER konfiguráció esetén hajtsa végre az alábbi lépéseket:

    1.  **Árfolyam** kijelölése.
    2.  Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3.  A **Tallózás** gombra kattintva válassza ki az XML-formátumú fájlt a szükséges ER-konfigurációhoz.
    4.  Válassza ki az **OK** lehetőséget.

## <a name="review-the-er-solution-that-is-provided"></a>A biztosított ER-megoldás áttekintése

1.  A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elem tartalmát.
2.  Válassza ki a **Paraméterezett hívások tanulási formátuma** elemet.
3.  Válassza a **Tervező** lehetőséget.
4.  Válassza a **Kibontás/Összecsukás** lehetőséget.

    A **Paraméterezett hívások tanulási formátuma** ER formátum célja az adókimutatás létrehozása XML formátumban, amely az adózás több szintjét megjeleníti (rendes, csökkentett és nincs). Minden szint különböző számú adatot tartalmaz.

    ![Az ER-formátum több szintje, Formátum paraméterezett hívások tanulásához](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  A **Leképezés** lapon bontsa ki a **Modell**, **Adat** és **Összesítés** elemeket.

    A **Model.Data.Summary** adatforrás az összes adótranzakciót felsorolja. Ezek a tranzakciók áfakód alapján vannak összesítve. Az adott adatforrásnál a **Model.Data.Summary.Level** számított mezőt úgy konfigurálták, hogy adja vissza az egyes összesített rekord adózási szintjéhez tartozó kódot. Bármely, a **Model.Data.Summary** adatforrásból futásidőben lekérhető adókód esetén a számított mező szöveges értékként visszaadja az adózási szint kódját (**Rendes**, **Csökkentett**, **Nincs** vagy **Egyéb**). A **Model.Data.Summary.LEvel** számított mező a **Model.Data.Summary** adatforrás rekordjainak szűrésére szolgál, és megadja a szűrt adatokat az egyes, adózási szintet képviselő XML-elemekben a **Model.Data2.Level1**, **Model.Data2.Level2** és **Model.Data2.Level3** mezők használatával.

    ![A Model.Data.Summary adatforrás az összes adótranzakciót visszadja](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    A **Model.Data.Summary.Level** számított mezője úgy van beállítva, hogy a tartalmaz egy ER-kifejezést. Ne feledje, hogy az adókódokat (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD**, és **InVAT0**) beégették ebbe a konfigurációba. Ennek megfelelően ez az ER formátum függ attól a jogi személytől, ahol ezeket az adókódokat konfigurálták.

    ![A Model.Data.Summary.Level számított mező előre megadott adókódokkal](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    A következő lépések végrehajtásával támogathatja az egyes jogi személyekhez tartozó adókódok másik csoportját:

    - Hozzon létre egy származtatott verziót az ER formátumból mindegyik jogi személyhez.
    - Módosítsa a **Model.Data.Summary.Levelt** számított mezőjét a jogi személy beállításai alapján.

6.  Zárja be a **Formátumtervező** lapot.

## <a name="create-a-derived-format"></a>Származtatott formátum létrehozása

Ezután az ER alkalmazásspecifikus paraméterek funkcióval a eltérő adókódok csoportját is támogathatja az egyes jogi személyekben egyetlen ER formátummal.

1.  A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elem tartalmát.
2.  Válassza ki a **Paraméterezett hívások tanulási formátuma** elemet.
3.  Válassza a **Konfiguráció létrehozása** lehetőséget.
4.  Válassza a **Származtatás névből: Formátum paraméterezett hívások tanulásához, Microsoft** lehetőséget.
5.  A **Név** mezőbe írja be: **LE adatok keresésének tanulási formátuma**.
6.  Válassza a **Konfiguráció létrehozása** lehetőséget.

## <a name="configure-a-derived-format"></a>Származtatott formátum konfigurálása

### <a name="add-a-format-enumeration"></a>Formátumfelsorolás hozzáadása

Ezután hozzáad egy új ER formátumfelsorolást. Ennek a formátumfelsorolásnak az értékei megjelennek az üzleti felhasználóknak, akik megadják a jogi személytől függő adókódok csoportját az ER formátumban használt különböző adózási szintekhez.

1.  Válassza a **Tervező** lehetőséget.
2.  Válassza a **Formátumfelsorolás** elemet.
3.  Válassza a **Hozzáadás** lehetőséget.
4.  A **Név** mezőbe írja be a következőt: **Adózási szintek listája**.
5.  Válassza a **Mentés** lehetőséget.
6.  A **Formátumfelsorolási értékek** lapon válassza a **Hozzáadás** elemet.
7.  A **Név** mezőbe írja be a következőt: **Rendes adózás**.
8.  Válassza ismét a **Hozzáadás** lehetőséget.
9.  A **Név** mezőbe írja be a következőt: **Csökkentett adózás**.
10. Válassza ismét a **Hozzáadás** lehetőséget.
11. A **Név** mezőbe írja be a következőt: **Nincs adózás**.
12. Válassza ismét a **Hozzáadás** lehetőséget.
13. A **Név** mezőbe írja be az **Egyéb** szót.

    ![Új rekord a Formázási enumerációk oldalon](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    Mivel az üzleti felhasználók különböző nyelveket használnak a jogi személytől függő áfakódok cosportjának meghatározására, azt ajánljuk, hogy az ilyen felsorolási értékeit olyan nyelvekre fordítsa le, amelyek az adott Finance-felhasználók számára preferált nyelvként vannak konfigurálva.

14. Válassza a **Nincs adózás** rekordot.
15. Kattintson a **Címke** mezőbe.
16. Válassza a **Fordítás** elemet.
17. A **Szöveg fordítása** panel **Címkeazonosító** mezőjében adja meg : **LBL_LEVELENUM_NO**.
18. A **Szöveg az alapértelmezett nyelven** mezőben adja meg: **Nincs adózás**.
19. A **Nyelv** mezőben válassza a **DE** kódot.
20. Írja be a szöveget a **Lefordított szöveg** mezőbe: **keine Besteuerung**.
21. Válassza a **Fordítás** elemet.

    ![Szöveg fordítás kicsúsztatása](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. Válassza a **Mentés** lehetőséget.
23. Zárja be a **Formátumfelsorolások** lapot.

### <a name="add-a-new-lookup-data-source"></a>Új keresési adatforrás hozzáadása

Ezután új adatforrást ad hozzá, amellyel megadhatja, hogy az üzleti felhasználók milyen módon határozzák meg a jogi személytől függő szabályokat az egyes összesített tranzakciórekordok helyes adózási szintjének felismeréséhez.

1.  Válassza a **Leképezés** lap **Hozzáadás** elemét.
2.  Válassza a **Formátumfelsorolás\Keresés** elemet.

    Most megállapította, hogy minden egyes szabály, amelyet az üzleti felhasználók megadnak az adózási szint felismeréséhez, egy ER formátumfelsorolási értéket ad majd vissza. Figyelje meg, hogy a **Keresés** adatforrástípus az **Adatmodell**, valamint **Dynamics 365 for Operations** blokkokban érhető el, a **Formátumfelsorolás** blokk mellett. Ennélfogva az ER adatmodellek felsorolásai és az alkalmazásfelsorolások segítségével megadhatja, hogy milyen típusú értékeket ad vissza a program az adott típusú adatforrásokhoz.
    
3.  A **Név** mezőbe írja be a **Választó** szót.
4.  A **Formátumfelsorolás** mezőben válassza a következőt: **Adózási szintek listája**.

    Most megadta, hogy minden egyes, az adott adatforrásban megadott szabály esetén az üzleti felhasználónak ki kell választania az **Adózási szintek listája** formátumfelsorolás egyik értékét visszaadott értékként.
    
5.  Válassza a **Keresés szerkesztése** lehetőséget.
6.  Válassza az **Oszlopok** elemet.
7.  Bontsa ki a **Modell** elemet.
8.  Bontsa ki az **Adat** elemet.
9.  Bontsa ki az **Adó** elemet.
10. Válassza ki a **Model.Data.Tax.Code** elemet.
11. Válassza a **Hozzáadás** gombot (a jobbra nyilat).

    ![Oszlopok kicsúsztatása](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    Most megadta, hogy minden egyes, az adott adatforrásban az adózási szint felismerésére megadott szabály esetén az üzleti felhasználónak ki kell választania feltételként az egyik adókódot. Az üzleti felhasználó számára kiválasztható adókódok listáját visszaadja a **Model.Data.Tax** adatforrás. Mivel ez az adatforrás a **Név** mezőt tartalmazza, az áfakód neve megjelenik az üzleti felhasználó számára a keresésben megjelenő minden egyes adókódértékhez.
    
12. Válassza ki az **OK** lehetőséget.

    ![Kereséstervező lap](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    Az üzleti felhasználók több szabályt is hozzáadhatnak az adatforrás rekordjaiként. Minden rekordot egy sorkóddal számoz a rendszer. A szabályok a sorszámok növekvő sorrendjében kerülnek kiértékelésre.

    Mivel az adott keresési adatforrás szabályainak egyik feltételeként kiválasztotta az **Adókód mezőt**, és mivel az **Adókód** **Karakterlánc** típusú mezőként van beállítva, az egyes szabályokat a rendszer futásidőben úgy értékeli ki, hogy összehasonlítja az adatforrásnak átadott adókódot az adatforrás rekordjában meghtaártozott adókóddal.

    Ha a rendszer talál egy szabályt, amely kielégíti a konfigurált feltételt, akkor ez az adatforrás a **keresési eredmények** mezőben megadott szabály keresési értékét adja vissza. Ha nem található szabály, akkor egy kivétel jelenik meg, amely értesíti a felhasználót, hogy az aktuális adatforrás nem tud helyes értéket visszaadni.

13. Válassza a **Mentés** lehetőséget.
14. Zárja be a **Kereséstervező** lapot.
15. Válassza ki az **OK** lehetőséget.

    Észreveheti, hogy hozzáadott egy új adatforrást, ami az adózási szintet az **Adózási szintek listája** formátumfelsorolás értékeként adja vissza bármely olyan adókód esetén, amelyet az adatforrásnak a **Karakterlánc** adattípusú **Kód** paraméter argumentumaként átadtak.
    
    ![Tervező lap formázása új adatforrással](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    Ne felejtse el, hogy a konfigurált szabályok értékelése a szabályok feltételeinek meghatározására kiválasztott mezők adattípusától függ. Ha a **numerikus** vagy a **dátum** típusú adattípusú mezőként beállított mezőt választja, akkor a feltételek eltérnek a **Karakterlánc** adattípusnál korábban leírt feltételektől. A **numerikus** és a **dátum** típusú mezők esetében a szabályt értéktartományként kell megadni. A szabály feltétele akkor tekinthető teljesítettnek, ha egy adatforrásnak átadott érték a konfigurált tartományban van.
    
    A következő ábrán egy példa látható az ilyen típusú beállításra. A **Karakterlánc adattípus** **Model.Data.Tax.Code** mezőjén kívül a **Valódi** adattípus **Modell.Tax.Summary.Base** mezőjét is használhatja a keresési adatforrás feltételeinek megadására.
    
    ![A kereséstervező lap további oszlopokkal](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    Mivel a **Model.Data.Tax.Code** és a **Model.Tax.Summary.Base** mezőket kiválasztották ehhez a keresési adatforráshoz, az adott adatforrás egyes szabályainak konfigurálása a következő módon történik:
    
    -   A megjelenített listán az **Adózási szintek listája** formátumfelsorolás értékét visszaadott értékként kell kiválasztani.
    -   Az adókódot az adott szabály feltételeként kell megadni. Csak a **Model.Data.Tax** adatforrás által megadott adókódok érvényesek.
    -   Az áfaalap összegének minimális és maximális értékét az adott szabály feltételeként kell megadni.

    Itt láthatja, hogy az adott adatforrás egyes szabályait a rendszer futásidőben hogyan értékeli ki:
    -   Az adatforrásnak átadott **Karakterlánc** adattípus kódja egyenlő egy szabály adózási kódjával?
    -   Az adatforrásnak átadott **Valódi** adattípus értékeba megadott minimális és maximális értékek közé esik?

    Egy szabályt akkor kell alkalmazhatónak tekinteni, ha mindkét feltétel teljesül.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>A hozzáadott keresési adatforrás címkéjének lefordítása

Mivel az üzleti felhasználók különböző nyelveket használnak a jogi személytől függő áfakódok cosportjának meghatározására, azt ajánljuk, hogy minden hozzáadott keresési adatforrás címkéjét fordítsa le, hogy az az egyes felhasználók preferált nyelvén jelenjen meg a kapcsolódó oldalon.

1.  Válassza ki a **Model.Data.Selector** adatforrást.
2.  Válassza ki a **Szerkesztés** opciót.
3.  Kattintson a **Címke** mezőbe.
4.  Válassza a **Fordítás** elemet.
5.  A **Szöveg fordítása** panel **Címkeazonosító** mezőjében adja meg : **LBL_SELECTOR_DS**.
6.  A **Szöveg az alapértelmezett nyelven** mezőben adja meg: **Adózási szint kiválasztása adókód szerint**.
7.  A **Nyelv** mezőben válassza a **DE** kódot.
8.  A **Lefordított szöveg** mezőben adja meg: **Steuerebene für Steuerkennzeichen auswählen**.
9.  Válassza a **Fordítás** elemet.
10. Válassza ki az **OK** lehetőséget.

    ![Az adatforrás tulajdonságainak kicsúsztatása](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>Új mező hozzáadása a konfigurált keresés felhasználásához

1.  Bontsa ki a **Model.Data** elemet.
2.  Válassza ki a **Model.Data.Summary** elemet.
3.  Válassza a **Hozzáadás** lehetőséget.
4.  Válassza a **Függvények/Számított mező** elemet.
5.  A **Név** mezőbe írja be a következőt: **LevelByLookup**.
6.  Válassza a **Képlet szerkesztése** elemet.
7.  A **Receptúra mezőbe** adja meg: **Model.Selector(Model.Data.Summary.Code)**.
8.  Válassza a **Mentés** lehetőséget.

    ![A Model.Selector(Model.Data.Summary.Code) hozzáadása a Képlettervező laphoz](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  Zárja be a **Képletszerkesztő** lapot.
10. Válassza ki az **OK** lehetőséget.

    ![Formátumtervező lap az új hozzáadott képlettel](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    Észreveheti, hogy a **LevelByLookup** számított mező, amit hozzáadott, visszaadja az adózási szintet az **Adózási szintek listája** formátumfelsorolás értékeként az egyes összesített adótranzakciós rekordhoz. A rendszer a rekord adókódját átadja a **Model.Selector** keresési adatforrásnak, és az adott adatforráshoz tartozó szabályok csoportjának használatával választja ki a megfelelő adózási szintet.

### <a name="add-a-new-format-enumeration-based-data-source"></a>Új formátumfelsoroláson alapuló adatforrás hozzáadása

Ezután adjon hozzá egy új adatforrást, amely a korábban hozzáadott formátumfelsorolásra hivatkozik. Az adott adatforrás értékeit használja majd a rendszer később egy ER formátumkifejezésben.

1.  Válassza a **Gyökér hozzáadása** elemet.
2.  Válassza a **Formátumfelsorolások\Felsorolás** elemet.
3.  A **Név** mezőbe írja be a következőt: **TaxationLevel**.
4.  A **Formátumfelsorolás** mezőben válassza a következőt: **Adózási szintek listája**.
5.  Válassza a **Mentés** lehetőséget.

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a>Meglévő mező módosítása a keresés használatához

Ezután módosítani fogja a meglévő számított mezőt, hogy a beállított keresési adatforrást használja a megfelelő adózási szint értékének visszaadására, az áfakód értékétől függően.

1.  Válassza ki a **Model.Data.Summary.Level** elemet.
2.  Válassza ki a **Szerkesztés** opciót.
3.  Válassza a **Képlet szerkesztése** elemet.

    Figyelje meg, hogy a **Model.Data.Summary.Level** mező jelenlegi értéke a következő beégetett adókódokat tartalmazza:
    
    ESET (@.Code, "VAT19", "Rendes", "InVAT19", "Rendes", "VAT7", "Csökkentett", "InVAT7", "Csökkentett", "THIRD", "Nincs", "InVAT0", "Nincs", "Egyéb")

4.  A **Receptúra** mezőben adja meg: **CASE(@.LevelByLookup, TaxationLevel.'Rendes adózás', "Rendes", TaxationLevel.'Csökkentett adózás', "Csökkentett", TaxationLevel.'Nincs adózás', "Nincs", "Egyéb")**.

    ![ER-művelettervező oldal](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    Figyelje meg, hogy a **Model.Data.Summary.Level** mező kifejezése most az adózási szintet adja vissza, az aktuális rekord adókódja, valamint az üzleti felhasználó által a **Model.Data.Selector** keresési adatforrásban beállított szabálycsoport alapján.
    
5.  Válassza a **Mentés** lehetőséget.
6.  Zárja be a **Képlettervező** lapot.
7.  Válassza ki az **OK** lehetőséget.
8.  Válassza a **Mentés** lehetőséget.
9.  Zárja be a **Formátumtervező** lapot.

## <a name="complete-the-draft-version-of-a-derived-format"></a>Származtatott formátum tervezet változatának befejezése

1.  A **Verziók** gyorslapon válassza az **Állapot módosítása** elemet.
2.  Válassza a **Kész** lehetőséget.
3.  Válassza ki az **OK** lehetőséget.

## <a name="export-completed-version-of-modified-format"></a>Módosított formátum befejezett változatának exportálása

1.  A konfigurációs fában válassza ki a **LE adatok keresésének tanulási formátuma** elemet.
2.  A **Verziók** gyorslapon válassza ki azt a rekordot, amelynek állapota **Befejeződött**.
3.  **Árfolyam** kijelölése.
4.  Válassza ki az **Exportálás XML-fájlként** elemet.
5.  Válassza ki az **OK** lehetőséget.
6.  A webböngésző letölt egy **LE adatok keresésének tanulási formátuma**-fájlt. A fájlt tárolja helyileg.

Az ebben a szakaszban található lépéseket ismételje meg a **LE adatok keresésének tanulási formátuma** formátum fölérendelt elemeinél, és tárolja helyileg a következő fájlokat:

-   Formátum paraméterezett hívások tanulásához.xml
-   Leképezés paraméterezett hívások tanulásához.xml
-   Modell paraméterezett hívások tanulásához.xml

Ha meg szeretné tudni, hogyan kell a konfigurált **LE adatok keresésének tanulási formátuma** ER-formátumot használni jogi személytől függő adókódcsoportok létrehozásához az adótranzakciók különböző adózási szintek alapján történő szűréséhez, kövesse az [ER-formátum paramétereinek beállítása jogi személyenként](er-app-specific-parameters-set-up.md) témakörben leírt lépéseket.

## <a name="additional-resources"></a>További erőforrások

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Az ER-formátum paramétereinek beállítása jogi személyenként](er-app-specific-parameters-set-up.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
