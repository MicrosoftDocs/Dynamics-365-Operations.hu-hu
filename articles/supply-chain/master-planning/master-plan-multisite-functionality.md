---
title: Az alaptervezés és a többhelyes funkció áttekintése
description: Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót.
author: t-benebo
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2434"
- intro-internal
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 289763931703eb354ae78fa18f37cd00f1102de8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844909"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Az alaptervezés és a többhelyes funkció áttekintése

[!include [banner](../includes/banner.md)]

Az Alaptervezés figyelembe veszi a webhely beállításait és a raktár készletdimenziót. 

A hely dimenzió kötelező és beállíthatja, hogy a raktárdimenzió is kötelező legyen.

Amikor egy dimenzió kötelező, akkor a dimenzióértéket minden készlettranzakció esetén meg kell adni. Tehát az alaptervezés ideje alatt a telephely és a raktár ismert a kezdeti igényhez. A helydimenzió konzisztens is, tehát az alacsonyabb rendű igény során történő alábontáskor az értéke nem fog változni.

Ha a raktár megadása nem kötelező, akkor előfordulhat, hogy a kezdeti igényből nem határozható meg a raktár. A tervezőmotornak ilyenkor a cikkre, az egyes raktárakra, valamint a rendeléssorra meghatározott beállítások alapján kell meghatároznia, hogy melyik raktárat használja.

Az alábbi cikkek leírják, hogy hogyan határozza meg a tervezőmotor a raktárat különböző beállítások megadásakor.

[Telephely és raktárfedezet alaptervezése, kötelező raktár](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Alaptervezés telephely-lefedettséghez, kötelező raktár](master-plan-site-coverage-warehouse-mandatory.md)

[Telephely és raktárfedezet alaptervezése, nem kötelező raktár](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Alaptervezés helyfedezethez, a raktár nem kötelező](master-plan-site-coverage-warehouse-not-mandatory.md)

[Anyagjegyzék-verzió meghatározása](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]