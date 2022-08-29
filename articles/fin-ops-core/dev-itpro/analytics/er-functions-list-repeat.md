---
title: ER funkció ISMÉTLÉSE
description: Ez a cikk az REPEAT Electronic Reporting (ER) funkció használatával kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 08/01/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-06-01
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: c56139a3c63b03f907b1dcbf4365990d2a13c35a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220723"
---
# <a name="repeat-er-function"></a>ER funkció ISMÉTLÉSE

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

A `REPEAT` függvény egy rekordot épít ki, amely tartalmazza a mezőt, amelynél a megadott adatbevitelnek megfelelő érték található. Ezután egy adott számú alkalommal *ismétlődő* rekord új rekordlistát ad vissza.

## <a name="syntax"></a>Szintaxis

```vb
REPEAT (item, number)
```

## <a name="arguments"></a>Argumentumok

`item`: Bármely támogatott egyszerű [vagy](er-formula-supported-data-types-primitive.md) [összetett](er-formula-supported-data-types-composite.md) adattípus

Az ismétléshez megadott érték.

`number`: *Egész*

Az ismétlések száma.

## <a name="return-values"></a>Visszatérési értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A visszaadott ismétlődő rekordok listája a következő mezőket tartalmazza:

- A megadott érték (`Item` mező)
- Az aktuális rekordindex (`Number` mező)

> [!NOTE]
> Mivel ehhez a funkcióhoz egy alapú számozás használatos, `Number`**a kapott lista első rekordja 1** értéket tartalmazza.

Ezzel a [funkcióval megszorozhatja a meglévő adatokat, hogy a Regression suite automatizálási eszközével (RSAT) a teljesítmény- és térfogattesztelést el tudja látni az elektronikus jelentéskészítő (ER)](general-electronic-reporting.md)[megoldásokon](../perf-test/rsat/rsat-overview.md).

## <a name="example"></a>Példa

OLYAN XML-formátumú `Party` dokumentumot szeretne létrehozni, amely annyi XML-elemet tartalmaz, amennyit futásidőben a párbeszédpanel adatbeviteli mezőjében meghatároz, mielőtt az ER-formátum elkezdődne.

A következő ábra az ER-formátumot mutatja [be](er-overview-components.md#format-component). Ebben a formátumban az egyetlen XML-elem `Party` hozzáadódik egyetlen fél tulajdonságainak elérhetővé.

<a href="./media/er-repeat-function-1.png"><img src="./media/er-repeat-function-1.png" alt="Format structure on the Format tab of the Format designer page." class="alignnone size-full" width="929" height="548" /></a>

A következő ábra a következő konfigurált adatforrásokat mutatja be:

- Az `Party` az adatforrás, amely egy felet képvisel. A `Party.Value` mező egyetlen szöveges értékhez ad meg értéket.
- Az `NumberOfRepeats`[az adatforrás](er-user-input-parameter-data-sources.md), amely futásidőben kínál egy adatbeviteli mezőt a párbeszédpanelen, így megadhatja, hogy hány felet kell megadni a generált dokumentumban.
- Az `Party2` adatforrás, amely az adatforrásban `Party``NumberOfRepeats` megadott számmal ismétli a rekordot.

<a href="./media/er-repeat-function-2.png"><img src="./media/er-repeat-function-2.png" alt="Configured data sources on the Mapping tab of the Format designer page." class="alignnone size-full" width="1044" height="411" /></a>

A következő ábra a kimenet XML-formátumú előállításához létrehozott szerkeszthető ER-formátum adatkötését mutatja be. Ez a kimenet az egyes feleket enumerált csomópontként mutatja.

<a href="./media/er-repeat-function-3.png"><img src="./media/er-repeat-function-3.png" alt="Configured data bindings on the Mapping tab of the Format designer page." class="alignnone size-full" width="1051" height="417" /></a>

A következő ábra a tervezett formátum futtatásakor `NumberOfRepeats`**látható, az adatforrás értéke pedig 5**.

<a href="./media/er-repeat-function-4.png"><img src="./media/er-repeat-function-4.png" alt="Result of running the format on a new web browser tab." class="alignnone wp-image-290711 size-full" width="400" height="380" /></a>

## <a name="additional-resources"></a>További erőforrások

[Listafüggvények](er-functions-category-list.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
