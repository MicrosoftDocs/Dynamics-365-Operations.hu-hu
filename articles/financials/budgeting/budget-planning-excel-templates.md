---
title: "Költségvetés-tervezési sablonok Excelhez"
description: "Ez a témakör ismerteti, hogyan hozhatók létre költségvetési tervekhez használt Microsoft Excel-sablonok."
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 156688b705337331e083ebc19fded57b028acb67
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-templates-for-excel"></a>Költségvetés-tervezési sablonok Excelhez

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogyan hozhatók létre költségvetési tervekhez használt Microsoft Excel-sablonok.

Ez a témakör azon Excel-sablonok létrehozásának módját mutatja be, amelyek költségvetési tervekhez használhatók a normál bemutató adatkészlet és rendszergazdai felhasználói bejelentkezés használatával. Költségvetés-tervezéssel kapcsolatos további tudnivalókért lásd: [A költségvetés-tervezés áttekintése.](budget-planning-overview-configuration.md) Végigcsinálhatja a [Költségvetés-tervezés 101](budget-plan.md) oktatóprogramot is a modul alapvető konfigurációjának és használati elveinek megismeréséhez.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Munkalap létrehozása költségvetési terv dokumentumelrendezésben

A költségvetésiterv-dokumentumok egy vagy több elrendezés használatával tekinthetők meg és szerkeszthetők. Minden elrendezéshez tartozhat egy kapcsolódó költségvetésiterv-dokumentumsablon, amely a költségvetési terv adatainak Excel-munkalapon történő megtekintésére és szerkesztésére szolgál., Ebben a témakörben a költségvetési terv dokumentumsablonját egy meglévő elrendezéskonfiguráció segítségével hozzuk létre. 

1. Nyissa meg a **Költségvetési tervek listája** (**Költségvetés készítése** &gt; **Költségvetési tervek**) elemet. 
2. Új költségvetésiterv-dokumentum létrehozásához kattintson az **Új** gombra. 

   [![Költségvetési tervek listája](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Használja a **Hozzáadás** elemet sorok hozzáadásához. Kattintson az **Elrendezések** elemre a költségvetésiterv-dokumentum elrendezési konfigurációjának megtekintéséhez. 

   [![Költségvetési tervek hozzáadása](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Áttekintheti és szükség szerint módosíthatja az elrendezés konfigurációját. 
1. Ha Excel-fájlt akar létrehozni ehhez az elrendezéshez, lépjen a **Sablon** &gt; **Létrehozás** elemre. 
2. A sablon létrejötte után a költségvetésiterv-dokumentumsablon megnyitásához és áttekintéséhez lépjen a **Sablon** &gt; **Nézet** elemre. Az Excel-fájlt elmentheti a helyi meghajtóra. 

[![Mentés másként](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> A költségvetésiterv-dokumentum elrendezését nem lehet szerkeszteni, miután egy Excel-sablonhoz lett társítva. Az elrendezés módosításához törölje a kapcsolódó Excel-sablonfájlt, és hozza létre újra. Ez az elrendezésben és a munkalapon lévő mezők szinkronizálásának megtartásához szükséges. 

Az Excel-sablon tartalmazza az összes olyan elemet a költségvetésiterv-dokumentumelrendezésből, ahol az **Elérhető a munkalapon** oszlop értéke Igaz. Egymást átfedő elemek nem használhatók az Excel-sablonban. Például ha az elrendezés 1. n.évi kérelem, 2. n.évi kérelem, 3. n.évi kérelem és 4. n.évi kérelem oszlopokat tartalmaz, és van egy összegző oszlop, amely a 4 negyedévi oszlop összegét tartalmazza, csak a negyedévi oszlopok vagy az összegző oszlop használható fel az Excel-sablonban. Az Excel-fájl nem tud átfedésben lévő oszlopokat frissíteni a frissítés során, mivel a tábla adatai elavultakká és pontatlanná válhatnak.

[![példa](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> A költségvetésiterv-adatok Excelben történő megtekintése és módosítása során fellépő lehetséges problémák elkerülése érdekében ugyanannak a felhasználónak kell bejelentkeznie a Microsoft Dynamics 365 for Finance and Operations alkalmazásba és a Microsoft Dynamics Office Adatcsatlakozó bővítményébe.

## <a name="add-a-header-to-budget-plan-document-template"></a>Fejléc felvétele költségvetésiterv-dokumentum sablonjába
Fejlécadatok hozzáadásához jelölje ki a felső sort az Excel-fájlban, és illesszen be üres sorokat. Kattintson a **Tervezés** elemre az **Adatcsatlakozóban** a fejlécmezők az Excel-fájlhoz történő hozzáadásához.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

A **Tervezés** lapon kattintson a **Hozzáadás** mezőre, és válassza ki a **BudgetPlanHeader** elemet az entitás adatforrásaként.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

Vigye a kurzort a kívánt helyre az Excel fájlban. Kattintson a **Címke hozzáadása** elemre a mezőfelirat a kijelölt helyen történő hozzáadásához. Válassza az **Érték hozzáadása** elemet az értékmező a kijelölt helyre történő hozzáadásához. A tervező bezárásához kattintson a **Kész** gombra.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Számított oszlop felvétele költségvetésiterv-dokumentum táblájába
--------------------------------------------------------------

Ezután következik a számított oszlopok hozzáadása a létrehozott költségvetésiterv-dokumentumsablonhoz. Ezek egy **Teljes kérelem** oszlop, amely összesíti az 1. n.évi kérelem:4. n.évi kérelem oszlopokat, és egy **Kiigazítás** oszlop, amely egy előre megadott tényezővel újraszámolja a **Teljes kérelem** oszlopot.

Kattintson a **Tervezés** elemre az **Adatcsatlakozóban** oszlopok a táblához történő hozzáadásához. Kattintson a **Szerkesztés** elemre a **BudgetPlanWorksheet** adatforrás mellett az oszlopok felvételének megkezdéséhez.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

A kiválasztott mezőcsoport megjeleníti a sablonban elérhető oszlopokat. Kattintson a **Képlet** lehetőségre egy új oszlop hozzáadásához. Adjon nevet az új oszlopnak, majd illessze be a képletet a **Képlet** mezőbe. Az oszlop beillesztéséhez kattintson a **Frissítés** elemre.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> A képlet megadásához hozza létre a képletet a táblázatban, majd másolja a **Tervezés** ablakba. A Finance and Operationshöz kapcsolt táblák neve általában „AXTable1”. Például az 1. n.évi kérelem : 4. n.évi kérelem oszlopok a táblázatban való összegzésére szolgáló képlet = AxTable1\[1. n.évi kérelem\]+AxTable1\[2. n.évi kérelem\]+AxTable1\[3. n.évi kérelem\]+AxTable1\[4. n.évi kérelem\].

Ismételje meg ezeket a lépéseket a **Kiigazítás** oszlop beillesztéséhez. Ennél az oszlopnál használja az = AxTable1\[Teljes kérelem\]\*$I$1 képletet. Ez veszi az I1 cella értékét, és megszorozza **Teljes kérelem** oszlop értékeit a helyesbítési összegek kiszámításához.

Mentse és zárja be az Excel-fájlt. Lépjen vissza a Finance and Operations rendszerbe, majd az **Elrendezések** részben kattintson a **Sablon &gt; Feltöltés** elemre a mentett és a költségvetési tervhez használandó Excel-sablon feltöltéséhez. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Zárja be az **Elrendezések** csúszkát. A **Költségvetési terv** dokumentumban, kattintson a **Munkalap** elemre a dokumentum Excelben történő megtekintéséhez és szerkesztéséhez. Ne feledje, hogy a kiigazított Excel-sablont használtuk ezen költségvetésiterv-munkalap létrehozásához, és hogy a számított oszlopok az előző lépésben megadott képletek alapján frissülnek. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Tippek és trükkök költségvetésiterv-sablonok létrehozásához
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Felvehetek és használhatok további adatforrásokat költségvetésiterv-sablonoknál?

Igen, a **Tervező** menüben további entitásokat is hozzáadhat az Excel-sablon ugyanazon vagy más lapjaihoz. Hozzáadhatja például a **BudgetPlanProposedProject** adatforrást, és költségvetésiterv-adatok az Excelben történő feldolgozásával egy időben létrehozhat és karbantarthat vele lehet egy javasolt projektek listáját. Fontos megjegyezni, hogy nagy mennyiségű adatforrás használata csökkentheti az Excel munkafüzet teljesítményét. 

Az **Adatcsatlakozó** **Szűrő** lehetőségével tetszés szerinti szűrőket adhat hozzá a további adatforrásokhoz.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Elrejthetem a Tervezés lehetőséget az Adatcsatlakozóban más felhasználók elől?

Igen, nyissa meg az **Adatcsatlakozó** beállításait, ha el kívánja rejteni a **Tervezés** funkciót más felhasználók elől.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Bontsa ki az **Adatcsatlakozó beállításai** elemet, és törölje a **Tervezés engedélyezése** jelölőnégyzetet. Ez elrejti a **Tervezés** funkciót az **Adatcsatlakozóból**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Megakadályozhatom, hogy a felhasználók adatokkal való munkavégzés közben véletlenül bezárják az Adatcsatlakozót?

Ajánlott zárolni a sablont, hogy a felhasználók ne tudják bezárni. A zárolás bekapcsolásához kattintson az **Adatcsatlakozó** elemre, és a jobb felső sarokban megjelenik egy nyíl. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Kattintson a nyílra a további menü megjelenítéséhez. Válassza a **Zárolás** elemet.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Használhatok más Excel-funkciókat, például cellaformázást, színeket, feltételes formázást és diagramokat a költségvetésiterv-sablonokhoz?

Igen, a legtöbb normál Excel-funkció működik a költségvetésiterv-sablonokban. Színkódolás használata ajánlott, hogy a felhasználók különbséget tudjanak tenni a csak olvasható és a szerkeszthető oszlopok között. A feltételes formázás segítségével kiemelhetők a költségvetés problémás területei. Az oszlopösszegek könnyen megjeleníthetők a táblázat felett szokásos Excel-képletek segítségével.

Emellett létrehozhatók és használhatók kimutatások és diagramok a költségvetési adatok további csoportosítása és képi megjelenítése érdekében. Az **Adatok** lapon, a **Kapcsolatok** csoportban kattintson a **Mindent frissít** elemre, majd kattintson a **Kapcsolat tulajdonságai** elemre. Kattintson a **Használat** lapra. A **Frissítés** részben jelölje be az **Adatfrissítés a fájl megnyitásakor** jelölőnégyzetet. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)




