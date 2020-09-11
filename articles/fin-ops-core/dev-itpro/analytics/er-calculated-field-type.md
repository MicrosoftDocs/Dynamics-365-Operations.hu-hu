---
title: ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban
description: Ez a témakör azt mutatja be, hogyan kell használni a Számított mezőtípust ER-adatforrásokhoz.
author: NickSelin
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 02d53f4326d8f31abf6ec7404575728837954bef
ms.sourcegitcommit: c9baf9a3b4552f0317b5ec87d252834f52df1b98
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665610"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a>ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet az elektronikus jelentéskészítési (ER) adatforrást tervezni a **Számított mező** típusban. Ez az adatforrás olyan ER-kifejezéseket tartalmazhat, amelyek a végrehajtás során paraméterargumentumok értékeivel vezérelhetők, amely egy hozzárendelésben konfigurálható, amely meghívja ezt az adatforrást. Egy ilyen adatforrás paraméterezett hívásának konfigurálásával több kötésben is felhasználható egyetlen adatforrás, ami csökkenti azoknak az adatforrásoknak a számát, amelyeket az ER-formátumok ER modell-leképezéseihez konfigurálni kell. Leegyszerűsíti a konfigurált ER-összetevőt is, amely csökkenti a karbantartási költségeket és a más felhasználók által felhasználás költségeit.

## <a name="prerequisites"></a>Előfeltételek
A jelen témakörben szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:

- Hozzáférés egy ilyen szerepkörhöz:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

- A Regulatory Configuration Services (RCS) szolgáltatáshoz való hozzáférés, ami ugyanattól a bérlőtől került szolgáltatásra, mint Finance and Operations Operations egyre vonatkozik az alábbi lépések közül:

    - Elektronikus jelentések fejlesztője
    - Elektronikus jelentések funkcióival foglalkozó konzulens
    - Rendszergazda

A következő fájlokat is le kell töltenie és helyben tárolnia.

| **Tartalom**                           | **Fájlnév**                                        |
|---------------------------------------|------------------------------------------------------|
| Minta ER-adatmodell konfigurációja    | [Model to learn parameterized calls.version.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| Minta ER-metaadat konfigurációja      | [Metadata to learn parameterized calls.version.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| Minta ER-adatmodell leképezési konfigurációja | [Mapping to learn parameterized calls.version.1.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| Minta ER-formátum konfigurációja        | [Format to learn parameterized calls.version.1.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a>Jelentkezzen be a RCS-példányba
Ebben a példában létrehozzuk egy konfigurációt a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő eljárás lépéseit kell végrehajtani az RCS-ben: [Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md):

1. Az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés**elemet.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A letöltött konfigurációkat importálja a következő sorrendben az RCS-be: adatmodell, metaadatok, modell-leképezés, formátum. Hajtsa végre a következő lépéseket mindegyik ER-konfiguráció esetében:

    1. Válassza az **Átváltás** lehetőséget.
    2. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3. Kattintson a **Tallózás** gombra, majd válassza ki a megfelelő, XML-formátumú fájlt a szükséges ER-konfigurációhoz.
    4. Válassza ki az **OK** lehetőséget.

## <a name="review-the-provided-er-solution"></a>A nyújtott ER-megoldás áttekintése

### <a name="review-model-mapping"></a>Modell-leképezés áttekintése

1. A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.
2. Válasza ki a **Leképezés paraméterezett hívások tanulásához elemet**.
3. Válassza a **Tervező** lehetőséget.
4. Válassza a **Tervező** lehetőséget.  
   
    Ez az ER-leképezés a következőkre képes:

    - Lekéri az adókódok listáját (**Adó** adatforrás) amelyek a **TaxTable** táblában találhatók.
    - Lekéri az adótranzakciók listáját (**Tranz** adatforrás) amelyek a **TaxTrans** táblában találhatók:
    
        - A beolvasott tranzakciók (**Gr** -adatforrás) listájának csoportosítása adózási kód szerint.
        - Kiszámítja a csoportosított tranzakciókat az adózási kód szerinti aggregált értékek szerint:

            - Adóalap-értékek összege.
            - Adóértékek összege.
            - Az alkalmazott adómérték minimális értéke.

    A modell-leképezés ebben a konfigurációban implementálása az alap adatmodellt bármely ER formátumhoz, amely ehhez a modellhez lett készítve és a Finance and Operations által lett végrehajtva. Ennek eredményeképpen az **Adó** és **Gr** -adatforrások tartalma ER-formátumoknak, például absztrakt adatforrásoknak van kitéve.

    ![Modell-hozzárendelés tervező lapja au Adó és Gr adatforrásokat jeleníti meg.](media/er-calculated-field-type-01.png)

5.  Zárja be a **Modell-hozzárendelési tervező** lapot.
6.  Zárja be a **Modell-hozzárendelés** lapot.

### <a name="review-format"></a>Formátum áttekintése

1. A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.
2. Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.
3. Válassza a **Tervező** lehetőséget. Ez az ER-formátum a következőkre képes:

    - Adókimutatás létrehozása XML-formátumban.
    - Az adóbevallásban a következő adómértékeket megjeleníti: normál, csökkentett és nincs.
    - Minden adózási szinten több részletet mutat be, amelyek mindegyik szintjén különböző számú adat szerepel.

    ![Formátumtervező oldal](media/er-calculated-field-type-02.png)

4. Válassza ki **Hozzárendelés** lehetőséget.
5. Bontsa ki a **Modell**, **Adatok** és **Összegzés** elemeket. 

    A **Model.Data.Summary.Level** számított mező tartalmazza azt a kifejezést, amely az adózási szint kódját adja vissza (**Normál**, **Csökkenetett**, **Nincs** vagy **Egyéb**). szöveges értékként, amely lekérhető a **Model.Data.summary** adatforrásból futásidőben.

    ![A Formátumtervező lap a paraméterezett hívások megtanulásához szükséges adatmodell részleteit jeleníti meg.](media/er-calculated-field-type-03.png)

6. Bontsa ki a **Model**.**Data2** elemet.
7. Bontsa ki a **Model**.**Data2.Summary2** elemet.
   
    A **Model**.**Data2.Summary2** adatforrás úgy van konfigurálva, hogy csoportba rendezze a **Model.Data.Summary** adatforrás tranzakcióadatait adózási szinten (ezt a **Model.Data.Summary.Level** számított mező adja vissza), és kiszámítsa az összesítéseket.

    ![A Formátumtervező lap a Model.Data2.Summary2 adatforrás részletes adatait jeleníti meg.](media/er-calculated-field-type-04.png)

8. Tekintse át a **Model**.**Data2.Level1**, **Model**.**Data2.Level2** és **Model**.**Data2.Level3** számított mezőket. Ezeket a számított mezőket a **Model**.**Data2.Summary2** rekordlista szűrésére használja a rendszer, és csak az adott adózási szintet képviselő rekordokat adja vissza.
9. Zárja be a **Formátumtervező** lapot.

## <a name="create-a-derived-format"></a>Származtatott formátum létrehozása
A megadott formátumot úgy javíthatja, hogy egy számított mezőt ad hozzá a szükséges adózási szint szűréséhez, nem pedig a meglévő három mezőt használja: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** és **Model**.**Data2.Level3**. A szükséges adózási szint meghatározható azon a helyen, ahol ennek az új számított mezőnek a meghívása történik.

1. A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.
2. Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.
3. Válassza a **Konfiguráció létrehozása** lehetőséget.
4. Válassza a **Származtatás névből: Formátum paraméterezett hívások tanulásához, Microsoft** lehetőséget.
5. A **Név** mezőbe írja be: **Paraméterezett hívások tanulási formátuma (egyéni)**.
6. Válassza a **Konfiguráció létrehozása** lehetőséget.

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a>A rekordok listáját visszaadó paraméterezett számított mező konfigurálása

### <a name="start-adding-a-new-calculated-field"></a>Kezdje el az új számított mező hozzáadását

1. Válassza a **Tervező** lehetőséget.
2. Válassza ki a **Kibontás/összecsukás** elemet az összes formátumelem kibontásához.
3. Válassza ki **Hozzárendelés** lehetőséget.
4. Bontsa ki a **Modell** elemet.
5. Válassza ki a **Model.Data2** elemet.
6. Válassza a **Hozzáadás** lehetőséget.
7. Válassa a **Függvények\\Számított mezőt**.
8. A **Név** mezőbe írja be a **szintek** szót.
9. Válassza a **Képlet szerkesztése** elemet.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Paraméter definiálása számított mező hozzáadásához

1. Válassza ki a **Paraméterek** elemet.
2. Válassza az **Új** lehetőséget.
3. A **Név** mezőbe írja be a következőt: **Adózási szint**.
4. A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.

    A paraméterek argumentumának típusát csak primitív adattípusokkal lehet megadni. Ezért a **Rekordlista**, **Rekord**és **Enum** típus nem használhatók erre a célra.

    Az egyetlen számított mezőhöz meghatározható paraméterek maximális száma 8.

    ![Paraméter adatforráslistája](media/er-calculated-field-type-05.png)

5. Válassza ki az **OK** lehetőséget.

Ennek a paraméternek a hozzáadásával megadhatja azt a feltételt, amely a kiszámított mező hívásához szükséges. Ha ezt a mezőt választja, akkor az **Adózási szint** paraméter argumentumát **Karakterlánc** formátumú értékként kell megadni.

   Győződjön meg róla, hogy csak olyan számított mezőkhöz határoz meg paramétereket, amelyek egy tárolóban találhatók (tehát **Rekordlista**, **Rekord** vagy **Tároló**).

   A konfigurált paraméter elérhető a számított mezőhöz tartozó adatforrásainak listáján. A konfigurált kifejezéshez úgy vehet fel paramétert, hogy az **Adatforrás hozzáadása** lehetőséget választja.

   ![Adatforrásmezők](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Kifejezés definiálása számított mező hozzáadásához

1. A **Képlet** mezőben adja meg a következőt: 

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level =**
    
2. Válassza ki az **Adózási szint** paramétert az adatforrások listáján.
3. **Adatforrás hozzáadása** lehetőség választása.
4. A **Képlet** mezőben véglegesítse a kifejezést a következőképpen:  

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**

5. Válassza a **Mentés** lehetőséget.

    ![Adatforrás mező adatai](media/er-calculated-field-type-07.png)

6. Zárja be a **Képlettervező** lapot.

### <a name="finish-adding-a-new-calculated-field"></a>Az új számított mező hozzáadásának befejezése

- Válassza ki az **OK** lehetőséget.

A **Formátumtervező** lapon a **Szintek** konfigurált paraméterezett számított mező **Karakterlánc** argumentumot igényel.

![Számított mezők szintjeinek kibontott listája](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a>A konfigurált számított mező használata formátumelemek kapcsolásához

1. Válasza ki a **Model.Data2.Levels** a konfigurált számított mező kiválasztásához.
2. Válassza ki a **Statement.Taxation.Regulars** formátumelemet.
3. Válassza a **Bind** elemet.
4. Az **igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level1**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.

    Az alkalmazott társítást a program a paraméterezett számított mező meghívásaként alakítja ki. Alapértelmezés szerint a társított formátumelem neve argumentumként használatos a paraméterezett számított mezőhöz a következő feltételek teljesülése esetén:

      - A számított mező úgy van beállítva, hogy egyetlen paramétert használjon.
      - A paraméter adattípusa **Karakterláncként** van definiálva.

    Amikor a társított formátumelem neve üres, az elemhez tartozó adatforrásnév használatos az alkalmazott társításban.

5. Válassza ki a **Statement.Taxation.Reduced** formátumelemet.
6. Válassza a **Bind** elemet.
7. Az **Igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level2**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.
8. Válassza ki a **Statement.Taxation.None** formátumelemet.
9. Válassza a **Bind** elemet.
10. Az **Igen** gombra kattintva visszaigazolhatja az aktuálisan használt adatforrás ( **Level3**) lecserélését az új **Szintek** adatforrásra a kiválasztott formátumelem minden beágyazott formátumeleme tekintetében.

   Ha megadja az adózási szintet képviselő XML-elem paraméterezett számított mezőjének argumentumát (például: **Model.Data2.Levels("Reduced")** szöveges értékként), akkor nem kell ugyanezt elvégeznie a beágyazott XML-attribútumok esetében – a kötések automatikusan öröklik a szülő szintjén megadott argumentum értékét (**Model.Data2.Levels.aggregated.Base** és nem **Model.Data2.Levels("Reduced").aggregated.Base**).

A paraméterezett számított mezők ismétlődő meghívása nem támogatott.

Kiválaszthatja a **Képlet szerkesztése** elemet, és módosíthatja a paraméterezett számított mező alapértelmezetten alkalmazott argumentumát a kiválasztott társításhoz. Ha hiányzik ez az argumentum, az futásidőben hibákat okozhat – a felhasználókat tájékoztatni kell erről a helyzetről, amikor az aktuális formátumot validálják.

![Ellenőrzési figyelmeztetés értesítése](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a>Rekordot visszaadó paraméterezett számított mező konfigurálása
Ha egy paraméterezett számított mező rekordot ad vissza, akkor támogatnia kell a rekord egyedi mezőinek társítását formátumelemekhez. Ilyen esetekben nem lesz olyan szülő társítás amely argumentum értékét tartalmazza egy paraméterezett számított mező meghívására – ezt az értéket egyetlen rekord mezőjének társítása során kell meghatározni.

### <a name="start-adding-a-new-calculated-field"></a>Kezdje el az új számított mező hozzáadását

1. Válassza ki a **Model.Data2** elemet.
2. Válassza a **Hozzáadás** lehetőséget.
3. Válassa a **Függvények\\Számított mezőt**.
4. A **Név** mezőbe írja be a **LevelRecord** értéket.
5. Válassza a **Képlet szerkesztése** elemet.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Paraméter definiálása számított mező hozzáadásához

1. Válassza ki a **Paraméterek** elemet.
2. Válassza az **Új** lehetőséget.
3. A **Név** mezőbe írja be a következőt: **Adózási szint**.
4. A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.
5. Válassza ki az **OK** lehetőséget.

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Kifejezés definiálása számított mező hozzáadásához

1. A **Képlet** mezőben adja meg a következőt:  
    
    **FIRSTORNULL(\@.Levels(**

2. Válassza ki az **Adózási szint** paramétert.
3. **Adatforrás hozzáadása** lehetőség választása.
4. A **Képlet** mezőbe írja fűzze hozzá a **"'Taxation Level'))** elemet ahhoz,amit megadott az 1. lépésben, hogy a következőképp véglegesítse a kifejezést:  
    
    **FIRSTORNULL(\@.Levels('Taxation Level'))**

5. Válassza a **Mentés** lehetőséget.
6. Zárja be a **Képlettervező** lapot.

### <a name="finish-adding-a-new-calculated-field"></a>Az új számított mező hozzáadásának befejezése

-   Válassza ki az **OK** lehetőséget.

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a>A konfigurált számított mező használata formátumelemek társításához

1. Bontsa ki a **Model.Data2.LevelRecord** elemet a konfigurált számított mező kiválasztásához.
2. Bontsa ki a **Model.Data2.LevelRecord.aggregated** tárolóját a konfigurált számított mezőnek.
3. Válassza ki **Model.Data2.LevelRecord.aggregated.Base** mezőt.
4. Válassza ki a **Statement.Taxation.None** formátumelemet.
5. Válassza a **Kötés megszűntetése** elemet.
6. Válassza ki a **Statement.Taxation.Base** formátumelemet.
7. Válassza a **Bind** elemet.
8. Válassza a **Képlet szerkesztése** elemet.
9. A kifejezés módosítása a következőre: **Model.Data2.LevelRecord("None").aggregated.Base**.

![Frissített kifejezés](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a>Nem használt számított mezők eltávolítása

1. Válassza a **Model.Data2.Level1** lehetőséget.
2. Válassza a **Törlés** lehetőséget.
3. Válassza a **Model.Data2.Level2** lehetőséget.
4. Válassza a **Törlés** lehetőséget.
5. Válassza a **Model.Data2.Level3** lehetőséget.
6. Válassza a **Törlés** lehetőséget.
7. Válassza a **Mentés** lehetőséget.

  > [!NOTE]
  > Ugyanezt a **Model.Data2.Levels** számított mezőt többször is felhasználhatja a formátumtársításokban. Sokkal könnyebb használni és karbantartani egyetlen számított mezőt,mint ugyanezt megtenni több hasonló mező esetében.

8. Zárja be a **Formátumtervező** lapot.

## <a name="complete-adjusted-version-of-a-derived-format"></a>Származtatott formátum korrigált változatának befejezése

1. A **Verziók** gyorslapon válassza az **Állapot módosítása** elemet.
2. Válassza a **Kész** lehetőséget.

## <a name="export-completed-version-of-a-derived-format"></a>Származtatott formátum korrigált változatának exportálása

1. Válassza a **Formátum tanulja meg a paraméterezett meghívásokat (egyén)** formátumot a konfigurációs fában.
2. A **Verziók** gyorslapon válassza ki a kész 1.1.1-es verziót.
3. **Árfolyam** kijelölése.
4. Válassza ki az **Exportálás XML-fájlként** elemet.
5. A letöltött konfiguráció tárolása helyben, XML-formátumban.

## <a name="test-er-formats"></a>ER-formátumok tesztelése 
A kezdeti és a továbbfejlesztett ER formátumot futtathatja, hogy meggyőzpdjön arról, hogy a konfigurált paraméterezett számított mezők megfelelően működnek.

### <a name="import-er-configurations"></a>ER-konfigurációk importálása
Az **RCS** típushoz tartozó ER-tároló használatával importálhatja az áttekintett konfigurációkat. Ha már elvégezte az [Elektronikus jelentéskészítési (ER) konfigurációkat importálása a Regulatory Configuration Service (RCS) szolgáltatásból](rcs-download-configurations.md) lépéseit, használja a konfigurált ER-tárolót, a korábban tárgyalt konfigurációk importálásához környezetébe. Máskülönben kövesse az alábbi lépéseket:

1. Válassza ki a **DEMF** vállalatot és az alapértelmezett irányítópulton válassza az **Elektronikus jelentéskészítés** lehetőséget.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A letöltött konfigurációkat importálja a Microsoft letöltőközpontból a sorrendben: adatmodell, metaadatok, modell-leképezés, formátum. Hajtsa végre a következő lépéseket mindegyik ER-konfiguráció esetében:

    1. Válassza az **Átváltás** lehetőséget.
    2. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3. Kattintson a **Tallózás** gombra, a megfelelő, XML-formátumú fájl kiválasztásához a szükséges ER-konfigurációhoz.
    4. Válassza ki az **OK** lehetőséget.

4. Importálja az exportált RCS befejezett 1.1.1. verzióját a **Formátum tanulja meg a paraméterezett meghívásokat** formátumából:

    1. Válassza az **Átváltás** lehetőséget.
    2. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3. A **Tallózás** gombra kattintva kiválaszthatja a **Paraméterezett hívások tanulási formátuma (egyéni)** fájlt XML-formátumban.
    4. Válassza ki az **OK** lehetőséget.

### <a name="run-er-formats"></a>ER formátumok futtatása

1. A konfigurációs fában bontsa ki a **Modell a paraméterezett hívások megtanulásához** elemet.
2. Válasza ki a **Formátum paraméterezett hívások tanulásához elemet**.
3. Válassza a **Futtatás** parancsot a legfelső menüszalagon.
4. Mentse el a helyileg előállított kimenetet.
5. Válassza ki a **Paraméterezett hívások tanulási formátuma (egyéni)** elemet.
6. Válassza a **Futtatás** parancsot a legfelső menüszalagon.
7. Mentse el az előállított kimenetet helyben. 
8. A generált kimenetek tartalmának összehasonlítása.

## <a name="additional-resources"></a>További erőforrások
[Képletszerkesztő elektronikus jelentésekhez (ER)](general-electronic-reporting-formula-designer.md)
