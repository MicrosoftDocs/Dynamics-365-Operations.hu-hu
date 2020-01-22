---
title: A szöveges kategóriába tartozó ER-függvények listája
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) támogatott szövegfüggvényekről.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f519d242fe74196b0d12bdc9df4f1b4b0e585752
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916614"
---
# <a name="list-of-er-functions-of-the-text-category"></a>A szöveges kategóriába tartozó ER-függvények listája

[!include [banner](../includes/banner.md)]

Az Elektronikus jelentéskészítés (ER) szövegfüggvényei a *Karakterlánc* típusú adattípusok adatforrásokon történő műveletek végrehajtására használhatók. Ez a témakör ezeknek a függvényeknek az összefoglalása.

## <a name="list-of-supported-functions"></a>Támogatott függvények listája

| Funkció | Leírás |
|----------|-------------|
| [Char](er-functions-text-char.md) | Ez a függvény olyan *Karakterlánc* értéket ad eredményül, amely egyetlen karaktert mutat be, amelyre a megadott Unicode szám hivatkozik. |
| [Összefűzés](er-functions-text-concatenate.md) | Ez a függvény az összes megadott karakterláncot *Karakterlánc* értékként adja vissza, miután egy karakterláncba lettek egyesítve. |
| [Formátum](er-functions-text-format.md) | Ez a függvény a megadott karakterláncot egy *Karakterlánc* értékként adja vissza, miután az **%N** minden előfordulását az *N*. argumentummal helyettesítve formázza. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Ez a függvény egy adott *Felsorolás* értéket keres a megadott felsorolási adatforrásban a *Karakterlánc* értékként megadott felsorolási név használatával. Ha a *Felsorolás* értéke megtalálható, a függvény azt visszaadja. |
| [GuidValue](er-functions-text-guidvalue.md) | Ez a függvény a megadott *Karakterlánc* típusú bemenetet *GUID* típusú adatelemmé konvertálja. |
| [JsonValue](er-functions-text-jsonvalue.md) | Ez a funkció elemzi az adatokat a megadott elérési úton elérhető JavaScript Object Notation (JSON) formátumban, a megadott azonosítón alapuló skaláris érték kibontásához. Ezután *Karakterlánc* értékként adja vissza a kivont skaláris értéket. |
| [Balra](er-functions-text-left.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc kezdete után. |
| [Len](er-functions-text-len.md) | Ez a függvény olyan *Egész* értéket ad vissza, amely a karakterek számát mutatja a megadott karakterláncban. |
| [Lower](er-functions-text-lower.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program kisbetűssé alakította. |
| [Mid](er-functions-text-mid.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc adott pozíciójától kiindulva. |
| [NumberFormat](er-functions-text-numberformat.md) | Ez a függvény egy *Karakterlánc* értéket ad eredményül, amely a megadott számot mutatja a megadott formátumban és egy opcionálisan meghatározott területi beállításokban. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott számot, miután kiírta (azaz szöveges karakterlánccá konvertálta) a megadott nyelven. |
| [PadLeft](er-functions-text-padleft.md) | Ez a funkció egy adott hosszúságú *Karakterlánc* értéket ad vissza, amelyben a megadott karakterlánc eleje egy vagy több megadott karakterrel van kitöltve. |
| [QrCode](er-functions-text-qrcode.md) | Ez a függvény egy olyan *Tároló* értéket ad vissza, amely a megadott karakterlánchoz bináris formátumban jeleníti meg a gyors válaszkódot (QR-kód). |
| [Csere](er-functions-text-replace.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal. |
| [Jobbra](er-functions-text-right.md) | Ez a függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc vége után. |
| [Szöveg](er-functions-text-text.md) | A függvény a megadott számot egy *Karakterlánc* értékként adja vissza, miután az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja. |
| [Fordítás](er-functions-text-translate.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott szöveges karakterláncot, miután annak egészét vagy egy részét lecserélték egy másik karakterlánccal. |
| [Trim](er-functions-text-trim.md) | Ez a funkció a megadott karakterláncot *Karakterlánc* értékként adja vissza, miután a kezdő és záró szóközöket levágta, és a szavak közötti több szóközt eltávolította. |
| [Upper](er-functions-text-upper.md) | Ez a függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program nagybetűssé alakította. |

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Képletszerkesztő az Elektronikus jelentéskészítésben](general-electronic-reporting-formula-designer.md)

[Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)
