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
ms.openlocfilehash: bac0910d213ee05a2a7a7b218a6714d4f935be16
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916752"
---
# <a name="QRCODE">QRCODE ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `QRCODE` függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód).

## <a name="syntax"></a>Szintaxis

```
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

```
QRCODE (model.ListOfShelfLabels.LabelText)`
```

A konfigurált ER-formátum futtatása esetén a **model.ListOfShelfLabels** adatforrás **LabelText** mezőjének szöveges értéke kerül felhasználásra a QR-kód képének létrehozására. A rendszer erre a képre cseréli le a QR-kód kép helyőrzőjét a kimenő dokumentum létrehozására használt dokumentumsablonban. Amikor a létrehozott dokumentum képe beolvasásra kerül, a függvény visszaadja a **model.ListOfShelfLabels** adatforrás **LabelText** mezőjében szereplő szöveget. További információkért lásd: [Beágyazott képek és alakzatok az ER-rel generált dokumentumokban](electronic-reporting-embed-images-shapes.md)

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)
