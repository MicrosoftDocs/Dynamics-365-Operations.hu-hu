---
title: QRCODE ER-függvény
description: A témakör tájékoztatást nyújt a QRCODE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: f634976d83fb4066a953b7ab09c963214415e29b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743758"
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
