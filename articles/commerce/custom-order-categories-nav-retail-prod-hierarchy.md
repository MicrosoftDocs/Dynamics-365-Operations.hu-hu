---
title: Árusítási entitások rendezési sorrendjének módosítása
description: Ez a témakör azt mutatja be, hogyan lehet szabályozni a különböző árusítási-entitások megjelenítési sorrendjét a Dynamics 365 Commerce megoldásban.
author: josaw1
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 31798508e4cc71e31a30dc91acebfdde8226b16c
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2021
ms.locfileid: "5937062"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Árusítási entitások rendezési sorrendjének módosítása


[!include [banner](includes/banner.md)]

A kiskereskedők a termékfelderítésre elsődleges eszközként tekintenek az ügyfélinterakciókhoz összes kereskedelmi csatornán. A különböző funkciók segítségével a vevők könnyedén felfedezhetik a termékeket. Tallózhatók például a kategóriák között, a kereshetnek és a szűrhetnek.

Ez a témakör azt mutatja be, hogyan lehet szabályozni a különböző árusítási-entitások megjelenítési sorrendjét. Bemutatja a rendezési sorrend módosításának módját is.

## <a name="overview"></a>Áttekintés

A különböző árusításhoz entitások rendezése tovább lett fejlesztve. Ez a támogatás most jobban igazodik a meglévő vevői esetekhez, amelyekhez korábban bővítmények voltak szükségesek az implementálási partnerektől.

A Retail 10.0.5 verziójánál korábbi verziókban a navigációs hierarchiában a kategóriák rendezési sorrendje ábécé sorrendben volt. Az új egyéni rendezési funkció lehetővé teszi a az árukezelők számára, hogy az összes végfelhasználói ügyfél számára konfigurálják a különböző árusítási entitások rendezési sorrendjét. Ezek az ügyfelek többek között a központok (HQ) és a hívásközpontok.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>A termékek hierarchiájában megjelenítési sorrend konfigurálása a kategóriákhoz

Ennek a műveletnek az elvégzése előtt a demóadatokat telepítenie kell a környezetébe.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Kereskedelmi termékhierarchia** lehetőségre.
2. Kattintson a **Kategóriahierarchiák szerkesztése** pontra.
3. Kattintson a **Szerkesztés** lehetőségre.
4. A fában bontsa ki az **ÖSSZES \> Akciósportok** elemet.
5. A fában bontsa ki az **ÖSSZES \> Csapatsportok** elemet.
6. Adjon meg egy számot az **Megjelenítés sorrendje** mezőben. (A szám negatív is lehet.)
7. Ismételje meg a 4–6 lépéseket minden olyan további kategória esetében, amelynek módosítani szeretné a sorrendet.

A csatorna navigációs hierarchiájának megjelenítési sorrendje tükröződni fog a központ számára a kereskedelmi termékek hierarchiájában, és kategóriánként kiadott termékeknél.

![A termékek hierarchiájának egyéni sorrendje negatív értékekkel](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Közzétett termékek kategóriák szerint, a termékek hierarchiája alapján egyéni módon rendezve](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>A csatornanavigáció hierarchiájában megjelenítési sorrend konfigurálása a kategóriákhoz

Ennek a műveletnek az elvégzése előtt a demóadatokat telepítenie kell a környezetébe.

1. Menjen a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Csatorna navigációs kategóriák** helyre.
2. A listából válassza ki a **Divatnavigáció** hierarchiát.
3. Kattintson a **Kategóriahierarchiák szerkesztése** pontra.
4. Kattintson a **Szerkesztés** lehetőségre.
5. A fában válassza ki a **Divat \> Női ruházat \> Női cipők** lehetőséget.
6. Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.
7. A fában válassza ki a **Divat \> Női ruházat \> Felsők** lehetőséget.

    Hasonlóképpen meghatározható az alkategóriák rendezési sorrendje is.

8. A fában válassza ki a **Divat \> Férfiruházat \> Casual ingek** lehetőséget.
9. Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.
10. A fában válassza ki a **Divat \> Férfiruházat \> Kabátok és dzsekik** lehetőséget.
11. Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.
12. Ismételje meg ezt minden olyan további kategória esetében, amelynek módosítani szeretné a sorrendet.

A csatorna navigációs hierarchiájának megjelenítési sorrendje a központ, katalógus és csatornákban is tükröződik.

![Csatornanavigáció hierarchiája egyéni módon rendezve](./media/ChannelNavCustomSorted.png)

![Katalógus-navigációs hierarchia egyéni módon rendezve a csatorna navigációs hierarchiája alapján](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Pénztár egyéni módon rendezett kategóriákkal](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Alapértelmezés szerint az egyéni rendezési sorrend funkció ki van kapcsolva. Ennek a funkciónak és egyéb funkcióknak a bekapcsolásával kapcsolatosan lásd: [Funkciókezelés](/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).


[!INCLUDE[footer-include](../includes/footer-banner.md)]