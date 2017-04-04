---
title: "Állítsa be a nyomtatási űrlapokhoz aláírók"
description: "A Cseh Köztársaság, Észtország, Magyarország, Litvánia, Lettország, Lengyelország és Oroszország jogalanyok állíthat be aláírók és a nyomtatott dokumentumok, például számlák és készpénz rendelések szállítók és vevők számára."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 263464
ms.assetid: 7213914a-ecb6-4711-99fe-4e11867aaf4d
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 45d2facde1e5502f4a5863863554a486916c26cd
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-signers-for-print-forms"></a>Állítsa be a nyomtatási űrlapokhoz aláírók

A Cseh Köztársaság, Észtország, Magyarország, Litvánia, Lettország, Lengyelország és Oroszország jogalanyok állíthat be aláírók és a nyomtatott dokumentumok, például számlák és készpénz rendelések szállítók és vevők számára.

<a name="set-up-default-values"></a>Alapértelmezett értékek beállítása
---------------------

A dokumentumok, amely egy vállalatot nyomtat aláírók megadásához használja a **tisztviselői** oldalon. A vállalat és a vevők vagy szállítók, a dokumentum típusától függően állíthat be aláírók és a címben. Az alábbi táblázat ismerteti a lapok a **tisztviselői** oldalon.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lap</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Általános</td>
<td>Pozíciók és a kapcsolódó információkat aláírók (igazgatója és vezető könyvelő) aki aláírhatja az összes típusú dokumentumok.</td>
</tr>
<tr class="even">
<td>Főkönyv</td>
<td>A pozíció és a vonatkozó információt az aláírók, akik is a következő belső pénzügyi dokumentumok aláírására, amelyek kapcsolódnak a cash flow hozzáadása:
<ul>
<li>Pénztárbizonylatok</li>
<li>Előzetes jelentés</li>
<li>Pénztárbizonylati oldal</li>
<li>Számlálási kivonat</li>
<li>Halasztások *</li>
</ul></td>
</tr>
<tr class="odd">
<td>Értékesítési rendelések</td>
<td>Az aláírók, akik a következő kimenő elsődleges dokumentumokat, amelyek kapcsolódnak a felhasználók bejelentkezhetnek pozíciók és kapcsolatos információ hozzáadása:
<ul>
<li>Számla fizetési *</li>
<li>Számla</li>
<li>Számviteli számla *</li>
<li>Számla - jóváírás</li>
<li>Számviteli számla - jóváírás-Megjegyzés: *</li>
<li>Adótranzakció-pénzügyi dokumentum (ügyfél) *</li>
</ul></td>
</tr>
<tr class="even">
<td>Beszerzési rendelések</td>
<td>Beosztások és kapcsolatos információk az aláírók, akik bejelentkezhetnek a következő bejövő elsődleges dokumentumokat, amelyek kapcsolódnak a Szállítók hozzáadása:
<ul>
<li>Számla</li>
<li>Számviteli számla *</li>
<li>Számla - jóváírás</li>
<li>Számviteli számla - jóváírás-Megjegyzés: *</li>
<li>Számla fizetési *</li>
<li>Adótranzakció-pénzügyi dokumentum (szállító) *</li>
</ul></td>
</tr>
<tr class="odd">
<td>Készletcikk kezelése</td>
<td>Adja hozzá a pozíciók és kapcsolatos információk az aláírók, akik a következő raktározási bizonylatok aláírhatja, ha egy vevő részére kiállított vagy a szállítótól kapott tárgyi eszközök:
<ul>
<li>Kiadási bizonylat értékesítési rendeléshez (M-15) *</li>
<li>RMB. Pénztárbizonylat vagy befizetési rendelés</li>
<li>Kiadási bizonylat átmozgatási rendeléshez (M-15) *</li>
</ul></td>
</tr>
</tbody>
</table>

\*A Bizonylattípus jogalanyokat, amelyek az elsődleges cím Oroszországban érhető el. Az alábbi táblázat ismerteti a mezőket a **tisztviselői** oldalon.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pozíció</td>
<td>Jelölje ki az aláíró postai címét.</td>
</tr>
<tr class="even">
<td>Név</td>
<td>Válassza ki az aláíró nevét. A listán szereplő neveket származik, a Névjegyalbum táblázat vagy az alkalmazottak tábla aláíró típusától függően (Ez azt jelenti, attól függően, hogy a <strong>a</strong> jelölőnégyzet be van jelölve). Ha az aláíró neve nem szerepel a listában, manuálisan adja meg az aláíró teljes neve.</td>
</tr>
<tr class="odd">
<td>Beosztás</td>
<td>Válassza ki az aláíró beosztása. Az aláíró cím nem szerepel a listán, ha kézzel írja be az aláíró címét.</td>
</tr>
<tr class="even">
<td>Számlakód</td>
<td>Válassza ki, hogy az aláíró aláírhatja a kiválasztott dokumentumtípus az összes dokumentum vagy dokumentumok csak egy adott vevő vagy szállító.</td>
</tr>
<tr class="odd">
<td>Számlakapcsolat</td>
<td>A kijelölt számla kód kapcsolódó vevői vagy szállítói számla kiválasztása. Ez a mező akkor érhető el, csak ha bejelöli <strong>rekord</strong> a a <strong>Számlakód</strong> mezőben.</td>
</tr>
<tr class="even">
<td>A mi</td>
<td>A bejelölt négyzet azt jelzi, hogy a pozíció belső.</td>
</tr>
<tr class="odd">
<td>Hozzárendelés raktárhoz</td>
<td>Válassza ki, hogy az aláíró összes raktár vagy csak egy adott raktár van rendelve. Az alábbi lehetőségek közül választhat:
<ul>
<li><strong>Minden</strong> – az aláíró összes raktár van rendelve.</li>
<li><strong>Rekord</strong> – az aláíró hozzá van rendelve egy adott raktár.</li>
</ul></td>
</tr>
<tr class="even">
<td>Raktár</td>
<td>Jelölje be a raktár kódja, amely megfelel a raktározásnak, hogy az aláíró hozzá van rendelve. Ez a mező akkor érhető el, csak ha bejelöli <strong>rekord</strong> a a <strong>társítás a raktári</strong> mezőben.</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-number-sequence-code-for-officials"></a>Tisztviselők számsorozatkód beállítása
Tisztviselők hozzárendelheti egy számsorozat kódja az **Number sequences** része a **jogi személyek** lap. A számsorozatkód kiválasztása a **Hivatalnokok munkamenet-azonosítója** hivatkozás.

## <a name="modify-signers-in-primary-documents"></a>Aláírók elsődleges dokumentumok módosítása
A tisztviselők funkciókat jeleníti meg az előre definiált alapértelmezett aláírók a tisztviselők táblából. A a **számla feladása** a lap a **tisztviselők** lapon módosíthatja az aláíró neve és címe a következő dokumentumtípusok elsődleges dokumentum:

-   Vevői számla
-   Szállítói számla
-   Átmozgatási rendelések szállítása
-   Készpénzutalvány

**Megjegyzés:** a bizonylat könyvelése után nem lehet szerkeszteni a tisztviselők.


