---
title: Vállalatközi költségek szinkronizálása
description: Ez a cikk bemutatja a vállalatközi költségek szinkronizálását.
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
ms.openlocfilehash: e7b3de3d7da7be6c1c8b5c3842862e7bccd78277
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857286"
---
# <a name="synchronize-intercompany-charges"></a>Vállalatközi költségek szinkronizálása

[!include [banner](../../includes/banner.md)]

A költségek csak a vállalatközi értékesítési rendelés és a vállalatközi beszerzési rendelés között szinkronizáltak, és ez a szinkronizálás mindig megtörténik.

Ha a vállalatközi beszerzési vagy értékesítési rendelésen be van jelölve az **Árszerkesztés engedélyezése** jelölőnégyzet, akkor kézzel is megadhatja a rendelések vegyes költségeit. Ellenkező esetben nem.

Ha az **Árszerkesztés engedélyezése** mező nincs bejelölve a vállalatközi értékesítési rendelésen, akkor nem tud manuálisan vegyes költségeket rögzíteni a vállalatközi értékesítési rendelésben.

Ha az **Árszerkesztés engedélyezése** mező nincs bejelölve a vállalatközi beszerzési rendelésen, akkor nem tud manuálisan vegyes költségeket rögzíteni a vállalatközi beszerzési rendelésben.

Ha az **Árszerkesztés engedélyezése** engedélyezve a vállalatközi beszerzési rendelésen és a vállalatközi értékesítési rendelésen is, akkor tud manuálisan vegyes költségeket rögzíteni mindkét rendelésen. Emiatt előfordulhat azonban, hogy sok költség helytelenül lesz hozzáadva.

Az ilyen ütközések elkerülésére a legjobb módszer az, hogy vagy csak a vállalatközi értékesítési rendelésen, vagy csak a vállalatközi beszerzési rendelésen engedélyezi a vegyes költségek hozzáadását.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
