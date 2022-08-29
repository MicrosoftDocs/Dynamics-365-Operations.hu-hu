---
title: A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol a cikkek tárolhatók fel.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: b6cec3d9d598be221516506388e4797ad579a610
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286752"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol a cikkek tárolhatók fel.

## <a name="description"></a>Leírás

A kiskereskedelmi üzlet nem jelenik meg azon üzletek listáján, amelyekben felvehető az áru.

## <a name="resolution"></a>Felbontás

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Az üzlet címét jelző földrajzi hosszúság és szélesség beállítása a Commerce központi felületén

Az üzlet címét jelző földrajzi hosszúság és szélesség beállításához a Commerce központi felületén kövesse az alábbi lépéseket.

1. Ugorjon a következő oldalra: **Kiskereskedelem és kereskedelem \> Csatornák \> Üzletek \> Minden kiskereskedelmi üzlet**.
1. Keresse meg azt az üzletet, amelyet meg szeretne jeleníteni a felvételi lehetőségek az e-kereskedelmi webhelyen. Jegyezze fel az **Üzemi egység száma** értékét.
1. Nyissa meg a következőt: **Szervezeti adminisztráció \> Szervezetek \> Üzemi egységek**.
1. Keresse meg a korábban feljegyzett üzemi egység számát, majd válassza ki az üzemi egységet a keresési eredmények közül.
1. A **Címek** gyorslapon válassza a **További beállítások** lehetőséget, majd válassza a **Speciális** lehetőséget.
1. Az **Általános** gyorslapon ellenőrizze, hogy helyesen van-e beállítva a **Földrajzi hosszúság** és a **Földrajzi szélesség** mező. Ennek a lépésnek a részeként ellenőrizze, hogy az értékek helyesen vannak-e megadva pozitív vagy negatív számként.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Teljesítési csoportok konfigurálása a Commerce központi felületén

A teljesítési csoportok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Retail és Commerce \> Csatornák \> Online áruházak**.
1. Válassza ki a konfigurálni kívánt online üzletet.
1. A műveleti ablaktáblán válassza a **Beállítás** lehetőséget, majd válassza ki a **Teljesítési csoport hozzárendelése** elemet.
1. A **Teljesítési csoportok hozzárendelése** oldalon válassza ki az online üzlet teljesítési csoportját.
1. A **Beállítás** csoportban győződjön meg arról, hogy a kiskereskedelmi üzlet megfelelően legyen konfigurálva a teljesítési csoporthoz.

## <a name="additional-resources"></a>További erőforrások 

[Üzemi egység létrehozása](../../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md)

[Online csatorna beállítása](../channel-setup-online.md)
