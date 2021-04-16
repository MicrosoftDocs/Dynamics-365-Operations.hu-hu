---
title: QRCODE ER-függvény
description: A témakör tájékoztatást nyújt a QRCODE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 6a76549ba5d663a7b6cfb858342a56921c5cd56b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746171"
---
# <a name="qrcode-er-function"></a>QRCODE ER-függvény

[!include [banner](../includes/banner.md)]

A `QRCODE` függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód).

## <a name="syntax"></a>Szintaxis

```vb
QRCODE (text)
```

## <a name="arguments"></a>Argumentumok

`text`: *Karakterlánc*

Az eredeti szöveget jelölő *Karakterlánc* érték.

## <a name="return-values"></a>Visszaadott értékek

*Konténer*

Az eredményül kapott bináris adatfolyam.

## <a name="example"></a>Példa

Az Elektronikus jelentéskészítési (ER) formátumot beállíthatja úgy, hogy a kimenő dokumentumot Microsoft Office-formátumban (Excel-munkafüzet vagy Word-dokumentum) hozza létre egy előre definiált sablonnal. Ez a sablon tartalmazhat egy **Kép** objektumot (Excel-munkafüzet) vagy egy **Képtartalom-vezérlőelemet** (Word-dokumentum) helyőrzőként a QR-kód képhez. A konfigurált ER-formátumhoz hozzá kell adni egy olyan **Cella** elemet, amelyet a program a helyőrző kitöltésére használ. A QR-kódban tárolható adatok meghatározásához kötést kell definiálnia ehhez a **Cella** elemhez. Például a következő kifejezést tartalmazó kötést lehet konfigurálni:

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

A konfigurált ER-formátum futtatása esetén a **model.ListOfShelfLabels** adatforrás **LabelText** mezőjének szöveges értéke kerül felhasználásra a QR-kód képének létrehozására. A rendszer erre a képre cseréli le a QR-kód kép helyőrzőjét a kimenő dokumentum létrehozására használt dokumentumsablonban. Amikor a létrehozott dokumentum képe beolvasásra kerül, a függvény visszaadja a **model.ListOfShelfLabels** adatforrás **LabelText** mezőjében szereplő szöveget. További információkért lásd: [Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]