---
title: IF ER-függvény
description: A témakör tájékoztatást nyújt az IF Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bd0a7181b441a0a00163b31d4f1116c8bad0705a7f3b52a2985f1b31ecdb28b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745210"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]