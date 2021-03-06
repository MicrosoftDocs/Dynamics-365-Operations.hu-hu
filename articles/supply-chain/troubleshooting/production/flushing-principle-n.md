---
title: Az anyagjegyzéksorok ürülési elvének beállításai nem teljesülnek
description: Az anyagjegyzék (BOM) sorok ürülési elvének beállításai nem teljesülnek.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026577"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a>Az anyagjegyzéksorok ürülési elvének beállításai nem teljesülnek

Tudásbáziscikk száma: 4612725

## <a name="symptoms"></a>Tünetek

Eza problémára akkor merül fel, ha a **Termelésvezérlés paraméterei** oldal **Automatikus frissítés** lapjának **Automatikus anyagjegyzék-felhasználás** mezője *Ürülési elv* értékre van beállítva. Ez a beállítás azt jelzi, hogy minden anyagjegyzék (BOM) sorok automatikusan fel vannak használva, ha beszerzési rendelés érkezik. Ha az anyagjegyzéksorok **Ürülési elv** mezője kifejezetten *Manuális* beállítású, akkor arra lehet számítani, hogy az anyagjegyzéksorok nem lesznek automatikusan felhasználva. Amikor azonban bekövetkezik ez a probléma, azok az Anyagjegyzéksorok, amelyekben az **Ürülési elv** mező beállítása *Manuális*, automatikusan felhasználja a program.

## <a name="resolution"></a>Felbontás

Ha ezt a problémát tapasztalja, előfordulhat, hogy a termelésellenőrzés paraméterei úgy vannak beállítva, hogy felülbírálja az anyagjegyzéksorok **Ürülési elv** beállítását. A **Gyártásvezérlés paraméterei** lapon, az **Automatikus frissítés** lapon ellenőrizze az **Automatikus anyagjegyzék-felhasználás** mező értékét. Ha a beállítás *Mindig*, a rendszer figyelmen kívül hagyja az összes anyagjegyzéksor **Ürülési elv** beállítását, és mindig üríti a sorokat. Ha azt szeretné, hogy a rendszer tiszteletben tartsa az **Ürülési elv** beállítást az anyagjegyzéksorokon, módosítsa az **Automatikus anyagjegyzék felhasználás** mezőt *Ürülési elv* értékre.
