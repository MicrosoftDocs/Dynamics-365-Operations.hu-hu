--- 
title: "Beszerzési katalógus létrehozása"
description: "Ez az segédlet bemutatja, hogyan lehet beszerzési katalógust létrehozni."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-procurement-catalog"></a>Beszerzési katalógus létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az segédlet bemutatja, hogyan lehet beszerzési katalógust létrehozni. Ezt a feladatot tipikusan egy beszerzési szakember végzi el. Azt is megtudhatja, hogy hogyan használhatják az alkalmazottak a katalógust egy igénylést létrehozásakor. Katalógus létrehozása előtt már kell egy beszerzési kategória hierarchiával rendelkeznie a rendszerben. Az új katalógussal örökli a hierarchiát, minden olyan termékkel együtt, ami a hierarchiában benne van. Használhatja ezt a segédletet az USMF bemutató adatok vállalatban, ahol a beszerzési kategóriák hierarchiája rendelkezésre áll, ugyanúgy, mint az eljárásban használt példák.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Győződjön meg arról, hogy létezik a beszerzési kategóriák hierarchiája
1. Ugorjon a Beszerzés és forrás > Beszerzési kategóriák pontra.
    * Egy beszerzési kategória hierarchia elérhető az USMF bemutató adatok vállalatnál és az Irodai gépek/Számítógépek kategóriához termékek lettek hozzáadva. Ha ezt a folyamatot feladat-útmutatóként használja, szüksége lehet az útmutató feloldására a kategóriák kereséséhez. Ha a hierarchia nem volt elérhető, hozzon létre egyet az Új gombra kattintva. Ez csak egyszer lehetséges.  
2. Zárja be a lapot.

## <a name="create-a-catalog"></a>Katalógus létrehozása
1. Ugorjon a Beszerzés és forrás > Katalógusok > Beszerzési katalógusok pontra.
2. Az Új beszerzési katalógus gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. Írjon be egy értéket a Név mezőbe.
4. Kattintson az OK gombra.
5. A fán, nyissa ki a „CORP PROCUREMENT CATEGORIES” pontot.
6. A fán, nyissa ki az „OFFICE MACHINES” pontot.
7. A fán, válassza a „Computers” pontot.
    * A beszerzési kategóriából származó termékek megjelennek a listában. Ha szeretne terméket hozzáadni a kategóriához, akkor ezt a Beszerzési kategóriák hierarchiája lapon vagy a Cikk részletei lapon teheti meg.  
    * Az Alapértelmezett frissítés típus meghatározza, hogy az új termékek amelyek hozzá lettek adva a beszerzési kategóriák hierarchiájához azonnal jelenjenek meg a katalógusban. Ha a frissítés típusa Dinamikus, a módosítások azonnal megjelennek. Ha a frissítés típusa Statikus, az új termékek csak azoknak az emberek számára fog megjelenni, akik az újra kiadott katalógust használják. A közzététel művelet a Művelet ablakban érhető el az oldal tetején. Ha termékek lettek eltávolítva a beszerzési kategóriák hierarchiájából, a változás azonnal látható, az Alapértelmezett frissítés típusától függetlenül.  
8. Keresse meg és jelölje ki a kívánt rekordot a listán.
9. Kattintson az Elrejtésre.
10. A Műveleti ablakban kattintson a Kategóriák szerinti navigációra.
11. Kattintson a Letiltásra.
12. A Műveleti ablakban kattintson a Kategóriák szerinti navigációra.
13. Kattintson az Engedélyezés gombra.
14. Kattintson a katalógus aktiválására.
15. Zárja be a lapot.

## <a name="make-the-catalog-visible"></a>Tegye láthatóvá a katalógust
1. Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Irányelvek > Beszerzési irányelvek.
2. Válassza az USMF Beszerzési Irányelvet.
    * Ki kell választania a beszerzési irányelvet ahhoz jogi személyhez amihez a dolgozó csatlakozik és aminek a felhasználói profilja termékek rendelésére engedélyezett. A USMF bemutató adatokban, az Admin felhasználó a Julia Funderburk nevű dolgozóhoz van csatlakoztatva és ő rendeli meg a termékeket az USMF-ben alapértelmezés szerint.  
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Válassza ki a most létrehozott katalógust.
5. Kattintson az OK gombra.
6. Zárja be a lapot.
7. Zárja be a lapot.

## <a name="use-the-catalog"></a>Használja a katalógust
1. Ugorjon a Beszerzés és forrás > Beszerzési igénylések > Összes beszerzési igénylés pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. Kattintson az OK gombra.
5. Kattintson a Termékek hozzáadása elemre.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Használhatja a bal oldalon található kategóriahierarchiát vagy a lista tetején található szűrőt a termékek szűréséhez.  
7. Kattintson a Hozzáadás a sorokhoz elemre.
8. Keresse meg és jelölje ki a kívánt rekordot a listán.
9. Kattintson a Hozzáadás a sorokhoz elemre.
10. Kattintson az OK gombra.


