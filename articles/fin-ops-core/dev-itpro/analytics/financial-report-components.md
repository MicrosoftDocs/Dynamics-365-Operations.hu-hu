---
title: A pénzügyi jelentés összetevői
description: A cikk ismerteti, hogy a jelentésdefiníciók alkotórészei, más néven az építőelemei hogyan használatosak a pénzügyi jelentéseketben.
author: aprilolson
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8512559ea33f16f3558b277999cc86240ee8277d1b3b0d6bf2aecba32df8e09f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761440"
---
# <a name="financial-report-components"></a>A pénzügyi jelentés összetevői

[!include [banner](../includes/banner.md)]

A cikk ismerteti, hogy a jelentésdefiníciók alkotórészei, más néven az építőelemei hogyan használatosak a pénzügyi jelentéseketben. Ezek az építőelemek tartalmaznak sordefiníciókat, oszlopdefiníciókat és jelentési fa definíciókat. A cikk az építőelemek szervezését és zárolását ismerteti.

A pénzügyi jelentéstervező mögötti tervezési filozófia az, hogy az információkat lebontjuk a legkisebb alkotórészekig vagy építőelemekig, majd szükség szerint keverjük és párosítjuk azokat. Ezért a jelentés formázása elkülönül az Ön pénzügyi adataitól, és a jelentések kinézetét anélkül változtathatja, hogy módosítaná a pénzügyi adatait a Microsoft Dynamics ERP rendszerben. Az ilyen építőelemes megközelítés használatával egyesíthet szövegeket, összegeket és számításokat olyan jelentések készítéséhez, amelyekre szüksége van. Továbbá ez a rugalmasság támogatja a kreativitást, mivel megkönnyíti a műveletek különböző módokon történő megtekintését. A jelentésdefiníciók építőelemei egy háromdimenziós táblázathoz hasonlatosak, a szerepük azonban kiemeltebb annál. A jelentésdefiníció határozza meg a jelentéshez használandó sordefiníciót, oszlopdefiníciót és opciós jelentési-fa definíciót. Emellett tartalmaz a létrehozott jelentés tárolási helyére, illetve formázási módjára vonatkozó információkat is.

## <a name="building-blocks-of-a-report"></a>Jelentés építőelemei

| Építőelem            | Leírás | További információ |
|---------------------------|-------------|----------------------|
| Sor definíciója            | A sordefiníció a jelentés leíró sorait határozza meg (pl. a fizetések vagy az értékesítés). Emellett felsorolja az egyes sorcikkek értékeit tartalmazó szegmensértékeket vagy dimenziókat is, valamint tartalmaz sorformázásokat és számításokat. | [Sordefiníciók](row-definitions-financial-reporting.md) |
| Oszlopdefiníció         | Az oszlopdefiníció határozza meg a pénzügyi dimenziókból történő adatkivonatolás során használandó időszakot. Emellett tartalmaz oszlopformázásokat és számításokat is. | [Oszlopdefiníciók](column-definitions-financial-reports.md) |
| Jelentési-fa definíció | A jelentési-fa definíció olyan, mint egy szervezeti diagram. Az egyes jelentési egységeket jeleníti meg az ábrán belül látható dobozok formájában. Az egységek lehetnek a pénzügyi adatokból származó önálló osztályok, vagy olyan magasabb szintű egységek, melyek más jelentési egységek adatait összesítik. | [Jelentési-fa definíciók](financial-reporting-tree-definitions.md) |
| Jelentésdefiníció         | A jelentésdefiníció egy sordefiníció, egy oszlopdefiníció és egy opciós jelentési-fa definíció segítségével határozza meg egy jelentés felépítését. Emellett tartalmaz további lehetőségeket és beállításokat, amelyeket használhat a jelentés testreszabásához. | [Jelentésdefiníció](design-financial-report-definitions.md) |

Ha még nem járatos a jelentések tervezésében, akkor tanácsos a jelentéstervező varázslót használnia, hogy gyorsan létrehozzon egy jelentésdefiníciót, amelyet később személyre szabhat. Ha tapasztalt a jelentések tervezésében és több rugalmasságra vágyik a jelentéstervezés során, akkor egyesítheti az új és a már létező építőelemeket egy új jelentésdefinícó létrehozásához. Nem kell teljesen értenie az összes elérhető jelentésdefiníció-beállítást ahhoz, hogy minőségi jelentéseket hozzon létre. Amint egyre nagyobb gyakorlatra tesz szert a jelentések tervezése kapcsán, úgy tudja majd bővíteni a jelentésdefinícióit, illetve igénybe venni a speciális funkciókat. Miután létrehozott egy alapjelentést személyre szabhatja a jelentésdefiníciót és annak bármely építőelemét.

## <a name="organize-the-building-blocks"></a>Építőelemek rendezése
Használjon mappákat az építőelemek rendezéséhez a Jelentéstervezőben. Minden mappát jellemez az, hogy milyen típusú építőelemeket tartalmaz. Például minden mappa, amely sordefiníciókat tartalmaz a Jelentéstervező **Sordefiníciók** oldalán található.

### <a name="create-a-folder"></a>Mappa létrehozása

1. Válassza ki a Jelentéstervezőben a navigációs ablaktáblában rendezni kívánt építőelem típusát. Ha például sordefiníciót szeretne rendezni, kattintson a **Sordefiníciók** lehetőségre.
2. A navigációs ablaktáblában válassza ki azt a meglévő mappát, amelyben az új mappát létre kívánja hozni, majd hajtsa végre az alábbi műveletek valamelyikét:

    - Kattintson jobb egérgombbal a szülőmappára, majd kattintson az **Új mappa** lehetőségre.
    - Válassza ki a szülőmappát, majd kattintson a **Fájl** lehetőségre, és az **Új mappa** lehetőségre.

3. Az új mappa megjelenésekor adja meg az új mappa nevét, majd nyomja meg az Enter billentyűt.

## <a name="lock-a-building-block"></a> Építőelem zárolása
Tud jelszót állítani be egy építőelem védelme és zárolása érdekében. Ezzel emelheti az egyik jelentés-összetevő biztonsági szintjét, anélkül, hogy az egész rendszert biztosítania kellene. Egy jelszó segíthet megvédeni az olyan építőelem információkat, melyek fontosak lehetnek hónap végi jelentéskészítési folyamat során. Bármely szerepkörbeli felhasználók zárolhatnak egy építőelemet. Azonban más felhasználók mindig csak olvasási hozzáféréssel fognak rendelkezni egy zárolt elemhez. A felhasználók továbbra is képesek lesznek megnyitni, módosítani, illetve új néven menteni a zárolt összetevőt. A rendszergazda szerepkörrel rendelkező felhasználó minden esetben hozzáfér, illetve módosítani képes a zárolt építőelemet.

1. Nyissa meg a zárolni kívánt összetevőt, például a sordefiníciót, az oszlopdefiníciót, a jelentésdefiníciót vagy a jelentési-fa definíciót a Jelentéstervezőben.
2. Az **Eszközök** menüben kattintson a **Védelem/Védelem törése** menüpontra. Vagy rákattinthat az eszköztár **Védelem/Védelem törlése** ikonjára (amelyet egy lakat jelöl).
3. A **Védelem** párbeszédpanelen írja be és erősítse meg a jelszót, majd kattintson az **OK** gombra. Egy nyitott építőelem zárolásakor a rendszer kijelöli az eszköztár lakat ikonját.

Egy zárolt építőelem zárolásának törléséhez nyissa meg az építőelemet, majd kattintson a **Védelem/Védelem törlése** ikonra. Másik megoldásként az **Eszközök** menüben kattintson a **Védelem/Védelem törése** menüpontra.

## <a name="building-block-groups"></a>Építőelem-csoportok

Az építőelem a jelentés létrehozásához használt sordefiníciókból, oszlopdefiníciókból, jelentési-fa definíciókból, és jelentésdefiníciókból áll. Az építőelem-csoportok definíciók és dimenziókészletek gyűjteményei.

### <a name="view-a-building-block-group"></a>Építőelem-csoport megtekintése

Mindegyik építőelem-csoporthoz rendelt építőelemet megtekintheti. Az építőelem-csoportok exportálhatók és importálhatók.

1. A Report Designer eszközben válassza a **Vállalat** menü **Építőelem-csoportok** elemét.
2. Az **Építőelem-csoportok** párbeszédpanelben válassza ki a megtekinteni kívánt építőelemet.
3. Kattintson a **Nézet** lehetőségre az **Építőelem-csoport megtekintése** párbeszédpanel megnyitásához, ahol megtekintheti az építőelem-csoport tartalmát.
4. A **Bezárás** gombbal zárja be a párbeszédpaneleket.

### <a name="export-a-building-block-group"></a>Építőelem-csoport exportálása

Exportálhatja, vagy importálhatja is az építőelem-csoportokat, vagy egyes adott jelentés-építőelemeket. Az exportált építőelem-csoportot biztonsági másolatként is használhatja. Az exportált adatokat a telepítések között is másolhatja. A Jelentéstervező tartalmazza a hivatkozott betűstílusokat és a dimenziókészleteket, az építőelem-csoportokkal együtt.

1. A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2. Az **Építőelem-csoportok** párbeszédpanelen válassza ki az exportálni kívánt építőelem-csoportot, majd kattintson az **Exportálás** parancsra.
3. Jelölje ki az exportálandó jelentésdefiníciókat az **Exportálás** párbeszédpanelben:

    - Az összes jelentésdefiníció illetve a társított építőelemek exportálásához kattintson az **Összes kijelölése** lehetőségre.
    - Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket. Ha több tételt szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt.

    > [!NOTE]
    > Ha jelentéseket jelöl ki az exportálásához, a rendszer a társított sorokat, oszlopokat, fákat és dimenziókészleteket is kijelöli.

4. Ha végzett az exportálandó cikkek kiválasztásával, kattintson az **Exportálás** lehetőségre.
5. A **Mentés másként** párbeszédpanelben jelölje ki, hogy hová szeretné exportálni az építőelem-csoportot.
6. Adja meg a fájlnevet a **Fájlnév** mezőben. A Jelentéstervező eszköz automatikusan .tdbx kiterjesztést illeszt a fájlnév végére.
7. Kattintson a **Mentés** gombra. Az építőelem-csoport az Ön által megadott helyre kerül elmentésre.

### <a name="import-a-building-block-group"></a> Építőelem-csoport importálása

Az építőelem-csoportok importálhatók egy meglévő építőelem-csoportba. Az összes importált építőelem-csoport megtartja az eredeti betűstílusát és a vállalati hivatkozásait, és tartalmazza a megfelelő dimenziókészleteket.

1. A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2. Az **Építőelem-csoportok** párbeszédpanelen jelölje ki azt az építőelem-csoportot, amelybe egy másik építőelem-csoportot kíván importálni, majd kattintson az **Importálás** parancsra.
3. A **Megnyitás** párbeszédpanelen válassza ki az importálni kívánt építőelem-csoportot, majd kattintson a **Megnyitás** gombra.
4. Jelölje ki az importálandó jelentésdefiníciókat az **Importálás** párbeszédpanelben:

    - Az összes jelentésdefiníció illetve az azt támogató építőelemek importálásához kattintson az **Összes kijelölése** lehetőségre.
    - Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.

5. Ha végzett az importálandó cikkek kiválasztásával, kattintson az **Importálás** lehetőségre.

### <a name="undo-a-checkout-of-a-building-block"></a>Építőelem kivételének visszavonása

Amikor megnyit egy építőelemet, a többi felhasználó csak olvasásra kap hozzáférést ahhoz az elemhez. Előfordulhat, hogy a felhasználók elfelejtik bezárni az építőelemeket, vagy kikapcsolják a rendszerüket az építőelem bezárása nélkül. Így az építőelem továbbra is kivett állapotú marad, és azt a többi felhasználó nem tudja megnyitni. Ilyen esetekben a pénzügyi jelentések rendszergazdája a **Kivett cikkek** párbeszédpanel segítségével, vissza tudja venni a másik felhasználó által kivett állapotban felejtett építőelemeket.

> [!NOTE]
> Építőelemek bevételéhez a **Kivett elemek** párbeszédpanellel rendszergazda szerepkörrel kell rendelkeznie.

1. A Jelentéstervező **Eszközök** menüjében kattintson a **Kivett cikkek** lehetőségre.
2. A **Kivett elemek** párbeszédpanelen válassza **Az összes felhasználó elemeinek megjelenítése** lehetőséget. A listában megjelenik az összes kivett építőelem és a hozzájuk kapcsolódó felhasználók listája.
3. Jelölje ki a kívánt építőelemet, majd kattintson a **Kivétel visszavonása** parancsra.
4. Kattintson az **Igen** gombra az építőelem bevételéhez.

## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]