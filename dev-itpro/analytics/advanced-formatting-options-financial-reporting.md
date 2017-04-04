---
title: "Speciális formázási beállítások a pénzügyi jelentésben"
description: "Pénzügyi jelentésről készült jelentés létrehozásakor további formázási funkciók érhetők el, többek között a dimenziók szűrői, oszlopok és jelentési egységek korlátozásai, a nem nyomtatható sorok és a számításokban szereplő IF/THEN/ELSE kimutatások."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 631fec1dc135565e6d38e7faf193a7a898b508cb
ms.lasthandoff: 03/29/2017


---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Speciális formázási beállítások a pénzügyi jelentésben

Pénzügyi jelentésről készült jelentés létrehozásakor további formázási funkciók érhetők el, többek között a dimenziók szűrői, oszlopok és jelentési egységek korlátozásai, a nem nyomtatható sorok és a számításokban szereplő IF/THEN/ELSE kimutatások. 

Az alábbi táblázat bemutatja a rendelkezésre álló formázási funkciókat a jelentések tervezésekor.

| Funkció                   | Leírás                                                                                                                                                                                                                                                                                                                     |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dimenziószűrő           | Az adatok bizonyos halmazainak eléréséhez használhatja a sordefiníció és oszlopdefiníció dimenzióit. Számos jelentés csak a természetes szegmenst használja a sorformátumban. A sorok azonban módosíthatók, úgy, hogy tartalmazzák a dimenzióértékeket. Az oszlopban a dimenziószűrők adott dimenzióértékek eléréséhez használatosak. |
| Jelentési egység korlátozása | A jelentéssort beállíthatja úgy, hogy csak a meghatározott kimutatási egységhez kapcsolódó információk legyenek láthatók.                                                                                                                                                                                                                      |
| Nem nyomtatható (NP) sorok     | A nem nyomtatható sorok számos jelentésnél lehetnek hasznosak. Ha több számítás szükséges annak érdekében, hogy egy értéket megkapjunk, ezek a számítások a nyomtatott jelentésen elrejthetők. A nem nyomtatható sorok a jelentéstervezés hibaelhárítása esetén is hasznosak, továbbá speciális cella elhelyezéséhez is.                                                    |
| Oszlopkorlátozás         | Az oszlopkorlátozás a sordefinícióban olyan értékek elrejtéséhez ajánlott, melyek csak a jelentés egyes sorainál relevánsak. Ha egy sorban százalékos számításokat végez, az oszlopkorlátozás megakadályozza, hogy az összeg- vagy más oszlopok is ki legyenek nyomtatva, ha azok a számok nem relevánsak.                              |
| Oszloptörés               | A sordefinícióban oszloptöréseket is hozzáadhat, hogy a jelentés információi egymás mellett jelenjenek meg. Több oszloptörést is hozzáadhat egy sordefinícióhoz, az oszlop fejléce minden oszlop tetején megismétlődik, az oszloptörés után. Az oszloptörések között jelennek meg a jelentéshez írt megjegyzések.                              |
| IF/THEN/ELSE utasítások     | A számítások a sor- vagy oszlopdefinícióban módosíthatók.                                                                                                                                                                                                                                                         |

## <a name="advanced-cell-placement"></a>Speciális cella elhelyezése
A speciális cella elhelyezése, vagy a *Kényszerítés* adott értékek meghatározott cellába való elhelyezését jelenti. Például a kényszerítés gyakran használatos a megfelelő egyenleg elmozdítására egy pénzforgalmi jelentésben. A kényszerítést például a következő célokra használhatja:

-   Értékek a Microsoft Excelből adott cellába való áthelyezése.
-   Bizonyos értékek végleges kódolása egy jelentésbe.
-   Jelek módosítása úgy, hogy egy értéket kimásol egy előző cellából, és ezt az értéket megszorozza -1-gyel.

**Megjegyzés:** Sok esetben úgy kell konfigurálnia a jelentésdefiníciót, hogy az oszlopszámítások a sorszámítások előtt történjenek. Ennek a konfigurációnak a befejezéséhez kövesse az alábbi lépéseket.

1.  A Jelentéstervezőben nyissa meg a jelentésdefiníciót.
2.  A **Beállítások** lapon, a **Számítási prioritás** lehetőségnél jelölje be az **Először az oszlopszámítás, majd a sorszámítás végrehajtása** lehetőséget.

## <a name="designing-the-report"></a>A jelentés megtervezése
A jelentés tervezésekor először hozza létre a leíró sorokat, hogy az értékek az elvárások szerint legyenek behúzva. Ezután adja hozzá a **NP** (nem nyomtatható) formátumot, hogy elrejtse a végleges értékeket tartalmazó részleteket. **Fontos:** Ha a **CAL** formátumkódot használja a sordefinícióban, akkor nem tud leásni tranzakció részleteihez. Az újraindítás, a képletek a következő formátum használandó: &lt;céloszlop&gt;=&lt;származó oszlopok&gt;. &lt;sor kód&gt; egymástól vesszővel és szóközzel sor bármilyen további gyakorlatok. Példa: D=C.190,E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Példák speciális formázási beállításokra
Az alábbi példák bemutatják, hogyan formatáljuk a sordefiníciót és az oszlopdefiníciót, hogy alapvető pénzforgalmi jelentést (1. példa) és statisztikai jelentést (2. példa) kapjunk.

### <a name="example-1-basic-forcing"></a>1. példa: alapvető kényszerítés

Az alábbi táblázat egy sordefiníció példáját mutatja be, amely alapvető kényszerítést használ.

| Sorkód | Leírás                      | Formátumkód | Kapcsolódó képletek/Sorok/Egységek | Formátum felülbírálása | Normál egyenleg | Nyomtatásvezérlés | Oszlopkorlátozás | Sormódosító               | Pénzügyi Dimenziókhoz Csatolás |
|----------|----------------------------------|-------------|-----------------------------|-----------------|----------------|---------------|--------------------|----------------------------|------------------------------|
| 100      | Készpénz az időszak elején (NP) |             |                             |                 |                |               |                    | Módosító számla = \[/bb\] | + Segment2 = \[1100\]         |
| 130      | Készpénz az időszak elején (NP)      | CAL         | C=C.100,F=D.100             |                 |                |               |                    |                            |                              |
| 160      |                                  |             |                             |                 |                |               |                    |                            |                              |
| 190      |                                  |             |                             |                 |                |               |                    |                            |                              |

Az alábbi táblázat egy oszlopdefiníció példáját mutatja be, amely alapvető kényszerítést használ a sorban.

|                              | N   | milliárd    | K        | A      | E:      | P    |
|------------------------------|-----|------|----------|--------|--------|------|
| 1. fejléc                     |     |      |          |        |        |      |
| 2. fejléc                     | N   | milliárd    | K        | A      | E:      | P    |
| 3. fejléc                     |     |      |          |        |        |      |
| Oszloptípus                  | SOR | DESC | FD       | FD     | FD     | CALC |
| Könyvelési kód / Attribútumkategória |     |      | TÉNYLEGES   | TÉNYLEGES | TÉNYLEGES |      |
| Pénzügyi év                  |     |      | ALAP     | ALAP   | ALAP   |      |
| Időszak                       |     |      | ALAP     | ALAP   | ALAP   |      |
| Érintett időszakok              |     |      | IDŐSZAKOS | IDEI/BB | IDEI    |      |
| Receptúra                      |     |      |          |        |        | E-D  |
| Oszlopszélesség                 | 5   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>2. példa: statisztikai jelentések

Az alábbi táblázat egy sordefiníció példáját mutatja be, amely kényszerítést használ a statisztikai jelentéshez.

| Sorkód | Leírás               | Formátumkód | Kapcsolódó képletek/Sorok/Egységek     | Formátum felülbírálása      | Normál egyenleg | Nyomtatásvezérlés | Oszlopkorlátozás | Sormódosító | Pénzügyi Dimenziókhoz Csatolás               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|---------------|--------------------|--------------|--------------------------------------------|
| 50       | Statisztikai adatok   | REM         |                                 |                      |                |               |                    |              |                                            |
| 100      | Létszám - Egyesült Államok            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 115      | Létszám - nemzetközi | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 130      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 190      | Egyesült államokbeli értékesítés                  |             |                                 |                      | K              |               |                    |              | + Segment2 = \[41\*\], Segment3 = \[00\]    |
| 220      | Nemzetközi értékesítés       |             |                                 |                      | K              |               |                    |              | + Segment2 = \[41\*\], Segment3 = \[01:99\] |
| 250      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 280      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 310      | Egyesült államokbeli értékesítés                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |               |                    |              |                                            |
| 340      | Nemzetközi értékesítés       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |               |                    |              |                                            |

Az alábbi táblázat egy oszlopdefiníció példáját mutatja be, amely kényszerítést használ a statisztikai jelentéshez.

|                              | A:   | milliárd    | K      | T            | E:     | P            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| 1. fejléc                     | A:   | milliárd    | K      | T            | E:     | P            |
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
Ha egy jelentési sort egy bizonyos jelentési egységre korlátozunk, akkor az a sor a csatolt adatokat csak a megnevezett jelentési egységhez mutatja, és a jelentési fa egyéb jelentési egységeinél az adatokat figyelmen kívül hagyja. Például létrehozhat egy sort, amely a teljes működési költségek egy adott részleghez tartozó részleteit jeleníti meg. A jelentés ismétlődő adatokat tartalmazhat, ha a jelentés tartalmaz egy jelentési fát és sordefiníciót is, amely a természetes fiókon túl többet is tartalmaz. Például adott egy jelentési fa, amely a cégen belül hat részleget sorol fel, és adott egy sordefiníció is, amely egy számla és egy részleg meghatározott kombinációját sorolja fel. A jelentés létrehozásakor a számla és a részleg a megadott kombinációja lesz rányomtatva a jelentési fa minden szintjére annak ellenére, hogy az adott részleg lehet, hogy nem felel meg annak, ami a fában van. Ennek az az oka, hogy a sor felülbírálja azt, amit a jelentésdefiníció általában kiszűr. Az adatismétlődés elkerülésének egyik módja, hogy egy sort egy meghatározott jelentési egységre korlátozunk. **Megjegyzés:** Ha egy sor dimenziókat tartalmaz, és ezt a sort egy alárendelt jelentési egységre korlátozza, a sor összege szerepelni fog az adott alárendelt egységnél és fölérendelt egységeinél, de nem fordul elő ismétlődés.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Sor korlátozása egy jelentési egységre

1.  A Jelentés Tervező eszközben, kattintson a **Sor Definíciók**, majd válassza ki a sor definíciót, hogy módosítsa.
2.  Kattintson duplán a megfelelő **Kapcsolódó képletek/Sorok/Egységek** cellára.
3.  A **Jelentési egység választása** párbeszédpanelben, a **Jelentési fa** mezőben válassza ki a fát, amely be van jelölve a jelentésdefinícióban.
4.  Válasszon ki egy jelentési egységet, és kattintson az **OK** gombra. A korlátozás a sordefiníció cellájában jelenik meg.
5.  Kattintson duplán a cellára a korlátozott sor **Hivatkozás a pénzügyi dimenziókhoz** oszlopában, és írjon be egy hivatkozást a pénzügyi adatok rendszerébe.

## <a name="selecting-print-control-in-a-row-definition"></a>Nyomtatásvezérlés kijelölése sordefinícióban
Az egyes oszlopokhoz megadhat nyomtatásvezérlő kódokat a **Nyomtatásvezérlés** cella használatával.

### <a name="add-print-control-codes-to-a-report-row"></a>Nyomtatásvezérlő kódok hozzáadása a jelentés sorához

1.  Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.
2.  Kattintson duplán a **Nyomtatásvezérlő** cellára.
3.  A **Nyomtatásvezérlés** párbeszédpanelen jelöljön ki egy nyomtatásvezérlő kódot, vagy tartsa lenyomva a Ctrl billentyűt több kód kiválasztásához. Nyomtatásvezérlő kódokat közvetlenül a **Nyomtatásvezérlés** cellába is beírhat. Ha több nyomtatásvezérlő kód van, ezeket vesszővel válassza el egymástól.
4.  Válasszon ki bármilyen feltételes nyomtatási beállítást.
5.  Kattintson az **OK** gombra.

### <a name="regular-print-control-codes"></a>Szokásos nyomtatási ellenőrzőkódok

A következő táblázat leírja a sordefiníció szokásos nyomtatásvezérlő kódjait.

| Nyomtatási vezérlőkód | A nyomtatásvezérlő kód értelmezése         | Leírás                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Nem nyomtatható sor                                 | Előzze meg, hogy a sorban szereplő összegek ki legyenek nyomtatva a jelentésben, és zárja ki az összegeket a számításokból. Nem nyomtatandó oszlopoknak a számításba való beiktatásához közvetlenül az oszlopra kell hivatkozni a számítási képletben. Például a 240. nem nyomtatható sor szerepel a következő számításban: **230+240+250**. Azonban a 240. nem nyomtatható sor nem szerepel a következő számításban: **230:250**. |
| CS                 | Pénznemszimbólum; ebben a sorban pénznem formátumot kell használni | A pénznem szimbólumát minden nem százalékos összegnek tartalmaznia kell. A százalékos értékek sosem kapnak pénznemszimbólumot.                                                                                                                                                                                                                                                                                                |
| XD                 | Sor elrejtése a számla részletes jelentésében            | Számlák elrejtése a számla részletes jelentéseiben és a tranzakció részletes jelentéseiben. Ez a nyomtatásvezérlő akkor hasznos, ha a sor több fiókot tartalmaz, amelyeknek nem szabad szerepelniük a számla részletes jelentésén vagy a tranzakció részletes jelentésén.                                                                                                                                                           |
| X0                 | Sor elrejtése, ha az összes nulla                        | Sor kizárása a jelentésből, ha az adott sorban az összes cella üres vagy nullákat tartalmaz. Ennek a nyomtatásvezérlőnek csak akkor van értelme, ha a nulla egyenleg elrejtése nincs bejelölve a jelentés definíciójában.                                                                                                                                                                                            |
| B0                 | Hagyja üresen a nulla oszlopokat                         | Hagyja a sorban üresen azokat az oszlopokat, amelyek nulla mennyiségeket tartalmaznak.                                                                                                                                                                                                                                                                                                                                                      |
| XR                 | Kumulatív frissítés kihagyása                                  | Kumulatív frissítés kihagyása. Ha a jelentés egy jelentési fát használ, az adott sorban szereplő összegek nem lesznek összesítve későbbi fölérendelt csomópontokba.                                                                                                                                                                                                                                                                               |
| SR                 | Kerekítés elrejtése                                | Az ebben a sorban szereplő összegek kerekítésének megakadályozása.                                                                                                                                                                                                                                                                                                                                                          |
| SZÖVEG                 | Sor elrejtése a tranzakció részletes jelentésében        | A tranzakciók elrejtése a tranzakció részletes jelentésein. Ez a nyomtatásvezérlő akkor hasznos, ha a sor több fiókot tartalmaz, amelyeknek nem szabad szerepelniük a számla részletes jelentésén vagy a tranzakció részletes jelentésén.                                                                                                                                                                                                             |

### <a name="conditional-print-control-codes"></a>Feltételes nyomtatási ellenőrzőkódok

A következő táblázat leírja a sordefiníció feltételes nyomtatásvezérlő kódjait.

| Nyomtatási vezérlőkód | Leírás                                  |
|--------------------|----------------------------------------------|
| (nincs)             | Törli a feltételes nyomtatási választást.       |
| ST                 | Csak a tartozik egyenlegek nyomtatása a sorban.  |
| K                 | Csak a követel egyenlegek nyomtatása a sorban. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Oszlopkorlátozás cella egy oszlopdefinícióban
Az **Oszlopkorlátozás** cellának a sordefinícióban több célja van. Attól függően, hogy milyen típusú sorról van szó, használhatja az **Oszlopkorlátozás** cellát a következő funkciók egyikének megadására:

-   A cella a sor összegeinek nyomtatását egy adott oszlopra korlátozhatja. Ez a funkció akkor hasznos, ha táblázatos mérleget hoz létre.
-   A cella meg tudja határozni a rendezni kívánt összegek oszlopát.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Számítási képlet alkalmazása egy sordefinícióban
Sordefiníció a számítási képlet tartalmazhat a **+**, **-**, **\***, és **/**piaci szereplők, és **IF/THEN/ELSE** kimutatások. Továbbá a számítás egyes cellákat és abszolút összegeket (a képletben szereplő tényleges számokat) foglalhat magában. A képlet legfeljebb 1,024 karakterből állhat. A számítások nem alkalmazhatók olyan sorokra, melyek **Hivatkozás a pénzügyi dimenziókhoz** (FD) típusú cellákat tartalmaznak. Azonban alkalmazhat számításokat egymás utáni sorokon, kihagyhatja ezen sorok nyomtatását, és ezután összesítheti a számítási sorokat.

### <a name="operators-in-a-calculation-formula"></a>Egy számítási képlet operátorai

A számítási képletek összetettebb operátorokat használnak, mint a sorösszegző képletek. Azonban is lehet használni a **\***és **/**és szorozzuk meg a további piaci szereplők piaci szereplők (\*) és osztás (/) összegeket. Egy tartomány vagy az összeg számítási képletben való használatához a kukac (@) jelet kell használni minden sorkód előtt, kivéve, ha oszlopot használ a sordefinícióban. Például az összeg 100 sor hozzáadása az összeg sorában 330, használhatja a sor teljes képlet **100 + 330** vagy a számítási képlet **@100+@330**. **Megjegyzés:** Minden sorkód előtt, amelyet számítási képletben használ, használnia kell a kukac (@) jelet. Ellenkező esetben a szám abszolút összegként lesz beolvasva. Például a képlet **@100+330** USD 330 ad hozzá a 100 sor összege. Amikor a számítási képletben szereplő oszlopra hivatkozik, nem szükséges a kukac jel (@).

### <a name="create-a-calculation-formula"></a>Számítási képlet létrehozása

1.  A Jelentés Tervező eszközben, kattintson **Sor Definíciók**, majd nyissa meg a sor definíciót, hogy módosítsa.
2.  Kattintson duplán a **Formátumkód** cellára, majd válassza ki a **CAL** lehetőséget.
3.  A **Kapcsolódó képletek/Sorok/Egységek** cellába írja be a számítási képletet.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Példa a számítási képletre adott sorokhoz

Ebben a példában a számítási képlet **@100+@330** azt jelenti, hogy 100 sor összege bekerül az összeg sorában 330. A sor teljes képlet **340 + 370** hozzáadja az összeg sor 340 370 sor összege. (370 sor összege nem a számítási képlet származó összeggel.)

| Sorkód | Leírás                 | Formátumkód | Kapcsolódó képletek/Sorok/Egység | Nyomtatásvezérlés | Sormódosító | Pénzügyi Dimenziókhoz Csatolás |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Készpénz az időszak elején (NP) |             |                            | NP            | BB           | + Számla =\[1100:1110\]       |
| 370      | Készpénz az év elején   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Készpénz az időszak elején (NP) | TOT         | 340+370                    |               |              |                              |

Ha a sor a sordefinícióban **CAL** formátumkóddal rendelkezik, és matematikai számítást ír be a **Kapcsolódó képletek/Sorok/Egységek** cellába, akkor is meg kell adnia a jelentésen a kapcsolódó oszlop és sor betűjét. Például, adja meg az **A.120** sor oszlop A jelölésére, a 120. Másik lehetőségként használhatja a kukac (@) az összes oszlop jelzi. Például, adja meg az **@120**120 sorban az összes oszlop jelölésére. A matematikai számítást, amely nem tartalmaz egy oszlop betűjelét vagy kukac (@) valós számot tekinti. **Megjegyzés:** egy sor hivatkozni a címke sor kódot használja, ha egy pontot (.) kell használnia az oszlop betűjelét és a címke elválasztására (például **A.GROSS\_MARGIN/A.SALES**). Ha egy kukac (@), az elválasztó nem szükséges (például **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Példa a számítási képletre egy adott sorhoz

Ebben a példában a számítási képlet **E=C.340**, amely azt jelenti, hogy a C oszlop, 340. sor cellájában a számítás csak az E oszlopon lesz elvégezve. **Megjegyzés:** ha hivatkozik egy oszlopra egy számítási képletben, a kukac jel (@) nem kötelező.

| Sorkód | Leírás                 | Formátumkód | Kapcsolódó képletek/Sorok/Egység | Nyomtatásvezérlés | Sormódosító | Pénzügyi Dimenziókhoz Csatolás |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Készpénz az időszak elején (NP) |             |                            | NP            | BB           | + Számla =\[1100:1110\]       |
| 370      | Készpénz az év elején   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Készpénz az időszak elején (NP) | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Szám módosítása a kijelölt oszlopokban

Amikor módosít egy számot vagy számítást egy bizonyos sor egyik oszlopában, de nem szeretné, hogy ez a jelentés többi oszlopára hatással legyen, megadhatja a **CAL** (Számítás) lehetőséget a sordefiníció **Formátumkód** oszlopában.

-   Ha egy számítást a jelentés összes (**FD**) oszlopán el szeretne végezni, ne adjon meg oszlop-hozzárendelést.
-   Képlet csak adott oszlopok, adja meg az oszlop betűjelét, egy egyenlőségjelet (**=**), majd az eredményt.
-   Megadhat hogy több oszlopot. Ha a kukac jelet (@) megadott oszlopelhelyezéssel használja, a kukac jel (@) a sorhoz kapcsolódik.
-   Több oszlopképletet is megadhat egy sorban. A képleteket vesszővel válassza el egymástól.

### <a name="calculation-examples"></a>Számítási példák

| Számítás            | Művelet létrehozása                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Minden oszlopban a 130. sor értéke 0,75-tel szorzódik. Az eredmény megjelenik az aktuális sor minden oszlopában. |
| B=@130\*.75            | Ugyanez a számítás a B oszlop esetében is megtörténik.                                                                      |
| A, B,C=(@100/@130)\*.75 | A=(A.100/A.130)\*.75 B=(B.100/B.130)\*.75 C=(C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>IF/THEN/ELSE utasítások a sordefinícióban

Az **IF/THEN/ELSE** állításokat bármely érvényes számításhoz hozzá lehet adni, és lehet őket használni a **CAL** formátummal. Az **IF/THEN/ELSE** számítási képleteket a cellában, a **Kapcsolódó képletek/Sorok/Egységek** oszlopban kell megadni. **IF/THEN/ELSE** számítási képletet használja a következő formátumot: Ha &lt;igaz/hamis nyilatkozat&gt; majd &lt;képlet&gt; ELSE &lt;képlet&gt; az **ELSE &lt;képlet&gt;** része a nyilatkozat nem kötelező.

#### <a name="if-statements"></a>IF utasítások

Az állítás, amely az **IF** állítást követi, bármilyen állítás lehet, amely igazként vagy hamisként értékelhető. Az állítás, amely az **IF** állítást követi, vonatkozhat egy egyszerű értékelésre, vagy lehet egy összetett állítás, amely több kifejezést tartalmazhat. Íme néhány példa:

-   **Ha A.200&gt;0** (egyszerű értékelés)
-   **Ha A.200&gt;0 és A.200&lt;10 000** (összetett utasítás)
-   **Ha A.200&gt;10000 vagy ((A.340/B.1200)\*2 &lt;1200)** (összetett utasítás több kifejezéseket tartalmazó)

Az **Időszakok** kifejezés az **IF** állításban az időszakok számát jelenti a jelentésben. Ez a kifejezés rendszerint az átlag kiszámításához használatos, év elejétől az aktuális dátumig. Például ha a jelentést a 7 IDEI időszakra futtatja, a **B.150/Időszakok** állítás azt jelenti, hogy a 150. sor B oszlop értékét a program elosztja a 7-tel.

#### <a name="then-and-else-formulas"></a>THEN és ELSE képletek

A **THEN** és AZ **ELSE** képletek lehetnek bármilyen érvényes számítások, a nagyon egyszerű értékhozzárendelésektől az összetett képletekig. Ha például a kimutatás **Ha A.200&gt;0, akkor a A=B.200** azt jelenti, "Ha az a cella, sor 200 a. oszlopában több mint 0 (nulla), 200 sor B oszlopában a cella értékét üzembe a cellát az a oszlopban az aktuális sor." A megelőző **IF/THEN** állítás ad meg értéket az aktuális sor egy oszlopában. Azonban használhatja a kukac jelet (@) is az igaz/hamis értékelésekben, vagy pedig a képletet, az összes oszlop jelölésére. Íme néhány további példa, amelyek a következő szakaszokban vannak leírva:

-   **Ha A.200 &gt;0, akkor a B.200**: A.200 cella értéke pozitív, ha az aktuális sor összes oszlopának helyezni, a cella B.200 érték.
-   **Ha A.200 &gt;majd 0 @200**: A.200 cella értéke pozitív, ha az érték minden egyes sor 200 oszlopában helyezni a megfelelő oszlop az aktuális sor.
-   **Ha @200&gt;majd 0 @200**: 200 sorában az aktuális oszlop értéke pozitív, ha az ugyanabban az oszlopban az aktuális sor helyezni, 200 sor értékét.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Egy számítás egy sordefiníció egyik jelentési egységére korlátozása

Számítás a jelentési fában egy jelentési egységet úgy, hogy az így keletkező összeget nem felvetített magasabb szintű egység korlátozásához használja a **@Unit**a kód a **kapcsolódó képletek/sorok/egységek** a sordefiníció cellájára. A **@Unit**kód szerepel, a B oszlopban a jelentési fa **egység neve**. Ha a **@Unit**kód, az értékeket nem felvetített, de a számítás a jelentési fa minden szintjén történik. **Megjegyzés:** Ennek a funkciónak a használatához jelentési fának társítva kell lennie a sordefinícióval. A számítási sor vonatkozhat egy számítási sorra vagy egy pénzügyi adatsorra. A számítást a rendszer rögzíti a sordefiníció **Kapcsolódó képletek/Sorok/Egységek** cellájába és a pénzügyi adat típusú korlátozásba. A számítást kell használni feltételes számítás kezdődő egy **Ha @Unit**építése. Példa: Ha @Unit(eladás) majd @100ELSE 0 Ez a számítás 100 sor minden oszlopban a jelentés összeget tartalmazza, de csak értékesítési egység számára. Ha több egységnek is ÉRTÉKESÍTÉS (SALES) a neve, az összeg minden ilyen egységben megjelenik. Ezenkívül a 100. sor lehet pénzügyi adatokat tartalmazó sor, és meg lehet adni, hogy ne legyen nyomtatható. Ebben az esetben az összeget a rendszer nem jeleníti meg a fa összes egységében. Az összeget a jelentés egyetlen oszlopára is korlátozhatja, például a H oszlopra, úgy, hogy oszlopkorlátozást használ, melynek segítségével az érték a jelentésnek csak ebben az oszlopában lesz kinyomtatva. Felvehet **OR** kombinációkat is az **IF** kimutatásban. Példa: Ha @Unit(értékesítés) vagy @Unit(SALESWEST), majd 5 ELSE @100megadhatja egy egységet a számítás típusú korlátozása a következő módszerek valamelyikével:

-   Egységnév megadása a megfelelő egységek szerepeltetéséhez Például **Ha @Unit(értékesítés)** lehetővé teszi, hogy minden egység Eladások nevű kiszámítása akkor is, ha több értékesítési egységek szerepelnek a jelentési fa.
-   Ha a számítást a cégen belül csak bizonyos egységekre kívánja korlátozni, adja meg a cég és az egység nevét. Például, adja meg **Ha @Unit(ACME: eladási**) korlátozhatja a ACME vállalat értékesítési egységek a számításban.
-   Adja meg a teljes hierarchiakódot a jelentési fából, hogy egy meghatározott egységre korlátozza a számítást. Például, adja meg az **Ha @Unit(összefoglaló ^ ACME ^ nyugati PARTJÁN ^ értékesítés)**. **Megjegyzés:** A teljes hierarchiakód megkereséséhez kattintson a jobb gombbal a jelentési fa meghatározásában, és válassza a **Jelentési azonosítójának másolása (H-kód)** lehetőséget.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Számítás korlátozása egy jelentési egységre

1.  A Jelentés Tervező eszközben, kattintson **Sor Definíciók**, majd nyissa meg a sor definíciót, hogy módosítsa.
2.  Kattintson duplán a **Formátumkód** cellára, majd válassza ki a **CAL** lehetőséget.
3.  Kattintson a **kapcsolódó képletek/sorok/egységek** cellára, és írja be a feltételes számítás kezdődő egy **Ha @Unit**építése.

### <a name="ifthenelse-statements-in-a-column-definition"></a>IF/THEN/ELSE utasítások az oszlopdefinícióban

Az **IF/THEN/ELSE** állítás lehetővé teszi, hogy bármely számítás bármely más oszlopból származó eredményektől függjön. Más oszlopokra is lehet hivatkozni, de nem hivatkozhat az **IF** állításban lévő jelentési cellára. Minden számítást az egész oszlopra kell alkalmazni. Ha például a kimutatás **Ha B&gt;100 majd más B-C\*1,25** azt jelenti, "Ha B oszlopban szereplő összeg több mint 100, helyezze az érték a B oszlopot a **CALC** oszlop. Ha a B oszlop összege nem nagyobb 100-nál, akkor C oszlop értékét szorozza meg 1,25-tel, és helyezze át az eredményt a **CALC** oszlopba. " Mindig kövesse az **IF** állítást egy logikus állítással, amely értékelhető igazként vagy hamisként. A képletek, melyeket a **THEN** és az **ELSE** állításokhoz is használ tartalmazhatnak hivatkozásokat tetszőleges számú oszlopra, és ezek a képletek annyira lesznek összetettek, amennyire szeretné. **Megjegyzés:** Egy számítás eredményeit nem helyezheti át a többi oszlopba. Az eredményeknek a képletet tartalmazó oszlopban kell lenniük.


