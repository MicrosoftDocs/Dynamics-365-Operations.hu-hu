---
title: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja az alulszállítás százalékos értékét
description: Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja az alulszállítás százalékos értékét
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
ms.openlocfilehash: 5339b9d800f7454e2a00c230a8d5deca3979c074
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938481"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a>Nem tudja megerősíteni a szállítmányt, mert a mennyiség meghaladja az alulszállítás százalékos értékét

Hibakód: WAX1687

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 rakomány szállítása nem igazolható vissza, mert a(z) %2 cikk mennyisége meghaladja az alulszállításhoz meghatározott százalékot.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rakomány vagy szállítmány mennyisége csak részben lett kitárolva. A mennyiség jelenleg olyan százalékértékkel kisebb a kitárolt mennyiségnél, amely kívül esik a megengedett alulszállítási százaléknál.

## <a name="resolution"></a>Felbontás

A probléma javításához végezze el a következő feladatok egyikét:

- A rakománysor mennyiségének beállítása.
- Az alulszállítás százalékának beállítása.

### <a name="set-the-load-line-quantity"></a>A rakománysor mennyiségének beállítása

A rakománysor mennyiségének beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja az alulszállítás százalékos arányát.
1. A **Sor részletei** gyorslapon válassza ki az **Rendelés** lehetőséget.
1. A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** érték), hogy a szállítmány megerősítése elvégezhető legyen.

### <a name="set-the-underdelivery-percentage"></a>Az alulszállítás százalékának beállítása

Az alulszállítás százalékértékének beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely meghaladja az alulszállítás százalékos arányát.
1. A **Sor részletei** gyorslapon válassza ki az **Általános** lehetőséget.
1. Az **Alulszállítás** mezőben állítsa nagyobb százalékértékre az értéket, amely a rakománymennyiséggel szemben kitárolt mennyiségnek megfelelő, így a szállítmány megerősítése lehetséges.
