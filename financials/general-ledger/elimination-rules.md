---
title: "Eltávolítási szabályok"
description: "Ez a témakör információt eltávolítási szabályok és eltávolítások jelentések beállítási lehetőségeit."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: db4b05bc55d735513d7580ca5908a1e84eb760c6
ms.openlocfilehash: 152b63fdfc78b3c4e79b93340d18c5cf69257024
ms.lasthandoff: 03/31/2017


---

# <a name="elimination-rules"></a>Eltávolítási szabályok

Ez a témakör információt eltávolítási szabályok és eltávolítások jelentések beállítási lehetőségeit.

Az eltávolítási tranzakciókra akkor van szükség, amikor egy konszolidált pénzügyi jelentést alkalmazó anyavállalat üzleti kapcsolatban van egy vagy több leányvállalatával. A konszolidált pénzügyi kiadásoknak csak olyan tranzakciókat kell tartalmazniuk, amelyek a konszolidált szervezet és egyéb, a szervezeten kívüli entitások között jönnek létre. Ezért szervezethez tartozó jogi személyek közötti tranzakciók kell eltávolítani, vagy megszűnik, a főkönyvből, nem jelennek meg a pénzügyi beszámolókat. Több mód létezik, hogy jelentést tegyünk az eltávolításokról:

-   Az eltávolítási szabály létrehozható és feldolgozható egy konszolidáló vagy eltávolító vállalatban.
-   A pénzügyi jelentés használható, hogy megmutassa az eltávolítások számláit és dimenziót az adott sorban vagy oszlopban.
-   Egy különálló jogi személy használható, hogy kézi tranzakció bejegyzéseket adjon föl az eltávolítások követéséhez.

Ez a téma azon eltávolítási szabályokra összpontosít, amelyek a konszolidáló vagy eltávolító vállalatban vannak feldolgozva. Annál a vállalatnál lehet felállítani eltávolítási szabályokat az eltávolítási tranzakciók létrehozására, amely az eltávolítások célvállalataként vagy eltávolítási vállalatként lett meghatározva. Ezt a célvállalatot eltávolítási jogi személynek is nevezik. Az eltávolítási naplók a konszolidáció folyamata során, vagy egy eltávolítási naplójavaslat felhasználásával hozhatók létre. Mielőtt eltávolítási szabályokat állítana fel, meg kell ismerkednie a következő fogalmakkal:

-   **Forrás jogi személy** – azon jogi személy, amelyben az eltávolítandó összegeket feladták.
-   **Cél jogi személy** – az a vállalat, amelybe az eltávolítási szabályok feladása történik.
-   **Eltávolítási jogi személy** – az a jogi személy, amely az eltávolítások cél jogi személyeként lett meghatározva.
-   **Konszolidációs jogi személy** – az a jogi személy, amelyet egy jogi személyek csoportjának pénzügyi eredményeinek jelentésére hoztak létre. A vállalatok pénzügyi adatai ebbe a vállalatba konszolidálódnak, majd a pénzügyi jelentés ezt a kombinált adatot felhasználva jön létre.

Az alábbi táblázat bemutatja azon típusú tranzakciókat, amelyeket lehet lehet eltávolítani.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tranzakció típusa</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Értékesítési rendelés bevitele és számlázása (központosított feldolgozás)</td>
<td>Ön egy terméket értékesít a vevőnek egy, az ön cégéhez tartozó másik jogi személy nevében.</td>
</tr>
<tr class="even">
<td>Értékesítési rendelés bevitele (több vállalat között/vállalaton belül) és számlázása</td>
<td>Ön termékeket értékesített a szervezetéhez tartozó jogi személyek között.</td>
</tr>
<tr class="odd">
<td>Beszerzési rendelések (központosított feldolgozás)</td>
<td>Ön készletet, fogyóeszközöket, szolgáltatásokat, tárgyi eszközöket és egyéb termékeket szerez be egy szállítótól egy, az ön szervezetéhez tartozó másik jogi személy nevében.</td>
</tr>
<tr class="even">
<td>Készletkezelés (vállalatközi/vállalaton belüli)</td>
<td><ul>
<li>Ön áthelyezi az egyik jogi személy készletét egy, az ön szervezetéhez tartozó másik jogi személy tárgyi eszközeinek körébe.</li>
<li>Ön áthelyezi az egyik jogi személy készletét egy, az ön szervezetéhez tartozó másik jogi személy készletébe.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Átmozgatás közbeni készletkövetés</td>
<td>Ön ugyanazon jogi személyhez tartozó, de eltérő helyeken fekvő raktárak között szállít át cikkeket.</td>
</tr>
<tr class="even">
<td>Kinnlevőségek központosított számlafeldolgozása</td>
<td>Ön számlát rögzít egy, az ön szervezetéhez tartozó másik jogi személy nevében.</td>
</tr>
<tr class="odd">
<td>Kinnlevőségek központosított kifizetés-feldolgozása</td>
<td>Ön számlát fizet ki egy, az ön szervezetéhez tartozó másik jogi személy nevében.</td>
</tr>
<tr class="even">
<td>Pénzgazdálkodás és pénzkészlet (központosított feldolgozás)</td>
<td><ul>
<li>Ön adókifizetések, adó-visszatérítések, kamatterhek, kölcsönök, kedvezmények, osztalékkifizetések és előre kifizetett jogdíjak vagy jutalékok feldolgozását végzi.</li>
<li>Ön költséget fizet ki egy, az ön szervezetéhez tartozó másik jogi személy nevében. A számla bekerül a célvállalatként szereplő cél jogi személy könyveibe, és önnek keresztelszámolást kell lefolytatnia a jogi személyek között. Ha például egy vállalat kifizeti egy másik vállalat alkalmazottjának költségjelentését. Ebben az esetben az alkalmazott költségjelentése egy másik vállalathoz tartozó költségeket tartalmaz.</li>
<li>Készpénzt utal át az ön szervezetéhez tartozó egyik jogi személytől a másikhoz.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kinnlevőségek (központosított feldolgozás)</td>
<td>Készpénzt vesz át egy másik vállalat vevői számlájáért és befizeti annak a vállalatnak a bankszámlájára.</td>
</tr>
<tr class="even">
<td>Bérlista (központosított feldolgozás, vállalatközi/vállalaton belüli)</td>
<td><ul>
<li>Kifizeti egy másik jogi személy bérlistáját. Például egy jogi személy kifizeti a saját alkalmazottainak a bérlistáját, de kifizetteti azt a munkát, amelyet az alkalmazott egy másik vállalat számára végzett az adott fizetési időszakban. Vagy ha egy alkalmazott fél munkaidőben A vállalat, a másik felében pedig B vállalat számára dolgozott, és a juttatásokat mindenki fizeti. Ebben az esetben az alkalmazott fizetése magában foglalja minkét jogi személytől származó fizetést. Nem csak a bérek feladása történik meg, de az adók, a juttatások, a levonások és a bérkönyvelések feladása is.</li>
<li>Ön munkaerőt helyez át egyik részlegről vagy osztályról a másikra</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tárgyi eszközök (vállalatközi/vállalaton belüli)</td>
<td>Ön tárgyi eszközöket helyez át egy másik jogi személy tárgyi eszközei körébe vagy a készletébe.</td>
</tr>
<tr class="even">
<td>Felosztások (vállalatközi/vállalaton belüli)</td>
<td>Ön vállalati felosztások feldolgozását végzi. Vállalati felosztások alatt a származtató modultól függetlenül bármelyik felosztott számlával kapcsolatos tevékenységek értendők.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Példa
Az ön vállalata, A jogi személy, eszközöket értékesített egy, az ön szervezetéhez tartozó másik jogi személynek, B jogi személy. A következő példa bemutatja, hogyan lehet a két jogi személy között lezajló tranzakciókat eltávolítani:

-   A jogi személy elad egy 10,00 egységet érő eszközt B jogi személynek 10,00 egységért.
-   A jogi személy elad egy 10,00 egységet érő eszközt B jogi személynek 10,00 egységért, plusz felszámolja a 2,00 egységnyi tényleges szállítási költséget.
-   A jogi személy elad egy 10,00 egységet érő eszközt B jogi személynek 15,00 egységért, és árrést realizál az eladáson.
-   A jogi személy elad egy 10,00 egységet érő eszközt B jogi személynek 15,00 egységért, és fele árrést realizál az eladáson. B jogi személy realizálja a másik felét az eladási árrésének. Emiatt a bevétel felosztásra kerül. A felosztott árbevétel ösztönzést jelent arra nézvést, hogy a szervezeten belüli más jogi személytől rendeljenek ahelyett, hogy egy külső céget bíznának meg.

Mindezen tranzakciók vállalatközi tranzakciók feladásait eredményezik a megfelelő számlákra. Ezen felül a tranzakciók tartalmazhatják a haszonkulcsokat és veszteségkulcsokat abban az esetben, ha a vállalatközi eladások összege és az eladott áruk beszerzési értéke nem egyenlő.

## <a name="set-up-elimination-rules"></a>Eltávolítási szabályok beállítása
Dynamics 365 műveletek eltávolítási szabályok beállításakor létrehozott pénzügyi dimenzió megszüntetése céljából kifejezetten ajánlott. A legtöbb ügyfél nevű kereskedelmi Partner, vagy valami hasonló. Ha úgy dönt, hogy nem használja a pénzügyi dimenzió, akkor ellenőrizze, hogy rendelkezik, amelyek csak a vállalatközi tranzakciók az fő számlák. 

A telepítő kiküszöbölésekhez a konszolidáció modul Beállítás területén található. Miután megadta a szabály leírását, ki kell választani a vállalat, amely az eltávolítási napló könyveli. El kell végezni egy olyan társaság, amelynek **pénzügyi eltávolítási folyamatokhoz** a jogi személy beállítás. 

Az eltávolítási szabály hatályba lép, és amikor lejárt, is beállíthat egy dátumot, ha szükséges. Meg kell **aktív** a **Igen** Ha azt szeretné, hogy a javaslat eltávolítási folyamat. Válassza ki a napló nevét, amelyen egy adott típusú **Eltávolítás**.

Után az alapvető, a tényleges feldolgozási szabályok gombra kattintva meghatározhatja **vonalak**. Két opció kiküszöbölésekhez, kiküszöbölve a forgalom összegét vagy rögzített összeg meghatározása. 

Válassza ki a forrásfiókéval. Használhatja a csillag (\*) helyettesítő karakterként. Például 1\* jelöljük ki, minden kezdődő számlákat 1 elosztására vonatkozó adatok forrásaként. 

A forrásfiókok kiválasztása után a **figyelembe specifikáció** a a célvállalat használt fiókot határozza meg. Válassza ki **forrás** meghatározott ugyanazt a fő fiókot használni kívánt a **forrás** számla. Ha **felhasználó által definiált**, majd meg kell adnia a Célszámla. 

A dimenzió meghatározása azonos módon működik. Ha **forrás**, ugyanezeket a dimenziókat a célvállalat, mint a forrás vállalat használja. Ha **felhasználó által definiált**, szüksége lesz a célvállalat a Dimenziók parancsra kattintva adható meg a **Cél dimenziókat** menüpont. 

Válassza ki a forrás dimenziói és a pénzügyi dimenziók és az újak forrásként használt értékek.

## <a name="process-elimination-transactions"></a>Eltávolítási tranzakciók feldolgozása
Kétféleképpen eltávolítási tranzakciók feldolgozásához vagy az eltávolítási napló létrehozása és futtatása a kármegszüntetési javaslati online összesítés során. Ez a szakasz a napló létrehozása és az eltávolítási folyamat fut összpontosít. 

Egy vállalat határozható meg, mint egy eltávolítási vállalatnak, jelölje ki a **eltávolítási napló** a konszolidáció modulban. Miután kiválasztotta a napló nevét, kattintson a **vonalak**. Kiválasztásával futtathatja a javaslat a **javaslatok** menü, és válassza a **eltávolítási javaslat**.

Jelölje ki az adatforrást a konszolidált vállalat, és válassza ki a feldolgozni kívánt szabályt. Adja meg az eltávolítási összegek esetében a keresés megkezdéséhez kezdő dátum és befejező dátum eltávolítási összegek Keresés vége. A **Főkönyvi könyvelési dátum** a mezőben az a dátum, a napló főkönyvbe való feladásához használatos. Amikor rákattint a **OK**, tekintse át az összegeket, és könyvelje a naplót.


