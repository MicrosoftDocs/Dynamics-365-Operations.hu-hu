---
title: "Hely lefedettsége kötelező raktári az Alaptervezés"
description: "Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenzióként webhellyel rendelkező cikket. A raktár kötelező dimenzió."
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
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4c595aa9809e37ba752b76f559ef909c071eb303
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Hely lefedettsége kötelező raktári az Alaptervezés

Ez a témakör leírja, hogyan terveznek meg egy fedezeti dimenzióként webhellyel rendelkező cikket. A raktár kötelező dimenzió.

Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephelydimenzió kötelezőre van állítva, és meg kell adni az igénytranzakcióban. Ez a beállítás nem módosítható.
-   A raktárdimenzió kötelező, és meg kell adni az igénytranzakcióban.
-   A telephely dimenzió be van állítva a fedezet tervezéséhez. Előfordulhat, hogy más dimenziók is be vannak állítva a fedezet tervezéséhez. A több telephelyes funkciók mindezeket nem érintik.
-   A raktárdimenzió nincs beállítva a fedezet tervezéséhez. Ezért a program telephelyenként esetleg más fedezeti tervezési dimenziók szerint vonja össze a készleteket és az igényeket.

Az alábbi ábra az alapütemezés folyamatát illusztrálja. Az ábrán látható paraméterek és helyeik a következők:
-   A cikkre cikkfedezet van meghatározva. Kattintson a **termék információkezelés &gt;termékek&gt;, amely a termékek**. Jelölje ki az elemet, és kattintson a **tervezett &gt;Cikkfedezet**.
-   A raktárban újratöltési viszonyok vannak meghatározva. Kattintson a **Inventory management &gt;a telepítő &gt;Készlet részletezése &gt;raktár**. Az **Alaptervezés** lapon lásd az **Elsődleges raktár** mezőcsoportot.
-   Az alapértelmezett rendelési típus beállítása Termelés, Beszerzési rendelés vagy Kanban. Kattintson a **termék információkezelés &gt;termékek&gt;, amely a termékek**. Jelölje ki az elemet, és kattintson **tervezett &gt;rendelés az alapbeállításokat**. Az a **Alapértelmezett rendelésbeállítások** űrlapon lásd a **Alapértelmezett rendeléstípus** elemet.

![Telephely fedezet igénylése, raktár kötelező](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Lásd még
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Alaptervezés - hely és raktár fedezet, a raktár kötelező](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Fő tervezési - fedezeti hely. kötelező raktár](master-plan-site-coverage-warehouse-mandatory.md)

[Alaptervezés - hely és raktár fedezet, a raktár nem kötelező](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Alaptervezés - Anyagjegyzék verzió meghatározása](master-plan-bom-version-determined.md)


