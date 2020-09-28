---
title: IF ER-függvény
description: A témakör tájékoztatást nyújt az IF Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87e252a2751beeecb51e512cae38b271c1456fae
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744695"
---
# <a name="if-er-function"></a>IF ER-függvény

[!include [banner](../includes/banner.md)]

Az `IF` függvény az első megadott értéket adja vissza a megadott feltétel teljesülése esetén. Ellenkező esetben a második megadott értéket adja vissza. A visszaadott érték bármely támogatott adattípus értéke lehet.

## <a name="syntax"></a>Szintaxis

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>Argumentumok

`condition`: *Logikai*

Érvényes feltételes kifejezés, amelyet tesztelni kell.

`first value`: *A támogatott adattípusok bármelyike*

A feltétel teljesülése esetén visszaadott eredmény.

`second value`: *A támogatott adattípusok bármelyike*

A feltétel nem teljesülése esetén visszaadott eredmény.

## <a name="return-values"></a>Visszaadott értékek

*A támogatott adattípusok bármelyike*

Bármely támogatott adattípus eredményül kapott értéke.

## <a name="usage-notes"></a>Használati megjegyzések

A `first value` és `second value` argumentumokat ugyanazzal az adattípussal kell megadni. Ha a konfigurált értékek adattípusai nem egyeznek, a tervezési időben kivétel történik.

Ha az első érték és a második érték és a *Tároló (rekord)* vagy a *Rekordlista* adattípus értékei, az eredménynek csak a mindkét értékben létező mezőkkel rendelkezik.

## <a name="example"></a>Példa

Az `IF (1=2, "condition is met", "condition is not met")` a **„feltétel nem teljesül”** karakterláncot adja eredményül.

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)
