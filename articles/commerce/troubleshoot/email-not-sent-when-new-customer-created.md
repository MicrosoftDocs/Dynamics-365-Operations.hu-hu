---
title: Az új vevők létrehozásakor az üdvözlő e-mail küldése nem történik meg.
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha az új vevők létrehozásakor nem küldnek el üdvözlő e-mail értesítést Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 1a4faf6cd189f69232e7f9ab8d0e79b320cfe2d9
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349924"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>Az új vevők létrehozásakor az üdvözlő e-mail küldése nem történik meg.

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha az új vevők létrehozásakor nem küldnek el üdvözlő e-mail értesítést Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Leírás

Amikor új vevőt hoznak létre a Commerce Headquarters alkalmazásban, akkor nem küld a rendszer üdvözlő e-mailt a vevőnek annak ellenére, **hogy** be van állítva egy e-mail értesítés a Vevő által létrehozott e-mail értesítéstípushoz.

## <a name="resolution"></a>Megoldás

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>A vevő által létrehozott e-mail értesítéstípus helyes e-mail azonosítójának beállítása

A vevő által a **központban** **létrehozott** e-mail értesítési típusnak megfelelő e-mail azonosító beállítását a következő lépések szerint hajtsa végre.

1. Menjen a **Retail and Commerce \> Headquarters beállításához a \> Commerce e-mail értesítési profilhoz**.
1. A bal oldali navigációs ablakban válassza ki az e-mail értesítési profilt.
1. A **Kiskereskedelmi esemény értesítési beállításai területen** a Vevő **által** létrehozott e-mail értesítési típusnál állítsa **be az e-mail** azonosító mezőjét **a NewCust típusra**.

## <a name="additional-resources"></a>További erőforrások

[E-mail-értesítési profil beállítása](../email-notification-profiles.md)
