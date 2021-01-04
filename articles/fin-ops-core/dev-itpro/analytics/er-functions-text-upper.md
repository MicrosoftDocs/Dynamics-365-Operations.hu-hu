---
title: UPPER ER-függvény
description: A témakör tájékoztatást nyújt az UPPER Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: c3e594138ef8e28f1b3aaf333026fa8f9e55cca0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688341"
---
# <a name="upper-er-function"></a><span data-ttu-id="0f2a7-103">UPPER ER-függvény</span><span class="sxs-lookup"><span data-stu-id="0f2a7-103">UPPER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f2a7-104">Az `UPPER` függvény *Karakterlánc* értékként adja vissza a megadott karakterláncot, miután a program nagybetűssé alakította.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f2a7-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="0f2a7-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="0f2a7-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="0f2a7-106">Arguments</span></span>

<span data-ttu-id="0f2a7-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0f2a7-107">`text`: *String*</span></span>

<span data-ttu-id="0f2a7-108">A *Karakterlánc* típus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="0f2a7-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="0f2a7-109">Return values</span></span>

<span data-ttu-id="0f2a7-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="0f2a7-110">*String*</span></span>

<span data-ttu-id="0f2a7-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0f2a7-112">Példa</span><span class="sxs-lookup"><span data-stu-id="0f2a7-112">Example</span></span>

<span data-ttu-id="0f2a7-113">Az `UPPER ("Sample")` a **"SAMPLE"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f2a7-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0f2a7-114">Additional resources</span></span>

[<span data-ttu-id="0f2a7-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="0f2a7-115">Text functions</span></span>](er-functions-category-text.md)
