---
title: FA_BALANCE ER-függvény
description: A témakör tájékoztatást nyújt a FA_BALANCE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 6a969e3a484208388fd82d7a714bee27b7fe64a9
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744167"
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
