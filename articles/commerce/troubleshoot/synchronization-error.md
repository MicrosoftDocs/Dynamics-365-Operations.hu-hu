---
title: Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása során.
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
ms.openlocfilehash: 49d16c39fdcee0a22d1cabe14cd9b6d124d6f04d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901676"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása során.

## <a name="description"></a>Leírás

Online rendelés szinkronizálása esetén a következő hibaüzenet jelenik meg: „A hitelkártyás tranzakciók feldolgozásához szükség van egy alapértelmezett fizetési szolgáltatásra.”

![Hiányzó alapértelmezett fizetési szolgáltatással kapcsolatos hiba.](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Megoldás

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Az alapértelmezett fizetési szolgáltatás megerősítése vagy beállítása a Commerce központi felületén

Kövesse az alábbi lépéseket az alapértelmezett fizetési szolgáltatás megerősítéséhez vagy beállításához a Commerce központi felületén.

1. Ugorjon a következő oldalra: **Kinnlevőségek \> Fizetési beállítások \> Fizetési szolgáltatások**.
1. Győződjön meg arról, hogy az **Új hitelkártyák alapértelmezett feldolgozója** beállítás értéke **Igen** legyen egy fizetési szolgáltatás esetén.

## <a name="additional-resources"></a>További erőforrások

[Hitelkártya beállítása, engedélyezése és rögzítése](../../finance/accounts-receivable/credit-card-authorizations.md)