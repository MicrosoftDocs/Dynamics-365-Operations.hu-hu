--- 
title: "Kanbanszabály létrehozása kanbansoresemény használatával"
description: "Ez az eljárás kanbanszabályt hoz létre a kanban soresemény beállítás segítségével a folyamattevékenységből történő lekérés aktiválásához."
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: cc8c3ff5e98ccce56a7a19b16c1aceac650cdf5a
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Kanbanszabály létrehozása kanbansoresemény használatával

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás kanbanszabályt hoz létre a kanban soresemény beállítás segítségével a folyamattevékenységből történő lekérés aktiválásához. A kanban folyamattevékenység által elindított kanbanszabály, amely mennyisége egyenként egyenlő vagy nagyobb mint 25. A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként. Ez a feladat a folyamatmérnök vagy az érték-előállítási vezető munkáját segíti, mivel ők készítik elő az új vagy módosított termékek termelését a lean környezetben.


## <a name="create-a-kanban-rule"></a>Kanbanszabály létrehozása
1. Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Feltöltési stratégia mezőben válassza az „Esemény” lehetőséget.
    * A rendszer kanbanokat hoz létre közvetlenül az igények alapján. Ez a rendelésre készített esetet meghatározó szabályok beállítására szolgál.  
4. Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.
    * Adja meg vagy válassza ki a SpeakerAssemblyAndPolish lehetőséget. A gyártási kanban szabály első tevékenysége a termelési folyamatban megjelenő folyamattevékenység. A tevékenység kiválasztásakor a rendszer a tevékenység érvényességi dátumát a kanbanszabály érvényességi dátumára másolja.  
5. A Részletek szakasz kibontása.
6. Írja be a „L0001” szöveget a Termék mezőbe.
7. Bontsa ki a Események szakaszt.
8. Válassza ki az „Automatikus” lehetőséget a Kanbansoresemény mezőben.
    * Igény szerint eseménykanbanokat hoz létre.  Ez a mező szolgál azon kanbanszabályok konfigurálására, amelyek lefelé irányuló folyamattevékenységhez szükséges anyagokat töltenek fel. Az automatikus lehetőség kiválasztásakor az eseménykanbanokat igény szerint hozzák létre. Ez a beállítás akkor ajánlott, ha ugyanazon a napon szeretné végrehajtani a gyártást.  
9. A minimális eseménymennyiséget állítsa „25” értékre.
    * A eseménykanbanok akkor jönnek létre, ha az igény mennyisége egyenlő vagy nagyobb, mint az ebben a mezőben található érték. Ez akkor hasznos, ha kisebb rendelési mennyiséget szeretne előállítani, mint egy gépen található mezőben és nagyobb rendelési mennyiséget, mint egy másik gépen található mezőben.  
10. Kattintson a Mentés gombra.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>Értékesítési rendelés létrehozása és kanban lánc aktiválása
1. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki az US-003, Forest Wholesales Vevői számlát.  
4. Kattintson az OK gombra.
5. A Cikkszám mezőbe írja be az „L0001” értéket.
    * Az L0001 elem az a cikk, amelyhez létrehozta a kanbanszabályt.  
6. Állítsa a mennyiséget 27 értékre.
    * Mivel 27 nagyobb, mint 25, a kanbanszabályban található minimális mennyiség, így egy eseménykanbant indít el.  
7. A Hely mezőbe írja be az „1” értéket.
8. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
    * Válasszak ki a 13. raktárt.  
9. Kattintson a Mentés gombra.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>A kanbanszabály által létrehozott kanban megtekintése
1. Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. Bontsa ki a Kanbanok szakaszt.
    * Jegyezze meg, hogy a rendszer a 27-es kanbant a létrehozott kanbanszabályon alapuló tevékenység feldolgozására hozta létre.  
    * Ez az utolsó lépés.  


