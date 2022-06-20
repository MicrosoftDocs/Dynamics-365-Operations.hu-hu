---
title: Base64StringToContainer ER-függvény
description: Ez a cikk a Base64StringToContainer Electronic reporting (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: bcbbead1155a7270a329c23055340492c73cdfda
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879920"
---
# <a name="base64stringtocontainer-er-function"></a>Base64StringToContainer ER-függvény

[!include [banner](../includes/banner.md)]

A `BASE64STRINGTOCONTAINER` [függvény](er-formula-language.md#Functions) a megadott *Karakterlánc* típusú bemenetet *[Tároló](er-functions-category-container.md)* típusú adatelemmé konvertálja.

## <a name="syntax"></a>Szintaxis

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>Argumentumok

`input`: *Karakterlánc*

A *Karakterlánc* típus adatforrásának érvényes elérési útja.

## <a name="return-values"></a>Visszatérési értékek

*Konténer*

A kapott bináris érték bináris nagy objektum (BLOB) formátumban.

## <a name="usage-notes"></a>Használati megjegyzések

A „Paraméter érvénytelen” kivétel akkor lép fel, ha a bemeneti karakterlánc nem ad meg megfelelő Base64-csoportot a bináris-szöveg kódolási sémákhoz.

## <a name="example"></a>Példa

A következő adatforrás megadása a modell-hozzárendelésben:

- A *Dynamics 365 for Operations / Enumeráció* típusú gyökér **DocuTypeGroupEnum** adatforrása, amey a **DocuTypeGroup** alkalmazás enumerációra hivatkozik
- A *Dynamics 365 for Operations / Táblarekordok* típus **Customer** adatforrása, amely a **CustTable** alkalmazástáblára hivatkozik
- A *Számított mező* típus **\#Média** adatforrása, amely a következőképpen van beállítva:

    - A **Vevő** adatforrás gyermek adatforrásaként van hozzáadva.
    - A `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)` kifejezést tartalmazza.

- A *Számított mező* típus **\#MediaAsBase64String** adatforrása, amely a következőképpen van beállítva:

    - A **Vevő\#Média** adatforrás gyermek adatforrásaként van hozzáadva.
    - A `Customer.'#Media'.'getFileContentAsBase64String()'` kifejezést tartalmazza.

- A *Számított mező* típus **\#BlobFomBase64** adatforrása, amely a következőképpen van beállítva:

    - A **Vevő\#Média** adatforrás gyermek adatforrásaként van hozzáadva.
    - A `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'` kifejezést tartalmazza.

Ebben a példában a **\#MediaAsBase64String** adatforrás az aktuális médiamelléklet bináris tartalmát szövegként kódolja, amely a bináris-szöveg kódolási sémák Base64-csoportját képviseli. A **\#BlobFomBase64** adatforrás dekódolja a Base64-karakterláncot, és BLOB-formátumú bináris értéket ad vissza.

![Minta adatforrások az ER-modell-leképezés tervező oldalán.](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>További erőforrások

[Tárolófüggvények](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
