---
title: Speciális szűrési és lekérdezési szintaxis
description: Ez a témakör leírja a Speciális szűrés/rendezés párbeszédpanel szűrési és lekérdezési beállításait, valamint a Szűrő ablaktábla vagy rács oszlopfejlécszűrőiben szereplő egyezés operátort.
author: jasongre
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 520c8b32099024e9a9619a6ecdcd3ba7b97c7ecf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856918"
---
# <a name="advanced-filtering-and-query-syntax"></a>Speciális szűrési és lekérdezési szintaxis

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

A témakör ismerteti a szűrési és lekérdezési beállításokat, amelyek elérhetők a Speciális szűrés/rendezés párbeszédpanelen vagy az **egyezések** operátor vagy a rács oszlop fejléce szűrők használata esetén.

## <a name="advanced-query-syntax"></a>Speciális lekérdezési szintaxis

<table>
<thead>
<tr>
<th>Szintaxis</th>
<th>Működése</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>Érték</em></td>
<td>Megegyezik a beírt értékkel.</td>
<td>Írja be a keresendő érték.</td>
<td>A <strong>Kovács</strong> keresésére a program a &quot;Kovács&quot; értéket találja meg.</td>
</tr>
<tr>
<td>!<em>érték</em> (felkiáltójel)</td>
<td>Nem egyezik meg a beírt értékkel</td>
<td>Írjon be egy felkiáltójelet az elé az érték elé, amelyet szeretne kizárni a keresésből.</td>
<td>A <strong>!Kovács</strong> keresésére a program a &quot;Kovács&quot; érték kivételével az összes értéket megtalálja.</td>
</tr>
<tr>
<td><em>Kezdő érték</em>..<em>Záró érték</em> (két pont)</td>
<td>A két ponttal elválaszott értékek között keres</td>
<td>Írja be a „-tól” értéket, majd két pontot, végül az „-ig” értéket.</td>
<td><strong>1..10</strong> keresése esetén az 1 és 10 közötti összes értéket megtalálja a program. Karakterláncmezőkben azonban az <strong>A..C</strong> keresése esetén az összes &quot;A&quot; és &quot;B&quot; kezdetű értéket, valamint a &quot;C&quot; értékkel pontosan megegyező értékeket találja meg a program (a „Ca” értéket például nem fogja megtalálni). Ez a lekérdezés például nem fogja megtalálni a &quot;Ca&quot; értéket. Hogy minden értéket megtaláljon &quot;A<em>&quot; értéktől &quot;C</em>&quot; értékig, írja be, hogy: <strong>A..D</strong>.</td>
</tr>
<tr>
<td>..<em>érték</em> (két pont)</td>
<td>Megkeresi a beírt értékkel egyenlő, vagy annál kisebb értékeket</td>
<td>Írjon be két pontot majd az értéket.</td>
<td><strong>..1000</strong> keresése esetén a program minden olyan számot megtalál, amely kisebb vagy egyenlő, mint 1000 - például &quot;100&quot;, &quot;999,95&quot; és &quot;1000&quot;.</td>
</tr>
<tr>
<td><em>érték</em>.. (két pont)</td>
<td>A beírt értékkel megegyező vagy annál nagyobb értékeket találja meg</td>
<td>Írja be az értéket, majd két pontot.</td>
<td><strong>1000..</strong> keresése esetén a program minden olyan számot megtalál, amely nagyobb, mint 1000 vagy pontosan annyi, például a következőket: &quot;1000&quot;, &quot;1000,01&quot; és &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&gt;<em>jel</em> (nagyobb mint jel)</td>
<td>Nagyobb, mint a beírt érték.</td>
<td>Írja be a „nagyobb” (<strong>&gt;</strong>) jelet, majd az értéket.</td>
<td><strong>&gt;1000</strong> keresésére esetén a program minden olyan számot megtalál, amely nagyobb, mint 1000 vagy pontosan annyi, például a következőket: &quot;1000,01&quot;, &quot;20 000&quot; és &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&lt;<em>érték</em> (kisebb mint jel)</td>
<td>Kisebb, mint a beírt érték</td>
<td>Írja be a „kisebb” (<strong>&lt;</strong>) jelet, majd az értéket.</td>
<td><strong>&lt;1000</strong> keresésére a program minden olyan számot megtalál, amely kisebb, mint 1000, például a következőket: &quot;999,99&quot;, &quot;1&quot; és &quot;-200&quot;.</td>
</tr>
<tr>
<td><em>érték</em>* (csillag)</td>
<td>A beírt értéktől kezdve</td>
<td>Írja be a kezdő értéket, majd egy csillagot (<strong>*</strong>).</td>
<td><strong>S*</strong> keresése esetén a program minden &quot;S&quot;-sel kezdődő karakterláncot megtalál, például a következőket: &quot;Stockholm&quot;, &quot;Sydney&quot; és &quot;San Francisco&quot;.</td>
</tr>
<tr>
<td>*<em>érték</em> (csillag)</td>
<td>A beírt értékre végződő</td>
<td>Írjon be egy csillagot, majd a végződésként szereplő értéket.</td>
<td><strong>*kelet</strong> keresése esetén a program minden olyan karakterláncot megtalál, amely a &quot;kelet&quot; szóra végződik, például a következőket: &quot;északkelet&quot;, &quot;délkelet&quot;.</td>
</tr>
<tr>
<td>*<em>érték</em>* (csillag)</td>
<td>Tartalmazza a beírt értéket</td>
<td>Írjon be egy csillagot, egy értéket, majd egy másik csillagot.</td>
<td><strong>*nt*</strong> keresése esetén a program minden olyan karakterláncot megtalál, amelyben szerepel az &quot;nt&quot; érték, például a következőket: &quot;Dunántúl&quot; és &quot;Tiszántúl&quot;.</td>
</tr>
<tr>
<td>? (kérdőjel)</td>
<td>Egy vagy több ismeretlen karakter szerepel benne.</td>
<td>Írjon be egy kérdőjelet az ismeretlen karakternek az értéken belüli helyére.</td>
<td><strong>Cseh?</strong> keresése esetén a program a &quot;Csehi&quot; és a &quot;Csehy&quot; értéket is megjeleníti.</td>
</tr>
<tr>
<td><em>érték</em>,<em>érték</em> (vessző)</td>
<td>A vesszővel elválasztott értékekkel megegyező értékek</td>
<td>Írja be az összes keresési feltételt vesszővel elválasztva.</td>
<td><strong>A, D, F, G</strong> keresése esetén a program az &quot;A&quot;, &quot;D&quot;, &quot;F&quot; és &quot;G&quot; értékeket találja meg. <strong>10, 20, 30, 100</strong> keresése esetén a &quot;10, 20, 30, 100&quot; értékeket találja meg a program.</td>
</tr>
<tr>
<td>"" (kettő dupla idézőjel)</td>
<td>Üres érték egyeztetése</td>
<td>Írjon be két egymást követő idézőjelet a mező üres értékeinek szűréséhez.</td>
<td>A két egymást követő dupla idézőjel (<strong>""</strong>) olyan sorokat keres, amelyeknek nincs értéke az aktuális oszlopban.</td>
</tr>
<tr>
<td>(<span class="code">Pénzügy és műveletek lekérdezése</span>) (Pénzügy és Műveletek lekérdezés zárójelek között)</td>
<td>A megadott lekérdezésnek megfelelő.</td>
<td>Írjon be egy SQL-lekérdezést zárójelek között a Pénzügy és műveletek lekérdezési nyelvének használatával.</td>
  <td><strong><span class="code">((AccountNum LIKE "US *") && (DirPartyTable.Name LIKE "Cont*"))</span></strong><br><br> 
       példaként egy szűrő feltételének szintaxisára a gyökérszintű adatforrás mezőjéből, valamint egy másik adatforrásmezőből (az összes vevő laphoz)</td>
</tr>
<tr>
<td>K</td>
<td>Mai dátum</td>
<td><strong>T</strong> típus.</td>
<td><strong>T</strong> megegyezik a mai dátummal.</td>
</tr>
<tr>
<td>(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> zárójelek közötti mód)</td>
<td>Az érték vagy a paraméterek a <strong>SysQueryRangeUtil</strong> metódus által megadott értékek</td>
<td>Az érték vagy a paraméterek a <strong>SysQueryRangeUtil</strong> metódus által megadott értékek</td>
<td>
<ol>
<li>Ugorjon a következőre: <strong>Kinnlévőségek</strong> &gt; <strong>Számlák</strong> &gt; <strong>Nyitott vevői számlák</strong>.</li>
<li>Nyomja le a Ctrl+Shift+F3 nyissa meg a <strong>Lekérdezési</strong> oldalon.</li>
<li>Kattintson a <strong>Tartomány</strong> lap <strong>Hozzáadás</strong> gombjára.</li>
<li>A <strong>Táblázat</strong> mezőben válassza a <strong>Nyitott vevői tranzakciók</strong> opciót.</li>
<li>A <strong>Mező</strong> mezőben válassza a <strong>Határidő</strong> lehetőséget.</li>
<li>A <strong>Kritérium</strong> mezőbe írja be a <strong>(yearRange(-2,0))</strong> szót.</li>
<li>Kattintson az <strong>OK</strong> gombra. A lista lap azoknak a feltételeknek megfelelő számlák frissítése. Ebben a példában az volt az előző két év az esedékes számlák szerepelnek a lista lap.</li>
</ol>
A tábla a következő szakaszban további részletekért lásd <strong>SysQueryRangeUtil</strong> dátum metódusok és több példák.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>Speciális dátum lekérdezések SysQueryRangeUtil módszerek használata

<table>
<thead>
<tr>
<th>Mód</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr>
<td>Nap (_relativeDays = 0)</td>
<td>Dátum képest a munkamenet dátuma található. A pozitív értékek jelezheti a jövőben esedékes, valamint a negatív értékek múltbeli dátumok.</td>
<td>
<ul>
<li><strong>Másnap</strong> – Írja be <strong>(Nap(1))</strong>.</li>
<li><strong>Ma</strong> – Írja be <strong>(Nap(0))</strong>.</li>
<li><strong>Tegnap</strong> – Írja be <strong>(Nap(-1))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Dátum képest a munkamenet dátuma található. A pozitív értékek jelezheti a jövőben esedékes, valamint a negatív értékek múltbeli dátumok.</td>
<td>
<ul>
<li><strong>Elmúlt 30 nap</strong> – Írja be <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>Az elmúlt 30 nap, és a következő 30 nap</strong> – Írja be <strong>(DayRange(-30,30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>A megadott relatív dátum után minden dátumra található.</td>
<td>
<ul>
<li><strong>Több mint 30 nap múlva</strong> – Írja be <strong>(GreaterThanDate(30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow ()</td>
<td>Az összes dátum/idő bejegyzés található a mostani idő utánra.</td>
<td>
<ul>
<li><strong>Az összes jövőbeni dátumot és időpontot</strong> – Írja be <strong>(GreaterThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>A megadott relatív dátum előtt minden dátumra található.</td>
<td>
<ul>
<li><strong>Kisebb, mint hét nap múlva</strong> – Írja be <strong>(LessThanDate(7))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow ()</td>
<td>Az összes dátum/idő bejegyzés található a mostani idő utánra.</td>
<td>
<ul>
<li><strong>Minden korábbi dátum/időpont</strong> – Írja be <strong>(LessThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>A dátumtartomány alapján hónapok az aktuális hónap képest található.</td>
<td>
<ul>
<li><strong>Megelőző két hónap</strong> – Írja be <strong>(MonthRange(-2,0))</strong>.</li>
<li><strong>Következő három hónap</strong> – Írja be <strong>(MonthRange(0,3))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>A dátumtartomány alapján hónapok az aktuális hónap képest található.</td>
<td>
<ul>
<li><strong>Következő év</strong> – Írja be <strong>(YearRange(0, 1))</strong>.</li>
<li><strong>Előző év</strong> – Írja be <strong>(YearRange(-1,0))</strong>.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]