--- 
title: "Szállítói fizetési áttekintés"
description: "Ez a feladatútmutató végigvezeti a szállítói kifizetések létrehozásához használt különböző módszereken, többek között a fizetési javaslat használatán, vagy egy egyszeri fizetés manuális rögzítésén."
author: kweekley
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cafd499e849570cae7b7f58bf2d487a7ac0093e6
ms.openlocfilehash: e9a94231f755ff23bb442d62e90daff8f2d1f4fb
ms.contentlocale: hu-hu
ms.lasthandoff: 10/30/2017

---
# <a name="vendor-payment-overview"></a>Szállítói fizetési áttekintés

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladatútmutató végigvezeti a szállítói kifizetések létrehozásához használt különböző módszereken, többek között a fizetési javaslat használatán, vagy egy egyszeri fizetés manuális rögzítésén. Ez az eljárás az USMF bemutatócéget használja.

1. Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
3. Válassza ki a kifizetési naplót, amelybe a szállítói kifizetéseket menti. 
4. Válassza ki a naplót, vagy manuálisan adja meg.
5. Kattintson a Sorok pontra.
6. Kattintson a Fizetési javaslat lehetőségre.
7. Kattintson a Fizetési javaslat létrehozása lehetőségre.
    * A fizetési javaslat egy lekérdezés, amely a kifizetendő számlák kiválasztásában segít. Szerkesztheti a fizetendő számlák listáját a szállítói kifizetések létrehozása vagy generálása előtt.  
8. Válassza ki a számlákat esedékesség dátuma, készpénzfizetési engedmény vagy mindkettő szerint kifizetendő számlák szerint. 
9. Adja meg a dátumot az esedékességi dátum vagy a készpénzfizetési engedmény dátumával való összehasonlításhoz. 
10. Választható: Az összes kifizetésekhez használt fizetési dátum megadása.
    * Az itt megadott dátum lesz a fizetési dátum minden létrehozott kifizetéshez, függetlenül a határidőtől vagy a készpénzfizetési engedmény dátumától.  
11. Választható: A fizetési dátumként használt minimális kifizetési dátum megadása.
    * A minimális kifizetési dátum a kifizetések létrehozásakor használt legkorábbi dátum. Ha például egy számla a minimális kifizetési dátum után esedékes, az esedékességi dátum lesz a kifizetési dátum a minimum kifizetési dátum helyett annak érdekében, hogy a lehető legkésőbbi időpontban kerüljön kifizetésre a számla.  
12. Adjon meg a további lekérdezési korlátozásokat a Szerepeltetni kívánt bejegyzések alatt.
    * A szűrő gyakran használatos a fizetésre kiválasztott számlák korlátozására szállítói csoport vagy fizetési mód szerint. Például hozzáadhat egy szűrőt, hogy csak a csekkes számlákat fizesse ki ebben a fizetési időszakban.  
13. Adjon meg további lekérdezési korlátozás vagy a fizetési alapértelmezéseket. 
    * A további paraméterekkel megadható a kifizetés pénzneme, lehetővé tehetők a központosított kifizetések ebben a fizetési időszakban.  
14. Kattintson az OK gombra.
    * Miután rákattint az OK gombra, a lekérdezés eredményei jelennek meg. Ha nem szeretné a kifizetésre kiválasztott számlák listáját megtekinteni, lépjen vissza a Paraméterek gyorslapra, és módosítsa a Fizetések létrehozása számlák előnézete nélkül beállítást Yes értékre.  
15. A Kifizetés megjelenítése gombra kattintva megtekintheti a kifizetéseket, amelyeket a kiválasztott számlán szereplő szállítóhoz hoz létre.
16. A Kifizetés elrejtése gombra kattintva elrejtheti a kifizetéseket. 
17. Kattintson a Fizetések létrehozása lehetőségre.
    * A Fizetések létrehozása előtt kattintson jobb gombbal a rácsra, és exportálja a számlák listáját az Excel programba. A Kifizetések létrehozása gombra kattintva létrejön a szállítói kifizetések a kifizetési naplóban.  
18. Olvassa be a kifizetéseket, és ellenőrizze, hogy minden kifizetéshez a fizetési mód meg van adva. 
    * Ha generálja a kifizetéseket, például csekk nyomtatás vagy egy elektronikus befizetés létrehozásával, a fizetési módot meg kell adni. A fizetési mód alapértelmezés szerint a bankszámla, amelyről a kifizetés történik.  
19. Az Új gombra kattintva hozzon létre egy egyszeri kifizetést.
    * Egyszeri fizetés bármikor adható hozzá a kifizetési naplóhoz a feladás előtt. Ez az Új gombra kattintással, és a fizetési adatok manuális hozzáadásával történet a Fizetési javaslat használata helyett.  
20. Válassza ki a szállítót, akinek a kifizetés történik.
21. Kifizetendő számla esetén válassza a Tranzakciók kiegyenlítése lehetőséget a kifizetendő számla kijelöléséhez.
    * Ha ez előleg, ez a lépés nem kötelező. A kifizetés számla kijelölése nélkül is létrehozható.  
22. Jelölje be a fizetendő számlákat.
    * A Kiegyenlítési tranzakciók segítségével válassza ki a számlákat a kifizetéshez, a kifizetett összeg automatikusan kiszámítódik a kifizetésre kijelölt számlák alapján, és a Kiegyenlítendő összeg mezőben megadott mennyiség alapján.  
23. Kattintson az OK gombra.
24. Ha törölni szeretne egy kifizetést, jelölje meg a sort.
25. Kattintson a Törlés gombra.
    * Egy kifizetés törlése csak a fizetést törli. A fizetéshez megjelölt számlák továbbra is elérhetők lesznek egy másik fizetéshez.  
26. Kattintson az Igen gombra.
27. Válassza ki a Fizetés létrehozása pontot a csekkek nyomtatásához, vagy az elektronikus kifizetési fájl létrehozásához.
28. Válassza ki a létrehozni kívánt kifizetési módot.
    * A kifizetési napló tartalmaz kifizetéseket mind csekkes és elektronikus formában, de egyszerre csak egy fizetéstípust készíthet.  
29. Válassza ki a bankszámlát, amelyről a kifizetéseket létrehozza.
30. Kattintson az OK gombra.
    * Kifizetések csak olyan fizetésekhez hozhatók létre, amelyek megfelelnek a fizetési módnak és a kijelölt bankszámlának.  
31. Csekkek generálásánál válassza a Dokumentum lehetőséget a csekkekhez megfelelő nyomtatási cél biztosításához.
32. Kattintson az OK gombra.
33. A kifizetések előállításához kattintson az OK gombra.
34. Kattintson a Feladás gombra, ha minden kifizetés jóváhagyása és létrehozása megtörtént. 


