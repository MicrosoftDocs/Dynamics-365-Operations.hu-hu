---
title: A Dynamics 365 Commerce díjszabási motor használata a Dynamics 365 Sales alkalmazással
description: Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Commerce árképzési motorját értékesítési árajánlatok a Dynamics 365 Sales alkalmazásból.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: shajain
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-11-03
ms.openlocfilehash: cd784bb37eddfc74699d1070eab453a3b527201a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560273"
---
# <a name="use-the-dynamics-365-commerce-pricing-engine-with-dynamics-365-sales"></a>A Dynamics 365 Commerce díjszabási motor használata a Dynamics 365 Sales alkalmazással

[!include [banner](../../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kell használni a Microsoft Dynamics 365 Commerce árképzési motorját értékesítési árajánlatok a Dynamics 365 Sales alkalmazásból.

Az Dynamics 365 Commerce árképzési motor a legtöbb cég és ügyfél közötti (B2C) árképzési forgatókönyveket támogatja, így például az üzlet szintjének árképzését, a tagságon alapuló és a hűségprogramon alapuló árképzést, a kombinációs engedményeket, a mennyiségi kedvezményeket és a küszöbérték-kedvezményeket. Az árképzési motor összetett szabályokat használ egy adott árajánlat vagy rendelés legjobb árának megállapításához.

Ha [kettős írást](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) használ , akkor három lehetősége van az árképzési szükségletek kielégítésére. Használhatja azt az árképzést, ami a Dynamics 365 Sales árlistáin alapul, a Dynamics 365 Supply Chain Management árképzési motorját vagy a Dynamics 365 Commerce árképzési motorját. Ezek közül a lehetőségek közül a Commerce árképzési motorja a legalkalmasabb a B2C esetekhez.

## <a name="use-the-commerce-pricing-engine-in-sales"></a>A Commerce árképzási motorjának használata a Sales alkalmazásban

> [!NOTE]
> Jelenleg a Commerce árképzési motor csak a árajánlat létrehozásához használható a Salesben. Még nem érhető el az értékesítési rendelés integrációja a Commerce árképzési motorjával.

Amikor a felhasználók árajánlatot kezdeményeznek a Sales alkalmazásban, a kettős írás keretrendszer a Commerce-be másolja az árajánlat adatait. A program átmásolja a meglévő ajánlati sorok vagy az összes újonnan hozzáadott árajánlati sor változását a Commerce rendszerbe. Amikor a felhasználók a Commerce árképzési motort szeretnék az árajánlat áraihoz használni, az árajánlatot az **Árajánlat** lehetőséget választva frissíthetik az árajánlat árait a Commerce árképzési motorja alapján. Az árak automatikusan frissülnek mind a Sales és a Commerce alkalmazásokban is.

## <a name="prerequisites"></a>Előfeltételek

- Ahhoz, hogy a Commerce árképzési motort a Salesben használhassa, el kell végeznie a [Potenciális vevők készpénzre váltása a kettős írás szolgáltatásban](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/) lépéseit.
- A következő lépések végrehajtásával ki kell kapcsolni a kereskedelmi megállapodás értékelését kézi bevitelhez:

    1. A Commerce környezetében **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
    1. Az **Árak** lapon a **Kereskedelmi megállapodás értékelése** gyorslapon törölje a **Manuális bevitel** jelölőnégyzet jelölését.

## <a name="additional-resources"></a>További erőforrások

[Potenciális vevők készpénzre váltása kettős írásban](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-prospect-to-cash/)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]