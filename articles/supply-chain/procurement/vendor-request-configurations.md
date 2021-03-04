---
title: Szállítókérés konfigurációi
description: Ez a témakör azokat a mezőket jeleníti meg, amelyeket ki kell tölteni egy új szállítókérésben.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: d78aa7c14ed2a2a5097f6f80c946c6ae4ed8bb94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429732"
---
# <a name="vendor-request-configurations"></a>Szállítókérés konfigurációi
[!include [banner](../includes/banner.md)]

A szállítókérés befejezéséhez egy szállítói kapcsolattartónak végre kell hajtania a potenciális szállító regisztrációs varázslóját.

A **Szállítókérés konfigurációi** űrlapon létrehozhat olyan profilokat, amelyek megadják a kötelező mezőket és a látható mezőket a potenciális szállító regisztrációs varázslójában.

A szállítói regisztrációs varázsló azzal kezd, hogy megkérdezi a potenciális szállítói felhasználótól, hogy mely országban/régióban végzi tevékenységét. Ez az információ határozza meg az alkalmazandó konfigurációt. Ha nincs megadott konfiguráció egy ország/régió számára, akkor az alapértelmezett konfigurációt használja a rendszer.

### <a name="set-up-a-vendor-request-configuration"></a>Szállítókérés konfigurációjának beállítása

Alapértelmezés szerint rendelkezésre áll egy szállítókonfiguráció a Szállítókérés konfigurációs űrlapon.

Nincs lehetőség országot/régiót kiválasztására az alapértelmezett konfigurációnál, így az **Országok/régiók** szakasz nem módosítható.

1. Kattintson a **Beszerzés és forrás** > **Beállítás** > **Szállítók** elemre, majd a **Szállítókérés konfigurációi** lehetőségre.
2. Kattintson a **Mezők** fülre a listában szereplő mezők állapotának beállításához.
3. Rejtett (nem látható)
4. Megjelenített (látható, de nem kötelező)
5. Szükséges (látható és kötelező)
6. Kattintson a **Tartalom** lapfülre annak megadásához, hogy jelenjen-e meg szöveg a varázslóban, illetve hogy szerepeljen-e üzenet arra vonatkozóan, hogy a potenciális szállítói felhasználónak el kell fogadnia ezt ahhoz, hogy a varázsló következő lépésével folytathassa a műveletet. Az információ vonatkozik mindazon feltételekre és kikötésekre, amelyeket a felhasználónak el kell fogadnia a folytatáshoz.

Emellett megadhat egy megerősítő üzenetet is, amely akkor jelenik meg, amikor a varázsló lefutott, és Ön hozzáadhat egy vagy több kérdőívet.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Hozzon létre egy szállítói konfigurációt egy adott ország/régió számára
1.  Kattintson a **Beszerzés és forrás** > **Beállítás** > **Szállítók** elemre, majd a **Szállítókérés konfigurációi** lehetőségre.
2.  Kattintson az **Új** lehetőségre egy új konfiguráció létrehozásához, és adja meg a konfiguráció nevét.
3.  Kattintson a **Mentés** gombra.
4.  Nyissa meg az **Országok/régiók** lapot, és válassza ki azt az országot/régiót, amelynél a konfigurációt használni kell.
5.  Hajtsa végre a következő konfigurációt, és kövesse following the guidelines for the default configuration.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]