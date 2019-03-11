---
title: Eltávolítási szabályok
description: Ez a témakör az eltávolítási szabályokról és a különböző lehetőségekről az eltávolításokról szóló jelentésekkel kapcsolatban szolgáltat információt.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0736d63c9a582948d197dc267f9941cbbd3e3c6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "333093"
---
# <a name="elimination-rules"></a>Eltávolítási szabályok

[!include [banner](../includes/banner.md)]

Ez a témakör az eltávolítási szabályokról és a különböző lehetőségekről az eltávolításokról szóló jelentésekkel kapcsolatban szolgáltat információt.

Az eltávolítási tranzakciókra akkor van szükség, amikor egy konszolidált pénzügyi jelentést alkalmazó anyavállalat üzleti kapcsolatban van egy vagy több leányvállalatával. A konszolidált pénzügyi kiadásoknak csak olyan tranzakciókat kell tartalmazniuk, amelyek a konszolidált szervezet és egyéb, a szervezeten kívüli entitások között jönnek létre. Emiatt azokat a jogi személyek közötti tranzakciókat, amelyek ugyanazon szervezet között jönnek létre, el kell távolítani a főkönyvből, hogy ne jelenjenek meg a pénzügyi jelentésekben. Több mód létezik, hogy jelentést tegyünk az eltávolításokról:

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
Eltávolítási szabályok beállításakor a Microsoft Dynamics 365 for Finance and Operations programban ajánlott létrehozni egy pénzügyi dimenziót kifejezetten eltávolítás céljából. A legtöbb ügyfél Kereskedelmi partnernek vagy valami hasonlónak nevezi. Ha úgy dönt, hogy nem használ pénzügyi dimenziót, úgy ügyeljen, hogy rendelkezzen olyan fő számlával, amely csak vállalatközi tranzakciókra vonatkozik. 

Az eltávolítási beállítások a Konszolidáció modul Beállítás területén találhatók. Miután megadta a szabály leírását, ki kell választania a vállalatot, amelyben az eltávolítási napló könyvelni fog. Ez olyan vállalat legyen, amelynél a **Pénzügyi eltávolítási folyamatokhoz** lehetőség ki van választva a jogi személy beállításainál. 

Szükség esetén az eltávolítási szabályhoz beállíthat egy hatálybalépési és egy lejárati dátumot. Az **Aktív** lehetőséget **Igen** értékre kell állítania, ha azt szeretné, hogy elérhető legyen az eltávolítási javaslati folyamat során. Válasszon egy olyan naplónevet, amelynek típusa **Eltávolítás**.

Az alapvető beállítások megadása után a tényleges feldolgozási szabályokat a **Sorok** gombra kattintva határozhatja meg. Két opció létezik eltávolításokhoz: a nettó változás összegének eltávolítása vagy rögzített összeg meghatározása. 

Válassza ki a forrásszámlát. Helyettesítő karakterként használhat csillag (\*) karaktert. Ebben a példában az 1\* a felosztás adatforrásaként minden olyan számlát használni fog, amelynek 1-gyel kezdődik a száma. 

A forrásszámlák kiválasztása után a **Számla meghatározása** határozza meg a célvállalat használt számláját. Válassza a **Forrás** lehetőséget, ha ugyanazt a fő számlát szeretné használni, mint ami a **Forrás** számlában van megadva. Ha a **Felhasználó által meghatározott** lehetőséget választja, meg kell adnia egy célszámlát. 

A dimenzió meghatározása azonos módon működik. Ha **Forrás** lehetőségetválasztja, ugyanazokat a dimenziókat fogja használni a célvállalatnál, mint a forrásvállalat. Ha a **Felhasználó által meghatározott** lehetőséget választja, a **Cél dimenziói** menüpont használatával meg kell adnia a célvállalat dimenzióit. 

Válassza ki a forrásdimenziókat és a pénzügyi dimenziókat, valamint az eltávolítás forrásához használt értékeket.

## <a name="process-elimination-transactions"></a>Eltávolítási tranzakciók feldolgozása
Eltávolítási tranzakciók feldolgozása kétféleképpen lehetséges: vagy az online összesítés során, vagy eltávolítási napló létrehozásával és az eltávolítási javaslati folyamat futtatásával. Ez a szakasz a napló létrehozására és az eltávolítási folyamat futtatására összpontosít. 

Egy eltávolítási vállalatként meghatározott vállalatnál válassza az **Eltávolítási napló** lehetőséget a Konszolidáció modulban. Miután kiválasztotta a napló nevét kattintson a **Sorok** elemre. A javaslat futtatásához válassza a **Javaslatok** menüt, majd az **Eltávolítási javaslat** elemet.

Válassza ki a konszolidált adatok forrásaként szolgáló vállalatot, és válassza ki a feldolgozni kívánt szabályt. Adjon meg egy kezdő dátumot, amelyen az eltávolítási összegek keresése kezdődik, és egy záró dátumot, amelyen az eltávolítási összegek keresése lezárul. A **Főkönyvi feladási dátum** mezőben adja meg a napló a főkönyvbe történő feladásának dátumát. Amikor rákattint a **OK** gombra, áttekintheti az összegeket és feladhatja a naplót.



