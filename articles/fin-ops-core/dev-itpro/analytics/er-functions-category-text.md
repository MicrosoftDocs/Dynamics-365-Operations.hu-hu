---
title: A szöveges kategóriába tartozó ER-függvények listája
description: Ez a cikk az elektronikus jelentés (ER) által támogatott szöveges funkciókkal kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 502a68d51705114adc096a1cd2217210f4e925bb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885543"
---
# <a name="list-of-er-functions-of-the-text-category"></a>A szöveges kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) szövegfüggvényei a *Karakterlánc* típusú adattípusok adatforrásokon történő műveletek végrehajtására használhatók. Ez a témakör összefoglalást nyújt a funkciókról.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [Char](er-functions-text-char.md) | Ez a függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik. |
| [Összefűzés](er-functions-text-concatenate.md) | Ez a függvény az összes megadott karakterláncot *Sztring* értékként adja vissza, miután egy karakterláncba lettek egyesítve. |
| [Formátum](er-functions-text-format.md) | Ez a függvény a megadott karakterláncot egy *Karakterlánc* értékként adja vissza, miután az **%N** minden előfordulását az *N*. argumentummal helyettesítve formázza. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Ez a függvény egy adott *Felsorolás* értéket keres a megadott felsorolási adatforrásban a *Karakterlánc* értékként megadott felsorolási név használatával. Ha a *Felsorolás* értéke megtalálható, a függvény azt visszaadja. |
| [GetLabelText](er-functions-text-getlabeltext.md) | Ez a funkció megkeres egy konkrét címkét, és olyan Karakterlánc *[értéket ad vissza, amely a](er-formula-supported-data-types-primitive.md#string)* megadott címke adott nyelven megadott fordításának megfelelő. |
| [GuidValue](er-functions-text-guidvalue.md) | Ez a függvény a megadott *Karakterlánc* típusú bemenetet *GUID* típusú adatelemmé konvertálja. |
| [JsonValue](er-functions-text-jsonvalue.md) | Ez a funkció elemzi az adatokat a megadott elérési úton elérhető JavaScript Object Notation (JSON) formátumban, a megadott azonosítón alapuló skaláris érték kibontásához. Ezután *Karakterlánc* értékként adja vissza a kivont skaláris értéket. |
| [Balra](er-functions-text-left.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc kezdete után. |
| [Len](er-functions-text-len.md) | Ez a függvény olyan *Egész* értéket ad vissza, amely a karakterek számát mutatja a megadott karakterláncban. |
| [Lower](er-functions-text-lower.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program kisbetűssé alakította. |
| [Mid](er-functions-text-mid.md) | Ez a függvény olyan *[Sztring](er-formula-supported-data-types-primitive.md#string)* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc adott pozíciójától kiindulva. |
| [NewGUID](er-functions-text-newguid.md) | Ez a függvény egy újonnan létrehozott *[GUID](er-formula-supported-data-types-primitive.md#guid)* értéket ad eredményül. |
| [NumberFormat](er-functions-text-numberformat.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott számot, miután kiírta (azaz szöveges karakterlánccá konvertálta) a megadott nyelven. |
| [PadLeft](er-functions-text-padleft.md) | Ez a funkció egy adott hosszúságú *Karakterlánc* értéket ad vissza, amelyben a megadott karakterlánc eleje egy vagy több megadott karakterrel van kitöltve. |
| [QrCode](er-functions-text-qrcode.md) | Ez a függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód). |
| [Csere](er-functions-text-replace.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal. |
| [Jobbra](er-functions-text-right.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc vége után. |
| [Szöveg](er-functions-text-text.md) | A függvény a megadott számot egy *Karakterlánc* értékként adja vissza, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja. |
| [Fordítás](er-functions-text-translate.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely a megadott szöveg karakterrel történő helyettesítésének eredményét tartalmazza egy másik megadott halmaz karaktereivel. |
| [Trim](er-functions-text-trim.md) | Ez a függvény a megadott szöveg-karakterláncot ad vissza karakterláncként a *lap*, a visszahelyezés, a sorbeszúrás és a képernyőbeszúrás karakterei egy karakterrel, a vezető és záró szóközök csonkolása, illetve a szavak közötti szóközök eltávolítása után. |
| [Upper](er-functions-text-upper.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program nagybetűssé alakította. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
