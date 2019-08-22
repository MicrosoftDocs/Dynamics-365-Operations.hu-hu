---
title: Számlaösszegek számlaegyeztetési eltéréseinek feloldása
description: A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek.
author: abruer
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c664f0b66b41b3db8f45b4507bca39e1ffefb599
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834561"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Számlaösszegek számlaegyeztetési eltéréseinek feloldása

[!include [banner](../includes/banner.md)]

A számlaegyeztetés ellenőrzésének egyik módja a számlaösszegek egyeztetése. Ha szeretné beállítani, hogy a rendszer elvégezze a számlaösszegek egyeztetését, a **Kötelezettségek paraméterei** oldalon, a **Számla ellenőrzése** fülön állítsa a **Számlaösszegek egyeztetése** lehetőséget **Igen** értékre. 

A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek. Hat összeget hasonlít össze a rendszer a **Számlaösszegek egyeztetésének részletei** oldalon. Ha az összegek bármelyike eltér a várt vonatkozó beszerzési rendelés összegétől, a rendszer egyeztetési eltérést jelez. 

Az összegek esetében számlaegyeztetési eltérést tartalmazó számla áttekintéséhez kattintson a **Szállítói számla bevitele** munkaterületen a **Függő számlák** lehetőségre. Ezután a Műveleti panelen az **Ellenőrzés** fülön kattintson az **Egyeztetési részletek** lehetőségre. Ha egyeztetési eltérések észlel, figyelmeztető ikon jelenik meg a számlaösszeg mellett. További részleteket is megtekinthet az összegekről, ha megtekinti a számlaösszegek egyeztetési részleteit. 

Az eltérés azonosítása után előfordulhat, hogy fel kell vennie a kapcsolatot a szállítóval, amennyiben úgy véli, hogy a számlán helytelen információ szerepel. A szállítóval folytatott egyeztetés eredményétől függően a következő műveletek bármelyikét elvégezheti:

-   Az áreltérés elfogadása és a számla feladása az egyeztetési eltérésekkel. Lehetséges, hogy a rendszerben jóváhagyás szükséges az egyeztetési eltérések feladása előtt. Ebben az esetben jóvá kell hagynia az egyeztetési eltérést, és opcionálisan meg kell adnia egy jóváhagyási megjegyzést. Ezután kiválaszthatja a számla feladását.
-   A számlaösszeg módosítása a várt összegre és a számla feladása.
-   Teljes jóváírás és új, javított számla kérése a szállítótól.

További tudnivalókért lásd: [Kivételek kivizsgálása/feloldása](tasks/research-resolve-exceptions.md).


