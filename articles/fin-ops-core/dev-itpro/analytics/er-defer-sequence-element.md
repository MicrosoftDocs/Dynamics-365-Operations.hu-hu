---
title: A szekvenciaelemek végrehajtásának elhalasztása az ER-formátumokban
description: Ez a témakör azt mutatja be, hogyan lehet elhalasztani egy szekvenciaelem végrehajtását egy elektronikus jelentési (ER) formátumban.
author: NickSelin
manager: kfend
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 9aa019e20b218fdaad4659fa65d9df629069204b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680734"
---
# <a name="defer-the-execution-of-sequence-elements-in-er-formats"></a>A szekvenciaelemek végrehajtásának elhalasztása az ER-formátumokban

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Áttekintés

A Művelettervezőt használhatja az [Elektronikus jelentési (ER)](general-electronic-reporting.md) keretrendszerben, hogy [konfigurálja](tasks/er-format-configuration-2016-11.md) a [formátum-összetevőjét](general-electronic-reporting.md#FormatComponentOutbound) egy olyan ER-megoldásnak, amely kimenő dokumentumok szöveges formában történő létrehozásához használatos. A konfigurált formátum-összetevő hierarchikus szerkezete különböző típusú formátumelemeket tartalmaz. Ezek a formátumelemek a létrejövő dokumentumok kitöltéséhez használhatók a szükséges információval, futásidőben. Alapértelmezés szerint, amikor egy ER-formátumot futtat, a formátum elemeit ugyanabban a sorrendben futtatja a rendszer, ahog a formátumhierarchiában vannak: egyesével, fentről lefelé haladva. A tervezéskor azonban bármikor módosíthatja a konfigurált formátum-összetevő bármely elemének végrehajtási sorrendjét.

Ha beállítja a <a name="DeferredSequenceExecution"></a>**Halasztott végrehajtás** beállítást a sorszámozott formátumelemre a konfigurált formátumban, akkor elhalaszthatja az elem végrehajtását. Ebben az esetben az elem mindaddig nem fut, amíg a szülő többi elemét nem futtatták.

Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben.

## <a name="limitations"></a>Korlátozások

A **Halasztott végrehajtás** beállítás csak olyan szekvenciaelemekhez használható, amelyek egy olyan ER-formátumhoz vannak használatban, amely **kimenő** dokumentumok szöveg formátumú létrehozásához használt.

A **Halasztott végrehajtás** beállítás nem alkalmazható olyan sorszámok esetében, amelyek a maximális hosszt korlátozó megtisztított szekvenciákként lettek beállítva.

## <a name="example-defer-the-execution-of-a-sequence-element-in-an-er-format"></a><a name="Example"></a>Példa: Szekvenciaelem végrehajtásának elhalasztása egy ER-formátumban

A következő lépésekkel megtudhatja, hogy a rendszergazda vagy elektronikus jelentéskészítési tanácsadó [szerepkörrel](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/sysadmin/tasks/assign-users-security-roles) rendelkező felhasználó hogyan konfigurálhat egy olyan, szekvenciaelemet tartalmazó ER-formátumot, amelynél a végrehajtási sorrend eltér a formátumhierarchiában megadott sorrendtől.

Ezeket a lépéseket a **USMF** vállalatban hajthatja végre a Microsoft Dynamics 365 Finance megoldásban.

### <a name="prerequisites"></a>Előfeltételek

A jelen példa végrehajtásához hozzáféréssel kell rendelkeznie az **USMF** vállalathoz a Finance megoldásban a következő szerepkörök egyikéhez:

- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Ha még nem végezte el a példát a következő témakörben: [Az XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md#Example), töltse le a minta ER-megoldás következő [konfigurációit](general-electronic-reporting.md#Configuration).

| Tartalom leírása            | Fájlnév |
|--------------------------------|-----------|
| ER-adatmodell konfigurációja    | [Model to learn deferred elements.version.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| ER-modell leképzési konfigurációja | [Mapping to learn deferred elements.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

A kezdés előtt le kell tölteni és menteni kell a minta ER-megoldás következő konfigurációját.

| Tartalom leírása     |Fájlnév |
|-------------------------|----------|
| ER-formátum konfigurációja | [Format to learn deferred sequences.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="import-the-sample-er-configurations"></a>Minta ER-konfigurációk importálása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A **Konfigurációk** oldalon, ha nem érhető el a **Mapping to learn deferred elements** konifiguráció a konfigurációs fában, importálja az ER-adatmodell konfigurációját:

    1. Válassza az **Exchange** elemet, majd válassza az **XML-fájlból történő betöltést**.
    2. Válassza a **Tallózás** elemet, keresse meg és válassza ki a **Model to learn deferred elements.1.xml** fájlt, majd majd kattintson az **OK** gombra.

4. Ha nem érhető el a **Mapping to learn deferred elements** konifiguráció a konfigurációs fában, importálja az ER-modell leképezés konfigurációját:

    1. Válassza az **Exchange** elemet, majd válassza az **XML-fájlból történő betöltést**.
    2. Válassza a **Tallózás** elemet, keresse meg és válassza ki a **Mapping to learn deferred elements.1.1.xml** fájlt, majd majd kattintson az **OK** gombra.

5. Az ER-formátumkonfiguráció importálása:

    1. Válassza az **Exchange** elemet, majd válassza az **XML-fájlból történő betöltést**.
    2. Válassza a **Tallózás** elemet, keresse meg és válassza ki a **Format to learn deferred sequences.1.1.xml** fájlt, majd majd kattintson az **OK** gombra.

6. A konfigurációs fában bontsa ki a **Model to learn deferred elements** elemet.
7. Tekintse át a konfigurációs fában importált ER-konfigurációk listáját.

    ![Importált ER-konfigurációk a Konfigurációk oldalon](./media/ER-DeferredSequence-Configurations.png)

### <a name="activate-a-configurations-provider"></a>Konfigurációs szolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Győződjön meg róla, hogy a **Honosítási konfigurációk** lap **Konfigurációs szolgáltatók** szakaszában a Litware, Inc. [konfigurációs szolgáltatója](general-electronic-reporting.md#Provider) (`http://www.litware.com`) szerepel a listán, és aktívként van megjelölve. Ha ez a konfigurációs szolgáltató nem szerepel a listán, vagy ha nem aktívként van megjelölve, hajtsa végre a [Konfigurációs szolgáltató létrehozása és megjelölje aktív](./tasks/er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit.

    ![Litware, Inc. mintavállalat a Lokalizációs konfigurációk oldalon](./media/ER-DeferredSequence-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Az importált adatleképezés ellenőrzése

Ellenőrizze az ER-modellhozzárendelési összetevő beállítását, amely az adóügyi tranzakciók elérése érdekében be van állítva, és igény szerint hozzáférhet az adatokhoz.

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. A **Konfigurációk** oldalon található konfigurációk fájában bontsa ki a **Model to learn deferred elements** elemet.
4. Válassza ki **Mapping to learn deferred elements** konfigurációt.
5. Válassza ki a **Tervezőt** a leképezések listájának megnyitásához.
6. A leképezésirészletek áttekintéséhez válassza a **Tervező** elemet.
7. Válassza a **Részletek megjelenítése** lehetőséget.
8. Tekintse át az adóügyi tranzakciók eléréséhez konfigurált adatforrásokat:

    - A **Tranzakció** adatforrás a *Táblabejegyzés* típusból úgy van beállítva, hogy elérje a **TaxTrans** alkalmazástábla rekordjait.
    - A **Bizonylatok** adatforrása a *Számított mező* típusból úgy van beállítva, hogy a szükséges bizonylatkódokat (**INV-10000349** és **INV-10000350**) adja vissza rekordok listájaként.
    - A **Szűrt** adatforrás a *Számított mező* típusból úgy van beállítva, hogy a **Tranzakciók** adatforrásból csak a szükséges bizonylatok adózási tranzakcióit válassza ki.
    - A **\$TaxAmount** mező a *Számított mező* típusból a **Szűrt** adatforráshoz van adva az ellenkező előjelű adózási érték megjelenítéséhez.
    - A **Csoportosított** adatforrás a *Csoportosítás alapja* típusból úgy van beállítva, hogy a **Szűrt** adatforrás szűrt adóügyi tranzakcióit csoportosítsa.
    - A **TotalSum** aggregációs mezője a **Csoportosított** adatforrásnak úgy van beállítva, hogy **\$TaxAmount** mező értékeit összesítse a **Szűrt adatforrás** adatforrásnak az adott adatforrás összes szűrt adóügyi tranzakciója esetében.

        ![A TotalSum aggregációs mező a „GroupBy” paraméterek lapon](./media/ER-DeferredSequence-GroupByParameters.png)

9. Annak áttekintése, hogy hogyan kötődnek a konfigurált adatforrások az adatmodellhez, és hogy hogyan teszik elérhetővé a hozzáférhető adatokat az ER-formátum számára:

    - A **Szűrt** adatforrás az adatmodell **Data.List** mezőjéhez kötődik.
    - A **\$TaxAmount** mezője a **Szűrt** adatforrásnak az adatmodell **Data.List.Value** mezőjéhez kötődik.
    - A **TotalSum** mezője a **Csoportosított** adatforrásnak az adatmodell **Data.Summary.Total** mezőjéhez kötődik.

    ![Modell-leképezés tervező oldal](./media/ER-DeferredSequence-ModelMapping.png)

10. Zárja be a **Modell-hozzárendelés tervező** és **Modell-hozzárendelések** lapokat.

### <a name="review-the-imported-format"></a>Tekintse át az importált formátumot

1. Válassza ki a **Konfigurációk** lap konfigurációs fájában a **Format to learn deferred sequences** konfigurációt.
2. A formátumrészletek áttekintéséhez válassza a **Tervező** elemet.
3. Válassza a **Részletek megjelenítése** lehetőséget.
4. Tekintse át azoknak az ER-formátum összetevőknek a beállításait, amelyek a kimenő dokumentumok szöveges formátumban történő előállítására vannak konfigurálva, amely az adóügyi tranzakciók részletes adatait tartalmazza.

    - A **Jelentés\\Sorai** sorformátum elem úgy van beállítva, hogy a kimenő dokumentumot a beágyazott szekvencia elemeiből létrejövő egyetlen sorral töltse fel (**Fejléc**, **Rekord** és **Összesítés**).

        ![A sorokhoz tartozó sorozatok formátumának eleme és beágyazott elemek a Formátumtervező oldalon](./media/ER-DeferredSequence-Format.png)

    - A **Jelentés\\Sorok\\Fejléc** szekvenciaformátum-elem úgy van konfigurálva, hogy a kimenő dokumentumot egyetlen fejlécsorral tölti ki, amelyben a feldolgozás elindulásának dátuma és időpontja látható.
    - A **Jelentés \\Sorok\\Rekord** szekvenciaformátum-elem úgy van konfigurálva, hogy a kimenő dokumentumot egyetlen sorral töltse ki, amely az egyes adótranzakciók adatait jeleníti meg. Ezeket az adózási tranzakciókat pontosvesszővel választják el egymástól.

        ![Rekordszekvencia-formátum eleme, amely pontosvesszőt használ a határolójelként](./media/ER-DeferredSequence-Format1.png)

    - A **Jelentés\\Sorok\\Összesítés** sorozatformat elem úgy van beállítva, hogy a kimenő bizonylatot egyetlen összesítő sorral töltse ki, amely tartalmazza a feldolgozott adózási tranzakciókból származó adók összegét.

4. A **Leképezés** lapon tekintse át a következő részleteket:

    - A **Jelentés\\Sorok\\Fejléc** elemet nem kötelező egy adatforráshoz csatlakoznia egy kimenő dokumentum egyetlen sorának létrehozásához.
    - A **Prefix1** elem a **P1** szimbólumokat generálja, amelyek azt jelzik, hogy a hozzáadott sor a jelentés fejlécének sora.
    - Az **ExecutionDateTime** elem a fejlécsor hozzáadásakor létrehozza a dátumot és az időt (ezredmásodpercekkel együtt).
    - A **Jelentés\\Sorok\\Rekord** eleme a **model.Data.List** listához van kötve, és a kötött lista minden rekordjához egy sort generál.
    - A **Prefix2** elem a **P2** szimbólumokat generálja, amelyek azt jelzik, hogy a hozzáadott sor a tranzakcióadatok részleteihez tartozik.
    - A **TaxAmount** elem a **model.Data.List.Value** elemhez tartozik (amely a következőként jelenik meg: **\@.Value** a relatív elérési út nézetben), az aktuális adózási tranzakció adózási értékének előállításához.
    - A **RunningTotal** elem az adózási értékek folyamatos összértékének a helyőrzője. Ez az elem jelenleg nem tartalmaz kimenetet, mert nincs beállítva hozzá kötelező vagy alapértelmezett érték.
    - A **ExecutionDateTime** elem az aktuális tranzakció feldolgozásakor a dátumot és az időt (ezredmásodpercekkel együtt) hozza létre.
    - A **Jelentés\\Sorok\\Összegzés** elemet nem kötelező egy adatforráshoz csatlakoznia egy kimenő dokumentum egyetlen sorának létrehozásához.
    - A **Prefix3** elem a **P3** szimbólumokat generálja, amelyek azt jelzik, hogy a hozzáadott sor teljes adóértéket tartalmazza.
    - A **TotalTaxAmount** elem a következőhöz tartozik: **model.Data.Summary.Total**, a feldolgozott adózási tranzakciók adózási értékeinek összegének előállításához.
    - Az **ExecutionDateTime** elem az összegzéssor hozzáadásakor létrehozza a dátumot és az időt (ezredmásodpercekkel együtt).

    ![Leképezés lap a Formátumtervező lapon](./media/ER-DeferredSequence-Format2.png)

### <a name="run-the-imported-format"></a>Importált formátum futtatása

1. A **Formátumtervező** oldalon válassza a **Futtatás** elemet.
2. Töltse le a webböngészőből a felkínált fájlt, és nyissa meg ellenőrzésre.

    ![Letöltött fájl](./media/ER-DeferredSequence-Run.png)

Figyelje meg, hogy a 22-es összesítő sor a feldolgozott tranzakciók adózási értékeinek összegét jeleníti meg. Mivel a formátum a **model.Data.Summary.Total** használatára van beállítva, az összeg visszaadására konfigurálva, a rendszer az összeget úgy számítja ki, hogy meghívja a **TotalSum** aggregációját az **Összesített** adatforrásnak a *GroupBy* típusból, amely a modell hozzárendelését használja. Ha ezt az összesítést szeretné kiszámítani, akkor a modell-hozzárendelés minden olyan tranzakciót megismétel, amely ki van választva a **Szűrt** adatforrásban. A 21-es és 22-es sor végrehajtási idejének összehasonlításával meghatározhatja, hogy az összeg számítása 10 ezredmásodpercet (MS) igényelt. A 2-es és 21-es sor végrehajtási idejének összehasonlításával meghatározhatja, hogy az összes tranzakciós sor számítása 7 ezredmásodpercet igényelt. Ezért összesen 17 ezredmásodperc szükséges.

### <a name="modify-the-format-so-that-the-summing-is-based-on-generated-output"></a>Módosítsa úgy a formátumot, hogy az összegzés alapja a létrejövő kimenet

Ha a tranzakciók mennyisége jóval nagyobb, mint az aktuális példában szereplő mennyiség, akkor az összegző idő növekedhet, és ez a teljesítménnyel kapcsolatos problémákat okozhat. A formátum beállításának módosításával segít elkerülni ezeket a teljesítménnyel kapcsolatos problémákat. Mivel a létrejövő jelentésben szerepeltetni szeretné az adózási értékeket, ezeket az adatokat újra fel lehet használni az adózási értékek összesítéséhez. A további tudnivalókat lásd: [Formátum konfigurálása számláláshoz és összegzéshez](./tasks/er-format-counting-summing-1.md).

1. A **Formátumtervező** lapon, a **Formátum** lapon, válassza ki a **Jelentés** fájlelemet a formátumfában.
2. A **Kimeneti részletek gyűjtése** beállításnál adja meg az **Igen** értéket. Ezt a formátumot úgy konfigurálhatja, hogy egy meglévő jelentés tartalmát adatforrásként használja, amely az [Adatgyűjtés](er-functions-category-data-collection.md) kategória beépített ER-funkciói révén érhető el.
3. A **Leképezés** lapon válassza a **Jelentés\\Sorok** sorelemet.
4. Configurálja a **Gyűjtött adatkulcs neve** kifejezést erre: `WsColumn`.
5. Configurálja a **Gyűjtött adatkulcs értéke** kifejezést erre: `WsRow`.

    ![Sorok sorozatának eleme a Formátumtervező oldalon](./media/ER-DeferredSequence-Format3.png)

6. Válassza ki a **Jelentés\\Sorok\\Rekord\\TaxAmount** numerikus elemet.
7. Configurálja a **Gyűjtött adatkulcs neve** kifejezést erre: `SummingAmountKey`.

    ![TaxAmount numerikus eleme a Formátumtervező oldalon](./media/ER-DeferredSequence-Format4.png)

    Ez a beállítás figyelembe vehető a virtuális munkalapok teljesítéseként, ahol az A1-es cella értékét kiegészíti a program az összes feldolgozott adózási tranzakcióból származó adóösszeg értékével.

8. Válassza ki a **Jelentés\\Sorok\\Rekord\\RunningTotal** numerikus elemet, majd válassza a **Receptúra szerkesztése** elemet.
9. A `SUMIF(SummingAmountKey, WsColumn, WsRow)` kifejezést konfigurálja a beépített [SUMIF](er-functions-datacollection-sumif.md) ER-függvény használatával.
10. Válassza a **Mentés** lehetőséget.

    ![SUMIF kifejezés](./media/ER-DeferredSequence-FormulaDesigner.png)

11. Zárja be a **Képlettervező** lapot.
12. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
13. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Letöltött fájl](./media/ER-DeferredSequence-Run1.png)

    A 21-es sor tartalmazza az összes feldolgozott tranzakcióhoz kiszámított adóbevallások teljes összegét, amely a létrejövő kimenetet adatforrásként használja. Ez az adatforrás a jelentés elejétől kezdődik, és folytatódik a legutóbbi adózási tranzakcióig. A 22-es sor a *GroupBy* típus adatforrásának felhasználásával minden feldolgozott tranzakció adózási értékének összegét tartalmazza. Figyelje meg, hogy ezek az értékek egyenlőek. Ezért a **GroupBy** helyett a kimenet alapú összegzés használható. A 2-es és 21-es sor végrehajtási idejének összehasonlításával meghatározhatja, hogy az összes tranzakciós sor generálása és összegzése 9 ezredmásodpercet igényelt. Ennélfogva a részletes sorok létrehozásához és az adózási értékek összegzéséhez a módosított formátum megközelítőleg kétszer gyorsabb, mint az eredeti formátum.

14. Válassza ki a **Jelentés\\Sorok\\Összegzés\\TotalTaxAmount** numerikus elemet, majd válassza a **Receptúra szerkesztése** elemet.
15. A `SUMIF(SummingAmountKey, WsColumn, WsRow)` kifejezés megadása a meglévő kifejezés helyett.
16. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
17. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Letöltött fájl](./media/ER-DeferredSequence-Run2.png)

    Figyelje meg, hogy a legutóbbi tranzakció részletei sorban szereplő adózási értékek teljes összege most megegyezik az összesítő sorban szereplő összeggel.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Kimenetalapú összegzés értékének beírása a jelentés fejlécébe

Ha például meg kell adnia a jelentés fejlécében szereplő adóértékek összegét, akkor módosíthatja a formátumot.

1. A **Formátumtervező** lapon, a **Formátum** lapon, válassza ki a **Jelentés\\Sorok\\Összegzés** fájlelemet a formátumfában.
2. Válassza a **Feljebb** lehetőséget.
3. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
4. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Letöltött fájl](./media/ER-DeferredSequence-Run3.png)

    Figyelje meg, hogy a 2. összesítő sor adóértékeinek összege most 0 (nulla), mert ez az összeg már ki van számítva a létrejövő kimenet alapján. A 2. sor létrehozásakor a létrehozott kimenet még nem tartalmaz tranzakciós adatokat tartalmazó sorokat. A formátumot úgy konfigurálhatja, hogy elhalasztja a **Jelentés\\Sorok\\Összesítő** sorozata elem végrehajtását mindaddig, amíg a **Jelentés\\Sorok\\Rekord** szekvencia elemét minden adózási tranzakció esetében le nem futtatták.

### <a name="defer-the-execution-of-the-summary-sequence-so-that-the-calculated-total-is-used"></a>Az összesítő szekvencia végrehajtásának elhalasztása, hogy a kiszámított összeg használatban legyen

1. A **Formátumtervező** lapon, a **Formátum** lapon, válassza ki a **Jelentés\\Sorok\\Összegzés** fájlelemet a formátumfában.
2. Állítsa a **Halasztott végrehajtás** beállítást **Igen** lehetőségre.

    ![A Formátumtervező oldalon található Összesítő szekvencia elem halasztott végrehajtási lehetősége](./media/ER-DeferredSequence-Format5.png)

3. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
4. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Letöltött fájl](./media/ER-DeferredSequence-Run4.png)

    A **Jelentés\\Sorok\\Összegzés** szekvenciaelemet csak azután futtatja a program, hogy minden más, a szülő elemhez beágyazott elem **Jelentés\\Sorok** lefutott. Ezért akkor fut le, ha a **Jelentés\\Sorok\\Rekord** szekvenciaelem lefutott az összes adóügyi tranzakcióra a **model.Data.List** adatforrásra. Az 1., 2. és 3. sor, valamint az utolsó sor, a 22-es sor végrehajtási időpontja megmutatja ezt a tényt.

## <a name="additional-resources"></a>További erőforrások

- [Számláláshoz és összegzéshez használt formátum konfigurálása](./tasks/er-format-counting-summing-1.md)
- [Az ER-formátum végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárításához](trace-execution-er-troubleshoot-perf.md)
- [A XML-elemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-xml-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]