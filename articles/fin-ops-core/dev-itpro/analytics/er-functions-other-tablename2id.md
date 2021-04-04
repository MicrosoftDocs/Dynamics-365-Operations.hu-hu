---
title: TABLENAME2ID ER-függvény
description: A témakör tájékoztatást nyújt a TABLENAME2ID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
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
ms.openlocfilehash: 49370af4ebb7552dd3aff4512890fd93fa67c72d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563270"
---
# <a name="tablename2id-er-function"></a>TABLENAME2ID ER-függvény

[!include [banner](../includes/banner.md)]

A `TABLENAME2ID` függvény a megadott táblanév táblaazonosítóját adja vissza *Egész* értékként.

## <a name="syntax"></a>Szintaxis

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Érvényes táblanevet képviselő szöveges érték.

## <a name="return-values"></a>Visszaadott értékek

*Egész*

Az eredményül kapott numerikus érték.

## <a name="usage-notes"></a>Használati megjegyzések

Ennek a funkciónak a végrehajtása különböző eredményeket hozhat a Microsoft Dynamics 365 Finance különböző példányain, még akkor is, ha ugyanazt a vállalatnevet használják.

## <a name="example"></a>Példa

A `TABLENAME2ID ("Intrastat")` az **1510** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]