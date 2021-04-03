---
title: CH_BANK_MOD_10 ER-függvény
description: A témakör tájékoztatást nyújt a CH_BANK_MOD_10 Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 21942fa47b968fa10bfc9b07f269d44e495139fe
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564840"
---
# <a name="ch_bank_mod_10-er-function"></a><span data-ttu-id="1527a-103">CH_BANK_MOD_10 ER-függvény</span><span class="sxs-lookup"><span data-stu-id="1527a-103">CH_BANK_MOD_10 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1527a-104">A `CH_BANK_MOD_10` függvény olyan *Karakterlánc* értéket ad vissza, amely a hitelezői hivatkozást MOD10-kifejezésként jelöli, a megadott számlaszám számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="1527a-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="1527a-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="1527a-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="1527a-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="1527a-106">Arguments</span></span>

<span data-ttu-id="1527a-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="1527a-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="1527a-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="1527a-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="1527a-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="1527a-109">Return values</span></span>

<span data-ttu-id="1527a-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="1527a-110">*String*</span></span>

<span data-ttu-id="1527a-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="1527a-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="1527a-112">Példa</span><span class="sxs-lookup"><span data-stu-id="1527a-112">Example</span></span>

<span data-ttu-id="1527a-113">A `CH_BANK_MOD_10 ("VEND-200002")` a **3** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="1527a-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1527a-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1527a-114">Additional resources</span></span>

[<span data-ttu-id="1527a-115">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="1527a-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]