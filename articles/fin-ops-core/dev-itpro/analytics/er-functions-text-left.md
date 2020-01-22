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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8280a05ea180d9de499d87efa53eca8ca912b0e3
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915648"
---
# <span data-ttu-id="0f6af-103"><a name="LEFT">LEFT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="0f6af-103"><a name="LEFT">LEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f6af-104">A `LEFT` függvény olyan *String* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc kezdete után.</span><span class="sxs-lookup"><span data-stu-id="0f6af-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f6af-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0f6af-105">Syntax</span></span>

```
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="0f6af-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0f6af-106">Arguments</span></span>

<span data-ttu-id="0f6af-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0f6af-107">`text`: *String*</span></span>

<span data-ttu-id="0f6af-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="0f6af-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="0f6af-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="0f6af-109">`number`: *Integer*</span></span>

<span data-ttu-id="0f6af-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg kezdetétől.</span><span class="sxs-lookup"><span data-stu-id="0f6af-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="0f6af-111">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="0f6af-111">Return values</span></span>

<span data-ttu-id="0f6af-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0f6af-112">*String*</span></span>

<span data-ttu-id="0f6af-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="0f6af-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0f6af-114">Példa</span><span class="sxs-lookup"><span data-stu-id="0f6af-114">Example</span></span>

<span data-ttu-id="0f6af-115">A `LEFT ("Sample", 3)` a **"Sam"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0f6af-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f6af-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0f6af-116">Additional resources</span></span>

[<span data-ttu-id="0f6af-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="0f6af-117">Text functions</span></span>](er-functions-category-text.md)
