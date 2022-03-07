---
title: A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol felvehető az áru.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6ccd60082b65fdbd47fef4a67ba269d7d7afc04679647d3eb8d2a5e9c21a19b0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762620"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>A kiskereskedelmi üzlet nem jelenik meg a felvételt lehetővé tevő üzletek listájában

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha egy kiskereskedelmi üzlet nem jelenik meg azon üzletek listájában, ahol felvehető az áru.

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