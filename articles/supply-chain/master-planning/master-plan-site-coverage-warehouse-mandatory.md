---
title: Alaptervezés helyfedezethez, a raktár kötelező
description: Ez a témakör azt ismerteti, hogy hogyan tervez a program fedezeti dimenzióként egy cikket, amely a telephelyet tartalmazza. A raktár kötelező dimenzió.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df58017c25737cc946d09bf86ff7ad8bd33f4176
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741040"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Alaptervezés helyfedezethez, a raktár kötelező

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogy hogyan tervez a program fedezeti dimenzióként egy cikket, amely a telephelyet tartalmazza. A raktár kötelező dimenzió.

Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban. Ez a beállítás nem módosítható.
-   A raktárdimenzió kötelező, és meg kell adni az igénytranzakcióban.
-   A telephely dimenzió be van állítva a fedezet tervezéséhez. Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez. A több telephelyes funkciók mindezeket nem érintik.
-   A raktárdimenzió nincs beállítva a fedezet tervezéséhez. Ezért a program telephelyenként esetleg más fedezeti tervezési dimenziók szerint vonja össze a készleteket és az igényeket.

Az alábbi ábra az alapütemezés folyamatát illusztrálja. Az ábrán látható paraméterek és helyeik a következők:
-   A cikkre cikkfedezet van meghatározva. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a cikket, majd kattintson a **Terv &gt; Cikkfedezet** pontra.
-   A raktárban újratöltési viszonyok vannak meghatározva. Kattintson a következő lehetőségre: **Készletgazdálkodás &gt; Beállítás &gt; Készlet részletezése &gt; Raktárak**. Az **Alaptervezés** lapon lásd az **Elsődleges raktár** mezőcsoportot.
-   Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban. Kattintson a **Termékinformációk kezelése &gt; Termékek &gt; Kiadott termékek** lehetőségre. Válassza ki a cikket, majd kattintson a **Terv &gt; Alapértelmezett rendelésbeállítások** parancsra. Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.

![Telephely fedezet igénylése, raktár kötelező.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>További erőforrások

- [Az alaptervezés és a több telephelyes funkció áttekintése](master-plan-multisite-functionality.md)
- [Telephely és raktárfedezet alaptervezése, kötelező raktár](master-plan-site-warehouse-coverage-warehouse-mandatory.md)
- [Alaptervezés telephely-lefedettséghez, kötelező raktár](master-plan-site-coverage-warehouse-mandatory.md)
- [Telephely és raktárfedezet alaptervezése, nem kötelező raktár](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)
- [Anyagjegyzék-verzió meghatározása](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]