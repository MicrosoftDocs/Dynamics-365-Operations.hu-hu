---
title: Költségvetés-tervezési sablonok az Excel programhoz
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni Microsoft Excel a költségvetési tervekkel használható sablonokat.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: kfend
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6bc190a48d0212e24c5bd72255ed6b6b3caf942c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872499"
---
# <a name="budget-planning-templates-for-excel"></a>Költségvetés-tervezési sablonok az Excel programhoz

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni Microsoft Excel a költségvetési tervekkel használható sablonokat.

Ez a cikk bemutatja, hogyan lehet létrehozni a költségvetési tervekhez használt Excel-sablonokat a normál bemutató adathalmaz és az Admin felhasználói bejelentkezés segítségével. Költségvetés-tervezéssel kapcsolatos további tudnivalók: [A költségvetés-tervezés áttekintése.](budget-planning-overview-configuration.md) A modul alapvető konfigurációjának és használati elveinek megismeréséhez végigcsinálhatja a [Költségvetés-tervezés](budget-plan.md) oktatóprogramot.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Munkalap létrehozása költségvetési terv dokumentumelrendezésben

A költségvetésiterv-dokumentumok egy vagy több elrendezés használatával tekinthetők meg és szerkeszthetők. Minden elrendezéshez tartozhat egy kapcsolódó költségvetésiterv-dokumentumsablon, amely a költségvetési terv adatainak Excel-munkalapon történő megtekintésére és szerkesztésére szolgál., Ebben a cikkben egy költségvetésiterv-dokumentumsablont egy meglévő elrendezéskonfigurációval hoz létre a rendszer. 

1. Nyissa meg a **Költségvetési tervek listája** (**Költségvetés készítése** &gt; **Költségvetési tervek**) elemet. 
2. Új költségvetésiterv-dokumentum létrehozásához kattintson az **Új** gombra. 

   [![Költségvetési tervek listája.](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Használja a **Hozzáadás** elemet sorok hozzáadásához. Kattintson az **Elrendezések** elemre a költségvetésiterv-dokumentum elrendezési konfigurációjának megtekintéséhez. 

   [![Költségvetési tervek hozzáadása.](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Áttekintheti és szükség szerint módosíthatja az elrendezés konfigurációját. 
1. Ha Excel-fájlt akar létrehozni ehhez az elrendezéshez, lépjen a **Sablon** &gt; **Létrehozás** elemre. 
2. A sablon létrejötte után a költségvetésiterv-dokumentumsablon megnyitásához és áttekintéséhez lépjen a **Sablon** &gt; **Nézet** elemre. Az Excel-fájlt elmentheti a helyi meghajtóra. 

[![Mentés másként.](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> A költségvetésiterv-dokumentum elrendezését nem lehet szerkeszteni, miután egy Excel-sablonhoz lett társítva. Az elrendezés módosításához törölje a kapcsolódó Excel-sablonfájlt, és hozza létre újra. Ez az elrendezésben és a munkalapon lévő mezők szinkronizálásának megtartásához szükséges. 

Az Excel-sablon tartalmazza az összes olyan elemet a költségvetésiterv-dokumentumelrendezésből, ahol az **Elérhető a munkalapon** oszlop értéke Igaz. Egymást átfedő elemek nem használhatók az Excel-sablonban. Például ha az elrendezés 1. n.évi kérelem, 2. n.évi kérelem, 3. n.évi kérelem és 4. n.évi kérelem oszlopokat tartalmaz, és van egy összegző oszlop, amely a 4 negyedévi oszlop összegét tartalmazza, csak a negyedévi oszlopok vagy az összegző oszlop használható fel az Excel-sablonban. Az Excel-fájl nem tud átfedésben lévő oszlopokat frissíteni a frissítés során, mivel a tábla adatai elavultakká és pontatlanná válhatnak.

> [!NOTE] 
> A költségvetési terv adatainak az Excel Microsoft Dynamics használatával történő megtekintésével és szerkesztésével kapcsolatos esetleges problémák elkerülése érdekében ugyanazt a felhasználót be kell jelentkeznie a 365 Pénzügy Microsoft Dynamics és az Office-bővítmény Data Connector alkalmazásba is.

## <a name="add-a-header-to-budget-plan-document-template"></a>Fejléc felvétele költségvetésiterv-dokumentum sablonjába
Fejlécadatok hozzáadásához jelölje ki a felső sort az Excel-fájlban, és illesszen be üres sorokat. Kattintson a **Tervezés** elemre az **Adatcsatlakozóban** a fejlécmezők az Excel-fájlhoz történő hozzáadásához.

A **Tervezés** lapon kattintson a **Hozzáadás** mezőre, és válassza ki a **BudgetPlanHeader** elemet az entitás adatforrásaként.

Vigye a kurzort a kívánt helyre az Excel fájlban. Kattintson a **Címke hozzáadása** elemre a mezőfelirat a kijelölt helyen történő hozzáadásához. Válassza az **Érték hozzáadása** elemet az értékmező a kijelölt helyre történő hozzáadásához. A tervező bezárásához kattintson a **Kész** gombra.

## <a name="select-add-valuemediabpt7png"></a>[![Az Érték hozzáadása lehetőség kiválasztása.](./media/bpt7.png)](./media/bpt7.png)

## <a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Számított oszlop felvétele költségvetésiterv-dokumentum táblájába

Ezután következik a számított oszlopok hozzáadása a létrehozott költségvetésiterv-dokumentumsablonhoz. Ezek egy **Teljes kérelem** oszlop, amely összesíti az 1. n.évi kérelem:4. n.évi kérelem oszlopokat, és egy **Kiigazítás** oszlop, amely egy előre megadott tényezővel újraszámolja a **Teljes kérelem** oszlopot.

Kattintson a **Tervezés** elemre az **Adatcsatlakozóban** oszlopok a táblához történő hozzáadásához. Kattintson a **Szerkesztés** elemre a **BudgetPlanWorksheet** adatforrás mellett az oszlopok felvételének megkezdéséhez.

[![Oszlopok hozzáadásának megkezdése.](./media/bpt8-1024x301.png)](./media/bpt8.png) 

A kiválasztott mezőcsoport megjeleníti a sablonban elérhető oszlopokat. Kattintson a **Képlet** lehetőségre egy új oszlop hozzáadásához. Adjon nevet az új oszlopnak, majd illessze be a képletet a **Képlet** mezőbe. Az oszlop beillesztéséhez kattintson a **Frissítés** elemre.

[![Oszlop hozzáadása és beszúrása.](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> A képlet megadásához hozza létre a képletet a táblázatban, majd másolja a **Tervezés** ablakba. A Finance and Operationshöz kapcsolt táblák neve általában „AXTable1”. Például az 1. n.évi kérelem : 4. n.évi kérelem oszlopok a táblázatban való összegzésére szolgáló képlet = AxTable1\[1. n.évi kérelem\]+AxTable1\[2. n.évi kérelem\]+AxTable1\[3. n.évi kérelem\]+AxTable1\[4. n.évi kérelem\].

Ismételje meg ezeket a lépéseket a **Kiigazítás** oszlop beillesztéséhez. Ennél az oszlopnál használja az = AxTable1\[Teljes kérelem\]\*$I$1 képletet. Ez veszi az I1 cella értékét, és megszorozza **Teljes kérelem** oszlop értékeit a helyesbítési összegek kiszámításához.

Mentse és zárja be az Excel-fájlt. Az **Elrendezések** részben kattintson a **Sablon &gt; Feltöltés** elemre a mentett és a költségvetési tervhez használandó Excel-sablon feltöltéséhez. 

[![Excel-sablon feltöltése.](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Zárja be az **Elrendezések** csúszkát. A **Költségvetési terv** dokumentumban, kattintson a **Munkalap** elemre a dokumentum Excelben történő megtekintéséhez és szerkesztéséhez. Ne feledje, hogy a kiigazított Excel-sablont használtuk ezen költségvetésiterv-munkalap létrehozásához, és hogy a számított oszlopok az előző lépésben megadott képletek alapján frissülnek. 

[![A dokumentum megtekintése és szerkesztése az Excel programban.](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Tippek és trükkök költségvetésiterv-sablonok létrehozásához
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Felvehetek és használhatok további adatforrásokat költségvetésiterv-sablonoknál?

Igen, a **Tervező** menüben további entitásokat is hozzáadhat az Excel-sablon ugyanazon vagy más lapjaihoz. Hozzáadhatja például a **BudgetPlanProposedProject** adatforrást, és költségvetésiterv-adatok az Excelben történő feldolgozásával egy időben létrehozhat és karbantarthat vele lehet egy javasolt projektek listáját. Fontos megjegyezni, hogy nagy mennyiségű adatforrás használata csökkentheti az Excel munkafüzet teljesítményét. 

Az **Adatcsatlakozó** **Szűrő** lehetőségével tetszés szerinti szűrőket adhat hozzá a további adatforrásokhoz.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Elrejthetem a Tervezés lehetőséget az Adatcsatlakozóban más felhasználók elől?

Igen, nyissa meg az **Adatcsatlakozó** beállításait, ha el kívánja rejteni a **Tervezés** funkciót más felhasználók elől.

[![Az Adatcsatlakozó beállításainak megnyitása.](./media/bpt13-1024x565.png)](./media/bpt13.png)

Bontsa ki az **Adatcsatlakozó beállításai** elemet, és törölje a **Tervezés engedélyezése** jelölőnégyzetet. Ez elrejti a **Tervezés** funkciót az **Adatcsatlakozóból**.

[![A Tervezés beállítás elrejtése az Adatcsatlakozóban.](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Megakadályozhatom, hogy a felhasználók adatokkal való munkavégzés közben véletlenül bezárják az Adatcsatlakozót?

Ajánlott zárolni a sablont, hogy a felhasználók ne tudják bezárni. A zárolás bekapcsolásához kattintson az **Adatcsatlakozó** elemre, és a jobb felső sarokban megjelenik egy nyíl. 

[![A zárolás bekapcsolása.](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Kattintson a nyílra a további menü megjelenítéséhez. Válassza a **Zárolás** elemet.

### <a name="select-lockmediabpt16png"></a>[![A Zárolás elem kiválasztása.](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Használhatok más Excel-funkciókat, például cellaformázást, színeket, feltételes formázást és diagramokat a költségvetésiterv-sablonokhoz?

Igen, a legtöbb normál Excel-funkció működik a költségvetésiterv-sablonokban. Színkódolás használata ajánlott, hogy a felhasználók különbséget tudjanak tenni a csak olvasható és a szerkeszthető oszlopok között. A feltételes formázás segítségével kiemelhetők a költségvetés problémás területei. Az oszlopösszegek könnyen megjeleníthetők a táblázat felett szokásos Excel-képletek segítségével.

Emellett létrehozhatók és használhatók kimutatások és diagramok a költségvetési adatok további csoportosítása és képi megjelenítése érdekében. Az **Adatok** lapon, a **Kapcsolatok** csoportban kattintson a **Mindent frissít** elemre, majd kattintson a **Kapcsolat tulajdonságai** elemre. Kattintson a **Használat** lapra. A **Frissítés** részben jelölje be az **Adatfrissítés a fájl megnyitásakor** jelölőnégyzetet. 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
