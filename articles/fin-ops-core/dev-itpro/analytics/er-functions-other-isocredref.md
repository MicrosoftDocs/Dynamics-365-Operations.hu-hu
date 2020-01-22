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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea72d824d3a98d7685a965e981d057991f012a0e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916959"
---
# <span data-ttu-id="cb11e-103"><a name="ISOCREDREF">ISOCREDREF ER-függvény</a></span><span class="sxs-lookup"><span data-stu-id="cb11e-103"><a name="ISOCREDREF">ISOCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cb11e-104">Az `ISOCREDREF` függvény egy olyan *Karakterlánc* értéket ad vissza, amely egy ISO (Nemzetközi Szabványügyi Szervezet) hitelezői hivatkozást jelenít meg a megadott számlaszám betűi és számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="cb11e-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb11e-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="cb11e-105">Syntax</span></span>

```
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="cb11e-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="cb11e-106">Arguments</span></span>

<span data-ttu-id="cb11e-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="cb11e-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="cb11e-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="cb11e-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="cb11e-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="cb11e-109">Return values</span></span>

<span data-ttu-id="cb11e-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="cb11e-110">*String*</span></span>

<span data-ttu-id="cb11e-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="cb11e-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cb11e-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cb11e-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="cb11e-113">A nem ISO-szabványos betűkből származó szimbólumok eltávolításához az `invoice number digits` argumentumokat le kell fordítani a függvénynek történő megfeleltetés előtt.</span><span class="sxs-lookup"><span data-stu-id="cb11e-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="cb11e-114">Példa</span><span class="sxs-lookup"><span data-stu-id="cb11e-114">Example</span></span>

<span data-ttu-id="cb11e-115">Az `ISOCredRef ("VEND-200002")` a **"RF23VEND-200002"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="cb11e-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb11e-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cb11e-116">Additional resources</span></span>

[<span data-ttu-id="cb11e-117">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="cb11e-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
