---
title: Az új vevők létrehozásakor az üdvözlő e-mail küldése nem történik meg
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha az új vevők létrehozásakor nem küldnek üdvözlő e-mail értesítést Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 5aa7d864555f96194500989e2d7ad200d8892121
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219404"
---
# <a name="welcome-email-isnt-sent-when-new-customers-are-created"></a>Új vevők létrehozásakor az üdvözlő e-mail nem lesz elküldve.

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amelyek segítséget nyújtanak abban az esetben, ha az új vevők létrehozásakor nem küldnek üdvözlő e-mail értesítést Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Leírás

Amikor új vevőt hoznak létre a Commerce Headquarters alkalmazásban, akkor nem küld a rendszer üdvözlő e-mailt a vevőnek annak ellenére, **hogy** be van állítva egy e-mail értesítés a Vevő által létrehozott e-mail értesítéstípushoz.

## <a name="resolution"></a>Megoldás

### <a name="associate-an-email-notification-profile-under-commerce-parameters"></a>E-mail értesítési profil társítása a Commerce-paraméterek között

1. A központi központban kattintson a **Retail and Commerce \> Headquarters beállítási \>\> Commerce-paraméterei – \> Általános beállítási webhelyre**.
2. Az e-mail **értesítési** profil legördülő listájában válassza ki azt az e-mail értesítési profilt, amely megfeleltetést tartalmaz a vevő által létrehozott értesítési típus és a vevő által létrehozott e-mail sablon között.  

> [!NOTE] 
> Ha engedélyezi a vevő által létrehozott értesítéseket, a jogi személy összes csatornája számára létrehozott vevők megkapják a vevő által létrehozott e-mailt. A vevő által létrehozott értesítések jelenleg nem korlátozható egyetlen csatornára.

További tájékoztatás: Tranzakciós események [e-mail sablonjainak létrehozása](../email-templates-transactions.md). 

## <a name="additional-resources"></a>További erőforrások

[E-mail-értesítési profil beállítása](../email-notification-profiles.md)
