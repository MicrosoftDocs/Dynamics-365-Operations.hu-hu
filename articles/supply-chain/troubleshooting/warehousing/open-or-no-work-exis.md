---
title: Befejezetlen vagy hiányzó munka miatt nem erősítheti meg a szállítmányt
description: Befejezetlen vagy hiányzó munka miatt nem erősítheti meg a szállítmányt
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123843"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a>Befejezetlen vagy hiányzó munka miatt nem erősítheti meg a szállítmányt

Hibakód: WAX515

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 szállítmány szállítása nem igazolható vissza, mert a rakomány minden munkájának be kell fejeződnie.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rakomány vagy szállítmány jelenleg olyan állapotban van, amelyben a szállítmány megerősítése sikertelen. A szállítmány megerősítése előtt legalább egy munkának léteznie kell a rakományhoz, és minden munkának *Lezárt* vagy *Visszavonva* állapotúnak kell lennie.

## <a name="resolution"></a>Felbontás

Ellenőrizze a rakomány vagy szállítmány kapcsolódó értékesítési rendeléseit és átmozgatott rendeléseit, illetve győződjön meg arról, hogy minden kapcsolódó munkát befejeztek vagy töröltek.

A szállítmányokkal és a rakományokkal több oldalon is dolgozhat. Az alábbi alszakaszok néhány példát mutatnak be.

### <a name="all-loads-page"></a>Minden rakomány lap

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. Az egyes munkaazonosítók állapotának vizsgálata. Minden olyan munkaazonosító nyomon követési állapota, amely nem *Lezárt* vagy *Visszavonva* állapotú.
1. Ha minden munkaazonosító állapota *Lezárt* vagy *Visszavonva*, akkor próbálja meg újra a szállítmány megerősítését.

### <a name="all-shipments-page"></a>Minden szállítmány oldal

1. Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.
1. Válassza ki azt a rakományt, amelyet nem lehet megerősíteni.
1. A Művelet ablaktábla **Szállítmányok** lapjának **Munka** csoportjában válassza a **Munka részletei** elemet.
1. Az egyes munkaazonosítók állapotának vizsgálata. Minden olyan munkaazonosító nyomon követési állapota, amely nem *Lezárt* vagy *Visszavonva* állapotú.
1. Ha minden munkaazonosító állapota *Lezárt* vagy *Visszavonva*, akkor próbálja meg újra a szállítmány megerősítését.

### <a name="all-work-page"></a>Minden munka lap

1. Ugorjon a **Raktárkezelés \> Munka \> Minden munka** pontra.
1. Válassza ki azt a rendelésszámot, amelyhez nem lehet megerősíteni a szállítmányt.
1. A műveleti ablaktábla **Szállítmány** fülön lévő **Szállítmány** csoportban válassza a **Szállítmány megerősítése** elemet.
1. Az egyes munkaazonosítók állapotának vizsgálata. Minden olyan munkaazonosító nyomon követési állapota, amely nem *Lezárt* vagy *Visszavonva* állapotú.
1. Ha minden munkaazonosító állapota *Lezárt* vagy *Visszavonva*, akkor próbálja meg újra a szállítmány megerősítését.
