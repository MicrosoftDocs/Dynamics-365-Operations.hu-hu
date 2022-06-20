---
title: ISOCREDREF ER-függvény
description: Ez a cikk az ISOCREDREF Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: dcbd53ec1939e6fb4bcd829bad01b353e823795a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896763"
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