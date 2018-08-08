---
title: "Járulékos költség számítása"
description: "Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 549e9b4b073a4e93dd3a1dd52dd6f43e7420a31b
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="overhead-calculation"></a>Járulékos költség számítása

[!include [banner](../includes/banner.md)]

Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.

<a name="term-definition"></a>A kifejezés meghatározása
---------------

A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak. A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára. Az alábbiakban néhány példa látható a járulékos költségekre:

-   Bérlet
-   Villamos energia
-   Adminisztratív fizetések

## <a name="overhead-calculation-overview"></a>Járulékos költség áttekintése
A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben. A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek. A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban. Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak. A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával. A verzió egyedi azonosítója a következő elemekből áll:

-   Verziótípus
-   Dátum és idő
-   Költségkönyvelési főkönyv
-   Pénzügyi év
-   Pénzügyi időszak

A járulékos költség kiszámítása a verziótól függetlenül fut. Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót. A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon. Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel. Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait. Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre. Ezáltal mindig teljes a nyomon követhetőség. 

[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>Az elektromos áram járulékos költségének kiszámítása és felosztása
A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják. Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél. A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül. A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia. A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.

<table>
<thead>
<tr>
<th>Könyvelési dátum</th>
<th colspan="2">Költséghely</th>
<th colspan="2">Fő számla</th>
<th>Összeg a könyvelési pénznemben</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017. január 3.</td>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása

Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél. A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.

#### <a name="define-the-cost-behavior-rule"></a>A költségviselkedési szabály meghatározása

Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú. A villanyszámlák gyakran megfelelnek ennek a meghatározásnak. Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet. Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:

-   Rögzített összeg 1,000.00
    -   0 &lt;= 1,000.00 = Rögzített
    -   1000,01 &lt; N = Változó

##### <a name="journal"></a>Napló

<table>
<thead>
<tr>
<th>Napló</th>
<th>Napló típusa</th>
<th colspan="3">Pénzügyi naptári időszak</th>
<th>Verzió</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>Költségműködés számítás napló</td>
<td>Pénzügyi</td>
<td>2017</td>
<td>1. időszak</td>
<td>Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)

<table>
<thead>
<tr>
<th>Könyvelési dátum</th>
<th colspan="2">Költségobjektum</th>
<th colspan="2">Költségösszetevő</th>
<th>Költség működése</th>
<th>Összeg</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017. január 3.</td>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Nem besorolt</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Költségbejegyzések

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th colspan="2">Költségösszetevő</th>
<th>Költség működése</th>
<th>Összeg</th>
<th>Könyvelési dátum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Nem besorolt</td>
<td>10,000.00</td>
<td>2017. január 3.</td>
</tr>
<tr>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Nem besorolt</td>
<td>-10,000.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>1000,00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>9,000.00</td>
<td>2017. január 31.</td>
</tr>
</tbody>
</table>

A költségműködéssel kapcsolatos részletes tudnivalókat lásd a Költségműködési irányelvekben. Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)

### <a name="step-2-process-the-cost-distribution-calculation"></a>2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása

A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával. A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.

#### <a name="define-the-cost-distribution-rule"></a>A költségelosztási szabály meghatározása

Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják. A költségkönyvelésben ez a módszer nem elég részletes. A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között. A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh). Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást. Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Kwh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>1000</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>6,000</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>0</td>
</tr>
</tbody>
</table>

Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Nagyság</th>
<th>Felosztási tényező</th>
<th>Összeg</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>1000</td>
<td>(1,000 ÷ 7,000) × 9,000.00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>6,000</td>
<td>(6,000 ÷ 7,000) × 9,000.00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>0</td>
<td>(0 ÷ 7,000) × 9,000.00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak. Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: ((Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Receptúra</th>
<th>Nagyság</th>
<th>Felosztási tényező</th>
<th>Összeg</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>(1,000 &gt; 0.00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1,000.00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>(6,000 &gt; 0.00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1,000.00</td>
<td>500.00</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>(0 &gt; 0.00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1,000.00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Napló

<table>
<thead>
<tr>
<th>Napló</th>
<th>Napló típusa</th>
<th colspan="3">Pénzügyi naptári időszak</th>
<th>Verzió</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>Költségfelosztás számítási naplója</td>
<td>Pénzügyi</td>
<td>2017</td>
<td>1. időszak</td>
<td>Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)

<table>
<thead>
<tr>
<th>Könyvelési dátum</th>
<th colspan="2">Költségobjektum</th>
<th colspan="2">Költségösszetevő</th>
<th>Költség működése</th>
<th>Összeg</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017. január 31.</td>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>1000,00</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>9,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Költségbejegyzések

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th colspan="2">Költségösszetevő</th>
<th>Költség működése</th>
<th>Összeg</th>
<th>Könyvelési dátum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>-1000,00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>500.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>500.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC099</td>
<td>Alapértelmezett költséghely</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>-9,000.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>1,285.71</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>7,714.29</td>
<td>2017. január 31.</td>
</tr>
</tbody>
</table>

Ha részletes információt szeretne a költségfelosztásról és a felosztási alapokról, lásd a Költségfelosztási irányelvet és a felosztási alapokat. Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)

### <a name="step-3-process-the-overhead-rate-calculation"></a>3. lépés: A járulékos költégek kiszámításának folyamata

A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum. A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul. 

#### <a name="define-the-overhead-rate"></a>A járulékos költség meghatározása

A CC001 HR költségobjektum számos belső projekthez hozzájárul. A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>óra</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>1. projekt</td>
<td>3</td>
</tr>
<tr>
<td>Proj 2</td>
<td>2. projekt</td>
<td>1</td>
</tr>
</tbody>
</table>

Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Költségösszetevő</th>
<th>Költség működése</th>
<th>Egységek</th>
<th>Árfolyam</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Változó költség</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Nagyság</th>
<th>Költségösszetevő</th>
<th>Felosztási tényező</th>
<th>Összeg</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj 1</td>
<td>1. projekt</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10.00</td>
<td>30.00</td>
</tr>
<tr>
<td>Proj 2</td>
<td>2. projekt</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10.00</td>
<td>10.00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Napló

<table>
<thead>
<tr>
<th>Napló</th>
<th>Napló típusa</th>
<th colspan="3">Pénzügyi naptári időszak</th>
<th>Verzió</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>Járulékos díj számítás napló</td>
<td>Pénzügyi</td>
<td>2017</td>
<td>1. időszak</td>
<td>Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)

<table>
<thead>
<tr>
<th>Könyvelési dátum</th>
<th colspan="2">Költségobjektum</th>
<th>Nagyság</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017. január 31.</td>
<td>Proj 1</td>
<td>Belső proj 1</td>
<td>3,00</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>Proj 2</td>
<td>Belső proj 2</td>
<td>1.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Költségbejegyzések

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th colspan="2">Költségösszetevő</th>
<th>Költség működése</th>
<th>Összeg</th>
<th>Könyvelési dátum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>-30.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Proj 1</td>
<td>Belső proj 1</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>30.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>-10,00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Proj 2</td>
<td>Belső proj 2</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>10.00</td>
<td>2017. január 31.</td>
</tr>
</tbody>
</table>

A járulékos díj irányelvére vonatkozó részletes információkért lásd: A járulékos díj irányelvei és Felosztási bázisok. Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)

### <a name="step-4-process-the-cost-allocation-calculation"></a>4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása

A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával. A Finance and Operations a reciprokális felosztási módszert támogatja. A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek. A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét. A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik. A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat. A felosztás sorrendjét a költség ellenőrzőegysége vezérli. 

[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)

#### <a name="define-the-cost-allocation"></a>A költségfelosztás meghatározása

Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok. A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul. A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>HR-szolgáltatások</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>10</td>
</tr>
</tbody>
</table>

A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul. A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Pénzügyi szolgáltatások</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>35</td>
</tr>
</tbody>
</table>

A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul. A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Összeszerelési szolgáltatások (óra)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>60</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>20</td>
</tr>
</tbody>
</table>

A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul. A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Csomagolóanyag-szolgáltatások (óra)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>80</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>15.</td>
</tr>
</tbody>
</table>

**Megjegyzés:** A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak. A statisztikai mérési szolgáltatókról szóló bővebb információkért lásd: Statisztikai mérték szolgáltatójának sablonjai. (Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.) Az alábbi táblázat azt az eredményt mutatja, amikor a HR-szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Nagyság</th>
<th>Felosztási tényező</th>
<th>Összeg</th>
<th>Költség működése</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>35</td>
<td>(35 ÷ 100) × 500.00</td>
<td>175.00</td>
<td>Fix költség</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>55</td>
<td>(55 ÷ 100) × 500.00</td>
<td>275.00</td>
<td>Fix költség</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>10</td>
<td>(10 ÷ 100) × 500.00</td>
<td>50,00</td>
<td>Fix költség</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>35</td>
<td>(35 ÷ 100) × 1,245.71</td>
<td>436.00</td>
<td>Változó költség</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>55</td>
<td>(55 ÷ 100) × 1,245.71</td>
<td>685.14</td>
<td>Változó költség</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>10</td>
<td>(10 ÷ 100) × 1,245.71</td>
<td>124.57</td>
<td>Változó költség</td>
</tr>
</tbody>
</table>

Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Nagyság</th>
<th>Felosztási tényező</th>
<th>Összeg</th>
<th>Költség működése</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>65</td>
<td>(65 ÷ 100) × (500.00 + 175.00)</td>
<td>438.75</td>
<td>Fix költség</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>35</td>
<td>(35 ÷ 100) × (500.00 + 175.00)</td>
<td>236.25</td>
<td>Fix költség</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>65</td>
<td>(65 ÷ 100) × (7,714.29 + 436.00)</td>
<td>5,297.69</td>
<td>Változó költség</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>35</td>
<td>(35 ÷ 100) × (7,714.29 + 436.00)</td>
<td>2,852.60</td>
<td>Változó költség</td>
</tr>
</tbody>
</table>

Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Nagyság</th>
<th>Felosztási tényező</th>
<th>Összeg</th>
<th>Költség működése</th>
</tr>
</thead>
<tbody>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>60</td>
<td>(60 ÷ 80) × (275.00 + 438.75)</td>
<td>535.31</td>
<td>Fix költség</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>20</td>
<td>(20 ÷ 80) × (275.00 + 438.75)</td>
<td>178.44</td>
<td>Fix költség</td>
</tr>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>60</td>
<td>(60 ÷ 80) × (5,297.69 + 685.14)</td>
<td>4,487.12</td>
<td>Változó költség</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>20</td>
<td>(20 ÷ 80) × (5,297.69 + 685.14)</td>
<td>1,495.71</td>
<td>Változó költség</td>
</tr>
</tbody>
</table>

Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th>Nagyság</th>
<th>Felosztási tényező</th>
<th>Összeg</th>
<th>Költség működése</th>
</tr>
</thead>
<tbody>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>80</td>
<td>(80 ÷ 95) × (50.00 + 236.25)</td>
<td>241.05</td>
<td>Fix költség</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>15.</td>
<td>(15 ÷ 95) × (50.00 + 236.25)</td>
<td>45.20</td>
<td>Fix költség</td>
</tr>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>80</td>
<td>(80 ÷ 95) × (2,852.60 + 124.57)</td>
<td>2,507.09</td>
<td>Változó költség</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>15.</td>
<td>(15 ÷ 95) × (2,852.60 + 124.57)</td>
<td>470.08</td>
<td>Változó költség</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)

<table>
<thead>
<tr>
<th>Napló</th>
<th>Napló típusa</th>
<th colspan="3">Pénzügyi naptári időszak</th>
<th>Verzió</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>Költségfelosztási napló</td>
<td>Pénzügyi</td>
<td>2017</td>
<td>1. időszak</td>
<td>Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>Naplósorok

<table>
<thead>
<tr>
<th>Könyvelési dátum</th>
<th colspan="2">Költségobjektum</th>
<th colspan="2">Költségösszetevő</th>
<th>Költség működése</th>
<th>Összeg</th>
</tr>
</thead>
<tbody>
<tr>
<td>2017. január 31.</td>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>500.00</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>1,245.71</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>675.00</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>8,150.29</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>713.75</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>5,982.83</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC003</td>
<td>Csomagolás</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>286.25</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>CC003</td>
<td>Csomagolás</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>2,977.17</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>Term. 1</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>776.36</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>Term. 1</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>6,994.21</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>Term. 2</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>223.64</td>
</tr>
<tr>
<td>2017. január 31.</td>
<td>Term. 2</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Költségbejegyzések

<table>
<thead>
<tr>
<th colspan="2">Költségobjektum</th>
<th colspan="2">Költségösszetevő</th>
<th>Költség működése</th>
<th>Összeg</th>
<th>Könyvelési dátum</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>-500,00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>175.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>275.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>50,00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC001</td>
<td>HR</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>-1,245.71</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>436.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>685.14</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>124.57</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>-675.00</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>438.75</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>236.25</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC002</td>
<td>Pénzügy</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>-8,150.29</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>5,297.69</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC004</td>
<td>Csomagolás</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>2,852.60</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>-713.75</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>535.31</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>178.44</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>-5,982.83</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>4,487.12</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>1,495.71</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>-286.25</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term 1</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>241.05</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Fix költség</td>
<td>45.20</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>CC003</td>
<td>Szerelvény</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>-2,977.17</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term. 1</td>
<td>1. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>2,507.09</td>
<td>2017. január 31.</td>
</tr>
<tr>
<td>Term. 2</td>
<td>2. termék</td>
<td>10001</td>
<td>Villamos energia</td>
<td>Változó költség</td>
<td>470.08</td>
<td>2017. január 31.</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>Következtetés
A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz. Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani. A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján. Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.

<table>
<thead>
<tr>
<th colspan="2" rowspan="2">Költségösszetevő</th>
<th colspan="9">Költségobjektum</th>
<th rowspan="2">Összesen</th>
</tr>
<tr>
<th>CC099</th>
<th>CC001</th>
<th>CC002</th>
<th>CC003</th>
<th>CC004</th>
<th>Proj 1</th>
<th>Proj 2</th>
<th>Term. 1</th>
<th>Term. 2</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">10001 Villamos energia</td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><strong>30,00</strong></td>
<td style="text-align: right;"><strong>10,00</strong></td>
<td style="text-align: right;"><strong>7.770,57</strong></td>
<td style="text-align: right;"><strong>2.189,43</strong></td>
<td style="text-align: right;"><strong>10.000,00</strong></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;">Nem besorolt</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Fix költség</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;">776.36</td>
<td style="text-align: right;">223.64</td>
<td style="text-align: right;"><strong>1.000,00</strong></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Változó költség</td>
<td style="text-align: right;">000</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">30.00</td>
<td style="text-align: right;">1000</td>
<td style="text-align: right;">6,994.21</td>
<td style="text-align: right;">1,965.79</td>
<td style="text-align: right;"><strong>9.000,00</strong></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez. Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva. Más szóval a legalsó szintű költségobjektumok viselik a költséget. Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását. Részletesebb tájékoztatás: Költségösszesítési irányelv. Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)




