---
title: JSONVALUE ER-függvény
description: A témakör tájékoztatást nyújt a JSONVALUE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 75f20632074cb4dead98991fd6522ab9b20b9965
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041216"
---
# <span data-ttu-id="06cb0-103"><a name="JSONVALUE">JSONVALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="06cb0-103"><a name="JSONVALUE">JSONVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="06cb0-104">A `JSONVALUE` függvény elemzi az adatokat a megadott elérési úton elérhető JavaScript Object Notation (JSON) formátumban, a megadott azonosítóval rendelkező skaláris érték kibontásához.</span><span class="sxs-lookup"><span data-stu-id="06cb0-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="06cb0-105">Ezután *Karakterlánc* értékként adja vissza a kivont skaláris értéket.</span><span class="sxs-lookup"><span data-stu-id="06cb0-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="06cb0-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="06cb0-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="06cb0-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="06cb0-107">Arguments</span></span>

<span data-ttu-id="06cb0-108">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="06cb0-108">`input`: *String*</span></span>

<span data-ttu-id="06cb0-109">A JSON adatokat tartalmazó, *Karakterlánc* típusú adatforrás érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="06cb0-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="06cb0-110">`path`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="06cb0-110">`path`: *String*</span></span>

<span data-ttu-id="06cb0-111">A JSON adatok skaláris értékének azonosítója.</span><span class="sxs-lookup"><span data-stu-id="06cb0-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="06cb0-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="06cb0-112">Return values</span></span>

<span data-ttu-id="06cb0-113">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="06cb0-113">*String*</span></span>

<span data-ttu-id="06cb0-114">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="06cb0-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="06cb0-115">Példa</span><span class="sxs-lookup"><span data-stu-id="06cb0-115">Example</span></span>

<span data-ttu-id="06cb0-116">A **JsonField** adatforrás a következő adatokat tartalmazza JSON formátumban: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="06cb0-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="06cb0-117">Ebben az esetben a `JSONVALUE (JsonField, "BuildNumber")` kifejezés a következő *Karakterlánc* adattípusú értéket adja eredményül: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="06cb0-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="06cb0-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="06cb0-118">Additional resources</span></span>

[<span data-ttu-id="06cb0-119">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="06cb0-119">Text functions</span></span>](er-functions-category-text.md)
