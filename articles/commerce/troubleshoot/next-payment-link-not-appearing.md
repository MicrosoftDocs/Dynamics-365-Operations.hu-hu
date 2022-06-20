---
title: A Mentés a következő fizetéshez lehetőség nem jelenik meg
description: Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az e-commerce webhely fizetési lapján nem jelenik meg a Mentés a következő fizetéshez négyzet a Fizetési mód alatt.
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
ms.openlocfilehash: efa04c87f78c376fd00da1b26aedb9e8b428dfa5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871555"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>A Mentés a következő fizetéshez lehetőség nem jelenik meg

[!include [banner](../../includes/banner.md)]

Ez a cikk olyan **hibaelhárítási** **útmutatást** tartalmaz, amely segítséget nyújt abban az esetben, ha az e-commerce webhely fizetési lapján nem jelenik meg a Mentés a következő fizetéshez négyzet a Fizetési mód alatt.

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
