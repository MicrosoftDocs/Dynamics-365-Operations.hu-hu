---
title: VALUE ER-függvény
description: A témakör tájékoztatást nyújt a VALUE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 7cdaa302e757b54858e36c3716167593383d7071
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561446"
---
# <a name="value-er-function"></a><span data-ttu-id="6004a-103">VALUE ER-függvény</span><span class="sxs-lookup"><span data-stu-id="6004a-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6004a-104">A `VALUE` függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott karakterláncból alakít át.</span><span class="sxs-lookup"><span data-stu-id="6004a-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="6004a-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="6004a-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="6004a-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="6004a-106">Arguments</span></span>

<span data-ttu-id="6004a-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="6004a-107">`text`: *String*</span></span>

<span data-ttu-id="6004a-108">Egy karakterlánc érték, amelyet numerikus értékké kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="6004a-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="6004a-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="6004a-109">Return values</span></span>

<span data-ttu-id="6004a-110">*Valós*</span><span class="sxs-lookup"><span data-stu-id="6004a-110">*Real*</span></span>

<span data-ttu-id="6004a-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="6004a-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6004a-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6004a-112">Usage notes</span></span>

<span data-ttu-id="6004a-113">A vesszőket és a pont karaktereket (.) decimális elválasztóknak tekintik és a vezető kötőjelet (-) negatív jelként használjál.</span><span class="sxs-lookup"><span data-stu-id="6004a-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="6004a-114">Kivételt ad futási időben, ha más nem numerikus karakterek találhatók a megadott karakterláncban.</span><span class="sxs-lookup"><span data-stu-id="6004a-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="6004a-115">1. példa</span><span class="sxs-lookup"><span data-stu-id="6004a-115">Example 1</span></span>

<span data-ttu-id="6004a-116">A `VALUE ("1 234,56")` kivételt dob.</span><span class="sxs-lookup"><span data-stu-id="6004a-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="6004a-117">2. példa</span><span class="sxs-lookup"><span data-stu-id="6004a-117">Example 2</span></span>

<span data-ttu-id="6004a-118">A `VALUE ("1234,56")` az **1234.56** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="6004a-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6004a-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6004a-119">Additional resources</span></span>

[<span data-ttu-id="6004a-120">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="6004a-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]