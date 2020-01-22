---
title: STRINGJOIN ER-függvény
description: A témakör tájékoztatást nyújt a STRINGJOIN Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 99d50313f8097d43b820ffc1c36eef0097e7ec55
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917189"
---
# <span data-ttu-id="04fab-103"><a name="STRINGJOIN">STRINGJOIN ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="04fab-103"><a name="STRINGJOIN">STRINGJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04fab-104">A `STRINGJOIN` függvény egy *Karakterlánc* értéket ad vissza, amely a megadott lista megadott mezőjének összefűzött értékeiből áll.</span><span class="sxs-lookup"><span data-stu-id="04fab-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="04fab-105">Az értékeket a megadott elválasztó elválaszthatja egymástól.</span><span class="sxs-lookup"><span data-stu-id="04fab-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="04fab-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="04fab-106">Syntax</span></span>

```
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="04fab-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="04fab-107">Arguments</span></span>

<span data-ttu-id="04fab-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="04fab-108">`list`: *Record list*</span></span>

<span data-ttu-id="04fab-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="04fab-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="04fab-110">`field`: *Mező*</span><span class="sxs-lookup"><span data-stu-id="04fab-110">`field`: *Field*</span></span>

<span data-ttu-id="04fab-111">A *Karakterlánc* adattípusú mezők érvényes elérési útja a megadott listában.</span><span class="sxs-lookup"><span data-stu-id="04fab-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="04fab-112">`delimiter`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="04fab-112">`delimiter`: *String*</span></span>

<span data-ttu-id="04fab-113">A részkarakterláncok elválasztására használt határolójel.</span><span class="sxs-lookup"><span data-stu-id="04fab-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="04fab-114">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="04fab-114">Return values</span></span>

<span data-ttu-id="04fab-115">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="04fab-115">*String*</span></span>

<span data-ttu-id="04fab-116">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="04fab-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="04fab-117">Példa</span><span class="sxs-lookup"><span data-stu-id="04fab-117">Example</span></span>

<span data-ttu-id="04fab-118">Ha megadja a `SPLIT("abc" , 1)` kifejezést **DS** adatforrásként, akkor a `STRINGJOIN (DS, DS.Value, "-")` kifejezés az **"a-b-c"** értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="04fab-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04fab-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="04fab-119">Additional resources</span></span>

[<span data-ttu-id="04fab-120">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="04fab-120">List functions</span></span>](er-functions-category-list.md)
