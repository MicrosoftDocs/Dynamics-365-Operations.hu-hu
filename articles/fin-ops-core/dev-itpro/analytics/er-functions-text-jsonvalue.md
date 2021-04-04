---
title: JSONVALUE ER-függvény
description: A témakör tájékoztatást nyújt a JSONVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
ms.topic: article
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
ms.openlocfilehash: 203fe1b1616f724ddf3015258306e0d9e8d4f599
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570016"
---
# <a name="jsonvalue-er-function"></a><span data-ttu-id="356e9-103">JSONVALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="356e9-103">JSONVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="356e9-104">A `JSONVALUE` függvény elemzi az adatokat a megadott elérési úton elérhető JavaScript Object Notation (JSON) formátumban, a megadott azonosítóval rendelkező skaláris érték kibontásához.</span><span class="sxs-lookup"><span data-stu-id="356e9-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="356e9-105">Ezután *Karakterlánc* értékként adja vissza a kivont skaláris értéket.</span><span class="sxs-lookup"><span data-stu-id="356e9-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="356e9-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="356e9-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="356e9-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="356e9-107">Arguments</span></span>

<span data-ttu-id="356e9-108">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="356e9-108">`input`: *String*</span></span>

<span data-ttu-id="356e9-109">A JSON adatokat tartalmazó, *Karakterlánc* típusú adatforrás érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="356e9-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="356e9-110">`path`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="356e9-110">`path`: *String*</span></span>

<span data-ttu-id="356e9-111">A JSON adatok skaláris értékének azonosítója.</span><span class="sxs-lookup"><span data-stu-id="356e9-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="356e9-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="356e9-112">Return values</span></span>

<span data-ttu-id="356e9-113">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="356e9-113">*String*</span></span>

<span data-ttu-id="356e9-114">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="356e9-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="356e9-115">Példa</span><span class="sxs-lookup"><span data-stu-id="356e9-115">Example</span></span>

<span data-ttu-id="356e9-116">A **JsonField** adatforrás a következő adatokat tartalmazza JSON formátumban: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="356e9-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="356e9-117">Ebben az esetben a `JSONVALUE (JsonField, "BuildNumber")` kifejezés a következő *Karakterlánc* adattípusú értéket adja eredményül: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="356e9-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="356e9-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="356e9-118">Additional resources</span></span>

[<span data-ttu-id="356e9-119">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="356e9-119">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]