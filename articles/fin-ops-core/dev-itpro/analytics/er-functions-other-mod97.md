---
title: MOD_97 ER-függvény
description: A témakör tájékoztatást nyújt a MOD_97 Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 618cb2b101dd0b1c91b3b1538ef3f87c21e4a70a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563342"
---
# <a name="mod_97-er-function"></a><span data-ttu-id="fe3f2-103">MOD_97 ER-függvény</span><span class="sxs-lookup"><span data-stu-id="fe3f2-103">MOD_97 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe3f2-104">A `MOD_97` függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást MOD97-kifejezésként jelöli, a megadott számlaszám számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="fe3f2-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="fe3f2-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="fe3f2-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="fe3f2-106">Arguments</span></span>

<span data-ttu-id="fe3f2-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fe3f2-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="fe3f2-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="fe3f2-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="fe3f2-109">Return values</span></span>

<span data-ttu-id="fe3f2-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="fe3f2-110">*String*</span></span>

<span data-ttu-id="fe3f2-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="fe3f2-112">Példa</span><span class="sxs-lookup"><span data-stu-id="fe3f2-112">Example</span></span>

<span data-ttu-id="fe3f2-113">A `MOD_97 ("VEND-200002")` a **"20000285"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe3f2-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fe3f2-114">Additional resources</span></span>

[<span data-ttu-id="fe3f2-115">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="fe3f2-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]