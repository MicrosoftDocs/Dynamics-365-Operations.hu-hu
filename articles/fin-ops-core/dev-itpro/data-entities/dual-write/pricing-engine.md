---
title: Igény szerinti szinkronizálás a(z) Dynamics 365 Supply Chain Management árképzés motorral
description: Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Supply Chain Management árképzési motorját a Dynamics 365 Sales alkalmazásból.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 740ae20704abd9c59f64c2c7622fa96d65dccb1d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4453431"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a>Igény szerinti szinkronizálás a(z) Dynamics 365 Supply Chain Management árképzés motorral

[!include [banner](../../includes/banner.md)]



A Microsoft Dynamics 365 Supply Chain Management tartalmaz egy árképzési motort, amely a kereskedelmi megállapodásokat, árlistákat, törzsvásárlói programokat, promóciókat és kedvezményeket kezel. Az árképzési motor összetett szabályokat használ egy adott árajánlat vagy rendelés legjobb árának megállapításához. Kettős írás használata esetén a Dynamics 365 Sales ajánlati és rendelési oldalain a Dynamics 365 Supply Chain Management alkalmazásból származó statikus árképzési vagy árképzési motor használható.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>A Supply Chain Management árképzési motorjának használata a Sales alkalmazásban

1. Az Sales alkalmazásban területen nyissa meg a **Sales \> Rendelések** elemet.
2. Válassza az **Új** lehetőséget egy új rendelés létrehozásához vagy válasszon egy meglévő rendelést a **Saját rendelések** listából.
3. Adjon hozzá egy új rendelési sort.
4. Ha új rendelést hoz létre, akkor a műveleti ablaktáblán válassza a **Rendelés árazása** elemet. Ha egy meglévő rendelést frissít e, akkor a műveleti ablaktáblán válassza az **Újraszámítás** elemet.

    A program automatikusan kitölti a következő mezőket:

    + Részletes összeg
    + Engedmény (%)
    + Engedmény
    + Szállítás előtti összeg
    + Szállítási összeg
    + Adó összesen
    + Teljes összeg
    
5. Annak biztosítására, hogy a rendszer a kereskedelmi és értékesítési szerződéseket figyelembe vegye az ár kiszámításához:
    1. Navigáljon a Supply Chain Management környezetébe.
    2. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
    3. Válassza ki az **Árak** lapot az oldalsó navigációs sávon.
    4. A **Kereskedelmi szerződés értékelése** gyorslapon törölje a **Manuális bejegyzés** beállítás jelölését.

## <a name="how-it-works"></a>Hogyan működik?

Amikor kiválasztja a **Rendelés árazása** lehetőséget a Sales alkalmazásban az **Összeg** funkció az **Értékesítési rendelés \> Nézet** lapon a Supply Chain Management alkalmazásban meg lesz hívva a társított rendelésért.. A rendelés teljes összege az Sales alkalmazásból lesz felhasználva a Supply Chain Management megfelelő mezőinek kitöltéséhez.

Amikor az értékesítési rendelés összesítése a Supply Chain Management alkalmazásban van kiszámítva a számítás a vevőre vonatkozó meglévő kereskedelmi megállapodásokat és értékesítési szerződéseket, valamint az értékesítési rendelésben felsorolt termékeket értékeli. Ezek az adatok lesznek felhasználva a végösszeg számításához. Ha a **Rendelés árazása** van kiválasztva, akkor a Sales automatikusan tükrözi a Supply Chain Management alkalmazásban elvégzett összes beállítást.

## <a name="limitations"></a>Korlátozások

Amikor az Sales mezői ki vannak töltve, a következő korlátozások érvényesek:

+ A Supply Chain Management alkalmazásben végzett költség-és költség-felosztási beállítások nem lesznek másolva a Sales alkalmazásba.
+ Az árképzés nem veszi figyelembe a különleges kiskereskedelmi árazást, ami a Supply Chain Management értékesítési rendelés sora oldalán van meghatározva a **Kiskereskedelmi csatorna** mezőben.
+ A rendszer nem veszi figyelembe a Supply Chain Management **Promóciós engedmény kezelése** részében meghatározott engedményeket.
