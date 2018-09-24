---
title: "Sordefiníciók a pénzügyi jelentéstervezőben"
description: "Egy sordefiníció egy jelentés-összetevő vagy építőelem, amely megadja az egyes sorok tartalmait egy pénzügyi jelentésben. A sordefiníciók kombinálhatóak oszlop,- jelentési fa- és jelentési definíciókkal, építőelem-csoportok létrehozásához, amelyek több vállalat által használhatóak."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: c829af1da1b3109f4687c9a2536dd156339d5c76
ms.contentlocale: hu-hu
ms.lasthandoff: 08/13/2018

---

# <a name="row-definitions-in-financial-report-designer"></a>Sordefiníciók a pénzügyi jelentéstervezőben

[!include [banner](../includes/banner.md)]

Egy sordefiníció egy jelentés-összetevő vagy építőelem, amely megadja az egyes sorok tartalmait egy pénzügyi jelentésben. A sordefiníciók kombinálhatóak oszlop,- jelentési fa- és jelentési definíciókkal, építőelem-csoportok létrehozásához, amelyek több vállalat által használhatóak.

## <a name="create-a-row-definition"></a>Sordefiníció létrehozása

1. A Jelentéstervezőben kattintson a navigációs panelen található **Sordefiníciók** lehetőségre.
2. A **Fájl** menüben kattintson az **Új** elemre, majd a **Sordefiníciók** pontra. Az egyes cellák tartalmával kapcsolatos további tudnivalókat lásd: [Sordefiníció cellák módosítása](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Sordefiníció megnyitása
1. A Jelentéstervezőben kattintson a navigációs panelen található **Sordefiníciók** lehetőségre.
2. Kattintson duplán a sordefiníció nevére, hogy megnyissa.
3. A sordefinícióhoz társított bármely építőelem megtekintéséhez kattintson a jobb gombbal a sordefinícióra, és válassza ki a **Társítások** lehetőséget.

## <a name="contents-of-a-row-definition"></a> Sordefiníció tartalma
Egy sordefiníció legfeljebb 20 000 pénzügyidimenzió-sort és a következő információkat tartalmazhatja:

- Leíró szöveget, amely értelmet ad a jelentésnek szakaszcímek, sorok és terek létrehozásával, például **Készpénz** vagy **Teljes bevétel**
- Pénzügyi adatokra mutató hivatkozásokat, amelyek tartalmazhatnak a Microsoft Dynamics 365 for Finance and Operations alkalmazásban szereplő dimenzióértékeket

    > [!NOTE]
    > A sordefiníciót beállíthatja úgy, hogy minden alkalommal lekérje az adatokat a pénzügyi dimenziók rendszeréből, amikor a jelentést elkészítik.

- Sorösszegeket és képleteket, amik a hivatkozott pénzügyi adatokon alapulnak.

Általában minden sordefiníció tartalmaz egyet a következő információtípusok közül:

- Hivatkozásokat a pénzügyi dimenziók rendszerére
- Összegeket vagy számításokat az adatok alapján
- Formázás

A sordefiníció információk megadására két módja van:

- A sorinformáció megadása manuálisan, egy új sordefinícióba. További tudnivalókért lásd: [Sordefiníció cellák módosítása](modify-row-definition-cells-financial-reporting.md).
- Használja a jelentéstervezőt, hogy közvetlenül kinyerje a sorinformációkat a pénzügyi dimenziókból. További információért lásd a „Kapcsolódó képletek/sorok/egységek" részt a [Sordefiniáló cellák módosítása](modify-row-definition-cells-financial-reporting.md) fejezetben.

## <a name="add-dimensions-in-a-row-definition"></a> Dimenziók hozzáadása egy sordefinícióhoz
Egy dimenzió az adatok és értékek egy metszete. Adat- és jelentéstervező értékeket csoportosíthat a jelentéstervezőben. Ezután részletesebben osztályozhatja és elemezheti a tranzakciókat. Használhatja a **Sorok beszúrása dimenziókból** párbeszédpanelt, hogy egy időben több sort adjon hozzá egy sordefinícióhoz. A párbeszédpanel minden dimenzióhoz egy oszlopot jelenít meg. A következő táblázat tartalmazza az egyes dimenziókhoz megadható információk leírását.

| Lehetőség                | Leírás |
|-----------------------|-------------|
| Dimenzió             | A szabály, amely azonosítja a sordimenzióhoz adandó dimenziót. Ez a szabály tartalmaz egy és-jelet (&), vagy egy kettős kereszt jelet (\#), minden pozícióhoz a dimenziókban. Általában használjon kizárólag jeleket a Fő számlához és kizárólag számokat a többi dimenzióhoz. |
| Dimenziótartomány kezdete | A sordefinícióhoz hozzáadni kívánt dimenzió első értéke. |
| Dimenziótartomány vége   | Az utolsó érték, amely ebből a dimenzióból a sordefinícióhoz adandó. |

Dimenziók hozzáadásához a sordefiníciókhoz végezze el a következő lépéseket.

1. A Jelentéstervezőben kattintson a **Sordefiníciók** lehetőségre, majd nyissa meg a sordefiníciót, hogy módosítsa.
2. A **Szerkesztés** menüben kattintson a **Sorok beszúrása dimenziókból** elemre.
3. A **Sorok beszúrása dimenziókból** párbeszédpanelen a **Dimenziók** sorban, jelölje ki a dimenzióból a sordefinícióba átvinni kívánt cellát, majd kattintson az **Összes &&&** elemre.
4. Hogy korlátozza a sordefiníciót a dimenzióértékek egy adott tartományára, adja meg a kezdő dimenzióértéket a **Dimenziótartomány kezdete** cellában, majd adja meg a záró dimenzióértéket a **Dimenziótartomány vége** cellában. Ha az összes értéket szerepeltetni kívánja a kiválasztott dimenzió esetén, hagyja üresen ezeket a cellákat.

    > [!NOTE]
    > Az ERP-adatbázis adatleválogatási módszerétől függően előfordulhat, hogy a helyettesítő karakterek (\* vagy ?) a dimenziótartományokban nem adják vissza az összes kívánt eredményt.

5. Adjon meg egy értéket a **Kezdő sorkód** mezőben, hogy megadja a sordefinícióhoz adandó, első dimenzióértékhez tartozó sorkódot.
6. Adjon meg egy értéket a **Sorok növekménye** mezőben, hogy megadja az egymást követő sorkódok közötti rést. Például, ha az első sorkódot 100, és a növekményértéke 30, akkor az első új sorok kódjai rendre 100, 130, 160, 190 és 220. Használjon olyan növekményértéket, amely elég helyet biztosít új formátum és receptúra sorok beszúrásához. Használjon olyan növekményértéket, amely elég helyet biztosít új formátum és receptúra sorok beszúrásához.
7. Kattintson az **OK** gombra. Minden kijelölt dimenzióérték után egy sor adódik a sordefinícióhoz.

## <a name="adjust-rounding-in-a-row-definition"></a> Kerekítés beállítása egy sordefinícióban
Egy olyan mérleg esetén, amelyben az összegek kerekítve vannak az összesítések eltérhetnek az egyensúlytól. Ez a probléma akkor fordulhat elő, ha például a kerekítési lehetőséget választja a mérlegkimutatáson, és a jelentésdefiníció is határoz meg kerekítést. Használhatja a **Kerekítés helyesbítés** lehetőséget a sordefinícióban, hogy kiegyenlítse a mérlegben szereplő összegeket. A kerekítést kikapcsolhatja vagy módosíthatja a jelentésdefiníció **Beállítások** lapján. A következő táblázat bemutatja az összegek kerekítését. Ebben a táblázatban a 100-as és 200-as sorok összesítései eltérnek, ha a kerekítés be van kapcsolva.

| Sorkód | Összegek kerekítés nélkül | Összeg teljes ezrekre kerekítéssel |
|----------|--------------------------|-----------------------------------------|
| 100      | 3600                    | 4                                       |
| 200      | 3700                    | 4                                       |
| Összesen    | 7300                    | 8                                       |

Hogy beállítsa a kerekítést egy mérlegben, kövesse a következő lépéseket.

1. A Jelentés Tervező eszközben, kattintson **Sor Definíciók**, majd nyissa meg a sor definíciót, hogy módosítsa.
2. Válassza a **Szerkesztés** menü **Kerekítési kiigazítás** parancsát.
3. A **Kerekítési helyesbítés** párbeszédpanelen írja be a következő értékeket:

    - **Sorkerekítési helyesbítés** – Az adott sorhoz tartozó sorkód helyesbítve lesz, hogy kiegyenlítse a mérleget.
    - **Összes eszköz sor** – A sorkód, amely ahhoz a sorhoz tartozik a mérlegben, amely tartalmazza az összes eszközt.
    - **Összes kötelezettség– és részvénysor** – A sorkód, amely ahhoz a sorhoz tartozik a mérlegben, amely tartalmazza az összes kötelezettséget és részvényt.
    - **Helyesbítési összeghatár** – egy pozitív egész szám, amely megadja az automatikus helyesbítések korlátját. A rendszer ezt a összeget hasonlítja össze a tényleges kerekítési különbség abszolút értékével.

    > [!NOTE]
    > Ezeket a sorkódokat a pénzügyi adatokhoz kell kapcsolni. Más megfogalmazásban: a sor **Kapcsolás a pénzügyi dimenziókhoz** cellájában szerepelnie kell egy dimenzióértéknek. Leírás (**DESC**), számított (**CALC**), vagy összesített (**TOT**) sorra **ne** hivatkozzon.

A mérlegben szereplő összegek most már kiegyenlítődnek, ha a kerekítés be van kapcsolva.

> [!NOTE]
> A kerekítési korlátozás alkalmazása a jelentésdefinícióhoz megadott **Kerekítés pontossága** beállítás alapján történik. Például, ha kijelöli, hogy ezrekre kerekíti a jelentését és beírja a **2** értéket a **Helyesbítési összeghatár** mezőbe, akkor egy figyelmeztető üzenetet kap, amikor a **Kerekítés helyesbítő sor** mezőben azonosításra került érték több mint 2000-rel növekszik, vagy nő.

## <a name="format-row-and-column-text"></a>Sor– és oszlopszöveg formázása
Személyre szabhatja a jelentései megjelenését szövegtípusok változtatásával és szövegszerkesztéssel. A következő bekezdések elmagyarázzák, hogyan szerkessze a sorok és oszlopok megjelenését a jelentésekben.

### <a name="manage-font-styles"></a>Betűstílusok kezelése

Létrehozhat, és módosíthat betűtípusokat a jelentéséhez. Ezeket a stílusokat alkalmazhatja a dokumentumban, vagy a jelentés egy adott sorában vagy oszlopában.

<table>
<tbody>
<tr>
<td><strong>Új betűstílus létrehozása</strong></td>
<td>
<ol>
<li>A jelentéstervezőben a <strong>Formátum</strong> menüben kattintson a <strong>Stílusok és formázás</strong> elemre.</li>
<li>A <strong>Stílusok és formázás</strong> párbeszédpanelen kattintson az <strong>Új</strong> gombra, és írjon be egy egyedi nevet az új stílus számára.</li>
<li>Válassza ki a kívánt betűtípus-beállításokat, majd kattintson az <strong>OK</strong> gombra.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Betűstílus módosítása</strong></td>
<td>
<ol>
<li>A jelentéstervezőben a <strong>Formátum</strong> menüben kattintson a <strong>Stílusok és formázás</strong> elemre.</li>
<li>Válassza ki a módosítani kívánt stílust a <strong>Stílusok és formázás</strong> párbeszédpanelen, majd kattintson a <strong>Módosítás</strong> gombra.</li>
<li>Válassza ki a kívánt betűtípus-beállításokat, majd kattintson az <strong>OK</strong> gombra.</li>
</ol>
</td>
</tr>
<tr>
<td><strong>Új betűstílus alkalmazása</strong></td>
<td>
<ol>
<li>A Jelentéstervezőben, egy definícióban vagy oszlopdefinícióban, vagy fejlécekben és láblécben jelöljön ki egy vagy több cellát.</li>
<li>Válasszon ki egy betűstílust az eszköztár <strong>Stílus</strong> listájáról.</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Sorszöveg formázása

A sordefinícióban meghatározott formázás felülír minden formázást, amely az oszlop- és jelentésdefinícióban van meghatározva. A Formázás eszköztár vezérlőelemei segítségével módosíthatja a szöveg formátumot. Ezek a vezérlők szabványos Microsoft Windows vezérlők.

1. Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.
2. Válassza ki a formázandó cellákat. Több cella kijelöléséhez tartsa lenyomva a Ctrl gombot, amíg kijelöli a cellát.
3. Kattintson a formátum eszköztári gombjára, hogy alkalmazza. Például, egy sor behúzásához jelölje ki a sort, és kattintson a Behúzás növelése **Behúzás növelése** ![Behúzás növelése](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Behúzás növelése") elemre az eszköztárban.

### <a name="adjust-columns-while-you-design-reports"></a>Oszlopok beállítása a jelentések tervezése közben

Hogy megkönnyítse azon oszlopok áttekintését, amelyeken a sordefinícióban dolgozik beállíthatja az oszlopszélességet és elrejtheti (minimalizálhatja) vagy megjelenítheti az oszlopokat a nézet oldalon. A végrehajtott módosítások csak az oszlopok képernyőn való megjelenésére vannak hatással. Nincsenek hatással a jelentések oszlopformázásra.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Oszlopszélesség megváltoztatása a nézet ablakban

1. Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.
2. A **Formátum** menüben válassza ki az **Oszlopszélesség** elemet.
3. Az **Oszlopszélesség** párbeszédpanelen adjon meg egy értéket, majd kattintson az **OK** gombra. Másik lehetőségként elhúzhatja az oszlop fejléccellájának jobb határát, hogy megváltoztassa az oszlopszélességet.

### <a name="hide-columns-in-the-view-pane"></a>Oszlopok elrejtése a nézet ablakban

1. Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.
2. Válassza ki azokat az oszlopokat, amelyeket kis méretűvé kíván tenni.
3. Kattintson jobb gombbal, majd kattintson az **Elrejtés** gombra.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Minden rejtett oszlop megjelenítése a nézet ablakban

1. Nyissa meg a módosítandó sordefiníciót a jelentéstervezőben.
2. Kattintson jobb gombbal a megjelenítendő minimalizált oszlopra, majd kattintson a **Megjelenítés** elemre.


## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)

