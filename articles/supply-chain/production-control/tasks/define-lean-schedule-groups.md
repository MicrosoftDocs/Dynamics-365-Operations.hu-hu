---
title: Lean ütemezési csoportok meghatározása
description: A lean ütemezési csoportok definiálásával csoportosíthatók és különböztethetők meg a termékek a kanbanütemezésben.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 647e721a0616ceae387322517f2955d75c06bfd2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828754"
---
# <a name="define-lean-schedule-groups"></a>Lean ütemezési csoportok meghatározása

[!include [banner](../../includes/banner.md)]

A lean ütemezési csoportok definiálásával csoportosíthatók és különböztethetők meg a termékek a kanbanütemezésben. A csoportosítás vállalatonként általános társításként hozható létre vagy munkacella-specifikusként. Mindegyik csoport rendelkezik egy színkóddal, amely a vizuális jelöléshez kell a kanbanütemezési listaoldalon. Ez az eljárás az USMF bemutatócéget használja.


## <a name="define-lean-scheduling-group"></a>Lean ütemezési csoport meghatározása
1. Ugorjon a Termékinformációk kezelése > Lean manufacturing > Lean ütemezéscsoportok lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket az Ütemezés mezőbe.
    * Egy ütemezéscsoportot meg lehet határozni globális csoportként vagy úgy, hogy egy konkrét munkacellára vonatkozzon. Ebben az egyszerű példában egy globális csoportot definiálunk, és a munkacella üres marad. Ezen csoport beállításai vonatkoznak minden munkacellára, amelyek nem rendelkeznek külön ütemezésicsoportokkal.  
4. Válasszon egy színt a színválasztékból.
    * A színek jelölik a feladatokat a kanbanütemezés listaoldalán vagy a kanban-folyamattáblán.  
5. A listában jelölje meg a kiválasztott sort.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.

## <a name="associate-product"></a>Termékek társítása
1. Egy konkrét termék társítása
    * Két módon lehet lean ütemezési csoportokhoz társítani termékeket; vagy konkrét termékként (cikk-kapcsolat típusa = Cikk) vagy egy cikkfelosztási kulcs részeként (cikk-kapcsolat típusa = csoport).    
2. A Cikk-kapcsolat típusa mezőben válassza ki a „Cikk” lehetőséget.
3. A cikkmezőbe írjon egy értéket.
4. Adjon meg egy számot a Teljesítmény aránya mezőben.
    * Az alapértelmezett teljesítményarány 1, amely azt jelenti, hogy a kapcsolódó termékek pontosan a termelési folyamatok folyamattevékenységeiben megadott kapacitást használják fel. A > 1 teljesítményarány egy magasabb erőforrás-felhasználást határoz meg, a < 1 teljesítményarány egy alacsonyabb erőforrás-felhasználást határoz meg. Az arány a költségszámításhoz és a kanbanfeladat felhasználásának kiszámítására használatos.  

## <a name="associate-item-allocation-key"></a>Cikkfoglalási kulcs társítása
1. Cikkfoglalási kulcs társítása
    * Adjon hozzá egy társítást egy cikkfelosztási kulcshoz a Cikk-kapcsolat típusa csoport segítségével.   Ne feledje, hogy ehhez a folyamathoz, meg kell határozni az adatokban egy előrejelzett cikkfelosztási kulcsot.  
2. A Cikk-kapcsolat típusa mezőben válassza ki a „Csoport” lehetőséget.
3. A Cikkfoglalási kulcs mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]