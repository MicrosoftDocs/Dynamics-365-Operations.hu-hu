---
title: GETLABELTEXT ER függvény
description: Ez a cikk a GETLABELTEXT Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 03/18/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: cb3af10d4725e87190f901aa99378e10bdf05bee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877067"
---
# <a name="getlabeltext-er-function"></a>GETLABELTEXT ER függvény

[!include [banner](../includes/banner.md)]

A `GETLABELTEXT` függvény egy adott címkét keres, és olyan Karakterlánc *[értéket ad vissza, amely a](er-formula-supported-data-types-primitive.md#string)* megadott címke fordításának megfelelő, megadott nyelven.

## <a name="syntax"></a>Szintaxis

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Argumentumok

### <a name="label-id"></a>Címkeazonosító

`label id`: Karakterlánc *vagy* *címkeazonosító*

A következő címketípusok egyikének érvényes azonosítója:

- [Elektronikus jelentési (ER)](general-electronic-reporting.md) címke
- Microsoft Dynamics 365 Pénzügyi címke

#### <a name="usage-notes"></a>Használati megjegyzések

Ez az argumentum csak konstansként definiálható a következő támogatott mintát használva:

- ER címkékhez:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- Pénzügyi címkék:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> A tervezéskor egy ellenőrzési hibaüzenet jelenik meg a **[...](er-advanced-formula-editor.md)** képlettervező oldalon, ha a megadott címkeazonosítóval nem található címke.

### <a name="language"></a>Nyelv

`language`: *Karakterlánc*

Nyelvkódot képviselő karakterlánc.

#### <a name="usage-notes"></a>Használati megjegyzések

Ez az argumentum szöveg konstansként vagy karakterlánc típusú értéket eredményül adott adatforrásmező elérési útjaként is *meg lehet* határozni.

> [!NOTE]
> A tervezés ideje alatt ellenőrzési hibaüzenet jelenik meg, `language` ha nem található nyelvkód a megadott argumentum használatával, amikor meg van adva szöveg állandóként.
>
> Futásidőben `EN-US` a rendszernyelv fordítása egy adott címkéhez ad vissza, ha a megadott argumentum használatával nem található nyelvkód `language`.

## <a name="return-values"></a>Visszatérési értékek

*Sztring*

Az eredményül kapott szövegérték.

## <a name="example-1-system-label"></a><a name=example-1></a> 1. példa: Rendszercímke

A kifejezések és `GETLABELTEXT (@"SYS70894", "en-us")``GETLABELTEXT ("SYS70894", "en-us")` visszaadják az alkalmazás címkéje számára a "Nincs nyomtatható" angol fordítást `@SYS70894`.

## <a name="example-2-er-label"></a><a name=example-2></a> 2. példa: ER-címke

Elkezd szerkeszteni egy [ISO20022](general-electronic-reporting.md#Configuration)[...](er-quick-start2-customize-report.md#DeriveProvidedFormat)**jóváírás-átviteli (DE)** konfigurációból származtatott ER-konfigurációt, beír egy új, Számított mezőtípusú *[...](er-calculated-field-ds-performance.md)* adatforrást, `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` és konfigurálja az adatforrás kifejezését. Ebben az esetben futásidőben az adatforrás a német "Kreditorenname" `@GER_LABEL:VendorName` fordítást adja vissza annak az ER-címkének **, amelyet eredetileg az ISO20022 Credit transfer (DE) ER konfigurációban** konfiguráltak.

## <a name="additional-resources"></a>További erőforrások

[Szöveges függvények](er-functions-category-text.md)

[Többnyelvű jelentések tervezése elektronikus jelentésekben](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
