---
title: Kanbanmennyiségi irányelv hozzáadása egy kanbanszabályhoz
description: Ez a folyamat egy kanbanmennyiség-számítási irányelv létrehozására irányul, valamint annak hozzáadásához egy kanbanszabályhoz, amivel optimalizálható a kanban mérete és a mennyisége.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a844d455b1e583f234ddc47280f5cac8ee0ab852
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579280"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a>Kanbanmennyiségi irányelv hozzáadása egy kanbanszabályhoz

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]