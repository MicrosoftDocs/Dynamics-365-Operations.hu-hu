---
title: ADDDAYS ER-függvény
description: A témakör tájékoztatást nyújt az ADDDAYS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: 8877bf5a1b6c06e1a25fa9ddaca9c3b039bd2e4d01f39eea9065125977f73e9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740335"
---
# <a name="adddays-er-function"></a>ADDDAYS ER-függvény

[!include [banner](../includes/banner.md)]

Az `ADDDAYS` függvény egy *DateTime* értéket számít ki, amely a megadott számú nappal a megadott kezdési dátum előtt vagy után van.

## <a name="syntax"></a>Szintaxis

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argumentumok

`datetime`: *DateTime*

A kezdő dátumot reprezentáló dátum-/időérték.

`days`: *Egész*

A `datetime` előtti vagy utáni napok száma.

## <a name="return-values"></a>Visszaadott értékek

*DateTime*

Az eredményül kapott dátum-/időérték.

## <a name="usage-notes"></a>Használati megjegyzések

A `days` pozitív értéke egy jövőbeli dátumot eredményez. A negatív érték egy múltbeli dátumot eredményez.

## <a name="example-1"></a>1. példa

Az `ADDDAYS (NOW(), 7)` megjeleníti a hét nappal későbbi dátumot és időpontot.

## <a name="example-2"></a>2. példa

Az `ADDDAYS (NOW(), -3)` megjeleníti a három nappal korábbi dátumot és időpontot.

## <a name="additional-resources"></a>További erőforrások

[Dátum és idő függvények](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]