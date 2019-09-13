---
title: Az alaptervezés és a többhelyes funkció áttekintése
description: Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót.
author: roxanadiaconu
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f05e3efd1716a27a659ae40145f37bb0b3d977f
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2019
ms.locfileid: "1865404"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Az alaptervezés és a többhelyes funkció áttekintése

[!include [banner](../includes/banner.md)]

Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót. 

A hely dimenzió kötelező és beállíthatja, hogy a raktárdimenzió is kötelező legyen.

Amikor egy dimenzió kötelező, akkor a dimenzióértéket minden készlettranzakció esetén meg kell adni. Tehát az alaptervezés ideje alatt a telephely és a raktár ismert a kezdeti igényhez. A helydimenzió konzisztens is, tehát az alacsonyabb rendű igény során történő alábontáskor az értéke nem fog változni.

Ha a raktár megadása nem kötelező, akkor előfordulhat, hogy a kezdeti igényből nem határozható meg a raktár. A tervezőmotornak ilyenkor a cikkre, az egyes raktárakra, valamint a rendeléssorra meghatározott beállítások alapján kell meghatároznia, hogy melyik raktárat használja.

A következő témakörök bemutatják, hogy hogyan határozza meg a tervezőmotor a raktárat különböző beállításoknál.

[Alaptervezés - hely és raktár fedezet, a raktár kötelező](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Alaptervezés - helyfedezet, a raktár kötelező](master-plan-site-coverage-warehouse-mandatory.md)

[Alaptervezés - hely és raktár fedezet, a raktár nem kötelező](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Alaptervezés - helyfedezet, a raktár nem kötelező](master-plan-site-coverage-warehouse-not-mandatory.md)

[Alaptervezés - Anyagjegyzék verzió meghatározása](master-plan-bom-version-determined.md)



