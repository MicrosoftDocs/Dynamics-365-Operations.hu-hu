---
title: LEFT ER-függvény
description: A témakör tájékoztatást nyújt a LEFT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e9cdff9bb5c22c74803cf17c056c0ff1af5ef43
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685883"
---
# <a name="left-er-function"></a><span data-ttu-id="88210-103">LEFT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="88210-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88210-104">A `LEFT` függvény olyan *String* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc kezdete után.</span><span class="sxs-lookup"><span data-stu-id="88210-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="88210-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="88210-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="88210-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="88210-106">Arguments</span></span>

<span data-ttu-id="88210-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="88210-107">`text`: *String*</span></span>

<span data-ttu-id="88210-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="88210-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="88210-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="88210-109">`number`: *Integer*</span></span>

<span data-ttu-id="88210-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg kezdetétől.</span><span class="sxs-lookup"><span data-stu-id="88210-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="88210-111">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="88210-111">Return values</span></span>

<span data-ttu-id="88210-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="88210-112">*String*</span></span>

<span data-ttu-id="88210-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="88210-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="88210-114">Példa</span><span class="sxs-lookup"><span data-stu-id="88210-114">Example</span></span>

<span data-ttu-id="88210-115">A `LEFT ("Sample", 3)` a **"Sam"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="88210-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88210-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="88210-116">Additional resources</span></span>

[<span data-ttu-id="88210-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="88210-117">Text functions</span></span>](er-functions-category-text.md)
