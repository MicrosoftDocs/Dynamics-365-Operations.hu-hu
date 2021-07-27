---
title: A XML-elemek végrehajtásának elhalasztása az ER-formátumokban
description: Ez a témakör azt mutatja be, hogyan lehet elhalasztani egy XML-elem végrehajtását egy elektronikus jelentési (ER) formátumban.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f89c671ae012907a4c3e07c09bdc867c1d67a101
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348069"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>A XML-elemek végrehajtásának elhalasztása az ER-formátumokban

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Áttekintés

A Művelettervezőt használhatja az [Elektronikus jelentési (ER)](general-electronic-reporting.md) keretrendszerben, hogy [konfigurálja](./tasks/er-format-configuration-2016-11.md) a [formátum-összetevőjét](general-electronic-reporting.md#FormatComponentOutbound) egy olyan ER-megoldásnak, amely kimenő dokumentumok XML-formában történő létrehozásához használatos. A konfigurált formátum-összetevő hierarchikus szerkezete különböző típusú formátumelemeket tartalmaz. Ezek a formátumelemek a létrejövő dokumentumok kitöltéséhez használhatók a szükséges információval, futásidőben. Alapértelmezés szerint, amikor egy ER-formátumot futtat, a formátum elemeit ugyanabban a sorrendben futtatja a rendszer, ahog a formátumhierarchiában vannak: egyesével, fentről lefelé haladva. A tervezéskor azonban bármikor módosíthatja a konfigurált formátum-összetevő bármely XML-elemének végrehajtási sorrendjét.

Ha beállítja a <a name="DeferredXmlElementExecution"></a>**Halasztott végrehajtás** beállítást a XML-elemre a konfigurált formátumban, akkor elhalaszthatja az elem végrehajtását. Ebben az esetben az elem mindaddig nem fut, amíg a szülő többi elemét nem futtatták.

Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben.

## <a name="limitations"></a>Korlátozások

A **Halasztott végrehajtás** beállítás csak olyan XML-elemekhez használható, amelyek egy olyan ER-formátumhoz vannak használatban, amely **kimenő** dokumentumok XML-formátumú létrehozásához használt.

A **Halasztott végrehajtási** beállítás csak olyan XML-elemekhez használható, amelyek csak egy másik XML-elemben vannak. Ennélfogva nem alkalmazható olyan XML-elemekre, amelyek más típusú formátumú elemekben találhatók (például egy **XML-szekvencia** elemben).

A **Halasztott végrehajtás** beállítás nem támogatott olyan XML-elemekhez, amelyek a **Közös\\Fájl** formátumban találhatók, amikor a **Fájl felosztása** beállítás **Igen** értékre van állítva. További információ az XML-fájlok felosztásáról: [Generált XML-fájlok felosztása méret és tartalommennyiség alapján](er-split-files.md).

## <a name="example-defer-the-execution-of-an-xml-element-in-an-er-format"></a><a name="Example"></a>Példa: XML-elem végrehajtásának elhalasztása egy ER-formátumban

A következő lépésekkel megtudhatja, hogy a rendszergazda vagy elektronikus jelentéskészítési tanácsadó [szerepkörrel](../sysadmin/tasks/assign-users-security-roles.md) rendelkező felhasználó hogyan konfigurálhat egy olyan, XML-elemet tartalmazó ER-formátumot, amelynél a végrehajtási sorrend eltér a formátumhierarchiában megadott sorrendtől.

Ezeket a lépéseket a **USMF** vállalatban hajthatja végre a Microsoft Dynamics 365 Finance megoldásban.

### <a name="prerequisites"></a>Előfeltételek

A jelen példa végrehajtásához hozzáféréssel kell rendelkeznie az **USMF** vállalathoz a Finance megoldásban a következő szerepkörök egyikéhez:

- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Ha még nem végezte el a példát a következő témakörben: [A szekvenciaelemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-sequence-element.md#Example), töltse le a minta ER-megoldás következő [konfigurációit](general-electronic-reporting.md#Configuration).

| Tartalom leírása            | Fájlnév |
|--------------------------------|-----------|
| ER-adatmodell konfigurációja    | [Model to learn deferred elements.version.1.xml](https://download.microsoft.com/download/7/6/0/760933ca-4ac3-4f50-bc0c-c35e596ee066/Modeltolearndeferredelements.version.1.xml) |
| ER-modell leképzési konfigurációja | [Mapping to learn deferred elements.version.1.1.xml](https://download.microsoft.com/download/c/9/c/c9c4b9dd-b700-4385-a087-a84ce9fc1d0f/Mappingtolearndeferredelements.version.1.1.xml) |

A kezdés előtt le kell tölteni és menteni kell a minta ER-megoldás következő konfigurációját a helyi számítógépre.

| Tartalom leírása     | Fájlnév |
|-------------------------|-----------|
| ER-formátum konfigurációja | [Format to learn deferred XML elements.version.1.1.xml](https://download.microsoft.com/download/4/7/8/478fa846-22e9-4fa0-89b1-d3aeae660067/FormattolearndeferredXMLelements.version.1.1.xml) |

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
    2. Válassza a **Tallózás** elemet, keresse meg és válassza ki a **Format to learn deferred XML elements.1.1.xml** fájlt, majd majd kattintson az **OK** gombra.

6. A konfigurációs fában bontsa ki a **Model to learn deferred elements** elemet.
7. Tekintse át a konfigurációs fában importált ER-konfigurációk listáját.

    ![Importált ER-konfigurációk a Konfigurációk oldalon.](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>Konfigurációszolgáltató aktiválása

1. Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Győződjön meg róla, hogy a **Honosítási konfigurációk** lap **Konfigurációs szolgáltatók** szakaszában a Litware, Inc. [konfigurációs szolgáltatója](general-electronic-reporting.md#Provider) (`http://www.litware.com`) szerepel a listán, és aktívként van megjelölve. Ha ez a konfigurációs szolgáltató nem szerepel a listán, vagy ha nem aktívként van megjelölve, hajtsa végre a [Konfigurációs szolgáltató létrehozása és megjelölje aktív](./tasks/er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit.

    ![Litware, Inc. mintavállalat a Lokalizációs konfigurációk oldalon.](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

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

        ![A TotalSum aggregációs mező a „GroupBy” paraméterek lapon.](./media/ER-DeferredXml-GroupByParameters.png)

9. Annak áttekintése, hogy hogyan kötődnek a konfigurált adatforrások az adatmodellhez, és hogy hogyan teszik elérhetővé a hozzáférhető adatokat az ER-formátum számára:

    - A **Szűrt** adatforrás az adatmodell **Data.List** mezőjéhez kötődik.
    - A **\$TaxAmount** mezője a **Szűrt** adatforrásnak az adatmodell **Data.List.Value** mezőjéhez kötődik.
    - A **TotalSum** mezője a **Csoportosított** adatforrásnak az adatmodell **Data.Summary.Total** mezőjéhez kötődik.

    ![Modell-leképezés tervező oldal.](./media/ER-DeferredXml-ModelMapping.png)

10. Zárja be a **Modell-hozzárendelés tervező** és **Modell-hozzárendelések** lapokat.

### <a name="review-the-imported-format"></a>Tekintse át az importált formátumot

1. Válassza ki a **Konfigurációk** lap konfigurációs fájában a **Format to learn deferred XML elements** konfigurációt.
2. A formátumrészletek áttekintéséhez válassza a **Tervező** elemet.
3. Válassza a **Részletek megjelenítése** lehetőséget.
4. Tekintse át azoknak az ER-formátum összetevőknek a beállításait, amelyek a kimenő dokumentumok XML-formátumban történő előállítására vannak konfigurálva, amely az adóügyi tranzakciók részletes adatait tartalmazza.

    - A **Jelentés\\Üzenet** XML-elem úgy van konfigurálva, hogy a kimenő dokumentumokat egyetlen csomóponttal töltse ki, amely tartalmazza a beágyazott XML-elemeket (**Fejléc**, **Rekord** és **Összesítás**).
    - A **Jelentés\\Üzenet\\Fejléc** XML-elem úgy van konfigurálva, hogy a kimenő dokumentumot egyetlen fejléc-csomóponttal tölti ki, amelyben a feldolgozás elindulásának dátuma és időpontja látható.
    - A **Jelentés \\Üzenet\\Rekord** XML-elem úgy van konfigurálva, hogy a kimenő dokumentumot egyetlen rekordcsomóponttal töltse ki, amely egy adótranzakció adatait jeleníti meg.
    - A **Jelentés\\Üzenet\\Összesítés** XML-elem úgy van beállítva, hogy a kimenő bizonylatot egyetlen összesítő csomóponttal töltse ki, amely tartalmazza a feldolgozott adózási tranzakciókból származó adók összegét.

    ![Üzenet XML-elem és beágyazott XML-elemek a Formátumtervező oldalon.](./media/ER-DeferredXml-Format.png)

5. A **Leképezés** lapon tekintse át a következő részleteket:

    - A **Jelentés\\Üzenet\\Fejléc** elemet nem kötelező egy adatforráshoz csatlakoznia egy kimenő dokumentum egyetlen csomópontjának létrehozásához.
    - Az **ExecutionDateTime** attribútum a fejléccsomópont hozzáadásakor létrehozza a dátumot és az időt (ezredmásodpercekkel együtt).
    - A **Jelentés\\Üzenet\\Rekord** elem a **model.Data.List** listához van kötve, és a kötött lista minden rekordjához egy rekordcsomópontot generál.
    - A **TaxAmount** attribútum a **model.Data.List.Value** elemhez tartozik (amely a következőként jelenik meg: **\@.Value** a relatív elérési út nézetben), az aktuális adózási tranzakció adózási értékének előállításához.
    - A **RunningTotal** attribútum az adózási értékek folyamatos összértékének a helyőrzője. Ez az attribútum jelenleg nem tartalmaz kimenetet, mert nincs beállítva hozzá kötelező vagy alapértelmezett érték.
    - A **ExecutionDateTime** attribútum az aktuális tranzakció feldolgozásakor a dátumot és az időt (ezredmásodpercekkel együtt) hozza létre.
    - A **Jelentés\\Üzenet\\Összegzés** elemet nem kötelező egy adatforráshoz csatlakoznia egy kimenő dokumentum egyetlen csomópontjának létrehozásához.
    - A **TotalTaxAmount** attribútum a következőhöz tartozik: **model.Data.Summary.Total**, a feldolgozott adózási tranzakciók adózási értékeinek összegének előállításához.
    - Az **ExecutionDateTime** attribútum az összefoglalás csomópont hozzáadásakor létrehozza a dátumot és az időt (ezredmásodpercekkel együtt).

    ![Leképezés lap a Formátumtervező lapon.](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>Importált formátum futtatása

1. A **Formátumtervező** oldalon válassza a **Futtatás** elemet.
2. Töltse le a webböngészőből a felkínált fájlt, és nyissa meg ellenőrzésre.

    ![Importált formátum letöltött fájlja.](./media/ER-DeferredXml-Run.png)

Figyelje meg, hogy az összesítő csomópont a feldolgozott tranzakciók adózási értékeinek összegét jeleníti meg. Mivel a formátum a **model.Data.Summary.Total** használatára van beállítva, az összeg visszaadására konfigurálva, a rendszer az összeget úgy számítja ki, hogy meghívja a **TotalSum** aggregációját az **Összesített** adatforrásnak a *GroupBy* típusból a modell hozzárendelésben. Ha ezt az összesítést szeretné kiszámítani, akkor a modell-hozzárendelés minden olyan tranzakciót megismétel, amely ki van választva a **Szűrt** adatforrásban. Az összesítő csomópont és az utolsó rekord csomópont végrehajtási idejének összehasonlításával meghatározhatja, hogy az összeg számítása 12 ezredmásodpercig (ms) tartott. Az első és utolsó rekord csomópont végrehajtási idejének összehasonlításával meghatározhatja, hogy az összes rekord csomópont generálása 9 ezredmásodpercet igényelt. Ezért összesen 21 ezredmásodperc szükséges.

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>Módosítsa úgy a formátumot, hogy a számítás alapja a létrejövő kimenet legyen

Ha a tranzakció mennyisége jóval nagyobb, mint az aktuális példában szereplő mennyiség, akkor a számítási idő növekedhet, és ez a teljesítménnyel kapcsolatos problémákat okozhat. A formátum beállításának módosításával segít elkerülni ezeket a teljesítménnyel kapcsolatos problémákat. Mivel a létrejövő jelentésben szerepeltetni szeretné az adózási értékeket, ezeket az adatokat újra fel lehet használni az adózási értékek számításához. A további tudnivalókat lásd: [Formátum konfigurálása számláláshoz és összegzéshez](./tasks/er-format-counting-summing-1.md).

1. A **Formátumtervező** lapon, a **Formátum** lapon, válassza ki a **Jelentés** fájlelemet a formátumfában.
2. A **Kimeneti részletek gyűjtése** beállításnál adja meg az **Igen** értéket. Ezt a formátumot úgy konfigurálhatja, hogy egy generált jelentés tartalmát adatforrásként használja, amely az [Adatgyűjtés](er-functions-category-data-collection.md) kategória beépített ER-funkciói révén érhető el.
3. A **Leképezés** lapon válassza a **Jelentés\\Üzenet\\Rekord** XML-elemet.
4. Configurálja a **Gyűjtött adatkulcs neve** kifejezést erre: `WsColumn`.
5. Configurálja a **Gyűjtött adatkulcs értéke** kifejezést erre: `WsRow`.

    ![Rekord XML-eleme a Formátumtervező oldalon.](./media/ER-DeferredXml-Format3.png)

6. A **Jelentés\\Üzenet\\Rekord\\TaxAmount** attribútumának kiválasztása.
7. Configurálja a **Gyűjtött adatkulcs neve** kifejezést erre: `SummingAmountKey`.

    ![TaxAmount attribútum a Formátumtervező oldalon.](./media/ER-DeferredXml-Format4.png)

    Ez a beállítás figyelembe vehető a virtuális munkalapok teljesítéseként, ahol az A1-es cella értékét kiegészíti a program az összes feldolgozott adózási tranzakcióból származó adóösszeg értékével.

8. Válassza ki a **Jelentés\\Sorok\\Rekord\\RunningTotal** attribútumot, majd válassza a **Receptúra szerkesztése** elemet.
9. A `SUMIF(SummingAmountKey, WsColumn, WsRow)` kifejezést konfigurálja a beépített [SUMIF](er-functions-datacollection-sumif.md) ER-függvény használatával, majd válassza a **Mentés** lehetőséget.

    ![SUMIF kifejezés.](./media/ER-DeferredXml-FormulaDesigner.png)

10. Zárja be a **Képlettervező** lapot.
11. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
12. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Adóérték létrehozott listája az összértékkel együtt.](./media/ER-DeferredXml-Run1.png)

    Az utolsó rekord csomópont tartalmazza az összes feldolgozott tranzakcióhoz kiszámított adóbevallások teljes összegét, amely a létrejövő kimenetet adatforrásként használja. Ez az adatforrás a jelentés elejétől kezdődik, és folytatódik a legutóbbi adózási tranzakcióig. Az összegzés csomópont a *GroupBy* típus adatforrásának felhasználásával minden feldolgozott tranzakció adózási értékének összegét tartalmazza. Figyelje meg, hogy ezek az értékek egyenlőek. Ezért a **GroupBy** helyett a kimenet alapú összegzés használható. Az első rekord csomópont és az összegzés csomópont végrehajtási idejének összehasonlításával meghatározhatja, hogy az összes rekord csomópont generálása és összegzése 11 ezredmásodpercet igényelt. Ennélfogva a rekord csomópontok létrehozásához és az adózási értékek összegzéséhez a módosított formátum megközelítőleg kétszer gyorsabb, mint az eredeti formátum.

13. Válassza ki a **Jelentés\\Üzenet\\Összegzés\\TotalTaxAmount** attribútumot, majd válassza a **Receptúra szerkesztése** elemet.
14. A `SUMIF(SummingAmountKey, WsColumn, WsRow)` kifejezés megadása a meglévő kifejezés helyett.
15. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
16. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![Adóértékek létrehozott listája szerkesztett képlettel.](./media/ER-DeferredXml-Run2.png)

    Figyelje meg, hogy a legutóbbi rekord csomópontban szereplő adózási értékek teljes összege most megegyezik az összesítő csomópontban szereplő összeggel.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Kimenetalapú összegzés értékének beírása a jelentés fejlécébe

Ha például meg kell adnia a jelentés fejlécében szereplő adóértékek összegét, akkor módosíthatja a formátumot.

1. A **Formátumtervező** lapon, a **Formátum** lapon, válassza ki a **Jelentés\\Üzenet\\Összegzés** XML-elemet a formátumfában.
2. Válassza a **Feljebb** lehetőséget.
3. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
4. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![A jelentésfejlécben található adóértékek letöltött fájlja.](./media/ER-DeferredXml-Run3.png)

    Figyelje meg, hogy az összesítő csomópont adóértékeinek összege most 0 (nulla), mert ez az összeg már ki van számítva a létrejövő kimenet alapján. Az első rekord csomópont létrehozásakor a létrehozott kimenet még nem tartalmaz tranzakciós adatokat tartalmazó rekord csomópontokat. A formátumot úgy konfigurálhatja, hogy elhalasztja a **Jelentés\\Üzenet\\Összesítő** sorozata elem végrehajtását mindaddig, amíg a **Jelentés\\Üzenet\\Rekord** szekvencia elemét minden adózási tranzakció esetében le nem futtatták.

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>Az összesítő XML-elem végrehajtásának elhalasztása, hogy a kiszámított összeg használatban legyen

1. A **Formátumtervező** lapon, a **Formátum** lapon, válassza ki a **Jelentés\\Üzenet\\Összegzés** XML-elemet a formátumfában.
2. Állítsa a **Halasztott végrehajtás** beállítást **Igen** lehetőségre.

    ![A Formátumtervező oldalon található Összesítő XML-elem halasztott végrehajtási lehetősége.](./media/ER-DeferredXml-Format5.png)

3. Válassza a **Mentés** parancsot, majd válassza a **Futtatás** elemet.
4. Töltse le és ellenőrizze a webböngészőből a felkínált fájlt.

    ![A halasztott végrehajtás letöltött fájlja.](./media/ER-DeferredXml-Run4.png)

    A **Jelentés\\Üzenet\\Összegzés** szekvenciaelemet csak azután futtatja a program, hogy minden más, a szülő elemhez beágyazott elem **Jelentés\\Üzenet** lefutott. Ezért akkor fut le, ha a **Jelentés\\Üzenet\\Rekord** szekvenciaelem lefutott az összes adóügyi tranzakcióra a **model.Data.List** adatforrásra. Az első és az utolsó rekord csomópontjainak, valamint a fejléc és az összesítő csomópontok végrehajtási ideje ezt a tényt fedi fel.

## <a name="additional-resources"></a>További erőforrások

- [Számláláshoz és összegzéshez használt formátum konfigurálása](./tasks/er-format-counting-summing-1.md)
- [Az ER-formátum végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárításához](trace-execution-er-troubleshoot-perf.md)
- [A szekvenciaelemek végrehajtásának elhalasztása az ER-formátumokban](er-defer-sequence-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
