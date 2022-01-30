---
title: A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése
description: Ez a témakör bemutatja, hogyan lehet engedélyezni a minősítések és az értékelések moderátor által manuális közzétételét a Microsoft Dynamics 365 Commerce-ben, és hogyan lehet manuálisan közzétenni a minősítéseket és az értékeléseket.
author: gvrmohanreddy
manager: annbe
ms.date: 09/03/2021
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
ms.openlocfilehash: 443ebaa13d7ac29df66ffe77a2ed938e44a0c488
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968203"
---
# <a name="enable-manual-publishing-of-ratings-and-reviews-by-a-moderator"></a>A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet engedélyezni a minősítések és az értékelések moderátor által manuális közzétételét a Microsoft Dynamics 365 Commerce-ben, és hogyan lehet manuálisan közzétenni a minősítéseket és az értékeléseket.

A Dynamics 365 Commerce minősítései és értékelései megoldás az Azure Cognitive Servicest használja, amellyel automatikusan kitörölhetők a közönséges kifejezések az értékelések címében és tartalmában, valamint közzétehetők a minősítések és az értékeslések. Emiatt a manuális beavatkozásra nincs szükség az értékelések és minősítések áttekintésére és közzétételére az e-kereskedelmi webhelyen.

Vannak azonban olyan vállalkozások, amelyek inkább azt részesítik előnyben, ha moderátorok manuálisan áttekintik és jóváhagyják az értékeléseket, mielőtt közzéteszik őket. Az értékelések és a minősítések moderátor általi manuális közzétételének engedélyezéséhez engedélyeznie kell a **Moderátor előírása a minősítésekhez és értékelésekhez** funkciót a Commerce webhelykészítőben.

## <a name="enable-the-require-moderator-for-ratings-and-reviews-feature-in-commerce-site-builder"></a>A Moderátor előírása a minősítésekhez és értékelésekhez funkció engedélyezése a Commerce webhelykészítőben

A **Moderátor előírása a minősítésekhez és értékelésekhez** funkció engedélyezéséhez a Commerce webhelykészítőben kövesse ezeket a lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Beállítások** elemet.
1. Állítsa a **Moderátor előírása a minősítésekhez és értékelésekhez** beállítást **Be** értékre.

> [!NOTE]
> Ha engedélyezi a **Moderátor előírása a minősítésekhez és értékelésekhez** funkciót, leállítja a minősítések és értékelések automatikus közzétételét, így most manuális közzétételre van szükség. Az Azure Cognitive Services azonban továbbra is kitörli a szókimondó kifejezéseket az értékelések címében és tartalmában.

<!--![Require moderator for ratings and reviews setting in Commerce site builder.](media/Ratings-reviews-settings-human-moderation.png)-->

## <a name="publish-ratings-and-reviews"></a>Minősítések és értékelések közzététele

Amikor engedélyezi a **Moderátor előírása a minősítésekhez és értékelésekhez** funkciót, egy moderátornak manuálisan át kell tekintenie és közzé kell tennie a minősítéseket és értékeléseket ahhoz, hogy megjelenjenek az e-kereskedelmi webhelyen.

A Commerce webhelykészítőben az értékelések és vélemények áttekintéséhez és közzétételéhez az alábbi lépéseket hajtsa végre.

1. Nyissa meg az **Értékelések \> Moderálás** elemet.
1. A rácsban, ha egy sor **Állapot** mezőjének beállítása **Nem közzétett**, akkor az abban a sorban lévő értékelés és minősítés még nincs közzétéve. Ha a közzé nem tett értékeléseket és minősítéseket szeretné megtekinteni, válassza az **Állapot: Ellenőrzésre van szükség** a rács fölötti állapotszűrőben.
1. Válasszon ki egy vagy több **Nem közzétett** állapotú értékelést és minősítést, majd válassza a **Közzététel** lehetőséget a parancssávon. A kiválasztott minősítések és értékelések bekerülnek a közzétételi várólistába, és közzétételük után megjelennek az e-kereskedelmi webhelyen.

> [!NOTE]
> - Az értékelés és a minősítés közzététele után az állapot értéke **Nem közzétett** értékről null értékre módosul (üres mező).
> - Ha több értékelést és minősítést választ ki, amelyek vegyes állapotúak, majd a **Közzététel** lehetőséget választja, a még közzé nem tett minősítések és értékelések közzétételre kerülnek. A már közzétett minősítések és értékelések azonban nem lesznek újra közzétéve.

Az alábbi ábra egy olyan példát mutat be, amelyben a Commerce webhelykészítő **Moderálás** oldalán három közzé nem tett minősítést és értékelést választottak ki.

![Három közzé nem tett értékelés és ellenőrzés kiválasztva a Commerce webhelykészítő Moderálás oldalán.](media/Ratings-reviews-publishing-reviews.png)

<!--![Dynamics 365 Commerce - Ratings and Review configuration 2](media/Ratings-reviews-published-reviews.png)-->
<!--![Status filter](media/Ratings-reviews-published-reviews-status-filter.png)-->

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása](sync-product-ratings.md)

[Minősítések és felülvizsgálatok importálása és exportálása](import-export-reviews.md)

[Szolgáltatás-szolgáltatás hitelesítés konfigurálása](service-to-service-auth.md)

[Értékelések és vélemények GYIK](ratings-reviews-faq.md)
