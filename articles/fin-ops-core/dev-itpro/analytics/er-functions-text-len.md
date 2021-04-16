---
title: LEN ER-függvény
description: A témakör tájékoztatást nyújt a LEN Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 394e07a7a573cc4462196b17440f8b0547d8dd48
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746315"
---
# <a name="len-er-function"></a><span data-ttu-id="14dbf-103">LEN ER-függvény</span><span class="sxs-lookup"><span data-stu-id="14dbf-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14dbf-104">a `LEN` függvény olyan *Egész* értéket ad vissza, amely a karakterek számát mutatja a megadott karakterláncban.</span><span class="sxs-lookup"><span data-stu-id="14dbf-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="14dbf-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="14dbf-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="14dbf-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="14dbf-106">Arguments</span></span>

<span data-ttu-id="14dbf-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="14dbf-107">`text`: *String*</span></span>

<span data-ttu-id="14dbf-108">Az eredeti szöveget jelölő *Karakterlánc* érték.</span><span class="sxs-lookup"><span data-stu-id="14dbf-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="14dbf-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="14dbf-109">Return values</span></span>

<span data-ttu-id="14dbf-110">*Egész*</span><span class="sxs-lookup"><span data-stu-id="14dbf-110">*Integer*</span></span>

<span data-ttu-id="14dbf-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="14dbf-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="14dbf-112">Példa</span><span class="sxs-lookup"><span data-stu-id="14dbf-112">Example</span></span>

<span data-ttu-id="14dbf-113">A `LEN ("Sample")` a **6** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="14dbf-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="14dbf-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="14dbf-114">Additional resources</span></span>

[<span data-ttu-id="14dbf-115">Szöveg függvények</span><span class="sxs-lookup"><span data-stu-id="14dbf-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]