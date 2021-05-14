---
title: Minőségi társítások
description: Ez a témakör azt mutatja be, hogyan használhatók a Microsoft Dynamics 365 Supply Chain Management minőségi társításai az értékesítési, beszerzési és termelési folyamatokkal kapcsolatos minőségi rendelések automatikus létrehozása során.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f46f09dc9b67cfb04d0320a071c2c739266af58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956681"
---
# <a name="quality-associations"></a>Minőségi társítások

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan használhatók a Microsoft Dynamics 365 Supply Chain Management minőségi társításai az értékesítési, beszerzési és termelési folyamatokkal kapcsolatos minőségi rendelések automatikus létrehozása során.

A minőségi társítás meghatározza a létrehozott minőségi rendelésre vonatkozó alábbi adatok mindegyikét:

- Tranzakcióesemény
- A cikkeken elvégzendő tesztek
- Az elfogadható minőségi szint (AQL)
- Mintavételi terv

Definiálnia kell egy minőségi társítást az üzleti folyamat minden olyan változatához, ahol minőségi rendelés automatikus létrehozása szükséges. Minőségi rendelés létrehozható például az üzleti folyamatokban beszerzési rendelésekhez, karanténutasításokhoz, értékesítési rendelésekhez és termelési rendelésekhez.

## <a name="working-with-quality-associations"></a>Minőségi társítások használata

Egy minőségi társítást használó üzleti folyamat különféle forrásbizonylatokkal lehet kapcsolatban (például beszerzési rendelésekkel, értékesítési rendelésekkel, vagy termelési rendelésekkel).

Minden egyes minőségi társítási rekord meghatározza a létrehozott minőségi rendelésekre vonatkozó teszteket, elfogadható minőségi szintet és mintavételi eljárást. Az üzleti folyamat minden egyes változatára definiálnia kell egy minőségi társítási rekordot. Például beállíthat egy olyan minőségi társítást, amely egy beszerzési rendelés termékbevételezésének frissítésekor létrehoz egy minőségi rendelést. A végrehajtási terv beállításaitól függően maga az aktiváló folyamat blokkolható nyitott minőségi rendelés közben. A további folyamatok, például a beszerzési rendelés számlázása is blokkolható.

> [!NOTE]
> Amíg vannak nyitott minőségi rendelések, a készletmennyiségek kiadása automatikusan le van tiltva. A **Cikkmintavételek** lap **Teljes zárolás** mező beállításától függően a mennyiség a minőségi rendelésen vagy a forrásbizonylat sorában szereplő mennyiség lehet. További információért lásd: [Minőségkezelési cikk mintavételezése](quality-item-sampling.md).

Egy adott üzleti folyamatra a minőségi társítási rekord azonosítja azokat az eseményeket és feltételeket, amelyek fennállása esetén a minőségi rendelés létrejön. A feltételek helyre vagy jogi személyre vonatkozhatnak. Romboló teszteket igénylő minőségi rendelés csak akkor generálható, ha az eseményhez létezik aktuális készlet.

A minőségi társítások használatához kattintson a **Készletkezelés \> Beállítás \> Minőségellenőrzés \> Minőségi társítások** gombra. A következő példák bemutatják egy minőségi társítási rekord meghatározását az egyes üzleti folyamatok változásainak megfelelően. Egy minőségi társítási rekord által az egyes példák esetén meghatározott eseményeket és feltételeket az alábbi táblázat összegzi.

<table>
<thead>
<tr>
<th>Hivatkozás típusa</th>
<th>Eseménytípus</th>
<th>Végrehajtás</th>
<th>Eseményzárolás</th>
<th>Dokumentumhivatkozás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Készlet</td>
<td>Nem alkalmazható</td>
<td>Nem alkalmazható</td>
<td>Egyik sem</td>
<td>Mind</td>
</tr>
<tr>
<td rowspan="7">Értékesítés</td>
<td rowspan="4">Kitárolási folyamat ütemezve</td>
<td rowspan="4">Előtte</td>
<td>Egyik sem</td>
<td rowspan="22">Csak Egyedi azonosító, Csoport vagy Mind</td>
</tr>
<tr>
<td>Kitárolási folyamat</td>
</tr>
<tr>
<td>Szállítólevél</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="3">Szállítólevél</td>
<td rowspan="3">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Szállítólevél</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="15">Beszerzés</td>
<td rowspan="7">Bevételezési lista</td>
<td rowspan="4">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Bevételezési lista</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="3">Utána</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="3">Nyilvántartás</td>
<td rowspan="3">Nem alkalmazható</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="5">Termékbevételezés</td>
<td rowspan="3">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="2">Utána</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="8">Termelés</td>
<td rowspan="3">Nyilvántartás</td>
<td rowspan="3">Nem alkalmazható</td>
<td>Egyik sem</td>
<td rowspan="12">Mind</td>
</tr>
<tr>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td rowspan="5">Készként jelentés</td>
<td rowspan="3">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td rowspan="2">Utána</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td rowspan="4">Karantén</td>
<td rowspan="3">Készként jelentés</td>
<td rowspan="2">Előtte</td>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td>Utána</td>
<td>Záró</td>
</tr>
<tr>
<td>Záró</td>
<td>Előtte</td>
<td>Záró</td>
</tr>
<tr>
<td rowspan="3">Útvonalművelet</td>
<td rowspan="3">Készként jelentés</td>
<td rowspan="2">Előtte</td>
<td>None</td>
<td rowspan="3">Egyedi azonosító, Csoport vagy Mind, valamint adott Erőforrás, Csoport vagy Mind</td>
</tr>
<tr>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Után</td>
<td>None</td>
</tr>
<tr>
<td rowspan="3">Társtermék gyártása</td>
<td>Nyilvántartás</td>
<td>Nem alkalmazható</td>
<td rowspan="3">None</td>
<td rowspan="3">Összes</td>
</tr>
<tr>
<td rowspan="2">Készként jelentés</td>
<td>Előtte</td>
</tr>
<tr>
<td>Után</td>
</tr>
</tbody>
</table>

> [!NOTE]
> A *Minőségkezelés a raktári folyamatokhoz* funkció hozzáadja a minőségi rendelés feldolgozásához szükséges képességeket, ahol az **Eseménytípus** mező beállítása *Készként jelentés*, és a **Végrehajtás** mező beállítása *Után*, és ahol az **Eseménytípus** mező típusú beszerzések beállítása *Regisztráció*. További információ: [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md).

A következő táblázatban bővebben tájékozódhat arról, hogy hogyan hozhatóak létre minőségi rendelések adott típusú folyamatokhoz.

<div class="tableSection">
<table>
<thead>
<tr>
<th>Folyamat típusa</th>
<th>Mikor hozhatóak létre automatikusan minőségi rendelések?</th>
<th>Mikor hozhatóak létre minőségi rendelések, amennyiben romboló tesztekre van szükség?</th>
<th>Feltételekre vonatkozó információ</th>
<th>Manuális létrehozásra vonatkozó információ</th>
</tr>
</thead>
<tbody>
<tr>
<td>Beszerzési rendelés</td>
<td>A bevételezett anyagra vonatkozó bevételezési lista vagy termékbevételezés feladása előtt vagy után</td>
<td>A bevételezett anyagra vonatkozó termékbevételezés feladása után, mivel az anyagnak rendelkezésre kell állnia a romboló teszt elvégzéséhez</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</td>
<td>A beszerzési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Karanténutasítás</td>
<td>Mielőtt vagy miután a karanténutasítás készként lett jelentve vagy befejeződött</td>
<td>Romboló teszteket igénylő minőségi rendelések nem hozhatóak létre. A rendszer feltételezi, hogy a karanténutasítás funkció kezeli a roncsolt anyag elhelyezését.</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</td>
<td>A karanténutasításokhoz manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Értékesítési rendelés</td>
<td>A szállított cikkekre vonatkozó ütemezett kitárolási folyamat vagy szállítólevél frissítése előtt</td>
<td>Bármelyik lépésnél</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy vevőre, illetve ezek bármilyen kombinációjára.</td>
<td>Az értékesítési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Termelési rendelés</td>
<td>A termelési rendelés befejezett mennyiségének jelentése előtt vagy után</td>
<td>A termelési rendelés befejezett mennyiségének jelentése után</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, illetve ezek bármilyen kombinációjára.</td>
<td>A termelési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Útvonalművelettel rendelkező termelési utasítás</td>
<td>A műveletre vonatkozó jelentés befejezése előtt vagy után</td>
<td>Miután az utolsó művelet készként való jelentése megtörtént</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, vevőre vagy üzemi erőforrásra, illetve ezek bármilyen kombinációjára.</td>
<td>Az útvonalművelethez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Készlet</td>
<td>A készletnaplón belüli tranzakciókhoz és az átmozgatási rendelési tranzakciókhoz nem generálhatók automatikusan minőségi rendelések.</td>
<td></td>
<td></td>
<td>Cikk készletmennyiségére vonatkozó minőségi rendelést manuálisan kell létrehozni. Tényleges aktuális készlet szükséges.</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Minőségi rendelések automatikus generálásával kapcsolatos példák

### <a name="purchasing"></a>Beszerzés

Ha a beszerzés modulban az **Eseménytípus** mezőt a *Termék nyugtája* értékre állítja, a **Végrehajtás** mezőt pedig *Után* értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:

- Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó összes bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján. Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben megkapnak, új minőségi rendelések jönnek létre az újonnan megkapott mennyiség alapján.
- Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre a beszerzési rendeléshez tartozó első bevételezéshez, a bevételezett mennyiség és a cikkmintavétel beállításai alapján. Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a nyomon követési dimenziók függvényében. Nem jönnek létre minőségi rendelések a beszerzési rendelés későbbi bevételezéseihez.

### <a name="production"></a>Termelés

Ha a gyártásban az **Eseménytípus** mezőt a *Befejezettnek jelentés* értékre állítja, a **Végrehajtás** mezőt pedig *Után* értékre a **Minőségi társítások** lapon, akkor a következő eredményeket kapja:

- Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre minden befejezett mennyiség és a cikkmintavételezés beállításai alapján. Minden alkalommal, amikor egy mennyiséget a beszerzési rendeléssel szemben késznek jelentenek, új minőségi rendelések jönnek létre az újonnan elkészült mennyiség alapján. Ez a generálási logika összhangban van a beszerzéssel.
- Ha a **Frissített mennyiség** beállítás *Igen* értékre van állítva , akkor a program minőségi rendelést hoz létre az első alkalommal, amikor a mennyiség készek van jelentve, a kész mennyiség és a cikkmintavétel beállításai alapján. Ezenkívül a program egy vagy több minőségi rendelést hoz létre a fennmaradó mennyiség alapján, a cikkmintavételezés nyomon követési dimenziói függvényében. A további kész mennyiségek esetében nem jönnek létre minőségi rendelések.

<table>
<thead>
<tr>
<th>Minőség megadása</th>
<th>Frissített mennyiségenként</th>
<th>Nyomon követési dimenziónként</th>
<th>Eredmény</th>
</tr>
</thead>
<tbody>
<tr>
<td>Százalék: 10%</td>
<td>Igen</td>
<td>
<p>Kötegszám: Nincs</p>
<p>Sorozatszám: Nincs</p>
</td>
<td>
<p>Rendelt mennyiség: 100</p>
<ol>
<li>Készként jelentés 30-hoz
<ul>
<li>1. minőségi rendelés 3-hoz (a 30 10%-a)</li>
</ul>
</li>
<li>Készként jelentés 70-hoz
<ul>
<li>2. minőségi rendelés 7-hez (a fennmaradó rendelési mennyiség 10%-a, amely ebben az esetben 70)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Rögzített mennyiség: 1</td>
<td>Nincs</td>
<td>
<p>Kötegszám: Nincs</p>
<p>Sorozatszám: Nincs</p>
</td>
<td>Rendelt mennyiség: 100
<ol>
<li>Készként jelentés 30-hoz
<ul>
<li>Az 1. minőségi rendelés 1-hez lesz létrehozva (az első jelentett kész mennyiséghez, amelynek rögzített értéke 1)</li>
<li>A 2. minőségi rendelés 1-hez lesz létrehozva (a fennmaradó mennyiséghez, amelynek rögzített értéke 1)</li>
</ul>
</li>
<li>Készként jelentés 10-hoz
<ul>
<li>Nem jönnek létre minőségi rendelések.</li>
</ul>
</li>
<li>Készként jelentés 60-hoz
<ul>
<li>Nem jönnek létre minőségi rendelések.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Rögzített mennyiség: 1</td>
<td>Igen</td>
<td>
<p>Kötegszám: Igen</p>
<p>Sorozatszám: Igen</p>
</td>
<td>
<p>Rendelt mennyiség: 10</p>
<ol>
<li>Készként jelentve a 3-hoz: 1 a b1 kötegszámhoz, sorozatszám: s1; 1 a b2 kötegszámhoz, sorozatszám: s2; 1 a b3 kötegszámhoz, sorozatszám: s3
<ul>
<li>1. minőségi rendelés 1-hez, b1 kötegszám, sorozatszám: s1</li>
<li>2. minőségi rendelés 1-hez, b2 kötegszám, sorozatszám: s2</li>
<li>3. minőségi rendelés 1-hez, b3 kötegszám, sorozatszám: s3</li>
</ul>
</li>
<li>Készként jelentve a 2-höz: 1 a b4 kötegszámhoz, sorozatszám: s4; 1 a b5 kötegszámhoz, sorozatszám: s5
<ul>
<li>4. minőségi rendelés 1-hez, b4 kötegszám, sorozatszám: s4</li>
<li>5. minőségi rendelés 1-hez, b5 kötegszám, sorozatszám: s5</li>
</ul>
</li>
</ol>
<p><strong>Megjegyzés:</strong> A köteg újra felhasználható.</p>
</td>
</tr>
<tr>
<td>Rögzített mennyiség: 2</td>
<td>Nincs</td>
<td>
<p>Kötegszám: Igen</p>
<p>Sorozatszám: Igen</p>
</td>
<td>
<p>Rendelt mennyiség: 10</p>
<ol>
<li>Készként jelentve a 3-hoz: 1 a b1 kötegszámhoz, sorozatszám: s1; 1 a b2 kötegszámhoz, sorozatszám: s2; 1 a b3 kötegszámhoz, sorozatszám: s3; és 1 a b4 kötegszámhoz, sorozatszám: s4
<ul>
<li>1. minőségi rendelés 1-hez, b1 kötegszám, sorozatszám: s1</li>
<li>2. minőségi rendelés 1-hez, b2 kötegszám, sorozatszám: s2</li>
<li>3. minőségi rendelés 1-hez, b3 kötegszám, sorozatszám: s3</li>
<li>4. minőségi rendelés 1-hez, b4 kötegszám, sorozatszám: s4</li>
</ul>
<ul>
<li>5. minőségi rendelés a 2-höz, egy kötegszámra és egy sorozatszámra való hivatkozás nélkül</li>
</ul>
</li>
<li>Készként jelentve a 6-hoz: 1 a b5 kötegszámhoz, sorozatszám: s5; 1 a b6 kötegszámhoz, sorozatszám: s6; 1 a b7 kötegszámhoz, sorozatszám: s7; 1 a b8 kötegszámhoz, sorozatszám: s8; 1 a b9 kötegszámhoz, sorozatszám: s9; 1 a b10 kötegszámhoz, sorozatszám: s10
<ul>
<li>Nem jönnek létre minőségi rendelések.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelési folyamatok](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
