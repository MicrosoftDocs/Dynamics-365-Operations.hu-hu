---
title: LEN ER-függvény
description: A témakör tájékoztatást nyújt a LEN Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: fce4b5311d84364310b76545a775f1cc8db2fd70
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569968"
---
# <a name="len-er-function"></a><span data-ttu-id="7de85-103">LEN ER-függvény</span><span class="sxs-lookup"><span data-stu-id="7de85-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7de85-104">a `LEN` függvény olyan *Egész* értéket ad vissza, amely a karakterek számát mutatja a megadott karakterláncban.</span><span class="sxs-lookup"><span data-stu-id="7de85-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="7de85-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="7de85-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="7de85-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="7de85-106">Arguments</span></span>

<span data-ttu-id="7de85-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="7de85-107">`text`: *String*</span></span>

<span data-ttu-id="7de85-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="7de85-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="7de85-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="7de85-109">Return values</span></span>

<span data-ttu-id="7de85-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="7de85-110">*Integer*</span></span>

<span data-ttu-id="7de85-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="7de85-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="7de85-112">Példa</span><span class="sxs-lookup"><span data-stu-id="7de85-112">Example</span></span>

<span data-ttu-id="7de85-113">A `LEN ("Sample")` a **6** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="7de85-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7de85-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7de85-114">Additional resources</span></span>

[<span data-ttu-id="7de85-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="7de85-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]