---
title: A Dynamics 365 Commerce díjszabási motor használata a Dynamics 365 Sales alkalmazással
description: Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Commerce árképzési motorját értékesítési árajánlatok a Dynamics 365 Sales alkalmazásból.
author: ShalabhjainMSFT
ms.date: 11/19/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c3f1527e5f37bebba57661ca86b1a3aae7e62da0
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416755"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>A Dynamics 365 Commerce díjszabási motor használata a Dynamics 365 Sales alkalmazással

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Commerce árképzési motorját értékesítési árajánlatok a Dynamics 365 Sales alkalmazásból.

Az Dynamics 365 Commerce árképzési motor a legtöbb cég és ügyfél közötti (B2C) árképzési forgatókönyveket támogatja, így például az üzlet szintjének árképzését, a tagságon alapuló és a hűségprogramon alapuló árképzést, a kombinációs engedményeket, a mennyiségi kedvezményeket és a küszöbérték-kedvezményeket. Az árképzési motor összetett szabályokat használ egy adott árajánlat vagy rendelés legjobb árának megállapításához.

Ha [kettős írást](./dual-write-overview.md) használ , akkor három lehetősége van az árképzési szükségletek kielégítésére. Használhatja azt az árképzést, ami a Dynamics 365 Sales árlistáin alapul, a Dynamics 365 Supply Chain Management árképzési motorját vagy a Dynamics 365 Commerce árképzési motorját. Ezek közül a lehetőségek közül a Commerce árképzési motorja a legalkalmasabb a B2C esetekhez.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>A Commerce árképzási motorjának használata a Sales alkalmazásban

> [!NOTE]
> Jelenleg a Commerce árképzési motor csak a árajánlat létrehozásához használható a Salesben. Még nem érhető el az értékesítési rendelés integrációja a Commerce árképzési motorjával.

Amikor a felhasználók árajánlatot kezdeményeznek a Sales alkalmazásban, a kettős írás keretrendszer a Commerce-be másolja az árajánlat adatait. A program átmásolja a meglévő ajánlati sorok vagy az összes újonnan hozzáadott árajánlati sor változását a Commerce rendszerbe. Amikor a felhasználók a Commerce árképzési motort szeretnék az árajánlat áraihoz használni, az árajánlatot az **Árajánlat** lehetőséget választva frissíthetik az árajánlat árait a Commerce árképzési motorja alapján. Az árak automatikusan frissülnek mind a Sales és a Commerce alkalmazásokban is.

## <a name="prerequisites"></a>Előfeltételek

- Ahhoz, hogy a Commerce árképzési motort a Salesben használhassa, el kell végeznie a [Potenciális vevők készpénzre váltása a kettős írás szolgáltatásban](./dual-write-prospect-to-cash.md) lépéseit.
- A következő lépések végrehajtásával ki kell kapcsolni a kereskedelmi megállapodás értékelését kézi bevitelhez:

    1. A Commerce környezetében **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
    1. Az **Árak** lapon a **Kereskedelmi megállapodás értékelése** gyorslapon törölje a **Manuális bevitel** jelölőnégyzet jelölését.

## <a name="additional-resources"></a>További erőforrások

[Potenciális vevők készpénzre váltása kettős írásban](./dual-write-prospect-to-cash.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]