---
title: Dokumentumirányítás címkeelrendezései
description: Ez a témakör azt ismerteti, hogyan lehet a címkékre nyomtatni az értékeket formázási módszerek használatával.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: a4e0c16b71c257cae832870ca58679884047ea16
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708645"
---
# <a name="document-routing-label-layout"></a>Dokumentumirányítás címkeelrendezése

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni elrendezéseket az táblához, tárolóhoz és hullámcímkékhez. Ez a témakör az elrendezések létrehozásához használt programozási nyelv (ZPL) használatával kapcsolatos irányelveket is tartalmaz.

A dokumentumirányítás címkeelrendezései határozzák meg a címkék elrendezését és a címkékre nyomtatandó adatokat. A nyomtatási műveletek aktiválási pontjait a mobileszköz menüelemeiben és a munkasablonok modulban állíthatja be.

Az ebben a cikkben található információ minden dokumentumirányítási címkeelrendezésre érvényes, [így](tasks/license-plate-label-printing.md) az táblacímkék, [...](print-container-labels.md)[a tárolócímkék és a hullámcímkék elrendezésére is vonatkozik](configure-wave-label-printing.md).

Rendkívül összetett címkéket nyomtathat, feltéve, hogy a nyomtatóeszköz értelmezni tudja a ráküldött szöveget. Például egy vonalkódot tartalmazó ZPL-elrendezés hasonló lehet a következő példához.

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

A címke nyomtatási folyamatának részeként a példa szövegét `$LicensePlateId$` egy adatértékkel helyettesíti a program. Számos széles körben elérhető címke-létrehozási eszköz segít a szöveg formázásában a címkék elrendezéséhez. Számos ilyen eszköz támogatja a `$FieldName$` formátumot. Mindemellett a Microsoft Dynamics 365 Supply Chain Management speciális formázási logikát használ a dokumentumirányítási elrendezés mező-hozzárendelésének részeként.

A kinyomtatni kívánt értékek megtekintéséhez nyissa meg a **Raktárkezelési \> Lekérdezéseket és a jelentések \> Azonosítótábla-címkék** lehetőséget.

## <a name="turn-on-this-feature-for-your-system"></a>A funkció bekapcsolása a rendszerhez

Ha a rendszer még nem tartalmazza az ebben a cikkben ismertetett funkciókat, akkor menjen a [Funkciókezeléshez](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), *és kapcsolja be az Táblacímke-elrendezések továbbfejlesztett funkcióját*. (Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni.)

## <a name="custom-number-formats"></a>Egyéni számformátumok

Testreszabhatja a numerikus mezőértékek formátumát, amely a következő formátumú kódokkal van kinyomtatva.

```dos
$FieldName:FormatString$
```

Itt találja a formátum magyarázatát:

- `FieldName` az adatmező neve (például **Mennyiség**).
- `FormatString` azt határozza meg, hogy hogyan kell kinyomtatni az adatokat.

A következő példák azt mutatják be, hogyan lehet testreszabni a munkamennyiség (**Mennyiség**) mezőt:

- Ha azt szeretné, hogy a program mindig négy számjegyet jelenítse meg (nullák használatával helyőrzőként), használja `$Qty:0000$` értéket. Ha például a mennyiség 10, akkor a címkén „0010” jelenik meg.
- Ha mindig két tizedesjegyet kíván megjeleníteni, használja a `$Qty:0.00$` értéket. Ha például a mennyiség 10, akkor a címkén „10.00” jelenik meg.

A rendelkezésre álló számformátum-karakterláncok teljes listája az [Egyéni numerikus formátumú karakterláncok](/dotnet/standard/base-types/custom-numeric-format-strings) című témakörben olvasható.

## <a name="custom-string-formats"></a>Egyéni karakterlánc-formátumok

A karakterlánc első karaktereit a következő mező és a formátumkód használatával lehet eltávolítani.

```dos
$FieldName:#..$
```

Itt a `#` a kihagyandó karakterek számár határozza meg. Például Konténer sorozatszámot (SSCC) szeretne nyomtatni, amely nem tartalmazza az első két karaktert, használja a `$LicensePlateId:2..$` értéket. Ebben az esetben a 0011111111111222221 azonosítótábla-szám „11111111111222221” értékkel lesz nyomtatva.

## <a name="custom-datetime-formats"></a>Egyéni dátum-/időformátumok

A következő példa bemutatja, hogyan lehet szabályozni a dátumok nyomtatásához használt formátumot.

```dos
$PrintedDate:dd-MM-yyyy$
```

Ebben a példában a 2020. április 30-i dátum „30-04-2020” értékkel lesz nyomtatva.

A rendelkezésre álló dátum-/időformátumok teljes listája az [Egyéni dátum- és időformátum karakterláncok](/dotnet/standard/base-types/custom-date-and-time-format-strings) című témakörben olvasható.

## <a name="print-individual-lines-from-multiline-data"></a>Különálló sorok nyomtatása a többsoros adatokból

Ha egy adatmező több sort tartalmaz (azaz a sortöréssel elválasztott sorokat), akkor a következő formátummal nyomtathat egy adott sort.

```dos
$FieldName[#]$
```

Itt `#` annak a sornak a száma, amelyet ki szeretne nyomtatni. (Az első sorhoz az 1 értéket használja)

A rendszere például egy olyan `AdditionalAddress` mezőt tartalmaz, amely a következő többsoros címet tárolja:

Contoso Inc.  
123 Utcanév  
Valamilyen város, Valamilyen állam

Ezt a címet soronként a következő kódokat használva nyomtathatja ki.

| Kód | A nyomtatott szöveg |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 Utcanév |
| `$AdditionalAddress[3]$` | Valamilyen város, Valamilyen állam |

## <a name="print-and-format-from-a-display-method"></a>Nyomtatás és formázás egy megjelenítési módból

A következő formátummal nyomtathat egy megjelenítési módból.

```dos
$DisplayMethod()$
```

Ez a formátum kombinálható a cikk korábbi leírásában ismertetett egyéb típusokkal. Például van egy `DisplayListOfItemsNumbers()` névvel ellátott megjelenítési módja, és ki szeretné nyomtatni a mód első cikkszámát. Ebben az esetben a következő kódot használhatja.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>A címkenyomtatással kapcsolatos további információk

A címkék beállítását és nyomtatását a következő cikkekben talál:

- [Táblacímke nyomtatása](tasks/license-plate-label-printing.md)
- [Tárolócímkék nyomtatása](print-container-labels.md)
- [Hullámcímke nyomtatása](configure-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
