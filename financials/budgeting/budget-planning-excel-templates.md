---
title: "Költségvetés-tervezési sablonok Excel"
description: "Ez a témakör ismerteti a költségvetési tervek használt Microsoft Excel sablonok létrehozása."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 0e2eb6e7c130f03edbf60a185d397d94b5d61d7d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-templates-for-excel"></a>Költségvetés-tervezési sablonok Excel

Ez a témakör ismerteti a költségvetési tervek használt Microsoft Excel sablonok létrehozása.

Ez a témakör bemutatja a szokásos demó adatkészlet és a rendszergazda felhasználói bejelentkezés költségvetési tervek használt Excel sablonok létrehozása. Költségvetés-tervezési kapcsolatos további tudnivalókért lásd: [a költségvetés-tervezési áttekintése.](budget-planning-overview-configuration.md) Is követheti a [költségvetés-tervezés 101](budget-plan.md) oktatóprogram további alapvető modul konfiguráció és használat elveket.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>A költségvetési terv dokumentum elrendezésben munkalap létrehozása
Költségvetési terv dokumentumai megtekinthetők és szerkeszthetők egy vagy több elrendezések használata. Minden elrendezés egy kapcsolódó költségvetési terv megtekintéséhez és szerkesztéséhez a költségvetési terv adatokat egy Excel-munkalap dokumentumsablon is. Ez a témakör a költségvetési terv dokumentumsablont jön létre, egy meglévő Elrendezés konfigurálása. Nyissa meg a **költségvetési tervek lista** (**költségvetés**&gt;**a költségvetési tervek**). Kattintson a **új** egy új költségvetés-tervezési dokumentum létrehozásához. [![bpt1](./media/bpt11-1024x552.png)](./media/bpt11.png) 

Használja a **hozzáadása** sor sorok hozzáadása lehetőséget. Kattintson a **elrendezések** a költségvetési terv dokumentum elrendezése konfigurációt. 
[![bpt2](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Elrendezés konfigurációjának áttekintése, és szükség szerint módosítsa. Ugrás a **sablon**&gt;**előállítása** Ez az elrendezés egy Excel fájlt létrehozni. Után a sablon létre, Ugrás a **sablon**&gt;**nézet** megnyitásához, majd tekintse át a költségvetési terv dokumentumsablon. A helyi meghajtóra mentheti az Excel-fájlt. [![bpt3](./media/bpt3-1024x545.png)](./media/bpt3.png) 

> [!NOTE] 
> A költségvetési terv dokumentum elrendezését nem lehet szerkeszteni, miután egy Excel-sablon társítva. Az elrendezés módosításához törölje a kapcsolódó Excel sablon fájlt, és újragenerálhatja azt. Ez szükséges megtartani a mezők elrendezését, és szinkronizálja a munkalapon. 

Az Excel-sablon tartalmazza az elemek a dokumentum elrendezésének költségvetési terv, ahol a **a munkalap** oszlop értéke True. Egymást átfedő elemek nem használhatók az Excel-sablon. Például ha az elrendezés kérelem Q1, kérelem 2. kérdés, kérés Q3, és kérés Q4 oszlopok és összegezés 4 negyedéves oszlop összes kérés teljes oszlop tartalmaz, csak a negyedéves oszlopok vagy a teljes oszlop érhető el az Excel-sablon használható. Az Excel-fájl nem frissíthető átfedésben lévő oszlopok a frissítés során, mert a tábla adatai elavultak és pontatlan válhat.

[![bpt4](./media/bpt4-1024x615.png)](./media/bpt4.png)

> [!NOTE] 
> Költségvetési terv adatok Excelben megtekintése és módosítása a lehetséges problémák elkerülése érdekében ugyanahhoz a felhasználóhoz kerüljenek a naplóba történő mindkét Dynamics 365 műveletekhez és a beépülő modul a Microsoft Dynamics Office Data Connector.

## <a name="add-a-header-to-budget-plan-document-template"></a>Fejléc felvétele a költségvetési terv dokumentum sablonja
Fejléc-információ hozzáadásához jelölje ki a felső sorban az Excel fájl, és üres sorok beszúrása. Kattintson a **Tervező** a a **Data Connector** üzenetfejléc-mezők hozzáadása az Excel-fájlt.

[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png) 

A a **Tervező** lap ** ** kattintson a **hozzáadása** mezőt, és válassza ki **BudgetPlanHeader** entitás adatforrásként.

[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)

A kurzort a kívánt helyre az Excel fájl. Kattintson a **címke hozzáadása** a mezőfelirat hozzáadása a kijelölt helyre. Válassza ki **érték hozzáadása** az érték mező hozzáadása a kijelölt helyre. Kattintson a **végzett** zárja be a tervezőt.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>[![bpt7](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>A számított oszlop hozzáadása a költségvetési terv dokumentum sablonja táblában
--------------------------------------------------------------

Következő, a számított oszlopok létrehozott költségvetési terv dokumentumsablon hozzáadódik. A **teljes kérelem** oszlop összesíti a kérelem 1. kérdés: kérelem Q4 oszlopok, és egy **korrekciós** oszlopban újraszámolja a **teljes kérelem** oszlop egy előre megadott tényezővel.

Kattintson a **Tervező** a a **Data connector** adhat oszlopokat a táblázathoz. Kattintson a **Szerkesztés** mellett **BudgetPlanWorksheet** adatforrás oszlopok felvételének megkezdése.

[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png) 

A kiválasztott mezőcsoport jeleníti meg az oszlopokat, amelyek a sablonban érhető el. Kattintson a **képlet** új oszlop hozzáadása. Az új oszlop neve, és illessze be a képletet a **képlet** mezőben. Kattintson a **frissítés** az oszlop beszúrása.

[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Adja meg a képletet, a képlet a számolótábla létrehozásához, és másolja azt a **Tervező** ablakot. A Dynamics 365 műveletek kötött tábla általában neve "AXTable1". Q1 kérése összegzéséhez például: kérése Q4 oszlopai a következő képlet a számolótábla = AxTable1\[kérése Q1\]+ AxTable1\[kérése Q2\]+ AxTable1\[kérése Q3\]+ AxTable1\[Q4 kérése\].

Ismételje ezeket a lépéseket, hogy a **helyesbítés** oszlop. Képlet = AxTable1\[teljes kérelem\]\*$I$ 1 oszlop. Ezzel vesz I1 cella értékét, és szorozzuk meg az értékeket a **teljes kérelem** oszlop helyesbítési összegek kiszámításához.

Mentse és zárja be az Excel-fájlt. Dynamics 365 műveletek, majd a vissza **elrendezések**, kattintson a **sablon &gt;feltöltése** feltölteni a költségvetési terv használandó mentett Excel-sablon. 

[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Bezárás a **elrendezések** csúszka. A **költségvetési terv** dokumentum, kattintson a **munkalap** megtekintése és szerkesztése az Excel programban a dokumentumot. Ne feledje, hogy a kiigazított Excel-sablon a költségvetési terv munkalap létrehozásához használt számított oszlopok frissülnek az előző lépésben megadott képletek alapján. 

[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Tippek és trükkök a költségvetési terv-sablonok létrehozása
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Felvehet és használhat további adatforrások költségvetési terv sablon?

Igen, a **Tervező** menü további személyek hozzáadása azonos vagy más lapok a Excel-sablon. Hozzáadhatja például a **BudgetPlanProposedProject** lehet létrehozni és karbantartani a javasolt projektek listája egyszerre mikor költségvetés munkaterve adatokat az Excel adatforrást. Fontos megjegyezni, hogy nagy mennyiségű adat források beleértve csökkentheti a teljesítményt az Excel munkafüzet. 

Használhatja a **szűrő** lehetőségével a **Data Connector** további adatforrásokat hozzáadni kívánt szűrőket.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Elrejtheti a más felhasználók számára az adatok összekötő Tervező beállítás?

Igen, nyissa meg a **Data Connector** beállítások elrejtése a **Tervező** más felhasználóktól lehetőséget.

[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)

Bontsa ki a **összekötő adatbeállítások**, és törölje a **lehetővé teszi a tervező** jelölőnégyzetet. Ez elrejti a **Tervező** a beállítás a **Data connector**.

[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Felhasználók megakadályozása véletlenül bezárja az adatokat összekötő adatok használata közben?

Ajánlott zárolásával megakadályozható, hogy a felhasználók lezárja a sablont. Kapcsolja be a zárolást, kattintson a **Data connector**, a jobb felső sarokban található nyíl jelenik meg. 

[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Kattintson a nyílra a további menü. Válassza ki **Lock**.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Használható többi Excel jellemző cellaformázás, színek, feltételes formázás és diagramokhoz hasonlóan a költségvetés-tervezési sablonokat?

Igen, szabványos Excel lehetőségeinek többsége a költségvetés-tervezési sablonokat fog működni. Csak olvasható és szerkeszthető oszlopok közti különbséget tenni a felhasználók színkódolás használata ajánlott. Feltételes formázás segítségével a költségvetés problémás területek kiemeléséhez. Oszlopösszegek könnyen megjeleníthetők a táblázat feletti szokásos Excel képletek segítségével.

Is létrehozhat, és a kimutatások és diagramok használata további csoportosításokat és költségvetési adatok képi megjelenítések. A a **adatok** lapon, az a **kapcsolatok** csoport, kattintson a **Mindent frissít**, és kattintson a **kapcsolat tulajdonságai**. Kattintson a **használat** fülre. A **frissítési**, jelölje be a **Adatfrissítés a fájl megnyitásakor** jelölőnégyzetet. 

[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)


