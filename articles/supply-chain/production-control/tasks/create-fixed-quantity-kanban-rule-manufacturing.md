--- 
title: "Rögzített mennyiségű kanbanszabály létrehozása gyártáshoz"
description: "Ez az eljárás a rögzített gyártású kanbanszabály létrehozására koncentrál az átalakítási tevékenységek elindításához egy munkacellában, lean környezetben."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8020a37bf0c725fc260574cfe87861aeb017519e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>Rögzített mennyiségű kanbanszabály létrehozása gyártáshoz

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás a rögzített gyártású kanbanszabály létrehozására koncentrál az átalakítási tevékenységek elindításához egy munkacellában, lean környezetben. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás a Folyamatmérnök vagy az Érték-előállítási vezető munkáját segíti, mert ők készítik elő az új vagy módosított termék termelését.


## <a name="create-new-kanban-rule"></a>Új kanbanszabály létrehozása
1. Ugorjon a Kanbanszabályokhoz.
2. Kattintson az Új lehetőségre.
    * Az alapértelmezett típus a Gyártás és a Feltöltési stratégia Rögzített. Ezeket a paramétereket nem kell megváltoztatnia.  
3. Az Első tervezési tevékenység mezőben adjon meg, vagy válasszon ki egy értéket.
    * Ez a tevékenység megtörténik kanbanok esetén a jelen kanbanszabály alapján.  Válassza ki a „SpeakerTestAndPackaging” lehetőséget.  
4. A Részletek szakasz kibontása.
5. A Termék mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza az L0050 lehetőséget.  
6. A Mértékegység mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a perceket.  
7. Adjon meg egy számot az Átfutási idő mezőben.
    * Adja meg az 5 értéket.  

## <a name="set-quantities"></a>Mennyiségek beállítása
1. Bontsa ki a Mennyiségek szakaszt.
2. Állítsa az Alapértelmezett mennyiséget a „10” értékre.
    * Ez a mennyiség átkerül az összes kanbanba.  
3. Jelölje be a Termékmennyiségi különbözet jelölőnégyzetet.
    * Ezzel a kiválasztott kanbanok az alapértelmezett értéktől eltérően fejeződnek be.  Ha a kanbanokat 8–12 közötti értékkel kívánja befejezni, állítsa mindkét különbözetet 2-re.  
4. Állítsa az alábbi Eltérést „2” értékre.
    * Így a befejezés 10 - 2 =8 értékig lehetséges.  
5. Állítsa a fenti Eltérést „2” értékre.
    * Így a befejezés 10 + 2 =12 értékig lehetséges.  
6. Adjon meg egy számot a Rögzített kanbanmennyiség mezőben.
    * Ez az aktív kanbanok mennyisége. Ebben az esetben 5 kanban van, melyek mindegyike 10-et dolgoz fel.  
7. A Minimális figyelmeztetési határ mezőben adja meg a „2” értéket.
    * Ennek segítségével nyomon követik azon teljes kanbanok minimum mennyiségét, amelyeknek a célhelyen kellene lenni. Például ezt használják a kanbanmennyiség ellenőrzésére.  
8. A Maximális figyelmeztetési határ mezőben adja meg a „4” értéket.
    * Ennek segítségével nyomon követik azon teljes kanbanok maximum mennyiségét, amelyeknek a célhelyen kellene lenni. Például ezt használják a kanbanmennyiség ellenőrzésére.  
9. Az Automatikus tervezési mennyiség mezőben adja meg az „1” értéket.
    * Ha ezt 1-re állítja, a kanbanok tervezése automatikusan történik.   Ha 3-at adnánk meg, a kanbanok tervezése nem történne meg, amíg 3 kanban tervezésre készen nem áll. Ennek segítségével csoportosítható a munka, és elkerülhető a túl sok beállítás.  

## <a name="create-kanbans"></a>Kanbanok létrehozása
1. Bontsa ki a Kanbanok szakaszt.
2. Kattintson a Mentés gombra.
    * A kanbanszabályt a kanbanok létrehozása előtt el kell menteni.  
3. Kattintson a Hozzáadás gombra.
    * Vegye figyelembe, hogy nincsenek aktív kanbanok, ennek köszönhetően a javasolt „Új kanbanok száma” 5. Ez egyenlő a Rögzített kanbanmennyiséggel.  
4. Kattintson a Létrehozás lehetőségre.
    * Ez 5 kanbant hoz létre.  
    * Vegye figyelembe, hogy ehhez a gyártási kanbanszabályhoz 5 kanban, egyenként 10 került létrehozásra. Ez az eljárás utolsó lépése.  


