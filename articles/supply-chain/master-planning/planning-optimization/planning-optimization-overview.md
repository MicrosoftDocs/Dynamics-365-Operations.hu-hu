---
title: Tervezés optimalizálása – áttekintés
description: Ez a témakör áttekintést ad a Tervezésoptimalizálása funkcióiról.
author: ChristianRytt
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 8fd73313b82319c35eb5fccbd68cd305403bfe3f635f6b267fb408943af3396c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739059"
---
# <a name="planning-optimization-overview"></a>Tervezés optimalizálása – áttekintés

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management Tervezésoptimalizálási bővítménye lehetővé teszi, hogy az alaptervezési számítás a Dynamics 365 Supply Chain Management szolgáltatáson és a kapcsolódó SQL-adatbázison kívül történjen. A tervezésoptimalizálás funkcióhoz társított előnyök között szerepel a továbbfejlesztett teljesítmény és az SQL-adatbázisra tett minimális hatás az Alaptervezés futtatásakor. A gyors tervezési futtatások a nyitvatartási idő alatt is megtehetők, így a tervezők azonnal reagálni tudnak a igényre vagy a paraméterek változásaira.

A Tervezésoptimalizálás funkció használatához telepítenie kell a Microsoft Dynamics Lifecycle Services (LCS) projektjéből a Tervezésoptimalizálás bővítményt, majd be kell kapcsolni a Tervezésoptimalizálás funkciót a Supply Chain Management szolgáltatásban. További tájékoztatás: [Első lépések a Tervezésoptimalizálással](get-started.md).

A következő ábra bemutatja, hogy milyen előnyökkel jár a Tervezésoptimalizálás a nyitvatartási órákban.

![A Tervezésoptimalizálás irodai órákban történő futtatásának előnyei.](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>Javított teljesítmény

A Tervezésoptimalizálás a hosszú távú alapterveket is magában foglaló esetekben használható. Ez kifejezetten nagyon gyors számításokhoz van tervezve, amelyek nagy mennyiségű adatot érintenek. Mivel a program a tetszőlegesen méretezhető multibérlő szolgáltatásként épült, több példány együtt dolgozhat egyidejűleg a terv kiszámításához. Ezenkívül a tervezési szolgáltatás eltávolítja az alaptervezés terhét a rendszerből, és olyan adatfolyamot dolgozik, amely minimalizálja a kiszolgáló terhelését.

A Tervezésoptimalizálás a következő célok elérése érdekében használható:

- A tervezési teljesítmény javítása a rövidebb futásidőn keresztül.
- Az Alaptervezés futtatása közben a többi folyamatra gyakorolt hatás csökkentése.
- Gyakrabban kell tervezni a tervezést. (Nem korlátozódik a napi futtatásra.)
- Győződjön meg arról, hogy a jövőbeli üzleti növekedés nem terheli meg a tervezési rendszert.

## <a name="architecture-and-data-flow"></a>Architektúra és az adatforgalom

Amikor a Tervezésoptimalizálás bővítményt telepíti a LCS-ből, létrejön egy biztonságos kapcsolat a Tervezésoptimalizálás szolgáltatással. A szolgáltatás ugyanabban az adatközpontként megadott országban vagy területen található, mint a kapcsolódó Supply Chain Management példány. A Tervezésoptimalizálás beállítása után az Alaptervezés futtatásakor az alapadatok és a tranzakciós adatok a Supply Chain Management szolgáltatásból érkeznek a Tervezésoptimalizálás szolgáltatásba.

Ha eltávolítja a Tervezésoptimalizálás bővítményt, akkor a program eltávolítja a Tervezésoptimalizálás szolgáltatással kapcsolatos összes adatot.

### <a name="high-level-data-flow-for-regeneration-runs"></a>A regeneráláshoz szükséges magas szintű adatfolyamok

1. A Supply Chain Management kliens egy olyan jelet küld, amely a Tervezésoptimalizálás kéri a tervezési futtatást.
2. A Tervezésoptimalizálás a szükséges adatokat a beépített összekötőn keresztül kéri.
3. Az SQL-adatbázis elküldi a Tervezésoptimalizálásnak a kért információkat a beállítással, alap- és tranzakciós adatokkal kapcsolatban az összekötőn keresztül. Az összekötő lefordítja az információkat a Supply Chain Management és a Tervezésoptimalizálás szolgáltatás között.
4. ATervezésoptimalizálás szolgáltatás a memóriában a tervezéssel kapcsolatos adatokat tárolja, és a szükséges számításokat.
5. A tervezési eredményt a program az összekötőn keresztül küldi el a Supply Chain Management adatbázisnak. Az eredmények között szerepelnek például a tervezett rendelések és a rögzített adatok. A Tervezésoptimalizálás jel küldésével jelzi a Supply Chain Management számára, hogy a tervezés futtatása befejeződött. Ezenkívül a megfelelő üzeneteket és figyelmeztetéseket is elküldi.

A következő ábra ábrázolja az adatok áramlását.

![Adatforgalom a regenerálási futtatásokhoz.](media/PlanningOptimization2.png)

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Tervezési optimalizálás kezdő lépései](get-started.md)

[A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)

[Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)

[Szűrők alkalmazása egy tervre](plan-filters.md)

[Tervezési feladat érvénytelenítése](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]