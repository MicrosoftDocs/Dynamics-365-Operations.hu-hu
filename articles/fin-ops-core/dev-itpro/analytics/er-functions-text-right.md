---
title: RIGHT ER-függvény
description: A témakör tájékoztatást nyújt a RIGHT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 75255eccf4da468b0946253f7570b1621f905cd7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570240"
---
# <a name="right-er-function"></a><span data-ttu-id="8a4ad-103">RIGHT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="8a4ad-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a4ad-104">A `RIGHT` függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc vége után.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a4ad-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="8a4ad-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="8a4ad-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="8a4ad-106">Arguments</span></span>

<span data-ttu-id="8a4ad-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="8a4ad-107">`text`: *String*</span></span>

<span data-ttu-id="8a4ad-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="8a4ad-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="8a4ad-109">`number`: *Integer*</span></span>

<span data-ttu-id="8a4ad-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg végétől.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="8a4ad-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="8a4ad-111">Return values</span></span>

<span data-ttu-id="8a4ad-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="8a4ad-112">*String*</span></span>

<span data-ttu-id="8a4ad-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="8a4ad-114">Példa</span><span class="sxs-lookup"><span data-stu-id="8a4ad-114">Example</span></span>

<span data-ttu-id="8a4ad-115">A `RIGHT ("Sample", 3)` a **"ple"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="8a4ad-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a4ad-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8a4ad-116">Additional resources</span></span>

[<span data-ttu-id="8a4ad-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="8a4ad-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]