---
title: A minősítések és ellenőrzések használatának kiválasztása
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697980"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>A minősítések és ellenőrzések használatának kiválasztása

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.

## <a name="overview"></a>Áttekintés

Az értékelések és a vélemények megoldása egy többcsatornás megoldás, amelyet a Dynamics 365 Commerce megoldásban a Microsoft Dynamics Lifecycle Services (LCS) segítségével tehet elérhetővé. Az LCS egy olyan felügyeleti portál, amelyet a kiskereskedők a környezeteik kezelésére használhatnak a telepítéstől egészen a megszüntetésig.

Ha azt szeretné, használni az értékelések és vélemények megoldást használhassa a kereskedelmi webhelyén, először el kell fogadnia azt.

## <a name="opt-in-to-use-ratings-and-reviews"></a>A minősítések és ellenőrzések használatának kiválasztása

A következő lépések végrehajtásával választhatja ki azt, hogy használni szeretné az értékelések és vélemények funkciót.

1. Kövesse az [Új e-commerce webhely telepítése](deploy-ecommerce-site.md) szakasz lépéseit.
1. Amikor még az LCS-ben van nyissa meg a **Retail-telepítés beállítása \> Egyéb beállítások** lehetőséget.
1. Állítsa be az **Értékelések és vélemények szolgáltatás engedélyezése** értékét **Igen** beállításra.
1. Az **AAD biztonsági csoport értékelések és vélemények moderátora (biztonsági csoport-objektumazonosító)** mezőbe írja be annak a Microsoft Azure Active Directory (Azure AD) biztonsági csoportnak az azonosítóját, amely tartalmazza az értékelések és vélemények moderátorait.

    ![A minősítések és ellenőrzések használatának kiválasztása](media/LCS_RnR_Preference.png)

1. Az e-commerce inicializálási folyamat végrehajtása.

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Retail](sync-product-ratings.md)
