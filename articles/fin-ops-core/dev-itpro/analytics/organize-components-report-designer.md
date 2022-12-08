---
title: Jelentés-összetevők rendezése a jelentéstervezőben
description: Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a94a88114072792243026e441e6c5a62ee80fc56
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802688"
---
# <a name="organize-report-components-in-report-designer"></a>Jelentés-összetevők rendezése a jelentéstervezőben

[!include [banner](../includes/banner.md)]

Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket. Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.

A jelentéstervezőben mappákat, jelentéseket, tömböket és más objektumokat átnevezhet, hogy a fájlokat rendszerezze. Attól függően, hogy milyen típusú objektumot nevez át, előfordulhat, hogy frissítenie kell az objektummal kapcsolatos társításokat.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Mappa vagy épületblokk átnevezése a Jelentéstervezőben
A Jelentéstervezőben átnevezhetők a mappák, a jelentésdefiníciók, a sordefiníciók, az oszlopdefiníciók és a jelentési fa definíciói.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Mappa vagy épületblokk átnevezése a Jelentéstervezőben

1. A Jelentéstervezőben a navigációs ablakban keresse meg az átnevezni kívánt mappát vagy objektumot.
2. Kattintson jobb gombbal a mappára vagy az objektumra, és kattintson a **Átnevezésre**. A navigációs ablakban lévő **Név** mező elérhetővé válik.
3. Írja be az új nevet, majd nyomja le az **Entert**.
4. Ha az építőelem egy sordefiníció, oszlopdefiníció vagy jelentési fa definíció, akkor frissítenie kell a többi építőelemet, amelyek társítva vannak hozzá. Kattintson jobb gombbal arra az építőelemre, amelyet a 3. lépésben átnevezett, válassza ki a **Társítások** lehetőséget, majd válasszon ki egy cikket a listában, hogy frissítse.
5. Ismételje meg a 4. lépést addig, amíg be nem fejeződik az összes kapcsolódó elem frissítése.

## <a name="create-and-manage-report-groups"></a>Jelentés csoportok létrehozása és kezelése
Ezzel egy időben a jelentésdefiníciókat csoportosíthatja több jelentés készítése érdekében. Jelentéscsoportok létrehozásához, módosításához, törléséhez és készítéséhez tervező vagy rendszergazda szerepkörrel kell rendelkeznie. A jelentéskészítő szerepkörrel rendelkező felhasználók létrehozhatnak jelentéscsoportokat, és módosíthatják a felhasználók jelentéscsoportokhoz tartozó jelentésdefinícióinak beállítását.

### <a name="create-a-report-group"></a>Jelentés csoport létrehozása

1. A Jelentéstervező navigációs ablakában kattintson a Jelentéscsoportok **elemre**.
2. A Fájl **menü** Új jelentéscsoport-definíció **·** &gt; **parancsára** kattintva új jelentéscsoportot nyit meg a megjelenítő ablakban. Másik lehetőségként kattintson a Jelentéscsoport **csoport** gombra ![.](media/report-group.gif "Jelentéscsoport") elemre az eszköztáron.
3. Kattintson a Jelentéscsoport **fülre** . Ha felül szeretné bírálni a jelentés generálásakor az egyes jelentésdefiníciókban található adatokat, **jelölje be a Vállalat felülbírálása, a részletesség és a dátum beállításait az egyes jelentésdefiníciók** jelölőnégyzetében. A vállalat nevét, a részletezési szintet, az ideiglenes beállítást és dátum információkat automatikusan feltölti a rendszer, de végezhet rajtuk frissítéseket.
4. Ha több jelentést is létre kell hozni a jelentési pénznemekkel, jelölje be **az Összes jelentési pénznem megjelenítése jelölőnégyzetet** . Ezután több nézethez férhet hozzá, ha a **Pénznem** gombra kattint a böngészőben, a jelentés megtekintésekkor.
5. A **Jelentések a csoportban** mezőben, kattintson a **Hozzáadás** gombra a jelentéscsoportba felvenni kívánt jelentések kiválasztásához. Több jelentés kijelöléséhez a **Hozzáadás** párbeszédablakban, tartsa lenyomva a Ctrl billentyűt, miközben kiválasztja az elemeket. Befejezése után jelölje ki a jelentéseket, és kattintson az **OK** gombra.
6. Kattintson a **Fájl** &gt; **Mentés** elemre az új jelentéscsoport mentéséhez.

### <a name="modify-a-report-group"></a>Jelentéscsoport módosítása

1. A Jelentéstervező navigációs ablakában kattintson a Jelentéscsoportok **elemre**.
2. Kattintson duplán a módosítani kívánt jelentéscsoportra.
3. A Jelentéscsoport **lapon** tegye meg a kívánt módosításokat.
4. A **Fájl** menüben kattintson a **Mentés** lehetőségre a módosított jelentéscsoport mentéséhez, vagy kattintson a **Mentés** gombra ![Mentés.](media/save.gif "Mentés") elemre az eszköztáron.

> [NOTE] Ha úgy ütemezte a jelentéseket, hogy meghatározott időközönként generálja őket, akkor ezeket a beállításokat felülbírálhatja, és azonnal jelentést generálhat.

### <a name="generate-a-report-group-report"></a>Jelentéscsoportról szóló jelentés készítése

1. A Jelentéstervező navigációs ablakában kattintson a Jelentéscsoportok **elemre**.
2. Nyissa meg a jelentéscsoportot a jelentés készítéséhez.
3. Kattintson a Jelentés **létrehozása** gombra a ![Jelentés létrehozása gombra.](media/generate-report.gif "Jelentés létrehozása") jelentések készítéséhez.

### <a name="delete-a-report-group"></a>Jelentéscsoport törlése

1. A Jelentéstervező navigációs ablakában kattintson a Jelentéscsoportok **elemre**.
2. A törléshez kattintson jobb gombbal a jelentés csoportra, és válassza **Törlés** lehetőséget.
3. Ha egy megerősítő üzenet jelenik meg, kattintson az **Igen** gombra.

## <a name="report-group-tab-controls"></a>Jelentéscsoport lap vezérlőelemei
Az alábbi táblázat leírja a Jelentéscsoport lap **vezérlőelemét** .

<table>
<thead>
<tr>
<th>Vezérlő</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Az egyéni jelentésdefiníciókban szereplő vállalati, részlet- és dátumbeállítások felülbírálása</td>
<td>Jelölje be ezt a jelölőnégyzetet, ha felül szeretné bírálni a jelentéscsoport jelentésdefinícióit kizárólag az ilyen jelentések létrehozása esetén.</td>
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
<td>Itt megjelenik minden további jelentési pénznem, amely a Microsoft Dynamics 365 pénzügyi rendszerben be van állítva. Jelölje be ezt a jelölőnégyzetet, ha a megadott pénznemekben további jelentéseket is létre kell hoznia. Ezen jelentések megtekinthetők a Web Viewer eszközben, ha a <strong>Pénznem</strong> gombra kattint és kiválaszt egy pénznemet.</td>
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
