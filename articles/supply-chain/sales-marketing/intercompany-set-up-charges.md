---
title: Vállalatközi rendelések költségeinek beállítása
description: Ez a témakör ismerteti vállalatközi rendelések költségeinek beállítását
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3786df5ce185fa8433d7c69bed5bef09b4983b8b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548314"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Vállalatközi rendelések költségeinek beállítása

[!include [banner](../../includes/banner.md)]

A vállalatközi rendelésekhez beállíthat hozzáadandó költségeket. Ha egy vállalatközi értékesítési rendeléshez költség kerül hozzáadásra, a program automatikusan szinkronizálja a vállalatközi beszerzési rendelést. Ez visszafelé is működik – a vállalatközi értékesítési rendelés szinkronizálásra kerül a beszerzési rendeléssel, és fordítva.

A költségeket arra is fel lehet használni, hogy nyereséget számítson fel a vállalatközi értékesítési rendelésekre oly módon, hogy vállalatközi százalékként definiálja a költséget.

Ha a vállalatközi rendelésekhez alkalmazandó költséget állít be, engedélyezi egy vállalatközi értékesítési rendeléshez tartozó belső nyereség kiszámítását az eredeti értékesítési rendelés nettó összegéből. Erre akkor lehet szüksége, ha vállalatközi szállítója önköltségi áron ad el Önnek. A következő eljárás bemutatja, hogyan valósítható meg ez vállalatközi vevőkkel. Ugyanezt az eljárást használhatja a szállítók esetén.

1. Ugorjon a **Kinnlevőségek \> Beállítások \> Költségek \> Vevői költségcsoportok** pontra.
1. Költségcsoport létrehozása.
1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget. Vevői számla hivatkozásának kiválasztása. A Műveleti panelen válassza ki a **Vevő** lapot, majd válassza ki az **Értékesítési rendelés** gyorslapot.
1. Válassza a **Szerkesztés** elemet a műveleti ablaktáblán a mezők módosításának engedélyezéséhez. A **Költségcsoport** mezőben válassza ki a 2. lépésben létrehozott vállalatközi költségcsoportot.
1. Ugorjon a **Kinnlevőségek \> Beállítások \> Költségek \> Automatikus költségek** pontra.
1. A megfelelő mezők kitöltésével állítsa be a költségeket.
1. Az **Ügyfélkapcsolat** mezőben válassza ki a 2. lépésben létrehozott vállalatközi költségcsoportot.
1. A **Sorok** gyorslap **Kategória** mezőjében válassza ki a **Vállalatközi százalék** értékét.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]