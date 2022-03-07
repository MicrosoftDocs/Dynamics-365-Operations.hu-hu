---
title: GETENUMVALUEBYNAME ER-függvény
description: A témakör tájékoztatást nyújt a GETENUMVALUEBYNAME Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 09/23/2020
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
ms.openlocfilehash: 03759852e5ceb13b79b0df4592bdcef76eb0a82865725c00df40b9cc5f786240
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774437"
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

## <a name="example-1"></a>1. példa

A következő ábra az adatmodellbe bevezetett **ReportDirection** sorszámozást mutatja be. Vegye figyelembe, hogy a címkék a felsorolási értékekhez vannak megadva.

![Az adatmodell-felsorolásához elérhető értékek.](./media/ER-data-model-enumeration-values.PNG)

A következő ábrán ezek a részletek láthatók:

- A **$Direction** -adatforrást egy ER-jelentés konfigurálja. Ez az adatforrás a **ReportDirection** modell felsorolása alapján van konfigurálva.
- Az `$IsArrivals` kifejezés a modellfelsorolás-alapú **$Direction** adatforrást a jelen függvény paramétereként használja.
- Az összehasonlító kifejezés értéke **IGAZ**.

![Egy adatmodell-felsorolás példája.](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>2. példa

A `GETENUMVALUEBYNAME` és a [`LISTOFFIELDS`](er-functions-list-listoffields.md) funkció lehetővé teszi a támogatott felsorolások értékeinek és címkéinek szöveges értékként történő beolvasását. (A támogatott felsorolások alkalmazás-felsorolások, adatmodell-felsorolások, valamint formátum-felsorolások.)

A következő ábra a modell-leképezésben bevezetett **TransType** adatforrást mutatja be. Ez az adatforrás az **LedgerTransType** alkalmazás-felsorolásra vonatkozik.

![Egy alkalmazás-felsorolásra hivatkozó modell-leképezési adatforrás.](./media/er-functions-text-getenumvaluebyname-example2-1.png)

A következő ábra a modell-leképezésben konfigurált **TransTypeList** adatforrást mutatja be. Ez az adatforrás a **TransType** alkalmazás felsorolása alapján van konfigurálva. A `LISTOFFIELDS` funkció használatával az összes felsorolási érték visszatéríthető mezőket tartalmazó rekordok listájaként. Így az összes felsorolási érték részletei megjeleníthetők.

> [!NOTE]
> Az **EnumValue** mező a **TransTypeList** adatforráshoz a `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` kifejezés használatával van konfigurálva. Ez a mező a lista minden rekordjához egy felsorolási értéket juttat vissza.

![Egy modell-leképezés adatforrása, amely egy kiválasztott felsorolás összes felsorolási értékét rekordok listájaként adja vissza.](./media/er-functions-text-getenumvaluebyname-example2-2.png)

A következő ábra a modell-leképezésben konfigurált **VendTrans** adatforrást mutatja be. Ez az adatforrás szállítói tranzakciórekordokat juttat vissza a **VendTrans** alkalmazástáblából. Minden tranzakció főkönyvi típusát a **TransType** mező értéke határozza meg.

> [!NOTE]
> Az **TransTypeTitle** mező a **VendTrans** adatforráshoz a `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` kifejezés használatával van konfigurálva. Ha elérhető a felsorolási érték, akkor ez a mező szövegként juttatja vissza az aktuális tranzakció felsorolási értékének címkéjét. Ellenkező esetben üres karakterláncértéket jelenít meg.
>
> A **TransTypeTitle** mező egy olyan adatmodell **LedgerType** mezőjéhez van kötve, amely lehetővé teszi, hogy ez az információ minden olyan ER-formátumban használható legyen, amely az adatmodellt adatforrásként használja.

![Szállítói tranzakciókat visszaadó modell-leképezési adatforrás.](./media/er-functions-text-getenumvaluebyname-example2-3.png)

A következő ábra bemutatja, hogyan használható az [adatforrás hibakeresője](er-debug-data-sources.md) a konfigurált modell-leképezés teszteléséhez.

![A konfigurált modell-leképezés tesztelése az adatforrás hibakeresőjének segítségével.](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

Az adatmodell **LedgerType** mezője a várt módon jeleníti meg a tranzakciótípusok címkéit.

Ha nagy mennyiségű tranzakciós adathoz kívánja használni ezt a tervet, akkor figyelembe kell vennie a végrehajtás teljesítményt. További információkért lásd: [Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>További erőforrások

[Szöveges függvények](er-functions-category-text.md)

[Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében](trace-execution-er-troubleshoot-perf.md)

[LISTOFFIELDS ER-függvény](er-functions-list-listoffields.md)

[FIRSTORNULL ER függvény](er-functions-list-firstornull.md)

[WHERE ER-függvény](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]