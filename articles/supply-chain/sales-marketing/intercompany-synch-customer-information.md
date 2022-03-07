---
title: Vállalatközi ügyféladatok szinkronizálása
description: Ez a témakör bemutatja a vevőadatok szinkronizálását a vállalatközi rendelésekhez
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
ms.openlocfilehash: c82216c8391f6c447bec74f25cd16b9db18d468d
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548313"
---
# <a name="synchronize-intercompany-customer-information"></a>Vállalatközi ügyféladatok szinkronizálása

[!include [banner](../../includes/banner.md)]

Ha a vevő adatainak, a szállítói hivatkozásnak vagy a vevői igénylés számának a módosítása esetén a **Vevőadatok** mező engedélyezve van, akkor a program szinkronizálja a vevői adatokat.

Ezekben a szinkronizációs mezőkben mindig módosíthatja az értéket. Ezt a paramétert választva azonban csak azt lehet meghatározni, hogy ez az érték más vállalatközi rendelésekre másolva legyen-e. Ha engedélyezte a **Vevőadatok** mezőt a vállalatközi értékesítési rendelésen, akkor a vállalatközi értékesítési rendelésen végzett módosításokat a program automatikusan szinkronizálja a vállalatközi beszerzési rendelésen. Ha a vállalatközi beszerzési rendelésen is engedélyezte a **Vevőadatok** mezőt, akkor a program az eredeti értékesítési rendeléssel is szinkronizálja a módosítást.

> [!NOTE]
> Ha a vállalatközi beszerzési rendelésen és a vállalatközi értékesítési rendelésen is engedélyezte a **Vevő adatai** mezőt, akkor az egyik vállalat egyik alkalmazottja által végzett módosításokat felülbírálhatják a másik vállalat másik alkalmazottja által ugyanazon a rendelésen végzett frissítések.

A legjobb gyakorlat az, ha engedélyezi a **Vevő adatai** mezőt a vállalatközi beszerzési rendelésen. Ez lehetővé teszi a szinkronizálást az eredeti értékesítési rendelés és a vállalatközi beszerzési rendelés között, valamint a vállalatközi beszerzési rendelés és a vállalatközi értékesítési rendelés között.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
