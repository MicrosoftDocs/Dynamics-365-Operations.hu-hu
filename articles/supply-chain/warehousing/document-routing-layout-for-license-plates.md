---
title: Dokumentumirányítás elrendezés azonosítótábla-címkékhez
description: Ez a témakör azt mutatja be, hogyan lehet használni a formázási metódusokat értékek nyomtatásához a címkékre.
author: perlynne
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 8c96aef5d66ed8f8c44d74eee9b60f0a7d38a46d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429855"
---
# <a name="document-routing-layout-for-license-plate-labels"></a>Dokumentumirányítás elrendezés azonosítótábla-címkékhez

[!include [banner](../includes/banner.md)]

A dokumentumirányítási elrendezés határozza meg az azonosítótábla-címkék elrendezését, valamint a rájuk nyomtatandó adatokat. A nyomtatási műveletek aktiválási pontjait a mobileszköz menüelemeiben és a munkasablonok modulban állíthatja be.

Egy tipikus esetben a raktári befogadó adminisztrátorok közvetlenül a fogadó területre érkezett raklapok tartalmának rögzítése után azonnal kinyomtatják az azonosítótábla-címkéket. A fizikai címkék a raklapokra lesznek rögzítve. Ezt követően a következő betárolási műveletek során és a kimenő kitárolási műveletek során is használhatók ellenőrzéshez.

Rendkívül összetett címkéket nyomtathat, feltéve, hogy a nyomtatóeszköz értelmezni tudja a ráküldött szöveget. Például a Zebra Programming Language (ZPL) egy vonalkódot tartalmazó elrendezése a következő példához hasonlíthat.

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

A címke nyomtatási folyamatának részeként a példa szövegét `$LicensePlateId$` egy adatértékkel helyettesíti a program.

A kinyomtatni kívánt értékek megtekintéséhez nyissa meg a **Raktárkezelési \> Lekérdezéseket és a jelentések \> Azonosítótábla-címkék** lehetőséget.

Számos széles körben elérhető címke-létrehozási eszköz segít a szöveg formázásában a címkék elrendezéséhez. Számos ilyen eszköz támogatja a `$FieldName$` formátumot. Mindemellett a Microsoft Dynamics 365 Supply Chain Management speciális formázási logikát használ a dokumentumirányítási elrendezés mező-hozzárendelésének részeként.

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

A rendelkezésre álló számformátum-karakterláncok teljes listája az [Egyéni numerikus formátumú karakterláncok](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings) című témakörben olvasható.

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

A rendelkezésre álló dátum-/időformátumok teljes listája az [Egyéni dátum- és időformátum karakterláncok](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings) című témakörben olvasható.

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

Ez a formátum kombinálható a témakör korábbi részében ismertetett egyéb típusokkal is. Például van egy `DisplayListOfItemsNumbers()` névvel ellátott megjelenítési módja, és ki szeretné nyomtatni a mód első cikkszámát. Ebben az esetben a következő kódot használhatja.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>A címkenyomtatással kapcsolatos további információk

A címkék beállításával és nyomtatásával kapcsolatos további tudnivalókat lásd az [Azonosítótábla-címke nyomtatásának engedélyezése](tasks/license-plate-label-printing.md) című témakört.
