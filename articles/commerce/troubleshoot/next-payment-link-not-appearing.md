---
title: A Mentés a következő fizetéshez lehetőség nem jelenik meg
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az e-kereskedelmi webhely pénztároldalán nem jelenik meg a Mentés a következő fizetéshez lehetőség jelölőnégyzet a Fizetési mód pontban.
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
ms.openlocfilehash: af19a3abd78d543d82f7a8d017e2dc413115a6d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018434"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>A Mentés a következő fizetéshez lehetőség nem jelenik meg

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az e-kereskedelmi webhely pénztároldalán nem jelenik meg a **Mentés a következő fizetéshez** lehetőség jelölőnégyzet a **Fizetési mód** pontban.

## <a name="description"></a>Leírás

Az e-kereskedelmi pénztároldalon a **Mentés a következő fizetéshez** lehetőség nem jelenik meg a **Fizetési mód** pontban.

A következő illusztráció egy olyan pénztároldalt mutat be, amely tartalmazza a **Mentés a következő fizetéshez** jelölőnégyzetet.

![A Mentés a következő fizetéshez jelölőnégyzet a Fizetés modulban](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Felbontás

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Győződjön meg arról, hogy a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz helyesen van-e konfigurálva a Commerce központi felületén

Annak ellenőrzésére, hogy a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz helyesen van-e konfigurálva a Commerce központi felületén, kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatornák \> Online áruházak**.
1. Válassza ki az online áruházat.
1. A **Fizetési számlák** gyorslapon győződjön meg arról, hogy a **Fizetési információ mentésének engedélyezése az e-kereskedelemben** mező értéke **Igaz** legyen.

![Fizetési információ mentésének engedélyezése az e-kereskedelemben a Commerce központi felületén](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>További erőforrások

[Fizetési modul](../payment-module.md)

[Online fizetési eszközök mentése az Adyen összekötővel](../dev-itpro/adyen-connector-listPI.md)
