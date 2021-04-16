---
title: RIGHT ER-függvény
description: A témakör tájékoztatást nyújt a RIGHT Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: f59b12f0b3f7b100b953b2072677c83c836746ff
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746123"
---
# <a name="right-er-function"></a><span data-ttu-id="db680-103">RIGHT ER-függvény</span><span class="sxs-lookup"><span data-stu-id="db680-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db680-104">A `RIGHT` függvény olyan *Karakterlánc* értéket ad vissza, amely megadott számú karaktert mutat a megadott karakterlánc vége után.</span><span class="sxs-lookup"><span data-stu-id="db680-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="db680-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="db680-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="db680-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="db680-106">Arguments</span></span>

<span data-ttu-id="db680-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="db680-107">`text`: *String*</span></span>

<span data-ttu-id="db680-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="db680-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="db680-109">`number`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="db680-109">`number`: *Integer*</span></span>

<span data-ttu-id="db680-110">Azoknak a karaktereknek a száma, amelyeket vissza kell adni az eredeti szöveg végétől.</span><span class="sxs-lookup"><span data-stu-id="db680-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="db680-111">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="db680-111">Return values</span></span>

<span data-ttu-id="db680-112">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="db680-112">*String*</span></span>

<span data-ttu-id="db680-113">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="db680-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="db680-114">Példa</span><span class="sxs-lookup"><span data-stu-id="db680-114">Example</span></span>

<span data-ttu-id="db680-115">A `RIGHT ("Sample", 3)` a **"ple"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="db680-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db680-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="db680-116">Additional resources</span></span>

[<span data-ttu-id="db680-117">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="db680-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]