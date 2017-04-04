---
title: "Az Alaptervezés a hely és a raktár lefedettség, kötelező raktár"
description: "Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket. A raktár dimenzió kötelező."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a0931d88f84544160803e42466575c02f47588a4
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>Az Alaptervezés a hely és a raktár lefedettség, kötelező raktár

Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenziókként webhellyel ás raktárral rendelkező cikket. A raktár dimenzió kötelező.

Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban.
-   A raktárdimenzió kötelező, és meg kell adni az igénytranzakcióban.
-   A telephely és raktár dimenzió be van állítva a fedezet tervezéséhez. Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez. A több telephelyes funkciók mindezeket nem érintik.

Az alábbi ábra az alapütemezés folyamatát illusztrálja. Az ábrán látható paraméterek és helyeik a következők:
-   The warehouse is set to **Manual**. Kattintson a **Inventory management &gt;a telepítő &gt;Készlet részletezése &gt;raktár**. Az a **Alaptervezés** gyorslapon lásd a **Kézi** mezőt.
-   A cikkre cikkfedezet van meghatározva. Kattintson a **termék információkezelés &gt;termékek&gt;, amely a termékek**. Jelölje ki az elemet, majd kattintson a műveletek ablaktábla a a **terv** fülre, kattintson a **Cikkfedezet**.
-   A raktárban újratöltési viszonyok vannak meghatározva. Kattintson a **Inventory management &gt;a telepítő &gt;Készlet részletezése &gt;raktár**. Az **Alaptervezés** gyorslapon lásd az **Elsődleges raktár** mezőcsoportot.
-   Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban. Kattintson a **termék információkezelés &gt;termékek&gt;, amely a termékek**. Jelölje ki az elemet, majd kattintson a műveletek ablaktábla a a **terv** fülre, kattintson a **alapértelmezett beállítások**. Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.

![Telephely és raktárfedezet igénylése, kötelező raktár](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Lásd még
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Alaptervezés - helyfedezet, a raktár kötelező](master-plan-site-coverage-warehouse-mandatory.md)

[Alaptervezés - helyfedezet, a raktár nem kötelező](master-plan-site-coverage-warehouse-not-mandatory.md)

[Alaptervezés - hely és raktár fedezet, a raktár nem kötelező](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Alaptervezés - Anyagjegyzék verzió meghatározása](master-plan-bom-version-determined.md)


