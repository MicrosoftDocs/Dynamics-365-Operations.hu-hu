---
title: Oszlopdefiníciók a pénzügyi jelentésben
description: Ez a cikk az oszlopdefiníciókról nyújt információkat. Egy oszlopdefiníció egy jelentés-összetevő, amely meghatározza az oszlopok tartalmait egy jelentésben.
author: aprilolson
ms.date: 10/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 106601
ms.assetid: 66e72a48-edab-4e9d-815f-596a1623c258
ms.search.form: FinancialReports
ms.openlocfilehash: 97f6c869e8d05e37ec3001d5de262ab8927d735a
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802796"
---
# <a name="column-definitions-in-financial-reports"></a>Oszlopdefiníciók a pénzügyi jelentésben

[!include [banner](../includes/banner.md)]

Ez a cikk az oszlopdefiníciókról nyújt információkat. Egy oszlopdefiníció egy jelentés-összetevő vagy építőelem, amely meghatározza az oszlopok tartalmait egy jelentésben. Például a sordefiníciók, az alap oszlopdefiníciókat több jelentésben is használhatják.

## <a name="create-and-modify-a-column-definition"></a>Oszlopdefiníciű létrehozása és módosítása

Az oszlopdefiníció 2 - 255 oszlopot tartalmazhat.

### <a name="create-a-column-definition"></a>Oszlopdefiníció létrehozása

1. A Jelentéstervező navigációs ablakában kattintson az Oszlopdefiníciók **elemre**.
2. Kattintson a Fájl **menü** Új **parancsára**, majd az Oszlopdefiníció **elemre**.
3. Adja hozzá a oszlopdefiníció tartalmát.

### <a name="open-a-column-definition"></a>Oszlopdefiníció megnyitása

1. A Jelentéstervező navigációs ablakában kattintson az Oszlopdefiníciók **elemre**.
2. A megnyitáshoz kattintson duplán egy oszlopdefinícióra.

### <a name="add-a-column-to-a-column-definition"></a>Oszlop hozzáadása oszlopdefinícióhoz

1. A Jelentéstervezőben kattintson az Oszlopdefiníciók **elemre**, majd nyissa meg a módosítani szeretné az oszlopdefiníciót.
2. Válassza ki azt az oszlopot, ahová új oszlopot szeretne beszúrni.
3. Kattintson a Szerkesztés **menü** Beszúrás **oszlopára**. Az új oszlop megjelenik a kijelölt oszloptól balra.

### <a name="delete-a-column-from-a-column-definition"></a>Oszlop törlése oszlopdefinícióból

1. A Jelentéstervezőben kattintson az Oszlopdefiníciók **elemre**, majd nyissa meg a módosítani szeretné az oszlopdefiníciót.
2. Jelölje ki a törölni kívánt oszlopot.
3. Kattintson a **Szerkesztés** menü Törlés **oszlopára**.

## <a name="contents-of-a-column-definition"></a>Az oszlopdefiníció tartalma
Egy oszlopdefiníció a következő információkat tartalmazza:

- Egy oszlop a sordefiníció leírásai számára
- Olyan összegoszlopok, amelyek a pénzügyi adatokból vagy az oszlopdefinícióban található más adatokon alapuló számításokból mutatnak adatokat
- Oszlopok formázása
- Attribútumoszlopok

Ez az információ az oszlopdefiníció következő területein jelenik meg:

- Az oszlopdefiníciók fejlécek területe tartalmazza a fejlécszöveget és azt a formázást, amely a jelentésben szerepel. A fejléc vonatkozhat csak egyetlen adatoszlopra, több oszlopra, vagy feltételes alapon is vonatkozhat oszlopokra. Az oszlopdefinícióban tetszőleges számú oszlopfejlécsort adhat meg.

    > [!NOTE]
    > Az oszlopfejlécek a jelentés egyes adatoszlopaira érvényesek. A jelentésfejlécek a teljes jelentésre érvényesek. A jelentésfejléceket a jelentésdefiníció **Fejlécek és lábléc** lapján lehet definiálni.

- Az oszlop részletsorok a fejlécsorok alatti sorok a oszlopdefinícióban. Az oszloprészletsorok a jelentésbe kerülő információt határozzák meg. Az alábbi táblázat az oszlop részletsorokat foglalja listába és írja le.

    | Az oszlop részletetsor neve                                                | Leírás                                                    |
    |-----------------------------------------------------------------------|-------------------------------------------------------------------------|
    | Oszloptípus                                                           | (Kötelező) Adja meg az oszlopban szereplő adatok típusát.                                      |
    | Könyvelési kód / Attribútumkategória                                          | Adja meg a pénzügyi adatok információit a **FD** és **ATTR** típusú oszlopokhoz.     |
    | Pénzügyi év időszakai - Érintett időszakok                                    | Adja meg a pénzügyi adatok információit a **FD** típusú oszlopokhoz.              |
    | Receptúra                                                               | Adja meg a számítási képletet a **CALC** típusú oszlopokhoz.                  |
    | Oszlopszélesség - Több szóköz az oszlop előtt - Formátumfelülíró nyomtatásvezérlés | Speciális formátumbeállítások megadása.                                               |
    | Oszlopkorlátozások                                                   | Korlátozza az adatokat.                                                                        |
    | Jelentésii egység                                                        | Korlátozza az oszlopot, hogy csak a meghatározott jelentési egységre vonatkozó adatokat mutassa.      |
    | Pénznem megjelenítése - Pénznemszűrő                                      | Pénznem formázása.                                                                      |
    | Dimenziószűrő                                                      | Adja meg a szűrőt, amivel az adatokat csak adott pénzügyiadat-jelentő egységekre korlátozhatja.           |
    | Attribútumszűrő                                                      | Adja meg egy szűrőt a pénzügyi adatok korlátozására.                                      |
    | Kezdő dátum záró dátum                                                   | A pénzügyi adatokat megadott dátumokra korlátozza.                                    |
    | Indoklás                                                         | Balra, középre vagy jobbra igazítja a sordefinícióban megadott leíró szöveget. |

## <a name="column-restrictions-in-a-column-definition"></a>Oszlopkorlátozások egy oszlopdefinícióban
Oszlopkorlátozások segítségével megadhatja, hogy egy oszlopdefiníció hogyan használja az adatokat vagy azámítson ki információkat. Továbbá korlátozhat például adott egységre vagy adott dátumokra egy jelentésoszlopot.

> [!NOTE]
> Az **oszlopkorlátozási** kódok felülbírálják a sordefinícióban található ütköző beállításokat.

### <a name="column-restrictions-cell"></a>Oszlopkorlátozási cella

Az **Oszlopra vonatkozó korlátozások** cellában olyan kódok is lehetnek, amelyek az adott oszlopra vonatkozó információkat, például sorformázást, részleteket és összegeket tartalmaznak.

#### <a name="add-a-column-restriction-in-a-column-definition"></a>Oszlopkorlátozások hozzáadása egy oszlopdefinícióban

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. A korlátozáshoz kattintson **duplán** az oszlopra vonatkozó Oszlopkorlátozási cellára.
3. Az Oszlopkorlátozások **párbeszédpanelen** válasszon ki egy vagy több kódot a listából, majd kattintson az **OK gombra**.

### <a name="column-restriction-codes"></a>Oszlopkorlátozási kódok

A következő táblázat az oszlopkorlátozás kódokat írja le.

| Oszlopkorlátozás kód | Leírás |
|-------------------------|-------------|
| SU                      | Az oszlop aláhúzásjelének elrejtése, ha aláhúzás parancs (**---**) vagy dupla aláhúzás parancs (**===**) van megadva a sordefinícióban. Például előfordulhat, hogy nem szeretné aláhúzni azokat az összegeket, amelyeket egy százalékszámítás adott. |
| ST                      | Összegek letiltása, így csak a részletek jelennek meg az oszlopban (például statisztikai oszlopnál). |
| SD                      | Részletek letiltása, hogy csak a **TOT** és **CAL** sorok jelenjenek meg (a sordefinícióból) az oszlopban. |
| ST                      | Az összegek korlátozása kizárólag tartozik összegekre egy **FD** oszlopban. |
| CR                      | Az összegek korlátozása kizárólag követel összegekre egy **FD** oszlopban. |
| Kiig.                     | Az oszlop összegeinek korlátozása periódushelyesbítési összegekre, ha vannak ilyen összegek elérhetőek. |
| XAD                     | Az összegek korlátozása az oszlopban úgy, hogy a periódushelyesbítések ne jelenjenek meg. |
| Tervezett átadás                      | Az összegek korlátozása az oszlopban úgy, hogy csak a feladott tranzakciók jelenjenek meg, ha vannak ilyen tranzakciók elérhetőek. |
| UPT                     | Az összegek korlátozása az oszlopban úgy, hogy csak a fel nem adott tranzakciók jelenjenek meg, ha vannak ilyen tranzakciók elérhetőek.<p><strong>Megjegyzés:</strong> Nem minden adatszolgáltató támogatja a fel nem adott tranzakciók használatát. </p> |

### <a name="restrict-a-column-to-a-reporting-unit"></a>Oszlop korlátozása egy jelentési egységre

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. A korlátozáshoz kattintson **duplán** az oszlop jelentésiegység-cellájára.
3. A Jelentési **egység kiválasztása** párbeszédpanel Jelentési **fa** listájáról válasszon ki egy fát.
4. Bontsa ki vagy csukja össze az egységek listáját, válasszon ki egy jelentésegységet, és kattintson az **OK** gombra.

## <a name="format-column-headers"></a>Oszlopfejlécek formázása
Hozzáadhat, módosíthat és törölhet olyan fejléceket, amelyek a jelentés oszlopainak tetején jelennek meg. A feltételes spanning **oszlopfejléceket**  **az** oszlopdefiníciók Időszak mezője és a jelentésdefiníciók Alapidőszak mezője alapján is beállíthatja. Az alapidőszak funkció segítségével időt takaríthat meg a gördülő előrejelzési jelentések létrehozásakor.

### <a name="create-and-manage-column-headers"></a>Oszlopfejlécek létrehozása és kezelése

Az Oszlopfejléc **párbeszédpanelen** hozzáadhatja, módosíthatja vagy törölheti a jelentés oszlopainak tetején megjelenő fejléceket. Az alábbi táblázat az Oszlopfejléc **párbeszédpanel mezőit** írja le.

| Mező                 | Leírás |
|-----------------------|-------------|
| Oszlopfejléc szöveg    | Ez a szöveg az oszlop fejlécében jelenik meg. Közvetlenül ebbe a mezőbe írhatja be a szöveget, vagy az Automatikus **szöveg beszúrása gombra kattintva kiválaszthat egy olyan beállítást,** amely a jelentés minden generálása esetén frissíti az oszlopfejlécet. Ha több automatikusszöveg-kódot is fel kell foglalni, kattintson **ismét az Automatikus** szöveg beszúrása gombra, majd kattintson a listában egy másik kódra. |
| Formátumbeállítások        | Formázás (például mező vagy aláhúzás) alkalmazása egy oszlopfejlécre. |
| Ettől terjed Eddig terjed | Azon oszlop vagy oszlopok meghatározása, amelyre a fejlécszöveg vonatkozik. |
| Indoklás         | Adja meg az oszlopfejléc szövegének igazítását azon oszlopra vagy oszloptartományra, amelyet az **Ettől terjed** és az **Eddig terjed** mezőkben meghatározott. |

### <a name="create-a-column-header"></a>Oszlopfejléc létrehozása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Kattintson duplán egy fejléccellára.
3. Az Oszlopfejléc **párbeszédpanelen** írja be az oszlop fejlécének szövegét. Másik lehetőségként kattintson az **Automatikus szöveg beszúrása parancsra**, és válasszon egy lehetőséget.
4. A **Formázási beállítások** mezőben válassza ki a fejléc formátumát.
5. Az **Ettől terjed** mezőbe írja be annak az oszlopnak a betűjét, ahonnan az oszlopfejlécet kezdeni szeretné. Az **Eddig terjed** mezőbe írja be annak az oszlopnak a betűjét, ameddig az oszlopfejlécet folytatni szeretné.
6. Az **Igazítás** elemnél válassza ki, hogy az oszlopfejléc szövege jobbra, középre vagy balra igazított legyen.
7. Kattintson az **OK** gombra.

### <a name="add-a-column-header-row"></a>Oszlopfejlécsor hozzáadása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Jelöljön ki egy cellát a fejlécsorban.
3. Kattintson a Szerkesztés **menü** Sor beszúrása **parancsára**. A program a 2. lépésben kijelölt sor fölé szúrja be az új sort.

> [!NOTE]
> Megjegyzés: Ha a jelentés jelentésben a fejlécek négy vagy több sort tartalmaznak, a fejléc átfedésbe kerül, amikor a jelentést az Excel munkafüzetbe exportálják. A jelentés összes fejlécének megtekintéséhez növelje meg a felső margót a jelentésdefinícióban.

### <a name="delete-a-column-header-row"></a>Oszlopfejlécsor törlése

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. A fejlécsorban válassza ki a törölni kívánt cellát.
3. Kattintson a **Szerkesztés** menü Sor **törlése parancsára**.

### <a name="create-an-automatically-generated-header"></a>Automatikusan generált fejléc létrehozása

A Jelentéstervező automatikusan oszlopfejléceket generálhat a készszövegkódok alapján. A készszövegkódok változók, amelyek minden jelentés előállításának alkalmával frissülnek. Bármely oszlopfejléc tartalmazhat ilyen kódokat, amelyek változó jelentésinformációkat, például dátumokat vagy időszakszámokat adhatnak meg. Ezért egy oszlopdefiníciót több jelentésdefiníciókhoz, időszakhoz és jelentési fához használhat. Mivel a készszövegkódok az oszlopdefiníció részletsorainak naptárinformációjára alapszanak, ezért csak **CALC** és **FD** oszlopoknál használhatóak. Egy készszövegkód megjelenésének módja az oszlopfejlécben befolyásolja az információ megjelenését a jelentésben. Az **Oszlopfejléc** párbeszédablakban a készszövegkódok kis- és nagybetűket egyaránt használva jelennek meg. Így a szöveg is kis- és nagybetűkkel jelenik meg a jelentésben. Egy normál naptári évben például a **\@CalMonthLong** kód használata esetén a **7**. hónap **júliusként** jelenik meg. Ha a hónap nevét csupa nagybetűvel szeretné látni (például **JÚLIUS**), akkor a készszövegkódot csupa nagybetűvel kell megadni az **Oszlopfejléc szövege** mezőben. Így például a **\@CALMONTHLONG** kódot kell beírni. A kódokat és a szövegeket össze is kombinálhatja. Például a következőt is beírhatja az oszlopfejléc szövegébe: **Period \@FiscalPeriod-\@FiscalYear from \@StartDate to \@EndDate**. A létrehozott jelentés fejléce ekkor a következőképpen fog megjelenni: **1-02 időszak, 01/01/02 és 01/31/02 között**.

> [!NOTE]
> Egyes szövegrészek, például a hosszú dátum a szerver regionális beállításaitól függ. Ezen beállítások módosításához kattintson a **Start** gombra, majd a **Vezérlőpult** elemre, majd válassza a **Régiók és nyelv** opciót. Az alábbi táblázat felsorolja az oszlopfejlécekhez elérhető készszöveg-beállítáokat.


| Kész szövegek beállításai és kódjai                | Leírás |
|-----------------------------------------|-------------|
| Hónap neve (@TeljNaptáriHónap)              | Az aktuális hónap nevét nyomtatja az oszlopfejlécbe. Ha úgy dönt, hogy a jelentésben szereplő összegeket ezerre, millióra vagy milliárdra kerekíti fel, vagy ha az oszlopszélességet négy karakternél szűkebbre állítja, akkor a hónap nevét a rendszer az első három betűre rövidíti. |
| Rövidített hónapnév (@RövNaptáriHónap) | A hónap teljes (nem rövidített) nevét nyomtatja ki a kiválasztott pénzügyi időszakra. |
| Időszakszám (@PénzügyiIdőszak)           | Az oszlophoz azonosított pénzügyi időszak számszerű formáját nyomtatja. Ha az oszlop több időszakra is kiterjed, a tartomány utolsó időszakát nyomtatja ki a program. |
| Időszakleírás (@PénzügyiIdőszakNév)  | A pénzügyi adatokban azonosított pénzügyi időszak azonosítását nyomtatja ki. |
| Pénzügyi év (@PénzügyiÉv)               | Az oszlop pénzügyi évét számszerű formában nyomtatja ki. |
| Naptári év (@NaptÉv)                | Az oszlop naptéri évét számszerű formában nyomtatja ki. |
| Kezdő dátum (@KezdőDátum)                 | Az oszlop kezdő dátumát nyomtatja ki. |
| Záró dátuma (@ZáróDátum)                     | Az oszlop záró dátumát nyomtatja ki. |
| Egység neve a fáról (@EgységNév)         | Ha egy oszlopot a jelentésfa egy meghatározott egységére korlátozza, akkor az egység nevét nyomtatja ki az oszlopfejlécben. |
| Egység leírása (@EgységLeírás)            | Ha egy oszlopot a jelentésfa egy meghatározott egységére korlátozza, akkor az egység leírását nyomtatja ki az oszlopfejlécben. |
| Könyvelési kód (@KönyvelésiKód)                   | Az oszlopban meghatározott könyvelési kódot nyomtatja ki. |
| Üres sor (@Üres)                     | Üres sort szúr be az oszlopfejlécbe. |

### <a name="create-a-conditional-spanning-header"></a>Feltételesen fejlesztett fejléc létrehozása

A feltételesen terjesztett fejlécek több oszlopon átterjedhetnek, amelyek adott időszakadatokon alapulnak. Ha például a költségvetési jelentés az adott pénzügyi évre vonatkozik, és az elmúlt hónapok valós költségvetéseit össze szeretné vetni a következő hónapok előrejelzett költségvetéseivel, akkor a feltételesen terjesztett fejléc használatával mindig automatikusan frissítheti a jelentés fejlécét. Feltételes átívelő fejléc készítésekor mérlegelje az alábbi helyzeteket:

- Minden olyan leállítási feltételt (**Szórás** mezőre), amely megfelelt az indítási feltételnek (**Eltárolt mező**) figyelmen kívül hagyás előtt. Tegyük fel, hogy a B oszlop terjesztési feltétele ALAP+1 kezdetű és ALAP végződésű, az ALAP a C oszlop, az ALAP+1 pedig a D oszlop. Ebben az esetben a C oszlop leállítási feltételét a rendszer nem veszi figyelembe, és a fejléc nyomtatása a D oszlopban kezdődik.
- Ha olyan oszlopfejléceket ad meg, amelyek átfedésben vannak, akkor a jelentés kinyomtatásakor átfedésben jelennek meg. A jelentés létrejön, de **a** Jelentési várólista állapotmezője a következő figyelmeztetést tartalmazza: "Az alapfejlécek más oszlopfejlécekkel együtt, egymást átfedő szöveget okozhatnak." Ha például a B oszlop fejlécdefiníciója B-től ALAP+1 elemig terjed, és a D oszlop fejlécdefiníciója ALAP+1 kezdetű és F végű, akkor a fejlécek egymásra lesznek nyomtatva, így nem lesznek olvashatóak. Ha ALAP elemet használ az **Ettől terjed/Eddig terjed** definícióban, akkor mindig nézze meg a generált jelentést, hogy nem fedik-e át egymást a fejlécek.
- Ha az ALAP elemet a terjesztési definícióban egy nem nyomtatandó (**NP**) oszlopban adja meg, akkor a rendszer nem veszi azt figyelembe, függetlenül attól, mi áll az oszlopdefinícióban. Lényegében ez az eset megegyezik azzal, mint ha nem hozott volna létre oszlopfejléc-definíciót.
- A feltételesen nyomtatandó oszlopok (**P&lt;B**, **P&gt;=B**) esetében a feltételes terjesztésű fejlécek ugyanúgy viselkednek, mint a szokásos oszlopfejléc-definíciók esetén. Ha például a feltétel hamis, minden olyan további oszlop, amely megegyezik a terjesztési feltétellel, elindítja a fejléc nyomtatását.

#### <a name="create-a-conditional-spanning-header"></a>Feltételesen fejlesztett fejléc létrehozása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Kattintson duplán egy fejléccellára.
3. Az Oszlopfejléc **párbeszédpanelen** írja be az oszlop fejlécének szövegét. Másik lehetőségként kattintson az **Automatikus szöveg beszúrása parancsra**, és válasszon egy lehetőséget.
4. A **Formázási beállítások** mezőben válassza ki a fejléc formázási stílusát.
5. Adjon meg egy időszakot ahhoz az alapidőszakhoz képest, amelyet a jelentés létrehozásakor adtak meg. Az **Ettől terjed** és az **Eddig terjed** mezőkben adja meg a következő értékek egyikét: **ALAP**, **ALAP-X** vagy **ALAP+X**, ahol az X az időszakok számát jelenti az alapidőszakhoz viszonyítva. Ha például az **ALAP** értéket adja meg az **Ettől terjed** mezőben, a feltételes terjesztésű oszlopfejlécszöveg abban az oszlopfejlécben kezdődik, ahol a jelentésdefiníció **Alapidőszak** értéke megegyezik az oszlopdefiníció **Időszak** értékével. Abban az oszlopban fog végződni, amelyet az **Eddig terjed** mezőben megadott. Így tehát ha a terjesztés kiterjedése ALAP-tól M-ig, és a jelentésdefiníció **Alapidőszak** értéke **4**, akkor a fejléc abban az oszlopban kezdődik, ahol az időszak értéke **4**, és az M oszlopig tart. A fejlécek csak a nyomtatandó oszlopoknál kezdődnek el és záródnak le.
6. Az **Igazítás** elemnél válassza ki, hogy az oszlopfejléc szövege jobbra, középre vagy balra igazított legyen.
7. Kattintson az **OK** gombra.

#### <a name="example-of-a-conditional-spanning-header"></a>Példa a feltételesen fejlesztett fejlécre

A felhasználó egy jelentést készít egy dinamikus hat hónapos előrejelzéshez. A felhasználó szeretné, ha a „Tényleges” szó jelenne meg minden olyan oszlopban, amely tényadatokat tartalmaz, és a „Költségvetés” szó azoknál, amelyek csak költségkeret-előrejelzést tartalmaznak. A jelentés futtatásának minden egyes hónapja esetében, van egy további tényleges oszlop és kisebb költségvetés oszlop. Bár a felhasználó kézzel is módosíthatná az oszlopdefiníciót a fejlécek kiigazítására, valahányszor jelentést generál, mégis időt és munkát spórol azzal, ha úgy dönt, feltételes terjesztésű fejléceket használ, amelyek automatikusan hozzák létre a fejléceket az érintett oszlopokban, valahányszor legenerálódik a jelentés. A felhasználó megnyitja a Jelentéstervezőt, rákattint az **Oszlopdefiníció** menüpontra a navigációs ablakban, és megnyitja az oszlopdefiníciót a jelentéshez. A felhasználó az alábbi adatokat adja meg. Az alapidőszak a jelentésdefinícióban 4.

|  Formátum   |  A   | milliárd     | K      | T       | E        | P       | G       | H      | I             | J             | ezer             | L             | H             |
|-----------|------|-------|--------|---------|----------|---------|---------|---------|-------------|---------------|---------------|---------------|---------------|
| 1. fejléc   |    | Tényleges    | Költségvetés        |         |         |        |       |          |        |               |               |               |               |
| 2. fejléc   |      | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap | @TeljNaptáriHónap |
| 3. fejléc    |      |       |        |        |        |         |        |          |               |               |               |               |               |
| Oszloptípus  | DESC | FD   | FD     | FD    | FD   | FD    | FD      | FD            | FD            | FD            | FD            | FD            | FD            |
| Könyvelési kód / Attribútum |      | TÉNYLEGES        | Költségvetés2012    | TÉNYLEGES        | Költségvetés2012    | TÉNYLEGES        | Költségvetés2012    | TÉNYLEGES        | Költségvetés2012    | TÉNYLEGES        | Költségvetés2012    | TÉNYLEGES        | Költségvetés2012    |
| Pénzügyi év |  | ALAP   | ALAP   | ALAP   | ALAP   | ALAP    | ALAP    | ALAP     | ALAP          | ALAP          | ALAP          | ALAP          | ALAP          |
| Időszak  |     | 1      | 1       | 2      | 2      | 3       | 3       | 4        | 4             | 5             | 5             | 6             | 6             |
| Érintett időszakok     |      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      | IDŐSZAKOS      |
| Oszlopszélesség   | 30   | 10    | 10     | 10     | 10    | 10    | 10    | 10     | 10            | 10            | 10            | 10            | 10            |
| Nyomtatásvezérlés  |    | P&lt;=B    | P&gt;B   | P&lt;=B  | P&gt;B   | P&lt;=B   | P&gt;B   | P&lt;=B  | P&gt;B   | P&lt;=B  | P&gt;B   | P&lt;=B       | P&gt;B        |

A felhasználó duplán kattint a B **oszlop** egyik oszlopfejléccellájára az Oszlopfejléc párbeszédpanel megnyitásához, és a következő adatokat írja be.

| Mező              | Érték                 |
|--------------------|-----------------------|
| Oszlopfejléc szöveg | Tényleges                |
| Készszöveg beszúrása    | Nincs bejelölve. |
| Formátumbeállítások     | Mező                   |
| Indoklás      | Nincs bejelölve. |
| Elosztva innen        | milliárd                     |
| Elosztva ide          | ALAP                  |

Az adatok megadása után a felhasználó az **OK** gombra kattint. A felhasználó ezután duplán kattint a C **oszlop** fejléccellájára az Oszlopfejléc párbeszédpanel megnyitásához, és a következő adatokat írja be.

| Mező              | Érték                 |
|--------------------|-----------------------|
| Oszlopfejléc szöveg | Költségvetés                |
| Készszöveg beszúrása    | Nincs bejelölve. |
| Formátumbeállítások     | Mező                   |
| Indoklás      | Nincs bejelölve. |
| Elosztva innen        | BASE+1                |
| Elosztva ide          | H                     |

Ezután valahányszor jelentés geenrálódik, a „Tényleges” szó jelenik meg minden olyan oszlopban, amely tényadatokat tartalmaz, és a „Költségvetés” szó azoknál, amelyek csak költségkeret-előrejelzést tartalmaznak. Ezen kívül a rendszer az oszlopok számát is korrigálja minden hónapban.

## <a name="apply-column-justification"></a>Alkalmazzon oszlopigazítást
Az **Igazítás** cella arra szolgál, hogy a leírásoszlophoz igazítóformázást lehessen alkalmazni a jelentésben. Ez a beállítás csak az oszlopleírást érinti, nem pedig a tényleges értékeket.

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Kattintson duplán az **Igazítás** cellára.
3. Válasszon a listában a következő értékek közül:

    - **Nincs** – nem szükséges igazítást alkalmazni.
    - **Balra** – az oszlopleírás balra igazítása.
    - **Középre** – az oszlopleírás középre igazítása.
    - **Jobbra** – az oszlopleírás jobbra igazítása.

## <a name="add-special-formatting-options"></a>Speciális formázási beállítás hozzáadása
Az oszlopdefinícióban a formázási oszlop részletsorok a kiválaszott oszlopok speciális formázására vonatkoznak. Bár a Nyomtatásvezérlés **és**  **·**  **az Oszlopra vonatkozó korlátozások közül egyes beállítások fD** oszlopokra vonatkoznak, a legtöbb beállítás minden oszloptípusra vonatkozik. Az oszlopdefinícióban meghatározott formázás felülírja a jelentésdefinícióban meghatározottat. Azonban a sordefinícióban meghatározott formázás felülírja az oszlopdefinícióban meghatározottat. A következő sorok tekintendők formázási soroknak:

- Oszlopszélesség
- Oszlop előtti extra szóköz
- Formázás/Pénznem felülbírálása
- Nyomtatásvezérlés

### <a name="changing-the-column-width"></a>Az oszlop szélességének módosítása

Az **Oszlop szélesség** cella azt határozza meg, hogy hány karaktert kell használni a nyomtatott jelentésben az oszlop szélességéhez. Az oszlop szélessége az összegeket (**CALC**, **WKS** vagy **FD** típusú), leírást (**DESC** típusú) és a kitöltés (**FILL** típusú) oszlopok esetében fontos adat. A rendszerben alapértelmezésként az **Automatikus illesztés** opció van beállítva, így az oszlopok szélessége automatikusan az oszloptartalom hosszához illeszkedik.

#### <a name="specify-the-width-of-a-column-on-a-report"></a>A jelentés egy oszlopa szélességének megadása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Az Oszlop szélesség **cellájában** adja meg az oszlop szélességének szóközöket. Az oszlopok maximális szélessége 255 karakter (ebbe beletartoznak a fillérértékek, vesszők és zárójelek is). Másik lehetőségként engedélyezheti a jelentéstervező számára, hogy a cella tartalma alapján válassza ki az oszlop megfelelő szélességét, **kattintson** duplán az Oszlop szélesség cellájára, **majd az Automatikus illesztés elemre**.

### <a name="add-space-between-columns"></a>Szóközök beszúrása az oszlopok közé

Az **oszlopcella** előtti extra szóközök az oszlopdefiníció egyik oszlopa és egymás melletti oszlopai közötti elválasztó szélességét adhatja meg. Az **oszlopbeállítás előtti extra** szóközök az oszlop minden oszlopadatsorát érintik, de az oszlopfejléc sorait nem. Ezzel az opcióval elválaszthatja egymástól az oszlopcsoportokat úgy, hogy a leírás előtt néhány szóközt szúr be, így a leíró oszlop be lesz húzva a jelentés balra igazított címeitől. A szóközök alapértelmezés szerinti száma két oszlop között kettő. Ezt a beállítást a jelentésdefiníció **Beállítások** lapján módosíthatja.

#### <a name="specify-the-space-between-columns"></a>Adja meg az oszlopok közötti szóközök számát

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Az Oszlopcella **előtti** Extra szóközök közé írja be, hogy hány szóközt kell beszúrni az oszlopok között.

### <a name="specify-a-format-currency-override"></a>Formátum/pénznem felülbírálásának beállítása

A **Formátum/pénznem felülbírálata** cella megadja az oszlopban a tizedes, a pénznem és a százalékérték formátumát. Ez a formázás felülírja minden, a jelentésdefinícióban meghatározott vagy rendszer szerinti alapértelemezett formátumot.

#### <a name="assign-a-format-currency-override-to-a-report-column"></a>Formátum és pénznem felülbírálásának beállítása egy jelentésoszlopra

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Kattintson duplán az összegoszlop **egy Formátum/pénznem** felülbírálati cellájára.
3. A Formátum **felülbírálása** párbeszédpanelen válassza ki a formázási beállításokat.

### <a name="add-a-print-control-code"></a>Adjon hozzá nyomtatási vezérlőkód

A **Nyomtatás vezérlőcella** olyan kódokat tartalmazhat, amelyek módosítják az oszlopok megjelenítési vagy nyomtatási jellemzőit. Kétféle típusú nyomtatási ellenőrzőkód létezik: szokásos és feltételes.

#### <a name="regular-print-control-codes"></a>Szokásos nyomtatási ellenőrzőkódok

| Nyomtatási vezérlőkód | Átszámítás                                     | Leírás |
|--------------------|-------------------------------------------------|-------------|
| NP                 | Nem nyomtatandó                                     | Az ebben az oszlopban szereplő összegek kizárása a nyomtatott jelentésből és a számításokból. Nem nyomtatandó oszlopoknak a számításba való beiktatásához közvetlenül az oszlopra kell hivatkozni a számítási képletben. Például a nem nyomtatandó C oszlop szerepel a következő számításban: **B+C+D**. Azonban a nem nyomtatandó C oszlop nem szerepel a következő számításban: **B:D**. |
| XCR                | Módosítsa a jelet, ha a jellemző soregyenlegmző egyenlege csak jóváírás | Költségvetés vagy különbözeti jelentés létrehozása, ahol a kedvezőtlen eltérés (például bevételi hiány vagy költségtúllépés) mindig negatív. Ha ezt a kódot **CALC** oszlopra használja, akkor megfordítja az oszlopösszeg előjelét, amennyiben egy adott sor tipikus egyenlege követel jellegű (ezt **C** betű jelöli a sordefiníció **Normál egyenleg** oszlopában).<p><strong>Megjegyzés:</strong> A <strong>TOT</strong> és </strong>CAL</strong> sorok esetében, amelyek tipikusan követel egyenleggel rendelkeznek, mindenképpen <strong>C</strong> beállítást adjon meg a sordefiníció <strong>Normál egyenleg</strong> oszlopában.</p> |
| X0            | Oszlop elrejtése, ha minden cella zéró vagy üres   | Egy **FD** oszlop kizárása a jelentésből, ha az adott oszlopban az összes cella üres vagy nullákat tartalmaz. |
| SR                 | Kerekítés elrejtése                               | Az ebben az oszlopban szereplő összegek kerekítésének megakadályozása. |
| XR                 | Kumulatív frissítés kihagyása                                 | Kumulatív frissítés kihagyása. Ha a jelentés egy jelentési fát használ, az adott oszlopban szereplő összegek nem lesznek összesítve későbbi fölérendelt csomópontokba. |
| RP                 | Oszlop megismétlése minden egyes lapokon                      | Ismételjen meg egy adott oszlopot a jelentés minden lapján. Használhatja például az **RP** nyomtatási ellenőrzőkódot, ha bele kíván venni egy **ROW** típusú oszlopot, amely minden oldalon behúzza a sorkódokat. |
| WT                 |  Szöveg sortörése                                      |  Ha egy oszlop szövege túl hosszú a rendelkezésre álló helyhez képest, sortöréssel az oszlopon belül tartja a szöveget. |

#### <a name="conditional-print-control-codes"></a>Feltételes nyomtatási ellenőrzőkódok

| Feltételes nyomtatási ellenőrzőkód | Leírás                                                                             |
|--------------------------------|-----------------------------------------------------------------------------------------|
| (nincs)                         | Törli a feltételes nyomtatási választást.                                                  |
| P&lt;B                         | Csak akkor jelenít meg egy adott oszlopot, ha az időszak száma alacsonyabb, mint az alapidőszak.             |
| P&gt;B                         | Csak akkor jelenít meg egy adott oszlopot, ha az időszak száma magasabb, mint az alapidőszak.             |
| P=B                            | Csak akkor jelenít meg egy adott oszlopot, ha az időszak száma megegyezik az alapidőszakkal.              |
| P&lt;=B                        | Csak akkor jelenít meg egy adott oszlopot, ha az időszak száma kisebb vagy egyenlő, mint az alapidőszak. |
| P&gt;=B                        | Csak akkor jelenít meg egy adott oszlopot, ha az időszak száma nagyobb vagy egyenlő, mint az alapidőszak. |

#### <a name="add-print-control-codes-to-a-report-column"></a>Nyomtatásvezérlő kódok hozzáadása a jelentés oszlopához

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Kattintson duplán a Nyomtatás **vezérlőcellára** .
3. A Nyomtatásvezérlő **párbeszédpanelen** válasszon ki egy kódot a **Nyomtatásvezérlő beállításainak kiválasztása listából** . Több cella kijelöléséhez tartsa lenyomva a Ctrl gombot, amíg kijelöli a cellát.
4. Válasszon egy opciót a **Feltételes nyomtatási beállítások** mezőben. Alapértelmezés szerint a **(nincs)** beállítás van kiválasztva. Egyszerre csak egy feltételes nyomtatási kód választható ki.
5. Kattintson az **OK** gombra.

> [!TIP]
> A nyomtatási kódokat közvetlenül is beírhatja a nyomtatásvezérlő **cellába** . Ha több nyomtatásvezérlő kód van, ezeket vesszővel válassza el egymástól.

## <a name="column-types"></a>Oszloptípusok
A jelentés egyes oszlopaiban megjelenő információ típusát az **Oszloptípus** sor határozza meg a sordefinícióban. Minden oszlopdefiníciónak tartalmaznia kell legalább egy leírás oszlopot (**DESC**) és egy összegoszlopot (**FD**, **WKS** vagy **CALC**).

> [!NOTE]
> Az Oszloptípus bemutatott kódjai nem minden könyvelési rendszerben érvényesek. Ha olyan típust választ, amelyik nem érvényes ebben a könyvelési rendszerben, az oszlop üres marad a jelentésben.

### <a name="specify-a-column-type"></a>Adjon meg egy oszloptípust.

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. A megfelelő oszlopban kattintson duplán a cellára az Oszloptípus **sorban** .
3. Válasszon egy oszloptípust a listából. A következő táblázat a különböző oszlopok típusait írja le.

    <table>
    <thead>
    <tr>
    <th>Oszloptípuskód</th>
    <th>Leírás</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>FD</td>
    <td>Pénzügyi adatok megjelenítése a <strong>Pénzügyi dimenziókhoz kapcsolás</strong> oszlop használata esetén a sordefinícióban. Amikor az <strong>FD</strong> oszloptípust választja, az alábbi sorokhoz alapértelmezett beállításokat állít be a rendszer: <ul>
    <li><strong>Könyvelési kód / Attribútumkategória:</strong> TÉNYLEGES</li>
    <li><strong>Könyvelési kód / Attribútumkategória:</strong> TÉNYLEGES</li>
    <li><strong>Pénzügyi év:</strong> ALAP</li>
    <li><strong>Időszak:</strong> ALAP</li>
    <li><strong>Érintett időszakok:</strong> IDŐSZAKOS</li>
    <li><strong>Oszlopszélesség:</strong> 14</li>
    </ul>
Az alapértelmezett beállítások módosíthatóak.</td>
    </tr>
    <tr>
    <td>CALC</td>
    <td>A <strong>Képlet</strong> cellában megadott egyszerű vagy összetett számítás eredményének megjelenítése. További tudnivalókért lásd: <a href="advanced-formatting-options-financial-reporting.md">Speciális formázási beállítások a pénzügyi jelentésekben</a>.</td>
    </tr>
    <tr>
    <td>DESC</td>
    <td>A sorleírás megjelenítése a sordefinícióból. Bár a leíró oszlop gyakran a legelső oszlop a jelentésben, valójában bárhová helyezheti.</td>
    </tr>
    <tr>
    <td>SOR</td>
    <td>Pénzügyi sorok egyedi sorkódjainak megjelenítése a sordefiníció <strong>Sorkód</strong> oszlopából. További tudnivalókért lásd: <a href="row-definitions-financial-reporting.md">Sordefiníciók a pénzügyi jelentésben</a>.</td>
    </tr>
    <tr>
    <td>ACCT (Számlakódok)</td>
    <td>A pénzügyi adatok szegmensértékeinek vagy dimenzióértékeinek megjelenítes, amelyek az egyes sorokra vonatkoznak. A számlák és a tranzakciók részletes jelentéseinél a teljes minősített számla is nyomtatásra kerül (például <strong>110140-070-0101</strong>). Ha tartományok vannak megadva a <strong>Hivatkozás a pénzügyi dimenziókhoz</strong> oszlopan egy társított sordefinícióban, akkor a tartomány szögletes zárójelek között jelenik meg, és egyedi értékként kezeli a rendszer (példa: <strong>[110140:110700]-070-[0101:0200]</strong>). Olyan pénzügyi és magas szintű jelentéseknél, amelyek több számlát kombinálnak, a rendszer kinyomtatja a pénzügyi adatok hivatkozását is a sordefinícióból (péládul: <strong>1100:1200</strong>).</td>
    </tr>
    <tr>
    <td>TÖLT</td>
    <td>Az aposztrófok közé írt karakterrel tölti ki a cellát. Ha nem ad meg karaktert, az oszlop üres lesz. Például ha pontokkal (...) szeretne kitölteni egy cellát, a következőt adja meg: <strong>TÖLT</strong> <strong>'.'</strong>.</td>
    </tr>
    <tr>
    <td>OLDAL</td>
    <td>Függőleges oldaltörést szúr be a jelentésbe. A <strong>PAGE</strong> oszloptól jobbra lévő oszlopok új lapon fognak megjelenni.</td>
    </tr>
    <tr>
    <td>ATTR</td>
    <td>Ha a könyvelési rendszere támogatja az attribútumok használatát, akkor számla- vagy tranzakcióattribútumot jelenít meg az oszlopban. Egy attribútum, amelynek vonatkoznia kell egyetlen teljes számlára, kivonatolja az alapul szolgáló számla- vagy tranzakcióadatokat a pénzügyi adatokból. A számlaszintű attribútumok a számlából jelenítenek meg adatokat, míg a tranzakciószintű attribútumok olyan adatokat mutatnak meg, amelyek a tranzakció feladásakor merültek fel. Ha az <strong>ATTR</strong> beállítást választja oszloptípusnak, akkor válasszon egy attribútumkategóriát az oszlopdefiníció <strong>Könyvelési kód / Attribútumkategória</strong> részletsorából.</td>
    </tr>
    </tbody>
    </table>

### <a name="financial-dimensions-column"></a>Pénzügyi dimenziók oszlopa

A következő oszlopdefiníciós **sordefiníciók** az olyan oszlopokra vonatkoznak, amelyek oszloptípusa **FD**  (Összegek a pénzügyi dimenziókból).

#### <a name="book-codeattribute-category-cell"></a>Könyvelési kód / Attribútumkategória cella

A **Könyvkód/Attribútumkategória** cella azonosítja az adatok könyvkódját az **FD oszlopban** . Egy oszlopdefiníció egynél több tényleges, költségvetési és statisztikai oszlopot is tartalmazhat. Egy oszlopdefiníció emellett különböző időszakokat is megjeleníthet, például az aktuális időszakot vagy az év aktuális dátumáig tartó részét, illetve különböző összegeket. Könyvelési kódok listája azokat a tényleges, költségvetési és statisztikai (nem pénzügyi) beállításokat tükrözi, amelyek az Ön pénzügyi adataiban kialakítottak.

#### <a name="fiscal-year-cell"></a>Pénzügyi év cellája

A **Pénzügyi év** cella azonosítja azt a pénzügyi évet, amelybe az oszlopnak bele kell foglalnia. Az év viszonylagos lehet ahhoz az alapévhez képest, amelyet a jelentés létrehozásakor adtak meg. Az alábbi lehetőségek közül választhat.

| Lehetőség  | Leírás                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------|
| ALAP    | A jelentés időpontjában meghatározott alapévet használja.                                                                          |
| ALAP+\# | Az alapévet követő \#. évet használja. Az alapévet követő harmadik év használatához például írja be az **ALAP+3** kódot. |
| ALAP-\# | Az alapévet megelőző \#. évet használja. Az előző év használatához az **ALAP-1** kódot kell használnia.                 |
| \#      | Adja meg az aktuális pénzügyi évet.                                                                                                |

#### <a name="period-cell"></a>Időszakcella

Az **Időszak** cella azonosítja a pénzügyi időszakot, amely az oszlopba kerül. Az időszak viszonylagos lehet ahhoz az alapidőszakhoz képest, amelyet a jelentés létrehozásakor adtak meg. Az alábbi lehetőségek közül választhat.

| Lehetőség          | Leírás |
|-----------------|-------------|
| ALAP            | Az alapidőszakot használja. |
| ALAP+\#         | Az alapidőszakot követő \#. időszakot használja. Az alapidőszakot követő harmadik időszak használatához például írja be az **ALAP+3** kódot. |
| ALAP-\#         | Az alapidőszakot megelőző \#. időszakot használja. Az előző időszak használatához az **ALAP-1** kódot kell használnia. |
| ALAP-\#:ALAP    | Több időszak használata, az alapidőszakot megelőzőektől az alapidőszakon keresztül. Ha például a három legutóbbi és az aktuális időszakot szeretné használni, a következőt adja meg: **ALAP-3:ALAP**. |
| ALAP:ALAP+\#    | Több időszak használata, az alapidőszaktól kezdve az azt követő több időszakon keresztül. Ha például az alapidőszakot és az azt követő két további időszakot szeretné használni, a következőt adja meg: **ALAP:ALAP+2**. |
| ALAP-\#:ALAP+\# | Több időszak használata, az alapidőszakot megelőzőektől az alapidőszakot követőkig. Ha például az alapidőszakot, az azt megelőző három korábbi és az azt követő két további időszakot szeretné használni, a következőt adja meg: **ALAP-3:ALAP+2**. |
| 1:ALAP          | Több időszak használata, az első időszaktól kezdve az alapidőszakig. |
| \#              | Mindig egy megadott időszakszámot használjon. Ezen opció használata nem ajánlott, mert csökkenti az oszlopdefiníció rugalmasságát. |
| \#                                      : \#           | Mindig egy megadott időszaktartományt használjon. Ezen opció használata nem ajánlott, mert csökkenti az oszlopdefiníció rugalmasságát. |

Bármely időszakmeghatározásban túlléphet a pénzügyi év határokon, és vegyítheti az éveket az időszakoktartományokban. Tegyük fel, hogy az **ALAP-5** értéket adja meg (így a legutóbbi 6 időszakot láthatja), majd olyan jelentést futtat, melynek alapidőszaka 2. Ebben az esetben a jelentés a meghatározott pénzügyi év első két időszakát mutatja, és a korábbi pénzügyi év utolsó hat időszakát.

### <a name="specify-the-periods-for-an-fd-column"></a>Időszakok meghatározása egy FD oszlophoz

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Egy **FD** oszlopban kattintson duplán az **Időszak** sorban lévő cellára, majd válasszon ki egy beállítást a listában.
3. A navigációs ablak feletti képletsorban vagy az **Időszak** cellában töltse ki a képletet. Minden kettős kereszt (\#) helyére írja be a megfelelő értéket.

#### <a name="periods-covered-cell"></a>Érintett időszakok cellája

Az Időszakok **által fedezett** cella azonosítja az oszlop által megjelenítendő összeget. Ez az összeg az oszlop **Pénzügyi**  **év** és Időszak celláiban található értékhez van arányban. Az alábbi lehetőségek közül választhat.

| Lehetőség      | Leírás                                                                 |
|-------------|-----------------------------------------------------------------------------|
| IDŐSZAKOS    | A tevékenység összegének megjelenítése az aktuális időszakra vagy időszakok tartományára. |
| IDŐSZAKOS/BB | A kezdő egyenleg megjelenítése az aktuális időszakra vagy időszakok tartományára.   |
| IDEI         | Az adott év aktuális dátumáig tartó tevékenység összegének megjelenítése.                               |
| IDEI/BB      | Az év kezdő egyenlegének megjelenítése.                                 |

### <a name="specify-the-periods-that-are-covered-for-an-fd-column"></a>Az FD oszlopra vonatkozó időszakok meghatározása

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Az FD **oszlopban** kattintson duplán **a** cellára az Időszakokkal fedezett sorban, és válasszon egy beállítást a listáról.

### <a name="attribute-filter-in-a-column-definition"></a>Attribútumszűrő az oszlopdefinícióban

Az attribútumok olyan pénzügyi adatértékek, amelyek továbbdefiniálnak egy számlát vagy tranzakciót. A számlaattribútumok közé tartozik az **Eszköz**, **Kötelezettség**, **Bevétel**, és a **Költség**. A tranzakcióattribútumok tartalmazzák a **tranzakció leírását és** a tranzakció **alkalmazásának dátumát**. Az attribútumtámogatás eltérhet a Microsoft Dynamics 365-ös finanace esetében. Az Attribútumszűrő **cella** **az attribútumkategóriák meghatározott értékeire vagy tartományaira korlátozza az FD** oszlopokban lévő adatokat. Habár ez a funkció együtt használható az **ATTR** oszloppal, az **ATTR** oszlop nem kötelező. Az **FD** oszlopokban korlátozva van az attribútumszűrő által a jelentésbe bekerülő számlák vagy tranzakciók száma.

> [!NOTE]
> Az ERP rendszer által támogatott attribútumokat illetően olvassa el a rendszer integrációs útmutatóját.

#### <a name="apply-an-attribute-filter-for-an-fd-column-on-a-report"></a>Attribútumszűrő alkalmazása a jelentés egy FD oszlopára

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Kattintson duplán az attribútumszűrő-cellára **egy** **FD-oszlopban** .
3. Az Attribútumszűrő **párbeszédpanelen** kattintson duplán a **cellára** az Attribútum oszlopban, majd válassza ki a szűrő típusát.
4. Az eredmények további szűréséhez adja meg a tartományt a **-tól** és az **-ig** oszlopokban. A **-tól** cellának pozitív értéket kell tartalmaznia.
5. Kattintson az **OK** gombra.

#### <a name="example-of-an-attribute-filter"></a>Példa az sttribútumszűrőre

A következő példa egy olyan oszlopleírás egy részét mutatja be, amely **rendelkezik számlaattribútummal a könyvkód/attribútumkategória sorában** . Ezen oszlop attribútumszűrőjre határozza meg a jelentésbe bekerülő értékek tartományát.

|      Szűrés                  | A    | milliárd                   |
|------------------------------|------|---------------------|
| Oszloptípus                  | DESC | FD                  |
| Könyvelési kód / Attribútumkategória |      | TÉNYLEGES              |
| Pénzügyi év                  |      | ALAP                |
| Időszak                       |      | 1:ALAP              |
| Érintett időszakok              |      | IDŐSZAKOS            |
| ...                          |      |                     |
| Oszlopszélesség                 | 30   |                     |
| ...                          |      |                     |
| Attribútumszűrő             |      | Hivatkozás=\[01:10\] |

### <a name="dimension-filter-in-a-column-definition"></a>Dimenziószűrő az oszlopdefinícióban

Dimenziószűrő használatával korlátozhatók az **FD** oszlopok a dimenzióértékek megadásához. Egy szűrő tartalmazhat egyetlen dimenziót, egy dimenziótartományt vagy dimenziók csoportját. A szűrő tartalmazhatja dimenzióértékek halmazát is. Mivel a dimenzióértékek változhatnak, a ..\\pénzügyi dimenzióalapú\\dimenzióalapú rendszereknek nem kell egy adott hosszúságnak megfelelniük. A szűrő alkalmazására kerül sor, függetlenül attól, hogy a jelentés tartalmaz-e jelentési fát. Bármelyik helyen használhat helyettesítő karaktert (\* vagy ?). Több számla meghatározásakor vesszővel válassza el azokat, például: +Számla=\[1200\], +Számla=\[1100\], Részleg=\[01?\] Ahhoz, hogy egy adott számla minden részlegét megkapja, kizárhatja a Részleg dimenziót a dimenziószűrőből. Például a következő dimenziószűrők ugyanúgy lesznek kezelve:

- +Számla=\[1100\], Részleg
- +Számla=\[1100\]

Használhatja továbbá az alfanumerikus karakterek bármely kombinációját a pontos találatokra, és részleges dimenziókat is meghatározhat. Például a **Hely = \[10\*\]** minden olyan helydimenzió-értéket tartalmaz, ami 10-zel kezdődik.

#### <a name="apply-a-dimension-filter-for-a-column-on-a-report"></a>Dimenziószűrő alkalmazása a jelentésben szereplő oszlopra

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. Kattintson duplán egy **FD-oszlop Dimenzió szűrőcellájára**  **.** 
3. A **Dimenziók** párbeszédpanelen adja meg az alkalmazandó szűrőket.
4. Kattintson az **OK** gombra.

### <a name="format-a-multiple-currency-report-in-a-column-definition"></a>Több pénznemű jelentés formázása egy oszlopdefinícióban

Több pénznemet tartalmazó jelentés képes megjeleníteni az összegeket a főkönyvi könyvelési pénznemében, a főkönyvi jelentések az eredeti tranzakció pénznemében vagy lefordított jelentési pénznemben. Egy vállalat könyvelési pénznemének meghatározására a Főkönyv beállításában kerül sor. Nem szabad összetéveszteni ezt a beállítást az operációs rendszer regionális opciók beállításával, ahol az alapértelmezett pénznemszimbólumokat állíthatja be a jelentésekhez. A következő, pénznemekhez kapcsolódó cellák találhatóak az oszlopdefinícióban:

- **Pénznem megjelenítése**  – adja meg, hogy milyen pénznemben (könyvelés, jelentés, tranzakció vagy lefordított jelentés) jelennek meg a tranzakciók. Átszámított a jelentési pénznemet néha pénznemátváltásnak is nevezik. A pénznemátváltás az a funkció, amellyel a főkönyvi összegeket olyan pénznemben is megjelenítheti a jelentésben, amely egyébként nem számít a cég jelentési pénznemének, vagy a tranzakció megadásakor használt pénznemnek.
- **Pénznemszűrő**  – pénznemszűrő megadása. Csak a kiválasztott pénznemben megadott tranzakciók jelennek meg a jelentésben.


A vállalat könyvelési pénznemének meghatározásához kövesse az alábbi lépéseket.

1. A Jelentéstervező vállalat menüjében **kattintson** a Vállalatok **elemre**.
2. A **Vállalatok** párbeszédpanelen válasszon egy vállalatot, majd kattintson az **Megtekintés** gombra.
3. A Vállalat **megtekintése párbeszédpanel** Területi beállításai **területnél** megtekintheti a kiválasztott vállalathoz meghatározott pénznemet.

#### <a name="specify-the-currency-on-a-multiple-currency-report"></a>Pénznem meghatározása több pénznemű jelentésen

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2.  **Kattintson duplán a Pénznem cisplay**  **cellára a megfelelő FD** oszlopban, majd válassza ki a pénzneminformációk megjelenítését: **Főkönyvi** könyvelési pénznem, főkönyvi **jelentés**, tranzakció pénzneme, vagy válassza másik jelentési pénznemre történő fordítást.
3. Kattintson duplán a **Pénznemszűrő** cellára a megfelelő **FD** oszlopban, és válassza ki a listában a megfelelő pénznemkódot. Csak az ebben a pénznemben megadott tranzakciók jelennek meg a jelentésben.


### <a name="example-for-currency-display-and-currency-filter-cells"></a>Példa pénznemek megjelenítésére és pénznemszűrő cellákra

A felhasználó a pénznemmel kapcsolatos következő választásokat tette az oszlopdefiníciójában:

- **Pénznemszűrő:** Yen
- **Pénznem megjelenítése:** Könyvelési pénznem a főkönyvben (USA dollár)

A felhasználó által kiválasztott pénznemszűrő miatt a jelentés csak japán jenben (JPY) bevitt tranzakciókat tartalmaz. A kiválasztott pénznemmegjelenítési beállítás miatt a jelentés ezeket a tranzakciókat a könyvelési pénznemben, amerikai dollárban (USD) jelenti meg.

#### <a name="currency-filter-and-currency-display-combinations"></a>Pénznemszűrő és pénznem megjelenítési kombinációi

Az alábbi táblázat **bemutatja**  **a** jelentés eredményeit, amelyek a beállítások különböző kombinációihoz fordulhatnak elő a Pénznemkijelen és a Pénznem szűrőcelláiban a kiválasztott beállítások miatt. A működési pénznem USD.


| Pénznem megjelenítése cella                        | Pénznemszűrő cella | Eredmények jelentése |
|----------------------------------------------|----------------------|---------------|
| Tranzakció pénzneme                 | **JEN**              | **Y 6000** – Az eredmény csak japán jenben rögzített tranzakciókat mutat meg. |
| Könyvelési pénznem a főkönyvből | **JEN**              |**$60** – Az eredmény csak japán jenben rögzített tranzakciókat mutat meg, ezeket azonban USD-ben jeleníti meg.<p><strong>Megjegyzés:</strong> Az átváltási árfolyam körülbelül 100 JPY / USD.</p> |
| Könyvelési pénznem a főkönyvből | Üres                | **$ 2310** – Az eredmény minden adatot a Főkönyvben beállított könyvelési pénznemben jelenít meg.<p><strong>Megjegyzés:</strong> Ez az összeg a tranzakciók összesítése, könyvelési pénznemben.</p> |
| Tranzakció pénzneme                 | Üres                | **$ 2250** – Az eredmény minden összeget abban a pénznemben mutat meg, amelyben a tranzakciót elvégezték. Ez azt jelenti, hogy a teljes összeg különféle pénznemekből áll össze. |

### <a name="calculation-column-in-a-column-definition"></a>Számítás oszlop egy oszlopdefinícióban

Egy oszlopdefiníció **CALC** típusú oszlopa támogatja az összetett számításokat a **Képlet** cellában, és tartalmazhatja a **+**, **-**, **\**_ és _*/** operátorokat, valamint az **IF/THEN/ELSE** utasításokat. Egy számításoszlop továbbá vonatkozhat bármely másik oszlopra, akár később következő oszlopokra is. Emellett a számítási oszlopok tartalmazhatják a pénzügyi évet és időszakot is, így támogatják az oszlopfejlécet. A számítási képlet legfeljebb 1,024 karakterből állhat. A számítás eredményének százalékban való kifejezéséhez használjon egy speciális formátumfelülírást.

> [!NOTE]
> A számítási képletek eredményeinek kiszámításakor a rendszer a nem nyomtatandó oszloptartományokat nem veszi figyelembe. Például az **A:D** kód a **0** (nulla) összeget nyomtatja ki, míg az **A+B+C** képlet nem nyomtatandó értékekre kiszámítja az értéket.

#### <a name="operators-in-calculation-columns"></a>Számításoszlopokban lévő operátorok

Hozzáadáshoz, kivonáshoz, szorzáshoz vagy osztáshoz a számítás sorrendjében adja meg a kívánt oszlop betűjelét, majd a szükséges műveleti jelet tegye az oszlopok közé. Az alábbi táblázat bemutatja az operátorokat, amelyeket a számításoszlopban használhat.

| Kezelő | Számítási példák | Leírás |
|----------|---------------------|-------------|
| +        | A+C                 | Hozzáadja az A oszlopban szereplő összeget a C oszlop összegéhez. |
| :        | A:C A:C-D           | Egymást követő oszloptartományok hozzáadása. Például az **A:C** képlet összeadja az A-tól C-ig terjedő oszlopok összegeit, míg az **A:C-D** képlet ugyanígy összeadja ezeket, majd kivonja belőlük a D oszlop összegét. |
| -        | A-C                 | A C oszlopban szereplő összeg kivonása az A oszlopban szereplő összegből<p><strong>Megjegyzés:</strong> A mínuszjel (-) segítségével megfordíthatja az oszlopban lévő jeleket. Például az <strong>-A+B</strong> képlettel az A oszlop negatív fordítottjának összegeit adhatja hozzá a B oszlophoz.</p> |
| \*       | A\*C                | Megszorozza az A oszlopban szereplő összeget a C oszlop összegével. |
| /        | A/C                 | Elosztja az A oszlopban szereplő összeget a C oszlop összegével. |

#### <a name="use-a-calculation-formula-in-a-column-definition"></a>Számítási képlet alkalmazása egy oszlopdefinícióban

1. A Jelentéstervezőben nyissa meg a módosítani szükséges oszlopdefiníciót.
2. A megfelelő **CALC** oszlopban adjon meg egy képletet a **Képlet** cellában.

#### <a name="complex-calculations"></a>Összetett számítások

Az összetett számítás cellahivatkozások, operátorok, értékek és beágyazott zárójelek szintjeinek tetszőleges kombinációját tartalmazhatja. Például A és B oszlop átlagának kiszámításához a következő képlet szükséges: **((A+B)/2)**.

#### <a name="specify-report-cells-in-a-column-calculation"></a>Adjon meg egy oszlopszámításban lévő jelentéscellát

Egy adott jelentéscellára is hivatkozhat, ha megadja az oszlop betűjelét és a sor kódját. Például a **B.100** azt a cellát jelöli, amely a B oszlop 100. sorában található. Akár egy egész oszlopot eloszthat egy adott jelentéscellában található összeggel, amely ugyanabban az oszlopban található. Például a **B/B.100** képlet alapján a rendszer elosztja a B oszlop összegét az oszlop 100. sorában található összeggel. Ha a képlet olyan oszlopra hivatkozik, amely egy másik oszlopra támaszkodik, akkor először a függő oszlopot oldja meg. Ha egy oszlopban olyan oszlopra hivatkozik, amely az első oszlopra hivatkozik vissza, akkor hivatkozási hurok hibát eredményez.

> [!NOTE]
> Ha módosítja a jelentés számítási prioritását, előfordulhat, hogy a számítás helytelen lesz. A számításprioritást a jelentésdefiníció **Beállítások** lapján állíthatja be.

#### <a name="multiply-or-divide-a-column-by-a-base-row"></a>Oszlop szorzása vagy elosztása egy alapsorral

Létrehozhat olyan oszlopot, amely egy megadott oszlop értékeit egy alapszám százalékaként jeleníti meg. Ezzel megmutathatja a kapcsolatokat a sorok között, amelyek lehetnek például egy értékesítési sor százalékai, vagy a teljes kiadás sor részarányai. Ahhoz, hogy egy adott oszlop minden egyes sorát megszorozhassa vagy eloszthassa egy alapsorral, írja be az oszlopot a kalkulációba, majd használja a **\*ALAPSOR** vagy a **/ALAPSOR** kódot. Példa: **C\*ALAPSOR** vagy **C/ALAPSOR**.

> [!NOTE]
> Ha alapsorszámítást használ egy oszlopdefinícióban, ügyeljen arra, hogy az oszlopdefinícióval használt minden egyes sordefiníció legalább egy alapsort tartalmazzon a számításokhoz.

#### <a name="divide-the-amount-in-a-column-by-the-number-of-periods"></a>Egy oszlop összegének elosztása az időszakok számával

Egy oszlopban szereplő összeget időszakok egy megadott számával oszhat el. Például a **B/időszakok** képlet elosztja a B oszlop értékét a B oszlopban látható időszakok számának Ha a számítás több oszlopra is kiterjed, adja meg a számításban használandó időszakok számát. Például a **(B+C)/időszakok** képlet összeadja a B oszlop és a C oszlop összegeit, majd elosztja az eredményt az időszak értékével.

## <a name="additional-resources"></a>További erőforrások

[Sordefiníciók a pénzügyi jelentéstervezőben](row-definitions-financial-reporting.md)

[Speciális formázási beállítások a pénzügyi jelentésben](advanced-formatting-options-financial-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
