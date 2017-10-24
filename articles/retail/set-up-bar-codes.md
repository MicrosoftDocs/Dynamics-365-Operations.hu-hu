---
title: "Vonalkódk beállítása"
description: "Ez a cikk a vonalkódok Microsoft Dynamics 365 for Retail rendszerben történő használatát írja le."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fdc56bf468babd4b0b0652d9791114af676c8470
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-bar-codes"></a>Vonalkódok beállítása

[!include[banner](includes/banner.md)]


Ez a cikk a vonalkódok Microsoft Dynamics 365 for Retail rendszerben történő használatát írja le.

A vonalkódok segítségével beszerzéseket és értékesítéseket is kezelhet, termékváltozatokat követhet nyomon, és vevőket és alkalmazottakat állíthat be. A vonalkódokkal emellett utalványokat, ajándékutalványokat és jóváírásokat adhat ki és hitelesíthet. A kereskedelmi termékekhez szabványos vonalkódok, és egyéni, saját kódolású alkalmazott vonalkódok is beállíthatók. Egy termékhez egynél több vonalkód is tartozhat. Például egy termék több vonalkóddal rendelkezhet, ha különböző gyártóktól származik, vagy ha méret, stílus és szín tekintetében különböző variánsai vannak. A vonalkódok a termék súlyát és árát is magukban foglalhatják. A vonalkódmaszkok a vonalkódok létrehozásához használt sablonok. **Megjegyzés:** Ha az egyes változatokhoz egyedi vonalkódot rendel, akkor a termék vonalkódjának pénztárgépnél történő leolvasásával lehetővé válik, hogy a program megtalálja az éppen értékesített változatot. Emellett ez lehetővé teszi, hogy változatok szerinti értékesítési statisztikát készítsen és jelenítsen meg. Minden egyes méret-, szín- és stíluscsoporthoz egy egyedi szám társítható, amely egy vonalkódba csoportosul. A Dynamics 365 for Retail a vonalkódmaszk segítségével automatikusan előállítja minden egyes változat-kombináció vonalkódját. Ez a funkció hasznos lehet, ha sok méret, szín vagy stílus fordul elő, mivel a kombinációk száma az egyes változatkódok hozzáadásával jelentősen nő. Ha nem használják ezt a funkciót, akkor a vonalkódokat kézzel kell hozzárendelni a termékváltozatot képviselő minden egyes kombinációhoz. A vonalkódokat manuálisan és automatikusan is létre lehet hozni. A vonalkódok létrehozásához kövesse az alábbi feladatokat a megadott sorrendben.

1.  [Vonalkódmaszk-karakterek beállítása](set-up-bar-code-masks.md).
2.  [Vonalkódmaszkok beállítása](set-up-bar-code-masks.md).
3.  Vonalkód-beállítások konfigurálása.
4.  Termékek vonalkódjainak létrehozása.


<a name="see-also"></a>Lásd még
--------

[Vonalkódmaszkok beállítása](set-up-bar-code-masks.md)




