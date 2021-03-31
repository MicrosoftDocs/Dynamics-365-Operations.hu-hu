---
title: Számlaösszegek számlaegyeztetési eltéréseinek feloldása – áttekintés
description: A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0635f388dba16a1e4374f0915fbab5b88c3b76ab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227450"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a>Számlaösszegek számlaegyeztetési eltéréseinek feloldása – áttekintés

[!include [banner](../includes/banner.md)]

A számlaegyeztetés ellenőrzésének egyik módja a számlaösszegek egyeztetése. Ha szeretné beállítani, hogy a rendszer elvégezze a számlaösszegek egyeztetését, a **Kötelezettségek paraméterei** oldalon, a **Számla ellenőrzése** fülön állítsa a **Számlaösszegek egyeztetése** lehetőséget **Igen** értékre. 

A számlaösszegek egyeztetése annak biztosításában nyújt segítséget, hogy a számlák végösszegei és a várható összegek egy elfogadható eltérésnél nagyobb mértékben ne különbözzenek. Hat összeget hasonlít össze a rendszer a **Számlaösszegek egyeztetésének részletei** oldalon. Ha az összegek bármelyike eltér a várt vonatkozó beszerzési rendelés összegétől, a rendszer egyeztetési eltérést jelez. 

Az összegek esetében számlaegyeztetési eltérést tartalmazó számla áttekintéséhez kattintson a **Szállítói számla bevitele** munkaterületen a **Függő számlák** lehetőségre. Ezután a Műveleti panelen az **Ellenőrzés** fülön kattintson az **Egyeztetési részletek** lehetőségre. Ha egyeztetési eltérések észlel, figyelmeztető ikon jelenik meg a számlaösszeg mellett. További részleteket is megtekinthet az összegekről, ha megtekinti a számlaösszegek egyeztetési részleteit. 

Az eltérés azonosítása után előfordulhat, hogy fel kell vennie a kapcsolatot a szállítóval, amennyiben úgy véli, hogy a számlán helytelen információ szerepel. A szállítóval folytatott egyeztetés eredményétől függően a következő műveletek bármelyikét elvégezheti:

-   Az áreltérés elfogadása és a számla feladása az egyeztetési eltérésekkel. Lehetséges, hogy a rendszerben jóváhagyás szükséges az egyeztetési eltérések feladása előtt. Ebben az esetben jóvá kell hagynia az egyeztetési eltérést, és opcionálisan meg kell adnia egy jóváhagyási megjegyzést. Ezután kiválaszthatja a számla feladását.
-   A számlaösszeg módosítása a várt összegre és a számla feladása.
-   Teljes jóváírás és új, javított számla kérése a szállítótól.

További tudnivalókért lásd: [Kivételek kivizsgálása/feloldása](tasks/research-resolve-exceptions.md).




[!INCLUDE[footer-include](../../includes/footer-banner.md)]