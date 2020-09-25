---
title: CASE ER-függvény
description: A témakör tájékoztatást nyújt a CASE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 605bd50005ee4e5866a5be9e16df6da3139ad19c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744767"
---
# <a name="case-er-function"></a>CASE ER-függvény

[!include [banner](../includes/banner.md)]

A `CASE` függvény kiértékeli a megadott kifejezés értékét a megadott alternatív beállításokkal, és visszaadja az első beállítás eredményét, amely megegyezik a megadott kifejezés értékével. Ellenkező esetben a nem kötelező alapértelmezett eredményt adja vissza, ha az alapértelmezett eredmény a hívott függvény utolsó argumentumaként van megadva, amelyet nem előz meg beállítás. A visszaadott érték bármely támogatott adattípus értéke lehet.

## <a name="syntax"></a>Szintaxis

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>Argumentumok

`expression`: *Primitív adattípus* (logikai, numerikus vagy szöveg)

Érvényes kifejezés, amely a primitív adattípus értékét adja eredményül.

`option 1`: *Primitív adattípus* (logikai, numerikus vagy szöveg)

Érvényes kifejezés, amely ugyanazt a primitív adattípust adja eredményül, mint a hívott függvény `expression` argumentuma. Az argumentum megadása kötelező.

`result 1`: *A támogatott adattípusok bármelyike*

Az előző beállításnak megfelelő visszaadott eredmény. Az argumentum megadása kötelező.

`option N`: *Primitív adattípus* (logikai, numerikus vagy szöveg)

Érvényes kifejezés, amely ugyanazt a primitív adattípust adja eredményül, mint a hívott függvény `expression` argumentuma. Ez az argumentum nem kötelező.

`result N`: *A támogatott adattípusok bármelyike*

Az előző beállításnak megfelelő visszaadott eredmény. Ez az argumentum nem kötelező.

`default result`: *A támogatott adattípusok bármelyike*

A visszaadott eredmény, ha nincs egyezés. Ez az argumentum nem kötelező.

## <a name="return-values"></a>Visszaadott értékek

*A támogatott adattípusok bármelyike*

Bármely támogatott adattípus eredményül kapott értéke.

## <a name="usage-notes"></a>Használati megjegyzések

Ha nincs egyezés, és nincs megadva alapértelmezett eredmény, a rendszer egy kivételt dob a futtatáskor.

Minden eredményt ugyanazzal az adattípusra kell megadni. Ha a konfigurált eredmények adattípusai nem egyeznek, a tervezési időben kivétel történik.

Ha az első eredmény értéke és az *N*. eredmény értéke a *Tároló (rekord)* vagy a *Rekordlista* adattípus értékei, az eredménynek csak a mindkét értékben létező mezői vannak.

## <a name="example"></a>Példa

A `CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` a **„TÉL”** karakterláncot adja vissza, ha az alkalmazás aktuális munkamenetdátuma október és december között van. Ellenkező esetben üres karakterláncot jelenít meg.

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)
