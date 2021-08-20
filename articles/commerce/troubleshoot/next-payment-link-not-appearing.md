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
ms.openlocfilehash: 4887cde3e4243ae7a4da6402782e69e780ae20331ed80df63ba1239ef5187e41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769271"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>A Mentés a következő fizetéshez lehetőség nem jelenik meg

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az e-kereskedelmi webhely pénztároldalán nem jelenik meg a **Mentés a következő fizetéshez** lehetőség jelölőnégyzet a **Fizetési mód** pontban.

## <a name="description"></a>Leírás

Az e-kereskedelmi pénztároldalon a **Mentés a következő fizetéshez** lehetőség nem jelenik meg a **Fizetési mód** pontban.

A következő illusztráció egy olyan pénztároldalt mutat be, amely tartalmazza a **Mentés a következő fizetéshez** jelölőnégyzetet.

![A Mentés a következő fizetéshez jelölőnégyzet a Fizetés modulban.](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Megoldás

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Győződjön meg arról, hogy a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz helyesen van-e konfigurálva a Commerce központi felületén

Annak ellenőrzésére, hogy a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz helyesen van-e konfigurálva a Commerce központi felületén, kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatornák \> Online áruházak**.
1. Válassza ki az online áruházat.
1. A **Fizetési számlák** gyorslapon győződjön meg arról, hogy a **Fizetési információ mentésének engedélyezése az e-kereskedelemben** mező értéke **Igaz** legyen.

![Fizetési információ mentésének engedélyezése az e-kereskedelemben a Commerce központi felületén.](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>További erőforrások

[Fizetési modul](../payment-module.md)

[Online fizetési eszközök mentése az Adyen összekötővel](../dev-itpro/adyen-connector-listPI.md)
