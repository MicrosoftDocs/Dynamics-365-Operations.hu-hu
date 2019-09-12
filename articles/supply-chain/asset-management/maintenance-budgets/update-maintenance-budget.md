---
title: Karbantartási költségvetések frissítése
description: Ez a témakör leírja, hogyan lehet karbantartási költségvetést frissíteni az Eszközkezelésben.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 486782968816cc585d9cf2d753f32e82f85e4f7e
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874785"
---
# <a name="update-maintenance-budgets"></a>Karbantartási költségvetések frissítése

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A **Karbantartási költségvetés sorai** oldalon látható az összes költségvetési sor, amelyet a **Karbantartási költségvetések** oldalon kiválasztott költségvetéshez hoztak létre. (További információ a [Karbantartási költségvetések létrehozása](create-maintenance-budget.md) című témakörben olvasható.) A karbantartási költségvetés sorainak újraszámítása és helyesbítése a karbantartási költségvetés jóváhagyása előtt történik. A költségvetési időszak lejártát követően és a költségek az Eszközkezelés modulban való feladása után a költségvetési sorokat frissítheti a tényleges költségekkel.

## <a name="recalculate-a-maintenance-budget"></a>Karbantartási költségvetés újraszámítása

A karbantartási költségvetéseket a **Karbantartás költségvetési sorok** lapon lehet újraszámítani. A karbantartási költségvetés újraszámításakor a program törli a meglévő költségvetési sorokat, és új számítást végez.

1. A **Karbantartási költségvetési sorok** lapon válassza az **Újraszámítás** lehetőséget.
2. A **Költségvetés újraszámítása** párbeszédpanelen végezze el az új számításhoz szükséges módosításokat, majd kattintson az **OK** gombra.

Az új költségvetési sorok a beállított értékek alapján jönnek létre.

## <a name="adjust-budget-lines"></a>Költségvetési sorok kiigazítása

A teljes karbantartási költségvetés újraszámítása helyett a költségvetési költségekkel kapcsolatos kiválasztott sorok is módosíthatók.

1. A **Karbantartási költségvetési sorok** lapon válassza ki azokat a sorokat, amelyekhez módosítani szeretné a költségvetési költséget.
2. Válassza ki a **Módosítás** parancsot.
3. Ha hozzá szeretne adni egy összeget a kiválasztott sorokhoz, válassza a **Költség hozzáadása** jelölőnégyzetet, majd adja meg az értéket az **Érték hozzáadása** mezőben.
4. Ha a kiválasztott költségvetési sorokon a költségvetési sorokat egy szorzóval szeretné megszorozni, akkor válassza a **Költség megszorzása** jelölőnégyzetet, és adja meg a szorzót a **Szorzó értéke** mezőben.

    Például, ha a **Szorzó értéke** mezőben megadja az **1,2** értéket, akkor a kiválasztott sorok költségvetési költségét 20%-kal növeli. Ha a **0,7** értéket adja meg, akkor a költségvetési költséget a kiválasztott sorokban 30 százalékkal csökkenti.

5. Válassza ki az **OK** lehetőséget.

A kiválasztott költségvetési sorok a 3. és 4. lépésben beállított értékek alapján frissülnek.

## <a name="update-actual-costs"></a>Tényleges költségek frissítése

Miután a költségvetési sorokhoz tartozó dátumok lejártak, és a tényleges költségeket feladták az Eszközkezelésben, frissítheti a tényleges költségeket a karbantartási költségvetésen.

1. A **Karbantartási költségvetési sorok** lapon válassza a **Költség frissítése** lehetőséget.
2. A **Tényleges költség számítása** párbeszédpanelen válassza az **OK** gombot.

A rendszer frissíti a költségvetési sorok **Tényleges költség** mezőit, ha a tényleges költségeket feladták. Új költségvetési sorok jöhetnek létre, ha a költségvetés létrehozása óta új eszköztípusokat hoztak létre, és ha ezeket az eszköztípusokat olyan eszközökhöz használták, amelyekhez munkarendeléseket hoztak létre, és kapcsolódó költségeket adtak fel. Az új költségvetési sorok csak a tényleges költségeket jelenítik meg, mivel a program nem számított költségvetési költséget.

> [!NOTE]
> Ha a tényleges költségeket megelőző, helyesbítő és befektetési költségekre bontva szeretné áttekinteni, ugyanarra az időszakra vonatkozóan számítást végezhet az **Eszköz költségkontrollja** oldalon. 

## <a name="manually-add-budget-lines"></a>Költségvetési sorok manuális hozzáadása

A **Karbantartási költségvetési sorok** lapon az új költségvetési sort manuálisan is hozzáadhatja, ha az **új** lehetőséget választja, majd elvégzi a megfelelő kiválasztásokat a soron. Néhány példa az olyan esetekre, amikor ez a megközelítés hasznos lehet:

- Ha tudja, hogy bizonyos eszközök felújítása jelenleg a tervezési fázisban van, de a kapcsolódó feladatok még nem lettek létrehozva az Eszközkezelés modulban. Azonban azt szeretné, hogy ezen feladatok költségvetési költségei szerepeljenek a karbantartási költségvetésben.
- Új eszközöket vagy eszköztípusokat hoztak létre, mióta létrehozta a karbantartási költségvetést, de ezekhez az eszközökhöz vagy eszköztípusokhoz még nem állították be a karbatartási terveket. Azonban azt szeretné, hogy ezen eszköztípusok költségvetési költségei szerepeljenek a karbantartási költségvetésben.
