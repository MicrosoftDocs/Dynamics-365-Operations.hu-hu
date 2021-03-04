---
title: Szállítmányok manuális konszolidálása a szállítmányok konszolidálása oldal használatával
description: Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba, majd később Szállítmányok konszolidálása oldallal konszolidálják őket.
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
ms.openlocfilehash: ac60bef797d8e0bbe0d20f1585d5c3c0163f8788
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429284"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>Szállítmányok manuális konszolidálása a szállítmányok konszolidálása oldal használatával

[!include [banner](../includes/banner.md)]

Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba, majd később a **Szállítmányok konszolidálása** oldallal konszolidálják őket.

## <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása

Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat. A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.

## <a name="create-the-sales-orders-for-this-scenario"></a>Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz

Első lépésként hozza létre a munkához használni kívánt értékesítési rendelések gyűjteményét. A speciális raktár (WMS) folyamataihoz engedélyezett raktárral kell dolgoznia. Ha külön nem említik a másik raktárat, akkor ugyanazt a raktárat kell használni a következő rendelések mindegyikéhez.

Nyissa meg a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** pontot, és hozza létre az értékesítési rendelések gyűjteményét, amelyek a következő alszakaszokban szereplő beállításokkal rendelkeznek.

### <a name="create-sales-orders-1-and-2"></a>1. és 2. értékesítési rendelés létrehozása

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-007*
    - **Gyűjtő:** *ShipCons*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

### <a name="create-sales-orders-3-and-4"></a>3. és 4. értékesítési rendelés létrehozása

1. Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-007*
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

## <a name="consolidate-shipments"></a>Szállítmányok konszolidálása

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Keresse meg és válassza ki a szállítmányt, amely az 1. értékesítési rendelés raktárba való kiadásakor jött létre. (Ennek **Szállítmánykonszolidációs irányelv** mezőjének *Rendelésgyűjtő* értékűnek kell lennie.)
1. A Művelet panel **Szállítmányok** lapján válassza a **Szállítmányok \> Szállítmányok konszolidálása** menüpontot.
1. Ellenőrizze a konszolidálásra javasolt szállítmányokat. A rendszer csak egyetlen olyan szállítmányt javasolhat a konszolidálásra, amelynek ugyanaz az irányelve.
1. Zárja be a **Szállítmány konszolidációja** oldalt.
1. Keresse meg és válassza ki a szállítmányt, amely az 3. értékesítési rendelés raktárba való kiadásakor jött létre. (Ennek **Szállítmánykonszolidációs irányelv** mezőjének *Alapértelmezett* értékűnek kell lennie.)
1. A Művelet panel **Szállítmányok** lapján válassza a **Szállítmányok \> Szállítmányok konszolidálása** menüpontot.
1. Ellenőrizze, hogy nincs konszolidálásra javasolt szállítmány.
1. Válassza ki a **Szűrők megjelenítése** elemet.
1. A **szűrők** ablaktáblán távolítsa el a **Rendelésszám** szűrőt, majd válassza az **alkalmazás** parancsot.
1. Ellenőrizze a konszolidálásra javasolt szállítmányokat. A rendszer csak egyetlen olyan szállítmányt javasolhat a konszolidálásra, amelynek ugyanaz az irányelve.

## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidációs irányelvek](about-shipment-consolidation-policies.md)
- [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]