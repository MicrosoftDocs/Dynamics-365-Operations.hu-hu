---
title: Kategória céloldalának bővítése
description: Ez a cikk a kategóriaoldalak a következőben történő bővítettségét tartalmazza:Dynamics 365 Commerce
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: e3397ffee9b32f3d3efedea38255f88daee5233c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282161"
---
# <a name="enrich-a-category-landing-page"></a>Kategória céloldalának bővítése

[!include [banner](includes/banner.md)]

Ez a cikk a kategóriaoldalak a következőben történő bővítettségét tartalmazza:Dynamics 365 Commerce

A Commerce egy alapértelmezett kategória-nyitólapot biztosít, amely a kategóriaadatok megjelenítésekor kerül felhasználásra. Az alapértelmezett kategórialap tartalmazza a szükséges elemeket, például a finomítókat, a kategorizált termékelhelyezést, a rendezési beállításokat, a választási lehetőségek összesítését és a laptördelési vezérlőelemeket. 

Az alapértelmezett kategórialap használata helyett előfordulhat, hogy olyan „bővített” kategória-nyitólapot szeretne használni, amely több tartalmat és konkrétabb elemeket tartalmaz. A jellemző bővítéshez szükség lehet a kategória-specifikus marketinganyagok kategóriaoldalhoz. Ez a tartalom több keresztértékesítési célú keresztkategóriás termékelhelyezést, szerkesztői listákat, képeket, videókat és egyéb szöveget tartalmazhat. Vagy módosíthatja az alapértelmezett kategórialap, vagy meghatározható egy másik kategórialap egy adott kategóriához.

![Bővített kategória-céloldal.](./media/CategoryLandingPages.png)

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

[Dinamikus e-kereskedelmi oldalak létrehozása URL-paraméterek alapján](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
