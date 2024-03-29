---
title: Az üzleti területre jellemző kategóriába tartozó ER-függvények listája
description: Ez a cikk az elektronikus jelentéskészítés (ER) által támogatott üzleti tartományspecifikus funkciókkal kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: b1ac46cf10d57b40af1fa99021156ad97a17ba20
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272682"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Az üzleti területre jellemző kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az elektronikus jelentéskészítés tartományspecifikus Microsoft Dynamics funkciói a 365 Pénzügy végrehajtásához szükséges számítások és adatelérési kérelmek elvégzésére használhatók. Ez a témakör összefoglalást nyújt a funkciókról.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció| Leírás |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást MOD10-kifejezésként jelöli, a megadott számlaszám számjegyei alapján. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely egyetlen pénzügyi dimenzióazonosítót jelöl, amely a megadott karakterláncból származik. A megadott karakterlánc az összes dimenziót vesszővel tagolt azonosítólistaként jeleníti meg. |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | Ez a funkció egy *Valós* értéket ad vissza, ami a megadott forráspénzösszeg konvertálását képviseli az eredeti pénznemről a megadott cél pénznemre a megadott vállalat beállításainak használata segítségével a megadott időpontban. |
| [CurCredRef](er-functions-other-curcredref.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást képviseli a megadott számlaszám számjegyei alapján. |
| [FA_Balance](er-functions-other-fabalance.md) | Ez a függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott tárgyieszköz-cikk, értékmodellkód, jelentési év és jelentési dátum tárgyieszköz-egyenlegének adatait tartalmazza. |
| [FA_Sum](er-functions-other-fasum.md) | Ez a függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott tárgyieszköz-cikk, értékmodellkód és dátumperiódusok tárgyieszközösszegének adatait tartalmazza. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | Ez a függvény egy olyan *Karakterlánc* értéket ad vissza, amely annak a jogi személynek (vállalat) a kódját képviseli, amelybe egy felhasználó jelenleg be van jelentkezve. |
| [ISOCredRef](er-functions-other-isocredref.md) | Ez a függvény egy olyan *Karakterlánc* értéket ad vissza, amely egy ISO (International Organization for Standardization ) hitelezői hivatkozást jelenít meg a megadott számlaszám betűi és számjegyei alapján. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | Ez a függvény *logikai* **IGAZ** értéket ad vissza, ha a megadott karakterlánc érvényes nemzetközi bankszámlaszámnak (IBAN) felel meg. Ellenkező esetben **HAMIS** *logikai* eredményt ad. |
| [Mod_97](er-functions-other-mod97.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást MOD97-kifejezésként jelöli, a megadott számlaszám számjegyei alapján. |
| [NumSeqValue](er-functions-other-numseqvalue.md) | Ez a függvény egy *Karakterlánc* értéket ad vissza, amely a megadott számsorozat, hatókör és hatókör-azonosító alapján egy számsorozat új generált értékét jelzi. A hatókör-azonosító egyenlő a vállalati kóddal, amelyet az ER-formátumot futtató kontextus biztosít. |
| [RoundAmount](er-functions-other-roundamount.md) | Ez a függvény egy *Valós* értéket ad eredményül, amely a megadott összeg megadott kerekítési szabály alapján a megadott számú tizedesjegyre való kerekítésének eredményét mutatja. |
| [TableName2ID](er-functions-other-tablename2id.md) | Ez a függvény a megadott táblanév táblaazonosítóját adja vissza *Egész* értékként. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
