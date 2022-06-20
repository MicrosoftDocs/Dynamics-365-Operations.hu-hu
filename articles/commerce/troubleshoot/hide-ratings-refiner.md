---
title: Ha a minősítések és az áttekintések megoldása nincs engedélyezve, akkor a minősítések finomítója megjelenik a keresési eredményekben és a kategóriaoldalakon
description: Ez a témakör hibaelhárítási Microsoft Dynamics 365 Commerce útmutatást ad arról, hogyan lehet elrejteni a minősítéseket finomítót a keresési eredmények és a kategóriaoldalakon, ha nincs engedélyezve az e-commerce webhelyre vonatkozó minősítési és áttekintési megoldás.
author: gvrmohanreddy
manager: annbe
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c35e176fc5673de194a81a3a4694a83f7bc9aa00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885058"
---
# <a name="ratings-refiner-appears-on-search-results-and-category-pages-when-the-ratings-and-reviews-solution-isnt-enabled"></a>Ha a minősítések és az áttekintések megoldása nincs engedélyezve, akkor a minősítések finomítója megjelenik a keresési eredményekben és a kategóriaoldalakon

[!include [banner](../includes/banner.md)]

Ez a témakör hibaelhárítási Microsoft Dynamics 365 Commerce útmutatást ad arról, hogyan lehet elrejteni a minősítéseket finomítót a keresési eredmények és a kategóriaoldalakon, ha nincs engedélyezve az e-commerce webhelyre vonatkozó minősítési és áttekintési megoldás.

## <a name="description"></a>Leírás

A minősítésfinomító megjelenik a keresési eredményekben és a kategóriaoldalakon azon az e-kereskedelmi webhelyen, amely nem használja a minősítések és értékelések megoldást.

## <a name="resolution"></a>Megoldás

### <a name="enable-the-hide-rating-setting-in-commerce-site-builder"></a>A Minősítési beállítás elrejtése beállítás engedélyezése a Commerce webhelyszerkesztőben

Ha engedélyezni szeretné a **Minősítési beállítás elrejtése** beállítást a Commerce webhelyszerkesztőben, hogy a minősítések finomítója ne legyen látható a keresési eredmények oldalon és a kategóriaoldalakon, kövesse ezeket a lépéseket.

1. Lépjen a **Webhelybeállítások \> Bővítmények** pontra.
1. A **Minősítések és értékelések** alatt jelölje be az **Értékelés elrejtése** jelölőnégyzetet.
1. Válassza a **Mentés és közzététel** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](../ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](../opt-in-ratings-reviews.md)
