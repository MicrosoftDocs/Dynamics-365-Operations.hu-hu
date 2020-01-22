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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6f2a661dd3a85c658ff85f5886d98f665e28718
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915579"
---
# <span data-ttu-id="fdc94-103"><a name="LEN">LEN ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="fdc94-103"><a name="LEN">LEN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fdc94-104">a `LEN` függvény olyan *Egész* értéket ad vissza, amely a karakterek számát mutatja a megadott karakterláncban.</span><span class="sxs-lookup"><span data-stu-id="fdc94-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fdc94-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="fdc94-105">Syntax</span></span>

```
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="fdc94-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="fdc94-106">Arguments</span></span>

<span data-ttu-id="fdc94-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fdc94-107">`text`: *String*</span></span>

<span data-ttu-id="fdc94-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="fdc94-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="fdc94-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="fdc94-109">Return values</span></span>

<span data-ttu-id="fdc94-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="fdc94-110">*Integer*</span></span>

<span data-ttu-id="fdc94-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="fdc94-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="fdc94-112">Példa</span><span class="sxs-lookup"><span data-stu-id="fdc94-112">Example</span></span>

<span data-ttu-id="fdc94-113">A `LEN ("Sample")` a **6** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fdc94-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fdc94-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fdc94-114">Additional resources</span></span>

[<span data-ttu-id="fdc94-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="fdc94-115">Text functions</span></span>](er-functions-category-text.md)
