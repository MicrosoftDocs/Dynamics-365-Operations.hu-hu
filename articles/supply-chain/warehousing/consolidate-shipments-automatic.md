---
title: A raktárba az értékesítési rendelések automatikus kiadásával kiadott szállítmányok összesítése
description: Ez a cikk egy olyan esetet mutatja be, amikor több rendelés kerül kiadásra a raktárba ugyanabban az automatikus raktári kiadási időszakban.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: ba8e9790a5b7eb00b20fba19f452118e1f05fed0
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428254"
---
# <a name="consolidate-shipments-released-to-the-warehouse-using-automatic-release-of-sales-orders"></a>A raktárba az értékesítési rendelések automatikus kiadásával kiadott szállítmányok összesítése

[!include [banner](../includes/banner.md)]

Ez a cikk egy olyan esetet mutatja be, amikor több rendelés kerül kiadásra a raktárba ugyanabban az automatikus raktári kiadási időszakban. A rendeléseket a program automatikusan konszolidálja szállítmányokba, a szállítási konszolidációs irányelvként meghatározott szabályok alapján.

A forgatókönyv során értékesítési rendelések készletét hozza létre, és minden készletet kiad a raktárba. Ezt követően megtekintheti a szállítmánykonszolidáció során létrehozott vagy frissített szállítmányokat a konfigurált irányelvek alapján.

## <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen cikkváltozat a Microsoft szabványos bemutatóadatában található értékekre és rekordokra hivatkozik Dynamics 365 Supply Chain Management. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása

Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat. A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.

## <a name="create-the-sales-orders-for-this-scenario"></a>Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz

Első lépésként hozza létre a munkához használni kívánt értékesítési rendelések gyűjteményét. A speciális raktár (WMS) folyamataihoz engedélyezett raktárral kell dolgoznia. Ha külön nem említik a másik raktárat, akkor ugyanazt a raktárat kell használni a következő rendelések mindegyikéhez.

Nyissa meg a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** pontot, és hozza létre az értékesítési rendelések gyűjteményét, amelyek a következő alszakaszokban szereplő beállításokkal rendelkeznek.

### <a name="create-order-set-1"></a>1. rendeléskészlet létrehozása

#### <a name="sales-order-1-1"></a>1-1. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Szállítási mód:** *Légitá-légi*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

#### <a name="sales-order-1-2"></a>1-2. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Szállítási mód:** *Légitá-légi*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

#### <a name="sales-order-1-3"></a>1-3. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Szállítás módja:** *10*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0002* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*
    - **Szállítási mód:** *Légitá-légi*

### <a name="create-order-set-2"></a>2. rendeléskészlet létrehozása

#### <a name="sales-orders-2-1-and-2-2"></a>2-1. és 2-2. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-002*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *M9200* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Gyúlékony*)
    - **Mennyiség:** *1.00*

1. Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *M9201* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Robbanásveszélyes*)
    - **Mennyiség:** *1.00*
    - **Szállítási mód:** *Légitá-légi*

### <a name="create-order-set-3"></a>3. rendeléskészlet létrehozása

#### <a name="sales-order-3-1"></a>3-1. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-002*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *M9200* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Gyúlékony*)
    - **Mennyiség:** *1.00*

1. Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *M9201* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Robbanásveszélyes*)
    - **Mennyiség:** *1.00*
    - **Szállítási mód:** *Légitá-légi*

> [!NOTE]
> Ez a rendelés megegyezik azzal a két rendeléssel, amelyet a 2. rendelési készlethez hozott létre. A program azonban a saját rendeléskészletként jeleníti meg, mert a későbbiekben ezt a forgatókönyvet külön kell kiadni.

### <a name="create-order-set-4"></a>4. rendeléskészlet létrehozása

#### <a name="sales-order-4-1"></a>4-1. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Vevői igénylés:** *1*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

### <a name="create-order-set-5"></a>5. rendeléskészlet létrehozása

#### <a name="sales-orders-5-1-and-5-2"></a>5-1. és 5-2. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Vevői igénylés:** *2*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

#### <a name="sales-order-5-3"></a>5-3. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Vevői igénylés:** *1*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

### <a name="create-order-set-6"></a>6. rendeléskészlet létrehozása

#### <a name="sales-orders-6-1-and-6-2"></a>6-1. és 6-2. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-003*
    - **Vevői igénylés:** *2*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

#### <a name="sales-orders-6-3-and-6-4"></a>6-3. és 6-4. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-004*
    - **Vevői igénylés:** *1*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

#### <a name="sales-orders-6-5-and-6-6"></a>6-5. és 6-6. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-007*
    - **Telephely:** *6*
    - **Raktár:** *61*
    - **Gyűjtő:** *ShipCons*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

#### <a name="sales-orders-6-7-and-6-8"></a>6-7. és 6-8. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-007*
    - **Telephely:** *6*
    - **Raktár:** *61*
    - **Gyűjtő:** Ezt a mezőt hagyja üresen.

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a>Értékesítési rendelések automatikus kiadása a raktárba

A korábban létrehozott értékesítési rendelések mindegyik készletéhez végre kell hajtania egy eljárást a raktárba történő automatikus kiadáshoz. Minden esetben az itt megadott [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) kell végrehajtania.

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a>Alapszintű eljárás raktárba történő kiadáshoz

A korábban létrehozott értékesítési rendelések mindegyik készletéhez végre kell hajtania a következő alszakaszban ismertetett három eljárást.

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a>A kiadás során használandó hullámsablon frissítése

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. Állítsa a **Hullámsablontípus** mezőt *Szállítás* értékre.
1. Keresse meg és válassza ki azt a hullámsablont, amely az adott esethez létrehozott rendeléskészletekben használt raktárhoz van társítva. Ha például a *24*-es számú raktárat használta, akkor válassza a **24 – szállítás – alapértelmezett** hullámsablont. Ha a *61*-es számú raktárat használta, akkor válassza a **61 – szállítás** hullámsablont.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Állítsa a **Hullám feldolgozása a raktárba történő kiadáskor** lehetőséget *Nem* értékre.

#### <a name="release-to-the-warehouse"></a>Kiadás a raktárba

1. Nyissa meg a **Raktárkezelés \> Kiadás a raktárba \> Értékesítési rendelések automatikus kiadása** elemet.
1. Állítsa a **Kiadandó mennyiség** mezőt *Mind* értékre.
1. A **Szerepeltetni kívánt rekordok** gyorslapján válassza a **Szűrő** parancsot, hogy megnyíljon a lekérdezés párbeszédpanel.
1. A **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:

    - **Tábla:** *Értékesítési rendelés*
    - **Származtatott tábla:** *Értékesítési rendelés*
    - **Mező:** *Értékesítési rendelés*
    - **Feltételek:** Adja meg az értékesítési rendelések számának vesszővel tagolt listáját a kívánt rendelési készletből.

1. A lekérdezés mentéséhez kattintson az **OK** gombra.
1. Az **OK** gombra kattintva elindíthatja az *Automatikus kiadás a raktárba* eljárást.

#### <a name="review-the-shipment-that-is-created-or-updated"></a>A létrehozott vagy frissített szállítmány áttekintése

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Keresse meg és válassza ki a kívánt szállítmányt.
1. Ha a szállítmány létrehozásakor használt konszolidációs irányelvet létrehozzák vagy frissítik, akkor meg kell jelennie a **Szállítmánykonszolidációs irányelv** mezőben.

### <a name="release-sales-orders-from-order-set-1"></a>Értékesítési rendelések kiadása az 1. rendeléskészletből

Az 1. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.

Ha befejezte a munkát, akkor azt kell látnia, hogy két szállítmány jött létre:

- Az első szállítmány három sort tartalmaz, és a *CustomerMode* szállítmánykonszolidációs irányelv használatával jött létre.
- A második szállítmányt, amely nem a *Légitársaságok* szállítási módot használja, a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával hozták létre.

### <a name="release-sales-orders-from-order-set-2"></a>Értékesítési rendelések kiadása a 2. rendeléskészletből

A 2. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.

Ha befejezte a munkát, akkor azt kell látnia, hogy három szállítmány jött létre:

- Az első szállítmány *Gyúlékony* cikkeket tartalmaz.
- A másik két szállítmány mindegyike egy sort tartalmaz, amelyben a *Robbanásveszélyes* cikk szerepel.

### <a name="release-sales-orders-from-order-set-3"></a>Értékesítési rendelések kiadása a 3. rendeléskészletből

A 3. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.

Ha befejezte a műveletet, a következő műveletek végrehajtását kell látnia:

- Egy létező szállítmány frissült (a 2. rendeléskészlet raktárba való kiadásakor létrejött szállítmány). A sor, amelyhez a *Gyúlékony* cikk lett hozzáadva.
- Létrejött egy új szállítmány, amelyben a *Robbanásveszélyes* cikk szerepel.

### <a name="release-sales-orders-from-order-set-4"></a>Értékesítési rendelések kiadása a 4. rendeléskészletből

A 4. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.

Ha befejezte a munkát, akkor látnia kell, hogy egy meglévő szállítmány frissült (ahol a **Vevői igénylés** mező értéke *1*). Egy új sor lett hozzáadva a szállítmányhoz.

### <a name="release-sales-orders-from-order-set-5"></a>Értékesítési rendelések kiadása az 5. rendeléskészletből

Az 5. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.

Ha befejezte a műveletet, a következő műveletek végrehajtását kell látnia:

- Egy meglévő szállítmány frissült (ahol a **Vevői igénylés** mező értéke *1*). A rendszer hozzáadta az 5-3. értékesítési rendelés (ahol a **Vevői igénylés** mező értéke *1*) egyik sorát.
- Egy új szállítmány jött létre, ahol az 5-1. és 5-2. értékesítési rendelések sorai egyetlen szállítmányba vannak csoportosítva.

### <a name="release-sales-orders-from-order-set-6"></a>Értékesítési rendelések kiadása a 6. rendeléskészletből

A 6. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.

Ha befejezte a munkát, akkor azt kell látnia, hogy négy szállítmány jött létre:

- Az *US-003* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-004* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-007* vevő 6-5. és 6-6. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-007* vevő 6-7. és 6-8. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *CrossOrder* szállítmánykonszolidációs irányelv használatával.

## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidáció irányelveinek áttekintése](about-shipment-consolidation-policies.md)
- [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]