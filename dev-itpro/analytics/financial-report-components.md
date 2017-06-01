---
title: "A pénzügyi jelentés összetevői"
description: "A cikk ismerteti, hogy a jelentésdefiníciók alkotórészei, más néven az építőelemei hogyan használatosak a pénzügyi jelentéseketben. Ezek az építőelemek tartalmaznak sordefiníciókat, oszlopdefiníciókat és jelentési fa definíciókat. Ez a cikk ismerteti, hogyan rendezheti és zárolhatja az építőelemeket, valamint a velük történő munkát."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 057c338c11518b3a1081223e432cbfd109d5e679
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="financial-report-components"></a>A pénzügyi jelentés összetevői

[!include[banner](../includes/banner.md)]


A cikk ismerteti, hogy a jelentésdefiníciók alkotórészei, más néven az építőelemei hogyan használatosak a pénzügyi jelentéseketben. Ezek az építőelemek tartalmaznak sordefiníciókat, oszlopdefiníciókat és jelentési fa definíciókat. Ez a cikk ismerteti, hogyan rendezheti és zárolhatja az építőelemeket, valamint a velük történő munkát. 

A pénzügyi jelentéstervező mögötti tervezési filozófia az, hogy az információkat lebontjuk a legkisebb alkotórészekig vagy építőelemekig, majd szükség szerint keverjük és párosítjuk azokat. Ezért a jelentés formázása elkülönül az Ön pénzügyi adataitól, és a jelentések kinézetét anélkül változtathatja, hogy módosítaná a pénzügyi adatait a Microsoft Dynamics ERP rendszerben. Az ilyen építőelemes megközelítés használatával egyesíthet szövegeket, összegeket és számításokat olyan jelentések készítéséhez, amelyekre szüksége van. Továbbá ez a rugalmasság támogatja a kreativitást, mivel megkönnyíti a műveletek különböző módokon történő megtekintését. A jelentésdefiníciók építőelemei egy háromdimenziós táblázathoz hasonlatosak, a szerepük azonban kiemeltebb annál. A jelentésdefiníció határozza meg a jelentéshez használandó sordefiníciót, oszlopdefiníciót és opciós jelentési-fa definíciót. Emellett tartalmaz a létrehozott jelentés tárolási helyére, illetve formázási módjára vonatkozó információkat is. A könnyebb újbóli felhasználás, illetve a megosztás érdekében létrehozhat építőelem-csoportokat, melyek a vállalathoz társított korábbi jelentésdefiníciókat, sordefiníciókat, oszlopdefiníciókat, jelentési fa-definíciókat és dimenziókészleteket tartalmazzák.

## <a name="building-blocks-of-a-report"></a> A jelentések építőelemei
| Építőelem            | Leírás                                                                                                                                                                                                                                                                              | További információ                                                                                                 |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Sor definíciója            | A sordefiníció a jelentés leíró sorait határozza meg (pl. a fizetések vagy az értékesítés). Emellett felsorolja az egyes sorcikkek értékeit tartalmazó szegmensértékeket vagy dimenziókat is, valamint tartalmaz sorformázásokat és számításokat.                                                    | [Sordefiníciók](row-definitions-financial-reporting.md)                       |
| Oszlopdefiníció         | Az oszlopdefiníció határozza meg a pénzügyi dimenziókból történő adatkivonatolás során használandó időszakot. Emellett tartalmaz oszlopformázásokat és számításokat is.                                                                                                                                 | [Oszlopdefiníciók](column-definitions-financial-reports.md)         |
| Jelentési-fa definíció | A jelentési-fa definíció olyan, mint egy szervezeti diagram. Az egyes jelentési egységeket jeleníti meg az ábrán belül látható dobozok formájában. Az egységek lehetnek a pénzügyi adatokból származó önálló osztályok, vagy olyan magasabb szintű egységek, melyek más jelentési egységek adatait összesítik. | [Jelentési-fa definíciók](financial-reporting-tree-definitions.md) |
| Jelentésdefiníció         | A jelentésdefiníció egy sordefiníció, egy oszlopdefiníció és egy opciós jelentési-fa definíció segítségével határozza meg egy jelentés felépítését. Emellett tartalmaz további lehetőségeket és beállításokat, amelyeket használhat a jelentés testreszabásához.                                                                    | [Jelentésdefiníció](design-financial-report-definitions.md)                  |

Ha még nem járatos a jelentések tervezésében, akkor tanácsos a jelentéstervező varázslót használnia, hogy gyorsan létrehozzon egy jelentésdefiníciót, amelyet később személyre szabhat. Ha tapasztalt a jelentések tervezésében és több rugalmasságra vágyik a jelentéstervezés során, akkor egyesítheti az új és a már létező építőelemeket egy új jelentésdefinícó létrehozásához. Nem kell teljesen értenie az összes elérhető jelentésdefiníció-beállítást ahhoz, hogy minőségi jelentéseket hozzon létre. Amint egyre nagyobb gyakorlatra tesz szert a jelentések tervezése kapcsán, úgy tudja majd bővíteni a jelentésdefinícióit, illetve igénybe venni a speciális funkciókat. Miután létrehozott egy alapjelentést személyre szabhatja a jelentésdefiníciót és annak bármely építőelemét.

## <a name="organize-the-building-blocks"></a>Építőelemek rendezése
Használjon mappákat az építőelemek rendezéséhez a Jelentéstervezőben. Minden mappát jellemez az, hogy milyen típusú építőelemeket tartalmaz. Például minden mappa, amely sordefiníciókat tartalmaz a Jelentéstervező **Sordefiníciók** oldalán található.

### <a name="create-a-folder"></a>Mappa létrehozása

1.  Válassza ki a Jelentéstervezőben a navigációs ablaktáblában rendezni kívánt építőelem típusát. Ha például sordefiníciót szeretne rendezni, kattintson a **Sordefiníciók** lehetőségre.
2.  A navigációs ablaktáblában válassza ki azt a meglévő mappát, amelyben az új mappát létre kívánja hozni, majd hajtsa végre az alábbi műveletek valamelyikét:
    -   Kattintson jobb egérgombbal a szülőmappára, majd kattintson az **Új mappa** lehetőségre.
    -   Válassza ki a szülőmappát, majd kattintson a **Fájl** lehetőségre, és az **Új mappa** lehetőségre.

3.  Az új mappa megjelenésekor adja meg az új mappa nevét, majd nyomja meg az Enter billentyűt.

## <a name="lock-a-building-block"></a> Építőelem zárolása
Tud jelszót állítani be egy építőelem védelme és zárolása érdekében. Ezzel emelheti az egyik jelentés-összetevő biztonsági szintjét, anélkül, hogy az egész rendszert biztosítania kellene. Egy jelszó segíthet megvédeni az olyan építőelem információkat, melyek fontosak lehetnek hónap végi jelentéskészítési folyamat során. Bármely szerepkörbeli felhasználók zárolhatnak egy építőelemet. Azonban más felhasználók mindig csak olvasási hozzáféréssel fognak rendelkezni egy zárolt elemhez. A felhasználók továbbra is képesek lesznek megnyitni, módosítani, illetve új néven menteni a zárolt összetevőt. A rendszergazda szerepkörrel rendelkező felhasználó minden esetben hozzáfér, illetve módosítani képes a zárolt építőelemet.
1.  Nyissa meg a zárolni kívánt összetevőt, például a sordefiníciót, az oszlopdefiníciót, a jelentésdefiníciót vagy a jelentési-fa definíciót a Jelentéstervezőben.
2.  Az **Eszközök** menüben kattintson a **Védelem/Védelem törése** menüpontra. Vagy rákattinthat az eszköztár **Védelem/Védelem törlése** ikonjára (amelyet egy lakat jelöl).
3.  A **Védelem** párbeszédpanelen írja be és erősítse meg a jelszót, majd kattintson az **OK** gombra. Egy nyitott építőelem zárolásakor a rendszer kijelöli az eszköztár lakat ikonját.

Egy zárolt építőelem zárolásának törléséhez nyissa meg az építőelemet, majd kattintson a **Védelem/Védelem törlése** ikonra. Másik megoldásként az **Eszközök** menüben kattintson a **Védelem/Védelem törése** menüpontra.

## <a name="building-block-groups"></a>Építőelem-csoportok

Az építőelem a jelentés létrehozásához használt sordefiníciókból, oszlopdefiníciókból, jelentési-fa definíciókból, és jelentésdefiníciókból áll. Az építőelem-csoportot az adott vállalattal társított definíciógyűjtemények, illetve dimenziókészletek alkotják. Az építőelemek lehetnek egy adott vállaltra jellemzőek, vagy több vállalat is használhatja ugyanazt az építőelem-készletet. Eltérő számlatükörrel rendelkező vállalatok esetén érdemes mindegyik vállalathoz önálló építőelem-csoportot használni. A másik lehetőség az, ha mindegyik építőelem elnevezése tükrözi, hogy az melyik vállalattal kompatibilis.
### <a name="create-a-building-block-group"></a>Építőelem-csoport létrehozása

1.  A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2.  Kattintson az **Új** lehetőségre az **Építőelem-csoportok** párbeszédpanelben.
3.  Adjon egyedi nevet és leírást az építőelem-csoportnak. Minden mező legfeljebb 256 karaktert tartalmazhat. (Ez a szám a szóközöket is tartalmazza.)
4.  Új építőelem-csoport létrehozásához kattintson az **OK** gombra.

### <a name="assign-a-building-block-group"></a>Építőelem-csoport hozzárendelése

Miután létrehozott egy új építőelem-csoportot, hozzá kell rendelnie azt legalább egy vállalathoz. Ezt követően tud jelentés-, sor-, oszlop- és jelentési-fa definíciót hozni létre, majd azokat elmenteni az építőelem-csoportba. Az alábbi eljárás megkezdése előtt be kell zárnia az összes építőelemet.
1.  A Jelentéstervezőben kattintson a **Vállalat** menü **Vállalatok** parancsára.
2.  A **Vállalatok** párbeszédpanelben válassza ki a vállalatot, amelyhez szeretné hozzárendelni az építőelem-csoportot.
3.  Kattintson a **Módosítás** lehetőségre.
4.  A **Vállalat módosítása** párbeszédpanelben, az **Építőelem-csoport** mezőben válassza ki a vállalathoz hozzárendelni kívánt építőelem-csoportot, vagy kattintson az **Új** lehetőségre új építőelem-csoport létrehozásához.
5.  Kattintson az **OK** lehetőségre az építőelem-csoport hozzárendeléséhez.
6.  Kattintson a **Bezárás** lehetőségre a **Vállalatok** párbeszédpanel bezárásához. Az Ön által kijelölt építőelem-csoport a vállalathoz hozzárendelésre került. Ezt követően az összes új sordefiníció, oszlopdefiníció stb., amelyet létrehoznak a vállalathoz hozzárendelt építőelem-csoport része lesz. Importálhat .tdbx fájlt vagy a jelentést egy másik rendszerből is.

### <a name="view-a-building-block-group"></a> Építőelem-csoport megtekintése

Építőelem-csoport létrehozását követően, a használatakor megtekintheti az összes építőelemet, amely hozzá van rendelve. Képes továbbá exportálni vagy importálni egy építőelem csoportot, és további karbantartást végrehajtani az építőelem-csoportokon.
1.  A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2.  Az **Építőelem-csoportok** párbeszédpanelben válassza ki a megtekinteni kívánt építőelemet.
3.  Kattintson a **Nézet** lehetőségre az **Építőelem-csoport megtekintése** párbeszédpanel megnyitásához, ahol megtekintheti az építőelem-csoport tartalmát.
4.  Kattintson a **Bezárás** gombra a párbeszédpanel bezárásához.

### <a name="save-a-building-block-group-under-a-new-name"></a>Mentse el új néven az építőelem-csoportot

Új néven el tud menteni egy meglévő építőelem-csoportot. Ezután anélkül tudja módosítani az új építőelem-csoportot, hogy az hatással lenne az eredeti építőelem-csoportra.
1.  A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2.  Az **Építőelem-csoportok** párbeszédpanelen jelölje ki az új néven menteni kívánt építőelem-csoportot.
3.  Kattintson a **Mentés másként** lehetőségre.
4.  Adjon új nevet és leírást az építőelem-csoportnak.
5.  Kattintson az **OK** gombra. Az új építőelem-csoport az **Építőelem-csoportok** párbeszédpanelben jelenik meg.

### <a name="export-a-building-block-group"></a> Építőelem-csoport exportálása

Exportálhat építőelem-csoportokat vagy adott építőelemeket egy építőelem-csoportból. Az exportált építőelem-csoportokat használhatja biztonsági mentésnek. Az exportált adatokat építőelem csoportok vagy a Dynamics 365 for Operations programok között is másolhatja. A Jelentéstervező tartalmazza a hivatkozott betűstílusokat és a dimenziókészleteket, az építőelem-csoportokkal együtt.
1.  A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2.  Jelölje ki az **Építőelem-csoportok** párbeszédpanelben az exportálni kívánt építőelem-csoportot, majd kattintson az **Exportálás** lehetőségre.
3.  Jelölje ki az exportálandó jelentésdefiníciókat az **Exportálás** párbeszédpanelben:
    -   Az összes jelentésdefiníció illetve a társított építőelemek exportálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket. Ha több tételt szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt. **Megjegyzés:** Ha exportálandó jelentéseket jelöl ki, úgy kiválasztásra kerülnek a társított sorok, oszlopok, fák és dimenziókészletek is.

4.  Ha végzett az exportálandó cikkek kiválasztásával, kattintson az **Exportálás** lehetőségre.
5.  A **Mentés másként** párbeszédpanelben jelölje ki, hogy hová szeretné exportálni az építőelem-csoportot.
6.  Adja meg a fájlnevet a **Fájlnév** mezőben. A Jelentéstervező eszköz automatikusan .tdbx kiterjesztést illeszt a fájlnév végére.
7.  Kattintson a **Mentés** gombra. Az építőelem-csoport az Ön által megadott helyre kerül elmentésre.

### <a name="import-a-building-block-group"></a> Építőelem-csoport importálása

Importálhat építőelem-csoportokat egy meglévő építőelem-csoportba, vagy létrehozhat egy új építőelem-csoportot az adatokhoz. Az összes importált építőelem-csoport megtartja az eredeti betűstílusát és a vállalati hivatkozásait, és tartalmazza a megfelelő dimenziókészleteket.
1.  A Jelentéstervezőben, a **Vállalat** menüben kattintson az **Építőelem-csoportok** lehetőségre.
2.  Jelölje ki az **Építőelem-csoportok** párbeszédpanelben, hogy melyik építőelembe kívánja importálni az építőelemet-csoportot, majd kattintson az **Importálás** lehetőségre.
3.  Jelölje ki a **Megnyitás** párbeszédpanelben az importálni kívánt építőelem-csoportot, majd kattintson a **Megnyitás** lehetőségre.
4.  Jelölje ki az importálandó jelentésdefiníciókat az **Importálás** párbeszédpanelben:
    -   Az összes jelentésdefiníció illetve az azt támogató építőelemek importálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.

5.  Ha végzett az importálandó cikkek kiválasztásával, kattintson az **Importálás** lehetőségre.

### <a name="undo-a-checkout-of-a-building-block"></a>Építőelem kivételének visszavonása

Amikor megnyit egy építőelemet, a többi felhasználó csak olvasásra kap hozzáférést ahhoz az elemhez. Előfordulhat, hogy a felhasználók elfelejtik bezárni az építőelemeket, vagy kikapcsolják a rendszerüket az építőelem bezárása nélkül. Így az építőelem továbbra is kivett állapotú marad, és azt a többi felhasználó nem tudja megnyitni. Ilyen esetekben a pénzügyi jelentések rendszergazdája a **Kivett cikkek** párbeszédpanel segítségével, vissza tudja venni a másik felhasználó által kivett állapotban felejtett építőelemeket. **Megjegyzés:** Csak rendszergazda szerepkörrel lehet építőelemet visszavenni a **Kivett cikkek** párbeszédpanel használatával.
1.  A Jelentéstervező **Eszközök** menüjében kattintson a **Kivett cikkek** lehetőségre.
2.  A **Kivett cikkek** párbeszédpanelben válassza a **Minden felhasználó minden cikkének megjelenítése** lehetőséget. A rendszer frissíti az összes kivett építőelemet, illetve az érintett felhasználókat megjelenítő listát.
3.  Jelöljön ki egy építőelemet majd kattintson a **Kivétel visszavonása** parancsra.
4.  Az építőelem visszavételéhez kattintson az **Igen** lehetőségre.

# <a name="see-also"></a>Lásd még

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)




