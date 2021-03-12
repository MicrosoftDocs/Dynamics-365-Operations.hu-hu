---
title: Hullámsablon csoportosítása
description: A hullámsablon csoportosítása lehetővé teszi a rendszer számára, hogy hullámsablon-beállítások használatával határozza meg, az Ön által megadott feltételek alapján, hogy hogyan kell megosztani a kiadott sorokat, és hozzárendelni azokat az új vagy meglévő hullámokhoz. Ez a funkció jól használható olyan raktárakban, ahol a hullámok meghatározott feltételek alapján jönnek létre, de a vezetők a kézi helyett az automatikus hullámlétrehozást részesítik előnyben.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b422eb432e579d4ae914fbc0efa79aaa15f1de27
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998378"
---
# <a name="wave-template-grouping"></a>Hullámsablon csoportosítása

[!include [banner](../includes/banner.md)]

A hullámsablon csoportosítása lehetővé teszi a rendszer számára, hogy [hullámsablon](tasks/configure-wave-processing.md)-beállítások használatával határozza meg, az Ön által megadott feltételek alapján, hogy hogyan kell megosztani a kiadott sorokat, és hozzárendelni azokat az új vagy meglévő hullámokhoz. Ez a funkció jól használható olyan raktárakban, ahol a hullámok meghatározott feltételek alapján jönnek létre, de a vezetők a kézi helyett az automatikus hullámlétrehozást részesítik előnyben. Ez lehetővé teszi a rendszer számára, hogy minden újonnan kiadott szállítmányt hozzáadjon az első hullámhoz, amelyeknél megállapítja, hogy megfelelő csoportosítási mezőértékeket tartalmaz. Ha nem talál egyezést, akkor a rendszer új hullámot hoz létre az új szállítmányhoz.

> [!IMPORTANT]
> A hullámsablon csoportosítása nem támogatott a *termelési nyersanyag-kitárolás* vagy *Kanban-kitárolás* típusok esetében. Ennek az az oka, hogy a hullámcsoportosítás a szállítmányokon alapul, és ezek a munkatípusok nem használnak szállítmányokat.

## <a name="turn-on-the-wave-template-grouping-feature"></a>A Hullámsablon-csoportosítás funkció bekapcsolása

A *Hullámsablon-csoportosítás* funkciót használata előtt be kell kapcsolni a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Hullámsablon-csoportosítás*

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a>Hullámsablon beállítása a hullámsablon-csoportosítás használatára

A hullámsablon-csoportosítás elérhetővé tételéhez hajtsa végre az alábbi lépéseket a [hullámsablon](tasks/configure-wave-processing.md) beállításához.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A bal oldali ablaktáblában válassza ki a beállítani kívánt hullámsablont. Ha a bemutató adatainak felhasználásával készül a témakörben később a forgatókönyvvel dolgozni, válassza ki a **62 Szállítási alapértelmezett** sablont.
1. Válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Hullámlétrehozás automatizálása:** *Igen*
    - **Hozzárendelés nyitott hullámokhoz:** *Igen*
    - **Hullám feldolgozása a raktárba történő kiadáskor:** *Nem*

1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget a lekérdezés párbeszédpanel megnyitásához.
1. A lekérdezés párbeszédpanel **Rendezés** lapján tekintse át a rendezési feltételeket, és győződjön meg arról, hogy van olyan szabály, amely tartalmazza a hullámok csoportosítására használni kívánt mezőt.

    Ha a bemutató adatainak felhasználásával készül a forgatókönyv alapján dolgozni, vegyen fel egy sort, amely a következő értékeket tartalmazza:

    - **Tábla:** *Szállítmányok*
    - **Származtatott tábla:** *Szállítmányok*
    - **Mező:** *Szállítmányozói szolgáltatás*

        > [!NOTE]
        > Miután kiválasztotta ezt az értéket, a következő üzenet jelenhet meg: „A Szállítmányozói szolgáltatás nem egy indexmező. Szeretne rendezést hozzáadni?” Válassza az **Igen** lehetőséget a rendezés hozzáadásához.

    - **Keresés iránya:** *Növekvő*

1. Az **OK** gombra kattintva mentse a változtatásokat, és zárja be a lekérdezés párbeszédpanelt.
1. A műveleti ablaktáblán válassza ki a **Hullámsablon-csoportosítás** lehetőséget.
1. A **Hullámsablon-csoportosítás** oldalon jelölje be a **Csoportosítás** jelölőnégyzetet minden olyan sor esetében, amelyet alkalmazni szeretne a rendeléssorok hullámokba történő csoportosításához. Ha a bemutató adatainak felhasználásával készül a forgatókönyvön keresztül dolgozni, akkor jelölje be a **Csoportosítás alapja** jelölőnégyzetet a *Szállítmányozói szolgáltatás* sorában.
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a **Hullámsablon-csoportosítás** lapot.
1. A sablon mentéséhez válassza a **Mentés** elemet.

## <a name="scenario"></a>Forgatókönyv

Ez a szakasz egy olyan szkriptet mutat be, amellyel megtudhatja, hogy a funkció milyen módon működik, és hogyan kell használni.

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

A forgatókönyvet a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja. Ebben az esetben azonban a saját értékeit kell helyettesítenie, és előfordulhat, hogy bizonyos típusú kötelező rekordok hiányoznak, amelyeket a szabvány demóadatok biztosítanak.

### <a name="scenario-wave-template-grouping"></a>Forgatókönyv: Hullámsablon-csoportosítás

Ez a példa azt mutatja be, hogyan kell használni a hullámsablon-csoportosítást több hullámnak a hullámsablonban definiált feltételek alapján történő automatikus létrehozásához. Ebben a forgatókönyvben a hullámsablon úgy van beállítva a rendszerben, hogy szállítmányozói szolgáltatásonként egy hullámot hozzon létre.

A kezdés előtt készítse elő a hullámsablont a témakör korábbi [Hullámsablon beállítása a hullámsablon-csoportosítás használatára](#set-up-template) szakaszában leírtak alapján. Ha ebben a helyzetben a bemutatóadatokkal dolgozik, ügyeljen arra, hogy az adott eljárásban javasolt bemutatóadat-értékeket használja. Ez a beállítás az egyes értékesítési rendelésekhez megadott szállítmányozói szolgáltatás alapján csoportosítja a hullámokat.

#### <a name="create-sales-order-1"></a>1. értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-004* számára.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *62* értéket.

1. Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához.
1. Az új értékesítési rendelést a **Sorok** nézetben nyitja meg a program. Jegyezze fel az értékesítési rendelés számát.
1. Váltson a **Fejléc** nézetre.
1. A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:

    - **Szállítmányozó:** *Légitársaság*
    - **Szállítmányozói szolgáltatás:** *Légi*

1. Váltson vissza a **Sorok** nézetre.
1. Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Sor hozzáadása** elemet egy sor rácshoz való hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *2*

1. Válassza ki az új rendelési sort, majd a **Készlet** menüben, a rács felett válassza a **Foglalás** pontot.
1. A **Foglalás** oldalon, a Művelet panelen válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg. Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait.

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a>Az 1. értékesítési rendelésből létrehozott hullám megtekintése

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki az értékesítési rendelésből létrehozott hullám azonosítóját.
1. A hullám részletei lap megnyitásához válassza a hullámazonosító hivatkozást.
1. Figyelje meg, hogy a szállítmány hozzá lett adva a **Hullámsorok** gyorslaphoz.

#### <a name="create-sales-order-2"></a>2. értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-005* számára.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *62* értéket.

1. Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához.
1. Az új értékesítési rendelést a **Sorok** nézetben nyitja meg a program. Jegyezze fel az értékesítési rendelés számát.
1. Váltson a **Fejléc** nézetre.
1. A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:

    - **Szállítmányozó:** *Virágszállító*
    - **Szállítmányozói szolgáltatás:** *Std*

1. Váltson vissza a **Sorok** nézetre.
1. Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Sor hozzáadása** elemet egy sor rácshoz való hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *1*

1. Válassza ki az új rendelési sort, majd a **Készlet** menüben, a rács felett válassza a **Foglalás** pontot.
1. A **Foglalás** oldalon, a Művelet panelen válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg. Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait. Figyelje meg, hogy a hullámazonosító eltér az első értékesítési rendelés hullámazonosítójától.

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a>A 2. értékesítési rendelésből létrehozott hullám megtekintése

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki a második értékesítési rendelésből létrehozott hullám azonosítóját.
1. A hullám részletei lap megnyitásához válassza a hullámazonosító hivatkozást.
1. Figyelje meg, hogy a szállítmány hozzá lett adva a **Hullámsorok** gyorslaphoz.

Új hullám jött létre ehhez a szállítmányhoz, mert az első értékesítési rendeléstől eltérő szállítmányozói szolgáltatásokat alkalmaz.

#### <a name="create-sales-order-3"></a>3. értékesítési rendelés létrehozása

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-006* számára.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *62* értéket.

1. Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához.
1. Az új értékesítési rendelést a **Sorok** nézetben nyitja meg a program. Jegyezze fel az értékesítési rendelés számát.
1. Váltson a **Fejléc** nézetre.
1. A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:

    - **Szállítmányozó:** *Légitársaság*
    - **Szállítmányozói szolgáltatás:** *Légi*

1. Váltson vissza a **Sorok** nézetre.
1. Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Sor hozzáadása** elemet egy sor rácshoz való hozzáadásához.
1. Az új sorban állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *1*

1. Válassza ki az új rendelési sort, majd a **Készlet** menüben, a rács felett válassza a **Foglalás** pontot.
1. A **Foglalás** oldalon, a Művelet panelen válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.
1. Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.
1. Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg. Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait. A szállítmány már hozzá van rendelve a meglévő hullámhoz az első értékesítési rendelésből.

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a>Az 1. és 3. értékesítési rendelések hullámának megtekintése

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki a harmadik értékesítési rendelésből létrehozott hullám azonosítóját.
1. A hullám részletei lap megnyitásához válassza a hullámazonosító hivatkozást.
1. Figyelje meg, hogy a szállítmány hozzá van-e rendelve a **Hullámsorok** gyorslaphoz az első értékesítési rendeléshez tartozó szállítmánnyal együtt.
