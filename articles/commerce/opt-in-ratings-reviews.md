---
title: A minősítések és értékelések használatának bekapcsolása
description: Ez a cikk bemutatja, hogyan lehet a webhelyen értékeléseket és értékeléseket Microsoft Dynamics 365 Commerce használni.
author: gvrmohanreddy
ms.date: 02/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: b591799bd5bf00e74e782040bfdc1b678c4c87d0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906912"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>A minősítések és értékelések használatának bekapcsolása

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet a webhelyen értékeléseket és értékeléseket Microsoft Dynamics 365 Commerce használni.

Az értékelések és a vélemények megoldása egy omnicsatornás megoldás, amelyet a Dynamics 365 Commerce megoldásban a Microsoft Dynamics Lifecycle Services (LCS) segítségével tehet elérhetővé. Az LCS egy olyan felügyeleti portál, amelyet a kiskereskedők a környezeteik kezelésére használhatnak a telepítéstől egészen a megszüntetésig.

Ha azt szeretné, hogy a minősítési és értékelési megoldást használhassa a Commerce webhelyén, akkor az e-Commerce webhely telepítését követően fel kell iratkoznia a minősítésekre és ellenőrzésekre a Dynamics 365 Commerce alkalmazásban.

## <a name="opt-in-to-use-ratings-and-reviews"></a>A minősítések és ellenőrzések használatának bekapcsolása

A következő lépések végrehajtásával választhatja ki azt, hogy használni szeretné az értékelések és vélemények funkciót.

1. Kövesse az [Új e-commerce webhely telepítése](deploy-ecommerce-site.md) szakasz lépéseit.
1. Amikor még az LCS-ben van nyissa meg a **Retail-telepítés beállítása \> Egyéb beállítások** lehetőséget.
1. Állítsa be az **Értékelések és vélemények szolgáltatás engedélyezése** értékét **Igen** beállításra.
1. **Az AAD biztonsági csoportban, amely minősítéseket és áttekintő moderátorokat** használ, adja meg a Microsoft Azure Active Directory biztonsági csoportjának azonosítóját,Azure AD amely a minősítéseket és a moderőket is tartalmazza.

    ![A minősítések és értékelések használatának bekapcsolása.](media/LCS_RnR_Preference_2.png)

1. Az e-commerce inicializálási folyamat végrehajtása.

> [!NOTE] 
> Ha olyan meglévő Dynamics 365 Commerce ügyfél, aki már telepített e-Commerce webhelyet anélkül, hogy feliratkozott volna a minősítések és értékelések funkcióra, és most használni kívánja a minősítések és értékelések funkciót a Dynamics 365 Commerce csomagból, akkor küldjön egy szolgáltatáskérelmet. A szolgáltatáskérelem elküldésével kapcsolatos további tudnivalókat lásd: [Szolgáltatáskérelem küldésének folyamata](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce](sync-product-ratings.md)

[A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése](manual-publish-rating-reviews.md)

[Értékelések és véleményezések importálása és exportálása](import-export-reviews.md)

[Szolgáltatás a szolgáltatáshoz típusú hitelesítés konfigurálása](service-to-service-auth.md)

[Értékelések és vélemények GYIK](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
