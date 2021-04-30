---
title: SPLIT ER-függvény
description: A témakör tájékoztatást nyújt a SPLIT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 26b6ddeb2880fc220283b6389327a497549a4511
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853443"
---
# <a name="split-er-function"></a><span data-ttu-id="2354f-103">SPLIT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="2354f-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2354f-104">A `SPLIT` függvény az adott bemeneti karakterláncot részkarakterláncokká osztja szét, és az eredményt új *Rekordlista* értékként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2354f-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="2354f-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="2354f-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="2354f-106">Ez a szintaxis a megadott bemeneti karakterlánc felosztására szolgál a részkarakterláncokban, amelyek mindegyike megadott időtartammal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="2354f-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="2354f-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="2354f-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="2354f-108">Ez a szintaxis a megadott bemeneti karakterlánc felosztására szolgál a részkarakterláncokban, megadott elválasztó alapján.</span><span class="sxs-lookup"><span data-stu-id="2354f-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="2354f-109">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="2354f-109">Arguments</span></span>

<span data-ttu-id="2354f-110">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2354f-110">`input`: *String*</span></span>

<span data-ttu-id="2354f-111">A felosztandó szöveg.</span><span class="sxs-lookup"><span data-stu-id="2354f-111">The text to split.</span></span>

<span data-ttu-id="2354f-112">`length`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="2354f-112">`length`: *Integer*</span></span>

<span data-ttu-id="2354f-113">Egyetlen részkarakterlánc maximális hossza.</span><span class="sxs-lookup"><span data-stu-id="2354f-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="2354f-114">`delimiter`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="2354f-114">`delimiter`: *String*</span></span>

<span data-ttu-id="2354f-115">A részkarakterláncok elválasztására használt határolójel.</span><span class="sxs-lookup"><span data-stu-id="2354f-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="2354f-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="2354f-116">Return values</span></span>

<span data-ttu-id="2354f-117">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="2354f-117">*Record list*</span></span>

<span data-ttu-id="2354f-118">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="2354f-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2354f-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2354f-119">Usage notes</span></span>

<span data-ttu-id="2354f-120">A visszaadott lista rekordstruktúrája a *Karakterlánc* típus **Érték** mezőjéből áll.</span><span class="sxs-lookup"><span data-stu-id="2354f-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="2354f-121">A visszaadott lista minden rekordja az ebben a mezőben generált részkarakterláncokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2354f-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="2354f-122">Ha a `delimiter` argumentum üres, egy új listát ad vissza, amely egy rekordból áll, amelynek van egy *Karakterlánc* típusú **Érték** mezője.</span><span class="sxs-lookup"><span data-stu-id="2354f-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="2354f-123">Ez a mező tartalmazza a beírt szöveget.</span><span class="sxs-lookup"><span data-stu-id="2354f-123">This field contains the input text.</span></span>

<span data-ttu-id="2354f-124">Ha az `input` argumentum üres, akkor egy új, üres listát ad vissza.</span><span class="sxs-lookup"><span data-stu-id="2354f-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="2354f-125">Ha az `input` vagy `delimiter` argumentum nincs megadva (null), alkalmazáskivétel történik.</span><span class="sxs-lookup"><span data-stu-id="2354f-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="2354f-126">1. példa</span><span class="sxs-lookup"><span data-stu-id="2354f-126">Example 1</span></span>

<span data-ttu-id="2354f-127">A `SPLIT ("abcd", 3)` két rekordot tartalmazó új listát jelenít meg, amelyek a *Karakterlánc* típusú **Érték** mezővel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="2354f-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="2354f-128">Az első rekordban szereplő **Érték** mező az **„abc”** szöveget tartalmazza és a második rekordban szereplő **Érték** mező a **„d”** betűt tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2354f-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2354f-129">2. példa</span><span class="sxs-lookup"><span data-stu-id="2354f-129">Example 2</span></span>

<span data-ttu-id="2354f-130">A `SPLIT ("XAb aBy", "aB")` három rekordot tartalmazó új listát jelenít meg, amelyek a *Karakterlánc* típusú **Érték** mezővel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="2354f-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="2354f-131">Az első rekordban szereplő **Érték** mező az **„X”** szöveget, a második rekordban szereplő **Érték** mező a **„&nbsp;”** szöveget, a harmadik rekordban szereplő **Érték** mező pedig az **„y”** szöveget tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="2354f-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="2354f-132">3. példa</span><span class="sxs-lookup"><span data-stu-id="2354f-132">Example 3</span></span>

<span data-ttu-id="2354f-133">Az [INDEX](er-functions-list-index.md) függvény segítségével lehet elérni a megadott bemeneti karakterlánc egyes elemeit.</span><span class="sxs-lookup"><span data-stu-id="2354f-133">Yo can use the [INDEX](er-functions-list-index.md) function to access individual elements of the specified input string.</span></span> <span data-ttu-id="2354f-134">Ha megadja a **Számított mező** típusú **MyList** adatforrást, és konfigurálja hozzá a `SPLIT("abc", 1)` kifejezést, akkor a `INDEX(MyList,2).Value` kifejezés a **„b”** szöveges értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2354f-134">If you enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, the expression `INDEX(MyList,2).Value` returns the text **"b"**.</span></span>

## <a name="example-4"></a><span data-ttu-id="2354f-135">4. példa</span><span class="sxs-lookup"><span data-stu-id="2354f-135">Example 4</span></span>

<span data-ttu-id="2354f-136">Az [ENUMERATE](er-functions-list-enumerate.md) függvény segítségével szintén el lehet érni a megadott bemeneti karakterlánc egyes elemeit.</span><span class="sxs-lookup"><span data-stu-id="2354f-136">The [ENUMERATE](er-functions-list-enumerate.md) function can also help you access individual elements of the specified input string.</span></span> <span data-ttu-id="2354f-137">Ha először a **Számított mező** típus **MyList** adatforrását adja meg, és annak konfigurálja a `SPLIT("abc", 1)` kifejezést, majd beírja a **Számított mező** típus **EnumeratedList** adatforrását, és konfigurálja a `ENUMERATE(MyList)` kifejezéshez, a `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` kifejezés a **„b”** szöveget adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2354f-137">If you first enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, and then enter the **EnumeratedList** data source of the **Calculated field** type and configure for it the `ENUMERATE(MyList)` expression, the expression `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` returns the text **"b"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2354f-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="2354f-138">Additional resources</span></span>

[<span data-ttu-id="2354f-139">Listafüggvények</span><span class="sxs-lookup"><span data-stu-id="2354f-139">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
