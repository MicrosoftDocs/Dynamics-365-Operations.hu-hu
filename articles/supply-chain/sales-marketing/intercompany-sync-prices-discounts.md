---
title: Vállalatközi árak és engedmények szinkronizálása
description: Ez a cikk bemutatja a vállalatközi értékesítési rendelések és beszerzési rendelések árainak és engedményének szinkronizálását.
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
ms.openlocfilehash: 64130c400212a819f931cc36459667e4d7c83f32
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905689"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>Vállalatközi árak és engedmények szinkronizálása

[!include [banner](../../includes/banner.md)]

A rendszer mindig szinkronizálja az engedményeket és az árakat a vállalatközi értékesítési rendelések és a vállalatközi beszerzési rendelések között. Az árak és az engedmények szinkronizálhatók az eredeti értékesítés rendelésbe (vagy onnan) történjen, hogy az összes rendelésben ugyanazok az árak és engedmények szerepeljenek. Ezt a **Vállalatközi** oldalon teheti meg, amely az **Általános** lapon az **Összes ügyfél** listaoldalon az **Értékesítés és marketing** vagy a **Beszerzés és forrás** lapról.

Az **Ár és kedvezmény** mezőt a rendszer a vállalatközi értékesítésirendelés-sorral szinkronizálja. Ez azt jelenti, hogy az **Ár szerkesztésének engedélyezése** és a **Kedvezmény szerkesztésének engedélyezése** mező választásával engedélyezi, hogy a vállalatközi értékesítési és a vállalatközi beszerzési rendelés között módosítások történjenek. A vállalatközi értékesítési rendelésben szereplő egységárnak, áregységnek vagy az értékesítés költségeinek a változása határozza meg a vállalatközi beszerzésirendelés-sorban szereplő árat.

Ha a vállalatközi értékesítési rendelésen vagy a vállalatközi beszerzési rendelésen engedélyezve van az **Ár szerkesztésének engedélyezése** és a **Kedvezmény szerkesztésének engedélyezése** mező, bármelyik rendelésen kézzel módosíthatja az árat vagy az engedményt. Ellenkező esetben nem.

Ha a vállalatközi értékesítési rendelésen vagy a vállalatközi értékesítési rendelésen nincs engedélyezve az **Ár szerkesztésének engedélyezése** és a **Kedvezmény szerkesztésének engedélyezése** mező, nem végezhet manuális módosításokat az ár (vagy díjak) vagy kedvezmény tekintetében egy vállalatközi értékesítési rendelésen.

Ha a vállalatközi értékesítési rendelésen vagy a vállalatközi beszerzési rendelésen nincs engedélyezve az **Ár szerkesztésének engedélyezése** és a **Kedvezmény szerkesztésének engedélyezése** mező, nem végezhet manuális módosításokat az ár (vagy díjak) vagy kedvezmény tekintetében egy vállalatközi beszerzési rendelésen.

Ha a vállalatközi értékesítési rendelésen és a vállalatközi beszerzési rendelésen is engedélyezve van az **Ár szerkesztésének engedélyezése** és a **Kedvezmény szerkesztésének engedélyezése** mező, mindkét rendelésen végezhet manuális módosításokat. Ez azonban olyan helyzetet okozhat, amikor az egyik személy által készített frissítéseket felülbírálják azok a frissítéseket, amelyek egy másik vállalat másik személye által ugyanazon a rendelésen végzett.

> [!NOTE]
> Ha az **Ár és kedvezmény** mezőt a vállalatközi beszerzési rendelésen és a vállalatközi értékesítési rendelésen is engedélyezte, akkor elveszti a felügyeletet az árképzés felett.

Az ilyen ütközések elkerülése érdekében vagy csak a vállalatközi értékesítési rendelésen, vagy csak a vállalatközi beszerzési rendelésen érdemes engedélyezni az árak és engedmények módosítását. Ehhez engedélyezni kell az **Ár szerkesztésének engedélyezése** és a **Kedvezmény szerkesztésének** engedélyezése mezőket is valamelyik rendelésen.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
