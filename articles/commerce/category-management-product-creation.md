---
title: Termékkategóriák és termékek kezelése
description: Ez a témakör leírja, hogy a termékkihelyezési vezetők hogyan használhatják a termékkategóriákat a Commerce-termékhierarchia és a kiadott termék részletei közötti kapcsolatok kezeléséhez.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: cee79d6937afeec1e607abde49d52790c51e98a4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001074"
---
# <a name="manage-product-categories-and-products"></a>Termékkategóriák és termékek kezelése

[!include [banner](./includes/banner.md)]

Ez a témakör a termékkategóriák és termékek kezelésének továbbfejlesztett módját mutatja be a Dynamics 365 Commerce alkalmazásban. A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a termékek hierarchiája és a kiadott termékrészletek között megosztott terméktulajdonság-struktúráját.

Ha többet szeretne tudni a termékkategóriák kezeléséről, a **Kategória és termék kezelése** munkaterületen válassza a **Kereskedelmi termékek hierarchiája** csempét.

Figyelje meg a megjelenő **Kereskedelmi termékek hierarchiája** lap továbbfejlesztett szerkezetét. Az alkalmazás korábbi verzióiban a terméktulajdonságok *alapvető terméktulajdonságokra* és *kiskereskedelmi termék tulajdonságaira* lettek felosztva, az alkalmazási hatókör alapján. A Retail termékek tulajdonságai alkalmazhatóságukban *globálisak*. Másként megfogalmazva ez azt jelenti, hogy egy adott terméktulajdonság esetében ugyanaz az érték van megosztva minden jogi személy esetében. Az alapvető terméktulajdonságok viszont *jogi személy specifikusak*. Ez azt jelenti, hogy egy adott alapvető terméktulajdonság értéke eltérő lehet a jogi személyek esetében a jogi személyek egyedi üzleti igényei alapján.

A továbbfejlesztett termékkategória struktúrában a terméktulajdonságok logikailag el vannak választva a csoporton belüli alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.

![Mezők csoportosítása a tulajdonságaik alkalmazhatóságának terjedelme alapján](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre, vagy egy meghatározott jogi személyre nézve kezeli.

A tulajdonságok az összes jogi személy közti kezeléséhez válassza a **Megjelenítés minden jogi személyre** (vagy **Szerkesztés minden jogi személyre**) lehetőséget.

![Megjelenítés/szerkesztés minden jogi személyre](media/ToggleBackToEditForSpecificLegalEntity.PNG)

A tulajdonságok meghatározott jogi személynél való kezeléséhez válassza a **Megjelenítés egy meghatározott jogi személyre** (vagy **Szerkesztés egy meghatározott jogi személyre**) lehetőséget.

![Megjelenítés/szerkesztés egy meghatározott jogi személyre](media/ToggleToEditForAllLegalEntities.PNG)

Amellett a bővített termékkategória-szerkezetben a termékkihelyezési vezető most meghatározhat egy alapértelmezett értéket a terméktulajdonságok egy további csoportjához egy egyéni kategória szintjén. Ezután a termékek létrehozáskor öröklik az alapértelmezett értékeket a termék tulajdonságaik alapján, ezen tulajdonságok a termékhierarchiában lévő egyedi kategóriával való társításuk alapján. A termékkihelyezési vezetők módosíthatják is ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a>Tulajdonságok kiválasztása a termékek frissítéséhez a Commerce termékhierarchia lapról

A terméktulajdonságok új, továbbfejlesztett struktúrája segítségével kiválaszthatja, melyik frissített terméktulajdonságoknak kell átkerülniük a kapcsolódó termékekbe. A **Commerce-termékek hierarchiája** oldalon a műveleti ablaktáblában válassza a **Kategória** elemet, majd a **Termékek frissítése** lehetőséget a **Termékek frissítése** dialógusablak megnyitásához.

![Termékek frissítése párbeszédpanel](media/NewUpdateProductsEnhancedView.PNG)
