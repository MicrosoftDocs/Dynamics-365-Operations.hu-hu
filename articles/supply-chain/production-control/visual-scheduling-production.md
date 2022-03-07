---
title: Munkaütemezés Gantt-diagram segítségével
description: A gyártástervezők Gantt-diagramok segítségével szabályozhatják és optimalizálhatják a termelési terveket.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage, GanttColorTable, GanttReqExplosionColor, GanttReqExplosionSetup, GanttTable, GanttTimescaleSetup, GanttWrkCtr, GanttWrkCtrColor, GanttWrkCtrJobInfo, GanttWrkCtrLoadResources, GanttWrkCtrMoveJob, GanttWrkCtrSetup, GanttWrkCtrView
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97fc3c6bd096854b5aa72980dd2bd6f3a8a1ef9e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353420"
---
# <a name="gantt-chart-for-job-scheduling"></a>Munkaütemezés Gantt-diagram segítségével

[!include [banner](../includes/banner.md)]

A Gantt-diagramot úgy tervezték, hogy a termeléstervezők számára lehetővé tegyék a termelési terv ellenőrzését és optimalizálását. A Gantt-diagram átlátja a műveletek áramlását, és megkönnyíti a termelési ütemezés módosítását, figyelembe véve az anyagi vagy erőforráshiányt. Ez segít abban, hogy a tervezők a rendelkezésre álló erőforrásokat a lehető legjobban kihasználják, minimalizálják a folyamatban lévő munkákat, valamint optimalizálják a termelési rendelések átfutási idejét.

A Gantt-diagram a beütemezett tevékenységek vizuális megjelenítése a megadott időintervallumon belül. A tevékenységek ütemezése olyan erőforrásokra vonatkozik, amelyek a kapacitási naptár által meghatározott kapacitással rendelkeznek. A Gantt-diagramon a következő típusú tevékenységek jeleníthetők meg.

-   Termelési rendelésekből ütemezett feladatok.
-   Tervezett termelési rendelések feladatai.
-   Óra-előrejelzések típusú ütemezett projekttevékenységek.

A Gantt-diagram két különböző nézetben nyitható meg – ezek a **Rendelés nézet** és az **Erőforrás nézet**. A **Rendelés nézet** alatt a tevékenységek csoportosítása termelési rendelések szerint történik. Ez hasznos lehet például olyankor, ha meg szeretné tartani az azonos rendelésekhez tartozó összes feladat áttekintését. Az **Erőforrás nézetben** az összes feladat az egyes erőforrások alatt van csoportosítva. Ez a nézet akkor lehet hasznos, amikor a tervet az erőforrás szintjén optimalizálja, például egy gép vagy gépek csoportja esetén. Az alábbi ábrákon látható Gantt-diagramok a **Rendelés megtekintése** és az **Erőforrás nézet** nézeteket jelenítik meg a következő kulcselemekkel:

1.  Gantt-diagram tevékenysége
2.  Anyaghiány ikon
3.  Anyagelérhetőség ikon
4.  Rendelés szállítási dátuma ikon
5.  Kapacitássáv

## <a name="order-view"></a>Rendelés nézet

[![Rendelés nézet.](./media/orderview.png)](./media/orderview.png)

## <a name="resource-view"></a>Erőforrás nézet
[![Erőforrás nézet.](./media/resview.png)](./media/resview.png)

## <a name="activities"></a>Tevékenységek
A tevékenységek sávok formájában jelennek meg, és ütemezett kezdési és befejezési időpontba szerveződnek egy időskálarácson, így a sávok hossza arányos a tevékenység befejezéséhez szükséges idővel. A tevékenységek egy időskálának megfelelően jelennek meg. Beállíthatja az időskálát a menüben, ahol kiválaszthatja a kezdő és záródátumot és az időegységet, például órákat vagy napokat. Az időskála beállításával meghatározhatja a fókuszt olyan időintervallumra, amelyben a tevékenységeket szeretné kezelni. 

A jobb áttekintés érdekében különböző beállítások segítségével színeket rendelhet a tevékenységekhez. Egyéni színeket rendelhet az egyes tevékenységekhez, használhatja az alkalmazáshoz használt általános színtémát, vagy beállíthatja a termelési rendelések színkódjával ellenőrzött színt. 

A tevékenységek időintervallumának háttérszíne van. A fehér árnyalatok jelölik a tevékenység erőforrására vonatkozó definiált kapacitású intervallumokat, a szürke árnyalatok pedig a nem definiált kapacitású időintervallumokat jelölik. 

A diagram bal oldalán kiegészítő információkat talál a tevékenységről, például azt az erőforrást, amelyre a tevékenységet ütemezték vagy a termelési rendelés számát. Az ugyanabba a sorrendbe tartozó feladatok közötti kapcsolat nyíllal van jelölve. 

A tevékenységgel kapcsolatban további információkat kaphat a tevékenység párbeszédpanelében. A párbeszédpanel megnyitásához kattintson duplán a tevékenységre, vagy válassza az **Adatok** menüt. A tevékenység párbeszédpanelen látható az ütemezett kezdési és záródátum, valamint és időadatok azzal kapcsolatban, hogy a tevékenység milyen anyagokat tervezett felhasználásra. 

A tevékenységeket Csoportosítási szintekre lehet csoportosítani. A Csoportosítási szintek hierarchikusak, és a tevékenységek logikai csoportosításaként használhatók. Ha például olyan elrendezéssel rendelkezik, amelyben a gyártási tevékenységek Hely, Termelési egységek, Erőforráscsoportok és Erőforrások szerint vannak csoportosítva, a Csoportosítási szintek segítségével csoportosíthatja a tevékenységeket az adott elrendezés szerint. A csoportosítási szintek kibonthatók és becsukhatók az egyes csoportosítási szinten vagy a diagram összes szintjén az **Összes kibontása** és az **Összes becsukása** a menügombokkal. Beállíthatja azt is, hogy a csoportosítási szintek kibontása vagy összecsukása következzen be a diagram megnyitásakor.

### <a name="material-availability"></a>Anyagok elérhetősége

A Gantt-diagramot be lehet állítani, hogy részletes információkkal lássa el a tervezőt az egyes tevékenységek anyagállapotára vonatkozóan. Ez például akkor lehet hasznos, ha az anyag késik, és ez befolyásolja a termelési tervet. Ebben az esetben az anyaggal kapcsolatos problémák kiemelten jelennek meg a Gantt-diagramon, segítve a tervezőt a következmények megértésében és a szükséges kiigazítások elvégzésében. 

A feladat anyaghiány ikonnal jelenik meg, ha a feladatütemezés kezdő dátuma későbbre esik, mint a feladat által felhasznált anyagok elérhetőségi dátuma. Az anyagelérhetőségi dátum kiszámítása a dinamikus alapterv a rögzítési adatainak alapján történik. Az anyaghiány ikon megjelenik például egy olyan feladatnál, amely olyan anyagot használ, amelynek termelési rendelésén megjelenő bevételezési dátum később van a feladat tervezett kezdő dátumánál.

### <a name="indicator-of-material-availability-date"></a>Az anyagelérhetőségi dátum jelzője

Ha a diagramot úgy állítja be, hogy az anyaghiányos feladatokat jelenítse meg, megjelenhet egy olyan ikon is, amely megjeleníti a feladat anyagelérhetőségének dátumát. Az ikon csak akkor jelenik meg, ha az anyagok elérhetőségi dátuma a diagram megadott időintervallumában van. Ha az anyagok elérhetőségi dátuma a megadott időintervallumon kívül esik, részletesebb anyagelérhetőségi adatok kérhetők le a feladat párbeszédpanelének anyaglistájáról. A listában szerepel egy ikon is, amelye a feladat késedelmes anyagait jeleníti meg. Újraütemezheti a feladatot az anyagok rendelkezésre állása dátumának kezdő dátumként történő beállításával.

### <a name="indicator-of-order-delivery-date"></a>Rendelés kiszállítási dátumának kijelzője

Ez az ikon a termelési rendelés szállítási dátumát jelzi. Az ikon csak Rendelés nézetben látható.

### <a name="capacity-bar"></a>Kapacitássáv

Beállíthatja, hogy a diagram megjelenítsen egy erőforrás-kapacitási sávot. Ez a sáv áttekintést nyújt a tevékenység erőforrás-kapacitásával kapcsolatban a diagram megadott időintervallumában. A kapacitás sáv nem jelenik meg olyankor, amikor az erőforrás nem foglalt. Az olyan időszakokban, amelyekben az erőforrás kapacitása le van foglalva, a kapacitássáv szilárd sávként jelenik meg. Azon időszakokban, amikor az erőforrás túl van foglalva, a sáv vastagabb és piros színnel jelenik meg. Például ha két feladat átfedésben van, a kapacitássáv túlfoglalást jelez az átfedési időszakra vonatkozóan. A kapacitássáv dinamikusan frissül egy feladat ütemezésekor. A kapacitássávot a **Kapacitássáv megjelenítése** menüben engedélyezheti. Csak az **Erőforrás nézetben** jeleníthető meg. Ha részletesebb képet szeretne kapni egy erőforrás kapacitásterheléséről, használja a **Kapacitásterhelés** diagramot, amelyet a kiválasztott tevékenységre vonatkozó menüből vagy a helyi menüből nyithat meg.

## <a name="job-scheduling-in-the-gantt-chart"></a>Munkaütemezés a Gantt-diagramban
A Gantt-diagram eltérő beállításokat kínál termelési terv kiigazításához. A Gantt-diagramon húzással történő áthelyezési interakcióval vagy egy ütemezési menüből újraütemezheti a tevékenységeket. A tervezési folyamatban figyelembe veheti az erőforrás-kapacitást, az erőforrásokhoz rendelt képességeket és az anyagelszámolású korlátozásokat.

### <a name="schedule-a-job-as-a-drag-and-drop-interaction"></a>Ütemezzen egy feladatot húzással történő áthelyezési interakcióval

A megadott időintervallumon belül újraütemezhet egy feladatot húzással történő áthelyezési interakcióként. A feladatot csak ugyanahhoz az erőforráshoz üótemezheti újra, és csak egy feladatot ütemezhet egyszerre.

### <a name="schedule-a-job-from-the-menu"></a>Feladat ütemezése a menüből

A **Feladatok ütemezése** menüben a diagramon levő egy vagy több feladatot ütemezheti az ütemezési irány és az ütemezési dátuma alapján. Három ütemezési irány érhető el.

-   A tervezés dátumától előre
-   Visszafelé az ütemezési dátumtól
-   Továbbítás az anyagelérhetőségi dátumból

Nincs lehetőség a Gantt-diagram megadott időintervallumán kívül eső feladat ütemezésére. Ha ezt teszi, a feladat nem tervezett állapotú marad, és a következő hibaüzenet jelenik meg: a „A betöltött időszak alatt nem sikerült ütemezni a feladatot.”

### <a name="schedule-previous-jobs"></a>Előző feladatok ütemezése

A tevékenységhálózatban, például az azonos termelési rendeléshez tartozó feladatok esetében használhatja az **Előző feladatok ütemezése** funkciót a hálózatban található kijelölt feladathoz képest előző feladat ütemezésére. A következő példában a kijelölt tevékenység a kijelölt feladat. Az ábra a korábbi feladat ütemezése előtti és a korábbi feladat ütemezése utáni állapotot mutatja. 

[![Előző feladat ütemezése.](./media/schprevjob3.png)](./media/schprevjob3.png)

### <a name="schedule-next-jobs"></a>Következő feladatok ütemezése

Használhatja a **Következő feladatok ütemezése** funkciót a tevékenységi hálózaton a kijelölt feladathoz képest a következő feladatok ütemezésére. A következő példában a kijelölt tevékenység a kijelölt feladat. Az ábra a következő feladat ütemezése előtti és a következő feladat ütemezése utáni állapotot mutatja. 

[![Következő feladat ütemezése.](./media/schnxtjob.png)](./media/schnxtjob.png)

### <a name="schedule-around-job"></a>Feladatokhoz alkalmazkodó ütemezés

Használhatja a **Feladatokhoz alkalmazkodó ütemezés** funkciót a tevékenységi hálózaton a következő feladat és a kijelölt feladathoz képest az előző feladat ütemezésére. A következő példában a kijelölt tevékenység a kijelölt feladat. Az ábra a feladat ütemezése előtti és a feladat ütemezése utáni állapotot mutatja. 

[![Feladatokhoz alkalmazkodó ütemezés.](./media/scharoundjob1.png)](./media/scharoundjob1.png)

### <a name="arrange-jobs"></a>Munkák elrendezése

Az **Elrendezés** funkcióval a kiválasztott tevékenységeket ugyanazon az erőforráson rendezheti el. Ezek a tevékenységek ugyanazon tevékenységi hálózatba is tartozhatnak, de akár különböző hálózatok részei is lehetnek. Ha az Elrendezési funkciót használja, a kiválasztott tevékenységek közötti időhiányok megszűnnek. Ezen funkció segítségével optimalizálhatja az erőforrások kapacitásának kihasználtságát. Az ábra a feladat ütemezése előtti és a feladat ütemezése utáni állapotot mutatja. 

[![Feladat elrendezése.](./media/arrangejobs1.png)](./media/arrangejobs1.png)

### <a name="reassign-activities-from-one-resource-to-another"></a>Tevékenységek ismételt hozzárendelése egyik erőforrásról a másikra

Lehetősége van egy feladat egyik erőforrásról a másikra történő ismételt hozzárendelésére. Ez akkor lehet hasznos, ha egy gép meghibásodott vagy túlfoglalt, és szeretné találni egy másik olyan szabad erőforrást, amely elvégezné a feladatot.

### <a name="reassigning-an-activity-as-a-drag-and-drop-interaction"></a>Ismételt hozzárendelés húzással történő elhelyezési interakcióval

A **Erőforrás** nézetben húzással történő elhelyezéssel rendelheti ismételten hozzá a tevékenységet egy másik erőforráshoz a Gantt-diagramon. Ezt úgy teheti meg, hogy kiválasztja azt a sort, amelyben a tevékenység be van ütemezve. A sor kijelölését követően áthúzhatja a sort a diagramban másik erőforrás csoportosítási szintjére.

### <a name="reassigning-an-activity-from-the-schedule-jobs-menu"></a>Tevékenység ismételt hozzárendelése a Feladatok ütemezése menüből

A **Feladat ütemezése** párbeszédpanelnek a **Feladat ütemezése** menüben történő megnyitásával ismételten hozzárendelheti a feladatot. Ebben a menüben csak olyan feladatot rendelhet hozzá ismételten egy erőforráshoz, amely már be van töltve a Gantt-diagramba. Ha csak egy feladatot választ ki, az erőforrás legördülő listája az alkalmazható erőforrások szerint lesz elrendezve. Ha több feladatot választ ki, nem jelennek meg adatok az alkalmazható erőforrásokkal kapcsolatban az erőforráslistából.

## <a name="load-additional-resources-to-the-gantt-chart"></a>További erőforrások betöltése a Gantt-diagramhoz
Az **Erőforrás nézetben** kiválaszthatja, hogy további erőforrásokat tölt-e be a Gantt-diagramhoz. Ez akkor lehet hasznos, ha egy túlfoglalt vagy meghibásodott gépre ütemezett feladathoz szeretne másodlagos erőforrást keresni. A **További erőforrások betöltése** lapon a lista megnyitásának időpontjától naprakész erőforrások listája jelenik meg. Először a Gantt-diagramon kijelölt feladathoz kapcsolódó alkalmazható erőforrások jelennek meg. Ha több feladatot jelölt ki a lista megnyitása előtt, az alkalmazható erőforrások nem jelennek meg. A **További erőforrások betöltése** lapon kiválaszthat egy vagy több erőforrást, amelyeket a rendszer betölt a Gantt-diagramra, miután megerősítette a választását. Ha nincsenek feladatok ütemezve a kiválasztott erőforráson a Gantt-diagram időintervallumában, az erőforrás egy erőforrás-csoportosítási szintre kerül a Gantt-diagramon levő tevékenységek listájának aljára.

### <a name="access-the-gantt-chart"></a>Hozzáférés a Gantt-diagramhoz

A Gantt-diagram a következő lapokról is megnyitható.


|                                                 <strong>Lap</strong>                                                  |                                                                                                                                                                                                                                                            <strong>Leírás</strong>                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   <strong>Termelési rendelési lista és részletek</strong>                                    | A <strong>Termelési rendelési lista és részletek</strong> lapon a Gantt-diagramot egy vagy több kijelölt rendelésből is megnyithatja. Ha a diagramot a <strong>Gantt-diagram</strong> menüelemből nyitja meg, ez betölti a kiválasztott termelési rendelésekhez kapcsolódó összes feladatot, valamint ugyanazon erőforrásokra ütemezett termelési rendelések feladatait is. A <strong>Gantt-diagram – Gyorsnézet</strong> menüelemből történő megnyitása csak a kiválasztott termelési rendelésekhez kapcsolódó feladatokat tölti be. Ebben a nézetben nincs lehetőség feladatok ütemezésére. |
|                                               <strong>Erőforrás</strong>                                                |                                                                                                                                                        Az <strong>Erőforrás</strong> lapon a Gantt-diagramot a <strong>Gantt-diagram</strong> menüelemből nyithatja meg. Ha ki van választva, az erőforrásra a kiválasztott időintervallumban ütemezett összes feladat betöltődik a diagramon.                                                                                                                                                         |
|                                            <strong>Erőforráscsoport</strong>                                             |                                                                                                                                                 Az <strong>Erőforráscsoport</strong> lapon a Gantt-diagramot a <strong>Gantt-diagram</strong> menüelemből nyithatja meg. Ha ki van választva, az erőforráscsoportban levő erőforrásokra a kiválasztott időintervallumban ütemezett összes feladat betöltődik a diagramon.                                                                                                                                                 |
|                                             <strong>Gantt-diagramok</strong>                                              |                                                                                 A <strong>Gantt-diagramok</strong> lapon a Gantt-diagramokat erőforrások és erőforráscsoportok szerint konfigurálhatja. Ha például ellenőrizni szeretné az erőforrások vagy erőforráscsoportok konkrét csoportjába tartoztó termelési tevékenységeket, egyedi beállításokat végezhet rajtuk a <strong>Gantt-diagramok</strong> lapon. Ezután minden konfigurációból megnyithatja a Gantt-diagramot.                                                                                 |
|                                       <strong>Óra-előrejelzések</strong> (projekt)                                        |                                                                                                                              Az <strong>Óra-előrejelzések</strong> típusú ütemezett projekttevékenységek erőforrásokra ütemezett feladatok lehetnek. Az <strong>Óramennyiség előrejelzése</strong> lapon az <strong>Ütemezés</strong> menüben megnyithatja a Gantt-diagramot megjelenítéséhez az óra-előrejelzések típusú ütemezett projekttevékenységek feladatot.                                                                                                                               |
|           <strong>Végrehajtandó feladat</strong> (A <strong>Termelési szint kezelése</strong> munkaterület listája)            |                                                                                               A <strong>Termelési szint kezelésében végrehajtandó feladatok listája</strong> munkaterület azon termelési és kötegrendelések feladait jeleníti meg, amelyek a munkaterület kijelölt erőforrásain folyamatban vannak. A <strong>Gantt-diagram</strong> menüelemben megnyithatja a Gantt-diagramot, ahol a listában kiválasztott összes feladat betöltődik a diagramra.                                                                                               |
| <strong>Kiadandó termelési rendelések</strong> (A <strong>Termelési szint kezelése</strong> munkaterületből megnyitva) |                                                                                                                                         A Kiadandó termelési rendelések lapot a <strong>Termelési szint kezelése</strong> munkaterületből nyitja meg. Ez a lap megmutatja a függő kiadásban levő ütemezett termelési és kötegrendeléseket. Ezen a lapon megnyithatja a Gantt-diagramot a kiválasztott termelési rendelésekhez.                                                                                                                                          |

## <a name="additional-resources"></a>További erőforrások  
[Vizuális ütemezés a Gantt-diagrammal a termelési és kötegrendelésekhez (videó)](https://youtu.be/BtbuShkGj4I)

[Vizuális ütemezés a termeléshez (demó parancsfájl)](/dynamics/s-e/)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]