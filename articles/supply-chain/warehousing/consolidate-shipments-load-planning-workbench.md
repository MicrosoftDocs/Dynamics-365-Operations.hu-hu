---
title: Szállítmányok konszolidálása a Kiadás a raktárba lehetőség használatával a Rakománytervező munkaterület oldalról
description: Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba ugyanabban a rakományban, amelyeket a rendszer automatikusan szállítmányokká konszolidál.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 2f1dd5c743664e638c043b600ae7b0f6bce5ddcd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429282"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a>Szállítmányok konszolidálása a Kiadás a raktárba lehetőség használatával a Rakománytervező munkaterület oldalról

[!include [banner](../includes/banner.md)]

Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba ugyanabban a rakományban, amelyeket a rendszer automatikusan szállítmányokká konszolidál.

## <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.

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

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

#### <a name="sales-order-1-2"></a>1-2. értékesítési rendelés

1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

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

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a>A rakománytervezési munkaterület használata a rakományok létrehozásához és kiadásához a raktárba

A következő lépések végrehajtásával rakományt hozhat létre az egyes rendeléskészletekhez, amelyeket ehhez az esethez készített, majd kiadhatja azt a raktárnak.

1. Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.
1. Az **Értékesítési sorok** lapon megkeresheti és kiválaszthatja az adott esethez létrehozott rendeléskészletek egyikének összes értékesítési rendelési sorait.
1. A művelet ablaktábla **Kereslet és kínálat** lapján válassza a **Hozzáadás \> Új rakományhoz** lehetőséget, amellyel a kiválasztott rendelési sorokat új rakományhoz adhatja.
1. A **Rakománysablon hozzárendelése** párbeszédablakban a **Rakománysablon azonosítója** mezőben válassza ki a rakománysablont, pl. a *Normál rakománysablon* elemet.
1. Az **OK** gombbal zárja be a párbeszédpanelt. 
1. A **Rakomány** szakaszban keresse meg és válassza ki az imént létrehozott rakományt.
1. A kiválasztott rakomány raktárba történő kiadásához válassza a **Kiadás \> Kiadás a raktárba** elemet.
1. Ismételje meg ezt az eljárást a három további rendeléskészletnél, amelyet az adott esethez létrehozott.

## <a name="verify-the-shipments"></a>Szállítmányok ellenőrzése

A következő eljárással ellenőrizhetők a szállítmánykonszolidálás eredményeképpen létrehozott vagy frissített szállítmányok. Ennek segítségével ellenőrizheti az adott esethez létrehozott összes rendeléskészletet, majd megtekintheti a következő részszakaszokat, amellyel meggyőződhet arról, hogy a várt eredményeket kapta.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Keresse meg és válassza ki a kívánt szállítmányt.
1. Ha a szállítmány létrehozásakor használt konszolidációs irányelvet létrehozzák vagy frissítik, akkor meg kell jelennie a **Szállítmánykonszolidációs irányelv** mezőben.

### <a name="release-order-set-1-in-one-load"></a>1. rendeléskészlet kiadása egy rakományban

Két szállítmányt kellett létrehozni:

- Az első szállítmány három sort tartalmaz, és a *CustomerMode* szállítmánykonszolidációs irányelv használatával jött létre.
- A második szállítmányt, amely nem a *Légitársaságok* szállítási módot használja, a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával hozták létre.

### <a name="release-order-set-2-in-one-load"></a>2. rendeléskészlet kiadása egy rakományban

Három szállítmányt kellett létrehozni:

- Az első szállítmány a *Gyúlékony* cikkeket tartalmazza.
- A másik két szállítmány mindegyike egy sort tartalmaz, amelyben a *Robbanásveszélyes* cikk szerepel.

### <a name="release-order-set-3-in-one-load"></a>3. rendeléskészlet kiadása egy rakományban

Két szállítmányt kellett létrehozni:

- Az első szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *1*.
- A második szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *2*.

### <a name="release-order-set-4-in-one-load"></a>4. rendeléskészlet kiadása egy rakományban

Négy szállítmányt kellett létrehozni:

- Az *US-003* vevői számla két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-004* vevői számla két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-007* vevői számla 4-5. és 4-6. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.
- Az *US-007* vevői számla 4-7. és 4-8. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *CrossOrder* szállítmánykonszolidációs irányelv használatával.

## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidációs irányelvek](about-shipment-consolidation-policies.md)
- [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]