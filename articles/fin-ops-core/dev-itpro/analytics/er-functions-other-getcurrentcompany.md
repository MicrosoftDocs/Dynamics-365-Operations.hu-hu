---
title: GETCURRENTCOMPANY ER-függvény
description: A témakör tájékoztatást nyújt a GETCURRENTCOMPANY Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: c74ffaf1ee134da8d962e054656301d5e99827ff53f560f5d93f9dcb51819c13
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760774"
---
# <a name="getcurrentcompany-er-function"></a>GETCURRENTCOMPANY ER-függvény

[!include [banner](../includes/banner.md)]

A `GETCURRENTCOMPANY` függvény egy olyan *Karakterlánc* értéket ad vissza, amely annak a jogi személynek (vállalat) a kódját képviseli, amelybe egy felhasználó jelenleg be van jelentkezve.

## <a name="syntax"></a>Szintaxis

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="example"></a>Példa

A `GETCURRENTCOMPANY ()` visszaadja az **USMF**-et a **Contoso Entertainment System USA** vállalathoz bejelentkezett felhasználó számára.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]