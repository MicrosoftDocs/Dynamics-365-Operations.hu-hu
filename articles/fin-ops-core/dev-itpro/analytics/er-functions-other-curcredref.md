---
title: CURCREDREF ER-függvény
description: A témakör tájékoztatást nyújt a CURCREDREF Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d5f126d71abdc9e3e488b4e8476850dc7763fe5a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567616"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="adb72-103">CURCREDREF ER-függvény</span><span class="sxs-lookup"><span data-stu-id="adb72-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="adb72-104">A `CURCREDREF` függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást képviseli a megadott számlaszám számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="adb72-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="adb72-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="adb72-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="adb72-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="adb72-106">Arguments</span></span>

<span data-ttu-id="adb72-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="adb72-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="adb72-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="adb72-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="adb72-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="adb72-109">Return values</span></span>

<span data-ttu-id="adb72-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="adb72-110">*String*</span></span>

<span data-ttu-id="adb72-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="adb72-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="adb72-112">Példa</span><span class="sxs-lookup"><span data-stu-id="adb72-112">Example</span></span>

<span data-ttu-id="adb72-113">A `CURCredRef ("VEND-200002")` a **"2200002"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="adb72-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="adb72-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="adb72-114">Additional resources</span></span>

[<span data-ttu-id="adb72-115">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="adb72-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]