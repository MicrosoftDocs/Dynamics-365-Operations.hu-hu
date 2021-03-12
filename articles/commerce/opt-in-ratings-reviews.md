---
title: A minősítések és ellenőrzések használatának kiválasztása
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 481a8750b2333d5dd5de2c05e175569804a6046f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985836"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>A minősítések és ellenőrzések használatának kiválasztása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyen beleegyezni az értékelések és vélemények használatába.

## <a name="overview"></a>Áttekintés

Az értékelések és a vélemények megoldása egy omnicsatornás megoldás, amelyet a Dynamics 365 Commerce megoldásban a Microsoft Dynamics Lifecycle Services (LCS) segítségével tehet elérhetővé. Az LCS egy olyan felügyeleti portál, amelyet a kiskereskedők a környezeteik kezelésére használhatnak a telepítéstől egészen a megszüntetésig.

Ha azt szeretné, hogy a minősítési és értékelési megoldást használhassa a Commerce webhelyén, akkor az e-Commerce webhely telepítését követően fel kell iratkoznia a minősítésekre és ellenőrzésekre a Dynamics 365 Commerce alkalmazásban.

## <a name="opt-in-to-use-ratings-and-reviews"></a>A minősítések és ellenőrzések használatának bekapcsolása

A következő lépések végrehajtásával választhatja ki azt, hogy használni szeretné az értékelések és vélemények funkciót.

1. Kövesse az [Új e-commerce webhely telepítése](deploy-ecommerce-site.md) szakasz lépéseit.
1. Amikor még az LCS-ben van nyissa meg a **Retail-telepítés beállítása \> Egyéb beállítások** lehetőséget.
1. Állítsa be az **Értékelések és vélemények szolgáltatás engedélyezése** értékét **Igen** beállításra.
1. Az **AAD biztonsági csoport értékelések és vélemények moderátora (biztonsági csoport-objektumazonosító)** mezőbe írja be annak a Microsoft Azure Active Directory (Azure AD) biztonsági csoportnak az azonosítóját, amely tartalmazza az értékelések és vélemények moderátorait.

    ![A minősítések és ellenőrzések használatának bekapcsolása](media/LCS_RnR_Preference.png)

1. Az e-commerce inicializálási folyamat végrehajtása.

> [!NOTE] 
> Ha olyan meglévő Dynamics 365 Commerce ügyfél, aki már telepített e-Commerce webhelyet anélkül, hogy feliratkozott volna a minősítések és értékelések funkcióra, és most használni kívánja a minősítések és értékelések funkciót a Dynamics 365 Commerce csomagból, akkor küldjön egy szolgáltatáskérelmet. A szolgáltatáskérelem elküldésével kapcsolatos további tudnivalókat lásd: [Szolgáltatáskérelem küldésének folyamata](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce](sync-product-ratings.md)


