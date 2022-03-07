---
title: Vállalatközi árak és engedmények szinkronizálása
description: Ez a témakör bemutatja a vállalatközi értékesítési rendelések és beszerzési rendelések árainak és engedményének szinkronizálását
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a9467e8d06a44cfaab9e3c8ea3944675c3eb8fb5
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548299"
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
