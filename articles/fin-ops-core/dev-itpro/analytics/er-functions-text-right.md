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
ms.openlocfilehash: 01718f9b153c1d6c46d50a9b17e899ccfba16915
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916729"
---
# <span data-ttu-id="ed9e0-103"><a name="RIGHT">RIGHT ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="ed9e0-103"><a name="RIGHT">RIGHT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed9e0-104">A `RIGHT` függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc vége után.</span><span class="sxs-lookup"><span data-stu-id="ed9e0-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed9e0-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="ed9e0-105">Syntax</span></span>

```
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="ed9e0-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="ed9e0-106">Arguments</span></span>

<span data-ttu-id="ed9e0-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="ed9e0-107">`text`: *String*</span></span>

<span data-ttu-id="ed9e0-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="ed9e0-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="ed9e0-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="ed9e0-109">`number`: *Integer*</span></span>

<span data-ttu-id="ed9e0-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg végétől.</span><span class="sxs-lookup"><span data-stu-id="ed9e0-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="ed9e0-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="ed9e0-111">Return values</span></span>

<span data-ttu-id="ed9e0-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="ed9e0-112">*String*</span></span>

<span data-ttu-id="ed9e0-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="ed9e0-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ed9e0-114">Példa</span><span class="sxs-lookup"><span data-stu-id="ed9e0-114">Example</span></span>

<span data-ttu-id="ed9e0-115">A `RIGHT ("Sample", 3)` a **"ple"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ed9e0-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ed9e0-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ed9e0-116">Additional resources</span></span>

[<span data-ttu-id="ed9e0-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="ed9e0-117">Text functions</span></span>](er-functions-category-text.md)
