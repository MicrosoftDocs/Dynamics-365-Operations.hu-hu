---
title: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja a felülszállítás százalékos értékét
description: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja a felülszállítás százalékos értékét
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b25050572662afebbeaa39fa5a96e70cef618ac671dceba189fab1315480ede2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755155"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a>Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja a felülszállítás százalékos értékét

Hibakód: WAX1687

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 rakomány szállítása nem igazolható vissza, mert a(z) %2 cikk mennyisége meghaladja a felülszállításhoz meghatározott százalékot.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rakomány vagy szállítmány mennyisége csak részben lett kitárolva. A mennyiség jelenleg olyan százalékértékkel nagyobb a kitárolt mennyiségnél, amely kívül esik a megengedett felülszállítási százaléknál.

## <a name="resolution"></a>Felbontás

A probléma javításához végezze el a következő feladatok egyikét:

- A rakománysor mennyiségének beállítása.
- A felülszállítás százalékának beállítása.

### <a name="set-the-load-line-quantity"></a>A rakománysor mennyiségének beállítása

A rakománysor mennyiségének beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja a felülszállítás százalékos arányát.
1. A **Sor részletei** gyorslapon válassza ki az **Rendelés** lehetőséget.
1. A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** érték), hogy a szállítmány megerősítése elvégezhető legyen.

### <a name="set-the-overdelivery-percentage"></a>A felülszállítás százalékának beállítása

Az alulszállítás százalékértékének beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja a felülszállítás százalékos arányát.
1. A **Sor részletei** gyorslapon válassza ki az **Általános** lehetőséget.
1. A **Felülszállítás** mezőben állítsa nagyobb százalékértékre az értéket, amely a rakománymennyiséggel szemben kitárolt mennyiségnek megfelelő, így a szállítmány megerősítése lehetséges.
