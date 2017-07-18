---
title: "Felosztás alapjai"
description: "A témakör a felosztási alapokról nyújt tájékoztatást. A felosztási alapok a költségkönyvelés kulcselemei, és többnyire az általános költségek elosztására szolgálnak."
author: YuyuScheller
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223174
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 74a3033ffbdba2efc6c5ecd6c55019898751a146
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="allocation-bases"></a>Felosztás alapjai 

[!include[banner](../includes/banner.md)]

A felosztási alap az az alap, amely szerint a Költségkönyvelés felosztja az általános költségeket. A felosztási alap olyan mennyiség lehet, mint például a felhasznált számítógépórák száma, a felhasznált kilowattórák (kWh) száma vagy a lefoglalt négyzetméterek száma. A felosztási bázisokat leginkább az általános költségek fedezésére használják a készlethez. Például egy informatikai részleg kiadja költségeit az egyes részlegek által használt számítógépek számának megfelelően.

A Költségkönyvelés felosztási alapjainak három típusa van:

- Előre meghatározott dimenziótag felosztási alapok
- Hierarchiafelosztási alapok
- Receptúrafelosztási alapok

## <a name="predefined-dimension-member-allocation-bases"></a>Előre meghatározott dimenziótag felosztási alapok

Az előre meghatározott dimenziótagok kiosztási bázisai automatikusan létrehozásra kerülnek, amikor egy következő típusú dimenziótagot hoz létre:

- Statisztikai dimenziótagok
- Költségösszetevő-dimenziótagok

> [!NOTE]
> Az előre definiált méretelem-elosztási bázisok, amelyek költségelem-dimenziós tagon alapulnak, csak az adatforrás-szolgáltatótól érik el az értékeket, például a főkönyvet vagy a költségkeretet.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>1. példa: Költségelem-dimenziótag használata a felosztási alaphoz
Ez a példa azt mutatja be, hogyan lehet létrehozni egy költségelosztási szabályt az 10002 költségelem (Munkavállalói biztosítás) elosztására a 10001 (Bérek) költségelemre rögzített egyenlegre. Az elosztási szabály az egyes osztályok fizetése és az összes bére közötti arány alapján kerül meghatározásra. (Az ellenőrzés szükséges.)

A főkönyvben a számlatükör az alábbiak szerint van meghatározva.

| Számlatükör | Fő számla | Leírás        | Főszámla típusa |
|------------------|--------------|--------------------|-------------------|
| Megosztott           | 10001        | Bérek           | Kiadás           |
| Megosztott           | 10002        | Alkalmazotti biztosítások | Kiadás           |

Határozza meg a költségelem dimenziót, és konfigurálja az adatcsatlakozót. Az adatok importálása után a következő bejegyzéseket hozza létre a költségkönyvelés során.

**Költségösszetevő-dimenziótagok**

| Költségösszetevő-dimenzió neve | Költségösszetevő |  Leírás       | Típus    |
|-----------------------------|--------------|--------------------|---------|
| Költségösszetevők               | 10001        | Bérek           | Elsődleges |
| Költségösszetevők               | 10002        | Alkalmazotti biztosítások | Elsődleges |

**Előre meghatározott dimenziótag felosztási alapok** 

| Név  | Leírás        | Költségösszetevő-dimenzió |
|-------|--------------------|------------------------|
| 10001 | Bérek           | Költségösszetevők          |
| 10002 | Alkalmazotti biztosítások | Költségösszetevők          |

A főkönyvben a következő bejegyzések a feladottak:

- A Bérek főfiókot megjelenítő bejegyzések a Bérszámfejtési rendszerből származnak, és a költségközpontokba kerülnek.
- A munkavállalói biztosítás költsége manuálisan kerül át az alapértelmezett költséghelyre.

| Könyvelési dátum | Költséghely |  Leírás        | Fő számla |  Leírás       | Összeg könyvelési pénznemben |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 2017/03/01      | CC001       | HR                  | 10001        | Bérek           | 2,000.00                      |
| 2017/03/01      | CC002       | FI                  | 10001        | Bérek           | 5,000.00                      |
| 2017/03/01      | CC003       | Készletátadás                  | 10001        | Bérek           | 3,000.00                      |
| 2017/03/01      | CC099       | Alapértelmezett költséghely | 10002        | Alkalmazotti biztosítás | 1000,00                      |

A főkönyvi forrásadatok feldolgozását követően a következő bejegyzéseket hozza létre a Költségkönyvelés.

**Költségbejegyzések**

| Költségobjektum |  Leírás        | Költségösszetevő  |  Leírás       | Költség működése   |Összeg|Könyvelési dátum|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | HR                  | 10001         | Bérek           | Nem besorolt    |2,000.00|  2017/03/01    |
| CC002       | FI                  | 10001         | Bérek           | Nem besorolt    |5,000.00|     2017/03/01         |
| CC003       | Készletátadás                  | 10001         | Bérek           | Nem besorolt    |3,000.00|      2017/03/01        |
| CC099       | Alapértelmezett költséghely | 10002         | Alkalmazotti biztosítás | Nem besorolt    |1000,00|      2017/03/01       |

Ez a példa azt mutatja be, hogyan lehet létrehozni egy költségelosztási szabályt az 10002 költségelem (Munkavállalói biztosítás) elosztására a 10001 (Bérek) költségelemre rögzített egyenlegre.

**Költségfelosztás szabály**

| Költségobjektum dimenzióhierarchia-csomópont | Költségösszetevő dimenzióhierarchia-csomópont | Költség működése | Felosztás alapja |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | Nem besorolt  | 10001           |

**Járulékos költség kiszámítása**

Miután az elosztási bázis 10001 (Bérek) költségelemet alkalmaz, az általános számítás eredményei a következők.

| Költségobjektum | Leírás | Nagyság |   Felosztási tényező         | Összeg |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | HR          | 2 000     | (2,000 ÷ 10,000) × 1,000.00 | 200,00 |
| CC002       | FI          | 5 000     | (5,000 ÷ 10,000) × 1,000.00 | 500.00 |
| CC003       | Készletátadás          | 3000     | (3,000 ÷ 10,000) × 1,000.00 | 300,00 |

**Napló**

| Napló | Napló típusa                          | Pénzügyi naptári időszak | Év | Időszak   | Verzió                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | Költségfelosztás számítási naplója | Pénzügyi                 | 2017 | 1. időszak | Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak |

**Költségobjektum-egyenlegek naplóbejegyzései**

| Könyvelési dátum | Költségobjektum | Leírás         | Költségösszetevő | Leírás        | Költség működése |  Összeg  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 2017/01/31      | CC099       | Alapértelmezett költséghely | 10002        | Alkalmazotti biztosítások | Nem besorolt  | 1000,00 |

**Költségbejegyzések**

| Költségobjektum |  Leírás        | Költségösszetevő |    Leírás     | Költség működése | Összeg    | Könyvelési dátum |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | Alapértelmezett költséghely | 10002        | Alkalmazotti biztosítások | Nem besorolt  | -1000,00 | 2017/01/31      |
| CC001       | HR                  | 10002        | Alkalmazotti biztosítások | Nem besorolt  | 200,00    | 2017/01/31      |
| CC002       | FI                  | 10002        | Alkalmazotti biztosítások | Nem besorolt  | 500.00    | 2017/01/31      |
| CC099       | Készletátadás                  | 10002        | Alkalmazotti biztosítások | Nem besorolt  | 300,00    | 2017/01/31      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>2. példa: Statisztikai dimenziótag használata a felosztási alaphoz

A statisztikai dimenzió tagjai felosztási alapként használhatók az irányelvek meghatározására vagy a nem pénzbeli fogyasztás költségelemekkel történő jelentésére. Manuálisan létrehozhat statisztikai dimenzió tagokat, vagy importálhatja azokat egy fájlból az Adatkezelés importálás/exportálás eszköz használatával.

**Statisztikai dimenziótagok**

| Statisztikai dimenzió neve | Statisztikai elem | Leírás               | Egység |
|----------------------------|---------------------|---------------------------|------|
| Statisztikai elemek       | FTE                 | Teljes munkaidős alkalmazottak       | Darab   |
| Statisztikai elemek       | Villamos energia         | Áramfogyasztás   | kWh  |

Ha egy statisztikai dimenzió tag mentésre kerül, a megfelelő rekord létrehozásra kerül az előre definiált dimenzió tag-elosztási bázisokban.

**Előre meghatározott dimenziótag felosztási alapok**

| Név        | Leírás             | Statisztikaielem-dimenziók |
|-------------|-------------------------|-------------------------------|
| FTE         | Teljes munkaidős alkalmazottak     | Statisztikai elemek          |
| Villamos energia | Áramfogyasztás | Statisztikai elemek          |

Statisztikai mérések különböző forrásokból származhatnak:

- A villamosenergia-fogyasztás mérőeszközökkel mérhető, amelyeket a vállalat különböző területein telepítenek.
- A táblázatok statisztikai mértékeket tartalmaznak. Például a HcmEmployment táblázat tartalmaz egy listát az összes alkalmazottról és a költségközpontokról, amelyeken dolgoznak.

| Név       | Költséghely |  Leírás  | Dolgozó típusa |
|------------|-------------|----|-------------|
| A alkalmazott | CC001       | HR | Alkalmazott    |
| B alkalmazott | CC002       | FI | Alkalmazott    |
| C alkalmazott | CC002       | FI | Alkalmazott    |
| D alkalmazott | CC003       | Készletátadás | Alkalmazott    |
| F alkalmazott | CC003       | Készletátadás | Alkalmazott    |

> [!NOTE]
> Minden olyan tábla, amely pénzügyi dimenziókat tartalmaz, statisztikai mérték forrásaként használható.

A költségkönyvelés statisztikai mérések gyűjtését támogatja a következő adatkapcsolatok használatával:

- Adatkezelési importálás/exportálás eszköz
- Statisztikai mértékek

A rendszer statisztikai méréseinek lekéréséhez statisztikai mérőszolgáltatást igénylő sablon szükséges. További információk: Statisztikaimérték-szolgáltató sablon (Ide egy hivatkozás kerül, miután ez a témakör megíródott.)

**Statisztikai mérték szolgáltatójának sablonjai**

| Név  | Funkció | Forrástábla  | Összeg mező      | Dátummező     |
|-------|----------|---------------|----------------|----------------|
| FTE | Számolás    | HcmEmployment | Nem alkalmazható | Nem alkalmazható |

A statisztikai mértékét adatforrásának feldolgozása után a Költségkönyvelésben a következő statisztikai bejegyzések jönnek majd létre.

**Statisztikai bejegyzések**

| Költségobjektum | Leírás      | Könyvelési dátum | Statisztikai dimenziótag | Leírás         | Nagyság |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | HR               | 2017/01/31      | FTE                        | Teljes munkaidős alkalmazottak | 1.00      |
| CC002       | FI               | 2017/01/31      | FTE                        | Teljes munkaidős alkalmazottak | 2.00      |
| CC003       | Készletátadás               | 2017/01/31      | FTE                        | Teljes munkaidős alkalmazottak | 2.00      |

Itt van egy példa a költségelosztási szabályra, ha az FTE előre definiált dimenziótag-felosztási alapját hozzárendeli a rendszer a benne lévő felosztási bázishoz.

| Költségobjektum | Leírás  | Nagyság | Felosztási tényező |
|-------------|------|-----------|-------------------|
| CC001       | HR   | 1.00      | (1/5) x Összeg    |
| CC002       | FI   | 2.00      | (2/5) x Összeg    |
| CC003       | Készletátadás   | 2.00      | (2/5) x Összeg    |

Az Importált statisztikai mérések adatentitásának segítségével statisztikai méréseket importálhat a Költségkönyvelésbe. Használhatja az Adatkezelés importálás/exportálás eszközét is. Az Excelben a következőképpen valósul meg az elektromos áram fogyasztása.

| Könyvelési dátum | Dimenziótag | Nagyság | Forrás azonosítója |
|-----------------|------------------|-----------|-------------------|
| 2017/01/31      | CC001            | 2,450.00  | Villamos energia       |
| 2017/01/31      | CC002            | 4,100.00  | Villamos energia       |
| 2017/01/31      | CC003            | 15,000.00 | Villamos energia       |

A statisztikai mértékét adatforrásának feldolgozása után a Költségkönyvelésben a következő statisztikai bejegyzések jönnek majd létre.

**Statisztikai bejegyzések**

| Költségobjektum |    | Könyvelési dátum | Statisztikai dimenziótag |    Leírás          | Nagyság |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | HR | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 2,450.00  |
| CC002       | FI | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 4,100.00  |
| CC003       | Készletátadás | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 15,000.00 |

Itt van egy példa a költségelosztási szabályra, ha a villamos energia előre meghatározott dimenzió tag-elosztási alapját hozzárendeli az elosztási bázis.

| Költségobjektum | Leírás  | Nagyság | Felosztási tényező          |
|-------------|------|-----------|----------------------------|
| CC001       | HR   | 2,450.00  | (2,450 ÷ 21,550) x Összeg  |
| CC002       | FI   | 4,100.00  | (4,100 ÷ 21,550) x Összeg  |
| CC003       | Készletátadás   | 15,000.00 | (15,000 ÷ 21,550) x Összeg |

## <a name="hierarchy-allocation-bases"></a>Hierarchiafelosztási alapok

A költségkönyvelők manuálisan hozhatják létre a hierarchiák felosztási alapjait egy költségobjektum-dimenzió hierarchikus csomópont meglévő elosztási bázis alkalmazásával. Ily módon korlátozhatja az eredeti előre meghatározott dimenzió tag-elosztási alap tartományát. Egy előre definiált dimenziótag kiosztási alap felhasználható több hierarchikus elosztási bázis létrehozására. A tartományok a költségkeret-dimenzió hierarchiában tarthatók fenn, amely a hierarchia allokációs bázisokhoz kapcsolódik.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>Példa: Hierarchia-allokációs bázisok, amelyek a szervezet teljes munkaidőben foglalkoztatottakra épülnek
Íme egy példa egy költségobjektum-dimenziók hierarchiájára, amelyet egy egyszerűsített szervezet leírásához lehet létrehozni.

| Hierarchia neve | 0 csomópontszint | 1 csomópontszint | 2 csomópontszint | Dimenziótagok |
|----------------|--------------|--------------|--------------|-------------------|
| Szervezet   | Vezérigazgató          | Pénzügyi igazgató          | FICO         | CC001             |
| Szervezet   | Vezérigazgató          | Pénzügyi igazgató          | HR           | CC002             |
| Szervezet   | Vezérigazgató          | Informatikai igazgató          | Készletátadás           | CC003             |

Az előző részben létrehozott FTE előre definiált dimenzióelosztási alapja a következő bejegyzéseket tartalmazza.

**Statisztikai bejegyzések**

| Költségobjektum | Leírás  | Könyvelési dátum | Statisztikai dimenziótag | Leírás | Nagyság |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | HR   | 2017/01/31      | FTE                        | Teljes munkaidős alkalmazottak | 1.00      |
| CC002       | FI   | 2017/01/31      | FTE                        | Teljes munkaidős alkalmazottak | 2.00      |
| CC003       | Készletátadás   | 2017/01/31      | FTE                        | Teljes munkaidős alkalmazottak | 2.00      |

A költségeket el kell osztani a költségparancsok között, amelyek jelentik a szervezet pénzügyi vezetőjének (CFO). Elismert tény, hogy a helyes elosztási arány a teljes munkaidőben foglalkoztatottak (FTE) száma a költségközpont által.

**Hierarchiafelosztási alapok**

| Név                  | Felosztás alapja | Költségobjektum dimenzióhierarchia | Költségobjektum dimenzióhierarchia-csomópont |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| A teljes munkaidőssel egyenértékű vállalati dolgozók száma a CFO-ban | FTE           | Szervezet                    | CFO                                  |

Az Előnézet funkció lehetővé teszi a létrehozott hierarchiafelosztási alap érvényesítését a rendszer statisztikai bejegyzései alapján.

**Felosztási alap részletei**

| Költségobjektum | Leírás  |  Nagyság |
|-------------|------|------------|
| CC001       | HR   | 1.00       |
| CC002       | FI   | 2.00       |

Ha a felosztási alap bele a teljes munkaidőssel egyenértékű Dolgozók a CFO-hierarchiában előre definiált dimenzió tagjának felosztási alap hozzá van rendelve, Íme egy példa költség felosztási szabály.

| Költségobjektum | Leírás  | Nagyság | Felosztási tényező |
|-------------|------|-----------|-------------------|
| CC001       | HR   | 1.00      | (1/3) x Összeg    |
| CC002       | FI   | 2.00      | (2/3) x Összeg    |

## <a name="formula-allocation-bases"></a>Receptúrafelosztási alapok

A képletletöltési bázisok lehetővé teszik, hogy meghatározzuk a fejlett képleteket a megfelelő elosztási alap eléréséhez. Manuálisan létrehozhat képletfelosztási bázisokat.

Amikor létrehoz egy képletfelosztási bázist, akkor válassza ki, hogy melyik statisztikai dimenzió és költségelem dimenzió legyen a képlet alapja. A korábban kiválasztott dimenziókból származó összes allokációs bázis használható egy képletletosztási bázisban.

> [!NOTE]
> A korábban definiált formula allokációs bázisok felhasználhatók egy új formula allokációs bázis meghatározására.

A képletletöltési alapfaktorokban létrehoz egy aliast, és hozzárendelheti azt egy allokációs bázishoz vagy egy konstanshoz. Az aliasokat ezt követően a képlet meghatározásához használja fel a rendszer.

A következő operátorokat használhatja a képlet meghatározásához.

| Szimbólumok | Szöveg           |
|---------|----------------|
| ( )     | Zárójelek    |
| \<      | Kisebb, mint   |
| \>      | Nagyobb mint    |
| +       | Hozzáadás       |
| –       | Kivonás    |
| \*      | szorzás |

A hagyományos **HA** állítások nem támogatottak. Létrehozhat azonban állításokat, és ellenőrizheti, hogy igazak-e.

| Kimutatás | Ellenőrzés | Eredmény |
|-----------|------------|--------|
| a \> b    | Igaz       | 1      |
| a \> b    | Hamis      | 0      |

### <a name="example-1-a-simple-formula"></a>1. példa: egyszerű képlet

A villanyszámlák gyakran két részből állnak:

- A hálózatra való csatlakozás alapdíja
- A kWh-nkénti fogyasztás költsége

Az Áram előre meghatározott tagfelosztási alap meghatározása már megtörtént, és tartalmazza ezeket az értékeket.

**Statisztikai bejegyzések**

| Költségobjektum | Név | Könyvelési dátum | Statisztikai dimenziótag | Leírás             | Nagyság |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | HR   | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 2,450.00  |
| CC002       | FI   | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 4,100.00  |
| CC003       | Készletátadás   | 2017/01/31      | Villamos energia                  | Áramfogyasztás | 15,000.00 |

Ha a rögzített díjnak egyenletesen el kell oszolnia a villamos energiát fogyasztó költségobjektumok között, akkor két lehetősége van a költségek felosztására:

- Hozzon létre egy új, előre definiált felosztási alapot, a Villamosenergia rögzített néven, majd alkalmazzon 1,00-s súlyozást minden olyan költségobjektum esetében, amely villamos energiát fogyasztott.
- Hozzon létre egy receptúrafelosztási bázist, az Rögzített villamos energiát, amely kihasználja a rendszerben már definiált Villamos energia előre meghatározott felosztási bázist. Ennek a lehetőségnek az előnye, hogy az adatokat csak egy villamosenergia statisztikai dimenzió tagjára kell könyvelni.

**Receptúrafelosztási alap** 

| Név              | Költségösszetevő-dimenzió | Statisztikai dimenzió | Receptúra |
|-------------------|------------------------|-----------------------|---------|
| Villamosenergia rögzített |                        | Statisztikai elemek  |         |

A **Receptúra** mező kitöltéséhez meg kell adnia az aliast, amelyet a képletben használni szeretne.

**Receptúrafelosztás alaptényezők**

| Alias | Állandó | Felosztás alapja |
|-------|----------|-----------------|
| a     |          | Villamos energia     |
| b     | 0,01     |                 |

Vegye figyelembe, hogy a nulla nem támogatott állandóként.

**Receptúrafelosztási alap**

| Név              | Költségösszetevő-dimenzió | Statisztikai dimenzió | Receptúra |
|-------------------|------------------------|-----------------------|---------|
| Villamosenergia rögzített |                        | Statisztikai elemek  | a \> b  |

Az Előnézet funkció lehetővé teszi a létrehozott képletletöltési alap érvényesítését a rendszer statisztikai bejegyzései alapján.

**Felosztási alap részletei**

| Költségobjektum | Leírás  | Receptúra           | Nagyság |
|-------------|------|-------------------|-----------|
| CC001       | HR   | 2.450,00 \> 0,01  | 1.00      |
| CC002       | FI   | 4.100,00 \> 0,01  | 1.00      |
| CC003       | Készletátadás   | 15.000,00 \> 0,01 | 1.00      |

Itt van egy példa a költségelosztási szabályra, ha a villamos energia előre meghatározott dimenzió tag-elosztási alapját hozzárendeli az elosztási bázis.

**Költségobjektum-nagyság felosztási tényezője**

| Költségobjektum | Név | Nagyság |  Felosztási tényező |
|-------------|------|-----------|--------------------|
| CC001       | HR   | 1.00      | (1/3) x Összeg     |
| CC002       | FI   | 1.00      | (1/3) x Összeg     |
| CC003       | Készletátadás   | 1.00      | (1/3) x Összeg     |

### <a name="example-2-an-advanced-formula"></a>2. példa: haladó receptúra
Ebben a példában a villamos energia költsége nemcsak a ténylegesen kWh-ban fogyasztott villamos energiát kell, hogy kövesse. A vezetőség ösztönözni szeretné a villamosenergia-fogyasztás csökkentését. 

| Szabály              | Árfolyam | 
|-------------------|------|
| a <= 10000,00 kWh | 0.75 |
| a > 10000,00 kWh  | 1.15 |

Létrejön egy új receptúrafelosztási alap, a Villamosenergia-felhasználás.

**Receptúrafelosztási alap**

| Név              | Költségösszetevő-dimenzió | Statisztikai dimenzió | Receptúra |
|-------------------|------------------------|-----------------------|---------|
| Villamosenergia-használat |                        | Statisztikai elemek  |         |

A **Receptúra** mező kitöltéséhez meg kell adnia az aliast, amelyet a képletben használni szeretne.

**Receptúrafelosztás alaptényezők**

| Alias | Állandó  | Felosztás alapja |
|-------|-----------|-----------------|
| a     |           | Villamos energia     |
| b     | 10,000.00 |                 |
| c     | 0.75      |                 |
| d     | 1.15      |                 |

**Receptúrafelosztási alap**

| Név              | Költségösszetevő-dimenzió | Statisztikai dimenzió | Receptúra                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| Villamosenergia rögzített |                        | Statisztikai elemek  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

Az Előnézet funkció lehetővé teszi a létrehozott képletletöltési alap érvényesítését a rendszer statisztikai bejegyzései alapján.

**Felosztási alap részletei**

| Költségobjektum |    | Receptúra                                                                                                                             | Nagyság |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | HR | ((2,450.00 \> 10.000.00) × ((10,000.00 × 0.75) + (2,450.00 – 10,000.00) × 1.15)) + ((2,450.00 \<= 10,000.00) × 2,450.00 × 0.75)     | 1,837.50  |
| CC002       | FI | ((4,100.00 \> 10.000.00) × ((10,000.00 × 0.75) + (4,100.00 – 10,000.00) × 1.15)) + ((4,100.00 \<= 10,000.00) × 4,100.00 × 0.75)     | 3,075.00  |
| CC003       | Készletátadás | ((15,000.00 \> 10.000.00) × ((10,000.00 × 0.75) + (15,000.00 – 10,000.00) × 1.15)) + ((15,000.00 \<= 10,000.00) × 15,000.00 × 0.75) | 1,3250.00 |

Íme egy közelebbi pillantás a CC003 (IT) receptúrára:

((15,000.00 \> 10,000.00) × ((10,000.00 × 0.75) + (15,000.00 – 10,000.00) × 1.15)) + ((15,000.00 \<= 10,000.00) × 15,000.00 × 0.75) = 13,250.00

(1 × (7,500.00 + 5,000.00 × 1.15)) + (0 × 15,000.00 × 0.75)            

1 × 7,500.00 + 5,750.00 + 0 

Itt van egy példa a költségelosztási szabályra, ha az Elektromos áram rögzített receptúra felosztási alapját hozzárendeli a rendszer a benne lévő felosztási bázishoz.

| Költségobjektum |  Leírás  | Nagyság | Felosztási tényező                |
|-------------|----|-----------|----------------------------------|
| CC001       | HR | 1,837.50  | (1,837.50 ÷ 18,162.50) x Összeg  |
| CC002       | FI | 3,075.00  | (3,075.00 ÷ 18,162.50) x Összeg  |
| CC003       | Készletátadás | 13,250.00 | (13,250.00 ÷ 18,162.50) x Összeg |

