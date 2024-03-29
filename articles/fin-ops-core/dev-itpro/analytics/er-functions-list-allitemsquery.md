---
title: ALLITEMSQUERY ER-függvény
description: Ez a cikk az ALLITEMSQUERY Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e350dfbe800ddc3e7b1f388fb951d091a283f4e3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285305"
---
# <a name="allitemsquery-er-function"></a>ALLITEMSQUERY ER-függvény

[!include [banner](../includes/banner.md)]

Az `ALLITEMSQUERY` függvény illesztett SQL-lekérdezésként fut. Egy új, összevont *Rekordlista* értéket ad vissza, amely rekordok olyan listájából áll, amely a megadott útvonalnak megfelelő minden rekordot képvisel.

## <a name="syntax"></a>Szintaxis

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>Argumentumok

`path`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja. Legalább egy objektumkapcsolatot kell tartalmaznia.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A megadott elérési utat egy érvényes adatforrás útvonalaként kell megadni a *Rekordlista* adattípus adatforrásához. Legalább egy objektumkapcsolatot is kell tartalmaznia. Adatelemek (például az elérési út *Karakterlánc* és *Dátum* eleme) hibaüzenetet jelenítenek meg az Elektronikus jelentéskészítés (ER) kifejezésszerkesztőben tervezéskor.

Ha ez a függvény olyan *Rekordlista* típusú adatforrásokon kerül alkalmazásra, amelyek olyan alkalmazásobjektumra hivatkoznak, amely az SQL használatával közvetlenül hívható (például tábla, entitás vagy lekérdezés), akkor illesztett SQL-lekérdezésként fut. Ellenkező esetben a memóriában fut, mint az [ALLITEMS](er-functions-list-allitems.md) függvény.

## <a name="example"></a>Példa

A következő adatforrás megadása a modell-hozzárendelésben:

- A *Táblarekordok* típus **CustInv** adatforrása, amely a CustInvoiceTable táblára hivatkozik
- A *Számított mező* típus **FilteredInv** adatforrása, amely a `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")` kifejezést tartalmazza
- A *Számított mező* típus **JourLines** adatforrása, amely a `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)` kifejezést tartalmazza

A modell-leképezés futtatásakor a **JourLines** adatforrás meghívásához a következő SQL-utasítás kerül futtatásra:

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
