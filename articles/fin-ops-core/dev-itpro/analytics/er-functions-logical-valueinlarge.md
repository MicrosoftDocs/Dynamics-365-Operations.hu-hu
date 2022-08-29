---
title: VALUEINLARGE ER függvény
description: Ez a cikk a VALUEINLARGE Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 08/17/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 425dbce8f229acbb9c8d721c8f1a554989e0533c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288078"
---
# <a name="valueinlarge-er-function"></a>VALUEINLARGE ER függvény

[!include [banner](../includes/banner.md)]

A `VALUEINLARGE` függvény azt határozza meg, hogy a megadott *Int64* vagy *Egész szám* típusú bemenet megegyezik-e a megadott lista valamelyik megadott elemének bármilyen értékével. A függvény egy *Logikai* **IGAZ** értéket ad eredményül, ha a megadott bemenet megegyezik a megadott kifejezésnek a megadott lista legalább egy rekordján való futtatásának eredményével. Ellenkező esetben **HAMIS** *logikai* eredményt ad. A funkcióval való eltérést a `VALUEIN` cikk későbbi [használati megjegyzése](#usage_note) című részében olvashatja.

## <a name="syntax"></a>Szintaxis

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>Argumentumok

`input`: *Mező*

A *Rekordlista* elemtípus adatforrásának érvényes elérési útja. Az elem értékét a rendszer megfelelteti.

`list`: *Rekordlista*

A *Rekordlista* adattípus adatforrásának érvényes elérési útja.

`list item expression`: *Kifejezés*

Egy érvényes feltételes kifejezés, amely a megadott lista egyetlen mezőjére mutat vagy azt tartalmazza, amely a megfeleltetéshez használandó.

## <a name="return-values"></a>Visszatérési értékek

*Logikai*

Az eredményül kapott *Logikai* érték.

## <a name=""></a><a name="usage_note">Használati megjegyzések</a>

Amikor a megadott bemenet egy *Int64* vagy *Egész szám* típusú adatforrás elemként jeleni meg , akkor a hívás egy közvetlen SQL-utasításnak van lefordítva, a megadott lista ideiglenes SQL-táblára lesz alakítva, és egyetlen `EXISTS JOIN` lekérdezés végrehajtásával történik meg a egyeztetés az adatbázisban. Ellenkező esetben ez a függvény a [`VALUEIN`](er-functions-logical-valuein.md) függvénnyel megegyezően működik.

Ha a megadott bemenet egy olyan adatforrás-elemet jelent, amely nem *Int64* vagy *Egész szám* típusú, akkor a tervezéskor hiba történik, ha a `VALUEINLARGE` függvény nem alkalmazható a konfigurált ER kifejezésre.

Ha `VALUEINLARGE` függvénykifejezés végre van hajtva , és a végrehajtásban egynél több ideiglenes tábla van használatban, futásidejű hiba történik.

## <a name="example"></a>Példa

A következő adatforrás megadása a modell-hozzárendelésben:

- A *Táblázatbejegyzés* típus **Tartalmazza** adatforrása.
    - Ez az adatforrás az **Intrastat** táblára hivatkozik.
    - A **Több vállalatot érintő** beállítás **Nem** értékre van állítva.
- A *Számított mező* típus **InMemory** adatforrása.
    - Az adatforrás tartalmazza a `WHERE (In, In.Port <> "")` kifejezést.
- A *Számított mező* típus **InFiltered** adatforrása.
    - Az adatforrás tartalmazza a `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)` kifejezést.

Amikor az adatforrás **InFiltered** vállalat **DEMF** környezetében van meghívva , az alkalmazás-adatbázisban egy új ideiglenes tábla jön létre, akkor a rendszer beilleszti a rekordok azonosító kódjainak a mezőbe történő beolvasását a táblába, és a következő SQL-utasítást hozza létre az **Intrastat** tábla szűrt rekordjainak visszaküldéséhez .

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>További erőforrások

[Logikai függvények](er-functions-category-logical.md)

[VALUEIN függvények](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
