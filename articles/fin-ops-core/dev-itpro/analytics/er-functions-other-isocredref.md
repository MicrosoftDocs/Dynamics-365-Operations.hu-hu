---
title: ISOCREDREF ER-függvény
description: A témakör tájékoztatást nyújt az ISOCREDREF Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 51adc6392b07ba4061a475f3072fb35452f15ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748317"
---
# <a name="isocredref-er-function"></a>ISOCREDREF ER-függvény

[!include [banner](../includes/banner.md)]

Az `ISOCREDREF` függvény egy olyan *Karakterlánc* értéket ad vissza, amely egy ISO (Nemzetközi Szabványügyi Szervezet) hitelezői hivatkozást jelenít meg a megadott számlaszám betűi és számjegyei alapján.

## <a name="syntax"></a>Szintaxis

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argumentumok

`invoice number digits`: *Karakterlánc*

A számlaszámok számjegyeit jelölő szöveges érték.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

> [!NOTE] 
> A nem ISO-szabványos betűkből származó szimbólumok eltávolításához az `invoice number digits` argumentumokat le kell fordítani a függvénynek történő megfeleltetés előtt.

## <a name="example"></a>Példa

Az `ISOCredRef ("VEND-200002")` a **"RF23VEND-200002"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]