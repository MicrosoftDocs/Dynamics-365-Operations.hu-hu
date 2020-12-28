---
title: Kategória céloldalának gazdagítása
description: Ez a témakör a kategória oldalainak bővítésével foglalkozik Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ca31ec7d2eee7d2b0c863506338341a870ff07ee
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412862"
---
# <a name="enrich-a-category-landing-page"></a>Kategória céloldalának gazdagítása


[!include [banner](includes/banner.md)]

Ez a témakör a kategória oldalainak bővítésével foglalkozik Dynamics 365 Commerce.

## <a name="overview"></a>Áttekintés

A Commerce egy alapértelmezett kategória-nyitólapot biztosít, amely a kategóriaadatok megjelenítésekor kerül felhasználásra. Az alapértelmezett kategórialap tartalmazza a szükséges elemeket, például a finomítókat, a kategorizált termékelhelyezést, a rendezési beállításokat, a választási lehetőségek összesítését és a laptördelési vezérlőelemeket. 

Az alapértelmezett kategórialap használata helyett előfordulhat, hogy olyan „bővített” kategória-nyitólapot szeretne használni, amely több tartalmat és konkrétabb elemeket tartalmaz. A jellemző bővítéshez szükség lehet a kategória-specifikus marketinganyagok kategóriaoldalhoz. Ez a tartalom több keresztértékesítési célú keresztkategóriás termékelhelyezést, szerkesztői listákat, képeket, videókat és egyéb szöveget tartalmazhat. Vagy módosíthatja az alapértelmezett kategórialap, vagy meghatározható egy másik kategórialap egy adott kategóriához.

![Bővített kategória-céloldal](./media/CategoryLandingPages.png)

A Commerce webhelykészítőben a **Termékrk** lap a webhelyhez társított csatorna kategóriáinak listáját tartalmazza. Ha a **Bővített** állapot van kiválasztva egy kategórialap számára, akkor a kategórialap bővített. Ellenkező esetben az alapértelmezett kategórialap és tartalom kerül felhasználásra a kategóriához. A kategória nevére kattintva megtekintheti a kategória bővített és nem bővített kategórialapjait.

A kategórialap bővítéséhez tegye a következőket.

1. A **Termékek** lapon válassza ki annak a kategóriának a nevét, amelyhez bővíteni szeretné a kategória lapját. A kiválasztott kategória alapértelmezett kategórialapja a lapszerkesztőben nyílik meg.
2. Válassza a **Kategórialap bővítése** lehetőséget.
3. Válassza ki a bővített kategórialap sablonját. Ha csak kisebb változtatásokat hajt végre, akkor választhatja az alapértelmezett kategórialapot. Azt is megteheti, hogy kijelöl egy adott kategórialap-sablont. Amikor kiválasztja a sablont, megnyílik a lap szerkesztője, és a kiválasztott sablon kerül felhasználásra a kiválasztott kategória új kategórialapjának létrehozásához. A lap ki van véve az Ön részére, és most elvégezheti a változtatásokat.

> [!NOTE]
> A kategória-meghatározási adatokat használó modulok a kiválasztott kategória adatait használják. A kiválasztott sablon beállításai határozzák meg, hogy milyen változtatásokat lehet végezni.

## <a name="additional-resources"></a>További erőforrások

[Meglévő webhelyoldal módosítása](modify-existing-page.md)

[Új webhelyoldal hozzáadása](add-new-page.md)

[Oldalelrendezések kiválasztása](select-page-layouts.md)

[SEO-metaadatok kezelése](manage-seo-metadata.md)

[Oldal mentése, megtekintése és közzététele](save-preview-publish-page.md)

[A termékoldal bővítése](enrich-product-page.md)

[Oldaltartalom hozzáférhetőségének ellenőrzése](verify-accessibility.md)
