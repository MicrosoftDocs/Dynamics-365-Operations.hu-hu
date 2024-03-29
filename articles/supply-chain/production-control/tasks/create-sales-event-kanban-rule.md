---
title: Az értékesítési esemény kanbanszabályának létrehozása
description: Ez az eljárás egy olyan kanbanszabály létrehozásához szükséges beállításokkal foglalkozik, amely az értékesítési rendelés létrehozásakor aktiválódik.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cd2b579e542b9f905fc51b63f2120e5a5c883ae
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566647"
---
# <a name="create-a-sales-event-kanban-rule"></a>Az értékesítési esemény kanbanszabályának létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás egy olyan kanbanszabály létrehozásához szükséges beállításokkal foglalkozik, amely az értékesítési rendelés létrehozásakor aktiválódik. Az esemény kanbanszabály eleget tesz azoknak a követelményeknek, amelyek az értékesítési rendelés soraiból származnak. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mert ők készítik elő az új vagy módosított termék termelését.




## <a name="create-a-new-kanban-rule"></a>Új kanbanszabály létrehozása
1. Ugorjon a Kanbanszabályokhoz.
2. Kattintson az Új lehetőségre.
3. A Feltöltési stratégia mezőben válassza az „Esemény” lehetőséget.
    * Az Esemény kiválasztása azt jelenti, hogy a kanbanszabályt egy esemény indítja el, például az értékesítési rendelés sor létrehozása.   Ez olyan területekre érvényes, ahol minden kanbanhoz adott igény tartozik.  
4. Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.
    * Utolsó szerelvény kiválasztása.  
5. A Részletek szakasz kibontása.
6. A Termék mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza az L0050 lehetőséget.  

## <a name="define-an-event"></a>Határozzon meg egy eseményt
1. Bontsa ki a Események szakaszt.
2. Az Értékesítési események mezőben válassza az „Automatikus” lehetőséget.
    * Ha az Automatikus értékesítési eseményt választja ki, ez a kanbanszabály automatikusan aktiválódik, ha az értékesítési sor egyedül a termék és a bevételezés helyéve. Ebben az eljárásban ez az L0050 termék a 13-as raktárban.  
3. A minimális eseménymennyiséget állítsa „50” értékre.
    * Az 50 minimális eseménymennyiséggel ez a kanbanszabály csak 50 vagy nagyobb mennyiségű események esetén aktiválódik.  
4. Bontsa ki a Termelési folyamat szakaszt.
    * Láthatja, hogy a Bevételezési hely a 13-as raktárban van. Ez azt jelenti, hogy ez a kanbanszabály ehhez a helyhez aktiválódik.  
    * Ebben a példában az L0050 termék értékesítési sora az 50 vagy annál nagyobb mennyiséggel a 13-as raktárban aktiválni fogja ezt a kanbanszabályt.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>A kanbanszabály aktiválásához hozzon létre értékesítési sort
1. Ugrás az összes értékesítési rendelésre.
    * A kanbanszabály mentésekor egy figyelmeztetés jelenik meg, ami arra utal, hogy a kanbanok valós időben, az értékesítési rendelés létrehozásakor jönnek létre.  
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például az US-003-at.  
4. Kattintson az OK gombra.
5. A Cikkszám mezőbe írja be az „L0050” értéket.
6. A Hely mezőbe írja be az „1” értéket.
    * Válassza az 1 Helyet, mert a 13-as raktár az 1 Helyen van.  
7. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
    * Állítsa be a 13-as raktárat.  
8. Állítsa a mennyiséget 75 értékre.
    * Írja be az 50-et vagy egy annál nagyobb mennyiséget, hogy a kanbanszabály aktiválódjon.  

## <a name="verify-that-kanban-is-created"></a>Győződjön meg róla, hogy a kanban létrehozása megtörtént
1. Kattintson a Termék és készlet menüpontra.
2. Az igénykövetési fa megtekintése lehetőségre.
    * Figyelje meg, hogy a kanban mennyisége azonos az értékesítési sor létrehozásakor. Azt is láthatja, hogy az L0050 termeléséhez anyagi kiadásokra van szükség. Ez az eljárás utolsó lépése.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]