---
title: A pénzügyi jelentés összetevői
description: A cikk ismerteti, hogy a jelentésdefiníciók alkotórészei, más néven az építőelemei hogyan használatosak a pénzügyi jelentéseketben.
author: aprilolson
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.form: FinancialReports
ms.openlocfilehash: 66430f81bd3d1efe126dfb29fa9c6a093716f90e
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802715"
---
# <a name="financial-report-components"></a>A pénzügyi jelentés összetevői

[!include [banner](../includes/banner.md)]

A cikk ismerteti, hogy a jelentésdefiníciók alkotórészei, más néven az építőelemei hogyan használatosak a pénzügyi jelentéseketben. Ezek az építőelemek tartalmaznak sordefiníciókat, oszlopdefiníciókat és jelentési fa definíciókat. A cikk az építőelemek szervezését és zárolását ismerteti.

A pénzügyi jelentéstervező mögötti tervezési filozófia az, hogy az információkat lebontjuk a legkisebb alkotórészekig vagy építőelemekig, majd szükség szerint keverjük és párosítjuk azokat. Emiatt a jelentés formátuma elkülönül a pénzügyi adatoktól, és a pénzügyi adatok módosítása nélkül is módosíthatja a jelentéstervet a  Microsoft Dynamics Pénzügy 365-ben. Az ilyen építőelemes megközelítés használatával egyesíthet szövegeket, összegeket és számításokat olyan jelentések készítéséhez, amelyekre szüksége van. Továbbá ez a rugalmasság támogatja a kreativitást, mivel megkönnyíti a műveletek különböző módokon történő megtekintését. A jelentésdefiníciók építőelemei egy háromdimenziós táblázathoz hasonlatosak, a szerepük azonban kiemeltebb annál. A jelentésdefiníció határozza meg a jelentéshez használandó sordefiníciót, oszlopdefiníciót és opciós jelentési-fa definíciót. Emellett tartalmaz a létrehozott jelentés tárolási helyére, illetve formázási módjára vonatkozó információkat is.

## <a name="building-blocks-of-a-report"></a>Jelentés építőelemei

| Építőelem            | Leírás | További információ |
|---------------------------|-------------|----------------------|
| Sor definíciója            | A sordefiníció a jelentés leíró sorait határozza meg (pl. a fizetések vagy az értékesítés). Emellett felsorolja az egyes sorcikkek értékeit tartalmazó szegmensértékeket vagy dimenziókat is, valamint tartalmaz sorformázásokat és számításokat. | [Sordefiníciók](row-definitions-financial-reporting.md) |
| Oszlopdefiníció         | Az oszlopdefiníció határozza meg a pénzügyi dimenziókból történő adatkivonatolás során használandó időszakot. Emellett tartalmaz oszlopformázásokat és számításokat is. | [Oszlopdefiníciók](column-definitions-financial-reports.md) |
| Jelentési-fa definíció | A jelentési-fa definíció olyan, mint egy szervezeti diagram. Az egyes jelentési egységeket jeleníti meg az ábrán belül látható dobozok formájában. Az egységek lehetnek a pénzügyi adatokból származó önálló osztályok, vagy olyan magasabb szintű egységek, melyek más jelentési egységek adatait összesítik. | [Jelentési-fa definíciók](financial-reporting-tree-definitions.md) |
| Jelentésdefiníció         | A jelentésdefiníció egy sordefiníció, egy oszlopdefiníció és egy opciós jelentési-fa definíció segítségével határozza meg egy jelentés felépítését. Emellett tartalmaz további lehetőségeket és beállításokat, amelyeket használhat a jelentés testreszabásához. | [Jelentésdefiníció](design-financial-report-definitions.md) |

Ha még nem járatos a jelentések tervezésében, akkor tanácsos a jelentéstervező varázslót használnia, hogy gyorsan létrehozzon egy jelentésdefiníciót, amelyet később személyre szabhat. Ha tapasztalt a jelentések tervezésében és több rugalmasságra vágyik a jelentéstervezés során, akkor egyesítheti az új és a már létező építőelemeket egy új jelentésdefinícó létrehozásához. Nem kell teljesen értenie az összes elérhető jelentésdefiníció-beállítást ahhoz, hogy minőségi jelentéseket hozzon létre. Amint egyre nagyobb gyakorlatra tesz szert a jelentések tervezése kapcsán, úgy tudja majd bővíteni a jelentésdefinícióit, illetve igénybe venni a speciális funkciókat. Miután létrehozott egy alapjelentést személyre szabhatja a jelentésdefiníciót és annak bármely építőelemét.

## <a name="organize-the-building-blocks"></a>Építőelemek rendezése
Használjon mappákat az építőelemek rendezéséhez a Jelentéstervezőben. Minden mappát jellemez az, hogy milyen típusú építőelemeket tartalmaz. Például a sordefiníciókat tartalmazó mappák a **Jelentéstervező Sordefiníciók** ablakában találhatók.

### <a name="create-a-folder"></a>Mappa létrehozása

1. A Jelentéstervezőben válassza ki a navigációs ablakban rendszerezni kívánt épületblokk típusát. Ha például sordefiníciót szeretne rendezni, kattintson a **Sordefiníciók** lehetőségre.
2. A navigációs ablaktáblában válassza ki azt a meglévő mappát, amelyben az új mappát létre kívánja hozni, majd hajtsa végre az alábbi műveletek valamelyikét:

    - Kattintson a jobb gombbal a szülőmappra, majd kattintson az **Új mappa elemre**.
    - Válassza ki a szülőmappát, kattintson a Fájl **gombra**, majd az Új **mappa gombra**.

3. Amikor megjelenik az új mappa, írja be az új mappa nevét, majd nyomja le az **Enter billentyűt**.

## <a name="lock-a-building-block"></a> Építőelem zárolása
Tud jelszót állítani be egy építőelem védelme és zárolása érdekében. Ezzel emelheti az egyik jelentés-összetevő biztonsági szintjét, anélkül, hogy az egész rendszert biztosítania kellene. Egy jelszó segíthet megvédeni az olyan építőelem információkat, melyek fontosak lehetnek hónap végi jelentéskészítési folyamat során. Bármely szerepkörbeli felhasználók zárolhatnak egy építőelemet. Azonban más felhasználók mindig csak olvasási hozzáféréssel fognak rendelkezni egy zárolt elemhez. A felhasználók továbbra is képesek lesznek megnyitni, módosítani, illetve új néven menteni a zárolt összetevőt. A rendszergazda szerepkörrel rendelkező felhasználó minden esetben hozzáfér, illetve módosítani képes a zárolt építőelemet.

1. A Jelentéstervezőben nyissa meg a zárolni szükséges jelentésösszetevőt, például sordefiníciót, oszlopdefiníciót, jelentésdefiníciót vagy jelentési fadefiníciót.
2. Az **Eszközök** menüben kattintson a **Védelem/Védelem törése** menüpontra. Vagy rákattinthat az eszköztár **Védelem/Védelem törlése** ikonjára (amelyet egy lakat jelöl).
3. A **Védelem** párbeszédpanelen írja be és erősítse meg a jelszót, majd kattintson az **OK** gombra. Egy nyitott építőelem zárolásakor a rendszer kijelöli az eszköztár lakat ikonját.

Egy zárolt építőelem zárolásának törléséhez nyissa meg az építőelemet, majd kattintson a **Védelem/Védelem törlése** ikonra. Másik megoldásként az **Eszközök** menüben kattintson a **Védelem/Védelem törése** menüpontra.

## <a name="building-block-groups"></a>Építőelem-csoportok

Az építőelem a jelentés létrehozásához használt sordefiníciókból, oszlopdefiníciókból, jelentési-fa definíciókból, és jelentésdefiníciókból áll. Az építőelem-csoportok definíciók és dimenziókészletek gyűjteményei.

### <a name="view-a-building-block-group"></a>Építőelem-csoport megtekintése

Mindegyik építőelem-csoporthoz rendelt építőelemet megtekintheti. Az építőelem-csoportok exportálhatók és importálhatók.

1. Kattintson a Jelentéstervező Vállalat **menüjének** **Blokkcsoportok létrehozása parancsára**.
2. A Blokkcsoportok **párbeszédpanelen** válassza ki a megtekinteni kívánt épületblokkot.
3. Kattintson **a Nézet** gombra az **Épületblokkok** megtekintése párbeszédpanel megnyitásához, ahol megtekintheti az épületblokk-csoport tartalmát.
4. A **Bezárás** gombbal zárja be a párbeszédpaneleket.

### <a name="export-a-building-block-group"></a>Építőelem-csoport exportálása

Exportálhatja, vagy importálhatja is az építőelem-csoportokat, vagy egyes adott jelentés-építőelemeket. Az exportált építőelem-csoportot biztonsági másolatként is használhatja. Az exportált adatokat a telepítések között is másolhatja. A Jelentéstervező tartalmazza a hivatkozott betűstílusokat és a dimenziókészleteket, az építőelem-csoportokkal együtt.

1. A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2. A Blokkcsoportok **párbeszédpanelen** válassza ki az exportálni kívánt épületblokkcsoportot, majd kattintson az Exportálás **gombra**.
3. Jelölje ki az exportálandó jelentésdefiníciókat az **Exportálás** párbeszédpanelben:

    - Ha az összes jelentésdefiníciót és a kapcsolódó épületblokkokat is exportálni kell, kattintson az Összes **kijelölése gombra**.
    - Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket. Ha több tételt szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt.

    > [!NOTE]
    > Ha jelentéseket jelöl ki az exportálásához, a rendszer a társított sorokat, oszlopokat, fákat és dimenziókészleteket is kijelöli.

4. Ha végzett az exportálandó cikkek kiválasztásával, kattintson az **Exportálás** lehetőségre.
5. A **Mentés másként** párbeszédpanelben jelölje ki, hogy hová szeretné exportálni az építőelem-csoportot.
6. A Fájlnév **mezőbe** írja be a fájl nevét. A Jelentéstervező eszköz automatikusan .tdbx kiterjesztést illeszt a fájlnév végére.
7. Kattintson a **Mentés** gombra. Az építőelem-csoport az Ön által megadott helyre kerül elmentésre.

### <a name="import-a-building-block-group"></a> Építőelem-csoport importálása

Az építőelem-csoportok importálhatók egy meglévő építőelem-csoportba. Az összes importált építőelem-csoport megtartja az eredeti betűstílusát és a vállalati hivatkozásait, és tartalmazza a megfelelő dimenziókészleteket.

1. Kattintson a Jelentéstervező Vállalat **menüjének** **Blokkcsoportok létrehozása parancsára**.
2. A Blokkcsoportok **párbeszédpanelen** válassza ki azt az épületblokkot, amelybe az épületblokkok csoportját importálni kell, **majd kattintson az Importálás gombra**.
3. A **Megnyitás** párbeszédpanelen válassza ki az importálni kívánt építőelem-csoportot, majd kattintson a **Megnyitás** gombra.
4. Jelölje ki az importálandó jelentésdefiníciókat az **Importálás** párbeszédpanelben:

    - Ha importálni kell az összes jelentésdefiníciót és a támogató épületblokkokat, kattintson az Összes **kijelölése gombra**.
    - Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.

5. Ha végzett az importálandó cikkek kiválasztásával, kattintson az **Importálás** lehetőségre.

### <a name="undo-a-checkout-of-a-building-block"></a>Építőelem kivételének visszavonása

Amikor megnyit egy építőelemet, a többi felhasználó csak olvasásra kap hozzáférést ahhoz az elemhez. Előfordulhat, hogy a felhasználók elfelejtik bezárni az építőelemeket, vagy kikapcsolják a rendszerüket az építőelem bezárása nélkül. Így az építőelem továbbra is kivett állapotú marad, és azt a többi felhasználó nem tudja megnyitni. Ilyen esetekben a pénzügyi jelentések rendszergazdája a **Kivett cikkek** párbeszédpanel segítségével, vissza tudja venni a másik felhasználó által kivett állapotban felejtett építőelemeket.

> [!NOTE]
> Építőelemek bevételéhez a **Kivett elemek** párbeszédpanellel rendszergazda szerepkörrel kell rendelkeznie.

1. A Jelentéstervező Eszközök menüjében **kattintson** a Kivett **elemek elemre**.
2. A Kivett **cikkek párbeszédpanelen** jelölje be az összes felhasználó **cikkének megjelenítése lehetőséget**. A listában megjelenik az összes kivett építőelem és a hozzájuk kapcsolódó felhasználók listája.
3. Válasszon egy épületblokkot, majd kattintson a Kivétel **visszavonása gombra**.
4. Kattintson az **Igen** gombra az építőelem bevételéhez.

## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
