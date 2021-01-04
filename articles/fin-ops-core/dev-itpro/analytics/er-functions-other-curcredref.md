---
title: CURCREDREF ER-függvény
description: A témakör tájékoztatást nyújt a CURCREDREF Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 3923126060963122634d90c2ba8a380f534e9178
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686762"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="a9d88-103">CURCREDREF ER-függvény</span><span class="sxs-lookup"><span data-stu-id="a9d88-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9d88-104">A `CURCREDREF` függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást képviseli a megadott számlaszám számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="a9d88-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9d88-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="a9d88-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="a9d88-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="a9d88-106">Arguments</span></span>

<span data-ttu-id="a9d88-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a9d88-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="a9d88-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="a9d88-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="a9d88-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="a9d88-109">Return values</span></span>

<span data-ttu-id="a9d88-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="a9d88-110">*String*</span></span>

<span data-ttu-id="a9d88-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="a9d88-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="a9d88-112">Példa</span><span class="sxs-lookup"><span data-stu-id="a9d88-112">Example</span></span>

<span data-ttu-id="a9d88-113">A `CURCredRef ("VEND-200002")` a **"2200002"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="a9d88-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9d88-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a9d88-114">Additional resources</span></span>

[<span data-ttu-id="a9d88-115">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="a9d88-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
