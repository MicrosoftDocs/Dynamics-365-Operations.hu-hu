---
title: "Retail-termékkategóriák és termékek kezelése"
description: "Ez a témakör leírja, hogy a termékkihelyezési vezetők hogyan használhatják a Retail termékkategóriákat a Retail-termékhierarchia és a kiadott termék részletei közötti kapcsolatok kezeléséhez."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 19c972164474c972aab642c3cccc67cf396a6cb2
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="manage-retail-product-categories-and-products"></a>Retail-termékkategóriák és termékek kezelése

[!include [banner](./includes/banner.md)]

Ez a témakör a Retail-termékkategóriák és termékek kezelésének továbbfejlesztett módját mutatja be a Microsoft Dynamics 365 for Retail alkalmazásban. A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a Retail termékek hierarchiája és a kiadott termékrészletek között megosztott terméktulajdonság-struktúráját.

Ha többet szeretne tudni a Retail-termékkategóriák kezeléséről, a **Kategória és termék kezelése** munkaterületen válassza a **Kiskereskedelmi termékek hierarchiája** csempét.

Figyelje meg a megjelenő **Kiskereskedelmi termékek hierarchiája** lap továbbfejlesztett szerkezetét. A Retail korábbi verzióiban a terméktulajdonságok *alapvető terméktulajdonságokra* és *kiskereskedelmi termék tulajdonságaira* lettek felosztva, az alkalmazási hatókör alapján. A Retail termékek tulajdonságai alkalmazhatóságukban *globálisak*. Másként megfogalmazva ez azt jelenti, hogy egy adott Retail-terméktulajdonság esetében ugyanaz az érték oszlik meg minden jogi személy esetében. Az alapvető terméktulajdonságok viszont *jogi személy specifikusak*. Ez azt jelenti, hogy egy adott alapvető terméktulajdonság értéke eltérő lehet a jogi személyek esetében a jogi személyek egyedi üzleti igényei alapján.

A továbbfejlesztett Retail-termékkategória struktúrában a terméktulajdonságok logikailag el vannak választva a csoporton belüli alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.

![Mezők csoportosítása a tulajdonságaik alkalmazhatóságának terjedelme alapján](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre, vagy egy meghatározott jogi személyre nézve kezeli.

A tulajdonságok az összes jogi személy közti kezeléséhez válassza a **Megjelenítés minden jogi személyre** (vagy **Szerkesztés minden jogi személyre**) lehetőséget.

![Megjelenítés/szerkesztés minden jogi személyre](media/ToggleBackToEditForSpecificLegalEntity.PNG)

A tulajdonságok meghatározott jogi személynél való kezeléséhez válassza a **Megjelenítés egy meghatározott jogi személyre** (vagy **Szerkesztés egy meghatározott jogi személyre**) lehetőséget.

![Megjelenítés/szerkesztés egy meghatározott jogi személyre](media/ToggleToEditForAllLegalEntities.PNG)

Amellett a bővített Retail termékkategória-szerkezetben a termékkihelyezési vezető most meghatározhat egy alapértelmezett értéket a terméktulajdonságok egy további csoportjához egy egyéni kategória szintjén. Ezután a termékek létrehozáskor öröklik az alapértelmezett értékeket a termék tulajdonságaik alapján, ezen tulajdonságok a Retail termékhierarchiában lévő egyedi kategóriával való társításuk alapján. A termékkihelyezési vezetők módosíthatják is ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a>Tulajdonságok kiválasztása a termékek frissítéséhez a Retail termékhierarchia lapról

A terméktulajdonságok új, továbbfejlesztett struktúrája segítségével kiválaszthatja, melyik frissített terméktulajdonságoknak kell átkerülniük a kapcsolódó termékekbe. A **Kiskereskedelmi termékek hierarchiája** oldalon a műveleti ablaktáblában válassza a **Kategória** elemet, majd a **Termékek frissítése** lehetőséget a **Termékek frissítése** dialógusablak megnyitásához.

![Termékek frissítése párbeszédpanel](media/NewUpdateProductsEnhancedView.PNG)

