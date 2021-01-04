---
title: LEN ER-függvény
description: A témakör tájékoztatást nyújt a LEN Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 8d766b8effa9d6936de7a3def252536603330965
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680361"
---
# <a name="len-er-function"></a><span data-ttu-id="3be38-103">LEN ER-függvény</span><span class="sxs-lookup"><span data-stu-id="3be38-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3be38-104">a `LEN` függvény olyan *Egész* értéket ad vissza, amely a karakterek számát mutatja a megadott karakterláncban.</span><span class="sxs-lookup"><span data-stu-id="3be38-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="3be38-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="3be38-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="3be38-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="3be38-106">Arguments</span></span>

<span data-ttu-id="3be38-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="3be38-107">`text`: *String*</span></span>

<span data-ttu-id="3be38-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="3be38-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="3be38-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="3be38-109">Return values</span></span>

<span data-ttu-id="3be38-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="3be38-110">*Integer*</span></span>

<span data-ttu-id="3be38-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="3be38-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="3be38-112">Példa</span><span class="sxs-lookup"><span data-stu-id="3be38-112">Example</span></span>

<span data-ttu-id="3be38-113">A `LEN ("Sample")` a **6** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="3be38-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3be38-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3be38-114">Additional resources</span></span>

[<span data-ttu-id="3be38-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="3be38-115">Text functions</span></span>](er-functions-category-text.md)
