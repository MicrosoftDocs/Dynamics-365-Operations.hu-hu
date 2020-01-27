---
title: ORDERBY ER-függvény
description: A témakör tájékoztatást nyújt az ORDERBY Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: a6aed53dcad6d402fc2ca61ae0687016cdb3af5b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916200"
---
# <a name="ORDERBY">ORDERBY ER-függvény</a>

[!include [banner](../includes/banner.md)]

Az `ORDERBY` függvény a megadott listát *Rekordlista* értékként adja vissza, miután a megadott argumentumok szerint rendezésre került. Ezek az argumentumok kifejezésként adhatók meg.

## <a name="syntax"></a>Szintaxis

```
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`expression 1`: *Mező*

Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik. A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie. Az argumentum megadása kötelező.

`expression N`: *Mező*

Az adatforrás egy mezőjének érvényes elérési útja, amelyre a hívott függvény `list` argumentuma hivatkozik. A hivatkozott mezőnek primitív adattípusú mezőnek kell lennie. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="example-1"></a>1. példa

Ha megadja a *Számított mező* típusú **DS** adatforrást és az tartalmazza a `SPLIT ("C|B|A", "|")` kifejezést, akkor a `FIRST( ORDERBY( DS, DS. Value)).Value` kifejezés az **„A”** szöveges értéket adja vissza.

## <a name="example-2"></a>2. példa

Ha **Szállító** a VendTable táblára hivatkozó Elektronikus jelentéskészítési (ER) adatforrásként van konfigurálva, akkor a `ORDERBY (Vendors, Vendors.'name()')` kifejezés megjeleníti a név szerinti növekvő sorrendben rendezett szállítók listáját.

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)
