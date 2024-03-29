---
title: A Mentés a következő fizetéshez lehetőség nem jelenik meg
description: Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha az e-commerce webhely fizetési lapján nem jelenik meg a Mentés a következő fizetéshez négyzet a Fizetési mód alatt.
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
ms.openlocfilehash: d0b398a4ffc5fb698ea04ba8642d05ccd4caf04c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287484"
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
