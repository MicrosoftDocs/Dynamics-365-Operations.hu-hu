---
title: Gyorsnézeti modul
description: Ez a témakör a gyorsnézeti modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 24b3a5552a83bfea52f6a274b836955e41acdb4281f7b7807acf040e9cd4af30
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777476"
---
# <a name="quick-view-module"></a>Modul gyors megtekintése

[!include [banner](includes/banner.md)]

Ez a témakör a gyorsnézeti modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A gyorsnézeti modul segítségével a felhasználók gyorsan megtekinthetik a termékinformációkat, amikor a termékeket egy listaoldalon böngészik, és egy vagy több terméket adnak a kosárhoz a listaoldalról anélkül, hogy a termék részleteit tartalmazó oldalra (PDP) kellene lépniük. A gyorsnézeti modul áttekintést nyújt a felhasználók által a „hozzáadás a kosárhoz” döntés meghozatalához szükséges termékinformációkról. A PDP-re mutató hivatkozást is tartalmaz, így a felhasználók további termékrészleteket és vásárlási lehetőségeket tekinthetnek meg.

A gyorsnézeti modult a [termékgyűjtési](product-collection-module-overview.md) és a [keresési eredmények](search-result-module.md) modul támogatja.

> [!IMPORTANT]
> A gyorsnézeti modul a Commerce 10.0.17-es verziójának kiadásaként érhető el.

A következő ábra bemutat egy példát egy gyorsnézeti modulról egy terméklistaoldalon.

![Példa gyorsnézeti modulra egy terméklistaoldalon.](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a>Modul tulajdonságai

A gyorsnézeti modul ugyanazokat a funkciókat támogatja, mint a vásárlásmező modul. Ezért a gyorsnézeti modul tulajdonságai hasonlítanak a vásárlásmező modul tulajdonságaira.

| Tulajdonság | Értékek | Leírás |
|----------------|--------|-------------|
| Címsor címkéje | **H1**, **H2**, **H3**, **H4**, **H5** vagy **H6** | Ez a tulajdonság határozza meg a termék címének címsorcímkéjét. Ha a gyornézeti modul a lap felső részén van, a tulajdonságot a **H1** értékre kell állítania a hozzáférhetőségi szabványok teljesítése érdekében. |
| Egyéni ár engedélyezése | **Igaz** vagy **Hamis** | Ha a tulajdonság értéke **Igaz**, a felhasználó egyéni árat adhat meg. |
| Minimális ár | Egész | Ez a tulajdonság csak akkor alkalmazható, ha az **Egyéni ár engedélyezése** tulajdonság értéke **Igaz**. Meghatározza a felhasználó által beírható minimális árat (például 1 dollár). |
| Maximális ár | Egész | Ez a tulajdonság csak akkor alkalmazható, ha az **Egyéni ár engedélyezése** tulajdonság értéke **Igaz**. Meghatározza a felhasználó által beírható maximális árat (például 1000 dollár). |

## <a name="commerce-site-builder-settings"></a>Commerce webhelykészítő beállításai

A vásárlásmező modulhoz hasonlóan a gyorsnézeti modul is tiszteletben tartja a **Webhelybeállítások \> Bővítmények \> Termék hozzáadása a kosárhoz** beállításait. Azonban a **Navigálás a kosárhoz oldal** beállítást figyelmen kívül hagyja, mivel az nem egyeztethető össze a gyorsnézeti modul céljával, amely lehetővé teszi a felhasználók számára, hogy több terméket böngésszenek egy listoldalon, és a listaoldal elhagyása nélkül hozzáadják őket a kosárhoz.

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a>Gyornézeti modul hozzáadása termékgyűjtési modulhoz

A gyorsnézeti modult hozzáadhatja a termékgyűjtési és a keresési eredmények modulhoz.

A gyorsnézeti modulnak a termékgyűjtési modulhoz való hozzáadásához a a Commerce webhelykészítő felületén hajtsa végre az alábbi lépéseket.

1. Nyissa meg az **Oldalak** lehetőséget, majd válassza ki a Fabrikam webhely kezdőlapját.
1. Lépjen a kezdőlap bármelyik **Termékgyűjtemény** moduljára, jelölje ki a három pontot (**...**), majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Gyorsnézet** modult, majd kattintson az **OK** gombra.
1. A **Gyorsnézet** modul tulajdonságok paneljében válassza a **Címsor** lehetőséget. A **Címsor** párbeszédpanelen állítsa a **Címsor szintje** mezőt **H2** értékre, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Termékgyűjtési modul](product-collection-module-overview.md)

[Keresési eredmények modul](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
