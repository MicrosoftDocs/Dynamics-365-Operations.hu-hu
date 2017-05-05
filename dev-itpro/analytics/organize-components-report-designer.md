---
title: "Jelentés-összetevők rendezése a jelentéstervezőben"
description: "Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket. Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-07 19 - 06 - 25
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Management Reporter, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: c8efd57805cd89eb8cdfabe81a60704bb4390194
ms.lasthandoff: 03/29/2017


---

# <a name="organize-report-components-in-report-designer"></a>Jelentés-összetevők rendezése a jelentéstervezőben

Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket. Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.

Átnevezheti a mappákat, jelentéseket, építőelemeket és más objektumokat jelentéstervezőben a fájlok rendszerezése érdekében. Attól függően, hogy milyen típusú objektumot nevez át, előfordulhat, hogy frissítenie kell az objektummal kapcsolatos társításokat.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Nevezze át a mappát vagy az építőelemet a Jelentés Tervezőben
A Jelentés Tervezőben átnevezheti a mappákat, a jelentésdefinicókat, sor meghatározásokat, az oszlopdefiníciókat és a szervezeti diagram meghatározásokat. **Megjegyzés:** Építőelem átnevezésekor frissítenie kell minden jelentési definíciót, amely azt az építőelemet használja. Ellenkező esetben nem hozható létre új jelentés.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Nevezze át a mappát vagy az építőelemet a Jelentés Tervezőben

1.  A Jelentés Tervezőben használja a navigációs ablakot a mappa megkeresésére vagy az objektum átnevezésére.
2.  Kattintson jobb gombbal a mappára vagy az objektumra, és kattintson a **Átnevezésre**. A navigációs ablakban lévő **Név** mező elérhetővé válik.
3.  Írja be az új nevet, majd nyomja le az Entert.
4.  Ha az építőelem egy sordefiníció, oszlopdefiníció vagy jelentési fa definíció, akkor frissítenie kell a többi építőelemet, amelyek társítva vannak hozzá. Kattintson jobb gombbal arra az építőelemre, amelyet a 3. lépésben átnevezett, válassza ki a **Társítások** lehetőséget, majd válasszon ki egy cikket a listában, hogy frissítse.
5.  Ismételje meg a 4. lépést addig, amíg be nem fejeződik az összes kapcsolódó elem frissítése.

## <a name="create-and-manage-report-groups"></a>Jelentés csoportok létrehozása és kezelése
Ezzel egy időben a jelentésdefiníciókat csoportosíthatja több jelentés készítése érdekében. Jelentéscsoportok létrehozásához, módosításához, törléséhez és készítéséhez tervező vagy rendszergazda szerepkörrel kell rendelkeznie. A jelentéskészítő szerepkörrel rendelkező felhasználók létrehozhatnak jelentéscsoportokat, és módosíthatják a felhasználók jelentéscsoportokhoz tartozó jelentésdefinícióinak beállítását.

### <a name="create-a-report-group"></a>Jelentés csoport létrehozása

1.  A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2.  A **Fájl** menüben kattintson az **Új** &gt; **Jelentéscsoport-definíció** lehetőségre, hogy megnyisson egy új jelentéscsoportot a megjelenítő ablakban. Másik lehetőségként kattintson a **Jelentéscsoport** gombra ![Jelentéscsoport](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Jelentéscsoport") az eszköztáron.
3.  Kattintson a **Jelentés Csoport** lapra. Ha felül szeretné bírálni ennek a jelentés létrehozásának egyes jelentésdefinícióban lévő információkat, jelölje be a **Az egyes jelentésdefiníciókból a vállalat, adat és dátumbeállítások felülbírálása** jelölőnégyzetet. A vállalat nevét, a részletezési szintet, az ideiglenes beállítást és dátum információkat automatikusan feltölti a rendszer, de végezhet rajtuk frissítéseket.
4.  Több jelentés létrehozásához, amelyek megmutatják a jelentési pénznemeket válassza ki a **Minden jelentési pénznem szerepeltetése** jelölőnégyzetet. Ezután több nézethez férhet hozzá, ha a **Pénznem** gombra kattint a böngészőben, a jelentés megtekintésekkor.
5.  A **Jelentések a csoportban** mezőben, kattintson a **Hozzáadás** gombra a jelentéscsoportba felvenni kívánt jelentések kiválasztásához. Több jelentés kijelöléséhez a **Hozzáadás** párbeszédablakban, tartsa lenyomva a Ctrl billentyűt, miközben kiválasztja az elemeket. Befejezése után jelölje ki a jelentéseket, és kattintson az **OK** gombra.
6.  Kattintson a **Fájl** &gt; **Mentés** elemre az új jelentéscsoport mentéséhez.

### <a name="modify-a-report-group"></a>Jelentéscsoport módosítása

1.  A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2.  Kattintson duplán a módosítani kívánt jelentéscsoportra.
3.  A **Jelentéscsoport** lapon, végezze el a kívánt módosításokat.
4.  A **Fájl** menüben kattintson a **Mentés** lehetőségre a módosított jelentéscsoport mentéséhez, vagy kattintson a **Mentés** gombra ![Mentés](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Mentés") az eszköztáron.

**Megjegyzés:** Ha meghatározott időközönként létrehozott jelentéseket ütemezett, felülírhatja ezeket a beállításokat, és azonnal jelentéseket készíthet.

### <a name="generate-a-report-group-report"></a>Jelentéscsoportról szóló jelentés készítése

1.  A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2.  Nyissa meg a jelentéscsoportot a jelentés készítéséhez.
3.  Kattintson a **Jelentés készítése** gombra ![Jelentés készítése](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Jelentés készítése") jelentések készítéséhez.

### <a name="delete-a-report-group"></a>Jelentéscsoport törlése

1.  A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2.  A törléshez kattintson jobb gombbal a jelentés csoportra, és válassza **Törlés**lehetőséget.
3.  Ha egy megerősítő üzenet jelenik meg, kattintson az **Igen** gombra.

## <a name="report-group-tab-controls"></a>Jelentéscsoport-lap vezérlők
Az alábbi táblázat ismerteti a **Jelentéscsoport** lap vezérlőit.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Vezérlő</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Az egyes jelentésdefiníciókból a vállalat-, adat- és dátumbeállítások felülbírálása</td>
<td>Jelölje be ezt a jelölőnégyzetet, ha felül szeretné bírálni a jelentések egyéni jelentésdefinícióit a csak ezeknek a jelentéseknek az előállítására szolgáló jelentéscsoportban.</td>
</tr>
<tr class="even">
<td>Vállalat neve</td>
<td>A jelentésekhez használt vállalat kiválasztása.</td>
</tr>
<tr class="odd">
<td>Részletezési szint</td>
<td>Adja meg, hogy milyen részletes jelentést szeretne készíteni.
<ul>
<li><strong>Pénzügyi</strong>− Átfogó és összegző jelentés. Nem lehet számlákra és dimenziókra lebontani, kivéve az olyan számláknál és dimenzióknál, amelyeket a jelentési fán keresztül adtak hozzá.</li>
<li><strong>Pénzügy és Számla</strong> – Egy jelentés, amely átfogó összegzést és részletes számlaadatokat tartalmaz.</li>
<li><strong>Pénzügy, Számla és Tranzakció</strong> – Egy jelentés, amely átfogó összegzést és a tranzakció részletes adatait tartalmazza.</li>
</ul></td>
</tr>
<tr class="even">
<td>Fedezetek</td>
<td>Adja meg, hogy milyen típusú tevékenységeket tartalmazzon a jelentés.
<ul>
<li><strong>Csak a feltüntetett tevékenység</strong> − Csak az olyan tranzakciókat és az egyenlegeket tartalmazza, amelyek a pénzügyi adataiban fel vannak tüntetve.</li>
<li><strong>Feltüntetett és nem feltüntetett tevékenység</strong> − Az összes tranzakció és egyenleg, amely meg van adva és fel van tüntetve a pénzügyi adataiban.</li>
<li><strong>Csak a nem feltüntetett tevékenység</strong> − Csak azokat a tranzakciókat tartalmazza, amelyek fel vannak jegyezve, de még nincsenek feltüntetve a pénzügyi adataiban.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Minden jelentési pénznemmel együtt</td>
<td>Bármely további jelentési pénznem, amely be van állítva a Microsoft Dynamics ERP rendszeréhez itt kerül felsorolásra. Jelölje ki ezt a jelölőnégyzetet, hogy további jelentéseket hozzon létre a jelölt pénznemekkel. Ezen jelentések megtekintéséhez a böngészőben kattintson a <strong>Pénznem</strong> gombra, majd válassza ki a pénznemet.</td>
</tr>
<tr class="even">
<td>A dátummal kapcsolatos adatok mentése nem történik meg a jelentésdefiníciójával</td>
<td><ul>
<li>Bázisidőszak</li>
<li>Bázisév</li>
<li>Érintett időszakok</li>
</ul>
Csak az alapértelmezett alapidőszak beállításainak mentése történik a jelentésdefinícióval.</td>
</tr>
<tr class="odd">
<td>A dátummal kapcsolatos adatok mentődnek a jelentésdefiníciójával</td>
<td><ul>
<li>Jelentés dátuma</li>
<li>Alapértelmezett alap időtartam</li>
</ul></td>
</tr>
<tr class="even">
<td>Jelentések a csoportokban</td>
<td>Jelentések hozzáadása, eltávolítása és újrarendezése jelentéscsoportban.
<ul>
<li>A jelentés csoporthoz való jelentésdefiníciók hozzáadásához, kattintson duplán a jelentéscsoport megnyitásához, és kattintson a <strong>Hozzáadásra</strong>. Válassza ki beleszámítani kívánt jelentéseket a jelentéscsoportban és kattintson az <strong>OK</strong>lehetőségre.</li>
<li>A jelentés csoportból a jelentés eltávolításához jelölje ki, és kattintson az <strong>Eltávolításra</strong>.</li>
<li>A létrehozott jelentések sorrendjének módosításához válasszon ki a listából egy jelentést, majd kattintson <strong>Mozgatás felfelé</strong> vagy <strong>Mozgatás lefelé</strong> gombra.</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Lásd még
--------

[Pénzügyi jelentéskészítés a Microsoft Dynamics 365 for Operations rendszerben](financial-reporting-intro.md)

