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
ms.openlocfilehash: dd53ece77b08fc9723c838da5ba08bf3825b5e56
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743711"
---
# <a name="right-er-function"></a><span data-ttu-id="27588-103">RIGHT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="27588-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27588-104">A `RIGHT` függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc vége után.</span><span class="sxs-lookup"><span data-stu-id="27588-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="27588-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="27588-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="27588-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="27588-106">Arguments</span></span>

<span data-ttu-id="27588-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="27588-107">`text`: *String*</span></span>

<span data-ttu-id="27588-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="27588-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="27588-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="27588-109">`number`: *Integer*</span></span>

<span data-ttu-id="27588-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg végétől.</span><span class="sxs-lookup"><span data-stu-id="27588-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="27588-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="27588-111">Return values</span></span>

<span data-ttu-id="27588-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="27588-112">*String*</span></span>

<span data-ttu-id="27588-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="27588-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="27588-114">Példa</span><span class="sxs-lookup"><span data-stu-id="27588-114">Example</span></span>

<span data-ttu-id="27588-115">A `RIGHT ("Sample", 3)` a **"ple"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="27588-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="27588-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="27588-116">Additional resources</span></span>

[<span data-ttu-id="27588-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="27588-117">Text functions</span></span>](er-functions-category-text.md)
