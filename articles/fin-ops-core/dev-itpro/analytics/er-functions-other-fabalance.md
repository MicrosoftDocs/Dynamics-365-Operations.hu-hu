---
title: FA_BALANCE ER-függvény
description: A témakör tájékoztatást nyújt a FA_BALANCE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 37c440a5c626016ebdb75703a2be63c9a1a2b560
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567592"
---
# <a name="fa_balance-er-function"></a>FA_BALANCE ER-függvény

[!include [banner](../includes/banner.md)]

A `FA_BALANCE` függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott tárgyieszköz-cikk, értékmodellkód, jelentési év és jelentési dátum tárgyieszköz-egyenlegének adatait tartalmazza.

## <a name="syntax"></a>Szintaxis

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>Argumentumok

`fixed asset code`: *Karakterlánc*

Egy *Karakterlánc* érték, amely egy olyan tárgyieszköz-cikk kódját jelöli, amelyhez az egyenleg számítása történik.

`value model code`: *Karakterlánc*

Egy *Karakterlánc* érték, amely egy olyan értékmodell kódját jelöli, amelyhez az egyenleg számítása történik.

`reporting year`: *Felsorolási érték*

Az **AssetYear** alkalmazás felsorolási értéke, amely meghatároz egy időszakot az egyenlegszámításhoz.

`reporting date`: *Dátum*

Egy *Dátum* érték, amely meghatározza az egyenleg kiszámításának dátumát.

## <a name="return-values"></a>Visszaadott értékek

*Tároló (rekord)*

Az eredményül kapott rekordérték.

## <a name="example"></a>Példa

A `FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` a **COMP-000001** tárgyieszköz-egyenlegek **Aktuális** értékmodellhez előkészített adattárolóját adja vissza az aktuális alkalmazás-munkamenet dátumán.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]