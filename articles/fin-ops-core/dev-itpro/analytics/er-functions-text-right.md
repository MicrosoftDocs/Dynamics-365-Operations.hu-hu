---
title: RIGHT ER-függvény
description: A témakör tájékoztatást nyújt a RIGHT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 7169d9d3d2cdfb9f36bb77c1688922549e79ff32
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040871"
---
# <span data-ttu-id="c6492-103"><a name="RIGHT">RIGHT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="c6492-103"><a name="RIGHT">RIGHT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6492-104">A `RIGHT` függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc vége után.</span><span class="sxs-lookup"><span data-stu-id="c6492-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6492-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="c6492-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="c6492-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="c6492-106">Arguments</span></span>

<span data-ttu-id="c6492-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c6492-107">`text`: *String*</span></span>

<span data-ttu-id="c6492-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="c6492-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="c6492-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="c6492-109">`number`: *Integer*</span></span>

<span data-ttu-id="c6492-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg végétől.</span><span class="sxs-lookup"><span data-stu-id="c6492-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="c6492-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="c6492-111">Return values</span></span>

<span data-ttu-id="c6492-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="c6492-112">*String*</span></span>

<span data-ttu-id="c6492-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="c6492-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c6492-114">Példa</span><span class="sxs-lookup"><span data-stu-id="c6492-114">Example</span></span>

<span data-ttu-id="c6492-115">A `RIGHT ("Sample", 3)` a **"ple"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c6492-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c6492-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c6492-116">Additional resources</span></span>

[<span data-ttu-id="c6492-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="c6492-117">Text functions</span></span>](er-functions-category-text.md)
