---
title: Folytonossági ütemezések meghatározása
description: Ez a témakör végigvezeti a folyamatos program (más néven ismétlődő rendelések) beállításának lépésein.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd70780927bb9aaa19c196705d6e8fa1c247ea66
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "330517"
---
# <a name="define-continuity-schedules"></a>Folytonossági ütemezések meghatározása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez a témakör végigvezeti a folyamatos program (más néven ismétlődő rendelések) beállításának lépésein. Ez a témakör az USRT cég bemutatóadatait használja.


## <a name="create-continuity-program"></a>Folytonos program létrehozása
1. Ugorjon a Kiskereskedelem és kereskedelem > Folytonosság > Hűségprogramok elemre.
2. Kattintson az Új lehetőségre.
3. Az Ütemezésazonosító mezőben adja meg a folytonossági ütemezés azonosítóját.
4. A Rendelés kezdete mezőben válassza az „Első esemény” lehetőséget.
    * Ha egy vevő új rendelést küld be a folytonos programba, a termékszállításra két lehetőség kínálkozik: 1. Első esemény: a folytonos program első terméke kerül kiszállításra.  2. Aktuális esemény: az aktuális termék kerül kiszállításra. Például: a vevő a program három hónapjának elteltével kapja meg a harmadikat a programban.  
5. Jelölje be az „Igen” lehetőséget, és a rendszer rákérdez a rendelés kezdő dátumára.
6. Kattintson az Új sor hozzáadása lehetőségre.
7. A Cikkszám mezőbe írja be az első termék cikkszámát (0013).
8. Írja be a következőt: „CP”.
9. Adja meg a dátumot, amikor az első termék rendelhető lesz.
10. Kattintson az Új sor hozzáadására.
11. A cikkszám mezőbe írja be a „0014” értéket.
12. A Dátumtartomány kódja mezőben törölje az értéket, hogy a mező üres legyen.
    * Ehhez az eljáráshoz törölje a dátumintervallumot. A dátumot növekményes módon kell beállítani az első cikk kezdési dátumától.  
13. Itt kell megadni a termékek szállítási intervallumát. Írja be a következőt: „30”.
    * Havi programnál 30 napot kell beírni időszakként.  
14. Kattintson az Új sor hozzáadása lehetőségre.
15. A cikkszám mezőbe írja be a „0015” értéket.
16. Írja be a következőt: „Vége”.
17. Kattintson a Mentés gombra.

## <a name="assign-to-continuity-item"></a>Hozzárendelés folytonos elemhez
1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. Válassza ki a „0016” elemet.
    * Ehhez az eljáráshoz válassza ki a 0016-os cikkszámot. Általában ekkor már létrehozott egy kibocsátott terméket, amelyre további folyamatos üzleti logika kerül alkalmazásra, amikor a hívásközpontban bekerül egy értékesítési rendelésbe.  
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a Szerkesztés lehetőségre.
5. Bontsa ki vagy csukja össze a(z) Értékesítés szakaszt.
6. Itt lehet megadni a folytonosság programot, amelyet ez a cikk képvisel. Írja be a korábban létrehozott ütemezésazonosítót.
    * Amikor sor kerül ennek a cikknek az eladására egy hívásközpontban, további üzleti logika kerül alkalmazásra a kijelölt folytonos programra.  
7. Kattintson a Mentés gombra.

