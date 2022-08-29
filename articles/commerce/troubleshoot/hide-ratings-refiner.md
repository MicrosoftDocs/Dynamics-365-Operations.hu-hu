---
title: Ha a minősítések és az áttekintések megoldása nincs engedélyezve, akkor a minősítések finomítója megjelenik a keresési eredményekben és a kategóriaoldalakon
description: Ez a témakör hibaelhárítási Microsoft Dynamics 365 Commerce útmutatást ad arról, hogyan lehet elrejteni a minősítéseket finomítót a keresési eredmények és a kategóriaoldalakon, ha nincs engedélyezve az e-commerce webhelyre vonatkozó minősítési és áttekintési megoldás.
author: gvrmohanreddy
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
manager: annbe
ms.openlocfilehash: 28a3cefd6aab81f5e7907bda457763f2306e5a1d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267377"
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
