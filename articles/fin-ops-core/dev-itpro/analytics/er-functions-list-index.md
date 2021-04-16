---
title: INDEX ER-függvény
description: A témakör tájékoztatást nyújt az INDEX Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
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
ms.openlocfilehash: 14f10359a3f20fb9d23639babce764b9ef64243d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750460"
---
# <a name="index-er-function"></a><span data-ttu-id="32d12-103">INDEX ER-függvény</span><span class="sxs-lookup"><span data-stu-id="32d12-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="32d12-104">Az `INDEX` függvény egy *Tároló (rekord)* értéket ad vissza, amely a megadott numerikus index használatával került kiválasztásra a megadott listában.</span><span class="sxs-lookup"><span data-stu-id="32d12-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="32d12-105">Kivétel történik, ha az index kívül esik a listán megadott rekordok tartományán.</span><span class="sxs-lookup"><span data-stu-id="32d12-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="32d12-106">Szintaxis</span><span class="sxs-lookup"><span data-stu-id="32d12-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="32d12-107">Argumentumok</span><span class="sxs-lookup"><span data-stu-id="32d12-107">Arguments</span></span>

<span data-ttu-id="32d12-108">`list`: *Rekordlista*</span><span class="sxs-lookup"><span data-stu-id="32d12-108">`list`: *Record list*</span></span>

<span data-ttu-id="32d12-109">A *Rekordlista* adattípus adatforrásának érvényes elérési útja.</span><span class="sxs-lookup"><span data-stu-id="32d12-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="32d12-110">`index`: *Egész*</span><span class="sxs-lookup"><span data-stu-id="32d12-110">`index`: *Integer*</span></span>

<span data-ttu-id="32d12-111">Numerikus index, amely a kívánt rekord pozícióját jelzi a megadott listában.</span><span class="sxs-lookup"><span data-stu-id="32d12-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="32d12-112">Visszaadott értékek</span><span class="sxs-lookup"><span data-stu-id="32d12-112">Return values</span></span>

<span data-ttu-id="32d12-113">*Tároló (rekord)*</span><span class="sxs-lookup"><span data-stu-id="32d12-113">*Container (record)*</span></span>

<span data-ttu-id="32d12-114">Az eredményül kapott rekordérték.</span><span class="sxs-lookup"><span data-stu-id="32d12-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="32d12-115">1. példa</span><span class="sxs-lookup"><span data-stu-id="32d12-115">Example 1</span></span>

<span data-ttu-id="32d12-116">Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor a `DS.Value` kifejezés a **„B”** szöveges értéket adja vissza a rekordlista második rekordjaként.</span><span class="sxs-lookup"><span data-stu-id="32d12-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="32d12-117">Az `INDEX (SPLIT ("A|B|C", "|"), 2).Value` kifejezés szintén a **„B”** szöveges értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="32d12-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="32d12-118">2. példa</span><span class="sxs-lookup"><span data-stu-id="32d12-118">Example 2</span></span>

<span data-ttu-id="32d12-119">Ha megadja a *Számított mező* típusú **DS** adatforrást, és az tartalmazza a `SPLIT ("A|B|C", "|")` kifejezést, akkor az `INDEX (SPLIT ("A|B|C", "|"), 4).Value` kifejezés kivételt dob futásidőben.</span><span class="sxs-lookup"><span data-stu-id="32d12-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="32d12-120">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="32d12-120">Additional resources</span></span>

[<span data-ttu-id="32d12-121">Lista függvények</span><span class="sxs-lookup"><span data-stu-id="32d12-121">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]