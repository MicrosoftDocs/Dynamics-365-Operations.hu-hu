---
title: STRINGJOIN ER-függvény
description: A témakör tájékoztatást nyújt a STRINGJOIN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: ac21651e0f5b5a1579b9335bb7f3217370c4d5a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745521"
---
# <a name="stringjoin-er-function"></a><span data-ttu-id="9c020-103">STRINGJOIN ER-függvény</span><span class="sxs-lookup"><span data-stu-id="9c020-103">STRINGJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c020-104">A `STRINGJOIN` függvény egy *Karakterlánc* értéket ad vissza, amely a megadott lista megadott mezőjének összefűzött értékeiből áll.</span><span class="sxs-lookup"><span data-stu-id="9c020-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="9c020-105">Az értékeket a megadott elválasztó elválaszthatja egymástól.</span><span class="sxs-lookup"><span data-stu-id="9c020-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c020-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="9c020-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="9c020-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="9c020-107">Arguments</span></span>

<span data-ttu-id="9c020-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="9c020-108">`list`: *Record list*</span></span>

<span data-ttu-id="9c020-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="9c020-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="9c020-110">`field`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="9c020-110">`field`: *Field*</span></span>

<span data-ttu-id="9c020-111">A *Karakterlánc* adattípusú mezők érvényes elérési útja a megadott listában.</span><span class="sxs-lookup"><span data-stu-id="9c020-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="9c020-112">`delimiter`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="9c020-112">`delimiter`: *String*</span></span>

<span data-ttu-id="9c020-113">A részkarakterláncok elválasztására használt határolójel.</span><span class="sxs-lookup"><span data-stu-id="9c020-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="9c020-114">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="9c020-114">Return values</span></span>

<span data-ttu-id="9c020-115">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="9c020-115">*String*</span></span>

<span data-ttu-id="9c020-116">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="9c020-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9c020-117">Példa</span><span class="sxs-lookup"><span data-stu-id="9c020-117">Example</span></span>

<span data-ttu-id="9c020-118">Ha megadja a `SPLIT("abc" , 1)` kifejezést **DS** adatforrásként, akkor a `STRINGJOIN (DS, DS.Value, "-")` kifejezés az **"a-b-c"** értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="9c020-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c020-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9c020-119">Additional resources</span></span>

[<span data-ttu-id="9c020-120">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="9c020-120">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]