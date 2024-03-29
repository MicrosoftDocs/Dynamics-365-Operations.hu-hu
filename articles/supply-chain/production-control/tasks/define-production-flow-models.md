---
title: Termelési folyamatmodellek meghatározása
description: A termelési folyamatmodellek írják le, hogyan kell kiszámítani és karban tartani a lean manufacturing munkacelláinak kapacitását.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlowModel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fb12be6f744cee8af3a845d6b278d1f1462ec5d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579136"
---
# <a name="define-production-flow-models"></a>Termelési folyamatmodellek meghatározása

[!include [banner](../../includes/banner.md)]

A termelési folyamatmodellek írják le, hogyan kell kiszámítani és karban tartani a lean manufacturing munkacelláinak kapacitását. Ennek megfelelően a termelési folyamatmodell meghatározása előfeltétele a munkacellák meghatározásának. Ez az eljárás az USMF bemutatócéget használja.


## <a name="define-a-production-flow-model"></a>Definiáljon egy termelési folyamatmodellt. 
1. Lépjen a Gyártásvezérlés > Beállítás > Lean típusú termelési folyamat > Termelési folyamatmodellek lehetőségre.
2. Kattintson az Új lehetőségre.
3. A Termelési folyamatmodell mezőben adja meg a termelési folyamatmodell azonosítóját.
4. Válasszon ki egy lehetőséget a Modelltípus mezőben.
    * Kétfajta modelltípus lehetséges: Teljesítmény és Órák. A Teljesítmény típus esetében a munkacellák kapacitása, amelyek ezt a termelési folyamatmodellt használják, termékmennyiségekben lesznek kifejezve és kiszámítva. Az Órák típus esetében a munkacellák kapacitása, amelyek ezt a termelési folyamatmodellt használják, órákban lesznek kifejezve és kiszámítva. Vegye figyelembe, hogy ez a tulajdonság nem módosítható egy meglévő termelési folyamatmodell esetében. Ha egy munkacella már rendelkezik kapacitásfoglalással, a termelési folyamatmodell típusát nem lehet módosítani.  
5. Adja meg az EPE-ciklus hosszát napokban.
    * Az intervallum azt az időszakot írja le, amikor minden, egy termelési folyamat vagy munkacella által előállított rész legalább egyszer elő lesz állítva. Minél rövidebb az EPE-ciklus, annál rugalmasabb a termelési folyamat. Ha az EPE ciklus = 0, minden igény előállítható ugyanazon a napon. Az EPE-ciklus használatos lean folyamatfeladatok ütemezésére használatos. Egy feladat ütemezésekor, amikor az EPE-ciklus = 5, az ütemezési folyamat az EPE-ciklus esedékes dátumán (5 nappal az esedékes dátum előtt) kapacitást fog keresni a munkacellán, ezzel biztosítva, hogy a terméket elő lehessen állítani abban a ciklusban. Egy termék leltárátfutási ideje rendszerint egyenlő vagy nagyobb, mint a kapcsolódó termelési folyamat EPE-ciklusa.  
6. Válassza ki valamelyik lehetőséget az Tervezési időszak típusa mezőben.
    * Ha egy munkacella már rendelkezik kapacitásfoglalással, a tervezési időszak típusát nem lehet módosítani. Ehhez az adott munkacellához csak azonos időszaktípusú termelési folyamatmodellt választhat.  
7. A Tervezésin időkeret mezőben adjon meg egy számot.
    * A tervezési időkorlát napokban írja le, hogy mikor lehet kapacitásfoglalást tenni a kapcsolódó munkacellákhoz. A tervezési időkorlát megadása napokban.   Az ezen időkorláton kívülre eső kanbanfeldolgozási feladatok esetében nincs automatikus tervezés. Tervezési időkorláton általában kétszerese az átlagos készletátfutási időnek termelési folyamatban vagy munkacellában előállított termékek esetén. Az EPE-ciklus nem lehet nagyobb, mint a tervezési időkorlát fele.     
8. Egy lehetőség kiválasztása a Kapacitáshiányra való reagálás mezőben.
    * A lehetőségek a következők: Elhalasztás – Az ütemezési esemény teljes igényének elhalasztása a következő elérhető termelési napon, rendelkezésre álló kapacitással. Érvénytelenítés – Az ütemezési esemény automatikus tervezésének befejezése és a kapcsolódó feladatok nem tervezettként hagyása.   Hozzáadás a kért naphoz – A kért feladatok megtervezése a kért időszakban. Ez a cella túlterhelése az adott napra, és megkövetel egy tervező által végzett vizsgálatot és kézi beavatkozást.   Rendelkezésre álló időszakokra elosztás – Elosztja az ütemezési esemény különböző feladatait az összes rendelkezésre álló termelési napra, az első elérhető naptól kezdődően. A minimális elosztási mennyiség a kanbanfeladat-mennyiség. A felosztás hozzárendeli a minimális tervezési mennyiséget (kanbanmennyiség) minden naphoz, amely elegendő elérhető teljesítménnyel rendelkezik.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]