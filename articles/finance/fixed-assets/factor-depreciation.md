---
title: Értékcsökkenési tényező
description: Ez a cikk az tényezős értékcsökkentési módszerről nyújt áttekintést.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c36441e926cd5a82c802a350adf6b2ed6d6387
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443916"
---
# <a name="factor-depreciation"></a>Értékcsökkenési tényező

[!include [banner](../includes/banner.md)]

Ez a cikk az tényezős értékcsökkentési módszerről nyújt áttekintést.

A szorzók a tárgyi eszközök értékcsökkenéséhez használt százalékos értékek. Ha az értékcsökkenési profilok beállítása során a **Mód** mezőjében a **Szorzó** értéket választja az **Értékcsökkenési profilok** oldalon, akkor növekvő, csökkenő vagy lineáris értékcsökkenést állíthat be:

-   Ha a növekvő értékcsökkenést választja, akkor az értékcsökkenés összege minden értékcsökkenési időszakban emelkedik.
-   Ha csökkenő értékcsökkenést állít be, akkor az értékcsökkenés időszakonkénti összege mindig csökken.
-   Ha lineáris értékcsökkenést választja, akkor az értékcsökkenés minden időszakban ugyanannyi.

Az itt következő szabályok és példák bemutatják, hogyan kell beállítani a szorzókat az értékcsökkenés különböző típusaihoz. 

> [!NOTE] 
> Megjegyzés: Ha a **Szorzó** értéket választja a **Mód** mezőben, megjelenik a **Szorzó** és az **Intervallum** mező.

## <a name="progressive-depreciation"></a>Növekvő értékcsökkenés
A **Szorzó** mezőben szereplő érték nagyobb mint **50**.

### <a name="example"></a>Példa

A beszerzési ár 100 000, a szorzó 70, az élettartam 10 év, és az értékcsökkenés január 1-jén indul. Az értékcsökkenési összegek és a nettó könyv szerinti érték csak az élettartam első hat évében láthatók.

| Év | Időszak      | Értékcsökkenés összege | Nettó könyv szerinti érték összege |
|------|-------------|---------------------|-----------------------|
| 1    | december 31. | 307,69              | 99 692,31             |
| 2    | december 31. | 1447,21            | 98 245,10             |
| 3    | december 31. | 3 104,50            | 95 140,60             |
| 4    | december 31. | 5 150,21            | 89 990,39             |
| 5    | december 31. | 7 522,95            | 82 467,44             |
| 6    | december 31. | 10 184,06           | 72 283,38             |

## <a name="digressive-depreciation"></a>Csökkenő értékcsökkenés
A **Szorzó** mezőben szereplő érték kisebb, mint **50**.

### <a name="example"></a>Példa

A beszerzési ár 100 000, a szorzó 20, az élettartam 10 év, és az értékcsökkenés január 1-jén indul. Az értékcsökkenési összegek és a nettó könyv szerinti érték csak az élettartam első hat évében láthatók.

| Év | Időszak      | Értékcsökkenés összege | Nettó könyv szerinti érték összege |
|------|-------------|---------------------|-----------------------|
| 1    | december 31. | 56 080,43           | 43 919,57             |
| 2    | december 31. | 10 665,70           | 33 253,87             |
| 3    | december 31. | 7 156,22            | 26 097,65             |
| 4    | december 31. | 5 538,06            | 20 559,59             |
| 5    | december 31. | 4 579,89            | 15 979,70             |
| 6    | december 31. | 3 937,36            | 12 042,34             |

## <a name="straight-line-depreciation"></a>Lineáris értékcsökkenés
A **Szorzó** mezőben szereplő érték egyenlő az **50** értékkel. Ebben az esetben az értékcsökkenés minden időszakban ugyanannyi, és ajánlott figyelembe venni a többi mezőben megadott beállítás következményeit, az [Élettartam alatti lineáris értékcsökkenés](straight-line-service-life-depreciation.md) témakörben leírtaknak megfelelően.



