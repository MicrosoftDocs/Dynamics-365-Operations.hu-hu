---
title: Több alkalmazási táblából származó adatok beolvasásához használja a JOIN adatforrásokat az ER-modell-leképezésekben.
description: Ez a témakör bemutatja, hogyan használhatók JOIN típusú adatforrások elektronikus jelentésekhez (ER).
author: NickSelin
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: d42016b914d7992b6f4ae1c573eb8f867ba87e22
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743977"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Több alkalmazási táblából származó adatok beolvasásához használja a JOIN adatforrásokat az elektronikus jelentéskészítési (ER) modell-leképezésekben.

[!include[banner](../includes/banner.md)]

Az elektronikus jelentéskészítési (ER) modell-leképezések vagy -formátumok konfigurálása során [hozzáadhatja](#review) az **Egyesítés** típusú adatforrásokat. A tervezéskor egy **Egyesítés** adatforrás több adatforrás-készletként van konfigurálva, amelyek mindegyike a rekordok listáját adja vissza. Az első kivételével minden adatforrás esetében meg kell határoznia a szükséges feltételeket az aktuális és a korábbi adatforrások rekordjainak egyesítéséhez. Futásidőben a konfigurált **Egyesítés** típusú adatforrás a beágyazott adatforrások rekordjaiból származó mezőket tartalmazó rekordok egyetlen összekapcsolt listáját [adja vissza](#executeERformat).

Jelenleg a következő egyesítéstípusok támogatottak:

- Külső (bal) egyesítés:
    - Az első (bal szélső) adatforrás összes rekordjának egyesítése, majd a második (jobbról balra) adatforrás konfigurált feltételeinek megfelelő rekordok egyeztetése.
- Belső (jobb) egyesítés:
    - Csak az első (bal szélső) adatforrás összes rekordjának egyesítése, majd a csak második (jobbról balra) adatforrás konfigurált feltételeinek megfelelő rekordok egyeztetése.

A konfigurált **Egyesítés** adatforrásban, amikor az összes adatforrás a **Tábla rekordja** típusú, akkor az [adatbázis szintjén](#analyze) egyetlen SQL-utasítás használatával lehet végrehajtani az egyesítési adatforrást. Ezzel az utasítással csökkenthető az adatbázis-meghívások száma, amely javítja a modell-leképezés teljesítményét. Ellenkező esetben az **Adatok egyesítése** forrás végrehajtását a memóriában végzi a rendszer.

> [!NOTE]
> A **VALUEIN** függvény használata az ER-kifejezésekben, amelyek meghatározzák, hogy milyen feltételekkel lehet egyesíteni rekordokat az Egyesítés típusú adatforrásokból még nem támogatott. Keresse fel a [Függvénytervező az elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md) oldalt az ezzel a függvénnyel kapcsolatos további részletekért.

Ha további tájékoztatást szeretne erről a funkcióról, végezze el a példafeladatot ebben a témakörben.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Példa: JOIN adatforrások használata az ER modell-leképezésekben

A következő lépések elmagyarázzák hogy a rendszergazda vagy az elektronikus jelentéskészítési fejlesztő hogyan konfigurálhatja az elektronikus jelentéskészítés (ER) model-léleképezését, ha egyszerre több alkalmazási táblából szeretné beolvasni az adatokat, ha az **Egyesítés** típusú adatforrások használatával az adatelérési teljesítmény javításához. Ezeket a lépéseket bármely Dynamics 365 Finance vagy Regulatory Configuration Service (RCS)-vállalathoz végrehajthatja.

### <a name="prerequisites"></a>Előfeltételek

A jelen témakörben szereplő példák végrehajtásához a következők egyikéhez hozzáaféréssel kell rendelkeznie, attól függően, hogy milyen szolgáltatással kívánja elvégezni a lépéseket:

**Hozzáférés a Finance alkalmazáshoz a következő szerepkörök egyikével:**

- Elektronikus jelentések fejlesztője
- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

**Hozzáférés a RCS alkalmazáshoz a következő szerepkörök egyikével:**

- Elektronikus jelentések fejlesztője
- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Mindemelett először el kell végeznie a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárás lépéseit.

Előzetesen le kell töltenie a [Microsoft letöltőközpontból](https://go.microsoft.com/fwlink/?linkid=000000) a következő minta konfigurációs fájlokat, és helyben el kell mentenie azokat:

| **Tartalom leírása**  | **Fájlnév**   |
|--------------------------|-----------------|
| A minta **ER-adatmodell** konfigurációs fájl, amelyeket a példákban adatforrásként használunk.| [Model to learn JOIN data sources.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| A minta **ER-modelleképezés** konfigurációs fájl, amely az ER adatmodellt implementálja a példákhoz. | [Mapping to learn JOIN data sources.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Minta **ER-formátum** konfigurációs fájl. Ez a fájl leírja azokat az adatokat, amelyek a példákban szereplő ER formátumú összetevőt töltik fel. | [Format to learn JOIN data sources.version.1.1.xml](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

### <a name="activate-a-configurations-provider"></a>Konfigurációs szolgáltató aktiválása

1. Eléri a Finance-t vagy az RCS-t a webböngésző első munkamenetében.
2. Ugorjon a **Szervezeti adminisztráció \> Munkaterületek \> Elektronikus jelentés** pontra.
3. Győződjön meg róla, hogy a **Honosítási konfigurációk** lap **Konfigurációs szolgáltatók** szakaszában a [Litware, Inc.](http://www.litware.com) konfigurációs szolgáltatója szerepel a listán, és **Aktívként** van megjelölve. Ha nem látja ezt a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltató létrehozása, és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

    ![Elektronikus jelentések munkaterülete](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>Minta ER-formátumkonfigurációs-fájlok importálása

1. Válassza a **Jelentéskészítési konfigurációk** elemet.
2. Importálja az ER adatmodell konfigurációs fájlját.
    1. **Árfolyam** kijelölése.
    2. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3. A **Tallózás** gombra kattintva megkeresheti a **Model to learn JOIN data sources.version.1.1.xml** fájlt.
    4. Válassza ki az **OK** lehetőséget.
3. Importálja az ER modell-leképezés konfigurációs fájlját.
    1. **Árfolyam** kijelölése.
    2. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3. A **Tallózás** gombra kattintva megkeresheti a **Mapping to learn JOIN data sources.version.1.1.xml** fájlt.
    4. Válassza ki az **OK** lehetőséget.
4. Az ER formátumkonfigurációs fájl importálása.
    1. **Árfolyam** kijelölése.
    2. Kattintson a **Betöltés XML-fájlból** lehetőségre.
    3. A **Tallózás** gombra kattintva megkeresheti a **Format to learn JOIN data sources.version.1.1.xm** fájlt.
    4. Válassza ki az **OK** lehetőséget.
5. A konfigurációk fában bontsa ki a **Model to learn JOIN data sources** eleme, illetve a további modellelemeket (ha rendelkezésre állnak).
6. Figyelje meg az ER konfigurációk listáját a fában, valamint a verziószám adatait a **Verziók** gyorslapon – ezeket a program a minta jelentéshez tartozó adatok forrásaként fogja használni.

    ![Elektronikus jelentéskészítési konfigurációk oldala](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Végrehajtási nyomkövetési beállítások bekapcsolása

1. Válassza a **KONFIGURÁCIÓK** lehetőséget.
2. Válassza a **Felhasználói paraméterek** lehetőséget.
3. A végrehajtási nyomkövetési paramétereket állítsa be a lenti képen látható módon.

    ![Elektronikus jelentéskészítés felhasználói paraméterei lap](./media/GER-JoinDS-Parameters.PNG)

    Ha ezek a paraméterek be vannak kapcsolva, akkor az importált automatikus fájlformátum minden végrehajtásához létrejön a végrehajtási nyomkövetés. A létrejövő végrehajtási nyomkövetés segítségével elemezheti a program az ER formátum és a ER modell-leképezési összetevők végrehajtását. Az ER végrehajtási nyomonkövetés funkcióval kapcsolatos további információkért látogasson el [Az ER-formátum végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárításához](trace-execution-er-troubleshoot-perf.md) oldalra.

### <a name="review-er-model-mapping-part-1"></a>Az ER modell-leképezés áttekintése (1. rész)

Az ER modell-leképezési összetevő beállításainak áttekintése. Az összetevő úgy van beállítva, hogy az **Egyesítés** típusú adatforrások használata nélkül hozzáférjen a konfigurációk verzióival kapcsolatos adatokhoz, illetve a konfigurációk és a konfigurációs szolgáltatók adataihoz.

1. Válassza ki a **Mapping to learn JOIN data sources** konfigurációt.
2. Válassza ki a **Tervezőt** a leképezések listájának megnyitásához.
3. A leképezésirészletek áttekintéséhez válassza a **Tervező** elemet.
4. Válassza a **Részletek megjelenítése** lehetőséget.
5. Bontsa ki a konfigurációk fastruktúrájában a **Set1** és a **Set1.Details** adatmodell-elemeket:

    1. A **Részletek: Rekordlista = Verziók** társítás jelzi, hogy a **Set1.Details** elem társítva van a **Verziók** adatforráshoz és az **ERSolutionVersionTable** tábla rekordjait adja vissza. Ennek a táblának minden rekordja egy ER konfiguráció egyetlen változatát jelöli. Ennek a táblának a tartalma a **Konfigurációk** lap **Verziók** gyorslapján jelenik meg.
    2. A **ConfigurationVersion: String = @.PublicVersionNumber** társítása azt jelenti, hogy az összes ER konfiguráció verziójának nyilvános verziójának értéke az **ERSolutionVersionTable** tábla **PublicVersionNumber** mezőjéből származik, és a **ConfigurationVersion** elembe kerül.
    3. A **ConfigurationTitle: String = @.'>Relations'.Solution.Name** kötése azt jelzi, hogy az ER konfiguráció neve a **Név** mezőből származik az **ERSolutionTable** táblából,amely egy a sokhoz kapcsolattal (**'>Kapcsolatok'**) használatával mér fel az **ERSolutionVersionTable** és **ERSolutionTable** táblák között. Az aktuális alkalmazáspéldány ER konfigurációinak nevei a konfigurációk lap **Konfigurációk** fájában jelennek meg.
    4. A **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** kötése azt jelzi, hogy az konfigurációszolgáltató neve, aki az aktuális konfiguráció tulajdonosa a **Név** mezőből származik az **ERVendorTable** táblából,amely egy a sokhoz kapcsolattal ('>Kapcsolatok') használatával mér fel az **ERSolutionVersionTable** és **ERVendorTable** táblák között. Az ER konfigurációszolgáltatók nevei a **Konfigurációk** lapon az egyes konfigurációk oldalfejlécében jelennek meg. Az összes konfigurációs szolgáltató listája a **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációs szolgáltató** tábla lapján érhető el.

    ![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/GER-JoinDS-Set1Review.PNG)

6. Bontsa ki a konfigurációk fastruktúrájában a **Set1.Summary** adatmodell-elemet:

    1. A **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** társítása azt jelzi, hogy a **Set1.Summary.VersionsNumber** elem társítva van a **VersionsNumber** egyesített mezőjéhez a **VersionsSummary** adatforrásnak a **GroupBy** típus alatt, amely úgy van knfigurálva, hogy az **ERSolutionVersionTable** rekordajinak számát adja vissza a **Verziók** adatforráson keresztül.

    ![GROUPBY adatforrás paraméterek lapja](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. Zárja be a lapot.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a>Az ER modell-leképezés áttekintése (2. rész)

Az ER modell-leképezési összetevő beállításainak áttekintése. Az összetevő úgy van beállítva, hogy az **Egyesítés** típusú adatforrások egyikénke használatával hozzáférjen a konfigurációk verzióival kapcsolatos adatokhoz, illetve a konfigurációk és a konfigurációs szolgáltatók adataihoz.

1. Bontsa ki a konfigurációk fastruktúrájában a **Set2** és a **Set2.Details** adatmodell-elemeket. A **Details: Record list = Details** társítás azt jelzi, hogy a **Set2.Details** elem társítva van a **Részletek** adatforrással, amely az **Egyesítés** típus adatforrásaként van konfigurálva.

    ![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/GER-JoinDS-Set2Review.PNG)

    Az **Egyesítés** adatforrás a **Functions\Join** adatforrás kiválasztásával adható hozzá:

    ![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/GER-JoinDS-AddJoinDS.PNG)

2. Válassza ki a **Részletek** adatforrást.
3. Válassza az **Adatforrás** ablaktábla **Szerkesztés** elemét.
4. Válassza ki az **Egyesítés szerkesztése** opciót.
5. Válassza a **Részletek megjelenítése** lehetőséget.

    ![A JOIN adatforrás paraméterek lapja](./media/GER-JoinDS-JoinDSEditor.PNG)

    Ez a lap az **Egyesítés típus** szükséges adatforrásának tervezéséhez használatos. Futásidőben ezt az adatforrás egyetlen egyesített rekordlistát fog létrehozni az **Egyesített lista** rács adatforrásaiból. A rekordok egyesítése a rácsban elsőként megadott **ConfigurationProviders** -adatforrás alapján kezdődik (a **Típus** oszlop üres). Minden más adatforrás egymás után lesz egyesítve a szülő adatforrás rekordjaihoz ennek a rácsnak a sorrendje alapján. Minden csatlakozó adatforrást a cél-adatforrás alá beágyazott adatforrásként kell konfigurálni (az `1Versions` adatforrás az `1Configurations` alá van beágyazva, az `1Configurations` adatforrás a **ConfigurationProviders** alá van beágyazva). Minden konfigurált adatforrásnak tartalmaznia kell az egyesítés feltételeit. Az adott **Egyesítéshez** tartozó adatforrásban a következő egyesítések vannak meghatározva:

    - A **ConfigurationProviders** adatforrás mindegyik rekordja (hivatkozva az **ERVendorTable** táblára) csak az **1Configurations** rekordokkal van egyesítve (a **ERSolutionTable** táblára hivatkozva) ugyanazzal az értékkel, mint a **SolutionVendor** és a **RecId** mező értékei. A **Belső egyesítés** használatos ehhez az egyesítéshez, valamint következő feltételek a rekordok egyeztetéséhez:

    SZŰRŐ (Configurations, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Az **1Configurations** adatforrás mindegyik rekordja (hivatkozva az **ERSolutionTable** táblára) csak az **1Versions** rekordjaival van egyesítve (az **ERSolutionVersionTable** táblára hivatkozva) ugyanazzal az értékkel, mint a **Solution** és a **RecId** mező értékei. A **Belső egyesítés** használatos ehhez az egyesítéshez, valamint következő feltételek a rekordok egyeztetéséhez:

    SZŰRŐ (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - A **végrehajtás** beállítás **Lekérdezésként** van beállítva, amely azt jelenti, hogy ez az adatforrás egyesítés az adatbázis szintjén futásidőben lesz végrehajtva közvetlen SQL-meghívásként.

    Az alkalmazási táblákat képviselő adatforrások rekordjainak egyesítése esetén az egyesítés feltételeit úgy adhatja meg, ha olyan mezőkat használ, amelyek nem írják le az AOT-kapcsolatokat ezen táblák között. Az ilyen típusú egyesítés beállítható az adatbázis szintjén történő végrehajtásra is.

6. Zárja be a lapot.
7. Válassza a **Mégse** lehetőséget.
8. Bontsa ki a konfigurációk fastruktúrájában a **Set2.Summary** adatmodell-elemet:

    - A **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** társítása azt jelzi, hogy a **Set2.Summary.VersionsNumber** elem társítva van a **VersionsNumber** egyesített mezőjéhez a **DetailsSummary** adatforrásnak a **GroupBy** típus alatt, amely úgy van konfigurálva, hogy az **Details** egyesített rekordjainak számát adja vissza az **Egyesített** típusban.
    - A **Végrehajtás** helybeállítás **Lekérdezésként** van beállítva, amely azt jelenti, hogy ez a **GroupBy** adatforrás futásidőben lesz futtatva közvetlen SQL-meghívásként. Ez a viselkedés azért lehetséges, mert az **Egyesítés** típusú **Részletek** alapadatforrás-adatait az adatbázis szintjén hajtják végre.

    ![GROUPBY adatforrás paraméterek lapja](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. Zárja be a lapot.
10. Válassza a **Mégse** lehetőséget.

### <a name="execute-er-format"></a><a name="executeERformat"></a> ER formátum végrehajtása

1. Érje el a Finance-t vagy RCS-t egy második munkamenetben a böngészőjében ugyanazon hitelesítő adatoka és vállalatot használva, mint az első munkamenetben.
2. Nyissa meg a következőt: **Szervezeti adminisztráció \> Elektronikus jelentéskészítés \> Konfigurációk**.
3. Bontsa ki a **Model to learn JOIN data sources** konfigurációt.
4. Válassza ki a **Format to learn JOIN data sources** konfigurációt.
5. Válassza a **Tervező** lehetőséget.
6. Válassza a **Részletek megjelenítése** lehetőséget.
7. Válassza ki **Hozzárendelés** lehetőséget.
8. Válassza a **Kibontás/Összecsukás** lehetőséget.

    Ez a formátum úgy van kialakítva, hogy egy ER konfiguráció minden verziójának új sorával töltse fel a létrejövő szövegfájlt (**Verzió** sorozat). Minden létrehozott sor tartalmazni fogja az aktuális konfigurációt birtokló konfigurációszolgáltató nevét, a konfiguráció nevét és a konfiguráció verzióját pontosvesszővel elválasztva. A létrejövő fájlok végleges sora az ER konfigurációk felismert verzióinak számát fogja tartalmazni **( Összegzés** sorozat).

    ![ER-formátumtervező oldal](./media/GER-JoinDS-FormatReview.PNG)

    Az **Adatok** és az **Összegzés** adatforrások a konfigurációs verziók adatainak a létrejövő fájlra történő feltöltésekor használatosak:

    - A **Set1** adatmodellből származó adatokat akkor használja a program , ha a felhasználó párbeszédpanelén a **Nem** lehetőséget választja a **Kiválasztó** adatforrás számára, amikor az ER formátumot futtatja.
    - A **Set2** adatmodellből származó adatokat akkor használja a program , ha a felhasználó párbeszédpanelén az **Igen** lehetőséget választja a **Kiválasztó** adatforrás számára, amikor az ER formátumot futtatja.

    ![ER-formátumtervező oldal](./media/GER-JoinDS-FormatMappingReview.PNG)

9. Válassza a **Futtatás** parancsot.
10. Válassza a párbeszédpanel lap **nem** elemét a **JOIN adatforrás használata** mezőben.
11. Válassza ki az **OK** lehetőséget.
12. Előállított fájl megtekintése.

    ![ER felhasználói párbeszédpanel](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Az ER formátum végrehajtási nyomkövetésének elemzése

1. A Finance vagy RCS első munkamenetében válassza a **Tervező** elemet.
2. Válassza a **Teljesítménykövetés** elemet.
3. A **Teljesítmény-nyomkövetés** rácsban válassza ki azt a legfelső rekordot, amely az aktuális modell-hozzárendelési összetevőt használó ER-formátum legutóbbi végrehajtási nyomonkövetése.
4. Válassza ki az **OK** lehetőséget.

    A végrehajtási statisztikák az alkalmazások tábláinak ismétlődő meghívásairól tájékoztatják:

    - Az **ERSolutionTable** meghívása ugyanannyiszor történik, mint ahány konfigurációs verzió rekordja van az **ERSolutionVersionTable** táblában, ugyanakkor az ilyen meghívások száma csökkenthető a teljesítmény javítása érdekében.
    - Az **ERVendorTable** meghívása kétszer történik minden felfedezett konfigurációs verzió rekordjához az **ERSolutionVersionTable** táblában, ugyanakkor az ilyen meghívások száma is csökkenthető.

    ![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/GER-JoinDS-Set1Run2.PNG)

5. Zárja be a lapot.

### <a name="execute-er-format"></a> ER formátum végrehajtása

1. Váltson át a második Finance vagy RCS munkamenetet tartalmazó webböngészőlapra.
2. Válassza a **Futtatás** parancsot.
3. Válassza a párbeszédpanel lap **Igen** elemét a **JOIN adatforrás használata** mezőben.
4. Válassza ki az **OK** lehetőséget.
5. Előállított fájl megtekintése.

    ![ER felhasználói párbeszédpanel](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> Az ER formátum végrehajtási nyomkövetésének elemzése

1. A Finance vagy RCS első munkamenetében válassza a **Tervező** elemet.
2. Válassza a **Teljesítménykövetés** elemet.
3. A **Teljesítmény-nyomkövetés** rácsban válassza ki azt a legfelső rekordot, amely az aktuális modell-hozzárendelési összetevőt használó ER-formátum legutóbbi végrehajtási nyomonkövetését jelzi.
4. Válassza ki az **OK** lehetőséget.

    A statisztika a következőkről tájékoztat:

    - Az alkalmazás-adatbázis hívása egyszer megtörtént az **ERVendorTable**, **ERSolutionTable** és **ERSolutionVersionTable** táblák rekordjainak lekéréséhez a szükséges mezők eléréséhez.

    ![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/GER-JoinDS-Set2Run2.PNG)

    - Az alkalmazás-adatbázis hívása egyszer történik a konfigurációs verziók számának kiszámításához a **Részletek** adatforrásban megadott egyesítések segítségével.

    ![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>Korlátozások

Amint a témakör példájában látható, az **EGYESSÍTÉS** adatforrás több olyan adatforrásból is elvégezhető, amely leírja azon rekordok egyedi adathalmazait, amelyeket végül egyesíteni kell. Ezeket az adatforrásokat a beépített ER [SZŰRŐ](er-functions-list-filter.md) funkcióval lehet konfigurálni. Amikor az adatforrás úgy van beállítva, hogy az az **EGYESÍTÉS** adatforráson túl legyen meghívva, az adatválasztás feltételei részeként használhat vállalattartományokat. Az **EGYESÍTÉS** adatforrás kezdeti implementációja nem támogatja az ilyen típusú adatforrásokat. Ha például egy [SZŰRŐ](er-functions-list-filter.md)alapú adatforrást hív meg egy **EGYESÍTÉS** adatforrás végrehajtásának hatókörén belül, akkor kivétel történik, ha a meghívott adatforrás az adatválasztási feltételének részeként tartalmaz vállalati tartományokat.

A Microsoft Dynamics 365 Finance 10.0.12 verzió (2020. augusztus) esetében a vállalati tartományokat is használhat az adatválasztás feltételének [SZŰRŐ](er-functions-list-filter.md) alapú adatforrásokban, amely egy **EGYESÍTÉS** adatforrás végrehajtásának hatókörében lettek meghívva. Az alkalmazás [lekérdezés](../dev-ref/xpp-library-objects.md#query-object-model) szerkesztőjének korlátai miatt a vállalati tartományok csak az **EGYESÍTÉS** adatforrás első adatforrásához használhatók.

### <a name="example"></a>Példa

Például egyetlen meghívást kell kezdeményezni az alkalmazás-adatbázishoz, hogy lekérje a több vállalatot érintő külkereskedelmi tranzakciók listáját, valamint az ezekben a tranzakciókban hivatkozott készletadatok lekéréséhez.

Ebben az esetben a következő műtermékeket konfigurálja az ER modell-leképezésekben:

- **Intrastat** gyökéradatforrás, amely az **Intrastat** táblát jelöli.
- **Cikke** gyökéradatforrás, amely az **InventTable** táblát jelöli.
- **Vállalatok** gyökéradatforrás, amely a vállalatok listáját adja vissza ( ebben a példában a **DEMF** és a **GBSI**), ahol a tranzakciókat el kell érni. A vállalati kód a **Companies.Code** mezőből érhető el.
- **X1** gyökéradatforrás, amelyben a `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))` kifejezés szerepel. Az adatválasztás feltételének részeként ez a kifejezés a vállalati tartományok definícióját tartalmazza `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`.
- **X2** adatforrás beágyazott elemként az **X1** adatforrás számára. A `FILTER (Items, Items.ItemId = X1.ItemId)` kifejezést tartalmazza.

Végezetül konfigurálhat egy **EGYESÍTÉS** adatforrást, ahol az **X1** az első adatforrás, az **X2** pedig a második adatforrás. Az adatforrásnak az adatbázis szintjén történő futtatásának kényszerítéséhez beállíthatja, hogy a **Lekérdezés** a **Végrehajtás** beállításként közvetlen SQL-hívásként fusson.

Amikor a konfigurált adatforrás a végrehajtása történik, amikor az ER-végrehajtás [nyomon követett](trace-execution-er-troubleshoot-perf.md), a következő utasítás jelenik meg az ER modell-leképezés-tervezőben az ER teljesítményének nyomon követése részeként.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> Hiba történik, ha olyan **EGYESÍTÉS** adatforrást futtat, amely úgy van beállítva, hogy olyan adatkiválasztási feltételeket tartalmazzon, amelyek vállalat-tartományokat tartalmaznak a végrehajtott **EGYESÍTÉS** adatforrás további adatforrásaihoz.

## <a name="additional-resources"></a>További erőforrások

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Az ER-formátum végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárításához](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]