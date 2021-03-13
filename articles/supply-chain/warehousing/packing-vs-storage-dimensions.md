---
title: Különböző dimenziók beállítása csomagoláshoz és tároláshoz
description: Ez a témakör bemutatja, hogyan adhatja meg, hogy az egyes megadott dimenziókat mely folyamathoz (csomagolás, tárolás vagy beágyazott csomagolás) használják.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 004d9b4522335b481b640ef0fe35f4db66e3c9f5
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078270"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>Különböző dimenziók beállítása csomagoláshoz és tároláshoz

[!include [banner](../includes/banner.md)]

Egyes cikkek csomagolása és tárolása olyan módon történik, hogy különböző folyamatoknál különböző módon kell nyomon követni a fizikai méreteket. A *Csomagolótermék-dimenziók* funkcióval termékenként egy vagy több dimenziótípust állíthat be. Minden dimenziótípus fizikai mértékek (súly, szélesség, mélység és magasság) sorozatát biztosítja, és meghatározza azt a folyamatot, amelyben ezek a fizikai mértékegységek érvényesek. Ha ez a funkció engedélyezve van, a rendszer a következő dimenziótípusokat támogatja:

- *Tárolás* – a tárolási dimenziók a helyi térfogatméréssel együtt használatosak annak meghatározására, hogy az egyes cikkek mekkora része tárolható különböző raktározási helyeken.
- *Csomagolás* – a csomagolási dimenziók a tárolóra bontás és a kézi csomagolási folyamat során használatosak annak meghatározására, hogy az egyes cikkek mekkora része fér el a különböző tárolótípusokban.
- *Beágyazott csomagolás* – a beágyazott csomagolási dimenziók akkor használatosak, ha a csomagolási folyamat több szintet tartalmaz.

A *Tárolás* dimenziók akkor is támogatottak, ha a *Csomagolótermék-dimenziók* funkció nincs engedélyezve. Ezeket a **Fizikai dimenzió** lapon állíthatja be a Supply Chain Management eszközben. Ezeket a dimenziókat minden olyan folyamat használja, ahol nincs megadva a csomagolás és a beágyazott csomagolási dimenzió.

A *Csomagolás* és a *Beágyazott csomagolás* dimenziók beállítása a **Tényleges termékdimenziók** lapon történik, amelyet a rendszer a *Csomagolótermék-dimenziók* funkció engedélyezésekor ad hozzá.
Ez a témakör egy olyan forgatókönyvet tartalmaz, amely bemutatja a funkció használatát.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>Kapcsolja be a Csomagolótermék-dimenziók funkciót

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Csomagolótermék-dimenziók*

## <a name="example-scenario"></a>Példaforgatókönyv

### <a name="set-up-the-scenario"></a>Forgatókönyv beállítása

A példahelyzet futtatása előtt elő kell készítenie a rendszert az ebben a részben leírt módon.

#### <a name="enable-demo-data"></a>Bemutatóadatok engedélyezése

Ha ezt a forgatókönyvet az itt megadott bemutatórekordok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az *USMF* jogi személyt is ki kell választani a kezdés előtt.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>Új fizikai dimenzió hozzáadása egy termékhez

Adjon hozzá új fizikai dimenziót egy termékhez a következő lépések alapján:

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válassza ki az *A0001* **Cikkszámú** terméket.
1. A Műveleti panelen nyissa meg a **Készletkezelés** lapot és a **Raktár** csoportban válassza ki a **Tényleges termékdimenziók** lehetőséget.
1. Megnyílik a **Tényleges termékdimenziók** lap. A Művelet panelen válassza az **Új** lehetőséget egy új dimenzió rácshoz való hozzáadásához a következő beállításokkal:
    - **Tényleges dimenziótípus** - *Csomagolás*
    - **Fizikai egység** - *db*
    - **Tömeg** - *4*
    - **Tömegegység** - *kg*
    - **Mélység** - *3*
    - **Magasság** - *4*
    - **Szélesség** - *3*
    - **Hossz** - *cm*
    - **Térfogategység** - *cm3*

A rendszer automatikusan kiszámítja a **Térfogat** mezőt a **Mélység**, a **Magasság** és a **Szélesség** beállításai alapján.

#### <a name="create-a-new-container-type"></a>Új tárolótípus létrehozása

Lépjen a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolótípusok** lehetőségre, és hozzon létre egy új rekordot a következő beállításokkal:

- **Tároló típuskódja** - *Kis méretű doboz*
- **Leírás** - *Kis méretű doboz*
- **Maximális nettó tömeg** - *50*
- **Térfogat** - *144*
- **Hossz** - *6*
- **Szélesség** - *6*
- **Magasság** - *4*

#### <a name="create-a-container-group"></a>Tárolócsoport létrehozása

Lépjen a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolócsoportok** lehetőségre, és hozzon létre egy új rekordot a következő beállításokkal:

- **Tárolócsoport azonosítója** - *Kis méretű doboz*
- **Leírás** - *Kis méretű doboz*

Adjon hozzá új sort adjon a **Részletek** részhez. Állítsa a **Tárolótípus** lehetőséget *Kis méretű doboz* típusúra.

#### <a name="set-up-a-container-build-template"></a>Tárolóépítési sablon beállítása

Lépjen a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolóépítési sablonok** lehetőségre, és válassza ki a **Dobozok** pontot. Módosítsa **Tárolócsoport azonosítója** értékét *Kis méretű doboz* értékre.

### <a name="run-the-scenario"></a>Forgatókönyv futtatása

Miután az előző szakaszban leírtak szerint előkészítette a rendszert, készen áll a forgatókönyv futtatására a következő szakaszban leírtak szerint.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>Értékesítési rendelés létrehozása és szállítmány létrehozása

Ebben a folyamatban szállítmányt hoz létre a cikk *csomagolási* dimenziói alapján, amelynek magassága 3-nál kisebb.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevőkód** *US-001*
    - **Raktár:** *63*

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaznia kell egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán. Ezen a soron állítsa be a következő értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *5*

1. Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.
1. A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.
1. Zárja be a lapot.
1. A Művelet ablaktáblán nyissa meg a **Raktár** lapot, és válassza a **Kiadás raktárba** parancsot munka létrehozásához a raktár számára.
1. Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Raktár \> Szállítmány részletes adatai** lehetőséget.
1. A Művelet ablakban nyissa meg a **Szállítás** lapot, és válassza a **Tárolók megtekintése** elemet. Győződjön meg arról, hogy a cikket a két *Kis méretű doboz* típusú tárolóba rakták.

#### <a name="place-an-item-into-storage"></a>Cikk tárolási helyre helyezése

1. Nyissa meg a mobileszközt, jelentkezzen be a 63-as raktárba, és lépjen a **Készlet \> Korrigálás be** lehetőségre.
1. Írja be a következőt: **Loc** = *SHORT-01*. Hozzon létre új azonosítótáblát a **Cikk** = *A0001* és a **Mennyiség** = *1 db* értékekkel.
1. Válassza ki az **OK** lehetőséget. Megjelenik a következő hibaüzenet: A SHORT-01 hely sikertelen, mert az A0001 cikk nem fér bele a hely megadott dimenzióiba. Ennek az az oka, hogy a termék *Tárolási* típusának dimenziói nagyobbak, mint a helyprofilban megadott dimenziók.
