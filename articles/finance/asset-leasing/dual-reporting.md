---
title: Kettős jelentéskészítés
description: Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444164"
---
# <a name="dual-reporting"></a>Kettős jelentéskészítés

[!include [banner](../includes/banner.md)]

Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben. A Microsoft Dynamics 365 Finance-ben a feladási rétegek ismeretével a példa könnyebben érthető lesz.

## <a name="example"></a>Példa

A következő példa az olasz jog szerinti lízinget mutatja be, amelyben a kötelezően előírt jelentés a pénzalap módszert és az IFRS-jelentési módszereket alkalmazza. A vállalatnak három könyvet kell létrehoznia, hogy mind az olasz, mind az IFRS 16 követelményeit figyelembe tudja venni. Egy könyv szükséges az IFRS 16 esetében, egy könyv szükséges a törvényi követelményekhez, és egy könyv szükséges a kötelező feladások automatikus sztornírozásához. A könyveket a következő táblákban látható módon lehet beállítani.

**IFRS 16 könyv**

Az IFRS 16 könyvet úgy kell beállítani, hogy megfeleljen az IFRS 16 könyvelési szabványának. A könyvbe feladott összes bejegyzést egy egyéni rétegre adja fel a program.

| Név                                    | Leírás    |
|-----------------------------------------|----------------|
| Könyv típusa                               | IFRS 16        |
| Könyv leírása                        | IFRS 16        |
| Feladási réteg                           | 1. egyéni réteg |
| Lízingtípus                              | Finance        |
| Könyvelési keretrendszer                    | IFRS 16        |
| Lízingfutamidő / hasznos élettartam beállítás         | 0,00           |
| Jelenérték / Eszköz valós értékének beállítása | 0,00           |
| Rövid távú küszöb                    | 12             |
| Alacsony értékű küszöb                     | 5,000.00       |
| Fizetés szállítónak                           | Nincs             |

**Kötelező könyv**

A kötelező könyv egy készpénzalapú könyv, ahol a vállalat a lízingköltséget a havi fizetés összegeként adja fel, amely az egyes hónapok bérletét fedezi. Ez a könyv nem termel használatijog-eszközt (ROU) vagy lízingkötelezettséget.

| Név                                    | Leírás |
|-----------------------------------------|-------------|
| Könyv típusa                               | Kötelező   |
| Könyv leírása                        | Helyi GAAP  |
| Feladási réteg                           | Aktuális     |
| Lízingtípus                              | Automatikus   |
| Könyvelési keretrendszer                    | Készpénzalap  |
| Lízingfutamidő / hasznos élettartam beállítás         | 0,00        |
| Jelenérték / Eszköz valós értékének beállítása | 0,00        |
| Rövid távú küszöb                    | 0           |
| Alacsony értékű küszöb                     | 0           |
| Fizetés szállítónak                           | Nincs          |

**Kötelező sztornírozási könyv**

A kötelező sztornírozási könyvet ugyanúgy kell beállítani, mint a kötelező könyvet.

| Név                                    | Leírás                    |
|-----------------------------------------|--------------------------------|
| Könyv típusa                               | Kötelező – Sztornírozás           |
| Könyv leírása                        | A kötelező könyv sztornírozási könyve |
| Feladási réteg                           | 1. egyéni réteg                 |
| Lízingtípus                              | Automatikus                      |
| Könyvelési keretrendszer                    | Készpénzalap                     |
| Lízingfutamidő / hasznos élettartam beállítás         | 0,00                           |
| Jelenérték / Eszköz valós értékének beállítása | 0,00                           |
| Rövid távú küszöb                    | 0                              |
| Alacsony értékű küszöb                     | 0                              |
| Fizetés szállítónak                           | Nincs                             |

Ez a példa egy olyan lízing létrejöttét hozta létre, amelynek a következő beállításait találja az **Általános** és a **Fizetési ütemezés sorai** lapon.

**Általános fül**

| Mező                      | Érték            |
|----------------------------|------------------|
| Járulékos kamatláb | 5%               |
| Kezdési dátum          | 2020.01.01.         |
| Lízingcsoport                | Épületek        |
| Szállító                     | 1001             |
| Az eszköz valós értéke    | 245,000          |
| Eszköz hasznos élettartama          | 120              |
| Annuitás típusa               | Szokásos annuitás |
| Összetételi intervallum       | Havi          |

**Kifizetési lista sorai fül**

| Mező             | Érték      |
|-------------------|------------|
| Kezdés dátuma        | 2020.01.01.   |
| Időszak intervalluma   | Hónap     |
| Időszakok           | 24         |
| Befejezés          | 2020.12.31. |
| Fizetés gyakorisága | Havi    |
| Fizetés összege    | 1000      |

Ha ezt a lízinget két keretrendszerben szeretné elszámolni, akkor egy aktuális feladási réteget és egy egyéni feladási réteget kell használnia. A következő táblázat egy példát mutat be az összes naplóbejegyzésről, amely szükséges az összes jelentési standard alatt lévő pénzügyek helyes megjelenítéséhez. Ezt követően a lízing első hónapjához tartozó valamennyi naplóbejegyzés részletes leírása jelenik meg.

<table>
<thead>
<tr>
<th rowspan='3'>Számlaszám</th>
<th rowspan='3'>Leírás</th>
<th colspan='3'>Kötelező könyv (jelenlegi réteg)</th>
<th rowspan='3'>Aktuális réteg összesen</th>
<th>Sztornírozási könyv (egyéni réteg)</th>
<th colspan='4'>IFRS 16 könyv (egyéni réteg)</th>
<th rowspan='3'>Aktuális réteg + egyéni réteg összesen</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
<th>JE-130</th>
<th>JE-140</th>
<th>JE-150</th>
<th>JE-160</th>
<th>JE-170</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Lízingköltség</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
<td>-1 000,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>2</td>
<td>Bankköltség</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Áfaköltség</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Elszámolási számla</td>
<td>-1 000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
<td>1,000.00</td>
<td></td>
<td>-1 000,00</td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Kötelezettségek</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>ROU-eszköz</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>22,794.00</td>
<td></td>
<td></td>
<td></td>
<td>22,793.90</td>
</tr>
<tr>
<td>7</td>
<td>Pénzügyi lízingkötelezettség</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>-22.794,00</td>
<td>1,000.00</td>
<td>-94,97</td>
<td></td>
<td>-21.888,87</td>
</tr>
<tr>
<td>8</td>
<td>Kamatköltség</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td>94.97</td>
<td></td>
<td>94.97</td>
</tr>
<tr>
<td>9</td>
<td>Készpénz</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Értékcsökkenés költsége</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>949.75</td>
<td>949.75</td>
</tr>
<tr>
<td>11</td>
<td>Halmozott értékcsökkenés</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-949,75</td>
<td>-949,75</td>
</tr>
</tbody>
</table>

Az előző táblában látható, hogy három könyv szükséges a kötelező jelentéshez és az IFRS-jelentéshez.

- A kötelező könyv rögzíti a lízingdíjfizetés az aktuális rétegben a pénzforgalmi elszámolás szabályainak megfelelően.
- A kötelező sztornírozási könyv a kötelező napló bejegyzéseit visszavonja.
- Az IFRS 16 könyv létrehozza az IFRS 16 alapján szükséges naplóbejegyzéseket.

A lízinget csak egy alkalommal kell megadnia. Ezután megnyithatja a **Könyvek** lapot, amelyen megtekintheti a lízinghez társított könyveket.

> [!NOTE]
> Amikor létrehozza a könyveket, mindháromnak ugyanahhoz a lízingrekordhoz kell tartoznia.

Az első naplóbejegyzés a kötelező könyv szerinti lízingköltséget rögzíti. A kifizetéseket egy kötegben is létrehozhatja, vagy kiválaszthatja a kötelező könyv szerinti kifizetési ütemezéseket.

Ebben a példában a következő naplóbejegyzés készül a kötelező könyveléshez a fizetési ütemezésből.

### <a name="lease-payment--1312020--je-100"></a>Lízingdíjfizetés – 2020.01.31. – JE 100

| Számla típusa | Számlaszám | Réteg   | Számla leírása | Tartozik    | Követel   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 1              | Aktuális | Lízingköltség       | 1,000.00 |          |
| Ledger       | 4              | Aktuális | Elszámolási számla    |          | 1,000.00 |

A Kötelezettségekkel kapcsolatos adminisztrátorok a standard Dynamics 365 funkciót használják egy számla létrehozásához, amely a lízing külső Eszközlízingje esetén fizetendő. Ha viszont a **Lízingköltség** lehetőséget nem tartozási számlaként választja, akkor a Kötelezettségek adminisztrátora egy elszámolási számlát választ a következő bejegyzés létrehozásához.

### <a name="ap-process--1312020--je-110"></a>AP-folyamat – 2020.01.31. – JE 110

| Számla típusa | Számlaszám | Réteg   | Számla leírása | Tartozik    | Követel   |
|--------------|----------------|---------|---------------------|----------|----------|
| Ledger       | 4              | Aktuális | Elszámolási számla    | 1,000.00 |          |
| Ledger       | 2              | Aktuális | Bankköltség            | 3.00     |          |
| Ledger       | 3              | Aktuális | Áfaköltség         | 5.00     |          |
| Szállító       | 5              | Aktuális | Kötelezettségek    |          | 1,008.00 |

Amikor a kimutatást kiállítják a szállítónak, a szokásos fizetési folyamatot követik. A folyamat során a következő naplóbejegyzés jön létre.

### <a name="cash-payment--1312020--je-120"></a>Készpénzes fizetés – 2020.01.31. – JE 120

| Számla típusa | Számlaszám | Réteg   | Számla leírása | Tartozik    | Követel   |
|--------------|----------------|---------|---------------------|----------|----------|
| Szállító       | 5              | Aktuális | Kötelezettségek    | 1,008.00 |          |
| Bank         | 9              | Aktuális | Készpénz                |          | 1,008.00 |

Ezen a ponton már teljes mértékben elszámolta ezt a lízinget a kötelező jelentési követelmények között, és a jelenlegi réteg használatával generálhat egy főkönyvi kivonatot. A rendszer a következő számú főkönyvi kivonatot küld vissza.

<table>
<thead>
<tr>
<th rowspan='3'>Számlaszám</th>
<th rowspan='3'>Leírás</th>
<th colspan='3'>Kötelező könyv (jelenlegi réteg)</th>
<th rowspan='3'>Aktuális réteg összesen</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Lízingköltség</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
</tr>
<tr>
<td>2</td>
<td>Bankköltség</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Áfaköltség</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Elszámolási számla</td>
<td>-1 000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Kötelezettségek</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>ROU-eszköz</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>7</td>
<td>Pénzügyi lízingkötelezettség</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>8</td>
<td>Kamatköltség</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>9</td>
<td>Készpénz</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Értékcsökkenés költsége</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>11</td>
<td>Halmozott értékcsökkenés</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
</tbody>
</table>

Ha azt szeretné, hogy az IFRS 16 számokkal ugyanaz a főkönyvi kivonat fusson, akkor a kötelező könyvelési napló bejegyzéseit sztornírozni kell, és az IFRS 16 napló bejegyzéseit fel kell adni. A kötelező naplóbejegyzések sztornírozásához ez a példa olyan kötelező sztornírozási könyvet tartalmaz, amelynek ugyanaz a beállítása, mint a kötelező könyvé, de ellenkező feladási profilú. Például a kötelező könyv *megterhelt* egy lízingköltség-számlát, de a sztornírozási könyv *jóváírja* ezt a számlát. Ezek a kapcsolatok könnyen meghatározhatók az **Eszközlízing paraméterek** oldalon (**Eszközlízing paraméterek \> Beállítás \> Eszközlízing paraméterek**) található Eszközlízing feladási számlákban.

Ha a sztornírozási könyvhöz a kötelező könyvhöz használt eljárást használja, a következő naplóbejegyzés jelenik meg. A különbség az, hogy a sztornírozási könyv a sztornírozási bejegyzéseket a kötelező könyvből állítja be. A sztornírozási bejegyzések az egyéni rétegre is vonatkoznak. Ha az aktuális rétegen fut egy főkönyvi kivonat, a sztornírozó naplóbejegyzések nem szerepelnek.

### <a name="lease-payment--1312020--je-130"></a>Lízingdíjfizetés – 2020.01.31. – JE 130

| Számla típusa | Számlaszám | Réteg  | Számla leírása | Tartozik    | Követel   |
|--------------|----------------|--------|---------------------|----------|----------|
| Ledger       | 4              | Egyéni | Elszámolási számla    | 1,000.00 |          |
| Ledger       | 1              | Egyéni | Lízingköltség       |          | 1,000.00 |

Most, hogy megszüntette a kötelező naplóbejegyzéseket, az IFRS 16 az IFRS 16-ban lefoglalja az összes naplóbejegyzést. Ezek a bejegyzések tartalmazzák a ROU-eszköz és a kötelezettség kezdeti megjelenítését, valamint a kamat- és értékcsökkenési nyilvántartást.

### <a name="initial-recognition--112020--je-140"></a>Kezdeti elszámolás – 2020.01.01. – JE 140

| Számla típusa | Számlaszám | Réteg  | Számla leírása      | Tartozik     | Követel    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| Ledger       | 6              | Egyéni | ROU-eszköz                | 22,793.90 |           |
| Ledger       | 7              | Egyéni | Pénzügyi lízingkötelezettség |           | 22,793.90 |

A lízingdíjfizetés a többi lízingdíjfizetéshez hasonlóan kerül feladása. A kiegyenlítési számla használatának oka annak biztosítása, hogy a készpénz csak egyszer kerüljön jóváírásra.

### <a name="lease-payment--1312020--je-150"></a>Lízingdíjfizetés – 2020.01.31. – JE 150

| Számla típusa | Számlaszám | Réteg  | Számla leírása      | Tartozik    | Követel   |
|--------------|----------------|--------|--------------------------|----------|----------|
| Ledger       | 7              | Egyéni | Pénzügyi lízingkötelezettség | 1,000.00 |          |
| Ledger       | 4              | Egyéni | Elszámolási számla         |          | 1,000.00 |

A kamatráfordítási naplóbejegyzés a kötelezettség amortizációs ütemezéséből jön létre.

### <a name="interest-expense--1312020--je-160"></a>Kamatköltség – 2020.01.31. – JE 160

| Számla típusa | Számlaszám | Réteg  | Számla leírása      | Tartozik | Követel |
|--------------|----------------|--------|--------------------------|-------|--------|
| Ledger       | 8              | Egyéni | Kamatköltség         | 94.97 |        |
| Ledger       | 7              | Egyéni | Pénzügyi lízingkötelezettség |       | 94.97  |

Az értékcsökkenési költség-naplóbejegyzés az eszközértékcsökkenési ütemezéséből jön létre.

### <a name="depreciation-expense--1312020--je-170"></a>Értékcsökkenés költsége – 2020.01.31. – JE 170

| Számla típusa | Számlaszám | Réteg  | Számla leírása      | Tartozik  | Követel |
|--------------|----------------|--------|--------------------------|--------|--------|
| Ledger       | 10             | Egyéni | Értékcsökkenés költsége     | 949.75 |        |
| Ledger       | 11             | Egyéni | Halmozott értékcsökkenés |        | 949.75 |

Miután az összes naplóbejegyzést létrehozta és feladta, akkor a következő „1. egyéni réteg” értékeket fogja látni. Ne feledje, hogy az utolsó oszlop tartalmazza a banki díjat, az áfaköltséget (ÁFA) és az előző rétegből származó készpénz csökkentését, de nem tartalmazza a kötelező jelentési naplóbejegyzéseket. Ezért valódi kettős jelentéskészítési képességeket érhet el. Ezen a ponton a vállalatnak csak futtatnia kell a főkönyvi kivonatot, és kombinálnia kell az aktuális réteget és az egyéni réteget az IFRS főkönyvi kivonat létrehozásához.

| Számlaszám | Leírás              | Kötelező könyv\-Aktuális réteg\-JE\-100\-Dr \(Cr\) | Kötelező könyv\-Aktuális réteg\-JE\-110\-Dr \(Cr\) | Kötelező könyv\-Aktuális réteg\-JE\-120\-Dr \(Cr\) | Aktuális réteg \- Összesen | - | Sztornírozási könyv\-Egyéni réteg\-JE\-130\-Dr \(Cr\) | IFRS 16 könyv\-Egyéni réteg\-JE\-140\-Dr \(Cr\) | IFRS 16 könyv\-Egyéni réteg\-JE\-150\-Dr \(Cr\) | IFRS 16 könyv\-Egyéni réteg\-JE\-160\-Dr \(Cr\) | IFRS 16 könyv\-Egyéni réteg\-JE\-170\-Dr \(Cr\) | Egyéni réteg \+ Egyéni réteg \- Összesen |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| 1          | Lízingköltség            | 1,000\.00                                         |                                                   |                                                   | 1,000\.00               |   | \-1.000.                                         |                                                |                                                |                                                |                                                | 0\.00                                   |
| 2          | Bankköltség                 |                                                   | 3\.00                                             |                                                   | 3\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 3\.00                                   |
| 3          | Áfaköltség              |                                                   | 5\.00                                             |                                                   | 5\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 5\.00                                   |
| 4          | Elszámolási számla         | \-1.000\.00                                       | 1,000\.00                                         |                                                   | 0\.00                   |   | 1000                                           |                                                | \-1.000.                                        |                                                |                                                | 0\.00                                   |
| 5          | Kötelezettségek         |                                                   | \-1.008\.00                                       | 1,008\.00                                         | 0\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 0\.00                                   |
| 6          | ROU-eszköz                |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | 22,794                                         |                                                |                                                |                                                | 22,793\.90                              |
| 7          | Pénzügyi lízingkötelezettség |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | \-22.794.                                       | 1000                                          | \-94\.97                                       |                                                | \-21.888\.87                            |
| 8          | Kamatköltség         |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                | 94\.97                                         |                                                | 94\.97                                  |
| 9          | Készpénz                     |                                                   |                                                   | \-1.008\.00                                       | \-1.008\.00             |   |                                                 |                                                |                                                |                                                |                                                | \-1.008\.00                             |
| 10         | Értékcsökkenés költsége     |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | 949\.75                                        | 949\.75                                 |
| 11         | Halmozott értékcsökkenés |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | \-949\.75                                      | \-949\.75                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]