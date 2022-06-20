---
title: Szállítmányok összesítése a szállítmányösszesítési szabályzat felülbírálása esetén
description: Ez a cikk olyan helyzetről ad le, amikor egy vagy több értékesítési sort manuálisan kell kiadni a raktárnak a Kiadás raktárba lapról a raktárba, és a rendszer által meghatározott szállítmánykonszolidációi házirendet a kiadás előtt felül kell bírálni.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 680941adeba1fc1cd54a02fb366d3d5903938d77
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878700"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden"></a>Szállítmányok összesítése a szállítmányösszesítési szabályzat felülbírálása esetén

[!include [banner](../includes/banner.md)]

Ez a cikk olyan helyzetről ad le, amikor egy vagy több értékesítési sort manuálisan kell kiadni a **raktárnak** a Kiadás raktárba lapról a raktárba, és a rendszer által meghatározott szállítmánykonszolidációi házirendet a kiadás előtt felül kell bírálni. Előfordulhat, hogy a szállítmánykonszolidációs irányelvének felülbírálására szükség lehet, ha például egy olyan rendelést, amelynél a nyitott szállítmányok általában nem lettek összesítve, nyitott szállítmányokkal kell összesíteni.

Az eset során létrehoz egy értékesítési rendelést, majd felülírja az alapértelmezett szállítmánykonszolidációs irányelvet, mielőtt a rendeléseket kiadja a raktárba.

## <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen cikkváltozat a Microsoft szabványos bemutatóadatában található értékekre és rekordokra hivatkozik Dynamics 365 Supply Chain Management. Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása

Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat. A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.

## <a name="create-the-sales-orders-for-this-scenario"></a>Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz

1. Ugorjon a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** lehetőséghez, és hozza létre a következő beállításokat tartalmazó három azonos értékesítési rendelést:

    - **Vevőkód** *US-002*

1. Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:

    - **Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)
    - **Mennyiség:** *1.00*

1. Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>Értékesítési rendelések kiadása a Kiadás a raktárba oldalról

Hajtsa végre a következő lépéseket a szállítmánykonszolidációs irányelv felülbírálásához a raktárba történő kiadás során.

1. Ugrás a **Raktárkezelés \> Kiadás a raktárba \> Kiadás a raktárba**.
1. A felső panelen válassza ki az ehhez az esethez létrehozott első értékesítési rendelést.
1. Válassza a **Hozzáadás** gombot, hogy a sort kiadja a raktárba. Figyelje meg, hogy az alsó panelre az *Alapértelmezett* szállítmánykonszolidációs irányelv vonatkozik.
1. Az alsó panelen válassza az **Új szállítmánykonszolidációs irányelv kiválasztása** lehetőséget.
1. Válasszon ki egy olyan irányelvet, amely lehetővé teszi a konszolidációt ugyanazon irányelv egyéb nyitott szállítmányai esetében. Például válassza ki a *CustomerOrderNo* irányelvet.
1. Válassza ki a **Kiadás a raktárba** lehetőséget.
1. Válassza ki az ehhez az esethez létrehozott második és harmadik értékesítési rendelést.
1. Válassza a **Hozzáadás** gombot, hogy a sort kiadja a raktárba. Figyelje meg, hogy az alsó panelre az *Alapértelmezett* irányelv vonatkozik.
1. Válassza ki a második sort, majd az **Új szállítmánykonszolidációs irányelv kiválasztása** mezőben válassza ki a *CustomerOrderNo* irányelvet.
1. Mindkét sor esetében válassza a **Kiadás a raktárba** lehetőséget.

## <a name="verify-the-shipments"></a>Szállítmányok ellenőrzése

Két szállítmányt kellett létrehozni:

- Az első szállítmány két sort tartalmaz, és a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával jött létre.
- A második szállítmány egy sort tartalmaz, és az *Alapértelmezett* szállítmánykonszolidációs irányelv használatával jött létre.

A létrehozott szállítmányok áttekintéséhez kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Keresse meg és válassza ki a kívánt szállítmányt.
1. A **Szállítmánykonszolidációs rányelv** mezőjében ellenőrizze a szállítmány létrehozásakor használt konszolidációs irányelvet.

## <a name="additional-resources"></a>További erőforrások

- [Szállítmánykonszolidációs irányelvek](about-shipment-consolidation-policies.md)
- [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]