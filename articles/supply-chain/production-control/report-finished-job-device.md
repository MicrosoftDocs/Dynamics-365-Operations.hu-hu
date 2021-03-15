---
title: Jelentés befejezettként a feladatkártya eszközből
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a rendszert úgy, hogy a Feladatkártya-eszköz felhasználói a termelési rendelésből a készletbe bejelenthetik a kész termékeket.
author: johanhoffmann
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 2e9258d0a2f2006f404b24f15605af5a2ad1b281
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986504"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Jelentés befejezettként a feladatkártya eszközből

[!include [banner](../includes/banner.md)]

A dolgozók a munkakártya eszköz **jelentés-végrehajtási** lapját használják a termelési feladatokra kitöltött mennyiségek jelentése céljából. Ez a témakör azt mutatja be, hogyan lehet beállítani a különböző lehetőségeket, amelyek meghatározzák, hogy a dolgozók hogyan jelenthetik készként a munkát ezen az oldalon, és mi történik a következőn. A lehetőségek a következők:

- Annak megadása, hogy a készként jelentett mennyiségeket hozzáadja-e a program a készlethez, és ha igen, akkor hogyan.
- Annak megadása, hogy a készként jelentett kötegszámokat létrehozza és alkalmazza-e, és ha igen, akkor hogyan.
- Annak megadása, hogy a készként jelentett sorozatszámokat létrehozza és alkalmazza-e, és ha igen, akkor hogyan.
- Annak megadása, hogy készként jelentse-e az azonosítótáblához, és ha igen, akkor hogyan.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Annak megadása, hogy a készként jelentett mennyiségeket adja-e a program a készlethez

A következő lépésekkel szabályozhatja, hogy az utolsó műveletben befejezettként jelentett mennyiségeket adja-e a rendszer a készlethez.

1. Kattintson a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> Termelési rendelés alapértékei** pontra.
1. A **Jelentés készként** lapon adja meg a **Készként jelentés online frissítése** mezőt a következő értékek valamelyikeként:

    - **Nem** – a rendszer nem adja hozzá a mennyiséget a készlethez, ha a legutóbbi műveletben mennyiséget jelentenek. A termelés állapota soha nem változik.
    - **Állapot + mennyiség** – A termelési rendelés állapota *Készként jelentve lesz*, és a program készként jelenti a mennyiséget a készletbe.
    - **Mennyiség** – A termelési rendelés állapota készként lesz jelentve a készletbe, de termelési rendelés állapota soha nem változik.
    - **Állapot** – Csak a termelési rendelés állapota változik. A rendszer nem adja hozzá a mennyiségeket a készlethez, ha a legutóbbi műveletben mennyiséget jelentenek.

> [!NOTE]
> A mennyiségek nem követhetők a készletben, ha az ezeket készként jelentő műveletek nem az utolsó műveletként vannak meghatározva. Ezek a mennyiségek azonban felhasználhatók a haladás megjelenítésére. Olyan szabályok is szerepelhetnek, amelyek meghatározzák, hogy a dolgozók elindíthatják-e a következő műveletet, mielőtt a korábbi műveletre vonatkozóan meghatározott küszöbértéket elérnek. Ezeket a szabályokat a **Mennyiségi ellenőrzés** lapja határozza meg a **Termelési rendelés alapértelmezései** lapon.

A **termelési rendelés alapadatai** munkalapjával kapcsolatos további tudnivalókat lásd: [Termelési paraméterek a gyártás végrehajtásánál](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Kötegelt vezérelt cikkek jelentése készként

A feladatkártya-eszköz három esetet támogat a kötegelt cikkek jelentéséhez. Ezek a helyzetek mind a speciális raktári folyamatokhoz engedélyezett cikkekre, mind a speciális raktári folyamatokhoz nem engedélyezett cikkekre vonatkoznak.

- **Kötegelt számok kézi hozzárendelése** – A dolgozók egyéni kötegszámot adnak meg. Ez a kötegszám olyan külső forrásból származhat, amelyet a rendszer nem ismer.
- **Előre definiált kötegszám** – A dolgozók egy kötegszámnak a kiválasztását végzik el egy listáról, amelyet a rendszer automatikusan generált, a termelési rendelésnek a feladatkártya-eszközbe történő kiadása előtt.
- **Rögzített kötegszámok** – A dolgozók kötegszámot nem adnak meg. Helyette a rendszer automatikusan hozzárendel egy kötegszámot a termelési rendeléshez a kiadás előtt.


### <a name="enable-the-feature-on-your-system"></a>A funkció engedélyezése a rendszerben

Ha engedélyezni szeretné, hogy a feladatkártya-eszközök elfogadhassanak egy kötegszámot a készként való jelentés során, akkor a [szolgáltatások kezelésével](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) be kell kapcsolni a következő szolgáltatásokat (ebben a sorrendben):

1. Javított felhasználói élmény a feladatkártya eszközében lévő jelentés az előrehaladásról párbeszédpanelhez
1. Engedélyezze, hogy a köteg-és sorozatszámokat megadhassa befejezettként a Feladatkártya eszközéből (előzetes)

### <a name="configure-products-that-require-batch-number-reporting"></a>A kötegszám-jelentést igénylő termékek konfigurálása

A következő lépésekkel engedélyezheti, hogy a termék támogassa az elérhető kötegvezérelt forgatókönyveket:

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki az konfigurálni kívánt terméket.
1. A **Készlet kezelése** gyorslap **Kötegszámcsoport** mezőjében válassza ki azt a nyomon követési számot, amely a forgatókönyv támogatásához van beállítva.

> [!NOTE]
> Alapértelmezés szerint, ha egy köteg által vezérelt termékhez nem rendel hozzá kötegszám-csoportot, a Feladatkártya-eszköz a készként való jelentés során manuális bejegyzést ad a kötegszám számára.

A következő szakaszok azt írják le, hogyan lehet beállítani a követésiszám-csoportokat, hogy a fenti három forgatókönyvet támogassák a kötegelt cikkek jelentéséhez.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Olyan követésiszám-csoport megadása, amellyel a dolgozók manuálisan rendelhetik hozzá a köteg számát

A kötegszámok manuális kiosztásának engedélyezéséhez, kövesse az alábbi lépéseket egy követési számcsoportot beállításához:

1. Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Manuális** beállítást **Igen** értékre.

    ![A kézi kötegszámok követési számcsoportja](media/tracking-number-group-manual.png "A kézi kötegszámok követési számcsoportja")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy szövegmezőt jelenít meg, ahol a dolgozók bármilyen értéket meghatározhatnak.

![Előrehaladás jelentése lap a manuális kötegszám mezővel](media/job-card-device-batch-manual.png "Előrehaladás jelentése lap a manuális kötegszám mezővel")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Egy követésiszám-csoport beállítása, amely előre definiált kötegszámok listáját tartalmazza

Előre meghatározott kötegszámok listájának megadásához, kövesse az alábbi lépéseket egy követésiszám-csoport beállításához:

1. Ugrás: **Készletkezelés \> Beállítás > Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Igen** értékre.
1. A **Mennyiségenként** mező használatával a kötegek számát a megadott érték alapján osztja fel. Például van egy termelési rendelés tíz darabra, és a **Mennyiségenként** mező értéke *2*. Ebben az esetben a létrehozáskor öt kötegszám lesz hozzárendelve a termelési rendeléshez.

    ![Az előre meghatározott kötegszámok követési számcsoportja](media/tracking-number-group-predefined.png "Az előre meghatározott kötegszámok követési számcsoportja")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy legördülő menüt jelenít meg, ahol a dolgozóknak egy előre megadott értéket kell megadniuk.

![Előrehaladás jelentése lap előre megadott kötegszámok listájával](media/job-card-device-batch-predefined.png "Előrehaladás jelentése lap előre megadott kötegszámok listájával")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Olyan követésiszám-csoport megadása, amely automatikusan osztja a kötegszámokat

Ha a kötegek számát automatikusan kell hozzárendelni, a dolgozói beavatkozás nélkül, a következő lépésekkel lehet beállítani a követésiszám-csoportot.

1. Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Nem** értékre.
1. Állítsuk a **Manuális** beállítást **Nem** értékre.

    ![A rögzített kötegszámok követési számcsoportja](media/tracking-number-group-fixed.png "A rögzített kötegszámok követési számcsoportja")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek kötegszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Kötegszám** mezője az **Előrehaladás jelentése** lapon egy értéket jelenít meg, amelyet a dolgozók nem módosíthatnak.

![Előrehaladás jelentése lap a rögzített kötegszámmal](media/job-card-device-batch-fixed.png "Előrehaladás jelentése lap a rögzített kötegszámmal")

## <a name="report-serial-controlled-items-as-finished"></a>Sorozatvezérelt cikkek jelentése készként

A feladatkártya-eszköz három esetet támogat a sorozatvezérelt cikkek jelentéséhez. Ezek a helyzetek mind a speciális raktári folyamatokhoz engedélyezett cikkekre, mind a speciális raktári folyamatokhoz nem engedélyezett cikkekre vonatkoznak.

- **Sorozatszámok kézi hozzárendelése** – A dolgozók egyéni sorozatszámot adnak meg. Ez a sorozatszám olyan külső forrásból származhat, amelyet a rendszer nem ismer.
- **Előre meghatározott sorozatszám** – A dolgozók egy sorozatszámnak a kiválasztását végzik el egy listáról, amelyet a rendszer automatikusan generált, a termelési rendelésnek a feladatkártya-eszközbe történő kiadása előtt.
- **Rögzített sorozatszám** – A dolgozók sorozatszámot nem adnak meg. Helyette a rendszer automatikusan hozzárendel egy sorozatszámot a termelési rendeléshez a kiadás előtt.

### <a name="enable-the-feature-on-your-system"></a>A funkció engedélyezése a rendszerben

Ha engedélyezni szeretné, hogy a feladatkártya-eszközök elfogadhassanak egy sorozatszámot a készként való jelentés során, akkor a [szolgáltatások kezelésével](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) be kell kapcsolni a következő szolgáltatásokat (ebben a sorrendben):

1. Javított felhasználói élmény a feladatkártya eszközében lévő jelentés az előrehaladásról párbeszédpanelhez
1. Engedélyezze, hogy a köteg-és sorozatszámokat megadhassa befejezettként a Feladatkártya eszközéből (előzetes)

### <a name="configure-products-that-require-serial-number-reporting"></a>A sorozatszám-jelentést igénylő termékek konfigurálása

A következő lépésekkel engedélyezheti, hogy a termék támogassa az elérhető sorozatvezérelt forgatókönyveket:

Kövesse az alábbi lépéseket az egyes forgatókönyvek engedélyezéséhez:

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki az konfigurálni kívánt terméket.
1. A **Készlet kezelése** gyorslap **Sorozatszám-csoport** mezőjében válassza ki azt a nyomon követési számot, amely a forgatókönyv támogatásához van beállítva.

> [!NOTE]
> Alapértelmezés szerint, ha egy sorozatvezérelt termékhez nem rendel hozzá sorozatszám-csoportot, a feladatkártya-eszköz a készként jelentés során manuális bejegyzést ad a sorozatszám számára.

A következő szakaszok azt írják le, hogyan lehet beállítani a követési számcsoportokat, hogy a fenti három forgatókönyvet támogassák a sorozatvezérelt cikkek jelentéséhez.

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-serial-number"></a>Olyan követésiszám-csoport megadása, amellyel a dolgozók manuálisan rendelhetik hozzá a sorozatszámot

A sorozatszámok manuális kiosztásának engedélyezéséhez, kövesse az alábbi lépéseket egy követési számcsoportot beállításához:

1. Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Manuális** beállítást **Igen** értékre.

    ![Követési számcsoportok lap, sorozatszámok](media/tracking-number-group-manual-serial.png "Követési számcsoportok lap, sorozatszámok")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek sorozatszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Sorozatszám** mezője az **Előrehaladás jelentése** lapon egy szövegmezőt jelenít meg, ahol a dolgozók bármilyen értéket meghatározhatnak a sorozatszámnak. Érték megadásakor az érték a sorozatszám-listára kerül. Ebben a listában a dolgozók a következőket tehetik:

- Ha a sorozatszámot selejtként szeretné megjelölni, válassza ki a **Selejt** gombot a megfelelő sorhoz. A program megkéri a dolgozót, hogy töltse ki a **Hiba oka** részt.
- Ha a sorozatszámot ki szeretné törölni, válassza a **Törlés** gombot a megfelelő sorhoz.

![Előrehaladás jelentése lap a manuális sorozatszámok mezővel](media/job-card-device-serial-manual.png "Előrehaladás jelentése lap a manuális sorozatszámok mezővel")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-serial-numbers"></a>Egy követésiszám-csoport beállítása, amely előre definiált sorozatszámok listáját tartalmazza

Előre meghatározott sorozatszámok listájának megadásához, kövesse az alábbi lépéseket egy követésiszám-csoport beállításához:

1. Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Igen** értékre.
1. A **Mennyiségenként** mező használatával a sorozatszámokat egyesével feloszthatja.

    ![Az előre meghatározott sorozatszámok követési számcsoportja](media/tracking-number-group-predefined-sn.png "Az előre meghatározott sorozatszámok követési számcsoportja")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek sorozatszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Sorozatszámok** mezője az **Előrehaladás jelentése** lapon egy legördülő menüt jelenít meg, ahol a dolgozóknak egy előre megadott értéket kell megadniuk.

![Előrehaladás jelentése lap előre megadott sorozatszámok listájával](media/job-card-device-serial-predefined.png "Előrehaladás jelentése lap előre megadott sorozatszámok listájával")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-serial-numbers"></a>Olyan követésiszám-csoport megadása, amely automatikusan osztja a sorozatszámokat

Ha a sorozatszámot automatikusan kell hozzárendelni dolgozói beavatkozás nélkül, a következő lépésekkel lehet beállítani a követésiszám-csoportot.

1. Ugrás: **Készletkezelés \> Beállítás \> Dimenziók \> Követésiszám-csoportok**.
1. Hozza létre vagy válassza ki a beállítani kívánt követésiszám-csoportot.
1. Az **Általános** gyorslapon állítsa a **Csak készlettranzakciókra** beállítást **Nem** értékre.
1. Állítsuk a **Manuális** beállítást **Nem** értékre.

    ![A rögzített sorozatszámok követési számcsoportja](media/tracking-number-group-fixed-sn.png "A rögzített sorozatszámok követési számcsoportja")

1. A szükséges módon adja meg a többi értéket, majd válassza ki ezt a követésiszám-csoportot azon felszabadított termékek sorozatszám-csoportjaként, amelyekre ezt a forgatókönyvet használni szeretné.

Ha ezt a forgatókönyvet választja, akkor a feladatkártya-eszköz **Sorozatszám** mezője az **Előrehaladás jelentése** lapon egy értéket jelenít meg, amelyet a dolgozók nem módosíthatnak. Ez a forgatókönyv csak akkor érvényes, ha egy termelési rendelést egy több sorozatszámmal vezérelt cikkhez hoznak létre.

![Előrehaladás jelentése lap a rögzített sorozatszámmal](media/job-card-device-serial-fixed.png "Előrehaladás jelentése lap a rögzített sorozatszámokkal")

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]