---
title: Vállalatközi beszerzés és vevői rendelések létrehozása több vállalatban
description: Ez a témakör leírja, hogyan lehet vállalatközi beszerzési rendeléseket vagy értékesítési rendeléseket létrehozni több vállalatban
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8458a08c1a2e5e656c496eb74188d0e2e7257020
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673718"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>Vállalatközi beszerzés és vevői rendelések létrehozása több vállalatban

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management nem csak egy termelési vállalattal és több értékesítési vállalattal használható. Minden vállalatközinek beállított vállalat lehet kereskedelmi vállalat, így a termelési vállalatok is.

Ha több vállalat tudja ugyanazt a cikket szállítani, akkor szabadon kiválaszthatja, hogy melyik vállalattól szeretne vásárolni, és a frissítések feldolgozása akkor is megtörténik, ha egy értékesítési rendelésből több beszerzési rendelés keletkezik.

Ahogy egy vállalatközi beszerzési rendelést automatikusan létre lehet hozni, ugyanúgy létre lehet hozni egy eredeti értékesítési rendelést a vállalatnál, majd több vállalatközi szállító vállalat bevonásával teljesíteni lehet a rendelést oly módon, hogy több vállalatközi beszerzési rendelést hoz létre. A Microsoft Dynamics 365 Supply Chain Management automatikusan létrehozza a vállalatközi értékesítési rendelést a szállító vállalatoknál.

Ehhez minden vállalatot kereskedelmi kapcsolatként kell beállítani. A szállító vállalatokat be kell állítani a Microsoft Dynamics 365 Supply Chain Management alkalmazásban vállalatközi szállítóként, és ők lesznek az adott cikk elsődleges szállítói. A **Fejléc** nézetben az értékesítési rendelésben ki kell választania a **Vállalatközi rendelések automatikus létrehozása** és a **Közvetlen kiszállítás** mezőt a **Vállalatközi beállítások** gyorslapon. Ez az alapértelmezett beállítás.

A szokásos módon hozza létre az értékesítési sorokat. Amikor elhagyja a rekordot, egy üzenet jelenik meg, amely arról tájékoztatja, hogy vállalatközi beszerzési rendelések és vállalatközi értékesítési rendelések létrejöttek. Az üzenet az új rendelésekre hivatkozásokat tartalmaz. A szállító vállalatoknál létrehozott vállalatközi értékesítési rendelések megtekintéséhez nyissa meg az eredeti értékesítési rendelést, és az **Általános** lapon, a **Kapcsolódó információk** csoportban válassza a **Hivatkozások** lehetőséget.

Ha megnyitja a szállítók vállalatközi beszerzési rendeléseit, láthatja, hogy a Microsoft Dynamics 365 Supply Chain Management minden szállítónál automatikusan kitölti az eredeti értékesítési rendelésszámot és a vállalatközi rendelésszámot.

Hasonlóan, ha megnyitja a szállítók vállalatközi értékesítési rendeléseit, láthatja, hogy a Microsoft Dynamics 365 Supply Chain Management minden szállítónál automatikusan kitölti az eredeti beszerzési rendelésszámot és a vállalatközi rendelésszámot.

> [!NOTE]
> Ha a rendelésben szereplő cikkek az egyik vállalatközi vállalatnál megtalálhatók, de a másiknál nem, akkor a Microsoft Dynamics 365 Supply Chain Management annál a szállító vállalatnál hozza létre a vállalatközi rendeléseket, amelynél megvannak a cikkek, viszont a másik vállalatnál leállítja a rendelés-létrehozást. Erről a program üzenetben értesíti a felhasználót.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
