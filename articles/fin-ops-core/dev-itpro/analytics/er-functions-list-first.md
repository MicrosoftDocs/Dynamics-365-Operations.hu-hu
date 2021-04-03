---
title: FIRST ER-függvény
description: A témakör tájékoztatást nyújt a FIRST Elektronikus jelentéskészítés (ER) függvény használatának módjáról.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: ec94a27776cf1069b50b5437f4d167019fdef120
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564735"
---
# <a name="first-er-function"></a><span data-ttu-id="8bca5-103">FIRST ER-függvény</span><span class="sxs-lookup"><span data-stu-id="8bca5-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8bca5-104">A `FIRST` függvény a megadott lista első rekordját *Tároló (rekord)* értékként adja vissza, ha a lista nem üres.</span><span class="sxs-lookup"><span data-stu-id="8bca5-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="8bca5-105">Ha a lista üres, a függvény kivételt dob.</span><span class="sxs-lookup"><span data-stu-id="8bca5-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bca5-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="8bca5-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="8bca5-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="8bca5-107">Arguments</span></span>

<span data-ttu-id="8bca5-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="8bca5-108">`list`: *Record list*</span></span>

<span data-ttu-id="8bca5-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="8bca5-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="8bca5-110">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="8bca5-110">Return values</span></span>

<span data-ttu-id="8bca5-111">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="8bca5-111">*Container (record)*</span></span>

<span data-ttu-id="8bca5-112">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="8bca5-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="8bca5-113">1. példa</span><span class="sxs-lookup"><span data-stu-id="8bca5-113">Example 1</span></span>

<span data-ttu-id="8bca5-114">Az `FIRST(SPLIT("ABC",1)).Value` kifejezés az **„A”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="8bca5-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="8bca5-115">2. példa</span><span class="sxs-lookup"><span data-stu-id="8bca5-115">Example 2</span></span>

<span data-ttu-id="8bca5-116">A `FIRST(SPLIT("",1)).Value` kifejezés futásidőben kivételt dob.</span><span class="sxs-lookup"><span data-stu-id="8bca5-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8bca5-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8bca5-117">Additional resources</span></span>

[<span data-ttu-id="8bca5-118">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="8bca5-118">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]