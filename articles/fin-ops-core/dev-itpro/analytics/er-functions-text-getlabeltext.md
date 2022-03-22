---
title: GETLABELTEXT ER funkció
description: Ez a témakör tájékoztatást nyújt a GETLABELTEXT Elektronikus jelentéskészítés (ER) funkció használatáról.
author: NickSelin
ms.date: 01/04/2022
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
ms.openlocfilehash: 911567a94b80c2b762a37e83d37fc500132edb18
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075751"
---
# <a name="getlabeltext-er-function"></a>GETLABELTEXT ER funkció

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

A`GETLABELTEXT` függvény egy adott címkét keres az a *[Húr](er-formula-supported-data-types-primitive.md#string)* érték, amely a megadott címke fordítását jelenti a megadott nyelven.

## <a name="syntax"></a>Szintaxis

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Argumentumok

### <a name="label-id"></a>Címkeazonosító

`label id`:*Húr* vagy *Címke Id*

Az alábbi címketípusok valamelyikének érvényes azonosítója:

- [Elektronikus jelentéstétel (ER)](general-electronic-reporting.md) címke
- Microsoft Dynamics 365 Finance címke

#### <a name="usage-notes"></a>Használati megjegyzések

Ez az argumentum csak konstansként definiálható a következő támogatott minták valamelyikének használatával:

- ER címkék esetén:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- Pénzügyi címkék esetén:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> Tervezéskor egy érvényesítési hibaüzenet jelenik meg a **[Képlettervező](er-advanced-formula-editor.md)** oldalt, ha nem található címke a megadott címkeazonosító használatával.

### <a name="language"></a>Nyelv

`language`: *Karakterlánc*

Egy nyelvi kódot jelentő karakterlánc.

#### <a name="usage-notes"></a>Használati megjegyzések

Ez az argumentum definiálható szövegállandóként vagy egy adatforrásmező elérési útjaként, amely az a-t adja vissza *Húr* érték.

> [!NOTE]
> Tervezéskor egy érvényesítési hibaüzenet jelenik meg, ha nem található nyelvi kód a megadott használatával`language` argumentum, ha szövegkonstansként definiálták.
>
> Futás közben a fordítás a`EN-US` A rendszer nyelvét a rendszer egy megadott címkéhez adja vissza, ha nem található nyelvi kód a megadott címkével`language` érv.

## <a name="return-values"></a>Visszatérési értékek

*Sztring*

Az eredményül kapott szövegérték.

## <a name="example-1-system-label"></a><a name=example-1></a> 1. példa: Rendszercímke

A kifejezések`GETLABELTEXT (@"SYS70894", "en-us")` és`GETLABELTEXT ("SYS70894", "en-us")` visszaküldi a "Nothing to print" angol fordítást a`@SYS70894` alkalmazási címke.

## <a name="example-2-er-label"></a><a name=example-2></a> 2. példa: ER címke

Elkezdi szerkeszteni az ER-t [konfigurációt](general-electronic-reporting.md#Configuration) az volt [származtatott](er-quick-start2-customize-report.md#DeriveProvidedFormat) tól **ISO20022 Kreditátutalás (DE)** konfigurációt, adja meg az új adatforrást *[Számított mező](er-calculated-field-ds-performance.md)* írja be, és konfigurálja a kifejezést`GETLABELTEXT(@"GER_LABEL:VendorName", "de")` ehhez az adatforráshoz. Ebben az esetben futás közben az adatforrás a „Kreditorenname” német fordítást adja vissza a`@GER_LABEL:VendorName` ER címke, amely eredetileg az alapban volt konfigurálva **ISO20022 Kreditátutalás (DE)** ER konfiguráció.

## <a name="additional-resources"></a>További erőforrások

[Szöveges függvények](er-functions-category-text.md)

[Többnyelvű jelentések tervezése elektronikus jelentésekben](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
