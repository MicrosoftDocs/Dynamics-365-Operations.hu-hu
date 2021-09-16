---
title: A beépített alaptervezés és a tervezési optimalizálás közötti különbségek
description: Ez a téma azokat a funkciókat sorolja fel, amelyeket a Tervezésoptimalizálás még nem támogat, és amelyek nem szerepelnek a Tervezésoptimalizálás illeszkedéselemzés oldalán.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a102f1d77362f650c060ce5d0aee5b62d2102532
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344954"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>A beépített alaptervezés és a tervezési optimalizálás közötti különbségek

[!include [banner](../../includes/banner.md)]

A Tervezésoptimalizálás eredményei eltérhetnek a beépített főtervező motor eredményeitől. A különbségeket a függőben lévő jellemzők okozhatják. Ez a téma azokat a funkciókat sorolja fel, amelyeket a Tervezésoptimalizálás még nem támogat, és amelyek nem szerepelnek a **[Tervezés Optimalizálás illeszkedéselemzés](planning-optimization-fit-analysis.md)** oldalon].

| Funkció | Jelenlegi viselkedés a tervezés optimalizálásában |
|---|---|
| Fogási súlyú termékek | A fogási súlyú termékek szokásos termékeknek minősülnek.|
| Bővíthető dimenziók | A bővíthető dimenziók üresek a tervezett megrendeléseken, még akkor is, ha a **Tárolási dimenziócsoportok** vagy a **Nyomon követési dimenziócsoportok** lapon be van jelölve a **Fedezeti terv dimenzió szerint** jelölőnégyzet. |
| Szűrt gyártási folyamatok | Részletekért lásd: [Termeléstervezés - Szűrők](production-planning.md#filters). |
| Előrejelzési terv | Az előrejelzés-tervezés nem támogatott. Javasoljuk a főterv használatát, ahol a főtervhez egy előrejelzési modell van hozzárendelve. |
| Számsorozatok a tervezett megrendelésekhez | A tervezett megrendelések számsorozatai nem támogatottak. A tervezett rendelési számok a szolgáltatási oldalon generálódnak. |
| Tervmásolás, terv törlése és tervverzió tisztítás | <p>A navigációs ablaktáblában a következő elemek vannak letiltva a **Főtervezés \> Főtervezés \> Tervek karbantartása** alatt:</p><ul><li>Tervmásolat</li><li>Terv törlése</li><li>Tervezett verzió tisztítása</li></ul> |
| Visszárurendelések | A visszaküldött megrendeléseket nem vesszük figyelembe. |
| Ütemezéssel kapcsolatos funkciók | Részletekért lásd: [Ütemezés végtelen kapacitással](infinite-capacity-planning.md#limitations). |
| Közlekedési naptárak | A szállítási **módok** lapon a **szállítási naptár** oszlopban szereplő értéket figyelmen kívül hagyjuk. |

## <a name="additional-resources"></a>További erőforrások

- [A Tervezési optimalizálás igazítási elemzése](planning-optimization-fit-analysis.md)
- [A Tervezési optimalizálás által nem használt paraméterek](not-used-parameters.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]