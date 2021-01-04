---
title: Az üzleti területre jellemző kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott üzleti területre jellemző függvényekről.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 8f7612e83d9f30281e2b1a783275365459e67a40
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686123"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Az üzleti területre jellemző kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentés (ER) üzleti területre jellemző függvényei a Microsoft Dynamics 365 Finance implementációjára vonatkozó számítások és adathozzáférési kérelmek végrehajtására használhatók. Ez a témakör ezeknek a függvényeknek az összefoglalása.

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
