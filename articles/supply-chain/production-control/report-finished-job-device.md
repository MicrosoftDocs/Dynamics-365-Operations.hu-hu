---
title: Jelentés befejezettként a feladatkártya eszközből
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a rendszert úgy, hogy a Feladatkártya-eszköz felhasználói a termelési rendelésből a készletbe bejelenthetik a kész termékeket.
author: johanhoffmann
manager: tfehr
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f5d34893ddc8adc3785ec50dbd72438cf8f68c5d
ms.sourcegitcommit: 52ba8d3e6af72df5dab6c04b9684a61454d353ad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/26/2020
ms.locfileid: "3403262"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Jelentés befejezettként a feladatkártya eszközből

[!include [banner](../includes/banner.md)]

A dolgozók a munkakártya eszköz **jelentés-végrehajtási** lapját használják a termelési feladatokra kitöltött mennyiségek jelentése céljából.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Annak megadása, hogy a készként jelentett mennyiségeket adja-e a program a készlethez

A következő lépésekkel szabályozhatja, hogy az utolsó műveletben befejezettként jelentett mennyiségeket adja-e a rendszer a készlethez.

1. Kattintson a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> Termelési rendelés alapértékei** pontra.
1. A **Jelentés készként** lapon adja meg a **Készként jelentés online frissítése** mezőt a következő értékek valamelyikeként:

    - **Nem** – a rendszer nem adja hozzá a mennyiséget a készlethez, ha a legutóbbi műveletben mennyiséget jelentenek. A termelés állapota soha nem változik.
    - **Állapot + mennyiség** – A termelési rendelés állapota *Készként jelentve lesz*, és a program készként jelenti a mennyiséget a készletbe.
    - **Mennyiség** – A termelési rendelés állapota készként lesz jelentve a készletbe, de termelési rendelés állapota soha nem változik.
    - **Állapot** – Csak a termelési rendelés állapota változik. A rendszer nem adja hozzá a mennyiségeket a készlethez, ha a legutóbbi műveletben mennyiséget jelentenek.

> [!NOTE]
> A mennyiségek nem követhetők a készletben, ha az ezeket készként jelentő műveletek nem az utolsó műveletként vannak meghatározva. Ezek a mennyiségek azonban felhasználhatók a haladás megjelenítésére. Olyan szabályok is szerepelhetnek, amelyek meghatározzák, hogy a dolgozók elindíthatják-e a következő műveletet, mielőtt a korábbi műveletre vonatkozóan meghatározott küszöbértéket elérnek. Ezeket a szabályokat a **Mennyiségi ellenőrzés** lapja határozza meg a **Termelési rendelés alapértelmezései** lapnak.

A **termelési rendelés alapadatai** munkalapjával kapcsolatos további tudnivalókat lásd: [Termelési paraméterek a gyártás végrehajtásánál](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Kötegelt vezérelt cikkek jelentése készként

A feladatkártya-eszköz három esetet támogat a kötegelt cikkek jelentéséhez. Ezek a helyzetek mind a speciális raktári folyamatokhoz engedélyezett cikkekre, mind a speciális raktári folyamatokhoz nem engedélyezett cikkekre vonatkoznak.

- **Kötegelt számok kézi hozzárendelése:** A dolgozók egyéni kötegszámot adnak meg. Ez a kötegszám olyan külső forrásból származhat, amelyet a rendszer nem ismer.
- **Előre definiált kötegszám:** A dolgozók egy kötegszámnak a kiválasztását végzik el egy listáról, amelyet a rendszer automatikusan generált, a termelési rendelésnek a feladatkártya-eszközbe történő kiadása előtt.
- **Rögzített kötegszámok:** A dolgozók kötegszámot nem adnak meg. Helyette a rendszer automatikusan hozzárendel egy kötegszámot a termelési rendeléshez a kiadás előtt.

Kövesse az alábbi lépéseket az egyes forgatókönyvek engedélyezéséhez:

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki az konfigurálni kívánt terméket.
1. A **Készlet kezelése** gyorslap **Kötegszámcsoport** mezőjében válassza ki azt a nyomon követési számot, amely a forgatókönyv támogatásához van beállítva.

> [!NOTE]
> Alapértelmezés szerint, ha egy köteg által vezérelt termékhez nem rendel hozzá kötegszám-csoportot, a Feladatkártya-eszköz a készként való jelentés során manuális bejegyzést ad a kötegszám számára.

A következő alszakaszok azt írják le, hogyan lehet beállítani a követésiszám-csoportokat, hogy a fenti három forgatókönyvet támogassák a kötegelt cikkek jelentéséhez.

### <a name="enable-batch-number-reporting-on-the-job-card-device"></a>Kötegszám-jelentés engedélyezése a feladatkártya-eszközön

Ha engedélyezni szeretné, hogy a feladatkártya-eszközök elfogadhassanak egy kötegszámot a készként való jelentés során, akkor a [szolgáltatások kezelésével](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) be kell kapcsolni a következő szolgáltatásokat (ebben a sorrendben):

1. Javított felhasználói élmény a feladatkártya eszközében lévő jelentés az előrehaladásról párbeszédpanelhez
1. Engedélyezze, hogy a köteg-és sorozatszámokat megadhassa befejezettként a Feladatkártya eszközéből (előzetes)

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Olyan követésiszám-csoport megadása, amellyel a dolgozók manuálisan rendelhetik hozzá a köteg számát

A kötegszámok manuális kiosztásának engedélyezéséhez, kövesse az alábbi lépéseket egy követési számcsoportot beállításához:

1. Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Manuális** beállítást **Igen** értékre.

    ![Követésiszám-csoportok lap](media/tracking-number-group-manual.png "Követésiszám-csoportok lap")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy szövegmezőt jelenít meg, ahol a dolgozók bármilyen értéket meghatározhatnak.

![Előrehaladás jelentése lap a manuális kötegszám mezővel](media/job-card-device-batch-manual.png "Előrehaladás jelentése lap a manuális kötegszám mezővel")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Egy követésiszám-csoport beállítása, amely előre definiált kötegszámok listáját tartalmazza

Előre meghatározott kötegszámok listájának megadásához, kövesse az alábbi lépéseket egy követésiszám-csoport beállításához:

1. Ugrás: **Készletkezelés \> Beállítás > Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Igen** értékre.
1. A **Mennyiségenként** mező használatával a kötegek számát a megadott érték alapján osztja fel. Például van egy termelési rendelés tíz darabra, és a **Mennyiségenként** mező értéke *2*. Ebben az esetben a létrehozáskor öt kötegszám lesz hozzárendelve a termelési rendeléshez.

    ![Követésiszám-csoportok lap](media/tracking-number-group-predefined.png "Követésiszám-csoportok lap")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy legördülő menüt jelenít meg, ahol a dolgozóknak egy előre megadott értéket kell megadniuk.

![Előrehaladás jelentése lap előre megadott kötegszámok listájával](media/job-card-device-batch-predefined.png "Előrehaladás jelentése lap előre megadott kötegszámok listájával")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Olyan követésiszám-csoport megadása, amely automatikusan osztja a kötegszámokat

Ha a kötegek számát automatikusan kell hozzárendelni, a dolgozói beavatkozás nélkül, a következő lépésekkel lehet beállítani a követésiszám-csoportot.

1. Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Nem** értékre.
1. Állítsuk a **Manuális** beállítást **Nem** értékre.

    ![Követésiszám-csoportok lap](media/tracking-number-group-fixed.png "Követésiszám-csoportok lap")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy értéket jelenít meg, amelyet a dolgozók nem módosíthatnak.

![Előrehaladás jelentése lap a rögzített kötegszámmal](media/job-card-device-batch-fixed.png "Előrehaladás jelentése lap a rögzített kötegszámmal")

## <a name="report-as-finished-to-a-license-plate"></a>Jelentés készként egy azonosítótáblára

A speciális raktári folyamatok az azonosítótábla-dimenzió segítségével nyomon követhetik az erre a célra beállított raktári helyeket. Ebben az esetben az azonosítótábla számának megadása szükséges, ha a dolgozó készként jelenti a mennyiségeket.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Azonosítótábla jelentésének és címke nyomtatásának engedélyezése

Az ebben a szakaszban ismertetett szolgáltatások használatához a [szolgáltatások kezelésénél](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) be kell kapcsolni a következő szolgáltatásokat (ebben a sorrendben):

1. A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla
1. Az azonosítótábla-szám automatikus létrehozásának engedélyezése, amikor a feladatkártya eszközében befejezettként jelentik
1. Címke nyomtatása a Feladatkártya eszközéből

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Jelentés készként egy azonosítótáblára beállítása

A következő lépésekkel szabályozhatja, hogy a dolgozók egy meglévő azonosítótábla újra felhasználható-e, vagy új rendszámtábla előállítása történjen, a mennyiségek készként jelentésekor.

1. Ugrás a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> Feladatkártya eszközének konfigurálása** részre.
2. Állítsa be a következő lehetőségeket minden egyes eszköznél:

    - **Azonosítótábla előállítása** – Ezt a lehetőséget **Igen** értékre állítsa új azonosítótábla előállításához minden készként történő jelentésenél. A beállítása **Nem** legyen, ha minden készként jelentéshez egy meglévő rendszámtábla használandó.
    - **Címke nyomtatása** – Ez a lehetőséget akkor legyen **Igen**, ha a dolgozó minden készként jelentéshez azonosítótábla-címkét nyomtat. Állítsa **Nem** értékre, ha nem szükséges címke. 

![Feladatkártya konfigurálása az eszközökhöz oldal](media/config-job-card-raf.png "Feladatkártya konfigurálása az eszközökhöz oldal")

> [!NOTE]
> A címke konfigurálásához ugrás ide: **Raktárkezelés \> Beállítás \> Dokumentumirányítás \> Dokumentumirányítás**. A további tudnivalókat lásd az [Azonosítótábla címke nyomtatásának engedélyezése](../warehousing/tasks/license-plate-label-printing.md) című témakörben.
