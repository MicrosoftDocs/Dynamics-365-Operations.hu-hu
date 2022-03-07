---
title: Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez
description: Ez az eljárás bemutatja a termékéletciklus-állapotnak a kiadott alaptermékhez és annak változataihoz történő hozzáadását.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 217bab38544c2794d2e57410f8c2a979605106b0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567007"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Termékéletciklus-állapot hozzárendelése egy kiadott alaptermékhez

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]