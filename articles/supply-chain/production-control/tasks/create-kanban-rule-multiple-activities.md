---
title: Kanbanszabály létrehozása több tevékenységhez
description: Ez az eljárás bemutatja, hogy hogyan hozhat létre olyan kanbanszabályt, amely a termelési folyamatból származó többféle tevékenységet tartalmaz.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f55034f4f0557023ce0c659c1e8258214cf8bfa3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569239"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Kanbanszabály létrehozása több tevékenységhez

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan hozhat létre olyan kanbanszabályt, amely a termelési folyamatból származó többféle tevékenységet tartalmaz. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként. Ez a feladat a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mivel ők készítik elő az új vagy módosított termékek termelését a lean környezetben.


## <a name="create-a-new-kanban-rule"></a>Új kanbanszabály létrehozása
1. Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Feltöltési stratégia mezőben válassza ki az „Ütemezve” lehetőséget.
4. Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a SpeakerAssemblyAndPolish lehetőséget.  
5. Jelölje be a Több tevékenység jelölőnégyzetet.
    * A cél az, hogy a kanbanszabály több, mint egy tevékenységet tartalmazzon. A termelési folyamatban útvonalat választ az utolsó tervezett tevékenység kiválasztásakor.  
6. Az Utolsó tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki a SpeakerTestAndPackaging lehetőséget. Miután kiválasztotta az értéket, automatikusan megjelenik egy oldal. Válassza ki a kanbanfolyamat SpeakerAssemblyAndPolish > SpeakerTestAndPackaging lehetőséget. Kattintson az OK gombra.  
7. A Részletek szakasz kibontása.
8. A Termék mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki az L0006 elemet.  

## <a name="create-kanban-and-view-jobs"></a>Kanban létrehozása és feladatok megtekintése
1. Bontsa ki a Kanbanok szakaszt.
2. Kattintson a Hozzáadás gombra.
3. Írja be az „1” értéket az Új kanbanok száma mezőbe.
    * Ez egy kanbant hoz létre.  
4. Állítsa a Termékmennyiséget az „3” értékre.
    * A kanban 3 terméket dolgoz fel.  
5. A Határidő dátuma/időpontja mezőben adjon meg egy dátumot és időpontot.
    * Az aktuális napot adhatja meg.  
6. Kattintson a Létrehozás lehetőségre.
7. Kattintson a Részletek gombra.
    * Jegyezze meg, hogy a kanban a termelési folyamatból származó két feldolgozási feladattal rendelkezik. Az első a SpeakerAssemblyAndPolish, és a második a SpeakerTestAndPackaging.  
    * Ez az utolsó lépés!  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]