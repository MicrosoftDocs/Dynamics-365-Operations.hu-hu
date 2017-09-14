---
title: "Konfigurációs szabályok"
description: "Ez a cikk a konfigurációs szabályokkal kapcsolatos általános információkat tartalmazza. A konfigurációs szabályok meghatározzák a dimenzió alapú konfigurációs technológiát alkalmazó termékek anyagjegyzékében (BOM) szereplő cikkek kapcsolatát."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 74c8ffe4ab00e7afa1235e24327e18a65061636a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017

---

# <a name="configuration-rules"></a>Konfigurációs szabályok

[!include[banner](../includes/banner.md)]


Ez a cikk a konfigurációs szabályokkal kapcsolatos általános információkat tartalmazza. A konfigurációs szabályok meghatározzák a dimenzió alapú konfigurációs technológiát alkalmazó termékek anyagjegyzékében (BOM) szereplő cikkek kapcsolatát.

A konfigurációs szabályok dimenzión alapuló konfigurációs modellek definiálásakor érhetők el. A konfigurációs szabályok segítségével megadott cikk-kombinációkat tehet kötelezővé vagy tilthat le egy anyagjegyzékben (AJ). Miután anyagjegyzéket (AJ) hozott létre, és a megfelelő cikkek hozzá lettek rendelve a megfelelő konfigurációs csoportokhoz, egy vagy több konfigurációs szabály adható meg. Ha két elem összetartozik, a **Kiválasztás** operátor használatával biztosítható a felvétel. Ha két cikk kölcsönösen kizárja egymást, a **Kijelölés megszüntetése** operátor használatával biztosítható a kizárás.  

**Megjegyzés:** Ez az információ csak a dimenzión alapuló konfigurációs technológiát használó alaptermékekre vonatkozik.  

A létező konfigurációkra nem vonatkoznak a konfigurációs szabályok későbbi módosításai. Fontos azonban, hogy a szabályokat az új konfiguráció megadása előtt beállítsa, illetve ellenőrizze őket, ha úgy gondolja, hogy módosultak.  

**Megjegyzés:** a **Kijelölés** módszernél a származtatott konfigurációs csoport, cikkszám és konfiguráció automatikusan lesz kiválasztva. A **Kijelölés megszüntetése** módszer használata esetén a származtatott konfigurációs csoport, cikkszám és konfiguráció nem választható ki.

<a name="see-also"></a>Lásd még
--------

[Dimenzión alapuló termékkonfiguráció](dimension-based-product-configuration.md)




