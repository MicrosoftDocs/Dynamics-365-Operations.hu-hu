---
title: Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával
description: Ez a cikk egy olyan helyzetet mutatja be, amikor több rendelés kerül ki a raktárba, majd a szállítmánykonszolidáció munkaterület használatával később szállítmányok leszállítják.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationSetShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: eed484cd37b02e58831e0041c3e0625091283b65
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428117"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a>Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával

[!include [banner](../includes/banner.md)]

Ez a cikk egy olyan helyzetet mutatja be, amikor több rendelés kerül ki a raktárba, majd a szállítmánykonszolidáció munkaterület használatával később szállítmányok leszállítják.

## <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen cikkváltozat a Microsoft szabványos bemutatóadatában található értékekre és rekordokra hivatkozik Dynamics 365 Supply Chain Management. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása

Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat. A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.

## <a name="turn-the-manual-shipment-consolidation-feature-on-or-off"></a>A kézi szállítmánykonszolidáció funkció be- és kikapcsolása

A kézi szállítmánykonszolidáció csak akkor használható, ha a rendszeren be van kapcsolva. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy *kapcsolhatják*[be és kapcsolják ki ezt a funkciót, hogy a Szolgáltatáskezelési munkaterület Kézi szállítmánykonszolidáció szolgáltatását](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) keresi.

*Irányelvek* létrehozása előtt be kell kapcsolnia a Szállítmány konszolidálása funkciót is (az Ellátásilánc-kezelés 10.0.29-es verziója esetén a funkció kötelező, és nem kapcsolható ki). A további tudnivalókat lásd a Szállítmánykonszolidáció [irányelveinek konfigurálása.](configure-shipment-consolidation-policies.md)

## <a name="create-the-sales-orders-for-this-scenario"></a>Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz

Első lépésként hozza létre a munkához használni kívánt értékesítési rendelések gyűjteményét. A speciális raktár (WMS) folyamataihoz engedélyezett raktárral kell dolgoznia. Ha külön nem említik a másik raktárat, akkor ugyanazt a raktárat kell használni a következő rendelések mindegyikéhez.

Nyissa meg a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** pontot, és hozza létre az értékesítési rendelések gyűjteményét, amelyek a következő alszakaszokban szereplő beállításokkal rendelkeznek.

### <a name="create-order-set-1"></a>1. rendeléskészlet létrehozása

#### <a name="sales-orders-1-1-and-1-2"></a>1-1. és 1-2. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Szállítási mód:** *Légitá-légi*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

#### <a name="sales-order-1-3"></a>1-3. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Szállítás módja:** *10*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.
1. Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0002* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*
    - **Szállítási mód:** *Légitá-légi*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a második rendelési sor foglalásához.

### <a name="create-order-set-2"></a>2. rendeléskészlet létrehozása

#### <a name="sales-orders-2-1-and-2-2"></a>2-1. és 2-2. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-002*
    - **Szállítási mód:** *Légitá-légi*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *M9200* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Gyúlékony*)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.
1. Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *M9201* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Robbanásveszélyes*)
    - **Mennyiség:** *1.00*
    - **Szállítási mód:** *Légitá-légi*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a második rendelési sor foglalásához.

### <a name="create-order-set-3"></a>3. rendeléskészlet létrehozása

#### <a name="sales-orders-3-1-and-3-2"></a>3-1. és 3-2. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Vevői igénylés:** *1*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

#### <a name="sales-orders-3-3-and-3-4"></a>3-3. és 3-4. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Vevői igénylés:** *2*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

### <a name="create-order-set-4"></a>4. rendeléskészlet létrehozása

#### <a name="sales-orders-4-1-and-4-2"></a>4-1. és 4-2. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-003*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

#### <a name="sales-orders-4-3-and-4-4"></a>4-3. és 4-4. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-004*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

#### <a name="sales-orders-4-5-and-4-6"></a>4-5. és 4-6. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-007*
    - **Telephely:** *6*
    - **Raktár:** *61*
    - **Gyűjtő:** *ShipCons*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

#### <a name="sales-orders-4-7-and-4-8"></a>4-7. és 4-8. értékesítési rendelések

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-007*
    - **Telephely:** *6*
    - **Raktár:** *61*
    - **Gyűjtő:** Ezt a mezőt hagyja üresen.

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

## <a name="release-the-orders-to-the-warehouse"></a>A rendelések kiadása a raktárba

A következő lépések végrehajtásával kiadhatja az ehhez az esethez létrehozott összes értékesítési rendelést a raktárba.

1. Ugrás a **Kinnlevőségek \> Rendelések \> Minden értékesítési rendelésre**.
1. Keresse meg és válassza ki a kiadandó értékesítési rendelést.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek \> Kiadás raktárba** parancsot a kiválasztott értékesítési rendelés kiadásához.
1. Ismételje meg ezt az eljárást minden olyan értékesítési rendelésnél, amelyet az adott esethez létrehozott.

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a>Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával

1. Nyissa meg a **Raktárkezelés \> Kiadás raktárba \> Szállítmánykonszolidációs munkaterület** pontot.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezésszerkesztő párbeszédablak **Tartomány** lapján a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:

    - **Tábla:** *Értékesítési rendelések*
    - **Mező:** *Értékesítési rendelés*
    - **Feltételek:** Adja meg az értékesítési rendelések számának vesszővel tagolt listáját a jelen esethez létrehozott minden egyes rendelési készlethez.

1. Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.
1. A Művelet panelen válassza a **Szállítmányok konszolidálása** elemet.
1. Válassza ki az összes szállítmányt, majd a műveleti ablaktáblán válassza a **Konszolidálás** lehetőséget.

## <a name="verify-the-shipments"></a>Szállítmányok ellenőrzése

A következő eljárással ellenőrizhetők a szállítmánykonszolidálás eredményeképpen létrehozott vagy frissített szállítmányok. Ennek segítségével ellenőrizheti az adott esethez létrehozott összes rendeléskészletet, majd megtekintheti a következő részszakaszokat, amellyel meggyőződhet arról, hogy a várt eredményeket kapta.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Keresse meg és válassza ki a kívánt szállítmányt.
1. Ha a szállítmány létrehozásakor használt konszolidációs irányelvet létrehozzák vagy frissítik, akkor meg kell jelennie a **Szállítmánykonszolidációs irányelv** mezőben.

### <a name="related-shipments-for-order-set-1"></a>Az 1. rendeléskészlethez kapcsolódó szállítmányok

Két szállítmányt kellett létrehozni:

- Az első szállítmány három sort tartalmaz, és a *CustomerMode* szállítmánykonszolidációs irányelv használatával jött létre.
- A második szállítmányt, amely nem a *Légitársaságok* szállítási módot használja, a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával hozták létre.

### <a name="related-shipments-for-order-set-2"></a>A 2. rendeléskészlethez kapcsolódó szállítmányok

Három szállítmányt kellett létrehozni:

- Az első szállítmány *Gyúlékony* cikkeket tartalmaz.
- A másik két szállítmány mindegyike egy sort tartalmaz, amelyben a *Robbanásveszélyes* cikk szerepel.

### <a name="related-shipments-for-order-set-3"></a>A 3. rendeléskészlethez kapcsolódó szállítmányok

Két szállítmányt kellett létrehozni:

- Az első szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *1*.
- A második szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *2*.

### <a name="related-shipments-for-order-set-4"></a>A 4. rendeléskészlethez kapcsolódó szállítmányok

Négy szállítmányt kellett létrehozni:

- Az *US-003* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-004* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-007* vevő 4-5. és 4-6. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-007* vevő 4-7. és 4-8. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *CrossOrder* szállítmánykonszolidációs irányelv használatával.

## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidáció irányelveinek áttekintése](about-shipment-consolidation-policies.md)
- [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]