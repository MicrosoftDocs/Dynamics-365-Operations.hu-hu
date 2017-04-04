---
title: "Az alaptervezés és a többhelyes funkció"
description: "Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 19eeee753c15cf2670948ce2c615a112813c16ad
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-and-multisite-functionality"></a>Az alaptervezés és a többhelyes funkció

Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót. 

A hely dimenzió kötelező és beállíthatja, hogy a raktárdimenzió is kötelező legyen.

Amikor egy dimenzió kötelező, akkor a dimenzióértéket minden készlettranzakció esetén meg kell adni. Tehát az alaptervezés ideje alatt a telephely és a raktár ismert a kezdeti igényhez. A helydimenzió konzisztens is, tehát az alacsonyabb rendű igény során történő alábontáskor az értéke nem fog változni.

Ha a raktár megadása nem kötelező, akkor előfordulhat, hogy a kezdeti igényből nem határozható meg a raktár. A tervezőmotornak ilyenkor a cikkre, az egyes raktárakra, valamint a rendeléssorra meghatározott beállítások alapján kell meghatároznia, hogy melyik raktárat használja.

A következő wiki cikkek leírják, hogyan működik a tervezési motor, amikor különböző beállítások vannak meghatározva, hogy meghatározzák, hogy melyik raktárak legyenek felhasználva.

[Alaptervezés - hely és raktár fedezet, a raktár kötelező](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Alaptervezés - helyfedezet, a raktár kötelező](master-plan-site-coverage-warehouse-mandatory.md)

[Alaptervezés - hely és raktár fedezet, a raktár nem kötelező](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Alaptervezés - helyfedezet, a raktár nem kötelező](master-plan-site-coverage-warehouse-not-mandatory.md)

[Alaptervezés - Anyagjegyzék verzió meghatározása](master-plan-bom-version-determined.md)


