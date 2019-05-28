---
title: Az Anyagjegyzéksor esemény kanbanszabályának létrehozása
description: Ez a feladat az esemény kanbanszabály létrehozásának beállítására szolgál a termelési Anyagjegyzék sorok ellátásának a vegyes lean és a klasszikus éles környezetben történő biztosítása érdekében.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a4252548fd030f2a044436ff607da5125d2854
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551929"
---
# <a name="create-a-bom-line-event-kanban-rule"></a>Az Anyagjegyzéksor esemény kanbanszabályának létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat az esemény kanbanszabály létrehozásának beállítására szolgál a termelési Anyagjegyzék sorok ellátásának a vegyes lean és a klasszikus éles környezetben történő biztosítása érdekében. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként. Ez az feladat a Folyamatmérnök vagy az Érték-előállítási vezető munkáját segíti, mert ők készítik elő az új vagy a módosított termék termelését.


## <a name="create-a-new-kanban-rule"></a>Új kanbanszabály létrehozása
1. Ugorjon a Gyártásvezérlés > Időszakos feladatok > Kanbanmennyiség-számítás > Kanbanszabályok pontra.
2. Kattintson az Új lehetőségre.
3. A Típus mezőben válassza ki a „Terhelések” lehetőséget.
    * A Levonás típusát az átvitel kanbanok létrehozására szolgál.  
4. A Feltöltési stratégia mezőben válassza az „Esemény” lehetőséget.
    * A rendszer az Esemény stratégiát választja ki az eseményen alapuló kanbanok átvitelének létrehozásához. A feladat útmutató később ajánlott aktiválni a folyamatot a termelési rendelés becslésével.  
5. Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.
    * Adja meg vagy válassza ki a ReplenishSpeakerComponents lehetőséget. Ez az Átmozgatási tevékenység érkeztetési (kimenő) raktárral és 12-es hellyel rendelkezik, ami azt jelenti, hogy az anyagot a 12-es raktárba, a 12-es helyre helyezik át.  
6. A Részletek szakasz kibontása.
7. A Termék mezőben adja meg vagy válassza ki az M0001 értéket.
8. Bontsa ki a Események szakaszt.
9. Az Anyagjegyzéksor-esemény mezőben válassza ki az „Automatikus” lehetőséget.
    * Az Anyagjegyzéksor esemény mező Automatikus módra van beállítva, a rendszer a kanbant a termelési rendelés anyagjegyzék soraihoz szükséges anyagok feltöltéséhez hozza létre.  
10. Zárja be a lapot.

## <a name="create-and-modify-a-new-production-order"></a>Új termelési rendelés létrehozása és módosítása.
1. Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.
2. Kattintson az Új termelési rendelés lehetőségre.
3. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Adja meg vagy válassza ki az „L0001” értéket. Ajánlatos az L0001 cikket használni, mert az L0001 cikk anyagjegyzéke tartalmazza az M0001 cikket.  
4. Kattintson a Létrehozás lehetőségre.
5. A listában kattintson az L0001-es sorban lévő hivatkozásra.
6. Kattintson az Anyagjegyzék elemre.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Kattintson a Szerkesztés lehetőségre.
9. A Sor típusa mezőben válassza ki a „Rögzített készletek” lehetőséget.
    * A rendszer a rögzített készleteket választja ki a kanban ellátási létrehozásának elindításához.  
10. Válassza a Nem lehetőséget az Erőforrás-felhasználás mezőben.
    * Az Erőforrás-felhasználás jelölőnégyzet törlése lehetővé teszi a raktár módosítását.  
11. Bontsa ki a Készletdimenziók szakaszt.
12. A Raktár mezőbe írja be a 12 értéket.
    * A Raktárt 12-es értékre állította be a rendszer, mert ez a visszavonási tevékenység kimeneti raktárat.  
13. Írja be a Hely mezőbe a „12” értéket.
    * A Helyet 12-es értékre állította be a rendszer, mert ez a visszavonási tevékenység kimeneti helye.  
14. Zárja be a lapot.
15. Zárja be a lapot.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>A termelési rendelés becslése és a létrehozott kanban megtekintése
1. Kattintson a Becslés elemre.
    * A termelési rendelés becslése a hozzárendelt kanban létrehozását indítja el az M0001 cikk beszerzéséhez.  
2. Kattintson az OK gombra.
3. Zárja be a lapot.
4. Zárja be a lapot.
5. Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki az M0001 cikkre vonatkozóan létrehozott esemény kanbanszabályt.  
7. Bontsa ki a Kanbanok szakaszt.
8. A listában jelölje meg a kiválasztott sort.
    * Vegye figyelembe, hogy a rendszer a kanbant az M0001 cikk beszerzésére hozta létre a becsült termelési rendelésre vonatkozóan.  
    * Ez az utolsó lépés!  

