---
title: EMPTYRECORD ER-függvény
description: A témakör tájékoztatást nyújt az EMPTYRECORD Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d50b31fcbbb99050fca46b0a5ce10cc3fd243691
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684811"
---
# <a name="emptyrecord-er-function"></a>EMPTYRECORD ER-függvény

[!include [banner](../includes/banner.md)]

Az `EMPTYRECORD` függvény egy nulla *Tároló (rekord)* értéket ad vissza, amely ugyanazzal a struktúrával rendelkezik, mint a megadott rekordlista vagy rekord.

## <a name="syntax"></a>Szintaxis

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista* vagy *Tároló (rekord)*

A *Rekordlista* vagy *Tároló (rekord)* típusú adatforrás érvényes elérési útja.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="usage-notes"></a>Használati megjegyzések

> [!NOTE] 
> A null rekord olyan rekord, amelyben minden mezőhöz üres érték tartozik. Az üres érték **0** (nulla) a számok esetén, üres karakterlánc a karakterláncoknál stb.

## <a name="example"></a>Példa

A `EMPTYRECORD (SPLIT ("abc", 1))` új üres rekordot ad vissza, amelynek ugyanolyan szerkezete van, mint a `SPLIT` funkció által megjelenített listának. További tudnivalók: [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>További erőforrások

[Rekord függvények](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]