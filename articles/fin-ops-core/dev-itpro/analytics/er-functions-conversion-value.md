---
title: VALUE ER-függvény
description: A témakör tájékoztatást nyújt a VALUE Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c90772ca1e93500ac45cc52ba92d4169c4d29bad
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042619"
---
# <span data-ttu-id="040e7-103"><a name="VALUE">VALUE ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="040e7-103"><a name="VALUE">VALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="040e7-104">A `VALUE` függvény egy *Valós* értéket ad eredményül, amelyet a rendszer a megadott karakterláncból alakít át.</span><span class="sxs-lookup"><span data-stu-id="040e7-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="040e7-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="040e7-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="040e7-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="040e7-106">Arguments</span></span>

<span data-ttu-id="040e7-107">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="040e7-107">`text`: *String*</span></span>

<span data-ttu-id="040e7-108">Egy karakterlánc érték, amelyet numerikus értékké kell konvertálni.</span><span class="sxs-lookup"><span data-stu-id="040e7-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="040e7-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="040e7-109">Return values</span></span>

<span data-ttu-id="040e7-110">*Valós*</span><span class="sxs-lookup"><span data-stu-id="040e7-110">*Real*</span></span>

<span data-ttu-id="040e7-111">Az eredményül kapott numerikus érték.</span><span class="sxs-lookup"><span data-stu-id="040e7-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="040e7-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="040e7-112">Usage notes</span></span>

<span data-ttu-id="040e7-113">A vesszőket és a pont karaktereket (.) decimális elválasztóknak tekintik és a vezető kötőjelet (-) negatív jelként használjál.</span><span class="sxs-lookup"><span data-stu-id="040e7-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="040e7-114">Kivételt ad futási időben, ha más nem numerikus karakterek találhatók a megadott karakterláncban.</span><span class="sxs-lookup"><span data-stu-id="040e7-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="040e7-115">1. példa</span><span class="sxs-lookup"><span data-stu-id="040e7-115">Example 1</span></span>

<span data-ttu-id="040e7-116">A `VALUE ("1 234,56")` kivételt dob.</span><span class="sxs-lookup"><span data-stu-id="040e7-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="040e7-117">2. példa</span><span class="sxs-lookup"><span data-stu-id="040e7-117">Example 2</span></span>

<span data-ttu-id="040e7-118">A `VALUE ("1234,56")` az **1234.56** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="040e7-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="040e7-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="040e7-119">Additional resources</span></span>

[<span data-ttu-id="040e7-120">Típuskonverziós függvények</span><span class="sxs-lookup"><span data-stu-id="040e7-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
