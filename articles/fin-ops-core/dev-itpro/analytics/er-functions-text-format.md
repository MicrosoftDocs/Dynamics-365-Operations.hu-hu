---
title: FORMAT ER-függvény
description: A témakör tájékoztatást nyújt a FORMAT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ae688ef6b24f8d90c0354c8c6449adba1588bfa
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041078"
---
# <a name="FORMAT">FORMAT ER-függvény</a>

[!include [banner](../includes/banner.md)]

A `FORMAT` függvény a megadott karakterláncot egy *Karakterlánc* értékként adja vissza, miután az **%N** minden előfordulását az *N*. argumentummal helyettesítve formázza.

## <a name="syntax"></a>Szintaxis

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>Argumentumok

`string`: *Karakterlánc*

Hivatkozás olyan *Karakterlánc* típusú adatforrásra, amelyet formázni kell. Az argumentum megadása kötelező.

`argument 1`: *Karakterlánc*

Az első argumentum, amely a **%1** előfordulásainak lecserélésére szolgál. Az argumentum megadása kötelező.

`argument N`: *Karakterlánc*

Az *N*. argumentum, amely a **%2**, **%3** stb. előfordulásainak lecserélésére szolgál. Ezek a további argumentumok nem kötelezők.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

Ha egy argumentum nem érhető el a paraméter számára, a paraméter a karakterláncban **„%N”** elemként jelenik meg. A *Valós* típus értékeihez az alapértelmezett karakterlánc-konverzió két tizedesjegyre korlátozódik.

## <a name="example"></a>Példa

A következő ábrán a **PaymentModel** adatforrás a **Vevő** összetevő használatával visszaadja a vevői rekordok listáját. A feldolgozás dátumértékét a **ProcessingDate** mező segítségével adja vissza.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

A kijelölt vevőkre vonatkozó elektronikus fájlok létrehozására tervezett Elektronikus jelentéskészítés (ER) formátumban a **PaymentModel** adatforrásként van kijelölve, és ellenőrzi a munkafolyamatot. A felhasználó tájékoztatásul kivételt kap, amikor a kiválasztott vevő le van állítva a jelentés feldolgozásának dátumára. Az ellenőrzés feldolgozásának ezen típusára vonatkozóan tervezett formula a következő forrásokat használhatja:

- A SYS70894 címke, amely a következő szöveggel rendelkezik:

    - **A EN-US nyelvhez:** „Nothing to print”
    - **DE nyelvhez:** „Nichts zu drucken”

- A SYS18389 címke, amely a következő szöveggel rendelkezik:

    - **A HU nyelvhez:** „A(z) %1 vevő le van állítva a következő esetében: %2.”
    - **A DE nyelvhez:** "Debitor '%1' wird für %2 gesperrt."

Íme a tervezhető kifejezés.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

Ha a jelentés feldolgozása a **Litware Retail** vevőre vonatkozóan 2015. december 17-én folyik, az **EN-US** területi beállításban és az **EN-US** nyelvben ez a képlet a következő szöveget jeleníti meg, amely a felhasználó számára egy kivételre vonatkozó üzenetként jeleníthető meg:

*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*

Ha ugyanazt a jelentést 2015. december 17-én a **Litware Retail** vevőre vonatkozóan a **DE** területi beállítással és a **DE** nyelven dolgozzák fel, ez a képlet a következő, eltérő dátumformátumot használó szöveget jeleníti meg:

*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> A címkék ER-képleteinél a következő szintaxis kerül alkalmazásra:
>
> - **A Microsoft Dynamics 365 Finance alkalmazás erőforrásaiból származó címkék esetében:** **\@X**, ahol **X** a címkeazonosító az alkalmazásobjektum-fában (AOT)
> - **Az ER-konfigurációkban található címkékhez:** **@"GER_LABEL:X"**, ahol **X** az ER-konfigurációban található címkeazonosító

## <a name="additional-resources"></a>További erőforrások

[Szöveg függvények](er-functions-category-text.md)
