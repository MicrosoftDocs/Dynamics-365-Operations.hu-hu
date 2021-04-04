---
title: Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: dd7c400f26b6fc7fbe1d4fec43a52295eb363333
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585351"
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

[Hitelkártya beállítása, engedélyezése és rögzítése](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
