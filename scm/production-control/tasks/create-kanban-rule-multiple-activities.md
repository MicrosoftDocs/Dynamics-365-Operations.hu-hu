--- 
title: "Kanbanszabály létrehozása több tevékenységhez"
description: "Ez az eljárás bemutatja, hogy hogyan hozhat létre olyan kanbanszabályt, amely a termelési folyamatból származó többféle tevékenységet tartalmaz."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 5b4c6f919072dd6497b0eab548077f68fc46dbf5
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Kanbanszabály létrehozása több tevékenységhez

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


