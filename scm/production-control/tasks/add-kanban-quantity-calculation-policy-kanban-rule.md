--- 
title: "Kanbanmennyiségi irányelv hozzáadása egy kanbanszabályhoz"
description: "Ez a folyamat egy kanbanmennyiség-számítási irányelv létrehozására irányul, valamint annak hozzáadásához egy kanbanszabályhoz, amivel optimalizálható a kanban mérete és a mennyisége."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f9e0ccf25a346d54e48f51b0866f0c11e98bf0a0
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Kanbanmennyiségi irányelv hozzáadása egy kanbanszabályhoz

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez a folyamat egy kanbanmennyiség-számítási irányelv létrehozására irányul, valamint annak hozzáadásához egy kanbanszabályhoz, amivel optimalizálható a kanban mérete és a mennyisége. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás az érték-előállítási folyamat vezetője számára készült. Ez az eljárás a Kanbanmennyiség-javaslatok kiszámítása eljárás létrehozásának előfeltétele. 


## <a name="create-a-kanban-quantity-calculation-policy"></a>Kanbanmennyiség-számítási irányelv létrehozása
1. Ugorjon a Gyártásvezérlés > Időszakos feladatok > Kanbanmennyiség-számítás > Kanbanmennyiség-számítási irányelvek lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
    * Például, írja be a Speaker2016 szöveget.  
4. Az Alapterv mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a StaticPlan lehetőséget a kereslet kiszámolására.  
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Kattintson a Mentés gombra.
8. A Minimális kanbanmennyiség mezőben adja meg az „1” értéket.
    * Ez a kanbanmennyiség-számításban szerepeltetett további kanbanok száma.  
9. Állítsa a biztonsági tényezőt „1” értékre.
    * Ez a további biztonsági készletmennyiség kiszámításához használt tényező.  
10. Az Elkövetkező napok száma mezőbe írja be a „30” értéket.
    * Ez a kanbanmennyiség kiszámítási dátumát megelőző napok száma, amelyek az igényszámítás részét képezik.  
11. Az Elmúlt napok száma mezőbe írja be a „30” értéket.
    * Ez a kanbanmennyiség kiszámítási dátumát követő napok száma, amelyek az igényszámítás részét képezik.  A számításokhoz használt képletet valódi értékekkel mutatjuk be. Például, kanbanmennyiség = ((átlagos napi igény x átfutási idő x 2,00) / termékmennyiség anyagkezelési egységenként) + 1  
12. Zárja be a lapot.

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Kanbanmennyiség-számítási irányelv hozzáadása a kanbanszabályhoz
1. Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a 000020 kanbanszabályt ehhez az eljáráshoz.  
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Bontsa ki a Kanbanmennyiség-számítási irányelvek részt.
5. Kattintson a Hozzáadás gombra.
    * Vegye fel a kanbanmennyiség előző alfeladatban létrehozott számítási irányelvét.  
6. A listában jelölje meg a kiválasztott sort.
7. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki a előző alfeladatban létrehozott Speaker2016 irányelvet.  


