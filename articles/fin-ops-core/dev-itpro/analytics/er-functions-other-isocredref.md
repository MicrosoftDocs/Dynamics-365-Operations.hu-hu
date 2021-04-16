---
title: ISOCREDREF ER-függvény
description: A témakör tájékoztatást nyújt az ISOCREDREF Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
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
ms.openlocfilehash: 51adc6392b07ba4061a475f3072fb35452f15ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748317"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="b54df-103">ISOCREDREF ER-függvény</span><span class="sxs-lookup"><span data-stu-id="b54df-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b54df-104">Az `ISOCREDREF` függvény egy olyan *Karakterlánc* értéket ad vissza, amely egy ISO (Nemzetközi Szabványügyi Szervezet) hitelezői hivatkozást jelenít meg a megadott számlaszám betűi és számjegyei alapján.</span><span class="sxs-lookup"><span data-stu-id="b54df-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="b54df-105">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="b54df-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="b54df-106">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="b54df-106">Arguments</span></span>

<span data-ttu-id="b54df-107">`invoice number digits`: *Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b54df-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="b54df-108">A számlaszámok számjegyeit jelölő szöveges érték.</span><span class="sxs-lookup"><span data-stu-id="b54df-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="b54df-109">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="b54df-109">Return values</span></span>

<span data-ttu-id="b54df-110">*Karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="b54df-110">*String*</span></span>

<span data-ttu-id="b54df-111">Az eredményül kapott szövegérték.</span><span class="sxs-lookup"><span data-stu-id="b54df-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b54df-112">Használati megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b54df-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="b54df-113">A nem ISO-szabványos betűkből származó szimbólumok eltávolításához az `invoice number digits` argumentumokat le kell fordítani a függvénynek történő megfeleltetés előtt.</span><span class="sxs-lookup"><span data-stu-id="b54df-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="b54df-114">Példa</span><span class="sxs-lookup"><span data-stu-id="b54df-114">Example</span></span>

<span data-ttu-id="b54df-115">Az `ISOCredRef ("VEND-200002")` a **"RF23VEND-200002"** értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b54df-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b54df-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b54df-116">Additional resources</span></span>

[<span data-ttu-id="b54df-117">Egyéb (üzleti területre jellemző) függvények</span><span class="sxs-lookup"><span data-stu-id="b54df-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]