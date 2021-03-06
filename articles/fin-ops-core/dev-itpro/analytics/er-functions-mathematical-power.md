---
title: POWER ER-függvény
description: A témakör tájékoztatást nyújt a POWER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: ce1f4c735f815c46003ded35156bb47febf177a3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750156"
---
# <a name="power-er-function"></a>POWER ER-függvény

[!include [banner](../includes/banner.md)]

A `POWER` függvény egy *Valós* értéket ad eredményül, amely a megadott pozitív számnak a megadott hatványra történő emelésének eredményét mutatja.

## <a name="syntax"></a>Szintaxis

```vb
POWER (number, power)
```

## <a name="arguments"></a>Argumentumok

`number`: *Valós* vagy *Egész*

Egy numerikus érték, amelyet a megadott hatványra kell emelni.

`power`: *Valós* vagy *Egész*

Az adott hatványt reprezentáló numerikus érték.

## <a name="return-values"></a>Visszaadott értékek

*Valós*

Az eredményül kapott numerikus érték.

## <a name="example-1"></a>1. példa

A `POWER (10, 2)` az **100** értéket adja vissza.

## <a name="example-2"></a>2. példa

A `POWER (4, 0.5)` az **2** értéket adja vissza.

## <a name="additional-resources"></a>További erőforrások

[Matematikai funkciók](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]