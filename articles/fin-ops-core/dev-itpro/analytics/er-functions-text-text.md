---
title: TEXT ER-függvény
description: A témakör tájékoztatást nyújt a TEXT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: c26d0c4c8c6290bd2dbb10a288bbd59941a8d98e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915556"
---
# <a name="TEXT">TEXT ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `TEXT` függvény a megadott számot egy *Karakterlánc* értékként adja vissza, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja.

## <a name="syntax"></a>Szintaxis

```
TEXT (number)
```

## <a name="arguments"></a>Argumentumok

`number`: *Egész* vagy *Valós*

Olyan szám, amelyet szöveges karakterlánccá kell konvertálni.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

A *Valós* típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik.

## <a name="example"></a>Példa

Ha a Microsoft Dynamics 365 Finance példány kiszolgáló területi beállítása **EN-US**, a `TEXT (NOW ())` a jelenlegi Finance munkamenet dátumát (2015. december 17.) **"12/17/2015 07:59:23 AM"** szöveges karakterláncként adja vissza. A `TEXT (1/3)` a **"0.33"** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)