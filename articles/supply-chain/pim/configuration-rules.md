---
title: Konfigurációs szabályok
description: Ez a cikk a konfigurációs szabályokkal kapcsolatos általános információkat tartalmazza. A konfigurációs szabályok meghatározzák a dimenzió alapú konfigurációs technológiát alkalmazó termékek anyagjegyzékében (BOM) szereplő cikkek kapcsolatát.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ddc74777ae0cde5367667f93eb29ffb21531e02
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570777"
---
# <a name="configuration-rules"></a>Konfigurációs szabályok

[!include [banner](../includes/banner.md)]

Ez a cikk a konfigurációs szabályokkal kapcsolatos általános információkat tartalmazza. A konfigurációs szabályok meghatározzák a dimenzió alapú konfigurációs technológiát alkalmazó termékek anyagjegyzékében (BOM) szereplő cikkek kapcsolatát.

A konfigurációs szabályok dimenzión alapuló konfigurációs modellek definiálásakor érhetők el. A konfigurációs szabályok segítségével megadott cikk-kombinációkat tehet kötelezővé vagy tilthat le egy anyagjegyzékben (AJ). Miután anyagjegyzéket (AJ) hozott létre, és a megfelelő cikkek hozzá lettek rendelve a megfelelő konfigurációs csoportokhoz, egy vagy több konfigurációs szabály adható meg. Ha két elem összetartozik, a **Kiválasztás** operátor használatával biztosítható a felvétel. Ha két cikk kölcsönösen kizárja egymást, a **Kijelölés megszüntetése** operátor használatával biztosítható a kizárás.  

**Megjegyzés:** Ez az információ csak a dimenzión alapuló konfigurációs technológiát használó alaptermékekre vonatkozik.  

A létező konfigurációkra nem vonatkoznak a konfigurációs szabályok későbbi módosításai. Fontos azonban, hogy a szabályokat az új konfiguráció megadása előtt beállítsa, illetve ellenőrizze őket, ha úgy gondolja, hogy módosultak.  

**Megjegyzés:** a **Kijelölés** módszernél a származtatott konfigurációs csoport, cikkszám és konfiguráció automatikusan lesz kiválasztva. A **Kijelölés megszüntetése** módszer használata esetén a származtatott konfigurációs csoport, cikkszám és konfiguráció nem választható ki.

## <a name="additional-resources"></a>További erőforrások

[Dimenzión alapuló termékkonfiguráció áttekintése](dimension-based-product-configuration.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]