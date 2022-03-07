---
title: Nem lehet törölni egy kiadott terméket
description: A kiadott termékeket és annak összes változatát csak akkor törölheti, ha a kiadott termékhez nem kapcsolódnak tranzakciók.
author: SmithaNataraj
ms.date: 06/11/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f03d45a36401314a4b02ff354fabb474568c48b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476584"
---
# <a name="you-cant-delete-a-released-product"></a>Nem lehet törölni egy kiadott terméket

## <a name="symptoms"></a>Tünetek

A kiadott termékeket és annak összes változatát csak akkor törölheti, ha a kiadott termékhez nem kapcsolódnak tranzakciók.

## <a name="resolution"></a>Megoldás

A kiadott termék vagy alaptermék törléséhez kövesse az alábbi lépéseket.

1. A cikkek összes nyitott tranzakciójának lezárása.
1. Csökkentse a készletet 0-ra (nulla).
1. Készletzárás végrehajtása.
1. Törölje a törölni kívánt alaptermék összes termékváltozatát.
