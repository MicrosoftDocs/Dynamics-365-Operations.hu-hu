---
title: A fizetés típusa csak hitelkártyás lehet hiba az értékesítési rendelés oldalán
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy rendelés szinkronizálása után hibaüzenet jelenik meg az értékesítési rendelés oldalán.
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
ms.openlocfilehash: 5be19949e9d1dbc43fdd3e6def119effa50a34d0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018410"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>„A fizetés típusa csak hitelkártyás lehet” hiba az értékesítési rendelés oldalon

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha egy rendelés szinkronizálása után hibaüzenet jelenik meg az értékesítési rendelés oldalán.

## <a name="description"></a>Leírás

Amikor a rendelés szinkronizálása után megnyitja az értékesítési rendelés lapot, a következő hibaüzenet jelenik meg: „A fizetés típusának hitelkártyának kell lennie, mivel a hitelkártya számát adta meg.”

![A fizetés típusa csak hitelkártyás lehet hiba](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Felbontás

### <a name="set-the-payment-type-in-commerce-headquarters"></a>A fizetéstípus beállítása a Commerce központi felületén

1. Ugorjon a **Kinnlevőségek \> Fizetési beállítás \> Fizetési feltételek** pontra.
1. A bal oldali navigációs részben válassza ki a fizetési feltételeket.
1. A **Fizetés típusa** mezőben győződjön meg arról, hogy a **Hitelkártya** lehetőség legyen kiválasztva.

## <a name="additional-resources"></a>További erőforrások

[Online értékesítések és kifizetések feladása](../tasks/posting-online-sales-payments.md)
