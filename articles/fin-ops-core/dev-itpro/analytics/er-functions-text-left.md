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
ms.openlocfilehash: 4293db244d04debf3679cf2bde0b892bd74e8ead
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041124"
---
# <span data-ttu-id="328f9-103"><a name="LEFT">LEFT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="328f9-103"><a name="LEFT">LEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="328f9-104">A `LEFT` függvény olyan *String* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc kezdete után.</span><span class="sxs-lookup"><span data-stu-id="328f9-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="328f9-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="328f9-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="328f9-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="328f9-106">Arguments</span></span>

<span data-ttu-id="328f9-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="328f9-107">`text`: *String*</span></span>

<span data-ttu-id="328f9-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="328f9-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="328f9-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="328f9-109">`number`: *Integer*</span></span>

<span data-ttu-id="328f9-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg kezdetétől.</span><span class="sxs-lookup"><span data-stu-id="328f9-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="328f9-111">Visszatérési értékek</span><span class="sxs-lookup"><span data-stu-id="328f9-111">Return values</span></span>

<span data-ttu-id="328f9-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="328f9-112">*String*</span></span>

<span data-ttu-id="328f9-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="328f9-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="328f9-114">Példa</span><span class="sxs-lookup"><span data-stu-id="328f9-114">Example</span></span>

<span data-ttu-id="328f9-115">A `LEFT ("Sample", 3)` a **"Sam"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="328f9-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="328f9-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="328f9-116">Additional resources</span></span>

[<span data-ttu-id="328f9-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="328f9-117">Text functions</span></span>](er-functions-category-text.md)
