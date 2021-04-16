---
title: TABLENAME2ID ER-függvény
description: A témakör tájékoztatást nyújt a TABLENAME2ID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 0f94d00d9d40830d895e906ffbaa2a236f1efc43
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746555"
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