---
title: LISTDISTINCT ER funkció
description: Ez a cikk a LISTDISTINCT Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 07/30/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: cd773f3455af1be1e952cb3852a648436670ce0f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285275"
---
# <a name="listdistinct-er-function"></a>LISTDISTINCT ER funkció

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

A `LISTDISTINCT` funkció kiszámítja a meghatározott kifejezések értékét, mint egy megadott lista minden rekordjához hozzárendelt választó. Ez visszaállít egy új *Rekordlista* értéket, amely egyetlen rekordot tartalmaz minden egyedi választóértékhez.

## <a name="syntax"></a>Szintaxis

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>Argumentumok

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`selector`: *Primitív adattípus*

Egy érvényes kifejezés, amely egy választóérték kiszámítására szolgál minden rekordhoz egy megadott listában.

A következő adattípusok támogatottak ehhez a paraméterhez:

- Logikai
- Dátum
- DateTime
- GUID azonosító
- Egész
- Int64
- Valós
- Karakterlánc

## <a name="return-values"></a>Visszatérési értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A létrehozott lista szerkezete egyezik a megadott lista struktúrájával.

A megadott listában ugyanaz a választóérték kiszámítható több rekordhoz. Ebben az esetben a megfelelő rekord mezőértékei a létrehozott listában megegyeznek az első rekord értékével a megadott listából, amit a választóérték kiszámításra került.

Ennek a funkciónak bármely [Elektronikus jelentéskészítés (ER)](general-electronic-reporting.md) *Rekordlista* típusú adatforrása végrehajtásra kerül, a memória által.

Az a **GROUPBY** adatforrás használható fel rekordok listájának előállítására is, amely egyedi értékű választóértékkel számol. Azonban a teljesítmény és a memóriahasználat szempontjából jobban ajánlott a `LISTDISTINCT` funkció a **GROUPBY** adatforrásnál, mivel a funkció végrehajtása a memóriában történik.

## <a name="example"></a>Példa

A következő példa azt mutatja be, hogyan lehet lekérni azokat az egyedi vevői számlaszámú listákat, amelyek legalább egy értékesítési számlát vagy egy projekt számlát bocsátottak ki egy adott időszakban.

1. Adja meg azt a **SalesInvoice** adatforrást a `Record list` típusból, amely a **CustInvoiceJour** alkalmazástáblára hivatkozik, és szűri az egyes időszakok értékesítési számláit.

    Az `InvoiceAccount` mezője ebből az adatforrásból téríti vissza egy számlázott vevő számlaszámát.

2. Adja meg azt a **ProjectInvoice** adatforrást a `Record list` típusból, amely a **ProjInvoiceJour** alkalmazástáblára hivatkozik, és szűri az egyes időszakok értékesítési számláit.

    Az `InvoiceAccount` mezője ebből az adatforrásból téríti vissza egy számlázott vevő számlaszámát.

3. Adja meg az  **AllInvoices** adatforrást a `Calculated field` típusból, ami a kifejezést tartalmazza `LISTJOIN(SalesInvoice, ProjectInvoice)`.

    Ez az adatforrás téríti vissza az értékesítési számlák és a projekt-számlák összekapcsolt listáját.

4. Adja meg az  **InvoicedCustomer** adatforrást a `Record list` típusból, ami a kifejezést tartalmazza `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.

    Ez az adatforrás egy új listát térít vissza, amely egyetlen rekordot tartalmaz minden olyan egyedi vevőnek, aki a megadott időszakban számlázva lett. A `InvoiceAccount` mezője erről a listáról tartalmaz egy vevői számlaszámot.

## <a name="additional-resources"></a>További erőforrások

[Listafüggvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
