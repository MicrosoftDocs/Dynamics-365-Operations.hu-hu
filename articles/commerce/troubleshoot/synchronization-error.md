---
title: Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.
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
ms.openlocfilehash: fa174bbb257379f6ce906dd21180bbcb19f8bc3f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021127"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.

## <a name="description"></a>Leírás

Online rendelés szinkronizálása esetén a következő hibaüzenet jelenik meg: „A hitelkártyás tranzakciók feldolgozásához szükség van egy alapértelmezett fizetési szolgáltatásra.”

![Hiányzó alapértelmezett fizetési szolgáltatással kapcsolatos hiba](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Felbontás

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Az alapértelmezett fizetési szolgáltatás megerősítése vagy beállítása a Commerce központi felületén

Kövesse az alábbi lépéseket az alapértelmezett fizetési szolgáltatás megerősítéséhez vagy beállításához a Commerce központi felületén.

1. Ugorjon a következő oldalra: **Kinnlevőségek \> Fizetési beállítások \> Fizetési szolgáltatások**.
1. Győződjön meg arról, hogy az **Új hitelkártyák alapértelmezett feldolgozója** beállítás értéke **Igen** legyen egy fizetési szolgáltatás esetén.

## <a name="additional-resources"></a>További erőforrások

[Hitelkártya beállítása, engedélyezése és rögzítése](../../finance/accounts-receivable/credit-card-authorizations.md)