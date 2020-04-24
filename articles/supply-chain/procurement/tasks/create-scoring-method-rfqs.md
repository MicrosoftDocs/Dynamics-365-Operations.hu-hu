---
title: Pontozási mód létrehozása az ajánlatkérésekhez
description: Ez az eljárás bemutatja, hogyan lehet pontozási módszert létrehozni.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd8657098519391ee488025e175e1499c58a55ce
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204654"
---
# <a name="create-a-scoring-method-for-rfqs"></a>Pontozási mód létrehozása az ajánlatkérésekhez

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet pontozási módszert létrehozni. A pontozási módszer olyan feltételek együttesét jelenti, amelyek alapján összehasonlíthatóak az ajánlatkérésre válaszként érkezett ajánlatok. Minősítheti például a szállítókat múltbeli teljesítményük, vállalatuk környezetbarát jellege, megfelelő együttműködő készségük alapján, vagy összehasonlíthatja az ajánlatokon szereplő árakat. A pontozási módszer társítható egy meghirdetési típussal; ekkor az adott típusú ajánlatkérések alapértelmezett pontozási módszere a kiválasztott módszer lesz. Ezeket a feladatokat jellemzően egy beszerzési vezető végezné el. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.

1. Navigáljon a következő helyre: Beszerzés és forrás > Beállítás > Ajánlatkérés > Pontozás típusa.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson a Mentés gombra.
6. Kattintson az Új lehetőségre.
7. Írjon be egy értéket a Név mezőbe.
8. A Leírás mezőben adjon meg egy értéket.
    * Ez a leírás a pontozási módszer nevével együtt jelenik meg, amennyiben kiválaszt egy pontozási módszert egy ajánlatkéréshez.  
9. Írjon be egy számot a Kezdő érték mezőbe.
    * A tartomány meghatározza, hogy a beszerzési szakember mely határértékek között adhat pontszámot. Amennyiben egy ajánlatkérést több pontozási feltétel szerint értékelnek, a bevitt pontértékek összeadódnak, és az ajánlatok a kapott összeg alapján hasonlíthatóak össze.  
10. Írjon be egy számot a Záró érték mezőbe.
11. Kattintson az Új lehetőségre.
12. Írjon be egy értéket a Név mezőbe.
13. A Leírás mezőben adjon meg egy értéket.
14. Írjon be egy számot a Kezdő érték mezőbe.
15. Írjon be egy számot a Záró érték mezőbe.

