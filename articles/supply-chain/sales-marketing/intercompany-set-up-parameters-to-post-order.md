---
title: Paraméterek beállítása vállalatközi rendelés feladásához
description: Ez a cikk bemutatja a vállalatközi rendelés feladott paramétereinek beállítását.
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
ms.openlocfilehash: 97ea0061d57beede6350eecfd497c12dd37aea31
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900796"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Paraméterek beállítása vállalatközi rendelés feladásához

[!include [banner](../../includes/banner.md)]

Vállalatközi vevői rendelés feladásakor beállítható a vállalatközi beszerzési rendelés és az eredeti vevői rendelési számla automatikus feladása.

> [!NOTE]
> Mielőtt végrehajtja ezt az eljárást, állítsa be a nyomtatáskezelést a szervezetnél, hogy a megfelelő számlanyomtatóra mutasson. Így biztosan a megfelelő nyomtatón lesz kinyomtatva az eredeti értékesítési rendelés számlája.

Ehhez a következő paramétereket kell beállítani:

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra. A munkához használni kívánt értékesítési rendelés kiválasztása.
1. Az értékesítési rendelés munkaablakában válassza a **Fejléc nézetet**, majd nyissa meg a **Vállalatközi beállítások** gyorsablakot a kijelölésével.
1. Ezután az **Értékesítési rendelés** lapon ugorjon a Műveleti panelre, majd válassza a **Szerkesztés** lehetőséget.
1. Menjen vissza a **Vállalatközi beállítások** gyorslapra, és válassza a **Közvetlen kiszállítás** lehetőséget, ha a teljes vállalatközi láncban (az összes rendelésben) engedélyezni szeretné a közvetlen kiszállítást.
1. Az értékesítési rendelés az új beállítással való mentéshez válassza a **Mentés** lehetőséget. Ezután a **Bezárás** lehetőséget választva zárja be az értékesítési rendelést.
1. Ugrás a **Beszerzés és forrás \> Beszállítók \> Minden szállító** pontra. Az **Általános** lapon válassza a **Vállalatközi** lehetőséget.
1. A **Vállalatközi** oldalon jelölje ki a **Beszerzési rendelési irányelvek** hivatkozást. A **Vállalatközi beszerzési rendelés (közvetlen kiszállítás)** mezőcsoportban válassza a **Számla automatikus feladása** lehetőséget, és törölje a jelet a **Számla automatikus nyomtatása** mezőből.
1. Az **Eredeti értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban jelölj be a **Számla automatikus feladása** mezőt, és a **Számla automatikus nyomtatása** mezőt.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
