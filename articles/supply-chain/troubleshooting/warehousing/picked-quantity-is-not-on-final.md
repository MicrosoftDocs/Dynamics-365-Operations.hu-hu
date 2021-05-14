---
title: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
description: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938483"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki

Hibakód: LoadNotPickedAndMrmedToFinalShippingLocation

## <a name="symptoms"></a>Tünetek

Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:

> A(z) %1 rakományhoz szükséges egyes cikkek még nem lettek kitárolva és a végső szállítási helyre áthelyezve.

Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.

## <a name="cause"></a>Ok

A rakomány vagy szállítmány jelenleg nem erősíthető meg, mert a következő feltételek valamelyike fennáll:

- A kapcsolódó munkát még nem választották ki és nem helyezték át a végső szállítási helyre.
- A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével.

## <a name="resolution"></a>Felbontás

A rakomány vagy szállítmány kapcsolódó értékesítési és átmozgatási rendelésének ellenőrzése. Győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.
1. A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.
1. Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.
1. A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.
1. Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.
1. Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.
