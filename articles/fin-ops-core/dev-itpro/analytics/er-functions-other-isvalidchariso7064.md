---
title: ISVALIDCHARACTERISO7064 ER-függvény
description: A témakör tájékoztatást nyújt a ISVALIDCHARACTERISO7064 Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 1f102a6a3eafe3b066101370b94fa2f17ad3ad8b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748293"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="64fe6-103">ISVALIDCHARACTERISO7064 ER-függvény</span><span class="sxs-lookup"><span data-stu-id="64fe6-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64fe6-104">A `ISVALIDCHARACTERISO7064` függvény *logikai* **IGAZ** értéket ad vissza, ha a megadott karakterlánc érvényes nemzetközi bankszámlaszámnak (IBAN) felel meg.</span><span class="sxs-lookup"><span data-stu-id="64fe6-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="64fe6-105">Ellenkező esetben **HAMIS** *logikai* eredményt ad.</span><span class="sxs-lookup"><span data-stu-id="64fe6-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="64fe6-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="64fe6-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="64fe6-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="64fe6-107">Arguments</span></span>

<span data-ttu-id="64fe6-108">`text`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="64fe6-108">`text`: *String*</span></span>

<span data-ttu-id="64fe6-109">Egy IBAN értéket képviselő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="64fe6-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="64fe6-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="64fe6-110">Return values</span></span>

<span data-ttu-id="64fe6-111">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="64fe6-111">*String*</span></span>

<span data-ttu-id="64fe6-112">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="64fe6-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="64fe6-113">Példa</span><span class="sxs-lookup"><span data-stu-id="64fe6-113">Example</span></span>

<span data-ttu-id="64fe6-114">Az `ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` **IGAZ** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="64fe6-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="64fe6-115">Az `ISVALIDCHARACTERISO7064 ("AT61")` **HAMIS** értéket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="64fe6-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64fe6-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="64fe6-116">Additional resources</span></span>

[<span data-ttu-id="64fe6-117">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="64fe6-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]