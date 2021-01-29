---
title: Bizonyos termékéletciklus-állapotokkal rendelkező termékek kizárása
description: Ez a témakör azt mutatja be, hogyan lehet kizárni a termékeket az életciklus-állapotuk alapján a Tervezési optimalizálás funkció használatakor.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 371d98eefa482fc3e430f2f0977ddffb9dd0d30e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645092"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>Bizonyos termékéletciklus-állapotokkal rendelkező termékek kizárása

[!include [banner](../../includes/banner.md)]

A kiadott termékek és a kiadott verziók tartalmazzák a **Termékéletciklus-állapot** mezőt. Ez a mező lehetővé teszi többek között az alaptervezés során figyelembe veendő termékek szabályozását. Az életciklus-állapotokat a **Termékinformáció-kezelés \> Beállítása \> Termékéletciklus-állapot** részre lépve lehet hozzáadni, eltávolítani és szerkeszteni. Állítsa az **Aktív a tervezéshez** beállítást minden egyes termékéletciklus-állapot esetében *Igen* értékre, ha az alaptervezés során figyelembe kell venni az ilyen állapotú termékeket. Ha a beállítás értéke *Nem*, akkor a program kizárja a társított termékeket és változatokat az alaptervezésből és minden számításból az anyagjegyzék szintjén.

Azokat a kiadott termékek és változatok, amelyeknél a **Termékéletciklus-állapot** mező üresen marad, úgy kell tekinteni, mintha olyan termékéletciklus-állapottal rendelkeznének, ahol az **Aktív a tervezéshez** beállítás a *Igen* értékre van állítva. Más szóval ezek az alaptervezés során szerepelni fognak.

> [!NOTE]
> A szükségtelen ellátási javaslatok elkerüléséhez kifejezetten ajánljuk, hogy az összes elavult kiadású terméket és változatot olyan termékéletciklus-állapottal társítsa, ahol az **Aktív a tervezéshez** beállítás esetében a *Nem* érték van beállítva. Ez a megközelítés különösen akkor fontos, ha olyan termékkonfiguráció-változatokkal dolgozik, amelyek nem használhatók fel újra, mert ez segít elkerülni a hulladékot.

## <a name="related-resources"></a>Kapcsolódó erőforrások

A termékéletciklus-állapotokkal kapcsolatos további tudnivalókat lásd: [Termékéletciklus-állapotok áttekintése](../../pim/product-lifecycle.md).

Részletes információkért arról, hogyan lehet a termékéletciklus-állapotokat termékek kizárására használni az alaptervezésből és az anyagjegyzékszint-számításból, lásd: [Termékéletciklus-állapot létrehozása termékek kizárására az alaptervezésből](../../pim/tasks/exclude-products-master-planning.md).