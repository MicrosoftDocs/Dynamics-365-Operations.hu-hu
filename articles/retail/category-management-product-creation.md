---
title: "Termékkategóriák kezelése és létrehozása"
description: "Ez a témakör leírja a fejlesztéseket, amelyek már megtörténtek a kiskereskedelmi termékek kategóriák kezelésére nézve. A fejlesztések segítségével a termékkihelyezési vezetők megtekinthetik a kiskereskedelmi termékek hierarchiája és a megjelent termékrészletek közötti korrelációt."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
ms.search.form: RetailCategoryAndProductWorkspace, RetailCategory
audience: Application User
ms.search.scope: Core, Retail
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 98250062892e0c5f665616dc3944181a3ff8599a
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="product-category-management-and-creation"></a>Termékkategóriák kezelése és létrehozása

[!include[banner](./includes/banner.md)]

A fejlesztések segítségével, amelyek megtörténtek a kiskereskedelmi termékek kategóriák kezelésére nézve, a termékkihelyezési vezetők megtekinthetik a kiskereskedelmi termékek hierarchiája és a megjelent termékrészletek közötti korrelációt. A fejlesztések megtekintéséhez a **Kategória és termék kezelése** munkaterületen válassza ki a **Kiskereskedelmi termékek hierarchiája** elemet a **Kiskereskedelmi termékkategória új szerkezete** lap megnyitásához. 

A korábbi kiadásokban a terméktulajdonságok alapvető terméktulajdonságokra és kiskereskedelmi termék tulajdonságaira lettek felosztva, az alkalmazási hatókör alapján. Kiskereskedelmi termék tulajdonságai *globálisak* voltak. Másként megfogalmazva ez azt jelenti, hogy egy adott terméktulajdonság esetében ugyanaz az érték van megosztva minden jogi személy esetében. Az alapvető terméktulajdonságok *jogi személy specifikusak* voltak. Ez azt jelenti, hogy egy adott terméktulajdonság eltérő lehet a jogi személyek esetében az egyedi üzleti igények alapján.

Ezekkel a fejlesztésekkel a kiskereskedelmi termékkategória terméktulajdonságai esetében továbbra is elválasztjuk a mezőket a csoporton belül alkalmazhatóság alapján a megjelent termék részletei képernyőstruktúrájának megfelelően.

Válthat aközött, hogy a jogi személyhez megadott tulajdonságokat az összes a jogi személyre nézve, vagy egy meghatározott jogi személyre nézve kezeli. Ehhez egyszerűen válassza a **Megjelenítés/szerkesztés minden jogi személyre** vagy a **Megjelenítés/szerkesztés egy meghatározott jogi személyre** lehetőségek közül a megfelelőt.

A termékkihelyezési vezetők emellett alapértelmezett értékeket határozhatnak meg terméktulajdonságok egy további halmazához az adott kategória szintjén. Ezeket a tulajdonságértékeket öröklik a termékek a termék létrehozásakor érvényes kategóriatársításuk alapján.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Jelölje ki a tulajdonságokat a termékek frissítéséhez a kiskereskedelmi termékkategória űrlapról

Logikai csoportosítási tulajdonságok segítségével válassza ki, melyik frissített terméktulajdonságokat kell leküldeni a kapcsolódó termékekbe.

A termékkihelyezési vezetők módosíthatják ezeket az örökölt terméktulajdonságokat az egyes termékekhez, az egyedi üzleti követelményeknek megfelelően.

