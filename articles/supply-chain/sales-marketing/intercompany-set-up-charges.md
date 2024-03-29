---
title: Vállalatközi rendelések költségeinek beállítása
description: Ez a cikk bemutatja a költségek vállalatközi rendeléseken való beállítását.
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7b84c0bac6c31139170a99afc65cd08d70bd018e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885841"
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
