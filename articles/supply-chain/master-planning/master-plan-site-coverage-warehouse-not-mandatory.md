---
title: Alaptervezés helyfedezethez, a raktár nem kötelező
description: Ez a témakör azt ismerteti, hogyan tervez a program fedezetre beállított hely dimenziókészletet beállítva egy cikkhez.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 327bb259cc108f1fad068c847441229dcaee7ff1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859227"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Alaptervezés helyfedezethez, a raktár nem kötelező

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan tervez a program fedezetre beállított hely dimenziókészletet beállítva egy cikkhez.

Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.
-   A raktár dimenzió nincs kötelezően beállítva. Lehet, hogy a raktár ismert, de ez nem befolyásolja az alapütemezési számítást.
-   A telephely dimenzió be van állítva a fedezet tervezéséhez.
-   A raktárdimenzió nincs beállítva a fedezet tervezéséhez. Ezért a program telephelyenként esetleg más fedezeti tervezési dimenziók szerint vonja össze a készleteket és az igényeket.

Az alábbi ábra az alapütemezés folyamatát illusztrálja. Az ábrán látható paraméterek és helyeik a következők:
-   A cikkre cikkfedezet van meghatározva. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a cikket, majd kattintson a **Terv &gt; Cikkfedezet** pontra.
-   A raktárban újratöltési viszonyok vannak meghatározva. Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**. Az **Alaptervezés** lapon lásd az **Elsődleges raktár** mezőcsoportot.
-   Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a cikket, majd kattintson a **Terv &gt; Alapértelmezett rendelésbeállítások** parancsra. Az **Alapértelmezett rendelésbeállítások** képernyőn lásd az **Alapértelmezett rendeléstípus** mezőt.

![Telephely fedezet igénylése, raktár nem kötelező.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>További erőforrások

[Az alaptervezés és a több telephelyes funkció áttekintése](master-plan-multisite-functionality.md)

[Telephely és raktárfedezet alaptervezése, kötelező raktár](master-plan-site-coverage-warehouse-mandatory.md)

[Alaptervezés telephely-lefedettséghez, kötelező raktár](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Alaptervezés helyfedezethez, a raktár nem kötelező](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Anyagjegyzék-verzió meghatározása](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]