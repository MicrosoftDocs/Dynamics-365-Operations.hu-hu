---
title: Speciális formázási beállítások a pénzügyi jelentésben
description: Ez a témakör ismerteti a speciális formázási funkciókat, többek között a szűrőket, a korlátozásokat, a nem nyomtatási sorokat és a feltételes utasításokat a számításokban.
author: panolte
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.form: FinancialReports
ms.openlocfilehash: 0bc0308fc6140a8b45de1b207a12307a6d731639
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291422"
---
# <a name="advanced-formatting-options-in-financial-reporting"></a>Speciális formázási beállítások a pénzügyi jelentésben

[!include [banner](../includes/banner.md)]

Pénzügyi jelentésről készült jelentés létrehozásakor további formázási funkciók érhetők el, többek között a dimenziók szűrői, oszlopok és jelentési egységek korlátozásai, a nem nyomtatható sorok és a számításokban szereplő IF/THEN/ELSE kimutatások.

Az alábbi táblázat bemutatja a rendelkezésre álló formázási funkciókat a jelentések tervezésekor.

| Funkció                   | Leírás |
|----------------------------|-------------|
| Dimenziószűrő           | Az adatok bizonyos halmazainak eléréséhez használhatja a sordefiníció és oszlopdefiníció dimenzióit. Számos jelentés csak a természetes szegmenst használja a sorformátumban. A sorok azonban módosíthatók, úgy, hogy tartalmazzák a dimenzióértékeket. Az oszlopban a dimenziószűrők adott dimenzióértékek eléréséhez használatosak. |
| Jelentési egység korlátozása | A jelentéssort beállíthatja úgy, hogy csak a meghatározott kimutatási egységhez kapcsolódó információk legyenek láthatók. |
| Nem nyomtatható (NP) sorok     | A nem nyomtatható sorok számos jelentésnél lehetnek hasznosak. Ha több számítás szükséges annak érdekében, hogy egy értéket megkapjunk, ezek a számítások a nyomtatott jelentésen elrejthetők. A nem nyomtatható sorok a jelentéstervezés hibaelhárítása esetén is hasznosak, továbbá speciális cella elhelyezéséhez is. |
| Oszlopkorlátozás         | Az oszlopkorlátozás a sordefinícióban olyan értékek elrejtéséhez ajánlott, melyek csak a jelentés egyes sorainál relevánsak. Ha egy sorban százalékos számításokat végez, az oszlopkorlátozás megakadályozza, hogy az összeg- vagy más oszlopok is ki legyenek nyomtatva, ha azok a számok nem relevánsak. |
| Oszloptörés               | A sordefinícióban oszloptöréseket is hozzáadhat, hogy a jelentés információi egymás mellett jelenjenek meg. Több oszloptörést is hozzáadhat egy sordefinícióhoz, az oszlop fejléce minden oszlop tetején megismétlődik, az oszloptörés után. Az oszloptörések között jelennek meg a jelentéshez írt megjegyzések. |
| IF/THEN/ELSE utasítások     | A számítások a sor- vagy oszlopdefinícióban módosíthatók. |
| Egyszeres idézőjelek ('') és „és” jel (&) használata a dimenzióértékeknél | A jelentéstervezéshez használhat dimenzióértékeket, többek között az „és” jelet. |

## <a name="advanced-cell-placement"></a>Speciális cella elhelyezése

A speciális cella elhelyezése, vagy a *Kényszerítés* adott értékek meghatározott cellába való elhelyezését jelenti. Például a kényszerítés gyakran használatos a megfelelő egyenleg elmozdítására egy pénzforgalmi jelentésben. A kényszerítést például a következő célokra használhatja:

- Microsoft Excel-táblázatokból származó értékeket helyezhet el adott cellákban.
- Bizonyos értékek végleges kódolása egy jelentésbe.
- Jelek módosítása úgy, hogy egy értéket kimásol egy előző cellából, és ezt az értéket megszorozza -1-gyel.

> [!NOTE]
> Sok esetben úgy kell konfigurálnia a jelentésdefiníciót, hogy az oszlopszámítások a sorszámítások előtt történjenek. Ennek a konfigurációnak a befejezéséhez kövesse az alábbi lépéseket.
>
> 1. A Jelentéstervezőben nyissa meg a jelentésdefiníciót.
> 2. A **Beállítások** lapon, a **Számítási prioritás** lehetőségnél jelölje be az **Először az oszlopszámítás, majd a sorszámítás végrehajtása** lehetőséget.

## <a name="designing-the-report"></a>A jelentés megtervezése

A jelentés tervezésekor először hozza létre a leíró sorokat, hogy az értékek az elvárások szerint legyenek behúzva. Ezután adja hozzá a **NP** (nem nyomtatható) formátumot, hogy elrejtse a végleges értékeket tartalmazó részleteket.

> [!IMPORTANT]
> Ha a sordefinícióban a **SZÁM** formátumkódot használja, nem áshat le a tranzakciók részleteibe.

A kényszerítéshez a képletek a következő formátumot használják: &lt;<céloszlop&gt;=&lt;forrásoszlop&gt;.&lt;sor kódja&gt; A sor további hozzáadott helyeit vesszővel és szóközzel kell elválasztani. Példa: D=C.190,E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Példák speciális formázási beállításokra

Az alábbi példák bemutatják, hogyan formatáljuk a sordefiníciót és az oszlopdefiníciót, hogy alapvető pénzforgalmi jelentést (1. példa) és statisztikai jelentést (2. példa) kapjunk.

### <a name="example-1-basic-forcing"></a>1. példa: alapvető kényszerítés

Az alábbi táblázat egy sordefiníció példáját mutatja be, amely alapvető kényszerítést használ.

| Sorkód |           Leírás            | Formátumkód | Kapcsolódó képletek/sorok/egységek |        Sormódosító        | Hivatkozás pénzügyi dimenziókra |
|----------|----------------------------------|-------------|-----------------------------|----------------------------|------------------------------|
| 100      | Készpénz az időszak elején (NP) |             |                             | Számlamódosító = \[/ BB\] | +Szegmens2: = \[1100\]         |
| 1.3.0      | Készpénz az időszak kezdetén      | CAL         | C=C.100,F=D.100             |                            |                              |
| 160      |                                  |             |                             |                            |                              |
| 190      |                                  |             |                             |                            |                              |

> [!NOTE]
> Az előző táblázatban a bemutató céljára üres oszlopok lettek eltávolítva: a Formátum felülbírálásához, a Normál egyenleg, a Nyomtatás-ellenőrzés és az Oszlopkorlátozás oszlopok nem jelennek meg.

Az alábbi táblázat egy oszlopdefiníció példáját mutatja be, amely alapvető kényszerítést használ a sorban.

|           Formátum             | A   | milliárd    | K        | T      | E      | P    |
|------------------------------|-----|------|----------|--------|--------|------|
| 1. fejléc                     |     |      |          |        |        |      |
| 2. fejléc                     | A   | milliárd    | K        | T      | E      | P    |
| 3. fejléc                     |     |      |          |        |        |      |
| Oszloptípus                  | ROW | DESC | FD       | FD     | FD     | CALC |
| Könyvelési kód / Attribútumkategória |     |      | TÉNYLEGES   | TÉNYLEGES | TÉNYLEGES |      |
| Pénzügyi év                  |     |      | ALAP     | ALAP   | ALAP   |      |
| Időszak                       |     |      | ALAP     | ALAP   | ALAP   |      |
| Érintett időszakok              |     |      | IDŐSZAKOS | IDEI/BB | IDEI    |      |
| Receptúra                      |     |      |          |        |        | E-D  |
| Oszlopszélesség                 | 5   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>2. példa: statisztikai jelentések

Az alábbi táblázat egy sordefiníció példáját mutatja be, amely kényszerítést használ a statisztikai jelentéshez.

| Sorkód | Leírás               | Formátumkód | Kapcsolódó képletek/sorok/egységek     | Formátum felülbírálása      | Normál egyenleg | Hivatkozás pénzügyi dimenziókra               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|--------------------------------------------|
| 50       | Statisztikai adatok   | REM         |                                 |                      |                |                                            |
| 100      | Létszám - Egyesült Államok            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |                                            |
| 115      | Létszám - nemzetközi | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |                                            |
| 1.3.0      |                           |             |                                 |                      |                |                                            |
| 190      | Egyesült államokbeli értékesítés                  |             |                                 |                      | K              | +Szegmens2 = \[41 \*\], Szegmens3 = \[00\]    |
| 220      | Nemzetközi értékesítés       |             |                                 |                      | K              | + Szegmens2 = \[41\*\], Szegmens3 = \[01:99\] |
| 250      |                           |             |                                 |                      |                |                                            |
| 280      |                           |             |                                 |                      |                |                                            |
| 310      | Egyesült államokbeli értékesítés                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |                                            |
| 340      | Nemzetközi értékesítés       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |                                            |

> [!NOTE]
> Az előző táblázatban a bemutató céljára üres oszlopok lettek eltávolítva: a Nyomtatás-ellenőrzés, az Oszlopkorlátozás és a Sormódosító oszlopok nem jelennek meg.

Az alábbi táblázat egy oszlopdefiníció példáját mutatja be, amely kényszerítést használ a statisztikai jelentéshez.

|    Formátum                    | A   | milliárd    | K      | T            | E     | P            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| 1. fejléc                     | A   | milliárd    | K      | T            | E     | P            |
| 2. fejléc                     | -   | -    | Folyó évi    | Éves értékesítés | Munkatárs | $ személyenként |
| 3. fejléc                     |     |      |        |              |       |              |
| Oszloptípus                  | SOR | DESC | FD     | CALC         | CALC  | CALC         |
| Könyvelési kód / Attribútumkategória |     |      | TÉNYLEGES |              |       |              |
| Pénzügyi év                  |     |      | ALAP   |              |       |              |
| Időszak                       |     |      | ALAP   |              |       |              |
| Érintett időszakok              |     |      | IDEI    |              |       |              |
| Receptúra                      |     |      |        |              |       | E-D          |
| Oszlopszélesség                 | 5   | 30   | 14     | 14           | 14    | 14           |

## <a name="restricting-a-row-to-a-specific-reporting-unit"></a>Egy meghatározott jelentési egységre korlátozza a sort.

Ha egy jelentési sort egy bizonyos jelentési egységre korlátozunk, akkor az a sor a csatolt adatokat csak a megnevezett jelentési egységhez mutatja, és a jelentési fa egyéb jelentési egységeinél az adatokat figyelmen kívül hagyja. Például létrehozhat egy sort, amely a teljes működési költségek egy adott részleghez tartozó részleteit jeleníti meg. A jelentés ismétlődő adatokat tartalmazhat, ha a jelentés tartalmaz egy jelentési fát és sordefiníciót is, amely a természetes fiókon túl többet is tartalmaz. Például adott egy jelentési fa, amely a cégen belül hat részleget sorol fel, és adott egy sordefiníció is, amely egy számla és egy részleg meghatározott kombinációját sorolja fel. A jelentés létrehozásakor a számla és a részleg a megadott kombinációja lesz rányomtatva a jelentési fa minden szintjére annak ellenére, hogy az adott részleg lehet, hogy nem felel meg annak, ami a fában van. Ennek az az oka, hogy a sor felülbírálja azt, amit a jelentésdefiníció általában kiszűr. Az adatismétlődés elkerülésének egyik módja, hogy egy sort egy meghatározott jelentési egységre korlátozunk.

> [!NOTE]
> Ha egy sor dimenziókat tartalmaz, és ezt a sort egy alárendelt jelentési egységre korlátozza, a sor összege szerepelni fog az adott alárendelt egységnél és fölérendelt egységeinél, de nem fordul elő ismétlődés.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Sor korlátozása egy jelentési egységre

1. A Jelentés Tervező eszközben, kattintson a **Sor Definíciók**, majd válassza ki a sor definíciót, hogy módosítsa.
2. Kattintson duplán a megfelelő **Kapcsolódó képletek/sorok/egységek** cellára.
3. A **Jelentési egység kiválasztása** párbeszédpanelen található **Jelentésfa** mezőben válassza ki a jelentésdefinícióban megadott fát.
4. Válasszon ki egy jelentési egységet, és kattintson az **OK** gombra. A korlátozás a sordefiníció cellájában jelenik meg.
5. Kattintson duplán a cellára a korlátozott sor **Hivatkozás a pénzügyi dimenziókhoz** oszlopában, és írjon be egy hivatkozást a pénzügyi adatok rendszerébe.

## <a name="selecting-print-control-in-a-row-definition"></a>Nyomtatásvezérlés kijelölése sordefinícióban

Az egyes oszlopokhoz megadhat nyomtatásvezérlő kódokat a **Nyomtatásvezérlés** cella használatával.

### <a name="add-print-control-codes-to-a-report-row"></a>Nyomtatásvezérlő kódok hozzáadása a jelentés sorához

1. Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.
2. Kattintson duplán a **Nyomtatásvezérlő** cellára.
3. A **Nyomtatásvezérlés** párbeszédpanelen jelöljön ki egy nyomtatásvezérlő kódot, vagy tartsa lenyomva a Ctrl billentyűt több kód kiválasztásához. Nyomtatásvezérlő kódokat közvetlenül a **Nyomtatásvezérlés** cellába is beírhat. Ha több nyomtatásvezérlő kód van, ezeket vesszővel válassza el egymástól.
4. Válasszon ki bármilyen feltételes nyomtatási beállítást.
5. Kattintson az **OK** gombra.

### <a name="regular-print-control-codes"></a>Szokásos nyomtatási ellenőrzőkódok

A következő táblázat leírja a sordefiníció szokásos nyomtatásvezérlő kódjait.

| Nyomtatási vezérlőkód | A nyomtatásvezérlő kód értelmezése         | Leírás |
|--------------------|--------------------------------------------------|-------------|
| NP                 | Nem nyomtatható sor                                 | Előzze meg, hogy a sorban szereplő összegek ki legyenek nyomtatva a jelentésben, és zárja ki az összegeket a számításokból. Nem nyomtatandó oszlopoknak a számításba való beiktatásához közvetlenül az oszlopra kell hivatkozni a számítási képletben. Például a 240. nem nyomtatható sor szerepel a következő számításban: **230+240+250**. Azonban a 240. nem nyomtatható sor nem szerepel a következő számításban: **230:250**. |
| CS                 | Pénznemszimbólum; ebben a sorban pénznem formátumot kell használni | A pénznem szimbólumát minden nem százalékos összegnek tartalmaznia kell. A százalékos értékek sosem kapnak pénznemszimbólumot. |
| XD                 | Sor elrejtése a számla részletes jelentésében            | Számlák elrejtése a számla részletes jelentéseiben és a tranzakció részletes jelentéseiben. Ez a nyomtatásvezérlő akkor hasznos, ha a sor több fiókot tartalmaz, amelyeknek nem szabad szerepelniük a számla részletes jelentésén vagy a tranzakció részletes jelentésén. |
| X0                 | Sor elrejtése, ha az összes nulla                        | Sor kizárása a jelentésből, ha az adott sorban az összes cella üres vagy nullákat tartalmaz. Ennek a nyomtatásvezérlőnek csak akkor van értelme, ha a nulla egyenleg elrejtése nincs bejelölve a jelentés definíciójában. |
| B0                 | Hagyja üresen a nulla oszlopokat                         | Hagyja a sorban üresen azokat az oszlopokat, amelyek nulla mennyiségeket tartalmaznak. |
| XR                 | Kumulatív frissítés kihagyása                                  | Kumulatív frissítés kihagyása. Ha a jelentés egy jelentési fát használ, az adott sorban szereplő összegek nem lesznek összesítve későbbi fölérendelt csomópontokba. |
| SR                 | Kerekítés elrejtése                                | Az ebben a sorban szereplő összegek kerekítésének megakadályozása. |
| SZÖVEG                 | Sor elrejtése a tranzakció részletes jelentésében        | A tranzakciók elrejtése a tranzakció részletes jelentésein. Ez a nyomtatásvezérlő akkor hasznos, ha a sor több fiókot tartalmaz, amelyeknek nem szabad szerepelniük a számla részletes jelentésén vagy a tranzakció részletes jelentésén. |

### <a name="conditional-print-control-codes"></a>Feltételes nyomtatási ellenőrzőkódok

A következő táblázat leírja a sordefiníció feltételes nyomtatásvezérlő kódjait.

| Nyomtatási vezérlőkód | Leírás                                  |
|--------------------|----------------------------------------------|
| (nincs)             | Törli a feltételes nyomtatási választást.       |
| ST                 | Csak a tartozik egyenlegek nyomtatása a sorban.  |
| K                 | Csak a követel egyenlegek nyomtatása a sorban. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Oszlopkorlátozás cella egy oszlopdefinícióban

Az **Oszlopkorlátozás** cellának a sordefinícióban több célja van. Attól függően, hogy milyen típusú sorról van szó, használhatja az **Oszlopkorlátozás** cellát a következő funkciók egyikének megadására:

- A cella a sor összegeinek nyomtatását egy adott oszlopra korlátozhatja. Ez a funkció akkor hasznos, ha táblázatos mérleget hoz létre.
- A cella meg tudja határozni a rendezni kívánt összegek oszlopát.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Számítási képlet alkalmazása egy sordefinícióban

Egy sordefinícióban a számítási képlet a **+**, **-**, **\**_ és _*/** operátorokat tartalmazhatja, és az **IF/THEN/ELSE** utasításokat. Továbbá a számítás egyes cellákat és abszolút összegeket (a képletben szereplő tényleges számokat) foglalhat magában. A képlet legfeljebb 1,024 karakterből állhat. A számítások nem alkalmazhatók olyan sorokra, melyek **Hivatkozás a pénzügyi dimenziókhoz** (FD) típusú cellákat tartalmaznak. Azonban alkalmazhat számításokat egymás utáni sorokon, kihagyhatja ezen sorok nyomtatását, és ezután összesítheti a számítási sorokat.

### <a name="operators-in-a-calculation-formula"></a>Egy számítási képlet operátorai

A számítási képletek összetettebb operátorokat használnak, mint a sorösszegző képletek. Azonban használhatja a **\**_ és _*/** operátorokat a további operátorokkal együtt az összegek szorzásához (\*) és (/) elosztásához. Egy tartomány vagy az összeg számítási képletben való használatához a kukac (@) jelet kell használni minden sorkód előtt, kivéve, ha oszlopot használ a sordefinícióban. Például ha a 100. sor összegét szeretné hozzáadni a 330. sor összegéhez, használhatja a **100 + 330** sorösszeg képletet vagy a **@100+@330** számítási képletet.

> [!NOTE]
> Minden sorkód előtt, amelyet számítási képletben használ, használnia kell a kukac (@) jelet. Ellenkező esetben a szám abszolút összegként lesz beolvasva. Ha például a képlet **@100 + 330**, akkor 330 USD-t ad a 100-as sorban lévő összeghez. Amikor a számítási képletben szereplő oszlopra hivatkozik, nem szükséges a kukac jel (@).

### <a name="create-a-calculation-formula"></a>Számítási képlet létrehozása

1. A Jelentés Tervező eszközben, kattintson **Sor Definíciók**, majd nyissa meg a sor definíciót, hogy módosítsa.
2. Kattintson duplán a **Formátumkód** cellára, majd válassza ki a **CAL** lehetőséget.
3. A **Kapcsolódó képletek/Sorok/Egységek** cellába írja be a számítási képletet.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Példa a számítási képletre adott sorokhoz

Ebben a példában a **@100+@330** számítási képlet azt jelenti, hogy a 100-as sor összege hozzáadásra kerül a 330. összegéhez. A sor **340+370** teljes képlete hozzáadja a 340. sor összegét a 370. sor összegéhez. (A 370. sorban lévő összeg a számítási összegből származó összeg.)

| Sorkód | Leírás                 | Formátumkód | Kapcsolódó képletek/Sorok/Egység | Nyomtatásvezérlés | Sormódosító | Pénzügyi Dimenziókhoz Csatolás |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Készpénz az időszak kezdetén |             |                            | NP            | BB           | +Számla=\[1100:1110\]       |
| 370      | Készpénz az év kezdetén   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Készpénz az időszak kezdetén | TOT         | 340+370                    |               |              |                              |

Ha a sor a sordefinícióban **CAL** formátumkóddal rendelkezik, és matematikai számítást ír be a **Kapcsolódó képletek/Sorok/Egységek** cellába, akkor is meg kell adnia a jelentésen a kapcsolódó oszlop és sor betűjét. Például adja meg a következőt: **A.120** az A oszlop és 120. sor jelölésére. Másik lehetőségként használhatja a kukac (@) jelet az összes oszlop kijelölésére. Például adja meg a következőt: **@120**, amely a 120. sor összes oszlopára vonatkozik. Minden olyan matematikai számítás, amely nem rendelkezik oszlopbetűvel vagy kukac (@) jellel, valós számként lesz értelmezve.

> [!NOTE]
> Megjegyzés: címke sorkód használatakor pontot (.) kell használni az oszlopbetű és a címke elválasztására (például **A.BRUTTÓ\_NYERESÉG/A.ÉRTÉKESÍTÉS**). Ha kukac jelet (@) használ, az elválasztó nem kötelező (például **\@BRUTTÓ\_HASZON/@ÉRTÉKESÍTÉS**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Példa a számítási képletre egy adott sorhoz

Ebben a példában a számítási képlet **E=C.340** azt jelenti, hogy a C oszlop, 340-es sor cellájában lévő cella számításai csak az E oszlopra vonatkozóan van elvégezve.

> [!NOTE]
> Amikor a számítási képletben szereplő oszlopra hivatkozik, nem szükséges a kukac jel (@).

| Sorkód | Leírás                 | Formátumkód | Kapcsolódó képletek/Sorok/Egység | Nyomtatásvezérlés | Sormódosító | Pénzügyi Dimenziókhoz Csatolás |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Készpénz az időszak elején (NP) |             |                            | NP            | BB           | +Számla=\[1100:1110\]       |
| 370      | Készpénz az év elején   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Készpénz az időszak elején (NP) | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Szám módosítása a kijelölt oszlopokban

Amikor módosít egy számot vagy számítást egy bizonyos sor egyik oszlopában, de nem szeretné, hogy ez a jelentés többi oszlopára hatással legyen, megadhatja a **CAL** (Számítás) lehetőséget a sordefiníció **Formátumkód** oszlopában.

- Ha egy számítást a jelentés összes (**FD**) oszlopán el szeretne végezni, ne adjon meg oszlop-hozzárendelést.
- Ha egy képletet bizonyos oszlopokra kíván korlátozni, írja be az oszlopbetűt, egy egyenlőségjelet (**=**), és ezután a képletet.
- Megadhat hogy több oszlopot. Ha a kukac jelet (@) megadott oszlopelhelyezéssel használja, a kukac jel (@) a sorhoz kapcsolódik.
- Több oszlopképletet is megadhat egy sorban. A képleteket vesszővel válassza el egymástól.

### <a name="calculation-examples"></a>Számítási példák

| Számítás            | Művelet létrehozása                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Minden oszlopban a 130. sor értéke 0,75-tel szorzódik. Az eredmény megjelenik az aktuális sor minden oszlopában. |
| B=@130\*.75            | Ugyanez a számítás a B oszlop esetében is megtörténik.                                                                      |
| A,B,C=(@100/@130)\*.75 | A=(A.100/A.130)\*,75 B=(B.100/B.130)\*,75 C=(C.100/C.130)\*,75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>IF/THEN/ELSE utasítások a sordefinícióban

Az **IF/THEN/ELSE** állításokat bármely érvényes számításhoz hozzá lehet adni, és lehet őket használni a **CAL** formátummal. Az **IF/THEN/ELSE** számítási képleteket a cellában, a **Kapcsolódó képletek/Sorok/Egységek** oszlopban kell megadni. Az **IF/THEN/ELSE** számítási képletek a következő formátumot használják: IF &lt;igaz/hamis állítás&gt; THEN &lt;képlet&gt; ELSE &lt;képlet&gt; Az ELSE **&lt;képlet&gt;** rész az utasításban opcionális.

#### <a name="if-statements"></a>IF utasítások

Az állítás, amely az **IF** állítást követi, bármilyen állítás lehet, amely igazként vagy hamisként értékelhető. Az állítás, amely az **IF** állítást követi, vonatkozhat egy egyszerű értékelésre, vagy lehet egy összetett állítás, amely több kifejezést tartalmazhat. Íme néhány példa:

- **IF A.200&gt;0** (Egyszerű értékelés)
- **IF A.200&gt;0 AND A.200&lt;10000** (Összetett állítás)
- **IF A.200&gt;10000 OR ((A.340/B.1200)\*2 &lt;1200)** (Összetett utasítás, amely több kifejezést tartalmaz)

Az **Időszakok** kifejezés az **IF** állításban az időszakok számát jelenti a jelentésben. Ez a kifejezés rendszerint az átlag kiszámításához használatos, év elejétől az aktuális dátumig. Például ha a jelentést a 7 IDEI időszakra futtatja, a **B.150/Időszakok** állítás azt jelenti, hogy a 150. sor B oszlop értékét a program elosztja a 7-tel.

#### <a name="then-and-else-formulas"></a>THEN és ELSE képletek

A **THEN** és AZ **ELSE** képletek lehetnek bármilyen érvényes számítások, a nagyon egyszerű értékhozzárendelésektől az összetett képletekig. Például az **IF A.200&gt;0 THEN A=B.200** utasítás azt jelenti, hogy „Ha a 200. sor A osztlopában a cella értéke nagyobb, mint 0 (nulla), a 200. sor B oszlopában lévő cella értékét másolja át az aktuális sor A oszlopában lévő cellába." A megelőző **IF/THEN** állítás ad meg értéket az aktuális sor egy oszlopában. Azonban használhatja a kukac jelet (@) is az igaz/hamis értékelésekben, vagy pedig a képletet, az összes oszlop jelölésére. Íme néhány további példa, amelyek a következő szakaszokban vannak leírva:

- **IF A.200 &gt;0 THEN B.200**: Ha az A.200 cella értéke pozitív, akkor a B.200 cella értékét az aktuális sor minden oszlopába be kell írni.
- **IF A.200&gt;0, THEN @200**: Ha az A.200 cella értéke pozitív, akkor a 200. sor minden oszlopának értékét az aktuális sor megfelelő oszlopába be kell írni.
- **IF @200 &gt;0 THEN @200**: Ha az aktuális oszlop 200. sorában az érték pozitív, akkor a 200. sor értéke ugyanabba az oszlopba, az aktuális sorba kerül.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Egy számítás egy sordefiníció egyik jelentési egységére korlátozása

A jelentési fában egy számítás egyetlen jelentési egységére való korlátozásához, úgy, hogy az eredményül kapott összeg ne legyen egy magasabb szintű egységbe összesítve, a **\@Unit** a kódot használhatja a sordefiníció **Kapcsolódó képletek/Sorok/Egységek** cellájában. A **\@Unit** kód a jelentési fa B oszlopában szerepel, **Egység neve**. Ha a **\@Unit** kódot használja, az értékek nem lesznek összesítve, de a számítás a jelentési fa minden szintjén értékelődik.

> [!NOTE]
> Ennek a funkciónak a használatához jelentési fának társítva kell lennie a sordefinícióval.

A számítási sor vonatkozhat egy számítási sorra vagy egy pénzügyi adatsorra. A számítást a rendszer rögzíti a sordefiníció **Kapcsolódó képletek/Sorok/Egységek** cellájába és a pénzügyi adat típusú korlátozásba. A számításnak feltételes számítást kell használnia, amely **IF \@Unit** szerkezettel kezdődik. Példa: IF @Unit(SALES) THEN @100 ELSE 0 Ez a számítás a jelentés minden oszlopának a 100. sorában szereplő összegre vonatkozik, de csak az ÉRTÉKESÍTÉSI (SALES) egység számára. Ha több egységnek is ÉRTÉKESÍTÉS (SALES) a neve, az összeg minden ilyen egységben megjelenik. Ezenkívül a 100. sor lehet pénzügyi adatokat tartalmazó sor, és meg lehet adni, hogy ne legyen nyomtatható. Ebben az esetben az összeget a rendszer nem jeleníti meg a fa összes egységében. Az összeget a jelentés egyetlen oszlopára is korlátozhatja, például a H oszlopra, úgy, hogy oszlopkorlátozást használ, melynek segítségével az érték a jelentésnek csak ebben az oszlopában lesz kinyomtatva. Felvehet **OR** kombinációkat is az **IF** kimutatásban. Példa: **IF @Unit(SALES) OR @Unit(SALESWEST) THEN 5 ELSE @100**. A következő módokon lehet megadni az egységet a számítási típus korlátozásában:

- Egységnév megadása a megfelelő egységek szerepeltetéséhez Például az **IF \@Unit(SALES)** lehetővé teszi, hogy minden ÉRTÉKESÍTÉS (SALES) nevű egységre vonatkozzon a számítás, akkor is, ha több ÉRTÉKESÍTÉSI (SALES) egység szerepel a jelentési fában.
- Ha a számítást a cégen belül csak bizonyos egységekre kívánja korlátozni, adja meg a cég és az egység nevét. Például adja meg az **IF @Unit (ACME:SALES)** kódot, ha a számítást az ACME vállalaton belül az ÉRTÉKESÍTÉSI (SALES) egységekre szeretné korlátozni.
- Adja meg a teljes hierarchiakódot a jelentési fából, hogy egy meghatározott egységre korlátozza a számítást. Például adja meg az **IF @Unit(SUMMARY^ACME^WEST COAST^SALES)** kódot.

> [!NOTE]
> A teljes hierarchiakód megállapításához kattintson jobb gombbal a jelentésfa-definícióra, majd válassza a **Jelentési egység azonosítójának (H-kód) másolása** parancsot.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Számítás korlátozása egy adott jelentési egységre

1. A Report Designer eszközben kattintson a **Sordefiníciók** lehetőségre, majd nyissa meg a módosítani kívánt sordefiníciót.
2. Kattintson duplán a **Formátumkód** cellára, majd válassza ki a **CAL** lehetőséget.
3. Kattintson a **Kapcsolódó képletek/Sorok/Egységek** cellára, és adjon meg egy feltételes számítást, amely egy **IF \@Unit** szerkezettel kezdődik.

### <a name="ifthenelse-statements-in-a-column-definition"></a>IF/THEN/ELSE utasítások az oszlopdefinícióban

Az **IF/THEN/ELSE** állítás lehetővé teszi, hogy bármely számítás bármely más oszlopból származó eredményektől függjön. Más oszlopokra is lehet hivatkozni, de nem hivatkozhat az **IF** állításban lévő jelentési cellára. Minden számítást az egész oszlopra kell alkalmazni. Például az **IF B&gt;100 THEN B ELSE C\*1.25** utasítás a következőt jelenti: „Ha a B oszlop összege 100-nál nagyobb, akkor B oszlop értékét helyezze a **CALC** oszlopba. Ha a B oszlop összege nem nagyobb 100-nál, akkor C oszlop értékét szorozza meg 1,25-tel, és helyezze át az eredményt a **CALC** oszlopba. " Mindig kövesse az **IF** állítást egy logikus állítással, amely értékelhető igazként vagy hamisként. A képletek, melyeket a **THEN** és az **ELSE** állításokhoz is használ tartalmazhatnak hivatkozásokat tetszőleges számú oszlopra, és ezek a képletek annyira lesznek összetettek, amennyire szeretné.

> [!NOTE]
> Egy számítás eredményeit nem helyezheti át a többi oszlopba. Az eredményeknek a képletet tartalmazó oszlopban kell lenniük.

#### <a name="use-single-quotes-and-an-ampersand-for-dimension-values-in-a-row-column-or-tree"></a>Egyszeres idézőjelek ('') és „és” jel (&) használata a dimenzióértékeknél egy sorban, oszlopban vagy fastruktúrában

Jelentéseket tervezhet dimenzióértékek használatával, amelyekben „és” jel (&) szerepel.

Bármely **Kapcsolás pénzügyi dimenziókhoz** mezőn belül megadhat olyan értéket, mint például az **Eredmény (P&L)**. A dimenzióérték mindkét oldalán szereplő egyszeres idézőjelek ('') azt jelzik, hogy szövekonstans értéket használ, például az „és” (&) jelet.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
