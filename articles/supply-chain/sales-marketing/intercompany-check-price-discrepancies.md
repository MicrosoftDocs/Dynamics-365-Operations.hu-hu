---
title: Vállalatközi rendelések áreltéréseinek ellenőrzése
description: Ez a cikk bemutatja a vállalatközi rendelési áreltéréseket
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ca27e86545ba8179c595e55487dbbf49cd9ec528
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890683"
---
# <a name="check-intercompany-order-price-discrepancies"></a>Vállalatközi rendelések áreltéréseinek ellenőrzése

[!include [banner](../../includes/banner.md)]

Az alábbi eljárással ellenőrizhető, hogy előfordul-e áreltérés vállalatközi rendelésekben.

1. Ugotjon a **Beszerzés és forrás \> Időszakos \> Tisztítás \> Vállalatközi rendelések áreltéréseinek ellenőrzése**.
1. Ha szükséges, állítson be egy kötegelt feladatot, majd válassza az **OK** lehetőséget a vállalatközi értékesítési és beszerzési rendelések árainak és kedvezményeinek ellenőrzéséhez. Ha ellenőrzés nélkül szeretné bezárni az oldalt, válassza a **Mégse** lehetőséget.

    > [!TIP]
    > Az esetleges szinkronizálási vagy árakkal kapcsolatos problémák megjelennek egy információs üzenetben. A tájékoztató üzenetet kinyomtatható későbbi használatra.

1. A tájékoztató üzenetben válassza ki a megfelelő sort a rendelés megnyitásához az aktuális jogi személyben. Nyissa meg a rendelést a kapcsolódó jogi személyben a **Vállalatközi** kiválasztásával, majd a **Vállalatközi beszerzési rendelés** vagy **Vállalatközi értékesítési rendelés** kiválasztásával.

    > [!NOTE]
    > A vállalatközi rendelés frissítésének engedélyezése:
    >
    > 1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
    > 1. A Műveleti ablaktáblán válassza az **Általános** lapot, majd válassza a **Vállalatközi** menüpontot.
    > 1. A **Vállalatközi** lapon válassza ki a **Beszerzési rendelés irányelvei** vagy az **Értékesítési rendelés irányelvei** lehetőséget.
    > 1. Mindkét területen válassza az **Ár szerkesztésének engedélyezése** és az **Engedmény szerkesztésének engedélyezése** lehetőséget.

1. Nyissa meg azt a vállalatközi rendelést, amelynél tartani szeretné az árat.
1. Valamennyi rendeléssornál módosítsa a kapcsolódó **Egységár** mező értékét, majd állítsa vissza az eredeti értéket. Módosítsa, majd állítsa vissza a sorhoz tartozó **Kedvezmény** mező értékét, és módosítsa, majd állítsa vissza a **Beszerzések díjai** vagy az **Értékesítések díjai** értékét. Az értékek módosítása, majd visszaállítása révén a rendszer szinkronizálja az aktuális vállalatközi rendeléssor árait, engedményeit és vegyes költségeit a hivatkozott vállalatközi rendeléssorral, így azok automatikusan össze lesznek hangolva.

    > [!NOTE]
    > Ez a szinkronizálás csak akkor hajtható végre, ha még nem készült számla a vállalatközi értékesítési rendelésről. Ha a vállalatközi értékesítési rendelés számlája már fel lett adva, és már elkészült a vevői számlanapló, akkor az árakat, az engedményeket és a vegyes költségeket közvetlenül a vállalatközi beszerzési rendelés sorain kell a vállalatközi vevői számlanaplóban szereplő értékekre módosítani. Ha nem hajtja végre ezt, akkor a vállalatközi beszerzési rendelés számláját nem lehet feladni, mert a rendelések végösszegei eltérőek.

1. A művelet ismétlésével végezze el az összes vállalatközi beszerzési és értékesítési rendelés szinkronizálását.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
