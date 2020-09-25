---
title: MID ER-függvény
description: A témakör tájékoztatást nyújt a MID Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: e2addace5c5606ebaae56ca658700347978a805b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744719"
---
# <a name="mid-er-function"></a>MID ER-függvény

[!include [banner](../includes/banner.md)]

A `MID` függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc adott pozíciójától kiindulva.

## <a name="syntax"></a>Szintaxis

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Egy *Karakterlánc* érték, amely megadja, hogy milyen szövegből legyenek visszaadva karakterek.

`starting position`: *Egész*

Egy *Egész* érték, amely megadja az első karakter pozícióját, amelyet a megadott szövegből vissza kell adni.

`number of characters`: *Egész*

Egy *Egész* érték, amely megadja a visszaadni szánt karakterek számát, a megadott kezdőpozíciótól kiindulva.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha a `starting position` argumentum értéke kisebb, mint 0 (nulla), a visszaadott karakterek a megadott karakterlánc első pozíciójától számítanak.

Ha a `starting position` argumentum értéke meghaladja a megadott karakterlánc hosszát, üres karakterláncot ad eredményül.

## <a name="example"></a>Példa

A `MID ("Sample", 2, 3)` az **„amp”** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)
