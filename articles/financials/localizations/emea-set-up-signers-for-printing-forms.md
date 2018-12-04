---
title: "Aláírók beállítása nyomtatási űrlapokhoz"
description: "A Cseh Köztársaság, Észtország, Magyarország, Litvánia, Lettország, Lengyelország és Oroszország területén működő jogalanyok esetén beállíthat aláírókat és beosztásokat a dokumentumokat, például számlákat és készpénzutalványokat nyomtató szállítók és vevők számára."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 263464
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 51449f2f8448a493ebf7e4496cebdb90d902869a
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-signers-for-print-forms"></a>Aláírók beállítása nyomtatási űrlapokhoz

[!include [banner](../includes/banner.md)]

A Cseh Köztársaság, Észtország, Magyarország, Litvánia, Lettország, Lengyelország és Oroszország területén működő jogalanyok esetén beállíthat aláírókat és beosztásokat a dokumentumokat, például számlákat és készpénzutalványokat nyomtató szállítók és vevők számára.

<a name="set-up-default-values"></a>Alapértelmezett értékek beállítása
---------------------

Aláírók megadásához egy vállalat által kinyomtatott dokumentumokhoz használja a **Tisztviselők** oldalt. Beállíthat aláírókat és a beosztásaikat mind a vállalat, mind a vevők vagy szállítók számára, a dokumentum típusától függően. Az alábbi táblázat ismerteti a **Tisztviselők** oldalon elérhető lapokat.

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
<td>Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz (igazgató és főkönyvelő), akik az összes típusú dokumentumot aláírhatják.</td>
</tr>
<tr class="even">
<td>Főkönyv</td>
<td>Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő, pénzforgalomhoz kapcsolódó belső pénzügyi dokumentumokat írhatják alá:
<ul>
<li>Pénztárbizonylatok</li>
<li>Előzetes jelentés</li>
<li>Pénztárbizonylati oldal</li>
<li>Számlálási kivonat</li>
<li>Halasztások<em></li>
</ul></td>
</tr>
<tr class="odd">
<td>Értékesítési rendelések</td>
<td>Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő, vevőkhöz kapcsolódó, kimenő elsődleges dokumentumokat írhatják alá:
<ul>
<li>Kifizetendő számla</em></li>
<li>Számla</li>
<li>Számviteli számla<em></li>
<li>Számla - jóváírás</li>
<li>Számviteli számla - jóváírás</em></li>
<li>Adótranzakció - pénzügyi dokumentum (ügyfél)<em></li>
</ul></td>
</tr>
<tr class="even">
<td>Beszerzési rendelések</td>
<td>Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő, szállítókhoz kapcsolódó, bejövő elsődleges dokumentumokat írhatják alá:
<ul>
<li>Számla</li>
<li>Számviteli számla</em></li>
<li>Számla - jóváírás</li>
<li>Számviteli számla - jóváírás<em></li>
<li>Kifizetendő számla</em></li>
<li>Adótranzakció - pénzügyi dokumentum (szállító)<em></li>
</ul></td>
</tr>
<tr class="odd">
<td>Készletcikk kezelése</td>
<td>Adjon hozzá beosztásokat és kapcsolódó információkat az aláírókhoz, akik a következő raktározási bizonylatokat írhatják alá, amikor materiális eszköz kiadására kerül sor vevő részére vagy bevételezésére szállítótól:
<ul>
<li>Kiadási bizonylat értékesítési rendeléshez (M-15)</em></li>
<li>Bevételezési pénztárbizonylat / befizetési utalvány</li>
<li>Kiadási bizonylat átmozgatási rendeléshez (M-15)*</li>
</ul></td>
</tr>
</tbody>
</table>

\* (Ez az dokumentumtípus csak a oroszországi elsődleges címmel rendelkező jogi személyek számára elérhető.) Az alábbi táblázat ismerteti a **Tisztviselők** oldalon elérhető mezőket.

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
<td>Válassza ki az aláíró beosztását.</td>
</tr>
<tr class="even">
<td>Név</td>
<td>Válassza ki az aláíró nevét. A listán szereplő nevek vagy a Kapcsolattartók táblából, vagy az Alkalmazottak táblából származnak az aláíró típusától függően (ez azt jelenti, attól függően, hogy az <strong>A mi</strong> jelölőnégyzet be van-e jelölve). Ha az aláíró neve nem szerepel a listában, manuálisan adja meg az aláíró teljes nevét.</td>
</tr>
<tr class="odd">
<td>Beosztás</td>
<td>Válassza ki az aláíró munkabeosztását. Ha az aláíró beosztása nem szerepel a listában, manuálisan adja meg az aláíró beosztását.</td>
</tr>
<tr class="even">
<td>Számlakód</td>
<td>Válassza ki, hogy az aláíró aláírhatja-e a kiválasztott dokumentumtípus összes dokumentumát, vagy csak egy adott vevő vagy szállító dokumentumait.</td>
</tr>
<tr class="odd">
<td>Számlakapcsolat</td>
<td>Válassza ki a vevői vagy szállítói számlát, amely a kijelölt számlakódhoz kapcsolódik. Ez a mező csak akkor érhető el, ha a <strong>Rekord</strong> lehetőséget választja a <strong>Számlakód</strong> mezőben.</td>
</tr>
<tr class="even">
<td>A mi</td>
<td>A bejelölt jelölőnégyzet azt jelzi, hogy a pozíció belső.</td>
</tr>
<tr class="odd">
<td>Hozzárendelés raktárhoz</td>
<td>Válassza ki, hogy az aláíró az összes raktárhoz hozzá van-e rendelve, vagy csak egy adott raktárhoz. Az alábbi lehetőségek közül választhat:
<ul>
<li><strong>Minden</strong> – az aláíró az összes raktárhoz hozzá van rendelve.</li>
<li><strong>Rekord</strong> – az aláíró adott raktárhoz van hozzárendelve.</li>
</ul></td>
</tr>
<tr class="even">
<td>Raktár</td>
<td>Válassza ki a raktárkódot, amely megfelel annak a raktárnak, amelyhez az aláíró hozzá van rendelve. Ez a mező csak akkor érhető el, ha a <strong>Rekord</strong> lehetőséget választja a <strong>Hozzárendelés raktárhoz</strong> mezőben.</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-number-sequence-code-for-officials"></a>Állítsa be a hivatalnokok számsorozatkódját
Hivatalnokokhoz számsorozatkódot a **Számsorozatok** részben rendelhet hozzá a **Jogi személyek** oldalon. Válasszon ki egy számsorozatkódot a **Hivatalnokok munkamenet-azonosítója** hivatkozáshoz.

## <a name="modify-signers-in-primary-documents"></a>Elsődleges dokumentumok aláíróinak módosítása
A Hivatalnokok funkció az előre definiált alapértelmezett aláírókat a Hivatalnokok táblából mutatja. A **Számla feladása** oldalon a **Hivatalnokok** lapon módosíthatja az aláíró nevét és beosztását az elsődleges dokumentumon a következő dokumentumtípusoknál:

-   Vevői számla
-   Szállítói számla
-   Átmozgatási rendelések szállítása
-   Készpénzutalvány

**Megjegyzés:** Könyvelt bizonylatoknál a hivatalnokokat nem lehet szerkeszteni.




