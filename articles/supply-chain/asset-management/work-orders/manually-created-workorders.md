---
title: Manuálisan létrehozott munkarendelések
description: Ez a cikk bemutatja, hogyan lehet manuálisan létrehozni munkarendeléseket az Eszközkezelésben.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5d2cc1f5b8eccb51b6bea8655fdee243c1a2df55
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015027"
---
# <a name="manually-created-work-orders"></a>Manuálisan létrehozott munkarendelések

[!include [banner](../../includes/banner.md)]


A munkarendelések manuális létrehozására két mód van:

- Az **Összes munkarendelés** vagy az **Aktív munkarendelések** oldalon 
- Az **Összes karbantartási kérés**, az **Aktív karbantartási kérések** vagy a **Saját munkavégzési helyszínhez tartozó karbantartási kérések** oldalon 

## <a name="create-work-order"></a>Munkarendelés létrehozása

1. Tárgyieszköz-kezelés munkarendelések **selece** > **·** > **: minden munkarendelés vagy** aktív **munkarendelés**.

2. Válassza az **Új** lehetőséget.

3. A **Munkarendelés létrehozása** párbeszédpanelen válassza ki a Munkarendelés típusát a **Munkarendelés típusa** mezőben.

4. Ha szükséges, válasszon ki egy **Leírást**.

5. Az **Eszköz** mezőben válassza ki az eszközt.

>[!NOTE]
>Amikor kiválaszt egy eszközt, három lap érhető el az **Eszköz** legördülő listájában: 

- **Aktív eszközök** - Ez a lap az összes olyan eszköz listáját tartalmazza, amelyek „Aktív” eszközéletciklus-állapottal rendelkeznek. 
- **Eszköznézet** – Ez a lap a munkavégzési helyszínek és az azokra telepített eszközök fanézetét jeleníti meg.
- **Saját eszközök** – Ez a lap olyan eszközöket tartalmaz, amelyek az Önhöz (a rendszerbe bejelentkezett dolgozó) esetlegesen hozzárendelt munkavégzési helyszínekhez vannak hozzárendelve. (A beállítással kapcsolatos további információkért lásd: [Karbantartó dolgozók és dolgozóicsoportok](../setup-for-objects/workers-and-worker-groups.md).) Ha egy dolgozónál nem állítottak be munkavégzési helyszíneket a [Karbantartási dolgozók és a dolgozócsoportok](../setup-for-objects/workers-and-worker-groups.md) számára, akkor a **Saját eszközök** lap nem érhető el. 

6. A **Karbantartási feladat típusa** mezőben válassza ki a karbantartási feladat típusát a munkarendeléshez.

7. Ha szükséges, válassza ki a **karbantartási feladat típusának változatát** és az **ügyletet**.

8. Ha szükséges, módosíthatja a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.

9. Válassza ki a **Várt kezdési** és **Vártbefejezési dátumokat** a megfelelő mezőkben.

10. Az új munkarendelés létrehozásához kattintson az **OK** lehetőségre.

11. Az **Összess munkarendelés** listaoldalon a munkarendelést igény szerint szerkesztheti.

Vegye figyelembe az alábbiakat:

- Az **Összes munkarendelés** listaoldal részletek nézetén több eszközt is hozzáadhat egy munkarendeléshez, ha hozzáadja a sorokat a **Munkarendelés karbantartási feladatai** gyorslapon. Egy eszköznél csak az eszközhöz kiválasztott eszköztípuson megadott karbantartásifeladat-típusok közül lehet választani.  

- Ha a beállítás során módosítja az eszköz szolgáltatási szintjét vagy az eszköz kritikusságát, miután már használta az eszközt egy munkarendelésen, a munkarendelés szolgáltatási szintje vagy kritikussága nem frissül ennek megfelelően. A szolgáltatási szintekről és a kritikusságról az [Eszközök szolgáltatási szintje](../setup-for-objects/object-priorities.md) és az [Eszközök kritikusságtípusai](../setup-for-objects/object-criticalities.md) témakörök tartalmaznak további információkat.

- A program minden alkalommal újraszámolja a munkarendelési feladaton szereplő kritikusságot, amikor a munkarendeléshez hozzáadnak vagy róla eltávolítanak egy munkarendelési feladatot.

- Az **Összes munkarendelés** részletek nézet > **Fejléc** lap > **Ütemezés** gyorslapon kiválaszthatja a felelős karbantartási dolgozói csoportot vagy a felelős karbantartási dolgozót a **Felelős csoport** vagy a **Felelős** mezőben. Ezek a beállítások módosíthatók, amíg a munkarendelés aktív. Módosíthatók például akkor, amikor a munkarendelés életciklus-állapota megváltozik. A munkarendelés létrehozása során végzett automatikus kiválasztás a **Felelős karbantartási dolgozók** oldal beállításain alapul. Ha egy munkarendelés létrehozása után hozzáadja vagy eltávolítja a munkarendelési feladatokat, és a **Felelős csoport** és a **Felelős** mező üresen marad, amikor frissíti a munkarendelést, az Eszközkezelő megpróbálja megtalálni a felelős karbantartási dolgozói csoportot vagy felelős karbantartási dolgozót a beállítási képernyőn. Ha a **Felelős csoport** mező vagy a **Felelős** mező ki már be van állítva a munkarendelés frissítésekor, akkor nem történik módosítás. A karbantartási dolgozók és karbantartási dolgozói csoportok beállítására vonatkozó további tudnivalókért tanulmányozza a [Felelős karbantartási dolgozók](../setup-for-maintenance-requests/responsible-workers.md) című témakört.

- A [Karbantartás állapota](../controlling-and-reporting/maintenance-status.md) oldalon számítást végezhet, hogy áttekintést kapjon a beérkező és a teljesített munkarendelésekre vonatkozó terhelésekről.  

- Az **Összes munkarendelés** lap részletek nézetében a **Sor részletei** gyorslapon a A **Szélesség** és a **Hosszúság** mezőket használhatja a kijelölt eszköz földrajzi koordinátáinak hozzáadására a munkarendelési feladathoz.  


## <a name="create-related-work-order"></a>Kapcsolódó munkarendelés létrehozása

Olyan munkarendelést hozhat létre, amely egy meglévő munkarendeléshez kapcsolódik. Ez a képesség például akkor lehet hasznos, ha elsődleges és másodlagos munkarendelésekkel szeretne dolgozni. Az új munkarendelés egy meglévő munkarendelésből származó munkarendelési feladaton alapul.

1. Válassza ki **az Eszközkezelés** > **munkarendelések minden** > **munkarendelését vagy** az aktív **munkarendeléseket**.

2. Válassza ki a munkarendelést, amelyhez kapcsolódó munkarendelést hoz létre.

3. A Művelet ablaktábla **Munkarendelés** lapjának **Új** csoportjában válassza a **Kapcsolódó munkarendelés** elemet.

4. A **Kapcsolódó munkarendelés létrehozása** legördülő párbeszédpanelen a **Munkarendelési feladat** mezőben válassza ki azt a munkarendelési feladatot, amelyhez kapcsolódó munkarendelést szeretne létrehozni.

5. A **Karbantartási feladat típusa** mezőben válassza ki a karbantartási feladat típusát.

6. A **Karbantartási feladattípus változója** és a **Szakma** mezőkben igény szerint válassza ki a karbantartási feladattípushoz tartozó változatot és szakmát.

7. Ha ez a munkarendelés a kiválasztott munkarendeléshez létrehozott első kapcsolódó munkarendelés, hajtsa végre az alábbi lépéseket:
    1. Válassza ki az **Új munkarendelési** lehetőséget.
    2. A **Munkarendelés típusa** mezőben válasszon ki egy munkarendelés-típust.
    3. Adjon meg egy leírást a **Leírás** alatt.
    4. Igény szerint módosítsa a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.
    5. A **Várható kezdés** és **Várható befejezés** mezőkben válassza ki a kezdés és a befejezés várható dátumait.
    6. Válassza ki az **OK** lehetőséget. Az új kapcsolódó munkarendelés az **Összes munkarendelés** listaoldalon jelenik meg.  

8. Ha a kapcsolódó munkarendelés, amelyhez létrehozza ezt a munkarendelést már rendelkezik kapcsolódó munkarendelésekkel, akkor az alábbi lépések végrehajtásával új munkarendelési feladatot adhat hozzá egy meglévő kapcsolódó munkarendeléshez:
    1. Válassza a **Hozzáadás a kapcsolódó munkarendeléshez** beállítást.
    2. A **Munkarendelés** mezőben válassza ki azt a kapcsolódó munkarendelést, amelyhez hozzá szeretné adni az új munkarendelési feladatot.
    3. Igény szerint módosítsa a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.
    4. A **Várható kezdés** és **Várható befejezés** mezőkben igény szerint módosítsa a kezdés és a befejezés várható dátumait.
    5. Válassza ki az **OK** lehetőséget. A munkarendelési feladatot a program hozzáadja a meglévő kapcsolódó munkarendeléshez.

Az alábbi ábra a **Munkarendelés létrehozása** párbeszédpanel egy példáját mutatja be.

![1. ábra](media/03-work-orders.png)

>[!NOTE]
>Ha egy összekapcsolt munkarendeléshez maszkot állított be az **Eszközkezelés paraméterei** > **Munkarendelések hivatkozás** lap > **Kapcsolódó munkarendelési maszk** mezőben, akkor a program a maszk beállításaival összhangban hozza létre a munkarendelés azonosítóit. Ha nincs beállítva maszk a kapcsolódó munkarendeléshez, akkor a program a következő elérhető munkarendelési azonosítót használja a kapcsolódó munkarendelésekhez.

## <a name="copy-a-work-order"></a>Egy munkarendelés másolása

Meglévő munkarendelésből gyorsan hozhat létre új munkarendelést. A munkarendelések ilyen használata különbözik a munkarendelések [karbantartási tervek](../preventive-and-reactive-maintenance/maintenance-plans.md) alapján történő létrehozásától. Ez például akkor lehet hasznos, ha a munkarendelés sok olyan munkarendelési feladatot tartalmaz, amelyek esetében adott időszakokban különböző eszközökön kell feladatokat elvégezni.

1. Válassza ki **az Eszközkezelés** > **munkarendelések minden** > **munkarendelését vagy** az aktív **munkarendeléseket**.

2. Válassza ki azt a munkarendelést, amelyből a tartalmat másolni szeretné.

3. A Művelet ablaktábla > **Munkarendelés** lapjának > **Új** csoportjában válassza a **Munkarendelés másolása** elemet.

4. Megjelenik a kiválasztott munkarendelés beállítása. Igény szerint módosíthatja a mezőket.

5. Az új munkarendelés létrehozásához válassza az **OK** elemet.

6. Az **Összess munkarendelés** listaoldalon a munkarendelést igény szerint szerkesztheti.

>[!NOTE]
>Az új munkarendelés létrehozásakor néhány információt közvetlenül a meglévő munkarendelésből másol a rendszer. A program nem másolja az előrejelzésekre, eszközökre, karbantartási ellenőrzőlistára, munkavégzési helyre, címekre és ütemezésre vonatkozó adatokat. Helyette a rendszer inicializálja ezeket az aktuális beállításból az Eszközkezelés modulból. Ezért ha az adatok megváltoztak az első munkarendelés létrehozása és a munkarendelés másolásának időpontja között, akkor a módosítások az új munkarendelésben szerepelnek. Ilyenek például az előrejelzések módosításai vagy a karbantartási ellenőrzőlisták frissítései.

Az alábbi ábra a **Munkarendelés másolása** párbeszédpanel egy példáját mutatja be.

![2. ábra](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a>Egy munkarendelés létrehozása karbantartási kérés alapján

1. Válassza ki az eszközkezelés **karbantartási kérését** > **, amely minden karbantartási kérést vagy** > **az aktív** karbantartási kérést kéri **.**

2. Válassza ki azt a karbantartási kérést, amelyhez munkarendelést szeretne létrehozni, majd kattintson a **Szerkesztés** elemre.

3. A Művelet ablaktábla > **Karbantartási kérés** lapjának > **Új** csoportjában válassza a **Munkarendelés** elemet.

4. A **Munkarendelés** párbeszédablakban állítsa be a mezőket. Ha karbantartási feladat típust választott a karbantartási kérésben, akkor igény szerint eltérő karbantartási feladattípust választhat ki, amikor létrehozza a munkarendelést.

5. Válassza ki az **OK** lehetőséget. Az üzenet tájékoztatja arról, hogy a munkarendelés létrehozása megtörtént.

6. A karbantartási kéréshez kapcsolódó munkarendelések megtekintéséhez az **Összes karbantartási kérés** vagy az **Aktív karbantartási kérések** listaoldalonválassza ki a karbantartási kérést. Majd a Művelet ablaktábla **Karbantartási kérés** lapjának **Nézet** csoportjában válassza a **Munkarendelés** elemet.


Az alábbi ábra a **Munkarendelés létrehozása** párbeszédpanel egy példáját mutatja be.

![3. ábra](media/05-work-orders.png)


>[!NOTE]
>Ha a munkarendeléseket automatikusan szeretné létrehozni, ütemezheti a karbantartási terv feladatait, vagy beállíthatja az „Automatikus létrehozású” [karbantartási terveket](../preventive-and-reactive-maintenance/maintenance-plans.md) vagy [karbantartási köröket](../preventive-and-reactive-maintenance/maintenance-rounds.md) az eszközhöz. A karbantartási kérések, amelyek az **Összes karbantartási ütemezés** listaoldalról vannak létrehozva a kiválasztott karbantartási feladattípusokkal hozza létre a program.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]