---
title: Árusítási entitások rendezési sorrendjének módosítása
description: Ez a témakör bemutatja a különböző árusítási entitások megjelenítési sorrendjének szabályozásával kapcsolatos fogalmakat a következő helyeken:Dynamics 365 Commerce
author: josaw1
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80586597f4f60476b341e4cf1cfd90f3681e15c0
ms.sourcegitcommit: 52e31b1ef2b3ed8675de931d06090cd57e057fc2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9265836"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Árusítási entitások rendezési sorrendjének módosítása


[!Include [banner](includes/banner.md)]

A kiskereskedők a termékfelderítésre elsődleges eszközként tekintenek az ügyfélinterakciókhoz összes kereskedelmi csatornán. Számos olyan funkció van, amely a vevők számára könnyen felhasználhatja a termékeket. Például a vevők kategóriákban, keresésben és szűrésben is kereshetnek.

Ez a témakör bemutatja a különböző árusítási entitások megjelenítési sorrendjének szabályozásával kapcsolatos fogalmakat. Bemutatja a rendezési sorrend módosításának módját is.

## <a name="overview"></a>Áttekintés

A Commerceben a különféle árusítási egymáshoz kapcsolódó entitások rendezése igazodik a meglévő vevői esetekhez, és a megvalósítási partnerek már nem igénylik a bővítmények használatát.

A Commerce rendszer 10.0.5-ös és korábbi verzióiban a kategóriák rendezési sorrendje betűrendes volt. A jelenlegi egyéni rendezési sorrend funkció lehetővé teszi az árusítási vezetők számára, hogy az összes végfelhasználó ügyfélen konfigurálják a különféle árusításokkal kapcsolatos entitások rendezési sorrendjét. Ezek az ügyfelek többek között a központok (HQ) és a hívásközpontok.

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

![A termékek hierarchiájának egyéni sorrendje negatív értékekkel.](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Közzétett termékek kategóriák szerint, a termékek hierarchiája alapján egyéni módon rendezve.](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>A csatornanavigáció hierarchiájában megjelenítési sorrend konfigurálása a kategóriákhoz

Ennek a műveletnek az elvégzése előtt a demóadatokat telepítenie kell a környezetébe.

1. Menjen a **Kiskereskedelem és kereskedelem \> Termékek és kategóriák \> Csatorna navigációs kategóriák** helyre.
2. A listából válassza ki a **Divatnavigáció** hierarchiát.
3. Kattintson a **Kategóriahierarchiák szerkesztése** pontra.
4. Kattintson a **Szerkesztés** lehetőségre.
5. A fában válassza **a Divatáru \> - és nőruházati \> női ruházatot**.
6. Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.
7. A fában válassza ki a **Divat \> Női ruházat \> Felsők** lehetőséget.

Hasonlóképpen meghatározhatja az alkategóriák rendezési sorrendjét is.

8. A fában válassza ki a **Divat \> Férfiruházat \> Casual ingek** lehetőséget.
9. Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.
10. A fában válassza ki a **Divat \> Férfiruházat \> Kabátok és dzsekik** lehetőséget.
11. Adjon meg egy számot az **Megjelenítés sorrendje** mezőben.
12. Ismételje meg ezt minden olyan további kategória esetében, amelynek módosítani szeretné a sorrendet.

A csatorna navigációs hierarchiájának megjelenítési sorrendje a központ, katalógus és csatornákban is tükröződik.

![Csatornanavigáció hierarchiája egyéni módon rendezve.](./media/ChannelNavCustomSorted.png)

![Katalógus-navigációs hierarchia egyéni módon rendezve a csatorna navigációs hierarchiája alapján.](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Pénztár egyéni módon rendezett kategóriákkal.](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Alapértelmezés szerint az **Árusítási entitások megjelenítési sorrendjének engedélyezése** funkció ki van kapcsolva. A [Funkciókezelés segítségével](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) bekapcsolhatja a funkciót. Miután lefutott a funkcióról, futtassa a **Globális konfiguráció -1110** CDX-feladatot az elosztási ütemezésből.
> Ha a POS-ban nem frissülnek a kategóriák sorrendje, aktiválja újra az eszközt. A kategóriaadatokat az eszköz aktiválása esetén a rendszer bekéri, így lehet, hogy az eszköznek át kell kérnie a kategóriaadatokat a frissített megjelenítési rendelésekkel. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
