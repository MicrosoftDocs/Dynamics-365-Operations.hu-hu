---
title: LISTOFFIELDS ER-függvény
description: A témakör tájékoztatást nyújt a LISTOFFIELDS Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 1d15649aed4343f2ed9192834047a17e273e29f190aa83c386bebe7857b47908
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761488"
---
# <a name="listoffields-er-function"></a>LISTOFFIELDS ER-függvény

[!include [banner](../includes/banner.md)]

A `LISTOFFIELDS` függvény egy *Rekordlista*-értéket ad vissza, amely a *Felsorolás* vagy a *Tároló (rekord)* típus megadott argumentumának szerkezete alapján jön létre.

## <a name="syntax-1"></a>Szintaxis 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>Argumentumok

`path`: Adatforrás hivatkozása

A következő adattípusok egyikéhez tartozó adatforrás érvényes hivatkozási útvonala:

- Modellfelsorolás
- Formátumok felsorolása
- Alkalmazásfelsorolás
- Tároló (rekord)

`language`: *Karakterlánc*

Nyelvkódot jelölő szöveg.

## <a name="return-values"></a>Visszaadott értékek

*Rekordlista*

A rekordok eredményül kapott listája.

## <a name="usage-notes"></a>Használati megjegyzések

A létrehozott lista olyan rekordokból áll, amelyek a következő mezőket tartalmazzák:

- **Név** (*Karakterlánc* adattípus)
- **Címke** (*Karakterlánc* adattípus)
- **Leírás** (*Karakterlánc* adattípus)
- **IsTranslated** (*Logikai* adattípus)

Ha a `path` argumentum egy *Tároló (rekord)* típusú adatforrásra hivatkozik, akkor a hivatkozott tárolórekord minden mezőjéhez új bejegyzés kerül hozzáadásra a létrehozott listára. Minden létrehozott rekord esetén a **Név** mező annak a hivatkozott tárolórekordnak a nevét adja vissza, amelyhez az aktuális rekord készült.

Ha a `path` argumentum a *Felsorolás* típusú adatforrások egyikére hivatkozik, akkor a hivatkozott felsorolás minden felsorolási értékéhez új bejegyzés kerül hozzáadásra a létrehozott listára. A **Név** mező minden létrehozott rekord esetében visszaadja a hivatkozott felsorolást, amelyhez az aktuális rekord létrehozásra került. A **Leírás** mező a felsorolás leírását, a **Címke** mező pedig a felsorolás címkéjét adja eredményül.

Futásidőben, ha az 1-es szintaxist használja, a **Címke** és a **Leírás** mezőknek a futó Elektronikus jelentési (ER) formátum nyelvi beállításain alapuló visszaadott értéket kell eredményül adniuk:

- Ha a kért nyelv címkéi és leírása rendelkezésre állnak, a **Címke** és a **Leírás** mezők a nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig az **Igaz** értéket adja vissza.
- Ha a kért nyelv címkéi és leírása nem állnak rendelkezésre, a **Címke** és **Leírás** mezők az alapértelmezett **EN-US** nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig a **Hamis** értéket adja vissza.

Futásidőben, ha az 2-es szintaxist használja, a **Címke** és a **Leírás** mezőknek a meghívott függvény második argumentumaként megadott nyelven alapuló visszaadott értéket kell eredményül adniuk:

- Ha a kért nyelv címkéi és leírása rendelkezésre állnak, a **Címke** és a **Leírás** mezők a nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig az **Igaz** értéket adja vissza.
- Ha a kért nyelv címkéi és leírása nem állnak rendelkezésre, a **Címke** és **Leírás** mezők az **EN-US** nyelven alapuló értékeket adnak eredményül, az **IsTranslated** mező pedig a **Hamis** értéket adja vissza.

## <a name="example-1"></a>1. példa

A következő ábra az ER-adatmodellbe bevezetett sorszámozást mutatja be.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

A következő ábrán ezek a részletek láthatók:

- A modell felsorolása adatforrásként kerül be egy jelentésbe.
- Az ER kifejezés a modellfelsorolást a `LISTOFFIELDS` függvény paramétereként használja.
- A *Rekordlista* típus adatforrása beillesztésre kerül egy jelentésbe a létrehozott ER-kifejezés használatával.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

A következő példa azokat az ER formázási elemeket mutat be, amelyek ahhoz a *Rekordlista* típusú adatforráshoz vannak kötve, amelyet a `LISTOFFIELDS` függvénnyel hoztak létre.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> A címkék és leírások fordított szövege az ER formátumú kimenetbe kerül bevitelre, a szülő **FILE** és **FOLDER** formátumelemekhez konfigurált nyelvi beállításainak megfelelően.

## <a name="example-2"></a>2. példa

Használhatja a *Számított mező* adatforrástípust az **enumType\_de** és **enumType\_deCH** adatforrásoknak az **enumType** adatmodell-felsoroláshoz való konfigurálására:

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

Ebben az esetben a következő kifejezést használhatja a felsorolási érték címkéjének svájci német nyelven történő lekéréséhez, ha ez a fordítás elérhető. Ha a svájci német fordítás nem érhető el, a címke németül szerepel.

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>További erőforrások

[Lista függvények](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]