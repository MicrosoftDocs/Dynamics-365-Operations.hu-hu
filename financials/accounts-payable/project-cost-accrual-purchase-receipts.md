---
title: "A beszerzési elismervények projekt költség felmerülése"
description: "Ez a témakör leírja, hogyan elszámolt projekt költségek a beszerzési elismervények Microsoft Dynamics 365 műveletek nyomon követhető."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 27a0a71095dce46c0119b32a92f8c4dce0f42e43
ms.lasthandoff: 03/31/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>A beszerzési elismervények projekt költség felmerülése

Ez a témakör leírja, hogyan elszámolt projekt költségek a beszerzési elismervények Microsoft Dynamics 365 műveletek nyomon követhető. 

A projekt számláinak gyakran érkeznek a legkésőbb az áruk és szolgáltatások érkeznek, amely jelentős hatással lehet a projekt fő teljesítménymutatók (KPI). Fontos, hogy ezek a pénzügyi tranzakciók nyomon követése és a projekt jelenti.

A következő példa forgatókönyv bemutatja ezt. 

Contoso konzultációt elindult egy új felhő telepítés projekthez. A beszerzési rendelés jön létre, a számítógép a projekt vásárolnak. A számítógép $1500 ára, és a távtelepítési szolgáltatás ára $150. A szállító leszállított és a számítógépre telepített, de a számlát még nem ért Contoso folytatott konzultációt. A projektmenedzser kíváncsi rá, $1650 a projekt költség felmerülése előtt a számla érkezik. Ezt a költséget a vállalat hónap vége pénzügyi kimutatásokat is tükröződnek. 

Az elszámolt költség jelentési célokra a pénzügyi szint és a projekt szintjén kell rögzíteni kell. Dynamics 365 műveletek szállítólevél pénzügyi frissítés a cikk és a beszerzési kategóriák nyomon lehet követni. 

Cikkek a a **kötelezettségek paramétereinek** lapon válassza azt a **könyvelése a főkönyvbe szállítólevelek** lehetőséget.
[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png) 

A beszerzési kategóriák a a **kategória-irányelvszabály** lapon adja **beszerzés** házirendek, és válassza ki **elhatárolt beszerzési költséget a nyugtán** minden beszerzési kategóriához.
[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png) 

A **kiadások nem számlázott beszerzési** és **beszerzési könyvelési** a számlák **könyvelési mátrix** lesz a bizonylatok, amelyek kapcsolódnak a szállítólevél könyvelésekor.
[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png) 

Ez a forgatókönyv használata esetén nézzük meg, hogyan egy szállítólevél könyvelési befolyásolja főkönyvi és a projekt adatait. 

**1. lépés:** létrehozása és rögzítse a beszerzés, a számítógép $1500 és -telepítési szolgáltatások $150 a projekt új beszerzési rendelés megerősítése.
[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Amikor a beszerzési rendelés megerősítést nyer, a vállalt költség tranzakciókat a projekt jön létre. 
[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> A tranzakciók a vállalt költség lesz a **tranzakció eredete** mező értéke **beszerzési rendelés**. Létrehozása és a beszerzési rendelés megerősítése nem hoz létre egy projekt tranzakcióit. 

**2. lépés:** az áruk és szolgáltatások kézbesítve, és egy szállítólevél regisztrálva van. 

Egy szállítólevél könyvelési létrehozása és könyvelése a főkönyvi bizonylat. A bizonylat a beszerzési kiadások, nem számlázott fiók tartozik, és követel beszerzési elhatárolása. 
[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> A szállítólevél könyvelése beszerzési kategóriák és a termékek és a projekt kategóriák nem a könyvelési mátrix kialakítása használja a könyvelési mátrix kialakítása. Annak érdekében, hogy megfelelően tükrözik a beszerzési könyvelések pénzügyi hatását, a telepítőnek meg kell igazítani. 

Projektkategóriákat a beszerzési kategóriák leképezéséhez a lehetséges a **beszerzési kategória** oldalon.
[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)

**3. lépés:** tervezet szállítói számla létrehozása. 

Műveletek 365 Dynamics egy szállítólevél könyvelési nincs hatással a projektre vonatkozó információk. Megoldás a tervezet szállítói számla közvetlenül a beszerzési bevétjegy könyvelése után sikerült létrehozni. Keresse fel a **beszerzési rendelés** lap &gt;**számla lap**&gt;**előállítása**&gt;**számla**. Ez létrehoz egy függőben lévő számla dokumentum, amely frissíti a projekt adatai. 

Vázlat szállítói számla létrehozása készítése a projekt függő tranzakcióit. 
[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png) 

A a **vállalt költség** lap, az 1. lépésben létrehozott bejegyzést le kell zárni, és új rekordokat hoz létre, hogy tükrözze a függőben lévő szállítói számla származó költség kötelezettségvállalás. A **tranzakció eredete** állítja be a vállalt költség mezőjének **szállítói számla**.
[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)

A szállítói számla függő állapotban marad, amíg a tényleges szállítói számla érkezik.


