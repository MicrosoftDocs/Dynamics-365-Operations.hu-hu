---
title: INDEX ER-függvény
description: A témakör tájékoztatást nyújt az INDEX Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: 5a0fdb8958670efe8e2a37cee183bf836fa6c7e8
ms.sourcegitcommit: 047b0503868cc7d7b21868e24405d76af35db747
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/21/2021
ms.locfileid: "6087751"
---
# <a name="index-er-function"></a><span data-ttu-id="1744b-103">INDEX ER-függvény</span><span class="sxs-lookup"><span data-stu-id="1744b-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1744b-104">Az `INDEX` függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott numerikus index használatával került kiválasztásra a megadott listában.</span><span class="sxs-lookup"><span data-stu-id="1744b-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="1744b-105">Kivétel történik, ha az index kívül esik a listán megadott rekordok tartományán.</span><span class="sxs-lookup"><span data-stu-id="1744b-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="1744b-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="1744b-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="1744b-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="1744b-107">Arguments</span></span>

<span data-ttu-id="1744b-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="1744b-108">`list`: *Record list*</span></span>

<span data-ttu-id="1744b-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="1744b-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="1744b-110">`index`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="1744b-110">`index`: *Integer*</span></span>

<span data-ttu-id="1744b-111">Numerikus index, amely a kívánt rekord pozícióját jelzi a megadott listában.</span><span class="sxs-lookup"><span data-stu-id="1744b-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

> [!NOTE]
> <span data-ttu-id="1744b-112">Mivel ehhez a funkcióhoz egyen alapuló számozást kell használni, a megadott lista első rekordjának visszaadásához adja meg az **1** értéket.</span><span class="sxs-lookup"><span data-stu-id="1744b-112">Because one-based numbering is used for this function, specify the value **1** to return the first record of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="1744b-113">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="1744b-113">Return values</span></span>

<span data-ttu-id="1744b-114">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="1744b-114">*Container (record)*</span></span>

<span data-ttu-id="1744b-115">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="1744b-115">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="1744b-116">1. példa</span><span class="sxs-lookup"><span data-stu-id="1744b-116">Example 1</span></span>

<span data-ttu-id="1744b-117">Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `DS.Value` kifejezés a **„B”** szöveges értéket adja vissza a rekordlista második rekordjaként.</span><span class="sxs-lookup"><span data-stu-id="1744b-117">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="1744b-118">Az `INDEX (SPLIT ("A|B|C", "|"), 2).Value` kifejezés szintén a **„B”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="1744b-118">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1744b-119">2. példa</span><span class="sxs-lookup"><span data-stu-id="1744b-119">Example 2</span></span>

<span data-ttu-id="1744b-120">Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor az `INDEX (SPLIT ("A|B|C", "|"), 4).Value` kifejezés kivételt dob futásidőben.</span><span class="sxs-lookup"><span data-stu-id="1744b-120">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1744b-121">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1744b-121">Additional resources</span></span>

[<span data-ttu-id="1744b-122">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="1744b-122">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
