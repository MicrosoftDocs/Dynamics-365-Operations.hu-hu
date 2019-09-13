---
title: Manuálisan létrehozott munkarendelések
description: Ez a cikk azt mutatja be, hogyan lehet manuálisan munkarendeléseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875692"
---
# <a name="manually-created-work-orders"></a>Manuálisan létrehozott munkarendelések

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


A munkarendelések manuális létrehozására két mód van:

- Az **Összes munkarendelés** vagy az **Aktív munkrendelések** részen  
- Az **Összes karbantartási kérés**, az **Aktív karbantartási kérések** vagy a **Saját munkavégzési helyszínhez tartozó karbantartási kérések** részen  

## <a name="create-work-order"></a>Munkarendelés létrehozása

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Kattintson az **Új** gombra.

3. A **Munkarendelés létrehozása** legördülő listából válassza ki a munkarendelés típusát.

4. Ha szükséges, válasszon ki leírást.

5. Válassza ki az eszközt a munkarendeléshez, valamint a karbantartási feladat típusát.

>[!NOTE]
>Az eszköz kiválasztásakor három lap érhető el: A **Saját eszközök** lap azokat a munkavégzési helyszínekhez kapcsolódó eszközöket tartalmazza, amelyekhez Önt (a rendszerre bejelentkezett dolgozót) beoszthatják (a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) részen állítható be). Ha nincs beállítva munkavégzési helyszín a dolgozóhoz a [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md) részen, akkor a **Saját eszközök** lap nem lesz látható. Az **Aktív eszközök** lap az „Aktív” eszköz-életciklus állapotú eszközök listáját tartalmazza. Az **Eszköznézet** lap a munkavégzési helyszínek és a helyszínekre telepített eszközök fanézetét jeleníti meg.

6. Ha szükséges, válassza ki a **karbantartási feladat típusának változatát** és az **ügyletet**.

7. Ha szükséges, módosíthatja a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.

8. Válassza ki a várt kezdési és befejezési dátumot a megfelelő mezőkben.

9. Az új munkarendelés létrehozásához kattintson az **OK** lehetőségre.

10. Ha szükséges, módosítsa a munkarendelést az **Összes munkarendelés** részen.

- Az **Összes munkarendelés** részen több eszközt is hozzáadhat egy munkarendeléshez a Részletek nézetben, ha hozzáadja a sorokat a **Munkarendelés karbantartási feladatai** gyorslapon. Egy eszköznél csak az eszközhöz kiválasztott eszköztípuson megadott karbantartásifeladat-típusok közül lehet választani.  
- Ha módosította egy eszköz szolgáltatási szintjét vagy egy eszköz kritikussági típusát, miután használta az eszközt a munkarendeléshez (lásd: [Eszköz szolgáltatásszintjei](../setup-for-objects/object-priorities.md) és [Eszközkritikusságok](../setup-for-objects/object-criticalities.md)), akkor a munkarendelésen szereplő szolgáltatási szint vagy kritikusság nem frissül ennek megfelelően.
- A program minden alkalommal újraszámolja a munkarendelésen szereplő kritikusságot, amikor a munkarendeléshez hozzáadnak vagy róla eltávolítanak egy munkarendelési sort.
- Az **Összes munkarendelés** Részletek nézet > **Fejléc** nézet > **Ütemezés** gyorslapon kiválaszthatja a felelős karbantartási dolgozói csoportot vagy a felelős karbantartási dolgozót a **Felelős csoport**vagy a **Felelős** mezőben. Ezek a beállítások mindaddig módosíthatók, amíg a munkarendelés aktív, ha például a munkarendelés életciklus-állapota megváltozik. A munkarendelés létrehozása során végzett automatikus kiválasztás a **Felelős karbantartási dolgozók** rész beállításain alapul. Ha egy munkarendelés létrehozása után hozzáadja vagy eltávolítja a munkarendelési feladatokat, és a **Felelős csoport** és a **Felelős** mező üresen marad, amikor frissíti a munkarendelést, az Eszközkezelő esetlegesen egyező felelős karbantartási dolgozói csoportot vagy felelős karbantartási dolgozót keres a beállítási képernyőn. Ha a **Felelős csoport** vagy a **Felelős** mező ki van töltve a munkarendelés frissítésekor, akkor nem történik módosítás. 

- A **Karbantartás állapota** részen számítást végezhet, hogy áttekintést kapjon a beérkező és a teljesített munkarendelésekre vonatkozó terhelésekről.  

- A **Sor részletei** gyorslapon a **Szélesség** és a **Hosszúság** mezőkben földrajzi koordinátákat adhat a munkarendelési feladathoz kiválasztott eszközhöz.  

## <a name="create-related-work-order"></a>Kapcsolódó munkarendelés létrehozása

Meglévő munkarendeléshez kapcsolódó munkarendelést is létrehozhat, ha például elsődleges és másodlagos munkarendelésekkel szeretné elvégezni a munkát. Az új munkarendelés egy meglévő munkarendelésből származó munkarendelési feladaton alapul.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki azt a munkarendelést, amelyhez kapcsolódó munkarendelést szeretne létrehozni.

3. Kattintson a **Kapcsolódó munkarendelés** elemre.

4. A **Kapcsolódó munkarendelés létrehozása** legördülő párbeszédpanelen válassza ki azt a munkarendelési feladatot, amelyhez kapcsolódó munkarendelést szeretne létrehozni a **Munkarendelési feladat** mezőben.

5. Válassza ki a karbantartási feladat típusát a **Karbantartási feladat típusa** mezőben, és ha szükséges, karbantartási feladat típusának változatát és az ügyletet a **Karbantartási feladat típusának változata** és az **Ügylet** mezőben.

6. Ha ez az első létrehozandó kapcsolódó munkarendelés, kapcsolja be az **Új munkarendelés** választógombot.

7. A kapcsolódó mezőkben válasszon **Munkarendelési típust** és **leírást**.

8. Ha szükséges, módosítsa a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.

9. Szúrja be a várt kezdési és befejezési dátumot a megfelelő mezőkbe.

10. Kattintson az **OK** gombra. Az új kapcsolódó munkarendelés az **Összes munkarendelés** listában jelenik meg.

11. Ha olyan munkarendeléshez hoz létre kapcsolódó munkarendelést, amelyhez már tartozik kapcsolódó munkarendelés, akkor a munkarendelési feladatot a már hozzárendelt munkarendeléshez is hozzáadhatja. Ehhez jelölje be a 6. lépésben említett **Hozzáadás kapcsolódó munkarendeléshez** választógombot. Ezután válassza ki azt a kapcsolódó munkarendelést, amelyhez hozzá szeretné adni az új munkarendelési feladatot. Szükség szerint módosítsa a **Szolgáltatási szint**, a **Várható kezdés** és a **Várható befejezés** mezőt, majd kattintson az **OK** gombra. A munkarendelési feladatot a program hozzáadja a meglévő kapcsolódó munkarendeléshez.


![1. ábra](media/03-work-orders.png)

**Megjegyzés:** Ha egy összekapcsolt munkarendeléshez maszkot állított be az **Eszközkezelés paraméterei** > **Munkarendelések** hivatkozás > **Kapcsolódó munkarendelési maszk** mezőben, akkor a program a maszk beállításaival összhangban hozza létre a munkarendelés azonosítóit. Ha nincs beállítva maszk a kapcsolódó munkarendeléshez, akkor a program a következő elérhető munkarendelési azonosítót fogja használni a kapcsolódó munkarendelésekhez.

## <a name="copy-work-order"></a>Munkarendelés másolása

Meglévő munkarendelésből gyorsan lehet új munkarendelést létrehozni. A munkarendelések ilyen használata különbözik a munkarendelések karbantartási tervek alapján történő létrehozásával. Ez például akkor lehet hasznos, ha a munkarendelés különböző olyan munkarendelési feladatokat tartalmaz, amelyek esetében adott időszakokban különböző eszközökön kell feladatokat elvégezni.

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki azt a munkarendelést, amelynek a tartalmát le szeretné másolni.

3. Kattintson a **Munkarendelés másolása** elemre. Megjelenik a kiválasztott munkarendelés beállítása. Ha szükséges, módosíthatja a mezőket.

4. Az új munkarendelés létrehozásához kattintson az **OK** elemre.

5. Ha szükséges, módosítsa a munkarendelést az **Összes munkarendelés** részen.

>[!NOTE]
>Az új munkarendelés létrehozásakor néhány információt közvetlenül a meglévő munkarendelésből másol a rendszer. A program nem másolja át az előrejelzéseket, az eszközöket, a karbantartási ellenőrzőlistákat, a munkavégzési helyszínt, a címeket és az ütemezést, de az Eszközkezelés aktuális beállításai alapján végzi az inicializálást. Ez azt jelenti, hogy ha az első munkarendelés létrehozási időpontja és a munkarendelés másolása közötti időszakban módosultak a munkarendelés adatai, akkor ezek a módosítások szerepelnek az újonnan létrehozott munkarendelésben. Ilyenek például az előrejelzések vagy a frissített karbantartási ellenőrzőlisták változásai.


![2. ábra](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a>Munkarendelés létrehozása karbantartási kérés alapján

1. Kattintson az **Eszközkezelés** > **Közös** > **Karbantartási kérések** > **Összes karbantartási kérés** vagy **Aktív karbantartási kérések** elemre.

2. Válassza ki azt a karbantartási kérést, amelyhez munkarendelést szeretne létrehozni, majd kattintson a **Szerkesztés** elemre.

3. Az **Összes kérelem** részen kattintson a **Munkarendelés** elemre.

4. Töltse ki a **Munkarendelés** legördülő listát. Ha karbantartási feladat típust választott a karbantartási kérésben, akkor szükség esetén másik karbantartási feladattípust választhat ki, amikor létrehozza a munkarendelést.

5. Kattintson az **OK** gombra. Egy üzenet jelenik meg, amely tájékoztatja a munkarendelés létrehozásáról.

6. Ha meg szeretné tekinteni, hogy melyik munkarendelések kapcsolódnak karbantartási kéréshez, válassza ki a karbantartási kérést az **Összes karbantartási kérés** vagy az **Aktív karbantartási kérések** listában, és kattintson a **Munkarendelések** gombra.


![3. ábra](media/05-work-orders.png)


>[!NOTE]
>A munkarendeléseket automatikusan is létrehozhatja, ha ütemezi a karbantartási terv feladatait, vagy beállítja az „Automatikus létrehozás” karbantartási terveket vagy karbantartási köröket az eszközhöz. A karbantartási kérésekből a **Karbantartási ütemezés** részen munkarendeléseket a karbantartási kérésekben kiválasztott karbantartási feladattípusokkal hozza létre a program.

