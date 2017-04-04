---
title: "A termékkonfigurációs modellek kifejezésmegszorításai"
description: "Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások. Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-02-24 15 - 08 - 06
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 1fe8a0d90a3f707fa7b0fea0310c819ce5040a42
ms.lasthandoff: 03/30/2017


---

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>A termékkonfigurációs modellek kifejezésmegszorításai

Ez a témakör leírja a kifejezés megszorítások és táblamegszorítások. Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja. 

Megszorítások szabályozni a termékattribútum-értékeinek, amelyből választani lehet a termékek egy értékesítési rendelés, árajánlat, beszerzési rendelés vagy termelési rendelés konfigurálásakor. Kifejezés megszorítások vagy táblamegszorítások, attól függően, hogy hogyan szeretné hozhatják létre a megszorítások használhatja.

## <a name="what-are-expression-constraints"></a>Kifejezésmegszorítás szerkesztője
Kifejezés megszorítások jellemző aritmetikai és logikai operátort és függvényt használó kifejezést. A termékkonfigurációs modell adott összetevő egy Kifejezésmegszorítás készült. Nem használja fel újra, és egy másik összetevő megosztva. Egy összetevőre vonatkozó kifejezés megszorításai az összetevők részösszetevőinek attribútumaira is hivatkozhatnak.

## <a name="what-are-table-constraints"></a>Kifejezésmegszorítás szerkesztője
Táblamegszorítások-kombinációkat termék konfigurálásakor attribútumok megengedett értékek listája. Táblamegszorítási definíciók általában használható. A termékkonfigurációs modell összetevőhöz táblamegszorítás létrehozásakor ki kell választania egy táblamegszorítás definíciója. A megengedett kombinációk létrehozásához hozzáadja az összetevők különféle jellemzőit. Minden egyes attribútumtípus egy adott értékű.

### <a name="example-of-a-table-constraint"></a>Táblamegszorítás típusa

Ez a példa azt mutatja, hogyan korlátozhatja egy adott kabinetfájl befejeződik és előlapot hangszóró konfigurációját. Az első táblázat mutatja a méreteket és a televízió, általában elérhető konfigurációs típusú. Az értékek meghatározott, a ** kabinet Befejezés ** és **első rács** típusú attribútum.

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

## <a name="what-syntax-should-be-used-to-write-constraints"></a>Milyen szintaxist kell használni megkötések írni?
A feltételt az Optimization Modeling Language (OML) szintaxisa alapján kell megírnia. A rendszer Microsoft Solver Foundation korlátozás a solver segítségével oldja meg a függőségeket.

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

(Szín == "Fekete" & (méret == "30" |} méret == "50")) |} (szín == "Piros" & mérete = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>I. operátorokkal, vagy infix a jelölés kifejezés megszorítások írva?
Előtag rendelkezésre álló operátorok a használatával egy Kifejezésmegszorítás írhat vagy használatával infix jelölés. A műveletek **Min**, **Max** és **Abs ** egy infix jelölés nem használhat. A legtöbb programnyelven alapértelmezésként ezen operátorok jelennek meg.

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
<li><strong>Üzemeltető:</strong> vonja maga után [x! = 0, y &gt;= 0]</li>
<li><strong>Infix jelölés:</strong> x! = 0-: i &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>És</td>
<td>Ez akkor is igaz, csak az összes feltételek teljesülése esetén. Ha a feltétel értéke 0 (nulla), <strong>Igaz</strong> hoz létre.</td>
<td>Infix [argumentumok], és: a &amp;b &amp; ... &amp;z</td>
<td><ul>
<li><strong>Üzemeltető:</strong> és [x == 2 y &lt;= 2]</li>
<li><strong>Infix jelölés:</strong> x == 2 &amp;y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Vagy</td>
<td>Ez akkor is igaz, ha bármelyik feltétel teljesül. Ha a feltétel értéke 0 (nulla), <strong>Hamis</strong> hoz létre.</td>
<td>Infix [argumentumok], vagy: a |}] b |}] ... | z</td>
<td><ul>
<li><strong>Üzemeltető:</strong> vagy [x == 2 y &lt;= 2]</li>
<li><strong>Infix jelölés:</strong> x == 2 |}] y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Plusz</td>
<td>Ez az összegek feltételeit. Ha a feltétel értéke 0 (nulla), <strong>0</strong>-t hoz létre.</td>
<td>Infix [argumentumok], plusz: a + b +... + z</td>
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
<td>Infix [argumentumok], időpont: a * b *... * z</td>
<td><ul>
<li><strong>Művelet:</strong> Times[x, y, 2] == z</li>
<li><strong>Infix jelölés:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Teljesítmény</td>
<td>Ez a termelésnek a tudományos. Ez akkor érvényes hatványkitevő jobbról balra. (Más szóval, jobb asszociatív.) Ezért <strong>[a, b, c] kiemelt</strong> egyenértékű <strong>teljesítmény [, teljesítmény [b, c]]</strong>. A <strong>Power</strong> csak használható pozitív állandó, mint a kitevő.</td>
<td>[Argumentumok] kiemelt, infix: egy ^ b ^... ^ z</td>
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
<li><strong>Üzemeltető:</strong> nem [x] &amp;nem [y == 3]</li>
<li><strong>Infix jelölés:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

Az alábbi táblázatban szereplő példák bemutatják, hogyan lehet írni egy infix jelölés.

| Jelölés Infix:    | Leírás                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| x + y + z         | Hozzáadás                                                                                      |
| X \*y \*z       | szorzás                                                                                |
| x - y             | Bináris kivonás egy fordító bináris összeadás második megkereséséhez, megegyezik. |
| x ^ y ^ z         | A jobb oldali asszociativitást hatványkitevő                                                   |
| !x                | Logikai                                                                                   |
| x -: y            | Logikai tényezők                                                                           |
| x | y | z         | Logikai vagy                                                                                    |
| x & y & z         | Logikai és                                                                                   |
| x == y == z       | egyenlőség                                                                                      |
| x != y != z       | Különálló                                                                                      |
| X &lt;y &lt;z   | Kisebb, mint                                                                                     |
| X &gt;y &gt;z   | Nagyobb, mint                                                                                  |
| X &lt;= y &lt;= z | Kisebb vagy egyenlő                                                                         |
| X &gt;= y &gt;= z | Nagyobb vagy egyenlő                                                                      |
| (x)               | Zárójelek alapértelmezett elsőbbségi sorrend felülbírálása.                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>Miért nem megfelelő a kifejezés megszorítások ellenőrzése?
Attribútumok, alkatrészek vagy az egy termékkonfigurációs modell alösszetevői attribútumfeloldó neve fenntartott kulcsszó nem használható. Itt van, amely nem használható a foglalt kulcsszavak listája:

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
-   Min.
-   Mínusz
-   Plusz
-   Teljesítmény
-   Idők
-   Időköz
-   Típus
-   Döntés
-   Cél


<a name="see-also"></a>Lásd még
--------

[Egy kifejezés korlátozás (feladat guide) létrehozása](http://ax.help.dynamics.com/en/wiki/create-an-expression-constraint/)

[Adja hozzá a számítás konfigurációs termékmodell (feladat guide)](http://ax.help.dynamics.com/en/wiki/add-a-calculation-to-a-product-configuration-model/)


