---
title: "Kézi értékcsökkenés"
description: "Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e0648d7f89b3e3a1f8fee6501ceb7443be16aa1a
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="manual-depreciation"></a>Kézi értékcsökkenés

[!include[banner](../includes/banner.md)]


Ez a cikk az értékcsökkenés felhasználási módszeréről nyújt áttekintést.

Amikor beállítja egy tárgyi eszköz értékesítési profilját és kijelöli a **Manuális** opciót a **Metódus** mezőben az **Értékcsökkenési profilok** lapon, akkor az értékcsökkenési profilhoz rendelt tárgyi eszközök értékcsökkenése az alapján a százalék alapján van meghatározva, amelyet megad az egyes időintervallumokhoz a naptári évben. Az időközök, amelyekhez százalékokat ad meg feladásra kerülnek azon értéknek megfelelően, amit az **Értékcsökkenési profilok** lap **Általános** gyorslapján az **Időszak-gyakoriság** mezőben meghatároz. Itt szerepelnek a kiválasztható értékek:

-   Évente
-   Havonta
-   Negyedévente
-   Féléves
-   Napi

Miután kijelöli az időszak-gyakoriságot kattintson a **Kézi ütemezések** gombra és állítsa be a százalékokat az egyes feladási intervallumokhoz. A kézi ütemezések és a feladási intervallumok közösen meghatározzák az értékcsökkenés összegét, úgy ahogy az ebben a cikkben szereplő példák később bemutatják. A kézi értékcsökkenés mindig a beszerzési ár egy százalékaként számítandó. Kézi értékcsökkenés esetén az Ön által az értékcsökkenés intervallumaiban megadott százalékok összegének nem kell 100 százaléknak lennie. A kézi értékcsökkenés egy rugalmas értékcsökkenési mód, amely gyakran használatos rendkívüli értékcsökkenési profilok meghatározásához a **Könyvek** lapon, úgy mint egy nem periodikus értékcsökkenés különleges célokra (mint például adó).

## <a name="examples"></a>Példák
Beszerzési ár: 11 000,00 Várható maradványérték: 1 000,00 A következő táblázat mutatja az időintervallumokat és százalékokat, amelyek Ön beállít a **Tárgyi eszköz értékcsökkenési profiljának ütemezései** lapon.

| Időköz száma | Százalék |
|-----------------|------------|
| 1               | 10,00      |
| 2               | 50,00      |
| 3               | 8,00       |

A következő táblázat mutatja, az értékcsökkenés számítását az egyes intervallumokra.

|  Időköz száma | Az éves értékcsökkenés-összeg számítása | Nettó könyv szerinti érték az intervallum végén |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11 000-1 000) × 10% = 1 000                | 10 000 × (11 000-1 000)                   |
| 2                | (11 000-1 000) × 50% = 5 000                | 5 000 × (10 000-5 000)                    |
| 3                | (11 000-1 000) × 8% = 800                   | 4 200 (5 000-800)                       |

Ha kiválasztja a **Havi** lehetőséget az**Időszak gyakoriság** mezőben, akkor 12 kézi ütemezési intervallum jön létre. A következő táblázat mutatja az értékcsökkenés-összegeket az első két időszakra.

| Intervallum | Értékcsökkenés összege            |
|----------|--------------------------------|
| Január  | (11 000-1 000) × 10% = 1 000 |
| Február | (11 000-1 000) × 50% = 5 000 |

Ha a **Féléves** lehetőséget választja az ****Időszak-gyakoriság** mezőben**, akkor 2 kézi ütemezési intervallum jön létre. A következő táblázat mutatja az értékcsökkenés-összegeket ezekhez az időszakokhoz.

| Intervallum    | Értékcsökkenés összege            |
|-------------|--------------------------------|
| június 30.     | (11 000-1 000) × 10% = 1 000 |
| december 31. | (11 000-1 000) × 50% = 5 000 |

Az intervallumokban megadott százalékoknak nem kell 100-at kiadniuk. Azonban üzenetet kap, ha a **Halmozott százalékos érték** mezőben a **Tárgyi eszköz értékcsökkenési profiljának ütemezései** lapon az érték nem **100**.




