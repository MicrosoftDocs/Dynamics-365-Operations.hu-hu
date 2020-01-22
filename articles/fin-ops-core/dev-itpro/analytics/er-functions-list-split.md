---
title: SPLIT ER-függvény
description: A témakör tájékoztatást nyújt a SPLIT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 31caf7c728a92d31428f47320c074fa9fc35bda6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916108"
---
# <span data-ttu-id="b05e4-103"><a name="SPLIT">SPLIT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="b05e4-103"><a name="SPLIT">SPLIT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b05e4-104">A `SPLIT` függvény az adott bemeneti karakterláncot részkarakterláncokká osztja szét, és az eredményt új *Rekordlista* értékként adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b05e4-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b05e4-105">Szintaxis 1</span><span class="sxs-lookup"><span data-stu-id="b05e4-105">Syntax 1</span></span>

```
SPLIT (input, length)
```

<span data-ttu-id="b05e4-106">Ez a szintaxis a megadott bemeneti karakterlánc felosztására szolgál a részkarakterláncokban, amelyek mindegyike megadott időtartammal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="b05e4-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="b05e4-107">Szintaxis 2</span><span class="sxs-lookup"><span data-stu-id="b05e4-107">Syntax 2</span></span>

```
SPLIT (input, delimiter)
```

<span data-ttu-id="b05e4-108">Ez a szintaxis a megadott bemeneti karakterlánc felosztására szolgál a részkarakterláncokban, megadott elválasztó alapján.</span><span class="sxs-lookup"><span data-stu-id="b05e4-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="b05e4-109">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="b05e4-109">Arguments</span></span>

<span data-ttu-id="b05e4-110">`input`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b05e4-110">`input`: *String*</span></span>

<span data-ttu-id="b05e4-111">A felosztandó szöveg.</span><span class="sxs-lookup"><span data-stu-id="b05e4-111">The text to split.</span></span>

<span data-ttu-id="b05e4-112">`length`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="b05e4-112">`length`: *Integer*</span></span>

<span data-ttu-id="b05e4-113">Egyetlen részkarakterlánc maximális hossza.</span><span class="sxs-lookup"><span data-stu-id="b05e4-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="b05e4-114">`delimiter`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b05e4-114">`delimiter`: *String*</span></span>

<span data-ttu-id="b05e4-115">A részkarakterláncok elválasztására használt határolójel.</span><span class="sxs-lookup"><span data-stu-id="b05e4-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="b05e4-116">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="b05e4-116">Return values</span></span>

<span data-ttu-id="b05e4-117">*Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="b05e4-117">*Record list*</span></span>

<span data-ttu-id="b05e4-118">A rekordok eredményül kapott listája.</span><span class="sxs-lookup"><span data-stu-id="b05e4-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b05e4-119">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b05e4-119">Usage notes</span></span>

<span data-ttu-id="b05e4-120">A visszaadott lista rekordstruktúrája a *Karakterlánc* típus **Érték** mezőjéből áll.</span><span class="sxs-lookup"><span data-stu-id="b05e4-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="b05e4-121">A visszaadott lista minden rekordja az ebben a mezőben generált részkarakterláncokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b05e4-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="b05e4-122">Ha a `delimiter` argumentum üres, egy új listát ad vissza, amely egy rekordból áll, amelynek van egy *Karakterlánc* típusú **Érték** mezője.</span><span class="sxs-lookup"><span data-stu-id="b05e4-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="b05e4-123">Ez a mező tartalmazza a beírt szöveget.</span><span class="sxs-lookup"><span data-stu-id="b05e4-123">This field contains the input text.</span></span>

<span data-ttu-id="b05e4-124">Ha az `input` argumentum üres, akkor egy új, üres listát ad vissza.</span><span class="sxs-lookup"><span data-stu-id="b05e4-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="b05e4-125">Ha az `input` vagy `delimiter` argumentum nincs megadva (null), alkalmazáskivétel történik.</span><span class="sxs-lookup"><span data-stu-id="b05e4-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="b05e4-126">1. példa</span><span class="sxs-lookup"><span data-stu-id="b05e4-126">Example 1</span></span>

<span data-ttu-id="b05e4-127">A `SPLIT ("abcd", 3)` két rekordot tartalmazó új listát jelenít meg, amelyek a *Karakterlánc* típusú **Érték** mezővel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="b05e4-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="b05e4-128">Az első rekordban szereplő **Érték** mező az **„abc”** szöveget tartalmazza és a második rekordban szereplő **Érték** mező a **„d”** betűt tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b05e4-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b05e4-129">2. példa</span><span class="sxs-lookup"><span data-stu-id="b05e4-129">Example 2</span></span>

<span data-ttu-id="b05e4-130">A `SPLIT ("XAb aBy", "aB")` három rekordot tartalmazó új listát jelenít meg, amelyek a *Karakterlánc* típusú **Érték** mezővel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="b05e4-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="b05e4-131">Az első rekordban szereplő **Érték** mező az **„X”** szöveget, a második rekordban szereplő **Érték** mező a **„&nbsp;”** szöveget, a harmadik rekordban szereplő **Érték** mező pedig az **„y”** szöveget tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b05e4-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="b05e4-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b05e4-132">Additional resources</span></span>

[<span data-ttu-id="b05e4-133">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="b05e4-133">List functions</span></span>](er-functions-category-list.md)
