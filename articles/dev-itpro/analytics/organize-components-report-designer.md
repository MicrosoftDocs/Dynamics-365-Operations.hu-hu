---
title: Jelentés-összetevők rendezése a jelentéstervezőben
description: Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket. Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3f2b34cccfd84a9e4bb76e7a1da64e5cefa9982e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "323939"
---
# <a name="organize-report-components-in-report-designer"></a>Jelentés-összetevők rendezése a jelentéstervezőben

[!include [banner](../includes/banner.md)]

Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket. Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.

Átnevezheti a mappákat, jelentéseket, építőelemeket és más objektumokat jelentéstervezőben a fájlok rendszerezése érdekében. Attól függően, hogy milyen típusú objektumot nevez át, előfordulhat, hogy frissítenie kell az objektummal kapcsolatos társításokat.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Nevezze át a mappát vagy az építőelemet a Jelentés Tervezőben
A Report Designer eszközben átnevezheti a mappákat, valamint a jelentés-, sor-, oszlop- és jelentésfa-definíciókat is.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Mappa vagy építőelem átnevezése a Report Designer eszközben

1. A Report Designer alkalmazás navigációs ablaktábláján keresse meg az átnevezni kívánt mappát vagy objektumot.
2. Kattintson jobb gombbal a mappára vagy az objektumra, és kattintson a **Átnevezésre**. A navigációs ablakban lévő **Név** mező elérhetővé válik.
3. Írja be az új nevet, majd nyomja le az Entert.
4. Ha az építőelem egy sordefiníció, oszlopdefiníció vagy jelentési fa definíció, akkor frissítenie kell a többi építőelemet, amelyek társítva vannak hozzá. Kattintson jobb gombbal arra az építőelemre, amelyet a 3. lépésben átnevezett, válassza ki a **Társítások** lehetőséget, majd válasszon ki egy cikket a listában, hogy frissítse.
5. Ismételje meg a 4. lépést addig, amíg be nem fejeződik az összes kapcsolódó elem frissítése.

## <a name="create-and-manage-report-groups"></a>Jelentés csoportok létrehozása és kezelése
Ezzel egy időben a jelentésdefiníciókat csoportosíthatja több jelentés készítése érdekében. Jelentéscsoportok létrehozásához, módosításához, törléséhez és készítéséhez tervező vagy rendszergazda szerepkörrel kell rendelkeznie. A jelentéskészítő szerepkörrel rendelkező felhasználók létrehozhatnak jelentéscsoportokat, és módosíthatják a felhasználók jelentéscsoportokhoz tartozó jelentésdefinícióinak beállítását.

### <a name="create-a-report-group"></a>Jelentés csoport létrehozása

1. A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2. A **Fájl** menüben kattintson az **Új** &gt; **Jelentéscsoport-definíció** lehetőségre, hogy megnyisson egy új jelentéscsoportot a megjelenítő ablakban. Másik lehetőségként kattintson a **Jelentéscsoport** gombra ![Jelentéscsoport](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Jelentéscsoport") az eszköztáron.
3. Kattintson a **Jelentéscsoport** lapra. Ha felül szeretné bírálni ennek a jelentés létrehozásának egyes jelentésdefinícióban lévő információkat, jelölje be a **Az egyes jelentésdefiníciókból a vállalat, adat és dátumbeállítások felülbírálása** jelölőnégyzetet. A vállalat nevét, a részletezési szintet, az ideiglenes beállítást és dátum információkat automatikusan feltölti a rendszer, de végezhet rajtuk frissítéseket.
4. Több jelentés létrehozásához, amelyek megmutatják a jelentési pénznemeket válassza ki a **Minden jelentési pénznem szerepeltetése** jelölőnégyzetet. Ezután több nézethez férhet hozzá, ha a **Pénznem** gombra kattint a böngészőben, a jelentés megtekintésekkor.
5. A **Jelentések a csoportban** mezőben, kattintson a **Hozzáadás** gombra a jelentéscsoportba felvenni kívánt jelentések kiválasztásához. Több jelentés kijelöléséhez a **Hozzáadás** párbeszédablakban, tartsa lenyomva a Ctrl billentyűt, miközben kiválasztja az elemeket. Befejezése után jelölje ki a jelentéseket, és kattintson az **OK** gombra.
6. Kattintson a **Fájl** &gt; **Mentés** elemre az új jelentéscsoport mentéséhez.

### <a name="modify-a-report-group"></a>Jelentéscsoport módosítása

1. A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2. Kattintson duplán a módosítani kívánt jelentéscsoportra.
3. A **Jelentéscsoport** lapon, végezze el a kívánt módosításokat.
4. A **Fájl** menüben kattintson a **Mentés** lehetőségre a módosított jelentéscsoport mentéséhez, vagy kattintson a **Mentés** gombra ![Mentés](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Mentés") az eszköztáron.

> [MEGJEGYZÉS] Ha meghatározott időközönként létrehozott jelentéseket ütemezett, felülírhatja ezeket a beállításokat, és azonnal jelentéseket készíthet.

### <a name="generate-a-report-group-report"></a>Jelentéscsoportról szóló jelentés készítése

1. A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2. Nyissa meg a jelentéscsoportot a jelentés készítéséhez.
3. Kattintson a **Jelentés készítése** gombra ![Jelentés készítése](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Jelentés készítése") jelentések készítéséhez.

### <a name="delete-a-report-group"></a>Jelentéscsoport törlése

1. A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.
2. A törléshez kattintson jobb gombbal a jelentés csoportra, és válassza **Törlés**lehetőséget.
3. Ha egy megerősítő üzenet jelenik meg, kattintson az **Igen** gombra.

## <a name="report-group-tab-controls"></a>Jelentéscsoport-lap vezérlők
Az alábbi táblázat ismerteti a **Jelentéscsoport** lap vezérlőit.

<table>
<thead>
<tr>
<th>Vezérlő</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Az egyes jelentésdefiníciókból a vállalat-, adat- és dátumbeállítások felülbírálása</td>
<td>Jelölje be ezt a jelölőnégyzetet, ha felül szeretné bírálni a jelentések egyéni jelentésdefinícióit a csak ezeknek a jelentéseknek az előállítására szolgáló jelentéscsoportban.</td>
</tr>
<tr>
<td>Vállalat neve</td>
<td>A jelentésekhez használt vállalat kiválasztása.</td>
</tr>
<tr>
<td>Részletezési szint</td>
<td>Adja meg, hogy milyen részletes jelentést szeretne készíteni.
<ul>
<li><strong>Pénzügyi</strong> − Átfogó összefoglaló jelentés. Nem lehet számlákra és dimenziókra lebontani, kivéve az olyan számláknál és dimenzióknál, amelyeket a jelentési fán keresztül adtak hozzá.</li>
<li><strong>Pénzügy és Számla</strong> – Egy jelentés, amely átfogó összegzést és részletes számlaadatokat tartalmaz.</li>
<li><strong>Pénzügy, Számla és Tranzakció</strong> – Egy jelentés, amely átfogó összegzést és a tranzakció részletes adatait tartalmazza.</li>
</ul></td>
</tr>
<tr>
<td>Fedezetek</td>
<td>Adja meg, hogy milyen típusú tevékenységeket tartalmazzon a jelentés.
<ul>
<li><strong>Csak feladott tevékenység</strong> − Csak a pénzügyi adatokba feladott tranzakciókat és egyenlegeket tartalmazza.</li>
<li><strong>Feladott és fel nem adott tevékenység</strong> − A pénzügyi adatokba felvett és feladott összes tranzakciót és egyenleget tartalmazza.</li>
<li><strong>Csak feladatlan tevékenység</strong> − Csak a pénzügyi adatokba felvett, de még fel nem adott tranzakciókat tartalmazza.</li>
</ul></td>
</tr>
<tr>
<td>Minden jelentési pénznemmel együtt</td>
<td>Bármely további jelentési pénznem, amely be van állítva a Microsoft Dynamics ERP rendszeréhez itt kerül felsorolásra. Jelölje ki ezt a jelölőnégyzetet, hogy további jelentéseket hozzon létre a jelölt pénznemekkel. Ezen jelentések megtekinthetők a Web Viewer eszközben, ha a <strong>Pénznem</strong> gombra kattint és kiválaszt egy pénznemet.</td>
</tr>
<tr>
<td>A dátummal kapcsolatos adatok mentése nem történik meg a jelentésdefiníciójával</td>
<td><ul>
<li>Bázisidőszak</li>
<li>Bázisév</li>
<li>Érintett időszakok</li>
</ul>
Csak az alapértelmezett alapidőszak beállításainak mentése történik a jelentésdefinícióval.</td>
</tr>
<tr>
<td>A dátummal kapcsolatos adatok mentődnek a jelentésdefiníciójával</td>
<td><ul>
<li>Jelentés dátuma</li>
<li>Alapértelmezett alap időtartam</li>
</ul></td>
</tr>
<tr>
<td>Jelentések a csoportokban</td>
<td>Jelentések hozzáadása, eltávolítása és újrarendezése jelentéscsoportban.
<ul>
<li>Ha jelentésdefiníciókat szeretne adni a jelentéscsoporthoz, dupla kattintással nyissa meg a csoportot, majd kattintson a <strong>Hozzáadás</strong> parancsra. Jelölje ki a jelentéscsoportba felvenni kívánt jelentéseket, majd kattintson az <strong>OK</strong> gombra.</li>
<li>Ha szeretne eltávolítani egy jelentést a jelentéscsoportból, jelölje ki, majd kattintson az <strong>Eltávolítás</strong> parancsra.</li>
<li>A létrehozott jelentések sorrendjének módosításához válasszon ki a listából egy jelentést, majd kattintson <strong>Mozgatás felfelé</strong> vagy <strong>Mozgatás lefelé</strong> gombra.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)
