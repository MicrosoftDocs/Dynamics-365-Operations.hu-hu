--- 
title: "Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez"
description: "Ez az eljárás bemutatja a termékéletciklus-állapotnak a kiadott alaptermékhez és annak változataihoz történő hozzáadását."
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d445ea2f2362f146a1e3e7bcf747898dc2cc89ba
ms.openlocfilehash: f476c1b2585ce0b5b67cd0d91684c86f7d3bda36
ms.contentlocale: hu-hu
ms.lasthandoff: 02/08/2018

---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja a termékéletciklus-állapotnak a kiadott alaptermékhez és annak változataihoz történő hozzáadását. Előfeltétel: Először le kell játszania az „Új termékéletciklus-állapot létrehozása” feladat-útmutatót, hogy megbizonyosodjon arról, hogy legalább egy termékéletciklus-állapotot létrehozott a jelen feladat-útmutató lejátszása előtt.


## <a name="find-a-released-product-master"></a>Keressen meg egy kiadott alapterméket
1. Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.

> [!NOTE]
> Az alaptermék az Alaptermék termékaltípussal rendelkezik.  

## <a name="update-the-lifecycle-state"></a>Az életciklus-állapot frissítése
1. Kattintson a Szerkesztés lehetőségre.
2. A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.
3. Kattintson a Mentés gombra.
4. Kattintson az Igen gombra.

> [!NOTE]
> Ha az Igen van bejelölve, minden kapcsolódó azon kiadott termékváltozat, amelyek eredeti állapota megegyezik a kiadott alaptermékével, ugyancsak frissül az új termékélettartam-állapotra. Ha a Nem van bejelölve, minden változat megőrzi az aktuális állapotát. A kiadott alapterméktől eltérő termékéletciklus-állapottal rendelkező változatokat a rendszer nem frissíti.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>A változatok életciklus-állapotának ellenőrzése
1. Kattintson a Kiadott termékváltozatok lehetőségre.

> [!NOTE]
> Vegye figyelembe, hogy minden változat esetében öröklődik a kiadott alaptermék kiválasztott életciklus-állapota.  

2. A listában jelölje meg a kiválasztott sort.
3. A Termékéletciklus állapota mezőben adjon meg vagy válasszon ki egy értéket.


