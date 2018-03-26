---
title: "Termékkategóriák kezelése"
description: "Ez a témakör leírja, hogy a termékkihelyezési vezetők hogyan használhatják a Retail termékkategóriákat a Retail termékhierarchia és a kiadott termék részletei közötti kapcsolatok kezeléséhez."
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
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: hu-hu
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a>Továbbfejlesztett kategória- és termékkezelés

[!include[banner](./includes/banner.md)]

Ez a témakör a Retail termékkategóriák és termékek kezelésének továbbfejlesztett módját mutatja be a Dynamics 365 for Retail alkalmazásban. A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a Retail termékek hierarchiája és a kiadott termékrészletek közös terméktulajdonság-struktúráját.

A Retail termékkategóriák kezelésével kapcsolatos további tudnivalókért kattintson a **Kiskereskedelmi termékek hierarchiája** elemre a **Kategória és termék kezelése** munkaterületen, és tekintse meg a **Kiskereskedelmi termékkategória** lap továbbfejlesztett szerkezetét.

![Kategória és termék kezelése munkaterület](media/LaunchRetailProductHierarchy.png)

A korábbi verziókban a terméktulajdonságok **alapvető terméktulajdonságokra** és **kiskereskedelmi termék tulajdonságaira** lettek felosztva, az alkalmazási hatókör alapján. A **kiskereskedelmi termék tulajdonságai** *globálisak* voltak az alkalmazás terjedelmét tekintve, ami azt jelenti, hogy egy adott **kiskereskedelmi termék tulajdonság** esetében ugyanazt az értéket mutatja az összes jogi személy. Az **alapvető terméktulajdonságok** *jogi személy specifikusak* voltak. Ez azt jelenti, hogy egy adott **alapvető terméktulajdonság** értéke eltérő lehet a jogi személyek esetében az egyedi üzleti igények alapján.

A továbbfejlesztett Retail termékkategória struktúrában a terméktulajdonságok logikailag el vannak választva a csoporton belüli alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.

![Mezők csoportosítása az alkalmazásuk terjedelme alapján](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre nézve, vagy egy meghatározott jogi személyre nézve kezeli. Ehhez válassza a **Megjelenítés/szerkesztés minden jogi személyre** vagy a **Megjelenítés/szerkesztés egy meghatározott jogi személyre** lehetőségek egyikét.

![Nézetváltás az egyén és jogi személyek között](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Nézetváltás az egyén és jogi személyek között](media/ToggleToEditForAllLegalEntities.PNG)  

Összehasonlítva a korábbi verziókkal, az új Retail termékkategória-szerkezetben a termékkihelyezési vezető meghatározhat egy alapértelmezett értéket a terméktulajdonságok egy további csoportjához egy egyéni kategória szintjén. A termék létrehozása során ezeket az alapértelmezett terméktulajdonság értékeket örökli egy termék, egy egyedi kategóriával való társításuk alapján a Retail termékhierarchiájából. A termékkihelyezési vezetők módosíthatják is ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Jelölje ki a tulajdonságokat a termékek frissítéséhez a kiskereskedelmi termékkategória űrlapról 
 
A terméktulajdonságok új, továbbfejlesztett struktúrája segítségével kiválaszthatja, hogy melyik frissített terméktulajdonságoknak kell átkerülniük a kapcsolódó termékekbe. 

![Frissített termékek új, továbbfejlesztett nézete](media/NewUpdateProductsEnhancedView.PNG) 

A termékkihelyezési vezetők módosíthatják ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.


