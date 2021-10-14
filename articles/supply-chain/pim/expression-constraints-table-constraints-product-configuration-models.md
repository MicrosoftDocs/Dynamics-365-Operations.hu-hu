---
title: A termékkonfigurációs modellek kifejezésmegszorításai
description: Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások. Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8775a9225313c0f5a132dbccbe583470fe23beab
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570729"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>A termékkonfigurációs modellek kifejezésmegszorításai

[!include [banner](../includes/banner.md)]

Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások. Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja. 

Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.

## <a name="what-are-expression-constraints"></a>Kifejezésmegszorítás szerkesztője
Kifejezés megszorítások jellemző aritmetikai és logikai operátort és függvényt használó kifejezést. A termékkonfigurációs modell adott összetevő egy Kifejezésmegszorítás készült. Nem használja fel újra, és egy másik összetevő megosztva. Egy összetevőre vonatkozó kifejezés megszorításai az összetevők részösszetevőinek attribútumaira is hivatkozhatnak.

## <a name="what-are-table-constraints"></a>Kifejezésmegszorítás szerkesztője
Táblamegszorítások-kombinációkat termék konfigurálásakor attribútumok megengedett értékek listája. Táblamegszorítási definíciók általában használható. A termékkonfigurációs modell összetevőhöz táblamegszorítás létrehozásakor ki kell választania egy táblamegszorítás definíciója. A megengedett kombinációk létrehozásához hozzáadja az összetevők különféle jellemzőit. Minden egyes attribútumtípus egy adott értékű.

### <a name="example-of-a-table-constraint"></a>Táblamegszorítás típusa

Ez a példa azt mutatja, hogyan korlátozhatja egy adott kabinetfájl befejeződik és előlapot hangszóró konfigurációját. Az első táblázat mutatja a méreteket és a televízió, általában elérhető konfigurációs típusú. Határozhatók meg az értékeket a **Kabinetfájl befejezés** és **Első rács** attribútum típusa.

| Attribútumtípus | Értékek                      |
|----------------|-----------------------------|
| Hangszóró borítása | Fekete, tölgyfa, rózsafa, fehér |
| Elülső rács    | Fekete, fém, fehér         |

A következő táblázat bemutatja a kombinációk határozzák meg, hogy a **Szín és kivitel** táblamegszorítás. A táblamegszorítás használatával konfigurálhatja egy tölgy Befejezés és fekete ráccsal, egy rózsafa Befejezés és fehér rács előadó, és így tovább.

| Elvégzés         | Rács                       |
|----------------|-----------------------------|
| Tölgyfa            | Fekete                       |
| Rózsafa       | Fehér                       |
| Fehér          | Fekete                       |
| Fehér          | Fehér                       |
| Fekete          | Fekete                       |
| Fekete          | Fém                       | 

A táblázatok megszorításai felhasználó által definiáltak vagy rendszer definiáltak is lehetnek. További tudnivalókért lásd: [Rendszer által definiált és felhasználó által definiált táblamegszorítások](system-defined-user-defined-table-constraints.md).

## <a name="what-syntax-should-be-used-to-write-constraints"></a>Milyen szintaxist kell használni korlátozások kiírására?
A feltételt az Optimization Modeling Language (OML) szintaxisa alapján kell megírnia. A rendszer a Microsoft Solver Foundation megszorításfeloldóját használja a megszorítások megoldására.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>Kifejezés megszorítások és táblamegszorítások
Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja. Hoz létre olyan táblamegszorításhoz be egy mátrixban, mivel egy Kifejezésmegszorítás az egyes utasítást. A termék konfigurálásához teljesen mindegy, milyen megszorítás használatos. Az alábbi példák mutatják a beállításainak alkalmazását.  

A termék a következő megszorítás beállítások használatával konfigurálásakor ezt követően a kombinációkat használhatók:

-   A termék fekete színnel 30 vagy 50 mérete
-   A termék piros színnel és 20 mérettel

### <a name="table-constraint-setup"></a>Táblamegszorítási csoport

| Szín | Méret |
|-------|------|
| Fekete | 30   |
| Fekete | 50   |
| Piros   | 20   |

### <a name="expression-constraint-setup"></a>Kifejezésmegszorítás

(Szín == "Fekete" & (méret == "30" | méret == "50")) | (szín == "Piros" & mérete = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?
Előtag rendelkezésre álló operátorok a használatával egy Kifejezésmegszorítás írhat vagy használatával infix jelölés. A **Min**, **Max** és **Abs** operátoroknál nem használhat infix jelölést. A legtöbb programnyelven alapértelmezésként ezen operátorok jelennek meg.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?
A következő táblázatokban a listában az operátorok és infix jelölések, amely lehet használni, amikor egy Kifejezésmegszorítás összetevőhöz ír egy termékkonfigurációs modell. A példákban a első táblázatban megtekintheti a kifejezés írása infix jelöléssel, vagy az operátorok segítségével.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Kezelő</th>
<th>Leírás</th>
<th>Szintaxis</th>
<th>Példák</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implikálja</td>
<td>Ez akkor is igaz, ha az első feltétel nem teljesül, a második feltétel értéke igaz, vagy mindkettőt.</td>
<td>Azt jelenti, [a, b] infix: a-: b</td>
<td><ul>
<li><strong>Műveleti jel:</strong> a következőt jelenti: [x != 0, y &gt;= 0]</li>
<li><strong>Infix jelölés:</strong> x != 0 -: y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>És</td>
<td>Ez akkor is igaz, csak az összes feltételek teljesülése esetén. Ha a feltétel értéke 0 (nulla), <strong>Igaz</strong> hoz létre.</td>
<td>And[argumentumok], infix: a &amp; b &amp; ... &amp; z</td>
<td><ul>
<li><strong>Műveleti jel:</strong> And[x == 2, y &lt;= 2]</li>
<li><strong>Infix jelölés:</strong> x == 2 &amp; y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Vagy</td>
<td>Ez akkor is igaz, ha bármelyik feltétel teljesül. Ha a feltétel értéke 0 (nulla), <strong>Hamis</strong> hoz létre.</td>
<td>Or[argumentumok], infix: a | b | ... | z</td>
<td><ul>
<li><strong>Műveleti jel:</strong> Or[x == 2, y &lt;= 2]</li>
<li><strong>Infix jelölés:</strong> x == 2 | y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Plusz</td>
<td>Ez az összegek feltételeit. Ha a feltétel értéke 0 (nulla), <strong>0</strong>-t hoz létre.</td>
<td>Plusz[argumentumok], infix: a + b + ... + z</td>
<td><ul>
<li><strong>Művelet:</strong> Plus[x, y, 2] == z</li>
<li><strong>Infix jelölés:</strong> x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Mínusz</td>
<td>Ez a argumentum ellentettjét adja. Ez kell pontosan egy feltételt.</td>
<td>[Kifejezés], csökkentett infix: - kifejezés</td>
<td><ul>
<li><strong>Művelet:</strong> Minus[x] == y</li>
<li><strong>Infix jelölés:</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>(ABS)</td>
<td>Ez a termelésnek állapotuk adat abszolút értéke. Ez kell pontosan egy feltételt.</td>
<td>[Kifejezés] ABS</td>
<td><strong>Művelet:</strong> Abs[x]</td>
</tr>
<tr class="odd">
<td>Idők</td>
<td>Ez a feltétel a termék vesz igénybe. Ha a feltétel értéke 0 (nulla), <strong>1</strong>-t hoz létre.</td>
<td>Szorzás[argumentumok], infix: a * b * ... * z</td>
<td><ul>
<li><strong>Művelet:</strong> Times[x, y, 2] == z</li>
<li><strong>Infix jelölés:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Teljesítmény</td>
<td>Ez a termelésnek a tudományos. Ez akkor érvényes hatványkitevő jobbról balra. (Ez azt jelenti, hogy jobbra társuló.) Ezért <strong>Hatvány[a, b, c]</strong> egyenlő: <strong>Hatvány[a, hatvány[b, c]]</strong>. A <strong>Power</strong> csak használható pozitív állandó, mint a kitevő.</td>
<td>Hatvány[argumentumok], infix: a ^ b ^ ... ^ z</td>
<td><ul>
<li><strong>Művelet:</strong> Power[x, 2] == y</li>
<li><strong>Infix jelölés:</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Max.</td>
<td>A legnagyobb feltétel jelenít meg. Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</td>
<td>Max[args]</td>
<td><strong>Művelet:</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Min.</td>
<td>A legkisebb feltételt jeleníti meg. Ha a feltétel értéke 0 (nulla), <strong>Végtelen</strong> hoz létre.</td>
<td>Min[args]</td>
<td><strong>Művelet:</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Nem</td>
<td>A feltétel logikai inverzét jelenít meg. Ez kell pontosan egy feltételt.</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>Műveleti jel:</strong> Not[x] &amp; Not[y == 3]</li>
<li><strong>Infix jelölés:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

Az alábbi táblázatban szereplő példák bemutatják, hogyan lehet írni egy infix jelölés.


|  Jelölés Infix:   |                                          Leírás                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     x + y + z     |                                           Hozzáadás                                            |
|    x \* y \* z    |                                        szorzás                                         |
|       x - y       | Bináris kivonás egy fordító bináris összeadás második megkereséséhez, megegyezik. |
|     x ^ y ^ z     |                          A jobb oldali asszociativitást hatványkitevő                          |
|        !x         |                                          Logikai                                          |
|      x -: y       |                                      Logikai tényezők                                      |
|         x         |                                               y                                               |
|     x & y & z     |                                          Logikai és                                          |
|    x == y == z    |                                           egyenlőség                                            |
|    x != y != z    |                                           Különálló                                            |
|  x &lt; y &lt; z  |                                           Kisebb, mint                                           |
|  x &gt; y &gt; z  |                                         Nagyobb, mint                                          |
| x &lt;= y &lt;= z |                                     Kisebb vagy egyenlő                                     |
| x &gt;= y &gt;= z |                                   Nagyobb vagy egyenlő                                    |
|        (x)        |                           Zárójelek alapértelmezett elsőbbségi sorrend felülbírálása.                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>Miért nem megfelelő a kifejezés megszorítások ellenőrzése?
Attribútumok, alkatrészek vagy az egy termékkonfigurációs modell alösszetevői attribútumfeloldó neve fenntartott kulcsszó nem használható. Az alábbi lista a foglalt kulcsszavakat mutatja, amelyek nem használhatók:

-   Felső határ
-   Elem
-   Egyenlő
-   Emelet
-   Ha
-   Kisebb
-   Nagyobb
-   Implikálja
-   Eseménynapló
-   Max.
-   perc
-   Mínusz
-   Plusz
-   Teljesítmény
-   Idők
-   Időköz
-   Típus
-   Döntés
-   Cél


## <a name="additional-resources"></a>További erőforrások

[Kifejezésmegszorítás szerkesztője](tasks/add-expression-constraint-product-configuration-model.md)

[Kalkuláció hozzáadása termékkonfigurációs modellhez](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]