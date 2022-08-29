---
title: Hibaelhárítás az ER-konfigurációk teljesítményével kapcsolatban
description: Ez a cikk bemutatja, hogyan lehet megtalálni és kijavítani a teljesítménybeli problémákat az elektronikus jelentési (ER) konfigurációkban.
author: kfend
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
ms.openlocfilehash: 283577e70d4e5c4314776f7420857cf8e25e735f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278736"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>Hibaelhárítás az ER-konfigurációk teljesítményével kapcsolatban

Ez a cikk bemutatja, hogyan lehet megtalálni és megoldani a teljesítménybeli problémákat az elektronikus [jelentési](general-electronic-reporting.md) (ER) konfigurációkban [...](general-electronic-reporting.md#Configuration).

A teljesítmény vizsgálata általában több lépésből áll.

1. Adatok [gyűjtése](#collecting-data).
2. Az összegyűjtött adatok elemzése.
3. Az elemzés eredményei alapján az ER-konfigurációk használatával lehet [változtatásokat eszközölni](#making-changes), vagy dönthet úgy, hogy további adatokat gyűjt.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="analyze-execution-time"></a>Végrehajtási idő elemzése

A végrehajtási idő kiszámíthatatlan tényezőktől függhet, például az azonos környezetben futó egyéb feladatoktól és az adatokat az első alkalommal használó gyorsítótárazástól. Ezért többször meg kell ismételnie a végrehajtást és a méréseket.

Bizonyos esetekben a teljesítményproblémákat nem a jelentésekhez használt ER-formátumkonfiguráció okozza. Ehelyett az az X++ kód okozza, amely az ER formátumkonfiguráció megnyitására használatos.

1. A [Műveletközpontban](#infolog-time) vagy az [eseménynaplóban](#event-log-time) tekintse meg a jelentés végrehajtási idejét.
2. Hasonlítsa összes a jelentés teljes végrehajtási idejét az eset teljes végrehajtási idejével.
3. Ha a jelentés végrehajtási ideje sokkal kevesebb, mint a teljes végrehajtási idő, vegye figyelembe a jelentés által feldolgozott adatok mennyiségét:

    - Ha a jelentés kis mennyiségű adatot dolgoz fel, akkor a probléma a konfiguráció betöltési idejéhez is kapcsolódhat.
    - Ha a jelentés nagy mennyiségű adatot dolgoz fel, akkor a probléma az X++ előfeldolgozáshoz is kapcsolódhat. Az eset elemzéséhez használja a [Trace Parser](#analyze-trace-parser-trace) megoldást.

    Egyéb esetekhez lásd a következő szakaszokat.

4. Több, különböző mennyiségű adatot magukban foglaló tesztet futtasson annak megállapításához, hogy a végrehajtás ideje hogyan függ az adatok mennyiségétől.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>Trace Parser hívásláncok elemzése

Állítson össze egy kis példát, vagy gyűjtsön több hívásláncot a jelentéskészítés véletlenszerű részeiből.

Ezután a [Trace Parserben](#trace-parser) egy szabványos, alulról felfelé ható elemzésre válaszolva a következő kérdéseket válaszolja meg:

- Melyek a legfontosabb metódusok az időfelhasználás szempontjából?
- A teljes időnek mekkora részét használják ezek a metódusok?

Válaszolja meg ugyanezeket a kérdéseket a lekérdezésekhez is.

Ha látja, hogy a metódusok előtagja "ER", lépjen tovább a következő szakaszra.

Ha azt látja, hogy a metódusok vagy lekérdezések az alkalmazáscsomagból származnak, akkor fontolja meg az általános optimalizálásokat (például hozzon létre indexeket).

A hívások számának elemzése. Ha a szám jelentősen magasabb a vártnál, akkor célszerű megfontolni a konfiguráció megfelelő csomópontjainak gyorsítótárazását.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>Adatbázishívások elemzése

Készítsen elő kis mennyiségű adatot tartalmazó példát, hogy [ER-nyomkövetést](#electronic-reporting-traces) gyűjthessen össze.

Ezután nyissa meg a hívásláncot az ER modellleképezés-tervezőben, és nézze meg az oldal alját. A következő kérdéseket válaszolja meg:

- Van ismétlődés a lekérdezésekben? Ha van, fontolja meg a következő javítások egyikét:

    - [Használjon gyorsítótárazást](#use-caching), ha úgy gondolja, hogy egy szülőrekordon belül több hívás van.
    - [Gyorsítótárazott, paraméterezett számított mezőt használjon](#cached-parameterized), ha úgy gondolja, hogy ugyanahhoz a rekordhoz több hívás is van több rekordon belül.
    - [Használjon **JOIN** adatforrást](#use-join-datasource), ha az adatbázisból jelentős számú különböző rekordot kell beolvasni.

- A lekérdezések és beolvasási rekordok száma megfelel az adatok teljes összegének? Ha például egy dokumentumnak 10 sora van, akkor a statisztikai adatok azt mutatják, hogy a jelentés 10 sort vagy 1000 sort nyer ki? Ha jelentős számú lekért rekordja van, fontolja meg a következő javítások egyikét:

    - [Az oldalon **található adatok feldolgozása** a WHERE funkció helyett a **FILTER**](#filter) funkcióval Microsoft SQL Server lehetséges.
    - Ugyanazon adatok beolvasásának elkerülése érdekében használjon gyorsítótárazást.
    - Az [összegyűjtött adatfüggvények](#collected-data) segítségével elkerülheti, hogy ugyanezeket az adatokat olvassa be az összegzéshez.

### <a name="analyze-perfview-traces"></a>PerfView-nyomkövetések elemzése

A [PerfView](#perfview) egy tapasztalt fejlesztőknek készült eszköz. A következő lépésekkel kapcsolatos további tudnivalókat lásd a [Wall Clock Time-vizsgálatok alapjai](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics) című részt.

1. Híváslánc begyűjtése a szálidő használatával.
2. Csak a **runUnattended** parancsot használó a vermeket foglalja bele, így csak a konfigurációt végrehajtó szálra szűrhet. (Adja hozzá a **runUnattended** parancsot az **IncPats** beviteli mezőbe.)
3. Minden processzor, hálózati és zárolt idő le legyen összecsukva.
4. [ER-készletek betöltése a PerfView nézethez](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).
5. Válassza ki az **ER** \> **Egyéb előbeállítások** lehetőséget.
6. Nézze meg a neveket:

    - Valószínűleg a legtöbb időt felhasználó platformkód látható.
    - Duplán kattinthat (vagy duplán kattinthat) és végighaladhat a **hívókon**.

        Ha olyan osztályokat talál, amelyek előtagja "ERExpression", és ezek képletekkel kapcsolatos függvények, akkor a függvény nevét az osztálynév alapján ki lehet következtetni, és az attribútumokat megtekintheti az ER-adattárban.

### <a name="fixes"></a>Javítások

- Ha azt látja, hogy a processzoridő nagy része lekérdezésekben van felhasználva, próbálja meg csökkenteni a lekérdezések számát:

    - Ellenőrizze, hogy van-e ismétlődő lekérdezés az [ER-hívásláncban](#analyze-database-calls).
    - Nézze meg, hány rekord van beolvasva, és értékelje ki, hogy elméletileg mennyi adat beolvasása szükséges.

- Ha azt látja, hogy a legtöbb processzoridőt a használt függvények használják fel, keresse meg azt a helyet a konfigurációban, amely a legtöbb erőforrást használja fel.
- Ha azt látja, hogy a processzoridő nagy része az adatgyűjtési függvények használják fel, akkor a modell-leképez oldalán érdemes megfontolni az *SQL-csoportosításra* való lecserélést.

### <a name="collecting-data"></a><a name="collecting-data"></a>Adatgyűjtés

A környezettől függően többféleképpen lehet összegyűjteni az elérhető adatokat:

- A teljes futási idő lekérdezése:

    - A Műveletközpontból
    - Az eseménynaplóból

- A végrehajtás profilozása:

    - Az ER eszközök segítségével
    - A Trace Parser használatával
    - A PerfView használatával

#### <a name="collecting-data-in-a-production-environment"></a>Adatok gyűjtése éles környezetben

Bizonyos esetekben a problémák csak működési környezetben reprodukálhatók. Az adatok a következő módokon gyűjthetők:

- [Trace Parser](../perf-test/trace-trace-tutorial.md) hívásláncok használatával
- [ER végrehajtási](trace-execution-er-troubleshoot-perf.md) hívásláncok használatával
- A teljes végrehajtási idő alkalmazásával

#### <a name="collecting-data-in-a-development-environment"></a>Adatok gyűjtése fejlesztési környezetben

A termelési környezetben használható eszközök mellett számos eszközt használhat fejlesztői környezetben:

- Eseménynapló (Microsoft-Dynamics-ElectronicReporting). Ez a napló a teljes végrehajtási időt adja vissza.
- Általános .NET eszközök, például a PerfView.

Ezenkívül a fejlesztői környezet nagyobb rugalmasságot nyújt a kísérletek során. A jelentések egyes részeit például kikapcsolhatja, hogy megismerhesse hogyan befolyásolják a végrehajtás idejét.

### <a name="tools"></a><a name="tools"></a>Eszközök

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>Végrehajtási idő a Műveletközpontban

Az ER meg tudja mutatni a konfiguráció végrehajtási idejét a műveletközpontban. Ez a beállítás csak egy adott felhasználóra és egy adott vállalatra, és csak interaktív munkamenetek esetén működik. A funkció elérhetővé tételéhez tegye meg a következő lépéseket.

1. Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.
2. A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.
3. A **Felhasználói paraméterek** párbeszédpanelen állítsa a **Fájlgenerálás idejének megjelenítése** beállítást **Igen** értékre.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>Végrehajtási idő az eseménynaplóban

1. Nyissa meg a Windows eseménymegjelenítőt.
2. Az **Alkalmazások és szolgáltatások naplóiban** nyissa meg a **Microsoft-Dynamics-ElectronicReporting/Operational** naplót.
3. Olyan **FormatMapingRun** eseményeket keressen, ahol az **EventID=2**, mivel ezek az események az eltelt időre vonatkozó adatokat tartalmaznak.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Trace Parser hívásláncok 

Mivel az ER az X++-ban van megvalósítva, a teljesítmény elemzésére általános X++ eszközök is használhatók. További információ: [Nyomon követés a Trace Parser használatával](../perf-test/trace-trace-tutorial.md).

Ez a megközelítés néhány korlátozással jár. Mivel az ER egy része C#-ban van megvalósítva, nem minden részlet lesz elérhető. Az adathasználat részletei azonban megtekinthetők. Ezenkívül a hosszú jelentési futtatásokkal túllépheti a nyomkövetés tárolási korlátait.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>ER nyomkövetések

Az ER gyűjtheti saját hívásláncait, és rendelkezik a nyomkövetéshez szükséges megjelenítő és elemzési eszközökkel. További információkért lásd: [Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md).

#### <a name="perfview"></a><a name="perfview"></a>PerfView

Mivel az X++ és az ER is a .NET platformon van megvalósítva, az általános .NET-eszközök használhatók. Használhatja például az ingyenes [PerfView](https://github.com/Microsoft/perfview) eszközt.

A parancssorból is lehet adatokat gyűjteni. A következő Windows PowerShell-parancsfájl például addig gyűjti a végrehajtási időt, amíg a számítógépen le nincs állítva valamilyen formátum-végrehajtás.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

Ez a megközelítés néhány korlátozással jár. Rendszergazdai hozzáférés szükséges a számítógéphez. Ezenkívül tapasztalt fejlesztőnek kell lennie, mert itt elég meredek a tanulási görbe.

### <a name="making-changes"></a><a name="making-changes"></a>Változások alkalmazása

#### <a name="use-caching"></a><a name="use-caching"></a>Gyorsítótárazás használata

Bár a gyorsítótárazás csökkenti az adatok újraolvasásához szükséges időt, memóriát fogyaszt. Gyorsítótárazás használata olyan esetekben, amikor a beolvasott adatok mennyisége nem túl nagy. A további tudnivalókat és a gyorsítótárazás használatát bemutató példát lásd a [modellleképezés javítása a végrehajtási nyomkövetés adatai alapján](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace) részben.

#### <a name="reduce-volume-of-data-fetched"></a><a name="reduce-fetched-data"></a> Bekért adatok térfogatának csökkentése

A gyorsítótárazás memóriafelhasználásának csökkentése érdekében korlátozhatja a futásidőben behívott alkalmazástáblák rekordjainak számát. Ebben az esetben csak azoknak a mezőértéknek a beolvasása történik meg az alkalmazástáblában, amelyekre szüksége van az ER modell megfeleltetése során. A tábla többi mezőjét nem lehet beolvasásra. Ennek megfelelően csökken a beolvasási rekordok gyorsítótárazához szükséges memória térfogata. A további tudnivalókat lásd az [ER-alapú megoldások teljesítményének javítása a futásidőben bekért táblamezők számának csökkentésével](er-reduce-fetched-fields-number.md).

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>Gyorsítótárazott, paraméterezett számított mező használata

Időnként többször is meg kell keresni az értékeket. Ilyen lehet például a fióknév vagy fiókszám. Az idő megtakaraítása érdekében létrehozhat egy számított mezőt, amely a legfelső szinten paraméterekkel rendelkezik, majd hozzáadhatja a mezőt a gyorsítótárhoz.

Javasoljuk, hogy ezt a megközelítést csak akkor használja, ha a gyorsítótárazott adatok mérete kicsi. További információ: [ER-megoldások teljesítményének javítása paraméterezett SZÁMÍTOTT MEZŐ-adatforrások](er-calculated-field-ds-performance.md) hozzáadásával.

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>Egy JOIN adatforrás használata

Az **ÖSSZEKAPCSOLÁS** adatforrás lehetővé teszi több kapcsolódó rekord beolvasását egyetlen lekérdezéssel. Nem kell külön lekérdezést használni minden egyes kapcsolódó rekord beolvasásakor. Ha például 1000 sora van, és kapcsolat szerint olvassa be az egyes sorokat, akkor 1001 lekérdezése lesz (= 1000 + 1). Egy **ÖSSZEKAPCSOLÁS** adatforrás használata esetén csak egy lekérdezést fog használni ugyanazoknak az adatoknak a beolvasására. További információ [Több alkalmazási táblából származó adatok lekéréséhez használja a JOIN adatforrásokat az ER modell-leképezésekben](er-join-data-sources.md).

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>Használja a FILTER függvényt a WHERE függvény helyett

A **[FILTER](er-functions-list-filter.md)** függvény feltételeket futtat az SQL Server kiszolgálón, míg a **WHERE** függvény minden adatot beolvas a listából, egyszerre egy rekordot beolvasva és alkalmazza a feltételt minden rekordra. Például ki szeretne választani egy rekordot 1000 rekordból. Ha a **WHERE** függvényt használja, mind az 1000 rekord be lesz olvasva. A **FILTER** használata esetén viszont pontosan egy rekordot lesz beolvasva. A **FILTER** az adatbázis oldalán is használhat indexeket.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>Összegyűjtött adatfüggvények vagy összesített adatforrás használata

Ha a konfiguráció rendelkezik egy *csoportosítás* összetevővel, amely összegzi a korábban lekért adatokat jelentés szerint, akkor az összetevő újra be fogja olvasni az összes adatot. Az összegyűjtött adatfüggvények használatával az ER számára lehetővé teszi az adatok összegyűjtését az első beolvasás során. A további tudnivalókat lásd: [ER formátum konfigurálása számláláshoz és összegzéshez](tasks/er-format-counting-summing-2.md).

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>A konfiguráció részeinek felülírása X++-ban

Az ER támogatja a táblák és osztályok metódusának ( például a bővítményeknek) a meghívását. A jobb teljesítmény érdekében célszerű átírni a modellleképezés egyes részeit az X++ kódban.

Az ER a következő forrásokból használhat adatokat:

- Osztályok (**objektum** és **osztály** adatforrások)
- Táblák (**tábla** és **táblarekord** adatforrások)

Az [ER alkalmazásprogramozási felület (API)](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) lehetőséget nyújt az előkalkulált adatoknak a hívó kódból történő elküldére is. Az alkalmazáscsomag számos példát tartalmaz erre a megközelítésre.
