---
title: GETENUMVALUEBYNAME ER-függvény
description: A témakör tájékoztatást nyújt a GETENUMVALUEBYNAME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ccf358dc5355cd00d5ff41ebd8148a334cba38
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743855"
---
# <a name="getenumvaluebyname-er-function"></a>GETENUMVALUEBYNAME ER-függvény

[!include [banner](../includes/banner.md)]

A `GETENUMVALUEBYNAME` függvény egy adott *Felsorolás* értéket keres a megadott felsorolási adatforrásban a *Karakterlánc* értékként megadott felsorolási név használatával. Ha a *Felsorolás* értéke megtalálható, a függvény azt visszaadja. Ellenkező esetben a függvény **null** értékű felsorolási értéket ad vissza.

## <a name="syntax"></a>Szintaxis

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argumentumok

`enumeration data source path`: *Felsorolás*

A következő felsorolástípusok egyikéhez tartozó adatforrás érvényes útvonala:

- Elektronikus jelentéskészítési (ER) modell felsorolása
- ER-formátum felsorolása
- Microsoft Dynamics 365 Finance felsorolás

`enumeration value text`: *Karakterlánc*

Egy karakterláncérték, amely egy felsorolási érték nevét jelöli.

## <a name="return-values"></a>Visszaadott értékek

Nullázható *Felsorolás*

Az eredményül kapott felsorolási érték.

## <a name="usage-notes"></a>Használati megjegyzések

Nem történik kivétel, ha a *Felsorolás* érték nem található a *Karakterlánc* értékként megadott felsorolási érték nevével.

## <a name="example"></a>Példa

A következő ábra az adatmodellbe bevezetett **ReportDirection** sorszámozást mutatja be. Vegye figyelembe, hogy a címkék a felsorolási értékekhez vannak megadva.

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

A következő ábrán ezek a részletek láthatók:

- A **$Direction** -adatforrást egy ER-jelentés konfigurálja. Ez az adatforrás a **ReportDirection** modell felsorolása alapján van konfigurálva.
- Az `$IsArrivals` kifejezés a modellfelsorolás-alapú **$Direction** adatforrást a jelen függvény paramétereként használja.
- Az összehasonlító kifejezés értéke **IGAZ**.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)
