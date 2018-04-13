--- 
title: "Kanbanmennyiség-javaslatok kiszámítása"
description: "Ez a folyamat a kanbanméret és -mennyiség egy adott kanbanszabályhoz történő optimalizálására irányul a kanbanmennyiség-számítás használatával."
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
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a817dbc02890d863f68c5bf2a6cc11b9a5328060
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-kanban-quantity-suggestions"></a>Kanbanmennyiség-javaslatok kiszámítása

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ez a folyamat a kanbanméret és -mennyiség egy adott kanbanszabályhoz történő optimalizálására irányul a kanbanmennyiség-számítás használatával. Ez az eljárás az USMF bemutatócéget használja. Ez az eljárás az érték-előállítási folyamat vezetője számára készült. Előfeltétele az Új kanban mennyiségszámítási irányelv hozzáadása a kanbanszabályhoz eljárás elvégzése.


## <a name="create-a-kanban-quantity-calculation"></a>Kanbanmennyiség-számítás létrehozása
1. Ugorjon a Gyártásvezérlés > Időszakos feladatok > Kanbanmennyiség-számítás > Kanbanmennyiség kiszámítása lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Név mezőbe írja be a „Speaker2016” szöveget.
4. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Válassza ki a létrehozott irányelvet az Új kanban mennyiségszámítási irányelv hozzáadása a kanbanszabályhoz eljárásban. Például, Speaker2016.  
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A Szabály aktiválási dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-12-17T08:00:00”.
    * Ez a dátum szolgál a kanbanmennyiség számításába bevont rögzített kanbanszabályok meghatározásának alapjául.  
7. A Teljesített igény időszakának kezdő dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-11-17T09:00:00”.
    * Az a dátum, amikortól a múltbeli igénytranzakciók bekerülnek a kanbanmennyiség számításába.  
8. A Teljesített igény időszakának záró dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-12-17T07:59:59”.
    * Az a dátum, ameddig a múltbeli igénytranzakciók bekerülnek a kanbanmennyiség számításába.  
9. Az Igényidőszak kezdő dátuma mezőben következőképpen adja meg a dátumot és az időt „2012-12-17T08:00:00”.
    * Az a dátum, amikortól az aktuális igénytranzakciók bekerülnek a rögzített kanbanmennyiség számításába.  
10. Az Igényidőszak záró dátuma mezőben következőképpen adja meg a dátumot és az időt „2013-01-16T07:59:59”.
    * Az a dátum, ameddig az aktuális igénytranzakciók bekerülnek a kanbanmennyiség számításába.  

## <a name="generate-kanban-quantity-proposal"></a>Kanbanmennyiség-javaslat generálása
1. Kattintson a Mentés gombra.
2. Kattintson a Létrehozás lehetőségre.
    * Ez létrehoz egy kanbanmennyiségi javaslatsort a 000020 kanbanszabályhoz.  

## <a name="run-kanban-quantity-calculation"></a>Kanbanmennyiség-számítás futtatása
1. Kattintson a Számítás lehetőségre.
    * Ez számítja ki a kanbanmennyiség-javaslatot.  
2. Kattintson az OK gombra.
3. A listában jelölje meg a kiválasztott sort.
    * Ne feledje, hogy a javasolt kanbanmennyiség a 2.  

## <a name="change-product-quantity-and-calculate-again"></a>Termékmennyiség módosítása és számítás újbóli elvégzése
1. Állítsa a Termékmennyiséget az „5” értékre.
2. Kattintson a Számítás lehetőségre.
3. Kattintson az OK gombra.
    * Ne feledje, hogy 5-ös kanbanmennyiségnél a javasolt kanbanmennyiség 4-re változik.  
    * Ennek oka az, hogy alacsonyabb termékmennyiség esetén több kanbanbra van szükség az igény teljesítésére.  

## <a name="update-kanban-rule"></a>Kanbanszabály frissítése
1. A Szabály hatályba lépési dátuma mezőben adjon meg egy dátumot és időpontot.
    * Állítsa a „Szabály aktiválási dátuma” értéket egy jövőbeli dátumra. Például a mai dátum + egy év.  
2. Kattintson a Módosítás gombra.
3. Kattintson az OK gombra.
4. Zárja be a lapot.

## <a name="validate-change-on-kanban-rule"></a>Kanbanszabály módosításának ellenőrzése
1. Ugorjon a Termékinformációk kezelése > A lean manufacturing > Kanbanszabályok lehetőségre.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki az előző alfeladatban létrehozott kanbanszabályt. Ez lesz az első kanbanszabály a számok szerint rendezett listában.  
3. Bontsa ki a Részletek részt.
    * Ne feledkezzenek meg az érvénybe lépési dátumról, amely azt jelzi, hogy a szabály nem aktiválódik az adott dátumig.  
4. Bontsa ki a Mennyiségek részt.
    * Ne feledje, hogy ez a kanbanmennyiség-számítás során megadott alapértelmezett mennyiség.  
    * Ne feledje, hogy ez a rögzített 4-es kanbanmennyiség a kanbanmennyiség-számításból.  
5. Kattintson a ListPanel fülre.


