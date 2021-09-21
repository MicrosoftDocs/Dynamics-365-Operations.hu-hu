---
title: Ha a minősítések és az áttekintések megoldása nincs engedélyezve, akkor a minősítések finomítója megjelenik a keresési eredményekben és a kategóriaoldalakon
description: Ez a témakör hibaelhárítási útmutatást ad arról, hogyan lehet elrejteni a minősítésfinomítót a keresési eredmények és a kategóriaoldalakon, ha egy e-kereskedelmi webhely esetében nincs engedélyezve a Microsoft Dynamics 365 Commerce minősítések és áttekintések megoldás.
author: gvrmohanreddy
manager: annbe
ms.date: 09/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f3438d12f4ffd06b07cbef724cda8fa490a5f4eb
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472623"
---
# <a name="ratings-refiner-appears-on-search-results-and-category-pages-when-the-ratings-and-reviews-solution-isnt-enabled"></a>Ha a minősítések és az áttekintések megoldása nincs engedélyezve, akkor a minősítések finomítója megjelenik a keresési eredményekben és a kategóriaoldalakon

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör hibaelhárítási útmutatást ad arról, hogyan lehet elrejteni a minősítésfinomítót a keresési eredmények és a kategóriaoldalakon, ha egy e-kereskedelmi webhely esetében nincs engedélyezve a Microsoft Dynamics 365 Commerce minősítések és áttekintések megoldás.

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
