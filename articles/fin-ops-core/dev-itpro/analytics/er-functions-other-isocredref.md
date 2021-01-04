---
title: ISOCREDREF ER-függvény
description: A témakör tájékoztatást nyújt az ISOCREDREF Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 6c9a75cedcf543b318df2850df3e4a60bac2dc6b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680686"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="42408-103">ISOCREDREF ER-függvény</span><span class="sxs-lookup"><span data-stu-id="42408-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42408-104">Az `ISOCREDREF` függvény egy olyan *Karakterlánc* értéket ad vissza, amely egy ISO (Nemzetközi Szabványügyi Szervezet) hitelezői hivatkozást jelenít meg a megadott számlaszám betűi és számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="42408-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="42408-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="42408-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="42408-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="42408-106">Arguments</span></span>

<span data-ttu-id="42408-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="42408-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="42408-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="42408-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="42408-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="42408-109">Return values</span></span>

<span data-ttu-id="42408-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="42408-110">*String*</span></span>

<span data-ttu-id="42408-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="42408-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="42408-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="42408-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="42408-113">A nem ISO-szabványos betűkből származó szimbólumok eltávolításához az `invoice number digits` argumentumokat le kell fordítani a függvénynek történő megfeleltetés előtt.</span><span class="sxs-lookup"><span data-stu-id="42408-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="42408-114">Példa</span><span class="sxs-lookup"><span data-stu-id="42408-114">Example</span></span>

<span data-ttu-id="42408-115">Az `ISOCredRef ("VEND-200002")` a **"RF23VEND-200002"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="42408-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42408-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="42408-116">Additional resources</span></span>

[<span data-ttu-id="42408-117">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="42408-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
