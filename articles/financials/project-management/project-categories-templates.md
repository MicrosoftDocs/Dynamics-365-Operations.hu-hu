---
title: "Projekt költségkategóriák szinkronizálása a Project Service Automation alkalmazásból"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt költségkategóriáinak Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: hu-hu
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Projekt költségkategóriák szinkronizálása a Finance and Operations és a Project Service Automation között

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt költségkategóriáinak Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra használhatók.

> [!NOTE]
> Projektfeladatok integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Dynamics 365 for Finance and Operations 8.0-ás verziójában érhető el.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Adatáramlás a Project Service Automation és a Finance and Operations esetében

A Project Service Automation és a Finance and Operations közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance and Operations példányok közötti szinkronizáláshoz. Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projektköltségtranzakció-kategóriákkal kapcsolatos adatáramlást a Project Service Automation és Finance and Operations alkalmazások között.

Ha a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve az integrációs folyamat először a Finance and Operations és a Project Service Automation között történik majd ezt követően történik a projektköltség-kategóriák integrációs azonosítóinak szinkronizálása a Project Service Automation és Finance and Operations között.

Ha a projektköltség-kategóriák a Project Service Automation alkalmazásban vannak kezelve, az integrációs folyamat először a Project Service Automation és a Finance and Operations között történik. A projektkategóriákat már előtt konfigurálni kell a Finance and Operations alkalmazásban, mielőtt szinkronizálná a Project Service Automation alkalmazásba. Majd szinkronizálja vissza a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba, majd ismét a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba. Ez biztosítja a kategóriák kapcsolását, az ismétlődések elkerülését.

> [!NOTE]
> Általában a projektköltség-kategóriák a Finance and Operations alkalmazásban vannak kezelve. Ha nem ez a helyzet, vagy már létrehozott költségkategóriákat a Project Service Automation alkalmazásban , először szinkronizálnia kell a Projektköltség-tranzakció kategóriák használatával (PSA to Fin and Ops) használatával és majd szinkronizálnia kell a Projektköltség-tranzakció kategóriák (Fin and Ops to PSA) használatával. Ezután ismét futtatnia kell a PSA to Fin and Ops szinkronizálást.

> Ha a szinkronizálás a Project Service Automation alkalmazásból történik, a projektkategóriákat már be kell állítani a Finance and Operations alkalmazásban és minden olyan projektkategóriát, melyet szinkronizálni kell a Projektszolgáltatás-automatizálás kategóriában be kell állítani az **Aktív a naplókban**.

A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)


## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok eléréséhez a Microsoft PowerApps Admin Centerben válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Finance and Operations között és a Project Service Automation között:

-  **Sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (Fin and Ops to PSA)
-  **A feladat neve a projektben** Sync categories to PSA (Kategóriák szinkronizálása PSA-ba)

## <a name="entity-set"></a>Entitás beállítása

| Finance and Operations               | Projekt szolgáltatásautomatizálása    |
|--------------------------------------|-------------------------------|
| Integrációs entitás a kategóriákhoz    | Tranzakciókategóriák.        |

## <a name="entity-flow"></a>Entitás folyamata

Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként.

## <a name="power-query"></a>Power Query

Microsoft Power Queryt kell használnia a számlázási típus beállításához a tranzakciókategórián, amikor a Project Service Automation alkalmazásba szinkronizál. A Projektkiadás-tranzakció kategóriák (Fin and Ops to PSA) sablonban van egy alapértelmezett oszlop, és a hozzárendelés már rendelkezésre áll. Ha saját sablont hoz létre, hozzá kell adnia egy feltételes oszlopot a Power Query-ben.
- Nyissa meg a Speciális lekérdezés és szűrés űrlapot a projektköltség-kategóriák feladat hozzárendelésében.
- Válassza a **Feltételes oszlop hozzáadása** lehetőséget.
- Adjon meg egy nevet az új oszlopnak, például BillingType.
- Adja meg a következő feltételt: Ha **CATEGORYID not equal to null then 19235001, Otherwise null**.
- Kattintson a **OK** elemre az oszlopon.
- Ügyeljen arra, hogy ez az új oszlop hozzá legyen rendelve a hozzárendelés oldalon.

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Finance and Operations – Project Service Automation irányban.

[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-kategóriák szinkronizálásához a Project Service Automation és a Finance and Operations között:

-**A sablon neve az adatintegrációban:** Projektköltség-tranzakció kategóriák (PSA to Fin and Ops) -**A feladat neve a projektben:** Kategóriák szinkronizálása a Fin Ops-ba

## <a name="entity-set"></a>Entitás beállítása

| Projekt szolgáltatásautomatizálása      | Finance and Operations             |
|---------------------------------|------------------------------------|
| Tranzakciókategóriák.          | Integrációs entitás a kategóriákhoz  | 

## <a name="entity-flow"></a>Entitás folyamata

Projektköltség-kategóriák kezelése a Finance and Operations alkalmazásban történik, majd ezek szinkronizálva lesznek a Project Service Automation alkalmazásba tranzakciókategóriaként. Majd szinkronizálja vissza a Finance and Operations alkalmazásból a Project Service Automation alkalmazásba, majd a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban

> [!NOTE]
> A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.

[![Sablon-hozzárendelés](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

